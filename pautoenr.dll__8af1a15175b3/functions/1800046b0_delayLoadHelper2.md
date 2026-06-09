# __delayLoadHelper2

- ea: `0x1800046b0`
- end: `0x1800046e6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180005c00`
- `0x180005caf`
- `0x180005dca`
- `0x180005ed3`
- `0x180005f70`
- `0x18000601f`
- `0x1800061b8`
- `0x180006243`
- `0x1800062ce`
- `0x18000637d`
- `0x180006498`
- `0x180006535`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800046db`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800046db`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800046ba`

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
0x1800046b0  sub     rsp, 38h
0x1800046b4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800046ba  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800046c1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800046c8  mov     [rsp+38h+var_10], eax
0x1800046cc  mov     [rsp+38h+var_18], rdx
0x1800046d1  mov     rdx, rcx
0x1800046d4  lea     rcx, __ImageBase
0x1800046db  call    cs:__imp_ResolveDelayLoadedAPI
0x1800046e1  add     rsp, 38h
0x1800046e5  retn
```
