# wil::ProcessShutdownInProgress(void)

- ea: `0x180009da4`
- end: `0x180009dd1`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800074c4`
- `0x180007548`
- `0x180008750`
- `0x180009dd8`
- `0x180009ec4`
- `0x18000a504`
- `0x18000b768`
- `0x180011d00`
- `0x180011d30`

## callees

- `0x180009da4`
- `0x180012010`

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
0x180009da4  sub     rsp, 28h
0x180009da8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009daf  jnz     short loc_180009DCA
0x180009db1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009db8  test    rax, rax
0x180009dbb  jz      short loc_180009DC6
0x180009dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc2  test    al, al
0x180009dc4  jnz     short loc_180009DCA
0x180009dc6  xor     al, al
0x180009dc8  jmp     short loc_180009DCC
0x180009dca  mov     al, 1
0x180009dcc  add     rsp, 28h
0x180009dd0  retn
```
