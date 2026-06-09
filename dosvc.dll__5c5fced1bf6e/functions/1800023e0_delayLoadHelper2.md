# __delayLoadHelper2

- ea: `0x1800023e0`
- end: `0x180002416`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180005baa`
- `0x180005c47`
- `0x180005ce4`
- `0x180005dc6`
- `0x180005eca`
- `0x180005f73`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000240b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000240b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800023ea`

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
0x1800023e0  sub     rsp, 38h
0x1800023e4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800023ea  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800023f1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800023f8  mov     [rsp+38h+var_10], eax
0x1800023fc  mov     [rsp+38h+var_18], rdx
0x180002401  mov     rdx, rcx
0x180002404  lea     rcx, __ImageBase
0x18000240b  call    cs:__imp_ResolveDelayLoadedAPI
0x180002411  add     rsp, 38h
0x180002415  retn
```
