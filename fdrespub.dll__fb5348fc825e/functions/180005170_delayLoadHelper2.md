# __delayLoadHelper2

- ea: `0x180005170`
- end: `0x1800051a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001950`
- `0x1800019db`
- `0x180001a66`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000519b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000519b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000517a`

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
0x180005170  sub     rsp, 38h
0x180005174  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000517a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180005181  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180005188  mov     [rsp+38h+var_10], eax
0x18000518c  mov     [rsp+38h+var_18], rdx
0x180005191  mov     rdx, rcx
0x180005194  lea     rcx, __ImageBase
0x18000519b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800051a1  add     rsp, 38h
0x1800051a5  retn
```
