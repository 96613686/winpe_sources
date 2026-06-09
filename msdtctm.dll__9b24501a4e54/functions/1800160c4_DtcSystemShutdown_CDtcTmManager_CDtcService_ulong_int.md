# DtcSystemShutdown(CDtcTmManager *,CDtcService *,ulong,int)

- ea: `0x1800160c4`
- end: `0x180016267`
- name: `?DtcSystemShutdown@@YAXPEAVCDtcTmManager@@PEAVCDtcService@@KH@Z`
- size: `419`
- prototype: `void(struct CDtcTmManager *, struct CDtcService *, unsigned int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x18000112c`
- `0x180006220`
- `0x1800063b0`
- `0x18000862c`
- `0x180015230`
- `0x1800160c4`
- `0x180016270`
- `0x180016344`
- `0x1800846c0`
- `0x1800856d4`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180016257`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180016257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001624c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001624c`

## string_xrefs

- `0x180016103`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180016229`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001620b`: `DtcSystemShutdown (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@2540): Shutting down with an error`
- `0x1800161a5`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`

## pseudocode

```c
void __fastcall DtcSystemShutdown(struct CDtcTmManager *a1, SERVICE_STATUS_HANDLE *a2, DWORD a3, int a4)
{
  unsigned int v7; // edx
  int v8; // eax
  CTrace *v9; // rcx
  CUITrace *v10; // rcx
  HANDLE CurrentProcess; // rax
  int CurrentProcessId; // [rsp+90h] [rbp+18h] BYREF

  TraceStringInline(3, 6, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 2520, L"DtcSystemShutdown", 0, L"In");
  CurrentProcessId = GetCurrentProcessId();
  CTrace::TraceEvent((CTrace *)&g_Trace, 1u, 0, &stru_180125D68, 0xCu);
  if ( z_pTrace )
  {
    v8 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64))(*(_QWORD *)z_pTrace + 24LL))(
           z_pTrace,
           4099,
           1);
    if ( v8 < 0 )
      TraceFile(v8, "failed in z_pTrace->Trace", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x961u);
  }
  else
  {
    DtcWriteToEventLoggerW(4u, v7, 0x4000100Fu, 0, 0, (unsigned __int16 *)4, (int)&CurrentProcessId);
  }
  CTrace::Terminate(v9);
  CUITrace::Terminate(v10);
  TraceLoggingUnregister_EventUnregister();
  if ( a2 )
    CDtcService::ReportStatus(a2, 1u, a3, 0, 0, a4);
  if ( a3 )
    DtcInternalErrorW(L"DtcSystemShutdown (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@2540): Shutting down with an error");
  TraceStringInline(
    3,
    4,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
    2541,
    L"DtcSystemShutdown",
    0,
    L"Calling TerminateProcess for MSDTC");
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0);
}

```

## disassembly

```asm
0x1800160c4  push    rbx
0x1800160c6  push    rsi
0x1800160c7  push    rdi
0x1800160c8  push    r13
0x1800160ca  sub     rsp, 58h
0x1800160ce  mov     rdi, rdx
0x1800160d1  lea     rax, aIn_0; "In"
0x1800160d8  mov     qword ptr [rsp+78h+var_48], rax
0x1800160dd  lea     r13, aDtcsystemshutd_0; "DtcSystemShutdown"
0x1800160e4  mov     edx, 6
0x1800160e9  mov     [rsp+78h+var_50], 0
0x1800160f2  mov     esi, r9d
0x1800160f5  mov     [rsp+78h+var_58], r13
0x1800160fa  mov     ebx, r8d
0x1800160fd  mov     r9d, 9D8h
0x180016103  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001610a  lea     ecx, [rdx-3]
0x18001610d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016112  call    cs:__imp_GetCurrentProcessId
0x180016118  mov     [rsp+78h+var_40], 0
0x180016121  lea     r9, stru_180125D68; struct _GUID *
0x180016128  xor     r8d, r8d; unsigned int
0x18001612b  mov     [rsp+78h+arg_10], eax
0x180016132  lea     rax, [rsp+78h+arg_10]
0x18001613a  mov     qword ptr [rsp+78h+var_48], rax; int
0x18001613f  lea     rcx, ?g_Trace@@3VCTrace@@A; this
0x180016146  mov     [rsp+78h+var_50], 4; unsigned __int16 *
0x18001614f  lea     edx, [r8+1]; unsigned int
0x180016153  mov     dword ptr [rsp+78h+var_58], 0Ch; unsigned int
0x18001615b  call    ?TraceEvent@CTrace@@QEAAJKKQEBU_GUID@@KZZ; CTrace::TraceEvent(ulong,ulong,_GUID const * const,ulong,...)
0x180016160  mov     rcx, cs:?z_pTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * z_pTrace
0x180016167  xor     r9d, r9d; unsigned int
0x18001616a  test    rcx, rcx
0x18001616d  jz      short loc_1800161BC
0x18001616f  mov     rax, [rcx]
0x180016172  lea     r8d, [r9+1]
0x180016176  mov     [rsp+78h+var_40], r9
0x18001617b  mov     edx, 1003h
0x180016180  mov     qword ptr [rsp+78h+var_48], r9
0x180016185  mov     dword ptr [rsp+78h+var_50], r9d
0x18001618a  mov     rax, [rax+18h]
0x18001618e  mov     dword ptr [rsp+78h+var_58], 4000100Fh
0x180016196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001619b  test    eax, eax
0x18001619d  jns     short loc_1800161D5
0x18001619f  mov     r9d, 961h; unsigned int
0x1800161a5  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800161ac  lea     rdx, aFailedInZPtrac; "failed in z_pTrace->Trace"
0x1800161b3  mov     ecx, eax; int
0x1800161b5  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800161ba  jmp     short loc_1800161D5
0x1800161bc  mov     ecx, 4; unsigned int
0x1800161c1  mov     [rsp+78h+var_58], 0; void *
0x1800161ca  mov     r8d, 4000100Fh; unsigned int
0x1800161d0  call    ?DtcWriteToEventLoggerW@@YAJKKKKPEAXPEAGH@Z; DtcWriteToEventLoggerW(ulong,ulong,ulong,ulong,void *,ushort *,int)
0x1800161d5  call    ?Terminate@CTrace@@QEAAXXZ; CTrace::Terminate(void)
0x1800161da  call    ?Terminate@CUITrace@@QEAAXXZ; CUITrace::Terminate(void)
0x1800161df  call    TraceLoggingUnregister_EventUnregister
0x1800161e4  test    rdi, rdi
0x1800161e7  jz      short loc_180016207
0x1800161e9  xor     r9d, r9d; unsigned int
0x1800161ec  mov     dword ptr [rsp+78h+var_50], esi; int
0x1800161f0  mov     r8d, ebx; unsigned int
0x1800161f3  mov     dword ptr [rsp+78h+var_58], 0; unsigned int
0x1800161fb  mov     rcx, rdi; this
0x1800161fe  lea     edx, [r9+1]; unsigned int
0x180016202  call    ?ReportStatus@CDtcService@@QEAAJKKKKH@Z; CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)
0x180016207  test    ebx, ebx
0x180016209  jz      short loc_180016218
0x18001620b  lea     rcx, aDtcsystemshutd; "DtcSystemShutdown (com\\complus\\dtc\\d"...
0x180016212  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180016218  mov     edx, 4
0x18001621d  lea     rax, aCallingTermina; "Calling TerminateProcess for MSDTC"
0x180016224  mov     qword ptr [rsp+78h+var_48], rax
0x180016229  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180016230  mov     [rsp+78h+var_50], 0
0x180016239  mov     r9d, 9EDh
0x18001623f  mov     [rsp+78h+var_58], r13
0x180016244  lea     ecx, [rdx-1]
0x180016247  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001624c  call    cs:__imp_GetCurrentProcess
0x180016252  mov     rcx, rax; hProcess
0x180016255  xor     edx, edx; uExitCode
0x180016257  call    cs:__imp_TerminateProcess
0x18001625d  add     rsp, 58h
0x180016261  pop     r13
0x180016263  pop     rdi
0x180016264  pop     rsi
0x180016265  pop     rbx
0x180016266  retn
```
