# __delayLoadHelper2

- ea: `0x180007f20`
- end: `0x180007f56`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002370`
- `0x18000245c`
- `0x1800025a6`
- `0x180002631`
- `0x1800026bc`
- `0x18000276b`
- `0x180002808`
- `0x180002947`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007f4b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007f4b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180007f2a`

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
0x180007f20  sub     rsp, 38h
0x180007f24  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180007f2a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180007f31  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180007f38  mov     [rsp+38h+var_10], eax
0x180007f3c  mov     [rsp+38h+var_18], rdx
0x180007f41  mov     rdx, rcx
0x180007f44  lea     rcx, __ImageBase
0x180007f4b  call    cs:__imp_ResolveDelayLoadedAPI
0x180007f51  add     rsp, 38h
0x180007f55  retn
```
