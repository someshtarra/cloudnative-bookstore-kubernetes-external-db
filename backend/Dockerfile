FROM node:20-alpine

WORKDIR /app

# Install production dependencies
COPY package*.json ./
RUN npm ci --omit=dev

# Copy application files with ownership set to non-root node user
COPY --chown=node:node . .

# Use non-root user for security
USER node

# Expose unprivileged application port
EXPOSE 5000

CMD ["node", "index.js"]
