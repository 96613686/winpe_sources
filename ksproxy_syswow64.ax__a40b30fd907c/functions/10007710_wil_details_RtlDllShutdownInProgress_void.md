# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x10007710`
- end: `0x10007743`
- name: `?RtlDllShutdownInProgress@details@wil@@YGEXZ`
- size: `51`
- prototype: `unsigned __int8()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x10007690`
- `0x10007710`
- `0x1002d510`

## string_xrefs

- `0x1000771d`: `RtlDllShutdownInProgress`

## pseudocode

```c
unsigned __int8 wil::details::RtlDllShutdownInProgress()
{
  FARPROC NtDllProcedureAddress; // esi

  NtDllProcedureAddress = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((int (__thiscall *)(FARPROC))NtDllProcedureAddress)(NtDllProcedureAddress);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (CD3DSurfaceAllocator *)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((int (__thiscall *)(FARPROC))NtDllProcedureAddress)(NtDllProcedureAddress);
  else
    return 0;
}

```

## disassembly

```asm
0x10007710  mov     edi, edi
0x10007712  push    esi; char *
0x10007713  mov     esi, ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA
0x10007719  test    esi, esi
0x1000771b  jnz     short loc_10007737
0x1000771d  mov     ecx, offset aRtldllshutdown; "RtlDllShutdownInProgress"
0x10007722  call    ?wil_details_GetNtDllProcedureAddress@@YGP6GHXZPBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x10007727  mov     esi, eax
0x10007729  mov     ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA, esi
0x1000772f  test    esi, esi
0x10007731  jnz     short loc_10007737
0x10007733  xor     al, al
0x10007735  pop     esi
0x10007736  retn
0x10007737  mov     ecx, esi; this
0x10007739  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000773f  call    esi ; ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA
0x10007741  pop     esi
0x10007742  retn
```
