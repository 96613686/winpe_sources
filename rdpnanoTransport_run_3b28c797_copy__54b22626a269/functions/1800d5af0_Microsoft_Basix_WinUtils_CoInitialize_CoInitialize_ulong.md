# Microsoft::Basix::WinUtils::CoInitialize::CoInitialize(ulong)

- ea: `0x1800d5af0`
- end: `0x1800d5d65`
- name: `??0CoInitialize@WinUtils@Basix@Microsoft@@QEAA@K@Z`
- size: `629`
- prototype: `__int64 __fastcall(Microsoft::Basix::WinUtils::CoInitialize *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800d601c`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x1800191b4`
- `0x18001bbdc`
- `0x180024700`
- `0x180027b84`
- `0x1800d5af0`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `ole32!CoInitializeEx` at `0x1800d5b26`
- `ole32!CoInitializeEx` at `0x1800d5c9e`
- `ole32!CoInitializeEx` at `0x1800d5b26`
- `ole32!CoInitializeEx` at `0x1800d5c9e`

## string_xrefs

- `0x1800d5b7c`: `We desired multithreaded COM, but COM was already initialized as apartment threaded on this thread. Check if you are running this method on the UI thread (and whether that is appropriate).`
- `0x1800d5c22`: `We desired apartment threaded COM, but COM was already initialized as multithreaded on this thread. Verify if you need additional thread synchronization!`
- `0x1800d5cfe`: `Failed to initialize COM`

## pseudocode

```c

```
