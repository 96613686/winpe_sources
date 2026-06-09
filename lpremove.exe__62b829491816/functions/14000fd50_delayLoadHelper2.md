# __delayLoadHelper2

- ea: `0x14000fd50`
- end: `0x14000fd86`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140002c92`
- `0x140002e1a`
- `0x140002ea5`
- `0x140002f30`
- `0x140002fc7`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x14000fd5a`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x14000fd7b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x14000fd7b`

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
0x14000fd50  sub     rsp, 38h
0x14000fd54  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000fd5a  mov     r9, cs:__imp_DelayLoadFailureHook
0x14000fd61  mov     r8, cs:__pfnDefaultDliFailureHook2
0x14000fd68  mov     [rsp+38h+var_10], eax
0x14000fd6c  mov     [rsp+38h+var_18], rdx
0x14000fd71  mov     rdx, rcx
0x14000fd74  lea     rcx, __ImageBase
0x14000fd7b  call    cs:__imp_ResolveDelayLoadedAPI
0x14000fd81  add     rsp, 38h
0x14000fd85  retn
```
