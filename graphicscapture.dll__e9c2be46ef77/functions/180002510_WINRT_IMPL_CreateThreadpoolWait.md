# WINRT_IMPL_CreateThreadpoolWait

- ea: `0x180002510`
- end: `0x180002516`
- name: `WINRT_IMPL_CreateThreadpoolWait`
- size: `6`
- prototype: `PTP_WAIT __stdcall(PTP_WAIT_CALLBACK pfnwa, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a6ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180002510`

## pseudocode

```c
// attributes: thunk
PTP_WAIT __stdcall WINRT_IMPL_CreateThreadpoolWait(PTP_WAIT_CALLBACK pfnwa, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)
{
  return CreateThreadpoolWait(pfnwa, pv, pcbe);
}

```

## disassembly

```asm
0x180002510  jmp     cs:__imp_CreateThreadpoolWait
```
