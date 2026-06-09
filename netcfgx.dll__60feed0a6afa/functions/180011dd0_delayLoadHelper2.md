# __delayLoadHelper2

- ea: `0x180011dd0`
- end: `0x180011e06`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002afd`
- `0x180002b76`
- `0x180002c25`
- `0x180002f02`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180011dfb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180011dfb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180011dda`

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
0x180011dd0  sub     rsp, 38h
0x180011dd4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180011dda  mov     r9, cs:__imp_DelayLoadFailureHook
0x180011de1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180011de8  mov     [rsp+38h+var_10], eax
0x180011dec  mov     [rsp+38h+var_18], rdx
0x180011df1  mov     rdx, rcx
0x180011df4  lea     rcx, __ImageBase
0x180011dfb  call    cs:__imp_ResolveDelayLoadedAPI
0x180011e01  add     rsp, 38h
0x180011e05  retn
```
