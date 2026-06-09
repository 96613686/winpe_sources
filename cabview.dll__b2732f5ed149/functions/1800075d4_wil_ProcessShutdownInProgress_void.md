# wil::ProcessShutdownInProgress(void)

- ea: `0x1800075d4`
- end: `0x180007601`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003cac`
- `0x180003d30`
- `0x180005a1c`
- `0x180007608`
- `0x180007694`
- `0x180007a24`
- `0x180008e48`
- `0x180012bc0`
- `0x180012bf0`

## callees

- `0x1800075d4`
- `0x180013010`

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
0x1800075d4  sub     rsp, 28h
0x1800075d8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800075df  jnz     short loc_1800075FA
0x1800075e1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800075e8  test    rax, rax
0x1800075eb  jz      short loc_1800075F6
0x1800075ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f2  test    al, al
0x1800075f4  jnz     short loc_1800075FA
0x1800075f6  xor     al, al
0x1800075f8  jmp     short loc_1800075FC
0x1800075fa  mov     al, 1
0x1800075fc  add     rsp, 28h
0x180007600  retn
```
