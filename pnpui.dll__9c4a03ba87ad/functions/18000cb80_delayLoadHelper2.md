# __delayLoadHelper2

- ea: `0x18000cb80`
- end: `0x18000cbb6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c60`
- `0x180001cfd`
- `0x180001d88`
- `0x180001e13`
- `0x180001e9e`
- `0x180001f5f`
- `0x180002032`
- `0x1800020bd`
- `0x180002244`
- `0x1800022f3`
- `0x1800023b4`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000cbab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000cbab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000cb8a`

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
0x18000cb80  sub     rsp, 38h
0x18000cb84  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000cb8a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000cb91  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000cb98  mov     [rsp+38h+var_10], eax
0x18000cb9c  mov     [rsp+38h+var_18], rdx
0x18000cba1  mov     rdx, rcx
0x18000cba4  lea     rcx, __ImageBase
0x18000cbab  call    cs:__imp_ResolveDelayLoadedAPI
0x18000cbb1  add     rsp, 38h
0x18000cbb5  retn
```
