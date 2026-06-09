# __delayLoadHelper2

- ea: `0x180006080`
- end: `0x1800060b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800071e0`
- `0x1800072a1`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800060ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800060ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000608a`

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
0x180006080  sub     rsp, 38h
0x180006084  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000608a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180006091  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180006098  mov     [rsp+38h+var_10], eax
0x18000609c  mov     [rsp+38h+var_18], rdx
0x1800060a1  mov     rdx, rcx
0x1800060a4  lea     rcx, __ImageBase
0x1800060ab  call    cs:__imp_ResolveDelayLoadedAPI
0x1800060b1  add     rsp, 38h
0x1800060b5  retn
```
