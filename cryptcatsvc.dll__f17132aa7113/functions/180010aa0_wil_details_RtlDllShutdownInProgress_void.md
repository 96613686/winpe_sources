# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180010aa0`
- end: `0x180010adc`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `60`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180010aa0`
- `0x180012410`
- `0x180022010`

## string_xrefs

- `0x180010ab9`: `RtlDllShutdownInProgress`

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
0x180010aa0  sub     rsp, 38h
0x180010aa4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180010aad  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180010ab4  test    rax, rax
0x180010ab7  jnz     short loc_180010AD1
0x180010ab9  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180010ac0  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180010ac5  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180010acc  test    rax, rax
0x180010acf  jz      short loc_180010AD7
0x180010ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ad6  nop
0x180010ad7  add     rsp, 38h
0x180010adb  retn
```
