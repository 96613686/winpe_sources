# __delayLoadHelper2

- ea: `0x180005080`
- end: `0x1800050b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000777a`
- `0x18000786e`
- `0x1800078f9`
- `0x1800079d0`
- `0x180007ad3`
- `0x180007b5e`
- `0x180007be9`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800050ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800050ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000508a`

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
0x180005080  sub     rsp, 38h
0x180005084  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000508a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180005091  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180005098  mov     [rsp+38h+var_10], eax
0x18000509c  mov     [rsp+38h+var_18], rdx
0x1800050a1  mov     rdx, rcx
0x1800050a4  lea     rcx, __ImageBase
0x1800050ab  call    cs:__imp_ResolveDelayLoadedAPI
0x1800050b1  add     rsp, 38h
0x1800050b5  retn
```
