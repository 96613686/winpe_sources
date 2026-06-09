# RtdspUnlock

- ea: `0x140001760`
- end: `0x140001778`
- name: `RtdspUnlock`
- size: `24`
- prototype: `LONG __fastcall(struct _KMUTANT *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140008920`
- `0x140009230`
- `0x14000a320`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140001766`
- `ntoskrnl!KeReleaseMutex` at `0x140001766`

## pseudocode

```c
LONG __fastcall RtdspUnlock(struct _KMUTANT *a1)
{
  return KeReleaseMutex(a1, 0);
}

```

## disassembly

```asm
0x140001760  sub     rsp, 28h
0x140001764  xor     edx, edx; Wait
0x140001766  call    cs:__imp_KeReleaseMutex
0x14000176d  nop     dword ptr [rax+rax+00h]
0x140001772  add     rsp, 28h
0x140001776  retn
```
