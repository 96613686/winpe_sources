# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008e60`
- end: `0x180008e94`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `52`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180008e60`
- `0x180009fb8`
- `0x180039010`

## string_xrefs

- `0x180008e70`: `RtlDllShutdownInProgress`

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
0x180008e60  sub     rsp, 28h
0x180008e64  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180008e6b  test    rax, rax
0x180008e6e  jnz     short loc_180008E88
0x180008e70  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008e77  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180008e7c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180008e83  test    rax, rax
0x180008e86  jz      short loc_180008E8E
0x180008e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e8d  nop
0x180008e8e  add     rsp, 28h
0x180008e92  retn
```
