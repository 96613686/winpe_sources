# SetThreadpoolWait_0

- ea: `0x1800024f8`
- end: `0x1800024fe`
- name: `SetThreadpoolWait_0`
- size: `6`
- prototype: `void __stdcall(PTP_WAIT pwa, HANDLE h, PFILETIME pftTimeout)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a6ec`
- `0x18001aa44`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800024f8`

## pseudocode

```c
// attributes: thunk
void __stdcall SetThreadpoolWait_0(PTP_WAIT pwa, HANDLE h, PFILETIME pftTimeout)
{
  SetThreadpoolWait(pwa, h, pftTimeout);
}

```

## disassembly

```asm
0x1800024f8  jmp     cs:__imp_SetThreadpoolWait
```
