# __delayLoadHelper2

- ea: `0x180003d10`
- end: `0x180003d46`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018c0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003d3b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003d3b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180003d1a`

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
0x180003d10  sub     rsp, 38h
0x180003d14  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180003d1a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003d21  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003d28  mov     [rsp+38h+var_10], eax
0x180003d2c  mov     [rsp+38h+var_18], rdx
0x180003d31  mov     rdx, rcx
0x180003d34  lea     rcx, __ImageBase
0x180003d3b  call    cs:__imp_ResolveDelayLoadedAPI
0x180003d41  add     rsp, 38h
0x180003d45  retn
```
