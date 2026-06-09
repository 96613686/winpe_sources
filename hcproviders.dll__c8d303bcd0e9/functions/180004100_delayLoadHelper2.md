# __delayLoadHelper2

- ea: `0x180004100`
- end: `0x18000413d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800059e0`
- `0x180005a7d`
- `0x180005b32`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000412b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000412b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000410a`

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
0x180004100  sub     rsp, 38h
0x180004104  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000410a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180004111  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180004118  mov     [rsp+38h+var_10], eax
0x18000411c  mov     [rsp+38h+var_18], rdx
0x180004121  mov     rdx, rcx
0x180004124  lea     rcx, __ImageBase
0x18000412b  call    cs:__imp_ResolveDelayLoadedAPI
0x180004132  nop     dword ptr [rax+rax+00h]
0x180004137  add     rsp, 38h
0x18000413b  retn
```
