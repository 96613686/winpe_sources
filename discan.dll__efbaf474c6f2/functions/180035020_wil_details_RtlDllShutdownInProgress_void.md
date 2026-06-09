# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180035020`
- end: `0x180035056`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180035020`
- `0x18003667c`
- `0x180039010`

## string_xrefs

- `0x180035030`: `RtlDllShutdownInProgress`

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
0x180035020  sub     rsp, 28h
0x180035024  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18003502b  test    rax, rax
0x18003502e  jnz     short loc_18003504D
0x180035030  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180035037  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003503c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180035043  test    rax, rax
0x180035046  jnz     short loc_18003504D
0x180035048  add     rsp, 28h
0x18003504c  retn
0x18003504d  add     rsp, 28h
0x180035051  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
