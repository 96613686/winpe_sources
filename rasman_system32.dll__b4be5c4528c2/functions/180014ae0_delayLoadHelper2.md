# __delayLoadHelper2

- ea: `0x180014ae0`
- end: `0x180014b1d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180016010`
- `0x18001609b`
- `0x18001615c`
- `0x18001620b`
- `0x1800162cc`
- `0x18001637b`
- `0x180016406`
- `0x1800164c7`
- `0x180016552`
- `0x180016601`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180014b0b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180014b0b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180014aea`

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
0x180014ae0  sub     rsp, 38h
0x180014ae4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180014aea  mov     r9, cs:__imp_DelayLoadFailureHook
0x180014af1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180014af8  mov     [rsp+38h+var_10], eax
0x180014afc  mov     [rsp+38h+var_18], rdx
0x180014b01  mov     rdx, rcx
0x180014b04  lea     rcx, __ImageBase
0x180014b0b  call    cs:__imp_ResolveDelayLoadedAPI
0x180014b12  nop     dword ptr [rax+rax+00h]
0x180014b17  add     rsp, 38h
0x180014b1b  retn
```
