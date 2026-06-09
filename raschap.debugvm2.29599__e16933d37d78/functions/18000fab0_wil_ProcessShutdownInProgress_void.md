# wil::ProcessShutdownInProgress(void)

- ea: `0x18000fab0`
- end: `0x18000fadd`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011934`
- `0x180011abc`
- `0x18001fdd4`
- `0x180021954`
- `0x1800219d4`
- `0x1800223a4`
- `0x1800263a0`
- `0x1800263e0`

## callees

- `0x18000fab0`
- `0x180027010`

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
0x18000fab0  sub     rsp, 28h
0x18000fab4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fabb  jnz     short loc_18000FAD6
0x18000fabd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fac4  test    rax, rax
0x18000fac7  jz      short loc_18000FAD2
0x18000fac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000face  test    al, al
0x18000fad0  jnz     short loc_18000FAD6
0x18000fad2  xor     al, al
0x18000fad4  jmp     short loc_18000FAD8
0x18000fad6  mov     al, 1
0x18000fad8  add     rsp, 28h
0x18000fadc  retn
```
