# wil::ProcessShutdownInProgress(void)

- ea: `0x180002470`
- end: `0x18000249d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005598`
- `0x180006bb0`
- `0x18000705c`
- `0x18000771c`
- `0x180008104`
- `0x180009f10`
- `0x180009f40`

## callees

- `0x180002470`
- `0x18000a010`

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
0x180002470  sub     rsp, 28h
0x180002474  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000247b  jnz     short loc_180002496
0x18000247d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180002484  test    rax, rax
0x180002487  jz      short loc_180002492
0x180002489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000248e  test    al, al
0x180002490  jnz     short loc_180002496
0x180002492  xor     al, al
0x180002494  jmp     short loc_180002498
0x180002496  mov     al, 1
0x180002498  add     rsp, 28h
0x18000249c  retn
```
