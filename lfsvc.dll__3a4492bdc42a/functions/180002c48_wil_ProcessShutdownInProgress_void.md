# wil::ProcessShutdownInProgress(void)

- ea: `0x180002c48`
- end: `0x180002c75`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003140`
- `0x18000321c`
- `0x180006ad8`
- `0x1800088cc`
- `0x180008954`
- `0x180009588`
- `0x18000b6a0`

## callees

- `0x180002c48`
- `0x18000c010`

## pseudocode

```c
bool __fastcall wil::ProcessShutdownInProgress(wil *this)
{
  return wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this);
}

```

## disassembly

```asm
0x180002c48  sub     rsp, 28h
0x180002c4c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180002c53  jnz     short loc_180002C6E
0x180002c55  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180002c5c  test    rax, rax
0x180002c5f  jz      short loc_180002C6A
0x180002c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c66  test    al, al
0x180002c68  jnz     short loc_180002C6E
0x180002c6a  xor     al, al
0x180002c6c  jmp     short loc_180002C70
0x180002c6e  mov     al, 1
0x180002c70  add     rsp, 28h
0x180002c74  retn
```
