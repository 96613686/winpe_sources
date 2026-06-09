# CloseThreadpoolWait_0

- ea: `0x1800024e0`
- end: `0x1800024e6`
- name: `CloseThreadpoolWait_0`
- size: `6`
- prototype: `void __stdcall(PTP_WAIT pwa)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a6c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800024e0`

## pseudocode

```c
// attributes: thunk
void __stdcall CloseThreadpoolWait_0(PTP_WAIT pwa)
{
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x1800024e0  jmp     cs:__imp_CloseThreadpoolWait
```
