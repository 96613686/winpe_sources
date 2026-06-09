# InitializeCVForLocalConfigSession(TraceLoggingCorrelationVector *)

- ea: `0x14000e4f0`
- end: `0x14000e707`
- name: `?InitializeCVForLocalConfigSession@@YAJPEAVTraceLoggingCorrelationVector@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(struct TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e3e4`

## callees

- `0x1400029ac`
- `0x140002a1c`
- `0x14000dc4c`
- `0x14000e4f0`
- `0x14000ecc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InitializeCVForLocalConfigSession(struct TraceLoggingCorrelationVector *a1)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v3; // rdi

  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v3 = *ThreadLocalStoragePointer;
  if ( dword_140024300 > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&dword_140024300);
    if ( dword_140024300 == -1 )
    {
      dword_140023520 = 1;
      off_140023528 = &qword_1400230E0;
      byte_140023530 = 0;
      GetCorrelationVectorForDmSession(L"OmaDmSession", &byte_140023530);
      Init_thread_footer(&dword_140024300);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_140023520, a1);
  if ( dword_1400242F8 > *(_DWORD *)(v3 + 4) )
  {
    Init_thread_header(&dword_1400242F8);
    if ( dword_1400242F8 == -1 )
    {
      dword_1400233E0 = 1;
      off_1400233E8 = &qword_1400230A8;
      byte_1400233F0 = 0;
      GetCorrelationVectorForDmSession(L"OmaDmSession", &byte_1400233F0);
      Init_thread_footer(&dword_1400242F8);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_1400233E0, a1);
  if ( dword_1400242FC > *(_DWORD *)(v3 + 4) )
  {
    Init_thread_header(&dword_1400242FC);
    if ( dword_1400242FC == -1 )
    {
      dword_140023480 = 1;
      off_140023488 = &qword_140023070;
      byte_140023490 = 0;
      GetCorrelationVectorForDmSession(L"OmaDmSession", &byte_140023490);
      Init_thread_footer(&dword_1400242FC);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_140023480, a1);
  if ( dword_1400242F4 > *(_DWORD *)(v3 + 4) )
  {
    Init_thread_header(&dword_1400242F4);
    if ( dword_1400242F4 == -1 )
    {
      dword_140023340 = 1;
      off_140023348 = &qword_140023038;
      byte_140023350 = 0;
      GetCorrelationVectorForDmSession(L"OmaDmSession", &byte_140023350);
      Init_thread_footer(&dword_1400242F4);
    }
  }
  Microsoft::Windows::TelemetryLogger::SetCorrelationVector((Microsoft::Windows::TelemetryLogger *)&dword_140023340, a1);
  return 0;
}

```

## disassembly

```asm
0x14000e4f0  mov     [rsp+arg_0], rbx
0x14000e4f5  mov     [rsp+arg_8], rsi
0x14000e4fa  push    rdi
0x14000e4fb  sub     rsp, 20h
0x14000e4ff  mov     rbx, rcx
0x14000e502  mov     esi, 4
0x14000e507  mov     rax, gs:58h
0x14000e510  mov     rdi, [rax]
0x14000e513  mov     eax, [rsi+rdi]
0x14000e516  cmp     cs:dword_140024300, eax
0x14000e51c  jg      loc_14000E5F0
0x14000e522  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x14000e525  lea     rcx, dword_140023520; this
0x14000e52c  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x14000e531  mov     eax, [rsi+rdi]
0x14000e534  cmp     cs:dword_1400242F8, eax
0x14000e53a  jg      loc_14000E64D
0x14000e540  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x14000e543  lea     rcx, dword_1400233E0; this
0x14000e54a  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x14000e54f  mov     eax, [rsi+rdi]
0x14000e552  cmp     cs:dword_1400242FC, eax
0x14000e558  jg      loc_14000E6AA
0x14000e55e  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x14000e561  lea     rcx, dword_140023480; this
0x14000e568  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x14000e56d  mov     eax, [rsi+rdi]
0x14000e570  cmp     cs:dword_1400242F4, eax
0x14000e576  jg      short loc_14000E59A
0x14000e578  mov     rdx, rbx; struct TraceLoggingCorrelationVector *
0x14000e57b  lea     rcx, dword_140023340; this
0x14000e582  call    ?SetCorrelationVector@TelemetryLogger@Windows@Microsoft@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; Microsoft::Windows::TelemetryLogger::SetCorrelationVector(TraceLoggingCorrelationVector *)
0x14000e587  xor     eax, eax
0x14000e589  mov     rbx, [rsp+28h+arg_0]
0x14000e58e  mov     rsi, [rsp+28h+arg_8]
0x14000e593  add     rsp, 20h
0x14000e597  pop     rdi
0x14000e598  retn
0x14000e59a  lea     rcx, dword_1400242F4
0x14000e5a1  call    _Init_thread_header
0x14000e5a6  cmp     cs:dword_1400242F4, 0FFFFFFFFh
0x14000e5ad  jnz     short loc_14000E578
0x14000e5af  mov     cs:dword_140023340, 1
0x14000e5b9  lea     rax, qword_140023038
0x14000e5c0  mov     cs:off_140023348, rax
0x14000e5c7  mov     cs:byte_140023350, 0
0x14000e5ce  lea     rdx, byte_140023350; char *
0x14000e5d5  lea     rcx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x14000e5dc  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x14000e5e1  nop
0x14000e5e2  lea     rcx, dword_1400242F4
0x14000e5e9  call    _Init_thread_footer
0x14000e5ee  jmp     short loc_14000E578
0x14000e5f0  lea     rcx, dword_140024300
0x14000e5f7  call    _Init_thread_header
0x14000e5fc  cmp     cs:dword_140024300, 0FFFFFFFFh
0x14000e603  jnz     loc_14000E522
0x14000e609  mov     cs:dword_140023520, 1
0x14000e613  lea     rax, qword_1400230E0
0x14000e61a  mov     cs:off_140023528, rax
0x14000e621  mov     cs:byte_140023530, 0
0x14000e628  lea     rdx, byte_140023530; char *
0x14000e62f  lea     rcx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x14000e636  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x14000e63b  nop
0x14000e63c  lea     rcx, dword_140024300
0x14000e643  call    _Init_thread_footer
0x14000e648  jmp     loc_14000E522
0x14000e64d  lea     rcx, dword_1400242F8
0x14000e654  call    _Init_thread_header
0x14000e659  cmp     cs:dword_1400242F8, 0FFFFFFFFh
0x14000e660  jnz     loc_14000E540
0x14000e666  mov     cs:dword_1400233E0, 1
0x14000e670  lea     rax, qword_1400230A8
0x14000e677  mov     cs:off_1400233E8, rax
0x14000e67e  mov     cs:byte_1400233F0, 0
0x14000e685  lea     rdx, byte_1400233F0; char *
0x14000e68c  lea     rcx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x14000e693  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x14000e698  nop
0x14000e699  lea     rcx, dword_1400242F8
0x14000e6a0  call    _Init_thread_footer
0x14000e6a5  jmp     loc_14000E540
0x14000e6aa  lea     rcx, dword_1400242FC
0x14000e6b1  call    _Init_thread_header
0x14000e6b6  cmp     cs:dword_1400242FC, 0FFFFFFFFh
0x14000e6bd  jnz     loc_14000E55E
0x14000e6c3  mov     cs:dword_140023480, 1
0x14000e6cd  lea     rax, qword_140023070
0x14000e6d4  mov     cs:off_140023488, rax
0x14000e6db  mov     cs:byte_140023490, 0
0x14000e6e2  lea     rdx, byte_140023490; char *
0x14000e6e9  lea     rcx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x14000e6f0  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x14000e6f5  nop
0x14000e6f6  lea     rcx, dword_1400242FC
0x14000e6fd  call    _Init_thread_footer
0x14000e702  jmp     loc_14000E55E
```
