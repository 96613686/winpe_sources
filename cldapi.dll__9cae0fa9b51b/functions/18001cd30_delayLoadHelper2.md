# __delayLoadHelper2

- ea: `0x18001cd30`
- end: `0x18001cd6d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002330`
- `0x180002427`
- `0x1800024d6`
- `0x180002573`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001cd5b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001cd5b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001cd3a`

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
0x18001cd30  sub     rsp, 38h
0x18001cd34  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001cd3a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18001cd41  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001cd48  mov     [rsp+38h+var_10], eax
0x18001cd4c  mov     [rsp+38h+var_18], rdx
0x18001cd51  mov     rdx, rcx
0x18001cd54  lea     rcx, __ImageBase
0x18001cd5b  call    cs:__imp_ResolveDelayLoadedAPI
0x18001cd62  nop     dword ptr [rax+rax+00h]
0x18001cd67  add     rsp, 38h
0x18001cd6b  retn
```
