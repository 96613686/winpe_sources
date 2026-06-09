# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008820`
- end: `0x180008853`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180008820`
- `0x18000a140`
- `0x18000c010`

## string_xrefs

- `0x180008830`: `RtlDllShutdownInProgress`

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
0x180008820  sub     rsp, 28h
0x180008824  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000882b  test    rax, rax
0x18000882e  jnz     short loc_180008848
0x180008830  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008837  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000883c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008843  test    rax, rax
0x180008846  jz      short loc_18000884E
0x180008848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000884d  nop
0x18000884e  add     rsp, 28h
0x180008852  retn
```
