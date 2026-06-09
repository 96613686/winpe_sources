# wil::ProcessShutdownInProgress(void)

- ea: `0x140004110`
- end: `0x14000413d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400087c4`
- `0x140009c24`
- `0x140009f54`
- `0x14000a3b4`
- `0x14000a434`
- `0x14000b410`
- `0x14000d124`
- `0x14000fda0`
- `0x14000fde0`

## callees

- `0x140004110`
- `0x140010010`

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
0x140004110  sub     rsp, 28h
0x140004114  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000411b  jnz     short loc_140004136
0x14000411d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140004124  test    rax, rax
0x140004127  jz      short loc_140004132
0x140004129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000412e  test    al, al
0x140004130  jnz     short loc_140004136
0x140004132  xor     al, al
0x140004134  jmp     short loc_140004138
0x140004136  mov     al, 1
0x140004138  add     rsp, 28h
0x14000413c  retn
```
