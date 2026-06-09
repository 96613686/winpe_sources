# WINRT_IMPL_SetThreadpoolWaitEx

- ea: `0x180002504`
- end: `0x18000250a`
- name: `WINRT_IMPL_SetThreadpoolWaitEx`
- size: `6`
- prototype: `BOOL __stdcall(PTP_WAIT pwa, HANDLE h, PFILETIME pftTimeout, PVOID Reserved)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001aa44`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x180002504`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WINRT_IMPL_SetThreadpoolWaitEx(PTP_WAIT pwa, HANDLE h, PFILETIME pftTimeout, PVOID Reserved)
{
  return SetThreadpoolWaitEx(pwa, h, pftTimeout, Reserved);
}

```

## disassembly

```asm
0x180002504  jmp     cs:__imp_SetThreadpoolWaitEx
```
