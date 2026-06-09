# __delayLoadHelper2

- ea: `0x180007cb0`
- end: `0x180007ce6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x180009b56`
- `0x180009c05`
- `0x180009c90`
- `0x180009d1b`
- `0x180009da6`
- `0x180009e31`
- `0x180009ebc`
- `0x180009f47`
- `0x18000a082`
- `0x18000a11f`
- `0x18000a1aa`
- `0x18000a2b0`
- `0x18000a34d`
- `0x18000a3ea`
- `0x18000a487`
- `0x18000a5f2`
- `0x18000a6c5`
- `0x18000a786`
- `0x18000a811`
- `0x18000a89c`
- `0x18000a939`
- `0x18000a9c4`
- `0x18000aa61`
- `0x18000ab10`
- `0x18000abf5`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007cdb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007cdb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180007cba`

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
0x180007cb0  sub     rsp, 38h
0x180007cb4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180007cba  mov     r9, cs:__imp_DelayLoadFailureHook
0x180007cc1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180007cc8  mov     [rsp+38h+var_10], eax
0x180007ccc  mov     [rsp+38h+var_18], rdx
0x180007cd1  mov     rdx, rcx
0x180007cd4  lea     rcx, __ImageBase
0x180007cdb  call    cs:__imp_ResolveDelayLoadedAPI
0x180007ce1  add     rsp, 38h
0x180007ce5  retn
```
