# AsyncUnbufferedFileReader::CancelPendingIos(void)

- ea: `0x1400a9fb4`
- end: `0x1400aa31d`
- name: `?CancelPendingIos@AsyncUnbufferedFileReader@@AEAAXXZ`
- size: `873`
- prototype: `void __fastcall(AsyncUnbufferedFileReader *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400aa330`
- `0x1400ad968`
- `0x1400adc50`

## callees

- `0x14000cb00`
- `0x14000cdc0`
- `0x14000e34c`
- `0x1400a8e18`
- `0x1400a9fb4`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!CancelIoEx` at `0x1400aa106`
- `KERNEL32!CancelIoEx` at `0x1400aa106`
- `KERNEL32!GetOverlappedResult` at `0x1400aa217`
- `KERNEL32!GetOverlappedResult` at `0x1400aa217`
- `KERNEL32!GetLastError` at `0x1400aa11a`
- `KERNEL32!GetLastError` at `0x1400aa22b`
- `KERNEL32!GetLastError` at `0x1400aa11a`
- `KERNEL32!GetLastError` at `0x1400aa22b`
- `KERNEL32!GetCurrentThreadId` at `0x1400aa134`
- `KERNEL32!GetCurrentThreadId` at `0x1400aa243`
- `KERNEL32!GetCurrentThreadId` at `0x1400aa134`
- `KERNEL32!GetCurrentThreadId` at `0x1400aa243`

## string_xrefs

- `0x1400aa2b5`: `(Ignored) Failed to wait for I/O to complete. Error:%?`
- `0x1400aa072`: `this:%p state:%? currentCacheBufferIndex:%? currentPendingBufferIndex:%? currentIoBufferIndex:%? currentBufferSize:%? queueDepth:%? numIoBuffers:%? asyncEof:%? `
- `0x1400a9fdf`: `AsyncUnbufferedFileReader::CancelPendingIos`
- `0x1400aa182`: `AsyncUnbufferedFileReader::CancelPendingIos`
- `0x1400aa1d9`: `AsyncUnbufferedFileReader::CancelPendingIos`
- `0x1400aa153`: `AsyncUnbufferedFileReader::CancelPendingIos`
- `0x1400aa262`: `AsyncUnbufferedFileReader::CancelPendingIos`

## pseudocode

```c

```
