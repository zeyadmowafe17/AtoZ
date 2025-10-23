# ===== Stage 1: Base image =====
FROM python:3.11-slim

# Set working directory inside container
WORKDIR /app

# Copy dependency files first (for caching)
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app
COPY . .

# Expose the FastAPI port
EXPOSE 8000

# Set environment variables (Railway will override these)
ENV PYTHONUNBUFFERED=1
ENV PORT=8000

# Command to start FastAPI with Uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
