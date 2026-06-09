# __delayLoadHelper2

- ea: `0x1800036d0`
- end: `0x18000370d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003fe0`
- `0x18000406b`
- `0x180004198`
- `0x180004223`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800036fb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800036fb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800036da`

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
0x1800036d0  sub     rsp, 38h
0x1800036d4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800036da  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800036e1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800036e8  mov     [rsp+38h+var_10], eax
0x1800036ec  mov     [rsp+38h+var_18], rdx
0x1800036f1  mov     rdx, rcx
0x1800036f4  lea     rcx, __ImageBase
0x1800036fb  call    cs:__imp_ResolveDelayLoadedAPI
0x180003702  nop     dword ptr [rax+rax+00h]
0x180003707  add     rsp, 38h
0x18000370b  retn
```
