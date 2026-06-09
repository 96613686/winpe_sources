# __delayLoadHelper2

- ea: `0x1800015c0`
- end: `0x1800015f6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800032c0`
- `0x180003381`
- `0x180003430`
- `0x180003539`
- `0x1800035c4`
- `0x18000364f`
- `0x1800036fe`
- `0x180003819`
- `0x1800038a4`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800015eb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800015eb`
- `KERNEL32!DelayLoadFailureHook` at `0x1800015ca`

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
0x1800015c0  sub     rsp, 38h
0x1800015c4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800015ca  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800015d1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800015d8  mov     [rsp+38h+var_10], eax
0x1800015dc  mov     [rsp+38h+var_18], rdx
0x1800015e1  mov     rdx, rcx
0x1800015e4  lea     rcx, __ImageBase
0x1800015eb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800015f1  add     rsp, 38h
0x1800015f5  retn
```
