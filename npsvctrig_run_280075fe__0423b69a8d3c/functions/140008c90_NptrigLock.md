# NptrigLock

- ea: `0x140008c90`
- end: `0x140008ca8`
- name: `NptrigLock`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`

## import_xrefs

- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008c96`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008c96`

## pseudocode

```c
__int64 __fastcall NptrigLock(__int64 a1)
{
  return FltAcquirePushLockExclusiveEx(a1, 0);
}

```

## disassembly

```asm
0x140008c90  sub     rsp, 28h
0x140008c94  xor     edx, edx
0x140008c96  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140008c9d  nop     dword ptr [rax+rax+00h]
0x140008ca2  add     rsp, 28h
0x140008ca6  retn
```
