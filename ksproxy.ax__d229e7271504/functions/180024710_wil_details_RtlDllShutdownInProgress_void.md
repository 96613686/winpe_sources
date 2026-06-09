# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180024710`
- end: `0x180024747`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `55`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180024710`
- `0x180025804`
- `0x180045010`

## string_xrefs

- `0x180024720`: `RtlDllShutdownInProgress`

## pseudocode

```c
__int64 (*__fastcall wil::details::RtlDllShutdownInProgress(wil::details *this))(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (__int64 (*)(void))((__int64 (__fastcall *)(wil::details *))result)(this);
  result = wil_details_GetNtDllProcedureAddress("RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180024710  sub     rsp, 28h
0x180024714  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18002471b  test    rax, rax
0x18002471e  jnz     short loc_18002473E
0x180024720  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180024727  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002472c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180024733  test    rax, rax
0x180024736  jnz     short loc_18002473E
0x180024738  add     rsp, 28h
0x18002473c  retn
0x18002473e  add     rsp, 28h
0x180024742  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
