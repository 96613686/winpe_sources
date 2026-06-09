# __delayLoadHelper2

- ea: `0x18000d4b0`
- end: `0x18000d4e6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a3e`
- `0x180002adb`
- `0x180002b78`
- `0x180002c03`
- `0x180002cb2`
- `0x180002d4f`
- `0x180002e2e`
- `0x180002f32`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000d4db`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000d4db`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000d4ba`

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
0x18000d4b0  sub     rsp, 38h
0x18000d4b4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000d4ba  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000d4c1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000d4c8  mov     [rsp+38h+var_10], eax
0x18000d4cc  mov     [rsp+38h+var_18], rdx
0x18000d4d1  mov     rdx, rcx
0x18000d4d4  lea     rcx, __ImageBase
0x18000d4db  call    cs:__imp_ResolveDelayLoadedAPI
0x18000d4e1  add     rsp, 38h
0x18000d4e5  retn
```
