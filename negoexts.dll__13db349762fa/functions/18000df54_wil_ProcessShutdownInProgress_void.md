# wil::ProcessShutdownInProgress(void)

- ea: `0x18000df54`
- end: `0x18000df81`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dcf0`
- `0x18000dde4`
- `0x1800113bc`
- `0x180012fe0`
- `0x18001372c`
- `0x1800137ac`
- `0x180014778`
- `0x18001f390`
- `0x18001f3c0`

## callees

- `0x18000df54`
- `0x180020010`

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
0x18000df54  sub     rsp, 28h
0x18000df58  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000df5f  jnz     short loc_18000DF7A
0x18000df61  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000df68  test    rax, rax
0x18000df6b  jz      short loc_18000DF76
0x18000df6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df72  test    al, al
0x18000df74  jnz     short loc_18000DF7A
0x18000df76  xor     al, al
0x18000df78  jmp     short loc_18000DF7C
0x18000df7a  mov     al, 1
0x18000df7c  add     rsp, 28h
0x18000df80  retn
```
