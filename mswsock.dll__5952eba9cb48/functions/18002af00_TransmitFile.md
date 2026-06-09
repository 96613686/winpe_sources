# TransmitFile

- ea: `0x18002af00`
- end: `0x18002afad`
- name: `TransmitFile`
- size: `173`
- prototype: `BOOL __stdcall(SOCKET hSocket, HANDLE hFile, DWORD nNumberOfBytesToWrite, DWORD nNumberOfBytesPerSend, LPOVERLAPPED lpOverlapped, LPTRANSMIT_FILE_BUFFERS lpTransmitBuffers, DWORD dwReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180051ff0`

## callees

- `0x18002af00`
- `0x180053010`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x18002af53`
- `WS2_32!WSAIoctl` at `0x18002af53`

## pseudocode

```c

```
