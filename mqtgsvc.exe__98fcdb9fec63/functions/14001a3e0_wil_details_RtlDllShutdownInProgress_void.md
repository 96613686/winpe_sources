# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14001a3e0`
- end: `0x14001a413`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14001a3e0`
- `0x14001c088`
- `0x140020010`

## string_xrefs

- `0x14001a3f0`: `RtlDllShutdownInProgress`

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
0x14001a3e0  sub     rsp, 28h
0x14001a3e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14001a3eb  test    rax, rax
0x14001a3ee  jnz     short loc_14001A408
0x14001a3f0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14001a3f7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001a3fc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14001a403  test    rax, rax
0x14001a406  jz      short loc_14001A40E
0x14001a408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a40d  nop
0x14001a40e  add     rsp, 28h
0x14001a412  retn
```
