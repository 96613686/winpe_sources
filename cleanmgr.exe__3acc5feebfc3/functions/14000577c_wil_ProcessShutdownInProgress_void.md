# wil::ProcessShutdownInProgress(void)

- ea: `0x14000577c`
- end: `0x1400057a9`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003ed8`
- `0x1400078d8`
- `0x140008584`
- `0x140008670`
- `0x140008b28`
- `0x1400091f4`
- `0x1400097fc`
- `0x1400178f0`
- `0x140017920`

## callees

- `0x14000577c`
- `0x140018010`

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
0x14000577c  sub     rsp, 28h
0x140005780  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140005787  jnz     short loc_1400057A2
0x140005789  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140005790  test    rax, rax
0x140005793  jz      short loc_14000579E
0x140005795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000579a  test    al, al
0x14000579c  jnz     short loc_1400057A2
0x14000579e  xor     al, al
0x1400057a0  jmp     short loc_1400057A4
0x1400057a2  mov     al, 1
0x1400057a4  add     rsp, 28h
0x1400057a8  retn
```
