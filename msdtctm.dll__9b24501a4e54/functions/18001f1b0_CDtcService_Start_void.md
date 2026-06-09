# CDtcService::Start(void)

- ea: `0x18001f1b0`
- end: `0x18001f345`
- name: `?Start@CDtcService@@UEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(CDtcService *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18001f1b0`
- `0x18001f34c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f23a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f23a`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x18001f223`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x18001f223`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2ec`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18001f26d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18001f26d`

## string_xrefs

- `0x18001f208`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18001f2a0`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18001f319`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18001f285`: `StartServiceCtrlDispatcherW failed.`
- `0x18001f1e4`: `CDtcService::Start IN`
- `0x18001f1f7`: `CDtcService::Start`
- `0x18001f2f9`: `CDtcService::Start OUT`

## pseudocode

```c
__int64 __fastcall CDtcService::Start(CDtcService *this)
{
  BOOL started; // eax
  int LastError; // ebx
  unsigned int v3; // eax
  int Argumentsa; // [rsp+30h] [rbp-38h]
  int Arguments; // [rsp+30h] [rbp-38h]
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+40h] [rbp-28h] BYREF
  __int64 v8; // [rsp+50h] [rbp-18h]
  __int64 v9; // [rsp+58h] [rbp-10h]
  HLOCAL Buffer; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    ServiceStartTable.lpServiceName = (LPWSTR)*((_QWORD *)this + 1);
    ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)ServiceMain;
    v8 = 0;
    v9 = 0;
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      250,
      L"CDtcService::Start",
      0,
      L"CDtcService::Start IN");
    started = StartServiceCtrlDispatcherW(&ServiceStartTable);
  }
  catch ( ... )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      273,
      L"CDtcService::Start",
      0,
      L"CNtStart: exception occured");
    DtcWriteToEventLoggerA(1u, 1u, 0xC0001004, 0, 0, 0, Argumentsa);
    return 0;
  }
  if ( started )
  {
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      269,
      L"CDtcService::Start",
      0,
      L"CDtcService::Start OUT");
    return 0;
  }
  else
  {
    Buffer = 0;
    LastError = GetLastError();
    FormatMessageA(0x100u, 0, LastError, 0x400u, (LPSTR)&Buffer, 0, 0);
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    else
      v3 = LastError;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      261,
      L"CDtcService::Start",
      v3,
      L"StartServiceCtrlDispatcherW failed.");
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    DtcWriteToEventLoggerA(1u, 1u, 0xC0001004, LastError, 0, 0, Arguments);
    LocalFree(Buffer);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18001f1b0  mov     r11, rsp
0x18001f1b3  mov     [r11+10h], rbx
0x18001f1b7  mov     [r11+18h], rdi
0x18001f1bb  push    r12
0x18001f1bd  sub     rsp, 60h
0x18001f1c1  mov     rax, [rcx+8]
0x18001f1c5  mov     [r11-28h], rax
0x18001f1c9  lea     rax, ?ServiceMain@@YAXKPEAPEAG@Z; ServiceMain(ulong,ushort * *)
0x18001f1d0  mov     [r11-20h], rax
0x18001f1d4  mov     qword ptr [r11-18h], 0
0x18001f1dc  mov     qword ptr [r11-10h], 0
0x18001f1e4  lea     rax, aCdtcserviceSta_0; "CDtcService::Start IN"
0x18001f1eb  mov     [r11-38h], rax
0x18001f1ef  mov     qword ptr [r11-40h], 0
0x18001f1f7  lea     r12, aCdtcserviceSta_1; "CDtcService::Start"
0x18001f1fe  mov     [r11-48h], r12
0x18001f202  mov     r9d, 0FAh
0x18001f208  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x18001f20f  mov     ebx, 6
0x18001f214  mov     edx, ebx
0x18001f216  lea     ecx, [rbx-3]
0x18001f219  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f21e  lea     rcx, [rsp+68h+ServiceStartTable]; lpServiceStartTable
0x18001f223  call    cs:__imp_StartServiceCtrlDispatcherW
0x18001f229  test    eax, eax
0x18001f22b  jnz     loc_18001F2F9
0x18001f231  mov     [rsp+68h+Buffer], 0
0x18001f23a  call    cs:__imp_GetLastError
0x18001f240  mov     ebx, eax
0x18001f242  mov     qword ptr [rsp+68h+Arguments], 0; Arguments
0x18001f24b  mov     [rsp+68h+nSize], 0; nSize
0x18001f253  lea     rax, [rsp+68h+Buffer]
0x18001f258  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18001f25d  mov     r9d, 400h; dwLanguageId
0x18001f263  mov     r8d, ebx; dwMessageId
0x18001f266  xor     edx, edx; lpSource
0x18001f268  mov     ecx, 100h; dwFlags
0x18001f26d  call    cs:__imp_FormatMessageA
0x18001f273  movzx   edi, bx
0x18001f276  test    ebx, ebx
0x18001f278  jg      short loc_18001F27E
0x18001f27a  mov     eax, ebx
0x18001f27c  jmp     short loc_18001F285
0x18001f27e  mov     eax, edi
0x18001f280  or      eax, 80070000h
0x18001f285  lea     rdx, aStartservicect; "StartServiceCtrlDispatcherW failed."
0x18001f28c  mov     qword ptr [rsp+68h+Arguments], rdx; int
0x18001f291  mov     [rsp+68h+nSize], eax
0x18001f295  mov     [rsp+68h+lpBuffer], r12
0x18001f29a  mov     r9d, 105h
0x18001f2a0  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x18001f2a7  mov     edx, 1
0x18001f2ac  lea     ecx, [rdx+2]
0x18001f2af  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f2b4  test    ebx, ebx
0x18001f2b6  jle     short loc_18001F2C0
0x18001f2b8  mov     ebx, edi
0x18001f2ba  or      ebx, 80070000h
0x18001f2c0  mov     qword ptr [rsp+68h+nSize], 0; char *
0x18001f2c9  mov     [rsp+68h+lpBuffer], 0; void *
0x18001f2d2  mov     r9d, ebx; unsigned int
0x18001f2d5  mov     edx, 1; unsigned int
0x18001f2da  mov     r8d, 0C0001004h; unsigned int
0x18001f2e0  mov     ecx, edx; unsigned int
0x18001f2e2  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x18001f2e7  mov     rcx, [rsp+68h+Buffer]; hMem
0x18001f2ec  call    cs:__imp_LocalFree
0x18001f2f2  mov     eax, 80004005h
0x18001f2f7  jmp     short loc_18001F331
0x18001f2f9  lea     rax, aCdtcserviceSta; "CDtcService::Start OUT"
0x18001f300  mov     qword ptr [rsp+68h+Arguments], rax
0x18001f305  mov     qword ptr [rsp+68h+nSize], 0
0x18001f30e  mov     [rsp+68h+lpBuffer], r12
0x18001f313  mov     r9d, 10Dh
0x18001f319  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x18001f320  mov     edx, ebx
0x18001f322  mov     ecx, 3
0x18001f327  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f32c  nop
0x18001f32d  jmp     short $+2
0x18001f32f  xor     eax, eax
0x18001f331  lea     r11, [rsp+68h+var_8]
0x18001f336  mov     rbx, [r11+18h]
0x18001f33a  mov     rdi, [r11+20h]
0x18001f33e  mov     rsp, r11
0x18001f341  pop     r12
0x18001f343  retn
```
