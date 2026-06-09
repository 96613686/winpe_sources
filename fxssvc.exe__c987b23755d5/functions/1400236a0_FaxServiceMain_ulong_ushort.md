# FaxServiceMain(ulong,ushort * *)

- ea: `0x1400236a0`
- end: `0x140023d11`
- name: `?FaxServiceMain@@YAXKPEAPEAG@Z`
- size: `1649`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140023108`
- `0x1400236a0`
- `0x140023fa0`
- `0x1400247d0`
- `0x1400248c8`
- `0x140024994`
- `0x140025194`
- `0x140046a7c`
- `0x1400480f0`
- `0x140065dbc`
- `0x140070684`
- `0x14007075c`
- `0x1400708c4`
- `0x1400709fc`
- `0x140071d04`
- `0x140081224`
- `0x140081508`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002384e`
- `ADVAPI32!RegCloseKey` at `0x140023bc4`
- `ADVAPI32!RegCloseKey` at `0x14002384e`
- `ADVAPI32!RegCloseKey` at `0x140023bc4`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x14002390b`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x14002390b`
- `ADVAPI32!DeregisterEventSource` at `0x140023c08`
- `ADVAPI32!DeregisterEventSource` at `0x140023c08`
- `KERNEL32!GetLastError` at `0x140023735`
- `KERNEL32!GetLastError` at `0x14002379f`
- `KERNEL32!GetLastError` at `0x140023941`
- `KERNEL32!GetLastError` at `0x1400239b6`
- `KERNEL32!GetLastError` at `0x140023acf`
- `KERNEL32!GetLastError` at `0x140023b4d`
- `KERNEL32!GetLastError` at `0x140023c2a`
- `KERNEL32!GetLastError` at `0x140023735`
- `KERNEL32!GetLastError` at `0x14002379f`
- `KERNEL32!GetLastError` at `0x140023941`
- `KERNEL32!GetLastError` at `0x1400239b6`
- `KERNEL32!GetLastError` at `0x140023acf`
- `KERNEL32!GetLastError` at `0x140023b4d`
- `KERNEL32!GetLastError` at `0x140023c2a`
- `KERNEL32!GetProcessHeap` at `0x140023ccb`
- `KERNEL32!GetProcessHeap` at `0x140023ccb`
- `KERNEL32!WaitForSingleObject` at `0x140023b2b`
- `KERNEL32!WaitForSingleObject` at `0x140023b2b`
- `KERNEL32!DeleteCriticalSection` at `0x140023c6a`
- `KERNEL32!DeleteCriticalSection` at `0x140023c6a`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140023710`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140023710`
- `KERNEL32!SetErrorMode` at `0x14002375c`
- `KERNEL32!SetErrorMode` at `0x140023767`
- `KERNEL32!SetErrorMode` at `0x14002375c`
- `KERNEL32!SetErrorMode` at `0x140023767`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14002385b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14002385b`
- `KERNEL32!HeapDestroy` at `0x140023cdd`
- `KERNEL32!HeapDestroy` at `0x140023cdd`
- `msvcrt!_wcsicmp` at `0x14002387c`
- `msvcrt!_wcsicmp` at `0x1400238b4`
- `msvcrt!_wcsicmp` at `0x14002387c`
- `msvcrt!_wcsicmp` at `0x1400238b4`

## string_xrefs

- `0x140023971`: `Software\Microsoft\Fax\Client\ServiceStartup`
- `0x140023a8b`: `RPCReady`
- `0x140023a99`: `RPCReady`

## pseudocode

```c
void __fastcall FaxServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  DWORD LastError; // eax
  UINT v5; // eax
  DWORD v6; // eax
  __int64 v7; // rdx
  HKEY v8; // rax
  HKEY v9; // rbx
  unsigned int i; // ebx
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // eax
  HKEY v14; // rsi
  int v15; // eax
  unsigned int v16; // edx
  CMapDeviceId *v17; // rcx
  int v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // ebx
  CMapDeviceId *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  int RegistryDwordDefault; // eax
  CMapDeviceId *v26; // rcx
  DWORD v27; // eax
  DWORD v28; // eax
  int v29; // eax
  unsigned int v30; // ecx
  DWORD v31; // eax
  unsigned int j; // ebx
  unsigned int v33; // edx
  int Data; // [rsp+60h] [rbp+18h] BYREF

  debugOpenLogFile();
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  Data = GetRedirectionPolicy();
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &Data, 4)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
  }
  v5 = SetErrorMode(0);
  SetErrorMode(v5 | 4);
  EncryptReceiptsPassword();
  if ( !(unsigned int)InitializeServiceGlobals() )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      v7 = 51;
LABEL_15:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v6);
      goto LABEL_86;
    }
    goto LABEL_86;
  }
  if ( !(unsigned int)InitializeFaxLibrariesGlobals() )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    }
    goto LABEL_86;
  }
  v8 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax", 1, 131097);
  v9 = v8;
  if ( v8 )
  {
    GetRegistryDwordEx(v8, L"UseDefaultFaultHandlingPolicy", &::Data);
    RegCloseKey(v9);
  }
  SetUnhandledExceptionFilter(FaxUnhandledExceptionFilter);
  for ( i = 1; i < a1; ++i )
  {
    if ( _wcsicmp(a2[i], L"/AlwaysRun") )
    {
      if ( _wcsicmp(a2[i], L"/DelaySuicide") )
        continue;
      g_bDelaySuicideAttempt = 1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        continue;
      }
      v12 = 54;
    }
    else
    {
      g_bServiceCanSuicide = 0;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        continue;
      }
      v12 = 53;
    }
    WPP_SF_(*((_QWORD *)v11 + 2), v12, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  hServiceStatus = RegisterServiceCtrlHandlerW(L"Fax", FaxServiceCtrlHandler);
  if ( !hServiceStatus )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v13);
    }
    goto LABEL_86;
  }
  v14 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax\\Client\\ServiceStartup", 1, 131103);
  if ( v14 )
  {
    v15 = UalOpenSession();
    if ( v15 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      v18 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids,
          (unsigned int)v15);
      }
    }
    else
    {
      v18 = 1;
    }
    v19 = ServiceStart((__int64)v17, v16);
    v21 = v19;
    if ( v19 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v23 = 58;
      v24 = v19;
LABEL_76:
      WPP_SF_d(*((_QWORD *)v22 + 2), v23, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v24);
LABEL_77:
      if ( v18 )
      {
        v29 = UalCloseSession();
        if ( v29 < 0
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids,
            (unsigned int)v29);
        }
      }
      v30 = 1;
      if ( !v21 )
        v30 = 3;
      EndFaxSvc(v30);
      RegCloseKey(v14);
      goto LABEL_86;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    }
    ReportServiceStatus(4u, v20, 0);
    Data = 0;
    RegistryDwordDefault = GetRegistryDwordDefault(v14, L"RPCReady", (BYTE *)&Data);
    if ( !(unsigned int)SetRegistryDword(v14, L"RPCReady", (Data & (unsigned int)-(RegistryDwordDefault != 0)) + 1) )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      {
LABEL_71:
        if ( !WaitForSingleObject(g_hSCMServiceShutDownEvent, 0xFFFFFFFF)
          || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v28 = GetLastError();
        v22 = WPP_GLOBAL_Control;
        v23 = 62;
        v24 = v28;
        goto LABEL_76;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_67:
        if ( v26 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 4) != 0 && *((_BYTE *)v26 + 25) >= 5u )
          WPP_SF_(*((_QWORD *)v26 + 2), 61, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
        goto LABEL_71;
      }
      v27 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v27);
    }
    v26 = WPP_GLOBAL_Control;
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    v7 = 56;
    goto LABEL_15;
  }
LABEL_86:
  FreeServiceGlobals();
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
  }
  if ( hEventLog )
  {
    if ( !DeregisterEventSource(hEventLog)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids, v31);
    }
    hEventLog = 0;
  }
  if ( byte_1400A18A8 )
  {
    DeleteCriticalSection(&stru_1400A1850);
    byte_1400A18A8 = 0;
  }
  for ( j = 0; j < dword_1400A187C; ++j )
    pMemFree(*((LPVOID *)gs_pFaxCategory + 2 * j));
  pMemFree(gs_pFaxCategory);
  gs_pFaxCategory = 0;
  dword_1400A187C = 0;
  if ( hHeap )
  {
    if ( hHeap != GetProcessHeap() )
      HeapDestroy(hHeap);
    hHeap = 0;
  }
  ReportServiceStatus(1u, v33, 0);
}

```

## disassembly

```asm
0x1400236a0  mov     [rsp+arg_0], rbx
0x1400236a5  mov     [rsp+arg_8], rsi
0x1400236aa  push    rdi
0x1400236ab  push    r12
0x1400236ad  push    r13
0x1400236af  push    r14
0x1400236b1  push    r15
0x1400236b3  sub     rsp, 20h
0x1400236b7  mov     r14, rdx
0x1400236ba  mov     esi, ecx
0x1400236bc  call    debugOpenLogFile
0x1400236c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400236c8  lea     r12, WPP_GLOBAL_Control
0x1400236cf  mov     r15d, 4
0x1400236d5  cmp     rcx, r12
0x1400236d8  jz      short loc_1400236FA
0x1400236da  test    [rcx+1Ch], r15b
0x1400236de  jz      short loc_1400236FA
0x1400236e0  cmp     byte ptr [rcx+19h], 5
0x1400236e4  jb      short loc_1400236FA
0x1400236e6  mov     rcx, [rcx+10h]
0x1400236ea  lea     edx, [r15+2Ch]
0x1400236ee  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400236f5  call    WPP_SF_
0x1400236fa  call    ?GetRedirectionPolicy@@YA?AU_PROCESS_MITIGATION_REDIRECTION_TRUST_POLICY@@XZ; GetRedirectionPolicy(void)
0x1400236ff  mov     r8, r15
0x140023702  mov     [rsp+48h+Data], eax
0x140023706  lea     rdx, [rsp+48h+Data]
0x14002370b  mov     ecx, 10h
0x140023710  call    cs:__imp_SetProcessMitigationPolicy
0x140023716  mov     r13b, 2
0x140023719  test    eax, eax
0x14002371b  jnz     short loc_14002375A
0x14002371d  mov     rax, cs:WPP_GLOBAL_Control
0x140023724  cmp     rax, r12
0x140023727  jz      short loc_14002375A
0x140023729  test    [rax+1Ch], r15b
0x14002372d  jz      short loc_14002375A
0x14002372f  cmp     [rax+19h], r13b
0x140023733  jb      short loc_14002375A
0x140023735  call    cs:__imp_GetLastError
0x14002373b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023742  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023749  mov     edx, 2Fh ; '/'
0x14002374e  mov     r9d, eax
0x140023751  mov     rcx, [rcx+10h]
0x140023755  call    WPP_SF_d
0x14002375a  xor     ecx, ecx; uMode
0x14002375c  call    cs:__imp_SetErrorMode
0x140023762  or      eax, r15d
0x140023765  mov     ecx, eax; uMode
0x140023767  call    cs:__imp_SetErrorMode
0x14002376d  call    ?EncryptReceiptsPassword@@YAXXZ; EncryptReceiptsPassword(void)
0x140023772  call    InitializeServiceGlobals
0x140023777  test    eax, eax
0x140023779  jnz     short loc_1400237C9
0x14002377b  mov     rax, cs:WPP_GLOBAL_Control
0x140023782  cmp     rax, r12
0x140023785  jz      loc_140023BCA
0x14002378b  test    [rax+1Ch], r15b
0x14002378f  jz      loc_140023BCA
0x140023795  cmp     [rax+19h], r13b
0x140023799  jb      loc_140023BCA
0x14002379f  call    cs:__imp_GetLastError
0x1400237a5  mov     edx, 33h ; '3'
0x1400237aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237b1  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400237b8  mov     r9d, eax
0x1400237bb  mov     rcx, [rcx+10h]
0x1400237bf  call    WPP_SF_d
0x1400237c4  jmp     loc_140023BCA
0x1400237c9  call    InitializeFaxLibrariesGlobals
0x1400237ce  test    eax, eax
0x1400237d0  jnz     short loc_14002380E
0x1400237d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237d9  cmp     rcx, r12
0x1400237dc  jz      loc_140023BCA
0x1400237e2  test    [rcx+1Ch], r15b
0x1400237e6  jz      loc_140023BCA
0x1400237ec  cmp     [rcx+19h], r13b
0x1400237f0  jb      loc_140023BCA
0x1400237f6  mov     rcx, [rcx+10h]
0x1400237fa  lea     edx, [rax+34h]
0x1400237fd  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023804  call    WPP_SF_
0x140023809  jmp     loc_140023BCA
0x14002380e  mov     r9d, 20019h
0x140023814  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14002381b  mov     r8d, 1
0x140023821  mov     rcx, 0FFFFFFFF80000002h
0x140023828  call    OpenRegistryKey
0x14002382d  mov     rbx, rax
0x140023830  test    rax, rax
0x140023833  jz      short loc_140023854
0x140023835  lea     r8, Data; lpData
0x14002383c  mov     rcx, rax; hKey
0x14002383f  lea     rdx, aUsedefaultfaul; "UseDefaultFaultHandlingPolicy"
0x140023846  call    GetRegistryDwordEx
0x14002384b  mov     rcx, rbx; hKey
0x14002384e  call    cs:__imp_RegCloseKey
0x140023854  lea     rcx, ?FaxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x14002385b  call    cs:__imp_SetUnhandledExceptionFilter
0x140023861  mov     ebx, 1
0x140023866  cmp     esi, ebx
0x140023868  jbe     loc_1400238FD
0x14002386e  movsxd  rdi, ebx
0x140023871  lea     rdx, aAlwaysrun; "/AlwaysRun"
0x140023878  mov     rcx, [r14+rdi*8]; String1
0x14002387c  call    cs:__imp__wcsicmp
0x140023882  test    eax, eax
0x140023884  jnz     short loc_1400238A9
0x140023886  mov     cs:?g_bServiceCanSuicide@@3HA, eax; int g_bServiceCanSuicide
0x14002388c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023893  cmp     rcx, r12
0x140023896  jz      short loc_1400238F3
0x140023898  test    [rcx+1Ch], r15b
0x14002389c  jz      short loc_1400238F3
0x14002389e  cmp     byte ptr [rcx+19h], 5
0x1400238a2  jb      short loc_1400238F3
0x1400238a4  lea     edx, [rax+35h]
0x1400238a7  jmp     short loc_1400238E3
0x1400238a9  mov     rcx, [r14+rdi*8]; String1
0x1400238ad  lea     rdx, aDelaysuicide; "/DelaySuicide"
0x1400238b4  call    cs:__imp__wcsicmp
0x1400238ba  test    eax, eax
0x1400238bc  jnz     short loc_1400238F3
0x1400238be  mov     cs:?g_bDelaySuicideAttempt@@3HA, 1; int g_bDelaySuicideAttempt
0x1400238c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400238cf  cmp     rcx, r12
0x1400238d2  jz      short loc_1400238F3
0x1400238d4  test    [rcx+1Ch], r15b
0x1400238d8  jz      short loc_1400238F3
0x1400238da  cmp     byte ptr [rcx+19h], 5
0x1400238de  jb      short loc_1400238F3
0x1400238e0  lea     edx, [rax+36h]
0x1400238e3  mov     rcx, [rcx+10h]
0x1400238e7  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400238ee  call    WPP_SF_
0x1400238f3  inc     ebx
0x1400238f5  cmp     ebx, esi
0x1400238f7  jb      loc_14002386E
0x1400238fd  lea     rdx, ?FaxServiceCtrlHandler@@YAXK@Z; lpHandlerProc
0x140023904  lea     rcx, SubsystemName; "Fax"
0x14002390b  call    cs:__imp_RegisterServiceCtrlHandlerW
0x140023911  mov     cs:hServiceStatus, rax
0x140023918  test    rax, rax
0x14002391b  jnz     short loc_14002396B
0x14002391d  mov     rax, cs:WPP_GLOBAL_Control
0x140023924  cmp     rax, r12
0x140023927  jz      loc_140023BCA
0x14002392d  test    [rax+1Ch], r15b
0x140023931  jz      loc_140023BCA
0x140023937  cmp     [rax+19h], r13b
0x14002393b  jb      loc_140023BCA
0x140023941  call    cs:__imp_GetLastError
0x140023947  mov     rcx, cs:WPP_GLOBAL_Control
0x14002394e  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023955  mov     edx, 37h ; '7'
0x14002395a  mov     r9d, eax
0x14002395d  mov     rcx, [rcx+10h]
0x140023961  call    WPP_SF_d
0x140023966  jmp     loc_140023BCA
0x14002396b  mov     r9d, 2001Fh
0x140023971  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Fax\\Client\\Servi"...
0x140023978  mov     r8d, 1
0x14002397e  mov     rcx, 0FFFFFFFF80000002h
0x140023985  call    OpenRegistryKey
0x14002398a  mov     rsi, rax
0x14002398d  test    rax, rax
0x140023990  jnz     short loc_1400239C4
0x140023992  mov     rax, cs:WPP_GLOBAL_Control
0x140023999  cmp     rax, r12
0x14002399c  jz      loc_140023BCA
0x1400239a2  test    [rax+1Ch], r15b
0x1400239a6  jz      loc_140023BCA
0x1400239ac  cmp     [rax+19h], r13b
0x1400239b0  jb      loc_140023BCA
0x1400239b6  call    cs:__imp_GetLastError
0x1400239bc  lea     edx, [rsi+38h]
0x1400239bf  jmp     loc_1400237AA
0x1400239c4  call    UalOpenSession
0x1400239c9  test    eax, eax
0x1400239cb  js      short loc_1400239D4
0x1400239cd  mov     edi, 1
0x1400239d2  jmp     short loc_140023A04
0x1400239d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400239db  xor     edi, edi
0x1400239dd  cmp     rcx, r12
0x1400239e0  jz      short loc_140023A04
0x1400239e2  test    [rcx+1Ch], r15b
0x1400239e6  jz      short loc_140023A04
0x1400239e8  cmp     [rcx+19h], r13b
0x1400239ec  jb      short loc_140023A04
0x1400239ee  mov     rcx, [rcx+10h]
0x1400239f2  lea     edx, [rdi+39h]
0x1400239f5  mov     r9d, eax
0x1400239f8  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400239ff  call    WPP_SF_d
0x140023a04  call    ?ServiceStart@@YAKXZ; ServiceStart(void)
0x140023a09  mov     ebx, eax
0x140023a0b  test    eax, eax
0x140023a0d  jz      short loc_140023A40
0x140023a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a16  cmp     rcx, r12
0x140023a19  jz      loc_140023B72
0x140023a1f  test    [rcx+1Ch], r15b
0x140023a23  jz      loc_140023B72
0x140023a29  cmp     [rcx+19h], r13b
0x140023a2d  jb      loc_140023B72
0x140023a33  mov     edx, 3Ah ; ':'
0x140023a38  mov     r9d, eax
0x140023a3b  jmp     loc_140023B62
0x140023a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a47  cmp     rcx, r12
0x140023a4a  jz      short loc_140023A6D
0x140023a4c  test    [rcx+1Ch], r15b
0x140023a50  jz      short loc_140023A6D
0x140023a52  cmp     byte ptr [rcx+19h], 5
0x140023a56  jb      short loc_140023A6D
0x140023a58  mov     rcx, [rcx+10h]
0x140023a5c  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023a63  mov     edx, 3Bh ; ';'
0x140023a68  call    WPP_SF_
0x140023a6d  xor     r8d, r8d; unsigned int
0x140023a70  mov     ecx, r15d; unsigned int
0x140023a73  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x140023a78  xor     r9d, r9d
0x140023a7b  mov     [rsp+48h+Data], 0
0x140023a83  lea     r8, [rsp+48h+Data]; lpData
0x140023a88  mov     rcx, rsi; hKey
0x140023a8b  lea     rdx, aRpcready; "RPCReady"
0x140023a92  call    GetRegistryDwordDefault
0x140023a97  neg     eax
0x140023a99  lea     rdx, aRpcready; "RPCReady"
0x140023aa0  mov     rcx, rsi
0x140023aa3  sbb     r8d, r8d
0x140023aa6  and     r8d, [rsp+48h+Data]
0x140023aab  inc     r8d
0x140023aae  call    SetRegistryDword
0x140023ab3  test    eax, eax
0x140023ab5  jnz     short loc_140023AF4
0x140023ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140023abe  cmp     rcx, r12
0x140023ac1  jz      short loc_140023B21
0x140023ac3  test    [rcx+1Ch], r15b
0x140023ac7  jz      short loc_140023AFB
0x140023ac9  cmp     [rcx+19h], r13b
0x140023acd  jb      short loc_140023AFB
0x140023acf  call    cs:__imp_GetLastError
0x140023ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140023adc  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023ae3  mov     edx, 3Ch ; '<'
0x140023ae8  mov     r9d, eax
0x140023aeb  mov     rcx, [rcx+10h]
0x140023aef  call    WPP_SF_d
0x140023af4  mov     rcx, cs:WPP_GLOBAL_Control
0x140023afb  cmp     rcx, r12
0x140023afe  jz      short loc_140023B21
0x140023b00  test    [rcx+1Ch], r15b
0x140023b04  jz      short loc_140023B21
0x140023b06  cmp     byte ptr [rcx+19h], 5
0x140023b0a  jb      short loc_140023B21
0x140023b0c  mov     rcx, [rcx+10h]
0x140023b10  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023b17  mov     edx, 3Dh ; '='
0x140023b1c  call    WPP_SF_
0x140023b21  mov     rcx, cs:?g_hSCMServiceShutDownEvent@@3PEAXEA; hHandle
0x140023b28  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140023b2b  call    cs:__imp_WaitForSingleObject
0x140023b31  test    eax, eax
0x140023b33  jz      short loc_140023B72
0x140023b35  mov     rax, cs:WPP_GLOBAL_Control
0x140023b3c  cmp     rax, r12
0x140023b3f  jz      short loc_140023B72
0x140023b41  test    [rax+1Ch], r15b
0x140023b45  jz      short loc_140023B72
0x140023b47  cmp     [rax+19h], r13b
0x140023b4b  jb      short loc_140023B72
0x140023b4d  call    cs:__imp_GetLastError
0x140023b53  mov     rcx, cs:WPP_GLOBAL_Control
0x140023b5a  mov     edx, 3Eh ; '>'
0x140023b5f  mov     r9d, eax
0x140023b62  mov     rcx, [rcx+10h]
0x140023b66  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023b6d  call    WPP_SF_d
0x140023b72  test    edi, edi
0x140023b74  jz      short loc_140023BAF
0x140023b76  call    UalCloseSession
0x140023b7b  test    eax, eax
0x140023b7d  jns     short loc_140023BAF
0x140023b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140023b86  cmp     rcx, r12
0x140023b89  jz      short loc_140023BAF
0x140023b8b  test    [rcx+1Ch], r15b
0x140023b8f  jz      short loc_140023BAF
0x140023b91  cmp     [rcx+19h], r13b
0x140023b95  jb      short loc_140023BAF
0x140023b97  mov     rcx, [rcx+10h]
0x140023b9b  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140023ba2  mov     edx, 3Fh ; '?'
  ... truncated ...
```
