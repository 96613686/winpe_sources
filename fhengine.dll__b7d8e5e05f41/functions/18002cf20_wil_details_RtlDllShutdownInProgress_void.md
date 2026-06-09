# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18002cf20`
- end: `0x18002cf53`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18002cf20`
- `0x18002e9b8`
- `0x180034010`

## string_xrefs

- `0x18002cf30`: `RtlDllShutdownInProgress`

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
0x18002cf20  sub     rsp, 28h
0x18002cf24  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18002cf2b  test    rax, rax
0x18002cf2e  jnz     short loc_18002CF48
0x18002cf30  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18002cf37  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002cf3c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18002cf43  test    rax, rax
0x18002cf46  jz      short loc_18002CF4E
0x18002cf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf4d  nop
0x18002cf4e  add     rsp, 28h
0x18002cf52  retn
```
