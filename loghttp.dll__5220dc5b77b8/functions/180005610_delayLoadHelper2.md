# __delayLoadHelper2

- ea: `0x180005610`
- end: `0x180005646`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002fb0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000563b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000563b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000561a`

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
0x180005610  sub     rsp, 38h
0x180005614  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000561a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180005621  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180005628  mov     [rsp+38h+var_10], eax
0x18000562c  mov     [rsp+38h+var_18], rdx
0x180005631  mov     rdx, rcx
0x180005634  lea     rcx, __ImageBase
0x18000563b  call    cs:__imp_ResolveDelayLoadedAPI
0x180005641  add     rsp, 38h
0x180005645  retn
```
