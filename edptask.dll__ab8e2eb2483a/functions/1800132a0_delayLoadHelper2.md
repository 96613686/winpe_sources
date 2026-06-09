# __delayLoadHelper2

- ea: `0x1800132a0`
- end: `0x1800132d6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002120`
- `0x1800021ab`
- `0x180002236`
- `0x1800022c1`
- `0x18000234c`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800132cb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800132cb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800132aa`

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
0x1800132a0  sub     rsp, 38h
0x1800132a4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800132aa  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800132b1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800132b8  mov     [rsp+38h+var_10], eax
0x1800132bc  mov     [rsp+38h+var_18], rdx
0x1800132c1  mov     rdx, rcx
0x1800132c4  lea     rcx, __ImageBase
0x1800132cb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800132d1  add     rsp, 38h
0x1800132d5  retn
```
