# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000ce00`
- end: `0x18000ce36`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000ce00`
- `0x180015a54`
- `0x180018010`

## string_xrefs

- `0x18000ce10`: `RtlDllShutdownInProgress`

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
0x18000ce00  sub     rsp, 28h
0x18000ce04  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000ce0b  test    rax, rax
0x18000ce0e  jnz     short loc_18000CE2D
0x18000ce10  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000ce17  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ce1c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000ce23  test    rax, rax
0x18000ce26  jnz     short loc_18000CE2D
0x18000ce28  add     rsp, 28h
0x18000ce2c  retn
0x18000ce2d  add     rsp, 28h
0x18000ce31  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
