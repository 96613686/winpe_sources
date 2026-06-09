# NptrigUnlock

- ea: `0x140008c70`
- end: `0x140008c88`
- name: `NptrigUnlock`
- size: `24`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x140008c76`
- `FLTMGR!FltReleasePushLockEx` at `0x140008c76`

## pseudocode

```c
__int64 __fastcall NptrigUnlock(__int64 a1)
{
  return FltReleasePushLockEx(a1, 0);
}

```

## disassembly

```asm
0x140008c70  sub     rsp, 28h
0x140008c74  xor     edx, edx
0x140008c76  call    cs:__imp_FltReleasePushLockEx
0x140008c7d  nop     dword ptr [rax+rax+00h]
0x140008c82  add     rsp, 28h
0x140008c86  retn
```
