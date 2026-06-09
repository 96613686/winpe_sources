# EapTlsInitialize2(int,int)

- ea: `0x180005ac0`
- end: `0x1800060e3`
- name: `?EapTlsInitialize2@@YAKHH@Z`
- size: `1571`
- prototype: `unsigned int __fastcall(int, int)`
- caller_count: `10`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004230`
- `0x1800054f0`
- `0x180005500`
- `0x180005730`
- `0x180060a40`
- `0x180060ce0`
- `0x180060e00`
- `0x18006c11c`
- `0x18006c46c`
- `0x180071b98`

## callees

- `0x1800041c0`
- `0x180004bd0`
- `0x180005ac0`
- `0x1800073b0`
- `0x1800075b0`
- `0x180016bf0`
- `0x180016f90`
- `0x180019730`
- `0x18001bab0`
- `0x18001c590`
- `0x18001dd20`
- `0x18001e320`
- `0x180022f1c`
- `0x18002ce48`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006057`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006077`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800060a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006057`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006077`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800060a1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005b37`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005b37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000603e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000603e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006008`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006008`
- `CRYPT32!CertCloseStore` at `0x180005fa5`
- `CRYPT32!CertCloseStore` at `0x180005fa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005cab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ebd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005cab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ebd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005d7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005d7e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005b00`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005b00`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005f45`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005f45`
- `rtutils!TraceDeregisterExA` at `0x18000601e`
- `rtutils!TraceDeregisterExA` at `0x18000601e`
- `ext-ms-win-shell-comctl32-init-l1-1-0!InitCommonControlsEx` at `0x180005b77`
- `ext-ms-win-shell-comctl32-init-l1-1-0!InitCommonControlsEx` at `0x180005b77`

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
  v5 = dword_1800A5FF0;
  if ( a1 )
  {
    if ( dword_1800A5FF0 )
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
      v5 = dword_1800A5FF0;
LABEL_60:
      if ( v5 != -1 )
        dword_1800A5FF0 = v5 + 1;
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
  if ( dword_1800A5FF0 )
  {
    --dword_1800A5FF0;
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
      qword_1800A5FC0 = 0;
      xmmword_1800A5FA0 = 0;
      xmmword_1800A5FB0 = 0;
    }
  }
LABEL_93:
  _InterlockedDecrement((volatile signed __int32 *)&g_EapTlsInitializeLock);
  return v3;
}

```

## disassembly

```asm
0x180005ac0  push    rbp
0x180005ac2  push    rbx
0x180005ac3  push    rsi
0x180005ac4  push    rdi
0x180005ac5  push    r14
0x180005ac7  mov     rbp, rsp
0x180005aca  sub     rsp, 40h
0x180005ace  xor     r14d, r14d
0x180005ad1  mov     esi, edx
0x180005ad3  mov     ebx, r14d
0x180005ad6  mov     [rbp+hKey], r14
0x180005ada  mov     [rbp+var_8], r14
0x180005ade  mov     edi, ecx
0x180005ae0  mov     eax, 1
0x180005ae5  lock xadd cs:?g_EapTlsInitializeLock@@3KA, eax; ulong g_EapTlsInitializeLock
0x180005aed  inc     eax
0x180005aef  cmp     eax, 1
0x180005af2  jbe     short loc_180005B1A
0x180005af4  lock dec cs:?g_EapTlsInitializeLock@@3KA; ulong g_EapTlsInitializeLock
0x180005afb  mov     ecx, 3E8h; dwMilliseconds
0x180005b00  call    cs:__imp_Sleep
0x180005b06  mov     eax, 1
0x180005b0b  lock xadd cs:?g_EapTlsInitializeLock@@3KA, eax; ulong g_EapTlsInitializeLock
0x180005b13  inc     eax
0x180005b15  cmp     eax, 1
0x180005b18  ja      short loc_180005AF4
0x180005b1a  mov     eax, cs:dword_1800A5FF0
0x180005b20  test    edi, edi
0x180005b22  jz      loc_180005EE4
0x180005b28  test    eax, eax
0x180005b2a  jnz     loc_180005ECE
0x180005b30  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005b37  call    cs:__imp_InitializeCriticalSection
0x180005b3d  cmp     cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA, rbx; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x180005b44  mov     cs:?g_fProtectCachedCredentialsLockInitialized@@3HA, 1; int g_fProtectCachedCredentialsLockInitialized
0x180005b4e  jz      short loc_180005B55
0x180005b50  call    ?ClearCachedCredList@@YAXXZ; ClearCachedCredList(void)
0x180005b55  test    esi, esi
0x180005b57  jz      short loc_180005B7F
0x180005b59  lea     rcx, aRastlsui; "RASTLSUI"
0x180005b60  call    DebugInitEx
0x180005b65  lea     rcx, [rbp+picce]; picce
0x180005b69  mov     [rbp+picce.dwSize], 8
0x180005b70  mov     [rbp+picce.dwICC], 3
0x180005b77  call    cs:__imp_InitCommonControlsEx
0x180005b7d  jmp     short loc_180005B8B
0x180005b7f  lea     rcx, aRastls; "RASTLS"
0x180005b86  call    DebugInitEx
0x180005b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b92  lea     rdi, WPP_GLOBAL_Control
0x180005b99  cmp     rcx, rdi
0x180005b9c  jz      short loc_180005BB3
0x180005b9e  mov     rcx, [rcx+10h]
0x180005ba2  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005ba9  mov     edx, 0Eh
0x180005bae  call    WPP_SF_
0x180005bb3  lea     r8, [rbp+hKey]; HKEY *
0x180005bb7  call    ?OpenEapTlsRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenEapTlsRegistryKey(ushort const *,ulong,HKEY__ * *)
0x180005bbc  test    eax, eax
0x180005bbe  jnz     loc_180005CB1
0x180005bc4  mov     rcx, [rbp+hKey]; HKEY
0x180005bc8  xor     edx, edx; int
0x180005bca  call    ?ReadAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAllPurposeCertKey(HKEY__ *,int)
0x180005bcf  mov     cs:?g_eapTlsUseAllPurposeCert@@3HA, eax; int g_eapTlsUseAllPurposeCert
0x180005bd5  test    eax, eax
0x180005bd7  jz      short loc_180005BFA
0x180005bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005be0  cmp     rcx, rdi
0x180005be3  jz      short loc_180005BFA
0x180005be5  mov     rcx, [rcx+10h]
0x180005be9  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005bf0  mov     edx, 0Fh
0x180005bf5  call    WPP_SF_
0x180005bfa  mov     rcx, [rbp+hKey]; HKEY
0x180005bfe  call    ?ReadSelfSignedKey@@YAHPEAUHKEY__@@@Z; ReadSelfSignedKey(HKEY__ *)
0x180005c03  mov     rcx, [rbp+hKey]; HKEY
0x180005c07  xor     edx, edx; int
0x180005c09  mov     cs:?g_selectSelfSignedCert@@3HA, eax; int g_selectSelfSignedCert
0x180005c0f  call    ?ReadAcceptAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAcceptAllPurposeCertKey(HKEY__ *,int)
0x180005c14  mov     cs:?g_eapTlsAcceptAllPurposeCert@@3HA, eax; int g_eapTlsAcceptAllPurposeCert
0x180005c1a  test    eax, eax
0x180005c1c  jz      short loc_180005C3F
0x180005c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c25  cmp     rcx, rdi
0x180005c28  jz      short loc_180005C3F
0x180005c2a  mov     rcx, [rcx+10h]
0x180005c2e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005c35  mov     edx, 10h
0x180005c3a  call    WPP_SF_
0x180005c3f  mov     rcx, [rbp+hKey]; hKey
0x180005c43  call    ?ReadADCheckKey@@YAHPEAUHKEY__@@@Z; ReadADCheckKey(HKEY__ *)
0x180005c48  mov     cs:?g_eapTlsDisableADChecks@@3HA, eax; int g_eapTlsDisableADChecks
0x180005c4e  test    eax, eax
0x180005c50  jz      short loc_180005C73
0x180005c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c59  cmp     rcx, rdi
0x180005c5c  jz      short loc_180005C73
0x180005c5e  mov     rcx, [rcx+10h]
0x180005c62  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005c69  mov     edx, 11h
0x180005c6e  call    WPP_SF_
0x180005c73  mov     rcx, [rbp+hKey]; HKEY
0x180005c77  call    ?ReadUseCustomRootStoreKey@@YA_NPEAUHKEY__@@@Z; ReadUseCustomRootStoreKey(HKEY__ *)
0x180005c7c  mov     cs:?g_useCustomRootStore@@3_NA, al; bool g_useCustomRootStore
0x180005c82  test    al, al
0x180005c84  jz      short loc_180005CA7
0x180005c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c8d  cmp     rcx, rdi
0x180005c90  jz      short loc_180005CA7
0x180005c92  mov     rcx, [rcx+10h]
0x180005c96  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005c9d  mov     edx, 12h
0x180005ca2  call    WPP_SF_
0x180005ca7  mov     rcx, [rbp+hKey]; hKey
0x180005cab  call    cs:__imp_RegCloseKey
0x180005cb1  lea     r8, [rbp+var_8]; HKEY *
0x180005cb5  call    ?OpenPeapRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenPeapRegistryKey(ushort const *,ulong,HKEY__ * *)
0x180005cba  test    eax, eax
0x180005cbc  jnz     short loc_180005D3A
0x180005cbe  mov     rcx, [rbp+var_8]; HKEY
0x180005cc2  mov     edx, 1; int
0x180005cc7  call    ?ReadAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAllPurposeCertKey(HKEY__ *,int)
0x180005ccc  mov     cs:?g_peapUseAllPurposeCert@@3HA, eax; int g_peapUseAllPurposeCert
0x180005cd2  test    eax, eax
0x180005cd4  jz      short loc_180005CF7
0x180005cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cdd  cmp     rcx, rdi
0x180005ce0  jz      short loc_180005CF7
0x180005ce2  mov     rcx, [rcx+10h]
0x180005ce6  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005ced  mov     edx, 13h
0x180005cf2  call    WPP_SF_
0x180005cf7  mov     rcx, [rbp+var_8]; HKEY
0x180005cfb  mov     edx, 1; int
0x180005d00  call    ?ReadAcceptAllPurposeCertKey@@YAHPEAUHKEY__@@H@Z; ReadAcceptAllPurposeCertKey(HKEY__ *,int)
0x180005d05  mov     cs:?g_peapAcceptAllPurposeCert@@3HA, eax; int g_peapAcceptAllPurposeCert
0x180005d0b  test    eax, eax
0x180005d0d  jz      short loc_180005D30
0x180005d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d16  cmp     rcx, rdi
0x180005d19  jz      short loc_180005D30
0x180005d1b  mov     rcx, [rcx+10h]
0x180005d1f  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005d26  mov     edx, 14h
0x180005d2b  call    WPP_SF_
0x180005d30  mov     rcx, [rbp+var_8]; hKey
0x180005d34  call    cs:__imp_RegCloseKey
0x180005d3a  lea     r8, [rbp+hKey]; HKEY *
0x180005d3e  call    ?OpenEapTlsRegistryKey@@YAKPEBGKPEAPEAUHKEY__@@@Z; OpenEapTlsRegistryKey(ushort const *,ulong,HKEY__ * *)
0x180005d43  test    eax, eax
0x180005d45  jnz     loc_180005EC3
0x180005d4b  mov     rcx, [rbp+hKey]; hKey
0x180005d4f  lea     rax, [rbp+picce]
0x180005d53  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180005d58  lea     r9, [rbp+Type]; lpType
0x180005d5c  lea     rax, [rbp+Data]
0x180005d60  mov     [rbp+Type], r14d
0x180005d64  xor     r8d, r8d; lpReserved
0x180005d67  mov     [rsp+40h+lpData], rax; lpData
0x180005d6c  lea     rdx, aOverrideeapcer; "OverrideEAPCertificateSelection"
0x180005d73  mov     [rbp+Data], r14d
0x180005d77  mov     [rbp+picce.dwSize], 4
0x180005d7e  call    cs:__imp_RegQueryValueExW
0x180005d84  test    eax, eax
0x180005d86  jnz     short loc_180005DB7
0x180005d88  cmp     [rbp+Type], 4
0x180005d8c  jnz     short loc_180005DB7
0x180005d8e  cmp     [rbp+picce.dwSize], 4
0x180005d92  jnz     short loc_180005DB7
0x180005d94  mov     eax, [rbp+Data]
0x180005d97  mov     ecx, eax
0x180005d99  mov     edx, eax
0x180005d9b  shr     ecx, 0Ch
0x180005d9e  mov     r8d, eax
0x180005da1  shr     edx, 8
0x180005da4  shr     r8d, 4
0x180005da8  and     ecx, 1
0x180005dab  and     edx, 1
0x180005dae  and     r8d, 1
0x180005db2  and     eax, 1
0x180005db5  jmp     short loc_180005DC3
0x180005db7  mov     ecx, r14d
0x180005dba  mov     edx, r14d
0x180005dbd  mov     r8d, r14d
0x180005dc0  mov     eax, r14d
0x180005dc3  mov     cs:?g_UseDefaultSCardCert@@3HA, eax; int g_UseDefaultSCardCert
0x180005dc9  mov     cs:?g_OverrideSCardFilter@@3HA, r8d; int g_OverrideSCardFilter
0x180005dd0  mov     cs:?g_OverrideRegCertFilter@@3HA, edx; int g_OverrideRegCertFilter
0x180005dd6  mov     cs:?g_IgnorePasswdCerts@@3HA, ecx; int g_IgnorePasswdCerts
0x180005ddc  test    eax, eax
0x180005dde  jz      short loc_180005E07
0x180005de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005de7  cmp     rcx, rdi
0x180005dea  jz      short loc_180005E0E
0x180005dec  mov     rcx, [rcx+10h]
0x180005df0  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005df7  mov     edx, 15h
0x180005dfc  call    WPP_SF_
0x180005e01  mov     eax, cs:?g_UseDefaultSCardCert@@3HA; int g_UseDefaultSCardCert
0x180005e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e0e  cmp     cs:?g_OverrideSCardFilter@@3HA, ebx; int g_OverrideSCardFilter
0x180005e14  jz      short loc_180005E45
0x180005e16  test    eax, eax
0x180005e18  jz      short loc_180005E45
0x180005e1a  cmp     rcx, rdi
0x180005e1d  jz      short loc_180005E3B
0x180005e1f  mov     rcx, [rcx+10h]
0x180005e23  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005e2a  mov     edx, 16h
0x180005e2f  call    WPP_SF_
0x180005e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e3b  mov     cs:?g_UseDefaultSCardCert@@3HA, 1; int g_UseDefaultSCardCert
0x180005e45  cmp     cs:?g_OverrideRegCertFilter@@3HA, ebx; int g_OverrideRegCertFilter
0x180005e4b  jz      short loc_180005E6E
0x180005e4d  cmp     rcx, rdi
0x180005e50  jz      short loc_180005E6E
0x180005e52  mov     rcx, [rcx+10h]
0x180005e56  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005e5d  mov     edx, 17h
0x180005e62  call    WPP_SF_
0x180005e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e6e  cmp     cs:?g_OverrideSCardFilter@@3HA, ebx; int g_OverrideSCardFilter
0x180005e74  jz      short loc_180005E97
0x180005e76  cmp     rcx, rdi
0x180005e79  jz      short loc_180005E97
0x180005e7b  mov     rcx, [rcx+10h]
0x180005e7f  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005e86  mov     edx, 18h
0x180005e8b  call    WPP_SF_
0x180005e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e97  cmp     cs:?g_IgnorePasswdCerts@@3HA, ebx; int g_IgnorePasswdCerts
0x180005e9d  jz      short loc_180005EB9
0x180005e9f  cmp     rcx, rdi
0x180005ea2  jz      short loc_180005EB9
0x180005ea4  mov     rcx, [rcx+10h]
0x180005ea8  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005eaf  mov     edx, 19h
0x180005eb4  call    WPP_SF_
0x180005eb9  mov     rcx, [rbp+hKey]; hKey
0x180005ebd  call    cs:__imp_RegCloseKey
0x180005ec3  call    EapProvPlugin_Initialize
0x180005ec8  mov     eax, cs:dword_1800A5FF0
0x180005ece  cmp     eax, 0FFFFFFFFh
0x180005ed1  jz      loc_1800060CF
0x180005ed7  inc     eax
0x180005ed9  mov     cs:dword_1800A5FF0, eax
0x180005edf  jmp     loc_1800060CF
0x180005ee4  test    eax, eax
0x180005ee6  jz      loc_1800060CF
0x180005eec  add     eax, 0FFFFFFFFh
0x180005eef  mov     cs:dword_1800A5FF0, eax
0x180005ef5  jnz     loc_1800060CF
0x180005efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f02  lea     rdi, WPP_GLOBAL_Control
0x180005f09  cmp     rcx, rdi
0x180005f0c  jz      short loc_180005F23
0x180005f0e  mov     rcx, [rcx+10h]
0x180005f12  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005f19  mov     edx, 1Ah
0x180005f1e  call    WPP_SF_
0x180005f23  test    esi, esi
0x180005f25  jnz     loc_180005FB9
0x180005f2b  cmp     cs:?g_fChangeNotificationSetup@@3HA, ebx; int g_fChangeNotificationSetup
0x180005f31  jz      loc_180005FB9
0x180005f37  mov     rcx, cs:?g_hWaitonStoreChangeEvt@@3PEAXEA; WaitHandle
0x180005f3e  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180005f45  call    cs:__imp_UnregisterWaitEx
0x180005f4b  test    eax, eax
0x180005f4d  jnz     short loc_180005F7B
0x180005f4f  call    cs:__imp_GetLastError
0x180005f55  mov     ebx, eax
0x180005f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f5e  cmp     rcx, rdi
0x180005f61  jz      short loc_180005F7B
0x180005f63  mov     rcx, [rcx+10h]
0x180005f67  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180005f6e  mov     edx, 1Bh
0x180005f73  mov     r9d, eax
0x180005f76  call    WPP_SF_d
0x180005f7b  mov     rcx, cs:?g_hStoreChangeNotificationEvt@@3PEAXEA; hObject
0x180005f82  test    rcx, rcx
0x180005f85  jz      short loc_180005F94
0x180005f87  call    cs:__imp_CloseHandle
0x180005f8d  mov     cs:?g_hStoreChangeNotificationEvt@@3PEAXEA, r14; void * g_hStoreChangeNotificationEvt
0x180005f94  mov     rcx, cs:?g_hLocalMachineStore@@3PEAXEA; hCertStore
0x180005f9b  test    rcx, rcx
0x180005f9e  jz      short loc_180005FB2
0x180005fa0  mov     edx, 2; dwFlags
0x180005fa5  call    cs:__imp_CertCloseStore
0x180005fab  mov     cs:?g_hLocalMachineStore@@3PEAXEA, r14; void * g_hLocalMachineStore
0x180005fb2  mov     cs:?g_fChangeNotificationSetup@@3HA, r14d; int g_fChangeNotificationSetup
0x180005fb9  mov     rsi, cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x180005fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fc7  cmp     rcx, rdi
0x180005fca  jz      short loc_180005FE1
0x180005fcc  mov     rcx, [rcx+10h]
0x180005fd0  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x180005fd7  mov     edx, 0Ch
0x180005fdc  call    WPP_SF_
0x180005fe1  test    rsi, rsi
  ... truncated ...
```
