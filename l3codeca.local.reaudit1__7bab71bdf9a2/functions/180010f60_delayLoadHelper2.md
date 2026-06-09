# __delayLoadHelper2

- ea: `0x180010f60`
- end: `0x180010f96`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d2e`
- `0x180001db9`
- `0x180001e44`
- `0x180001ecf`
- `0x180001f5a`
- `0x180002009`
- `0x1800020a6`
- `0x180002131`
- `0x1800021bc`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180010f8b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180010f8b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180010f6a`

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
0x180010f60  sub     rsp, 38h
0x180010f64  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180010f6a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180010f71  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180010f78  mov     [rsp+38h+var_10], eax
0x180010f7c  mov     [rsp+38h+var_18], rdx
0x180010f81  mov     rdx, rcx
0x180010f84  lea     rcx, __ImageBase
0x180010f8b  call    cs:__imp_ResolveDelayLoadedAPI
0x180010f91  add     rsp, 38h
0x180010f95  retn
```
