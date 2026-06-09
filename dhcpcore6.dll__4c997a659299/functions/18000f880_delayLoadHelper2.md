# __delayLoadHelper2

- ea: `0x18000f880`
- end: `0x18000f8bd`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a44a`
- `0x18001a4f9`
- `0x18001a5c6`
- `0x18001a7dd`
- `0x18001a868`
- `0x18001a917`
- `0x18001aa0e`
- `0x18001ab26`
- `0x18001ac1a`
- `0x18001acd5`
- `0x18001ad96`
- `0x18001aee2`
- `0x18001af6d`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000f8ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000f8ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000f88a`

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
0x18000f880  sub     rsp, 38h
0x18000f884  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000f88a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000f891  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000f898  mov     [rsp+38h+var_10], eax
0x18000f89c  mov     [rsp+38h+var_18], rdx
0x18000f8a1  mov     rdx, rcx
0x18000f8a4  lea     rcx, __ImageBase
0x18000f8ab  call    cs:__imp_ResolveDelayLoadedAPI
0x18000f8b2  nop     dword ptr [rax+rax+00h]
0x18000f8b7  add     rsp, 38h
0x18000f8bb  retn
```
