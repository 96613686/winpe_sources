# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180006e90`
- end: `0x180006ec3`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006e90`
- `0x180008db8`
- `0x180029010`

## string_xrefs

- `0x180006ea0`: `RtlDllShutdownInProgress`

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
0x180006e90  sub     rsp, 28h
0x180006e94  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180006e9b  test    rax, rax
0x180006e9e  jnz     short loc_180006EB8
0x180006ea0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180006ea7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180006eac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006eb3  test    rax, rax
0x180006eb6  jz      short loc_180006EBE
0x180006eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebd  nop
0x180006ebe  add     rsp, 28h
0x180006ec2  retn
```
