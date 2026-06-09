# __delayLoadHelper2

- ea: `0x1800149c0`
- end: `0x1800149f6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800026a0`
- `0x18000272b`
- `0x1800027ec`
- `0x18000289b`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800149eb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800149eb`
- `KERNEL32!DelayLoadFailureHook` at `0x1800149ca`

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
0x1800149c0  sub     rsp, 38h
0x1800149c4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800149ca  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800149d1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800149d8  mov     [rsp+38h+var_10], eax
0x1800149dc  mov     [rsp+38h+var_18], rdx
0x1800149e1  mov     rdx, rcx
0x1800149e4  lea     rcx, __ImageBase
0x1800149eb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800149f1  add     rsp, 38h
0x1800149f5  retn
```
