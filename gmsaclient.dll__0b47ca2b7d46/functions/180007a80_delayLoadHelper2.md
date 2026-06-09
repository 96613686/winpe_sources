# __delayLoadHelper2

- ea: `0x180007a80`
- end: `0x180007abd`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ce6`
- `0x180001d71`
- `0x180001e0e`
- `0x180001e99`
- `0x180001f48`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007aab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007aab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180007a8a`

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
0x180007a80  sub     rsp, 38h
0x180007a84  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180007a8a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180007a91  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180007a98  mov     [rsp+38h+var_10], eax
0x180007a9c  mov     [rsp+38h+var_18], rdx
0x180007aa1  mov     rdx, rcx
0x180007aa4  lea     rcx, __ImageBase
0x180007aab  call    cs:__imp_ResolveDelayLoadedAPI
0x180007ab2  nop     dword ptr [rax+rax+00h]
0x180007ab7  add     rsp, 38h
0x180007abb  retn
```
