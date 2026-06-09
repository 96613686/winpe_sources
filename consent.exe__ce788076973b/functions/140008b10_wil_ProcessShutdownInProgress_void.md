# wil::ProcessShutdownInProgress(void)

- ea: `0x140008b10`
- end: `0x140008b3d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140008980`
- `0x14000d6e4`
- `0x14000fd34`
- `0x14001003c`
- `0x140011974`
- `0x140012adc`
- `0x14001e8d0`
- `0x14001e910`

## callees

- `0x140008b10`
- `0x14001f010`

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
0x140008b10  sub     rsp, 28h
0x140008b14  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008b1b  jnz     short loc_140008B39
0x140008b1d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008b24  test    rax, rax
0x140008b27  jz      short loc_140008B32
0x140008b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b2e  test    al, al
0x140008b30  jnz     short loc_140008B39
0x140008b32  xor     al, al
0x140008b34  add     rsp, 28h
0x140008b38  retn
0x140008b39  mov     al, 1
0x140008b3b  jmp     short loc_140008B34
```
