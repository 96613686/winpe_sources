# wil::ProcessShutdownInProgress(void)

- ea: `0x180003664`
- end: `0x180003691`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800033fc`
- `0x1800034f4`
- `0x1800063b4`
- `0x1800085d4`
- `0x180008654`
- `0x180009118`
- `0x18000b680`

## callees

- `0x180003664`
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
0x180003664  sub     rsp, 28h
0x180003668  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000366f  jnz     short loc_18000368A
0x180003671  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180003678  test    rax, rax
0x18000367b  jz      short loc_180003686
0x18000367d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003682  test    al, al
0x180003684  jnz     short loc_18000368A
0x180003686  xor     al, al
0x180003688  jmp     short loc_18000368C
0x18000368a  mov     al, 1
0x18000368c  add     rsp, 28h
0x180003690  retn
```
