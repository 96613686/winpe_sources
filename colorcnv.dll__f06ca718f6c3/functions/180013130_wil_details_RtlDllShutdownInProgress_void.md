# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180013130`
- end: `0x180013166`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180013130`
- `0x180014cb0`
- `0x18002b010`

## string_xrefs

- `0x180013140`: `RtlDllShutdownInProgress`

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
0x180013130  sub     rsp, 28h
0x180013134  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001313b  test    rax, rax
0x18001313e  jnz     short loc_18001315D
0x180013140  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180013147  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001314c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180013153  test    rax, rax
0x180013156  jnz     short loc_18001315D
0x180013158  add     rsp, 28h
0x18001315c  retn
0x18001315d  add     rsp, 28h
0x180013161  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
