# __delayLoadHelper2

- ea: `0x18000b340`
- end: `0x18000b376`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019fa`
- `0x180001a85`
- `0x180001b10`
- `0x180001bad`
- `0x180001ca4`
- `0x180001d2f`
- `0x180001dcc`
- `0x180001e57`
- `0x180001f96`
- `0x18000211d`
- `0x1800021cc`
- `0x18000227b`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000b36b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000b36b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000b34a`

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
0x18000b340  sub     rsp, 38h
0x18000b344  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000b34a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000b351  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000b358  mov     [rsp+38h+var_10], eax
0x18000b35c  mov     [rsp+38h+var_18], rdx
0x18000b361  mov     rdx, rcx
0x18000b364  lea     rcx, __ImageBase
0x18000b36b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000b371  add     rsp, 38h
0x18000b375  retn
```
