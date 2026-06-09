# __delayLoadHelper2

- ea: `0x180003100`
- end: `0x18000313d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001294`
- `0x180001331`
- `0x1800013e0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000312b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000312b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000310a`

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
0x180003100  sub     rsp, 38h
0x180003104  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000310a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003111  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003118  mov     [rsp+38h+var_10], eax
0x18000311c  mov     [rsp+38h+var_18], rdx
0x180003121  mov     rdx, rcx
0x180003124  lea     rcx, __ImageBase
0x18000312b  call    cs:__imp_ResolveDelayLoadedAPI
0x180003132  nop     dword ptr [rax+rax+00h]
0x180003137  add     rsp, 38h
0x18000313b  retn
```
