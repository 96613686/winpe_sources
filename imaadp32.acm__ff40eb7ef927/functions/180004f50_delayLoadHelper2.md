# __delayLoadHelper2

- ea: `0x180004f50`
- end: `0x180004f86`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d06`
- `0x180001d91`
- `0x180001e40`
- `0x180001ecb`
- `0x180001f56`
- `0x180001ff3`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180004f7b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180004f7b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180004f5a`

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
0x180004f50  sub     rsp, 38h
0x180004f54  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180004f5a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180004f61  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180004f68  mov     [rsp+38h+var_10], eax
0x180004f6c  mov     [rsp+38h+var_18], rdx
0x180004f71  mov     rdx, rcx
0x180004f74  lea     rcx, __ImageBase
0x180004f7b  call    cs:__imp_ResolveDelayLoadedAPI
0x180004f81  add     rsp, 38h
0x180004f85  retn
```
