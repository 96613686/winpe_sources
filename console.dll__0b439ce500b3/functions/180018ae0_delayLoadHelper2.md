# __delayLoadHelper2

- ea: `0x180018ae0`
- end: `0x180018b1d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020ee`
- `0x180002179`
- `0x180002228`
- `0x1800022c5`
- `0x180002350`
- `0x180002411`
- `0x18000249c`
- `0x180002539`
- `0x1800025fa`
- `0x180002685`
- `0x1800027c4`
- `0x18000284f`
- `0x180002910`
- `0x18000299b`
- `0x180002a26`
- `0x180002ac3`
- `0x180002b60`
- `0x180002beb`
- `0x180002c76`
- `0x180002d01`
- `0x180002d8c`
- `0x180002e29`
- `0x180002eb4`
- `0x180002f51`
- `0x180002fdc`
- `0x180003067`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180018b0b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180018b0b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180018aea`

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
0x180018ae0  sub     rsp, 38h
0x180018ae4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180018aea  mov     r9, cs:__imp_DelayLoadFailureHook
0x180018af1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180018af8  mov     [rsp+38h+var_10], eax
0x180018afc  mov     [rsp+38h+var_18], rdx
0x180018b01  mov     rdx, rcx
0x180018b04  lea     rcx, __ImageBase
0x180018b0b  call    cs:__imp_ResolveDelayLoadedAPI
0x180018b12  nop     dword ptr [rax+rax+00h]
0x180018b17  add     rsp, 38h
0x180018b1b  retn
```
