# __delayLoadHelper2

- ea: `0x1400058b0`
- end: `0x1400058e6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002200`
- `0x1400022c1`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x1400058ba`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1400058db`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1400058db`

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
0x1400058b0  sub     rsp, 38h
0x1400058b4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1400058ba  mov     r9, cs:__imp_DelayLoadFailureHook
0x1400058c1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1400058c8  mov     [rsp+38h+var_10], eax
0x1400058cc  mov     [rsp+38h+var_18], rdx
0x1400058d1  mov     rdx, rcx
0x1400058d4  lea     rcx, __ImageBase
0x1400058db  call    cs:__imp_ResolveDelayLoadedAPI
0x1400058e1  add     rsp, 38h
0x1400058e5  retn
```
