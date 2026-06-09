# __delayLoadHelper2

- ea: `0x1800079c0`
- end: `0x1800079f6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a8c0`
- `0x18000a96f`
- `0x18000a9fa`
- `0x18000aa85`
- `0x18000aba0`
- `0x18000ac4f`
- `0x18000acda`
- `0x18000ad9b`
- `0x18000aeec`
- `0x18000b03d`
- `0x18000b0c8`
- `0x18000b1ad`
- `0x18000b25c`
- `0x18000b2e7`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x1800079ca`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800079eb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800079eb`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(__int64 a1, __int64 a2)
{
  return ResolveDelayLoadedAPI(
           &_ImageBase,
           a1,
           _pfnDefaultDliFailureHook2,
           DelayLoadFailureHook,
           a2,
           _ResolveDelayLoadedAPIFlags);
}

```

## disassembly

```asm
0x1800079c0  sub     rsp, 38h
0x1800079c4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800079ca  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800079d1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800079d8  mov     [rsp+38h+var_10], eax
0x1800079dc  mov     [rsp+38h+var_18], rdx
0x1800079e1  mov     rdx, rcx
0x1800079e4  lea     rcx, __ImageBase
0x1800079eb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800079f1  add     rsp, 38h
0x1800079f5  retn
```
