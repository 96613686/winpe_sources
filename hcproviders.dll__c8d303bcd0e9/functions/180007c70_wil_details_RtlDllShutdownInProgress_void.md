# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180007c70`
- end: `0x180007ca7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `55`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180007c70`
- `0x18000891c`
- `0x18000b010`

## string_xrefs

- `0x180007c80`: `RtlDllShutdownInProgress`

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
0x180007c70  sub     rsp, 28h
0x180007c74  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180007c7b  test    rax, rax
0x180007c7e  jnz     short loc_180007C9E
0x180007c80  lea     rcx, ProcName; "RtlDllShutdownInProgress"
0x180007c87  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180007c8c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180007c93  test    rax, rax
0x180007c96  jnz     short loc_180007C9E
0x180007c98  add     rsp, 28h
0x180007c9c  retn
0x180007c9e  add     rsp, 28h
0x180007ca2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
