# __delayLoadHelper2

- ea: `0x18000d7b0`
- end: `0x18000d7e6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b70`
- `0x180001bfb`
- `0x180001c86`
- `0x180001d7d`
- `0x180001e08`
- `0x180001ea5`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000d7db`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000d7db`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000d7ba`

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
0x18000d7b0  sub     rsp, 38h
0x18000d7b4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000d7ba  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000d7c1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000d7c8  mov     [rsp+38h+var_10], eax
0x18000d7cc  mov     [rsp+38h+var_18], rdx
0x18000d7d1  mov     rdx, rcx
0x18000d7d4  lea     rcx, __ImageBase
0x18000d7db  call    cs:__imp_ResolveDelayLoadedAPI
0x18000d7e1  add     rsp, 38h
0x18000d7e5  retn
```
