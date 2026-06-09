# __delayLoadHelper2

- ea: `0x14000dd40`
- end: `0x14000dd76`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400020e0`
- `0x14000216b`
- `0x1400021f6`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000dd6b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000dd6b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000dd4a`

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
0x14000dd40  sub     rsp, 38h
0x14000dd44  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000dd4a  mov     r9, cs:__imp_DelayLoadFailureHook
0x14000dd51  mov     r8, cs:__pfnDefaultDliFailureHook2
0x14000dd58  mov     [rsp+38h+var_10], eax
0x14000dd5c  mov     [rsp+38h+var_18], rdx
0x14000dd61  mov     rdx, rcx
0x14000dd64  lea     rcx, __ImageBase
0x14000dd6b  call    cs:__imp_ResolveDelayLoadedAPI
0x14000dd71  add     rsp, 38h
0x14000dd75  retn
```
