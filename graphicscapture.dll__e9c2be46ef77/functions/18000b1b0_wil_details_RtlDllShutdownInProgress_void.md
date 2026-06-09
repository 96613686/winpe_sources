# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000b1b0`
- end: `0x18000b1e3`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000b1b0`
- `0x18000cdb0`
- `0x180028010`

## string_xrefs

- `0x18000b1c0`: `RtlDllShutdownInProgress`

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
0x18000b1b0  sub     rsp, 28h
0x18000b1b4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000b1bb  test    rax, rax
0x18000b1be  jnz     short loc_18000B1D8
0x18000b1c0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000b1c7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b1cc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000b1d3  test    rax, rax
0x18000b1d6  jz      short loc_18000B1DE
0x18000b1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1dd  nop
0x18000b1de  add     rsp, 28h
0x18000b1e2  retn
```
