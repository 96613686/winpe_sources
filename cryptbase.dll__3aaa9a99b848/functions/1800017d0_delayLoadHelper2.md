# __delayLoadHelper2

- ea: `0x1800017d0`
- end: `0x18000180d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002824`
- `0x18000293f`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800017fb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800017fb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800017da`

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
0x1800017d0  sub     rsp, 38h
0x1800017d4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800017da  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800017e1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800017e8  mov     [rsp+38h+var_10], eax
0x1800017ec  mov     [rsp+38h+var_18], rdx
0x1800017f1  mov     rdx, rcx
0x1800017f4  lea     rcx, __ImageBase
0x1800017fb  call    cs:__imp_ResolveDelayLoadedAPI
0x180001802  nop     dword ptr [rax+rax+00h]
0x180001807  add     rsp, 38h
0x18000180b  retn
```
