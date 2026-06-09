# EapTlsInitialize2(int,int)

- ea: `0x180005f80`
- end: `0x18000660e`
- name: `?EapTlsInitialize2@@YAKHH@Z`
- size: `1678`
- prototype: `unsigned int __fastcall(int, int)`
- caller_count: `10`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800045d0`
- `0x1800059a0`
- `0x1800059b0`
- `0x180005be0`
- `0x1800643c0`
- `0x180064670`
- `0x180064790`
- `0x180070884`
- `0x180070bf8`
- `0x180076a1c`

## callees

- `0x180004560`
- `0x180005010`
- `0x180005f80`
- `0x180007af0`
- `0x180007d00`
- `0x180018280`
- `0x180018730`
- `0x18001af90`
- `0x18001d460`
- `0x18001df90`
- `0x18001f930`
- `0x180020040`
- `0x1800258fc`
- `0x18002f38c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000656f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006595`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800065c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000656f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006595`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800065c5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005ffd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005ffd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006550`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006443`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000650e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000650e`
- `CRYPT32!CertCloseStore` at `0x1800064a5`
- `CRYPT32!CertCloseStore` at `0x1800064a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000617d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006210`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000617d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006210`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006260`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006260`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005fc0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005fc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180006433`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180006433`
- `rtutils!TraceDeregisterExA` at `0x18000652a`
- `rtutils!TraceDeregisterExA` at `0x18000652a`
- `ext-ms-win-shell-comctl32-init-l1-1-0!InitCommonControlsEx` at `0x180006043`
- `ext-ms-win-shell-comctl32-init-l1-1-0!InitCommonControlsEx` at `0x180006043`

## pseudocode

```c
__int64 __fastcall EapTlsInitialize2(int a1, int a2)
{
  DWORD v3; // ebx
  int v5; // eax
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  int v12; // ecx
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  struct _EAPTLS_CONTROL_BLOCK *v16; // rcx
  DWORD LastError; // eax
  HLOCAL v18; // rsi
  HMODULE v19; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY v22; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+80h] [rbp+40h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+48h] BYREF

  v3 = 0;
  hKey = 0;
  v22 = 0;
  while ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&g_EapTlsInitializeLock) > 1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)&g_EapTlsInitializeLock);
    Sleep(0x3E8u);
  }
  v5 = dword_1800AC0C0;
  if ( a1 )
  {
    if ( dword_1800AC0C0 )
      goto LABEL_60;
    InitializeCriticalSection(&g_csProtectCachedCredentials);
    g_fProtectCachedCredentialsLockInitialized = 1;
    if ( g_pCachedCreds )
      ClearCachedCredList();
    if ( a2 )
    {
      DebugInitEx("RASTLSUI");
      picce.dwSize = 8;
      picce.dwICC = 3;
      InitCommonControlsEx(&picce);
    }
    else
    {
      DebugInitEx("RASTLS");
    }
    v7 = (const unsigned __int16 *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
    if ( !(unsigned int)OpenEapTlsRegistryKey(v7, v6, &hKey) )
    {
      g_eapTlsUseAllPurposeCert = ReadAllPurposeCertKey(hKey, 0);
      if ( g_eapTlsUseAllPurposeCert && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      g_selectSelfSignedCert = ReadSelfSignedKey(hKey);
      g_eapTlsAcceptAllPurposeCert = ReadAcceptAllPurposeCertKey(hKey, 0);
      if ( g_eapTlsAcceptAllPurposeCert && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      g_eapTlsDisableADChecks = ReadADCheckKey(hKey);
      if ( g_eapTlsDisableADChecks && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      g_useCustomRootStore = ReadUseCustomRootStoreKey(hKey);
      if ( g_useCustomRootStore && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      RegCloseKey(hKey);
    }
    if ( !(unsigned int)OpenPeapRegistryKey(v9, v8, &v22) )
    {
      g_peapUseAllPurposeCert = ReadAllPurposeCertKey(v22, 1);
      if ( g_peapUseAllPurposeCert && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      g_peapAcceptAllPurposeCert = ReadAcceptAllPurposeCertKey(v22, 1);
      if ( g_peapAcceptAllPurposeCert && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      RegCloseKey(v22);
    }
    if ( (unsigned int)OpenEapTlsRegistryKey(v11, v10, &hKey) )
    {
LABEL_59:
      EapProvPlugin_Initialize();
      v5 = dword_1800AC0C0;
LABEL_60:
      if ( v5 != -1 )
        dword_1800AC0C0 = v5 + 1;
      goto LABEL_93;
    }
    Type = 0;
    Data = 0;
    picce.dwSize = 4;
    if ( !RegQueryValueExW(hKey, L"OverrideEAPCertificateSelection", 0, &Type, (LPBYTE)&Data, (LPDWORD)&picce)
      && Type == 4
      && picce.dwSize == 4 )
    {
      v12 = (Data >> 12) & 1;
      v13 = (Data >> 8) & 1;
      v14 = (Data >> 4) & 1;
      v15 = Data & 1;
    }
    else
    {
      v12 = 0;
      v13 = 0;
      v14 = 0;
      v15 = 0;
    }
    g_UseDefaultSCardCert = v15;
    g_OverrideSCardFilter = v14;
    g_OverrideRegCertFilter = v13;
    g_IgnorePasswdCerts = v12;
    if ( v15 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_44;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      v15 = g_UseDefaultSCardCert;
    }
    v16 = WPP_GLOBAL_Control;
LABEL_44:
    if ( g_OverrideSCardFilter && v15 )
    {
      if ( v16 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v16 + 2), 22, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      g_UseDefaultSCardCert = 1;
    }
    if ( g_OverrideRegCertFilter && v16 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)v16 + 2), 23, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( g_OverrideSCardFilter && v16 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)v16 + 2), 24, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( g_IgnorePasswdCerts && v16 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v16 + 2), 25, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
    RegCloseKey(hKey);
    goto LABEL_59;
  }
  if ( dword_1800AC0C0 )
  {
    --dword_1800AC0C0;
    if ( v5 == 1 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      if ( !a2 && g_fChangeNotificationSetup )
      {
        if ( !UnregisterWaitEx(g_hWaitonStoreChangeEvt, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
              LastError);
        }
        if ( g_hStoreChangeNotificationEvt )
        {
          CloseHandle(g_hStoreChangeNotificationEvt);
          g_hStoreChangeNotificationEvt = 0;
        }
        if ( g_hLocalMachineStore )
        {
          CertCloseStore(g_hLocalMachineStore, 2u);
          g_hLocalMachineStore = 0;
        }
        g_fChangeNotificationSetup = 0;
      }
      v18 = g_pCachedCreds;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids);
      if ( v18 )
      {
        do
        {
          RemoveNodeFromCachedCredList(v18);
          v18 = g_pCachedCreds;
        }
        while ( g_pCachedCreds );
      }
      g_pCachedCreds = 0;
      LocalFree(g_eapTlsCACertList);
      if ( g_dwEapTlsTraceId != -1 )
      {
        TraceDeregisterExA(g_dwEapTlsTraceId, 4u);
        g_dwEapTlsTraceId = -1;
      }
      if ( g_fProtectCachedCredentialsLockInitialized )
      {
        DeleteCriticalSection(&g_csProtectCachedCredentials);
        g_fProtectCachedCredentialsLockInitialized = 0;
      }
      if ( g_hInstanceScardDlg )
      {
        FreeLibrary(g_hInstanceScardDlg);
        g_hInstanceScardDlg = 0;
        g_fnDlgSelectCard = 0;
      }
      if ( g_netapi32Handle )
        FreeLibrary(g_netapi32Handle);
      v19 = g_hEapProvPluginDll;
      if ( g_hEapProvPluginDll )
      {
        if ( *(&g_EapProvPluginDllFunctionTable + 1) )
        {
          (*(&g_EapProvPluginDllFunctionTable + 1))();
          v19 = g_hEapProvPluginDll;
        }
        FreeLibrary(v19);
        g_hEapProvPluginDll = 0;
      }
      *(_OWORD *)&g_EapProvPluginDllFunctionTable = 0;
      qword_1800AC090 = 0;
      xmmword_1800AC070 = 0;
      xmmword_1800AC080 = 0;
    }
  }
LABEL_93:
  _InterlockedDecrement((volatile signed __int32 *)&g_EapTlsInitializeLock);
  return v3;
}

```

## disassembly

```asm
0x180005f80  push    rbp
0x180005f82  push    rbx
0x180005f83  push    rsi
0x180005f84  push    rdi
0x180005f85  push    r14
0x180005f87  mov     rbp, rsp
0x180005f8a  sub     rsp, 40h
0x180005f8e  xor     r14d, r14d
0x180005f91  mov     esi, edx
0x180005f93  mov     ebx, r14d
0x180005f96  mov     [rbp+hKey], r14
0x180005f9a  mov     [rbp+var_8], r14
0x180005f9e  mov     edi, ecx
0x180005fa0  mov     eax, 1
0x180005fa5  lock xadd cs:?g_EapTlsInitializeLock@@3KA, eax; ulong g_EapTlsInitializeLock
0x180005fad  inc     eax
0x180005faf  cmp     eax, 1
0x180005fb2  jbe     short loc_180005FE0
0x180005fb4  lock dec cs:?g_EapTlsInitializeLock@@3KA; ulong g_EapTlsInitializeLock
0x180005fbb  mov     ecx, 3E8h; dwMilliseconds
0x180005fc0  call    cs:__imp_Sleep
0x180005fc7  nop     dword ptr [rax+rax+00h]
0x180005fcc  mov     eax, 1
0x180005fd1  lock xadd cs:?g_EapTlsInitializeLock@@3KA, eax; ulong g_EapTlsInitializeLock
0x180005fd9  inc     eax
0x180005fdb  cmp     eax, 1
0x180005fde  ja      short loc_180005FB4
0x180005fe0  mov     eax, cs:dword_1800AC0C0
0x180005fe6  test    edi, edi
0x180005fe8  jz      loc_1800063D2
0x180005fee  test    eax, eax
0x180005ff0  jnz     loc_1800063BC
0x180005ff6  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005ffd  call    cs:__imp_InitializeCriticalSection
0x180006004  nop     dword ptr [rax+rax+00h]
0x180006009  cmp     cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA, rbx; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x180006010  mov     cs:?g_fProtectCachedCredentialsLockInitialized@@3HA, 1; int g_fProtectCachedCredentialsLockInitialized
0x18000601a  jz      short loc_180006021
0x18000601c  call    ?ClearCachedCredList@@YAXXZ; ClearCachedCredList(void)
0x180006021  test    esi, esi
0x180006023  jz      short loc_180006051
0x180006025  lea     rcx, aRastlsui; "RASTLSUI"
0x18000602c  call    DebugInitEx
0x180006031  lea     rcx, [rbp+picce]; picce
0x180006035  mov     [rbp+picce.dwSize], 8
0x18000603c  mov     [rbp+picce.dwICC], 3
0x180006043  call    cs:__imp_InitCommonControlsEx
0x18000604a  nop     dword ptr [rax+rax+00h]
0x18000604f  jmp     short loc_18000605D
0x180006051  lea     rcx, aRastls; "RASTLS"
0x180006058  call    DebugInitEx
0x18000605d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006064  lea     rdi, WPP_GLOBAL_Control
0x18000606b  cmp     rcx, rdi
0x18000606e  jz      short loc_180006085
0x180006070  mov     rcx, [rcx+10h]
0x180006074  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18000607b  mov     edx, 0Eh
0x180006080  call    WPP_SF_
0x180006085  lea     r8, [rbp+hKey]; HKEY *
0x180006089  call    ?OpenEapTlsRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenEapTlsRegistryKey(ushort const *,ulong,HKEY__ * *)
0x18000608e  test    eax, eax
0x180006090  jnz     loc_180006189
0x180006096  mov     rcx, [rbp+hKey]; HKEY
0x18000609a  xor     edx, edx; int
0x18000609c  call    ?ReadAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAllPurposeCertKey(HKEY__ *,int)
0x1800060a1  mov     cs:?g_eapTlsUseAllPurposeCert@@3HA, eax; int g_eapTlsUseAllPurposeCert
0x1800060a7  test    eax, eax
0x1800060a9  jz      short loc_1800060CC
0x1800060ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060b2  cmp     rcx, rdi
0x1800060b5  jz      short loc_1800060CC
0x1800060b7  mov     rcx, [rcx+10h]
0x1800060bb  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800060c2  mov     edx, 0Fh
0x1800060c7  call    WPP_SF_
0x1800060cc  mov     rcx, [rbp+hKey]; HKEY
0x1800060d0  call    ?ReadSelfSignedKey@@YAHPEAUHKEY__@@@Z; ReadSelfSignedKey(HKEY__ *)
0x1800060d5  mov     rcx, [rbp+hKey]; HKEY
0x1800060d9  xor     edx, edx; int
0x1800060db  mov     cs:?g_selectSelfSignedCert@@3HA, eax; int g_selectSelfSignedCert
0x1800060e1  call    ?ReadAcceptAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAcceptAllPurposeCertKey(HKEY__ *,int)
0x1800060e6  mov     cs:?g_eapTlsAcceptAllPurposeCert@@3HA, eax; int g_eapTlsAcceptAllPurposeCert
0x1800060ec  test    eax, eax
0x1800060ee  jz      short loc_180006111
0x1800060f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060f7  cmp     rcx, rdi
0x1800060fa  jz      short loc_180006111
0x1800060fc  mov     rcx, [rcx+10h]
0x180006100  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006107  mov     edx, 10h
0x18000610c  call    WPP_SF_
0x180006111  mov     rcx, [rbp+hKey]; hKey
0x180006115  call    ?ReadADCheckKey@@YAHPEAUHKEY__@@@Z; ReadADCheckKey(HKEY__ *)
0x18000611a  mov     cs:?g_eapTlsDisableADChecks@@3HA, eax; int g_eapTlsDisableADChecks
0x180006120  test    eax, eax
0x180006122  jz      short loc_180006145
0x180006124  mov     rcx, cs:WPP_GLOBAL_Control
0x18000612b  cmp     rcx, rdi
0x18000612e  jz      short loc_180006145
0x180006130  mov     rcx, [rcx+10h]
0x180006134  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18000613b  mov     edx, 11h
0x180006140  call    WPP_SF_
0x180006145  mov     rcx, [rbp+hKey]; HKEY
0x180006149  call    ?ReadUseCustomRootStoreKey@@YA_NPEAUHKEY__@@@Z; ReadUseCustomRootStoreKey(HKEY__ *)
0x18000614e  mov     cs:?g_useCustomRootStore@@3_NA, al; bool g_useCustomRootStore
0x180006154  test    al, al
0x180006156  jz      short loc_180006179
0x180006158  mov     rcx, cs:WPP_GLOBAL_Control
0x18000615f  cmp     rcx, rdi
0x180006162  jz      short loc_180006179
0x180006164  mov     rcx, [rcx+10h]
0x180006168  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18000616f  mov     edx, 12h
0x180006174  call    WPP_SF_
0x180006179  mov     rcx, [rbp+hKey]; hKey
0x18000617d  call    cs:__imp_RegCloseKey
0x180006184  nop     dword ptr [rax+rax+00h]
0x180006189  lea     r8, [rbp+var_8]; HKEY *
0x18000618d  call    ?OpenPeapRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenPeapRegistryKey(ushort const *,ulong,HKEY__ * *)
0x180006192  test    eax, eax
0x180006194  jnz     loc_18000621C
0x18000619a  mov     rcx, [rbp+var_8]; HKEY
0x18000619e  mov     edx, 1; int
0x1800061a3  call    ?ReadAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAllPurposeCertKey(HKEY__ *,int)
0x1800061a8  mov     cs:?g_peapUseAllPurposeCert@@3HA, eax; int g_peapUseAllPurposeCert
0x1800061ae  test    eax, eax
0x1800061b0  jz      short loc_1800061D3
0x1800061b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061b9  cmp     rcx, rdi
0x1800061bc  jz      short loc_1800061D3
0x1800061be  mov     rcx, [rcx+10h]
0x1800061c2  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800061c9  mov     edx, 13h
0x1800061ce  call    WPP_SF_
0x1800061d3  mov     rcx, [rbp+var_8]; HKEY
0x1800061d7  mov     edx, 1; int
0x1800061dc  call    ?ReadAcceptAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAcceptAllPurposeCertKey(HKEY__ *,int)
0x1800061e1  mov     cs:?g_peapAcceptAllPurposeCert@@3HA, eax; int g_peapAcceptAllPurposeCert
0x1800061e7  test    eax, eax
0x1800061e9  jz      short loc_18000620C
0x1800061eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061f2  cmp     rcx, rdi
0x1800061f5  jz      short loc_18000620C
0x1800061f7  mov     rcx, [rcx+10h]
0x1800061fb  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006202  mov     edx, 14h
0x180006207  call    WPP_SF_
0x18000620c  mov     rcx, [rbp+var_8]; hKey
0x180006210  call    cs:__imp_RegCloseKey
0x180006217  nop     dword ptr [rax+rax+00h]
0x18000621c  lea     r8, [rbp+hKey]; HKEY *
0x180006220  call    ?OpenEapTlsRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenEapTlsRegistryKey(ushort const *,ulong,HKEY__ * *)
0x180006225  test    eax, eax
0x180006227  jnz     loc_1800063B1
0x18000622d  mov     rcx, [rbp+hKey]; hKey
0x180006231  lea     rax, [rbp+picce]
0x180006235  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000623a  lea     r9, [rbp+Type]; lpType
0x18000623e  lea     rax, [rbp+Data]
0x180006242  mov     [rbp+Type], r14d
0x180006246  xor     r8d, r8d; lpReserved
0x180006249  mov     [rsp+40h+lpData], rax; lpData
0x18000624e  lea     rdx, aOverrideeapcer; "OverrideEAPCertificateSelection"
0x180006255  mov     [rbp+Data], r14d
0x180006259  mov     [rbp+picce.dwSize], 4
0x180006260  call    cs:__imp_RegQueryValueExW
0x180006267  nop     dword ptr [rax+rax+00h]
0x18000626c  test    eax, eax
0x18000626e  jnz     short loc_18000629F
0x180006270  cmp     [rbp+Type], 4
0x180006274  jnz     short loc_18000629F
0x180006276  cmp     [rbp+picce.dwSize], 4
0x18000627a  jnz     short loc_18000629F
0x18000627c  mov     eax, [rbp+Data]
0x18000627f  mov     ecx, eax
0x180006281  mov     edx, eax
0x180006283  shr     ecx, 0Ch
0x180006286  mov     r8d, eax
0x180006289  shr     edx, 8
0x18000628c  shr     r8d, 4
0x180006290  and     ecx, 1
0x180006293  and     edx, 1
0x180006296  and     r8d, 1
0x18000629a  and     eax, 1
0x18000629d  jmp     short loc_1800062AB
0x18000629f  mov     ecx, r14d
0x1800062a2  mov     edx, r14d
0x1800062a5  mov     r8d, r14d
0x1800062a8  mov     eax, r14d
0x1800062ab  mov     cs:?g_UseDefaultSCardCert@@3HA, eax; int g_UseDefaultSCardCert
0x1800062b1  mov     cs:?g_OverrideSCardFilter@@3HA, r8d; int g_OverrideSCardFilter
0x1800062b8  mov     cs:?g_OverrideRegCertFilter@@3HA, edx; int g_OverrideRegCertFilter
0x1800062be  mov     cs:?g_IgnorePasswdCerts@@3HA, ecx; int g_IgnorePasswdCerts
0x1800062c4  test    eax, eax
0x1800062c6  jz      short loc_1800062EF
0x1800062c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062cf  cmp     rcx, rdi
0x1800062d2  jz      short loc_1800062F6
0x1800062d4  mov     rcx, [rcx+10h]
0x1800062d8  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800062df  mov     edx, 15h
0x1800062e4  call    WPP_SF_
0x1800062e9  mov     eax, cs:?g_UseDefaultSCardCert@@3HA; int g_UseDefaultSCardCert
0x1800062ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062f6  cmp     cs:?g_OverrideSCardFilter@@3HA, ebx; int g_OverrideSCardFilter
0x1800062fc  jz      short loc_18000632D
0x1800062fe  test    eax, eax
0x180006300  jz      short loc_18000632D
0x180006302  cmp     rcx, rdi
0x180006305  jz      short loc_180006323
0x180006307  mov     rcx, [rcx+10h]
0x18000630b  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006312  mov     edx, 16h
0x180006317  call    WPP_SF_
0x18000631c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006323  mov     cs:?g_UseDefaultSCardCert@@3HA, 1; int g_UseDefaultSCardCert
0x18000632d  cmp     cs:?g_OverrideRegCertFilter@@3HA, ebx; int g_OverrideRegCertFilter
0x180006333  jz      short loc_180006356
0x180006335  cmp     rcx, rdi
0x180006338  jz      short loc_180006356
0x18000633a  mov     rcx, [rcx+10h]
0x18000633e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006345  mov     edx, 17h
0x18000634a  call    WPP_SF_
0x18000634f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006356  cmp     cs:?g_OverrideSCardFilter@@3HA, ebx; int g_OverrideSCardFilter
0x18000635c  jz      short loc_18000637F
0x18000635e  cmp     rcx, rdi
0x180006361  jz      short loc_18000637F
0x180006363  mov     rcx, [rcx+10h]
0x180006367  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18000636e  mov     edx, 18h
0x180006373  call    WPP_SF_
0x180006378  mov     rcx, cs:WPP_GLOBAL_Control
0x18000637f  cmp     cs:?g_IgnorePasswdCerts@@3HA, ebx; int g_IgnorePasswdCerts
0x180006385  jz      short loc_1800063A1
0x180006387  cmp     rcx, rdi
0x18000638a  jz      short loc_1800063A1
0x18000638c  mov     rcx, [rcx+10h]
0x180006390  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006397  mov     edx, 19h
0x18000639c  call    WPP_SF_
0x1800063a1  mov     rcx, [rbp+hKey]; hKey
0x1800063a5  call    cs:__imp_RegCloseKey
0x1800063ac  nop     dword ptr [rax+rax+00h]
0x1800063b1  call    EapProvPlugin_Initialize
0x1800063b6  mov     eax, cs:dword_1800AC0C0
0x1800063bc  cmp     eax, 0FFFFFFFFh
0x1800063bf  jz      loc_1800065F9
0x1800063c5  inc     eax
0x1800063c7  mov     cs:dword_1800AC0C0, eax
0x1800063cd  jmp     loc_1800065F9
0x1800063d2  test    eax, eax
0x1800063d4  jz      loc_1800065F9
0x1800063da  add     eax, 0FFFFFFFFh
0x1800063dd  mov     cs:dword_1800AC0C0, eax
0x1800063e3  jnz     loc_1800065F9
0x1800063e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f0  lea     rdi, WPP_GLOBAL_Control
0x1800063f7  cmp     rcx, rdi
0x1800063fa  jz      short loc_180006411
0x1800063fc  mov     rcx, [rcx+10h]
0x180006400  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006407  mov     edx, 1Ah
0x18000640c  call    WPP_SF_
0x180006411  test    esi, esi
0x180006413  jnz     loc_1800064BF
0x180006419  cmp     cs:?g_fChangeNotificationSetup@@3HA, ebx; int g_fChangeNotificationSetup
0x18000641f  jz      loc_1800064BF
0x180006425  mov     rcx, cs:?g_hWaitonStoreChangeEvt@@3PEAXEA; WaitHandle
0x18000642c  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006433  call    cs:__imp_UnregisterWaitEx
0x18000643a  nop     dword ptr [rax+rax+00h]
0x18000643f  test    eax, eax
0x180006441  jnz     short loc_180006475
0x180006443  call    cs:__imp_GetLastError
0x18000644a  nop     dword ptr [rax+rax+00h]
0x18000644f  mov     ebx, eax
0x180006451  mov     rcx, cs:WPP_GLOBAL_Control
0x180006458  cmp     rcx, rdi
0x18000645b  jz      short loc_180006475
0x18000645d  mov     rcx, [rcx+10h]
0x180006461  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180006468  mov     edx, 1Bh
0x18000646d  mov     r9d, eax
0x180006470  call    WPP_SF_d
0x180006475  mov     rcx, cs:?g_hStoreChangeNotificationEvt@@3PEAXEA; hObject
0x18000647c  test    rcx, rcx
0x18000647f  jz      short loc_180006494
0x180006481  call    cs:__imp_CloseHandle
0x180006488  nop     dword ptr [rax+rax+00h]
0x18000648d  mov     cs:?g_hStoreChangeNotificationEvt@@3PEAXEA, r14; void * g_hStoreChangeNotificationEvt
0x180006494  mov     rcx, cs:?g_hLocalMachineStore@@3PEAXEA; hCertStore
0x18000649b  test    rcx, rcx
0x18000649e  jz      short loc_1800064B8
0x1800064a0  mov     edx, 2; dwFlags
0x1800064a5  call    cs:__imp_CertCloseStore
0x1800064ac  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
