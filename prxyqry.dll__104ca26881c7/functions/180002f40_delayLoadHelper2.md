# __delayLoadHelper2

- ea: `0x180002f40`
- end: `0x180002f76`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001294`
- `0x180001331`
- `0x1800013e0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180002f6b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180002f6b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180002f4a`

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
0x180002f40  sub     rsp, 38h
0x180002f44  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180002f4a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180002f51  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180002f58  mov     [rsp+38h+var_10], eax
0x180002f5c  mov     [rsp+38h+var_18], rdx
0x180002f61  mov     rdx, rcx
0x180002f64  lea     rcx, __ImageBase
0x180002f6b  call    cs:__imp_ResolveDelayLoadedAPI
0x180002f71  add     rsp, 38h
0x180002f75  retn
```
