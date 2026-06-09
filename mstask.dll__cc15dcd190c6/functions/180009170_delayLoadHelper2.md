# __delayLoadHelper2

- ea: `0x180009170`
- end: `0x1800091a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a950`
- `0x18000a9db`
- `0x18000aac0`
- `0x18000ab4b`
- `0x18000abe6`
- `0x18000ac95`
- `0x18000ad20`
- `0x18000adab`
- `0x18000ae36`
- `0x18000aed3`
- `0x18000af5e`
- `0x18000b1cf`
- `0x18000b2ea`
- `0x18000b375`
- `0x18000b424`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000919b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000919b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000917a`

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
0x180009170  sub     rsp, 38h
0x180009174  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000917a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180009181  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180009188  mov     [rsp+38h+var_10], eax
0x18000918c  mov     [rsp+38h+var_18], rdx
0x180009191  mov     rdx, rcx
0x180009194  lea     rcx, __ImageBase
0x18000919b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800091a1  add     rsp, 38h
0x1800091a5  retn
```
