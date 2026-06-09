# __delayLoadHelper2

- ea: `0x1800063b0`
- end: `0x1800063e6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d26`
- `0x180001db1`
- `0x180001e60`
- `0x180001eeb`
- `0x180001f76`
- `0x180002013`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800063db`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800063db`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800063ba`

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
0x1800063b0  sub     rsp, 38h
0x1800063b4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800063ba  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800063c1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800063c8  mov     [rsp+38h+var_10], eax
0x1800063cc  mov     [rsp+38h+var_18], rdx
0x1800063d1  mov     rdx, rcx
0x1800063d4  lea     rcx, __ImageBase
0x1800063db  call    cs:__imp_ResolveDelayLoadedAPI
0x1800063e1  add     rsp, 38h
0x1800063e5  retn
```
