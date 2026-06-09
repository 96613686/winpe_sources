# __delayLoadHelper2

- ea: `0x18000d050`
- end: `0x18000d086`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fbe0`
- `0x18000fc8f`
- `0x18000fd50`
- `0x18000fded`
- `0x18000fec0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000d07b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000d07b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000d05a`

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
0x18000d050  sub     rsp, 38h
0x18000d054  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000d05a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000d061  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000d068  mov     [rsp+38h+var_10], eax
0x18000d06c  mov     [rsp+38h+var_18], rdx
0x18000d071  mov     rdx, rcx
0x18000d074  lea     rcx, __ImageBase
0x18000d07b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000d081  add     rsp, 38h
0x18000d085  retn
```
