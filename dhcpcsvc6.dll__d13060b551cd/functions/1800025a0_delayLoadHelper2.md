# __delayLoadHelper2

- ea: `0x1800025a0`
- end: `0x1800025d6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004304`
- `0x18000438f`
- `0x1800044b6`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800025cb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800025cb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800025aa`

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
0x1800025a0  sub     rsp, 38h
0x1800025a4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800025aa  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800025b1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800025b8  mov     [rsp+38h+var_10], eax
0x1800025bc  mov     [rsp+38h+var_18], rdx
0x1800025c1  mov     rdx, rcx
0x1800025c4  lea     rcx, __ImageBase
0x1800025cb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800025d1  add     rsp, 38h
0x1800025d5  retn
```
