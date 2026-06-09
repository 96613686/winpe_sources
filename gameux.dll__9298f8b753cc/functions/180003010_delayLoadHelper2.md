# __delayLoadHelper2

- ea: `0x180003010`
- end: `0x180003046`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a90`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x18000301a`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18000303b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18000303b`

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
0x180003010  sub     rsp, 38h
0x180003014  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000301a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003021  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003028  mov     [rsp+38h+var_10], eax
0x18000302c  mov     [rsp+38h+var_18], rdx
0x180003031  mov     rdx, rcx
0x180003034  lea     rcx, __ImageBase
0x18000303b  call    cs:__imp_ResolveDelayLoadedAPI
0x180003041  add     rsp, 38h
0x180003045  retn
```
