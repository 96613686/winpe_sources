# __delayLoadHelper2

- ea: `0x1800030d0`
- end: `0x180003106`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005212`
- `0x18000529d`
- `0x1800053b2`
- `0x180005449`
- `0x18000550a`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800030fb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800030fb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800030da`

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
0x1800030d0  sub     rsp, 38h
0x1800030d4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800030da  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800030e1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800030e8  mov     [rsp+38h+var_10], eax
0x1800030ec  mov     [rsp+38h+var_18], rdx
0x1800030f1  mov     rdx, rcx
0x1800030f4  lea     rcx, __ImageBase
0x1800030fb  call    cs:__imp_ResolveDelayLoadedAPI
0x180003101  add     rsp, 38h
0x180003105  retn
```
