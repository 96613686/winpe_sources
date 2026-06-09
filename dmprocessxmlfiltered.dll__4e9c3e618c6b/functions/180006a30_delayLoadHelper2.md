# __delayLoadHelper2

- ea: `0x180006a30`
- end: `0x180006a66`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e60`
- `0x180001eeb`
- `0x18000200a`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180006a5b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180006a5b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180006a3a`

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
0x180006a30  sub     rsp, 38h
0x180006a34  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180006a3a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180006a41  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180006a48  mov     [rsp+38h+var_10], eax
0x180006a4c  mov     [rsp+38h+var_18], rdx
0x180006a51  mov     rdx, rcx
0x180006a54  lea     rcx, __ImageBase
0x180006a5b  call    cs:__imp_ResolveDelayLoadedAPI
0x180006a61  add     rsp, 38h
0x180006a65  retn
```
