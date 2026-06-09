# __delayLoadHelper2

- ea: `0x140019490`
- end: `0x1400194cd`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002d20`
- `0x140002dab`
- `0x140002f06`
- `0x140002f91`
- `0x1400030a2`
- `0x1400031dd`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1400194bb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1400194bb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14001949a`

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
0x140019490  sub     rsp, 38h
0x140019494  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14001949a  mov     r9, cs:__imp_DelayLoadFailureHook
0x1400194a1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1400194a8  mov     [rsp+38h+var_10], eax
0x1400194ac  mov     [rsp+38h+var_18], rdx
0x1400194b1  mov     rdx, rcx
0x1400194b4  lea     rcx, __ImageBase
0x1400194bb  call    cs:__imp_ResolveDelayLoadedAPI
0x1400194c2  nop     dword ptr [rax+rax+00h]
0x1400194c7  add     rsp, 38h
0x1400194cb  retn
```
