# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18007c130`
- end: `0x18007c167`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `55`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18007c130`
- `0x18007d698`
- `0x180095010`

## string_xrefs

- `0x18007c140`: `RtlDllShutdownInProgress`

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
0x18007c130  sub     rsp, 28h
0x18007c134  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18007c13b  test    rax, rax
0x18007c13e  jnz     short loc_18007C15E
0x18007c140  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18007c147  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18007c14c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18007c153  test    rax, rax
0x18007c156  jnz     short loc_18007C15E
0x18007c158  add     rsp, 28h
0x18007c15c  retn
0x18007c15e  add     rsp, 28h
0x18007c162  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
