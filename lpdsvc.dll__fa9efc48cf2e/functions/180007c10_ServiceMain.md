# ServiceMain

- ea: `0x180007c10`
- end: `0x180008227`
- name: `ServiceMain`
- size: `1559`
- prototype: `void()`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x1800026f0`
- `0x18000276c`
- `0x180002e7c`
- `0x180002ea4`
- `0x180003d4c`
- `0x1800079d0`
- `0x180007c10`
- `0x180008230`
- `0x180009ae4`
- `0x180009eb8`
- `0x18000aaac`
- `0x18000e010`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x180008104`
- `ntdll!EtwEventWriteNoRegistration` at `0x180008104`
- `KERNEL32!WaitForSingleObject` at `0x180007ff6`
- `KERNEL32!WaitForSingleObject` at `0x180007ff6`
- `KERNEL32!GetLastError` at `0x180007d24`
- `KERNEL32!GetLastError` at `0x180007d9e`
- `KERNEL32!GetLastError` at `0x180007e83`
- `KERNEL32!GetLastError` at `0x180007f3d`
- `KERNEL32!GetLastError` at `0x180007d24`
- `KERNEL32!GetLastError` at `0x180007d9e`
- `KERNEL32!GetLastError` at `0x180007e83`
- `KERNEL32!GetLastError` at `0x180007f3d`
- `KERNEL32!DeleteCriticalSection` at `0x180007f74`
- `KERNEL32!DeleteCriticalSection` at `0x180008043`
- `KERNEL32!DeleteCriticalSection` at `0x180007f74`
- `KERNEL32!DeleteCriticalSection` at `0x180008043`
- `KERNEL32!GetProcAddress` at `0x180007d4c`
- `KERNEL32!GetProcAddress` at `0x180007d6c`
- `KERNEL32!GetProcAddress` at `0x180007d8c`
- `KERNEL32!GetProcAddress` at `0x180007d4c`
- `KERNEL32!GetProcAddress` at `0x180007d6c`
- `KERNEL32!GetProcAddress` at `0x180007d8c`
- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x180007e53`
- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x180007e53`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800081ed`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800081ed`
- `ADVAPI32!RegisterTraceGuidsA` at `0x180007cb9`
- `ADVAPI32!RegisterTraceGuidsA` at `0x180007cb9`
- `ADVAPI32!DeregisterEventSource` at `0x1800081ad`
- `ADVAPI32!DeregisterEventSource` at `0x1800081ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007d12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007d12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007dba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007dba`

## string_xrefs

- `0x1800080cb`: `LPD Service`
- `0x180007d05`: `ualapi.dll`

## pseudocode

```c
void ServiceMain()
{
  ULONG64 *v0; // rbx
  const GUID **v1; // rdi
  int v2; // esi
  const GUID *v3; // r8
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  _UNKNOWN **v8; // rbx
  __int64 v9; // rbx
  DWORD v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int started; // edi
  __int64 v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // eax
  TRACEHANDLE v21; // rcx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+64h] [rbp-9Ch]
  _BYTE v28[668]; // [rsp+74h] [rbp-8Ch] BYREF
  _QWORD v29[8]; // [rsp+310h] [rbp+210h] BYREF

  v0 = (ULONG64 *)&WPP_MAIN_CB;
  qword_180013470 = 0;
  WPP_MAIN_CB = 0;
  v1 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_LPDSVC;
  v2 = 1;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  qword_180013478 = 1;
  do
  {
    v3 = *v1;
    TraceGuidReg.Guid = v3;
    ++v1;
    TraceGuidReg.RegHandle = 0;
    v0[4] = (ULONG64)v3;
    RegisterTraceGuidsA(WppControlCallback, v0, v3, 1u, &TraceGuidReg, 0, 0, v0 + 1);
    v0 = (ULONG64 *)*v0;
  }
  while ( v0 );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
  if ( ualapiModule )
    goto LABEL_16;
  Library = LoadLibraryExW(L"ualapi.dll", 0, 0x800u);
  ualapiModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  fnUalInstrument = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(Library, "UalInstrument");
  if ( fnUalInstrument )
  {
    fnUalStart = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStart");
    if ( fnUalStart )
    {
      fnUalStop = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStop");
      if ( fnUalStop )
      {
LABEL_16:
        memset_0(v28, 0, sizeof(v28));
        v26 = 688;
        v27 = SumGuid_PRINT;
        v6 = ((__int64 (__fastcall *)(int *))fnUalStart)(&v26);
        goto LABEL_17;
      }
    }
  }
  v7 = GetLastError();
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  FreeLibrary(ualapiModule);
  ualapiModule = 0;
  fnUalInstrument = 0;
  fnUalStart = 0;
  fnUalStop = 0;
LABEL_17:
  if ( v6 < 0 )
  {
    v2 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids,
        (unsigned int)v6);
  }
  hSvcHandleGLB = RegisterServiceCtrlHandlerA("LPDSVC", (LPHANDLER_FUNCTION)LPDCntrlHandler);
  if ( hSvcHandleGLB )
  {
    if ( (unsigned int)Feature_LpdDeprecationAndRemoval__private_IsEnabledDeviceUsageNoInline() )
    {
      v22 = 2317201;
      v29[0] = &v22;
      v24 = 24;
      v29[2] = &v23;
      v29[7] = 24;
      v29[4] = &v24;
      v23 = 0;
      v29[6] = L"LPD Service";
      v29[1] = 4;
      v29[3] = 4;
      v29[5] = 4;
      EtwEventWriteNoRegistration(AE_PCA_ETW_LOG, AE_PCA_DEPRECATED_FEATURE, 4, v29);
    }
    else
    {
      if ( !(unsigned int)TellSrvcController(2, v11, 1, 30000) )
      {
        v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_61;
        v12 = 13;
        goto LABEL_30;
      }
      if ( !(unsigned int)InitStuff() )
      {
        v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_61;
        v12 = 14;
LABEL_30:
        WPP_SF_(v8[2], v12, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
        goto LABEL_60;
      }
      started = StartLPD();
      if ( started )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v16 = GetLastError();
          WPP_SF_d(v15, 15, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids, v16);
        }
        LpdReportEvent(0xC0000FA3, 0, 0, started);
LABEL_40:
        FreeStrings();
        DeleteCriticalSection(&csConnSemGLB);
        goto LABEL_60;
      }
      if ( !(unsigned int)TellSrvcController(4, v13, 0, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
        StopLPD();
        TellSrvcController(1, v17, 0, 0);
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
      WaitForSingleObject(hEventShutdownGLB, 0xFFFFFFFF);
      if ( !(unsigned int)TellSrvcController(3, v18, 1, 30000)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
      }
      StopLPD();
      FreeStrings();
      DeleteCriticalSection(&csConnSemGLB);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
        v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
      if ( !hSvcHandleGLB )
        goto LABEL_61;
    }
    TellSrvcController(1, v19, 0, 0);
    goto LABEL_60;
  }
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v10 = GetLastError();
    WPP_SF_d(v9, 12, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids, v10);
LABEL_60:
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_61:
  if ( v2 )
  {
    v20 = UalCloseSession();
    if ( v20 >= 0 )
    {
LABEL_66:
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      goto LABEL_67;
    }
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_70;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids,
        (unsigned int)v20);
      goto LABEL_66;
    }
  }
LABEL_67:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
  {
    WPP_SF_(v8[2], 18, WPP_90a417783231378e8d16226d33123045_Traceguids);
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_70:
  if ( hLogHandleGLB )
  {
    DeregisterEventSource(hLogHandleGLB);
    goto LABEL_75;
  }
  if ( v8 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v8 + 28) & 8) != 0 )
  {
    WPP_SF_(v8[2], (unsigned int)((_DWORD)hLogHandleGLB + 19), WPP_90a417783231378e8d16226d33123045_Traceguids);
LABEL_75:
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      WPP_SF_(v8[2], 21, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control )
    {
      while ( v8 )
      {
        v21 = (TRACEHANDLE)v8[1];
        if ( v21 )
        {
          UnregisterTraceGuids(v21);
          v8[1] = 0;
        }
        v8 = (_UNKNOWN **)*v8;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
}

```

## disassembly

```asm
0x180007c10  push    rbp
0x180007c12  push    rbx
0x180007c13  push    rsi
0x180007c14  push    rdi
0x180007c15  push    r12
0x180007c17  push    r14
0x180007c19  push    r15
0x180007c1b  lea     rbp, [rsp-260h]
0x180007c23  sub     rsp, 360h
0x180007c2a  mov     rax, cs:__security_cookie
0x180007c31  xor     rax, rsp
0x180007c34  mov     [rbp+290h+var_40], rax
0x180007c3b  xor     r14d, r14d
0x180007c3e  lea     rax, WPP_ThisDir_CTLGUID_LPDSVC
0x180007c45  lea     rbx, WPP_MAIN_CB
0x180007c4c  mov     cs:qword_180013470, r14
0x180007c53  mov     cs:WPP_MAIN_CB, r14
0x180007c5a  lea     rdi, WPP_REGISTRATION_GUIDS
0x180007c61  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180007c68  lea     esi, [r14+1]
0x180007c6c  mov     cs:WPP_GLOBAL_Control, rbx
0x180007c73  mov     cs:qword_180013478, rsi
0x180007c7a  mov     r8, [rdi]; ControlGuid
0x180007c7d  lea     rax, [rbx+8]
0x180007c81  mov     [rsp+390h+RegistrationHandle], rax; RegistrationHandle
0x180007c86  lea     rcx, WppControlCallback; RequestAddress
0x180007c8d  mov     [rsp+390h+MofResourceName], r14; MofResourceName
0x180007c92  lea     rax, [rsp+390h+var_340]
0x180007c97  mov     [rsp+390h+var_340.Guid], r8
0x180007c9c  lea     rdi, [rdi+8]
0x180007ca0  mov     [rsp+390h+var_340.RegHandle], r14
0x180007ca5  mov     r9d, esi; GuidCount
0x180007ca8  mov     [rsp+390h+MofImagePath], r14; MofImagePath
0x180007cad  mov     rdx, rbx; RequestContext
0x180007cb0  mov     [rsp+390h+TraceGuidReg], rax; TraceGuidReg
0x180007cb5  mov     [rbx+20h], r8
0x180007cb9  call    cs:__imp_RegisterTraceGuidsA
0x180007cbf  mov     rbx, [rbx]
0x180007cc2  test    rbx, rbx
0x180007cc5  jnz     short loc_180007C7A
0x180007cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cce  lea     r15, WPP_GLOBAL_Control
0x180007cd5  lea     r12, WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids
0x180007cdc  cmp     rcx, r15
0x180007cdf  jz      short loc_180007CF6
0x180007ce1  test    [rcx+1Ch], sil
0x180007ce5  jz      short loc_180007CF6
0x180007ce7  mov     rcx, [rcx+10h]
0x180007ceb  lea     edx, [rbx+0Ah]
0x180007cee  mov     r8, r12
0x180007cf1  call    WPP_SF_
0x180007cf6  cmp     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * ualapiModule
0x180007cfd  jnz     loc_180007DDE
0x180007d03  xor     edx, edx; hFile
0x180007d05  lea     rcx, LibFileName; "ualapi.dll"
0x180007d0c  mov     r8d, 800h; dwFlags
0x180007d12  call    cs:__imp_LoadLibraryExW
0x180007d18  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ualapiModule
0x180007d1f  test    rax, rax
0x180007d22  jnz     short loc_180007D42
0x180007d24  call    cs:__imp_GetLastError
0x180007d2a  mov     ebx, eax
0x180007d2c  test    eax, eax
0x180007d2e  jle     loc_180007E18
0x180007d34  movzx   ebx, ax
0x180007d37  or      ebx, 80070000h
0x180007d3d  jmp     loc_180007E18
0x180007d42  lea     rdx, ProcName; "UalInstrument"
0x180007d49  mov     rcx, rax; hModule
0x180007d4c  call    cs:__imp_GetProcAddress
0x180007d52  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x180007d59  test    rax, rax
0x180007d5c  jz      short loc_180007D9E
0x180007d5e  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x180007d65  lea     rdx, aUalstart; "UalStart"
0x180007d6c  call    cs:__imp_GetProcAddress
0x180007d72  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x180007d79  test    rax, rax
0x180007d7c  jz      short loc_180007D9E
0x180007d7e  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x180007d85  lea     rdx, aUalstop; "UalStop"
0x180007d8c  call    cs:__imp_GetProcAddress
0x180007d92  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x180007d99  test    rax, rax
0x180007d9c  jnz     short loc_180007DDE
0x180007d9e  call    cs:__imp_GetLastError
0x180007da4  mov     ebx, eax
0x180007da6  test    eax, eax
0x180007da8  jle     short loc_180007DB3
0x180007daa  movzx   ebx, ax
0x180007dad  or      ebx, 80070000h
0x180007db3  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x180007dba  call    cs:__imp_FreeLibrary
0x180007dc0  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * ualapiModule
0x180007dc7  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, r14; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x180007dce  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, r14; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x180007dd5  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, r14; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x180007ddc  jmp     short loc_180007E18
0x180007dde  xor     edx, edx; Val
0x180007de0  lea     rcx, [rsp+390h+var_31C]; void *
0x180007de5  mov     r8d, 29Ch; Size
0x180007deb  call    memset_0
0x180007df0  movups  xmm0, cs:SumGuid_PRINT
0x180007df7  mov     rax, cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x180007dfe  lea     rcx, [rsp+390h+var_330]
0x180007e03  mov     [rsp+390h+var_330], 2B0h
0x180007e0b  movdqu  [rsp+390h+var_32C], xmm0
0x180007e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e16  mov     ebx, eax
0x180007e18  test    ebx, ebx
0x180007e1a  jns     short loc_180007E45
0x180007e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e23  mov     esi, r14d
0x180007e26  cmp     rcx, r15
0x180007e29  jz      short loc_180007E45
0x180007e2b  test    byte ptr [rcx+1Ch], 8
0x180007e2f  jz      short loc_180007E45
0x180007e31  mov     rcx, [rcx+10h]
0x180007e35  mov     edx, 0Bh
0x180007e3a  mov     r9d, ebx
0x180007e3d  mov     r8, r12
0x180007e40  call    WPP_SF_d
0x180007e45  lea     rdx, LPDCntrlHandler; lpHandlerProc
0x180007e4c  lea     rcx, ServiceName; "LPDSVC"
0x180007e53  call    cs:__imp_RegisterServiceCtrlHandlerA
0x180007e59  mov     cs:hSvcHandleGLB, rax
0x180007e60  test    rax, rax
0x180007e63  jnz     short loc_180007EA1
0x180007e65  mov     rbx, cs:WPP_GLOBAL_Control
0x180007e6c  cmp     rbx, r15
0x180007e6f  jz      loc_180008120
0x180007e75  test    byte ptr [rbx+1Ch], 8
0x180007e79  jz      loc_180008120
0x180007e7f  mov     rbx, [rbx+10h]
0x180007e83  call    cs:__imp_GetLastError
0x180007e89  mov     edx, 0Ch
0x180007e8e  mov     r8, r12
0x180007e91  mov     r9d, eax
0x180007e94  mov     rcx, rbx
0x180007e97  call    WPP_SF_d
0x180007e9c  jmp     loc_180008119
0x180007ea1  call    Feature_LpdDeprecationAndRemoval__private_IsEnabledDeviceUsageNoInline
0x180007ea6  test    eax, eax
0x180007ea8  jnz     loc_180008085
0x180007eae  mov     ebx, 7530h
0x180007eb3  lea     ecx, [rax+2]
0x180007eb6  mov     r9d, ebx
0x180007eb9  lea     r8d, [rax+1]
0x180007ebd  call    TellSrvcController
0x180007ec2  test    eax, eax
0x180007ec4  jnz     short loc_180007EF4
0x180007ec6  mov     rbx, cs:WPP_GLOBAL_Control
0x180007ecd  cmp     rbx, r15
0x180007ed0  jz      loc_180008120
0x180007ed6  test    byte ptr [rbx+1Ch], 8
0x180007eda  jz      loc_180008120
0x180007ee0  lea     edx, [rax+0Dh]
0x180007ee3  mov     rcx, [rbx+10h]
0x180007ee7  mov     r8, r12
0x180007eea  call    WPP_SF_
0x180007eef  jmp     loc_180008119
0x180007ef4  call    InitStuff
0x180007ef9  test    eax, eax
0x180007efb  jnz     short loc_180007F1C
0x180007efd  mov     rbx, cs:WPP_GLOBAL_Control
0x180007f04  cmp     rbx, r15
0x180007f07  jz      loc_180008120
0x180007f0d  test    byte ptr [rbx+1Ch], 8
0x180007f11  jz      loc_180008120
0x180007f17  lea     edx, [rax+0Eh]
0x180007f1a  jmp     short loc_180007EE3
0x180007f1c  call    StartLPD
0x180007f21  mov     edi, eax
0x180007f23  test    eax, eax
0x180007f25  jz      short loc_180007F7F
0x180007f27  mov     rbx, cs:WPP_GLOBAL_Control
0x180007f2e  cmp     rbx, r15
0x180007f31  jz      short loc_180007F56
0x180007f33  test    byte ptr [rbx+1Ch], 8
0x180007f37  jz      short loc_180007F56
0x180007f39  mov     rbx, [rbx+10h]
0x180007f3d  call    cs:__imp_GetLastError
0x180007f43  mov     edx, 0Fh
0x180007f48  mov     r8, r12
0x180007f4b  mov     r9d, eax
0x180007f4e  mov     rcx, rbx
0x180007f51  call    WPP_SF_d
0x180007f56  xor     edx, edx
0x180007f58  mov     r9d, edi
0x180007f5b  xor     r8d, r8d
0x180007f5e  mov     ecx, 0C0000FA3h; dwEventID
0x180007f63  call    LpdReportEvent
0x180007f68  call    FreeStrings
0x180007f6d  lea     rcx, csConnSemGLB; lpCriticalSection
0x180007f74  call    cs:__imp_DeleteCriticalSection
0x180007f7a  jmp     loc_180008119
0x180007f7f  xor     r9d, r9d
0x180007f82  xor     r8d, r8d
0x180007f85  lea     ecx, [r9+4]
0x180007f89  call    TellSrvcController
0x180007f8e  test    eax, eax
0x180007f90  jnz     short loc_180007FC9
0x180007f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f99  cmp     rcx, r15
0x180007f9c  jz      short loc_180007FB3
0x180007f9e  test    byte ptr [rcx+1Ch], 8
0x180007fa2  jz      short loc_180007FB3
0x180007fa4  mov     rcx, [rcx+10h]
0x180007fa8  lea     edx, [rax+10h]
0x180007fab  mov     r8, r12
0x180007fae  call    WPP_SF_
0x180007fb3  call    StopLPD
0x180007fb8  xor     r9d, r9d
0x180007fbb  xor     r8d, r8d
0x180007fbe  lea     ecx, [r9+1]
0x180007fc2  call    TellSrvcController
0x180007fc7  jmp     short loc_180007F68
0x180007fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fd0  cmp     rcx, r15
0x180007fd3  jz      short loc_180007FEC
0x180007fd5  test    byte ptr [rcx+1Ch], 2
0x180007fd9  jz      short loc_180007FEC
0x180007fdb  mov     rcx, [rcx+10h]
0x180007fdf  mov     edx, 11h
0x180007fe4  mov     r8, r12
0x180007fe7  call    WPP_SF_
0x180007fec  mov     rcx, cs:hEventShutdownGLB; hHandle
0x180007ff3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007ff6  call    cs:__imp_WaitForSingleObject
0x180007ffc  mov     ecx, 3
0x180008001  mov     r9d, ebx
0x180008004  lea     r8d, [rcx-2]
0x180008008  call    TellSrvcController
0x18000800d  test    eax, eax
0x18000800f  jnz     short loc_180008032
0x180008011  mov     rcx, cs:WPP_GLOBAL_Control
0x180008018  cmp     rcx, r15
0x18000801b  jz      short loc_180008032
0x18000801d  test    byte ptr [rcx+1Ch], 8
0x180008021  jz      short loc_180008032
0x180008023  mov     rcx, [rcx+10h]
0x180008027  lea     edx, [rax+12h]
0x18000802a  mov     r8, r12
0x18000802d  call    WPP_SF_
0x180008032  call    StopLPD
0x180008037  call    FreeStrings
0x18000803c  lea     rcx, csConnSemGLB; lpCriticalSection
0x180008043  call    cs:__imp_DeleteCriticalSection
0x180008049  mov     rbx, cs:WPP_GLOBAL_Control
0x180008050  cmp     rbx, r15
0x180008053  jz      short loc_180008073
0x180008055  test    byte ptr [rbx+1Ch], 2
0x180008059  jz      short loc_180008073
0x18000805b  mov     rcx, [rbx+10h]
0x18000805f  mov     edx, 13h
0x180008064  mov     r8, r12
0x180008067  call    WPP_SF_
0x18000806c  mov     rbx, cs:WPP_GLOBAL_Control
0x180008073  cmp     cs:hSvcHandleGLB, r14
0x18000807a  jz      loc_180008120
0x180008080  jmp     loc_18000810A
0x180008085  lea     rax, [rsp+390h+var_350]
0x18000808a  mov     [rsp+390h+var_350], 235B91h
0x180008092  mov     edx, 18h
0x180008097  mov     [rbp+290h+var_80], rax
0x18000809e  lea     rcx, [rsp+390h+var_34C]
0x1800080a3  mov     [rsp+390h+var_348], edx
0x1800080a7  mov     [rbp+290h+var_70], rcx
0x1800080ae  lea     r9, [rbp+290h+var_80]
0x1800080b5  lea     rcx, [rsp+390h+var_348]
0x1800080ba  mov     [rbp+290h+var_48], rdx
0x1800080c1  lea     eax, [rdx-14h]
0x1800080c4  mov     [rbp+290h+var_60], rcx
0x1800080cb  lea     rcx, aLpdService; "LPD Service"
0x1800080d2  mov     [rsp+390h+var_34C], r14d
0x1800080d7  mov     [rbp+290h+var_50], rcx
0x1800080de  lea     rdx, AE_PCA_DEPRECATED_FEATURE
0x1800080e5  lea     rcx, AE_PCA_ETW_LOG
0x1800080ec  mov     [rbp+290h+var_78], rax
0x1800080f3  mov     r8d, eax
0x1800080f6  mov     [rbp+290h+var_68], rax
0x1800080fd  mov     [rbp+290h+var_58], rax
0x180008104  call    cs:__imp_EtwEventWriteNoRegistration
0x18000810a  xor     r9d, r9d
0x18000810d  xor     r8d, r8d
0x180008110  lea     ecx, [r9+1]
0x180008114  call    TellSrvcController
0x180008119  mov     rbx, cs:WPP_GLOBAL_Control
0x180008120  test    esi, esi
0x180008122  jz      short loc_18000815A
0x180008124  call    UalCloseSession
0x180008129  test    eax, eax
0x18000812b  jns     short loc_180008153
0x18000812d  mov     rbx, cs:WPP_GLOBAL_Control
0x180008134  cmp     rbx, r15
0x180008137  jz      short loc_180008181
0x180008139  test    byte ptr [rbx+1Ch], 8
0x18000813d  jz      short loc_18000815A
0x18000813f  mov     rcx, [rbx+10h]
0x180008143  mov     edx, 14h
  ... truncated ...
```
