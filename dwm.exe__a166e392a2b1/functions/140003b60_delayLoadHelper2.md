# __delayLoadHelper2

- ea: `0x140003b60`
- end: `0x140003b96`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140006272`
- `0x140006352`
- `0x1400063ef`
- `0x14000649e`
- `0x14000661a`
- `0x140006732`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140003b8b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140003b8b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x140003b6a`

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
0x140003b60  sub     rsp, 38h
0x140003b64  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x140003b6a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140003b71  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140003b78  mov     [rsp+38h+var_10], eax
0x140003b7c  mov     [rsp+38h+var_18], rdx
0x140003b81  mov     rdx, rcx
0x140003b84  lea     rcx, __ImageBase
0x140003b8b  call    cs:__imp_ResolveDelayLoadedAPI
0x140003b91  add     rsp, 38h
0x140003b95  retn
```
