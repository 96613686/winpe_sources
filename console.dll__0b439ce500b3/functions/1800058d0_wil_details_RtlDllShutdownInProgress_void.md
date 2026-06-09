# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800058d0`
- end: `0x180005904`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `52`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800058d0`
- `0x1800066e4`
- `0x18001a010`

## string_xrefs

- `0x1800058e0`: `RtlDllShutdownInProgress`

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
0x1800058d0  sub     rsp, 28h
0x1800058d4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800058db  test    rax, rax
0x1800058de  jnz     short loc_1800058F8
0x1800058e0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800058e7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800058ec  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800058f3  test    rax, rax
0x1800058f6  jz      short loc_1800058FE
0x1800058f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058fd  nop
0x1800058fe  add     rsp, 28h
0x180005902  retn
```
