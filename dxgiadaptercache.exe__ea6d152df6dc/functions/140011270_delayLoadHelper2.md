# __delayLoadHelper2

- ea: `0x140011270`
- end: `0x1400112a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140002db2`
- `0x140002e3d`
- `0x140002ec8`
- `0x140002f53`
- `0x140003002`
- `0x14000309f`
- `0x14000312a`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14001129b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14001129b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14001127a`

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
0x140011270  sub     rsp, 38h
0x140011274  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14001127a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140011281  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140011288  mov     [rsp+38h+var_10], eax
0x14001128c  mov     [rsp+38h+var_18], rdx
0x140011291  mov     rdx, rcx
0x140011294  lea     rcx, __ImageBase
0x14001129b  call    cs:__imp_ResolveDelayLoadedAPI
0x1400112a1  add     rsp, 38h
0x1400112a5  retn
```
