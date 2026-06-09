# __delayLoadHelper2

- ea: `0x18000c580`
- end: `0x18000c5b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000278a`
- `0x180002827`
- `0x1800028ed`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000c5ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000c5ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000c58a`

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
0x18000c580  sub     rsp, 38h
0x18000c584  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000c58a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000c591  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000c598  mov     [rsp+38h+var_10], eax
0x18000c59c  mov     [rsp+38h+var_18], rdx
0x18000c5a1  mov     rdx, rcx
0x18000c5a4  lea     rcx, __ImageBase
0x18000c5ab  call    cs:__imp_ResolveDelayLoadedAPI
0x18000c5b1  add     rsp, 38h
0x18000c5b5  retn
```
