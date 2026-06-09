# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000a510`
- end: `0x14000a543`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14000a510`
- `0x14000ed40`
- `0x14001a010`

## string_xrefs

- `0x14000a520`: `RtlDllShutdownInProgress`

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
0x14000a510  sub     rsp, 28h
0x14000a514  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000a51b  test    rax, rax
0x14000a51e  jnz     short loc_14000A538
0x14000a520  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000a527  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a52c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000a533  test    rax, rax
0x14000a536  jz      short loc_14000A53E
0x14000a538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a53d  nop
0x14000a53e  add     rsp, 28h
0x14000a542  retn
```
