# DllRegisterServer

- ea: `0x1800173a0`
- end: `0x180017a4c`
- name: `DllRegisterServer`
- size: `1708`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800172e0`
- `0x180017358`
- `0x1800173a0`
- `0x18002bc00`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180017502`
- `ADVAPI32!RegCloseKey` at `0x180017517`
- `ADVAPI32!RegCloseKey` at `0x1800176a1`
- `ADVAPI32!RegCloseKey` at `0x18001779a`
- `ADVAPI32!RegCloseKey` at `0x1800178ed`
- `ADVAPI32!RegCloseKey` at `0x1800178fd`
- `ADVAPI32!RegCloseKey` at `0x180017a29`
- `ADVAPI32!RegCloseKey` at `0x180017a39`
- `ADVAPI32!RegCloseKey` at `0x180017502`
- `ADVAPI32!RegCloseKey` at `0x180017517`
- `ADVAPI32!RegCloseKey` at `0x1800176a1`
- `ADVAPI32!RegCloseKey` at `0x18001779a`
- `ADVAPI32!RegCloseKey` at `0x1800178ed`
- `ADVAPI32!RegCloseKey` at `0x1800178fd`
- `ADVAPI32!RegCloseKey` at `0x180017a29`
- `ADVAPI32!RegCloseKey` at `0x180017a39`
- `ADVAPI32!RegSetValueExW` at `0x180017588`
- `ADVAPI32!RegSetValueExW` at `0x1800175dc`
- `ADVAPI32!RegSetValueExW` at `0x18001762a`
- `ADVAPI32!RegSetValueExW` at `0x18001765e`
- `ADVAPI32!RegSetValueExW` at `0x18001768e`
- `ADVAPI32!RegSetValueExW` at `0x180017740`
- `ADVAPI32!RegSetValueExW` at `0x180017787`
- `ADVAPI32!RegSetValueExW` at `0x180017839`
- `ADVAPI32!RegSetValueExW` at `0x1800178a6`
- `ADVAPI32!RegSetValueExW` at `0x1800178da`
- `ADVAPI32!RegSetValueExW` at `0x18001799c`
- `ADVAPI32!RegSetValueExW` at `0x180017a0d`
- `ADVAPI32!RegSetValueExW` at `0x180017588`
- `ADVAPI32!RegSetValueExW` at `0x1800175dc`
- `ADVAPI32!RegSetValueExW` at `0x18001762a`
- `ADVAPI32!RegSetValueExW` at `0x18001765e`
- `ADVAPI32!RegSetValueExW` at `0x18001768e`
- `ADVAPI32!RegSetValueExW` at `0x180017740`
- `ADVAPI32!RegSetValueExW` at `0x180017787`
- `ADVAPI32!RegSetValueExW` at `0x180017839`
- `ADVAPI32!RegSetValueExW` at `0x1800178a6`
- `ADVAPI32!RegSetValueExW` at `0x1800178da`
- `ADVAPI32!RegSetValueExW` at `0x18001799c`
- `ADVAPI32!RegSetValueExW` at `0x180017a0d`
- `ADVAPI32!RegCreateKeyExW` at `0x18001749f`
- `ADVAPI32!RegCreateKeyExW` at `0x180017710`
- `ADVAPI32!RegCreateKeyExW` at `0x180017809`
- `ADVAPI32!RegCreateKeyExW` at `0x180017876`
- `ADVAPI32!RegCreateKeyExW` at `0x18001796c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800179d5`
- `ADVAPI32!RegCreateKeyExW` at `0x18001749f`
- `ADVAPI32!RegCreateKeyExW` at `0x180017710`
- `ADVAPI32!RegCreateKeyExW` at `0x180017809`
- `ADVAPI32!RegCreateKeyExW` at `0x180017876`
- `ADVAPI32!RegCreateKeyExW` at `0x18001796c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800179d5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017536`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180017536`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017441`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800176b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800177b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017914`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017441`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800176b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800177b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017914`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017420`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017420`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017453`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017465`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800176ca`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800176dc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800177c3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800177d5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017926`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017938`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017453`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017465`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800176ca`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800176dc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800177c3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800177d5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017926`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017938`
- `iisutil!PuDbgPrintError` at `0x1800174f2`
- `iisutil!PuDbgPrintError` at `0x1800174f2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001752c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001752c`

## string_xrefs

- `0x18001760b`: `AccessPermission`
- `0x18001764c`: `LocalService`
- `0x180017889`: `inetsrv\ftpctrlps.dll`
- `0x1800178c8`: `ThreadingModel`
- `0x1800179b5`: `ProxyStubClsid32`
- `0x1800174ce`: `DllRegisterServer failed\n`
- `0x1800174da`: `DllRegisterServer`
- `0x1800174eb`: `inetsrv\iis\iisrearc\ftp\server\core\com_registration.cxx`
- `0x1800176a7`: `CLSID`
- `0x1800177a0`: `CLSID`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT GlobalGUIDStrings; // ebx
  LSTATUS v1; // eax
  bool v2; // cc
  HKEY v3; // rcx
  bool v5; // cc
  __int64 v6; // rdi
  __int64 v7; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v12[32]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-78h]
  _QWORD v14[4]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE *lpData; // [rsp+C0h] [rbp-40h]
  int v16; // [rsp+C8h] [rbp-38h]
  __int16 v17; // [rsp+CCh] [rbp-34h]
  unsigned __int16 v18[256]; // [rsp+D0h] [rbp-30h] BYREF

  v16 = 32;
  hKey = 0;
  phkResult = 0;
  v14[0] = 0;
  lpData = (BYTE *)v14;
  v17 = 256;
  cbData = 0;
  *(_DWORD *)Data = 6;
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v12, v18, 0x100u);
  GlobalGUIDStrings = AllocateGlobalGUIDStrings();
  if ( GlobalGUIDStrings < 0 )
    goto LABEL_6;
  STRU::Copy((STRU *)v12, L"AppID");
  STRU::Append((STRU *)v12, L"\\");
  STRU::Append((STRU *)v12, (const unsigned __int16 *)::lpData);
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  GlobalGUIDStrings = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_3;
  v1 = RegSetValueExW(hKey, &WideCharStr, 0, 1u, L"IIS Ftp Control", 0x20u);
  GlobalGUIDStrings = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_3;
  GlobalGUIDStrings = CreateSecurityDescriptorForCom((struct BUFFER *)v14, &cbData, 9u);
  if ( GlobalGUIDStrings < 0 )
    goto LABEL_6;
  v1 = RegSetValueExW(hKey, L"LaunchPermission", 0, 3u, lpData, cbData);
  GlobalGUIDStrings = v1;
  v2 = v1 <= 0;
  if ( v1 )
  {
LABEL_3:
    if ( v2 )
      goto LABEL_5;
    goto LABEL_4;
  }
  GlobalGUIDStrings = CreateSecurityDescriptorForCom((struct BUFFER *)v14, &cbData, 3u);
  if ( GlobalGUIDStrings < 0 )
    goto LABEL_6;
  v1 = RegSetValueExW(hKey, L"AccessPermission", 0, 3u, lpData, cbData);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(hKey, L"LocalService", 0, 1u, (const BYTE *)L"FTPSVC", 0xEu);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(hKey, L"AuthenticationLevel", 0, 4u, Data, 4u);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  RegCloseKey(hKey);
  hKey = 0;
  STRU::Copy((STRU *)v12, L"CLSID");
  STRU::Append((STRU *)v12, L"\\");
  STRU::Append((STRU *)v12, (const unsigned __int16 *)::lpData);
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(hKey, &WideCharStr, 0, 1u, L"IIS Ftp Control", 0x20u);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&::lpData[2 * v7] );
  v1 = RegSetValueExW(hKey, L"AppID", 0, 1u, ::lpData, 2 * v7 + 2);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  RegCloseKey(hKey);
  hKey = 0;
  STRU::Copy((STRU *)v12, L"CLSID");
  STRU::Append((STRU *)v12, L"\\");
  STRU::Append((STRU *)v12, (const unsigned __int16 *)qword_1800614E8);
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(hKey, &WideCharStr, 0, 1u, L"IIS Ftp Control Interface ProxyStub", 0x48u);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegCreateKeyExW(hKey, L"InprocServer32", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(phkResult, &WideCharStr, 0, 1u, L"inetsrv\\ftpctrlps.dll", 0x2Cu);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  hKey = 0;
  STRU::Copy((STRU *)v12, L"Interface");
  STRU::Append((STRU *)v12, L"\\");
  STRU::Append((STRU *)v12, (const unsigned __int16 *)qword_1800614E8);
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegSetValueExW(hKey, &WideCharStr, 0, 1u, L"IFtpControl", 0x18u);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  v1 = RegCreateKeyExW(hKey, L"ProxyStubClsid32", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_36;
  do
    ++v6;
  while ( *(_WORD *)&qword_1800614E8[2 * v6] );
  v1 = RegSetValueExW(phkResult, &WideCharStr, 0, 1u, qword_1800614E8, 2 * v6 + 2);
  v5 = v1 <= 0;
  if ( v1 )
  {
LABEL_36:
    if ( v5 )
    {
      GlobalGUIDStrings = v1;
LABEL_5:
      if ( GlobalGUIDStrings >= 0 )
      {
LABEL_8:
        v3 = hKey;
        goto LABEL_9;
      }
LABEL_6:
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\com_registration.cxx",
          559,
          "DllRegisterServer",
          GlobalGUIDStrings,
          "DllRegisterServer failed\n");
      goto LABEL_8;
    }
LABEL_4:
    GlobalGUIDStrings = (unsigned __int16)v1 | 0x80070000;
    goto LABEL_5;
  }
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  v3 = 0;
  hKey = 0;
LABEL_9:
  if ( v3 )
  {
    RegCloseKey(v3);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  FreeGlobalGUIDStrings();
  STRU::~STRU(v12);
  BUFFER::~BUFFER((BUFFER *)v14);
  return GlobalGUIDStrings;
}

```

## disassembly

```asm
0x1800173a0  push    rbp
0x1800173a2  push    rbx
0x1800173a3  push    rsi
0x1800173a4  push    rdi
0x1800173a5  push    r13
0x1800173a7  push    r14
0x1800173a9  push    r15
0x1800173ab  lea     rbp, [rsp-1E0h]
0x1800173b3  sub     rsp, 2E0h
0x1800173ba  mov     rax, cs:__security_cookie
0x1800173c1  xor     rax, rsp
0x1800173c4  mov     [rbp+210h+var_40], rax
0x1800173cb  xor     esi, esi
0x1800173cd  mov     [rbp+210h+var_248], 20h ; ' '
0x1800173d4  lea     rax, [rbp+210h+var_270]
0x1800173d8  mov     [rsp+310h+hKey], rsi
0x1800173dd  xor     edx, edx; Val
0x1800173df  mov     [rsp+310h+var_2B8], rsi
0x1800173e4  mov     r8d, 200h; Size
0x1800173ea  mov     [rbp+210h+var_270], rsi
0x1800173ee  lea     rcx, [rbp+210h+var_240]; void *
0x1800173f2  mov     [rbp+210h+lpData], rax
0x1800173f6  lea     r14d, [rsi+1]
0x1800173fa  mov     [rbp+210h+var_244], 100h
0x180017400  mov     [rsp+310h+cbData], esi
0x180017404  mov     dword ptr [rsp+310h+Data], 6
0x18001740c  call    memset_0
0x180017411  mov     r8d, 100h
0x180017417  lea     rdx, [rbp+210h+var_240]
0x18001741b  lea     rcx, [rsp+310h+var_2A8]
0x180017420  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180017426  call    AllocateGlobalGUIDStrings
0x18001742b  mov     ebx, eax
0x18001742d  test    eax, eax
0x18001742f  js      loc_1800174BE
0x180017435  lea     rdx, aAppid_0; "AppID"
0x18001743c  lea     rcx, [rsp+310h+var_2A8]
0x180017441  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017447  lea     rdx, asc_18004BD10; "\\"
0x18001744e  lea     rcx, [rsp+310h+var_2A8]
0x180017453  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017459  mov     rdx, cs:lpData
0x180017460  lea     rcx, [rsp+310h+var_2A8]
0x180017465  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001746b  mov     rdx, [rbp+210h+lpSubKey]; lpSubKey
0x18001746f  lea     rax, [rsp+310h+hKey]
0x180017474  mov     [rsp+310h+lpdwDisposition], rsi; lpdwDisposition
0x180017479  mov     r13d, 0F003Fh
0x18001747f  mov     [rsp+310h+phkResult], rax; phkResult
0x180017484  xor     r9d, r9d; lpClass
0x180017487  mov     [rsp+310h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001748c  xor     r8d, r8d; Reserved
0x18001748f  mov     [rsp+310h+samDesired], r13d; samDesired
0x180017494  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001749b  mov     [rsp+310h+dwOptions], esi; dwOptions
0x18001749f  call    cs:__imp_RegCreateKeyExW
0x1800174a5  mov     ebx, eax
0x1800174a7  test    eax, eax
0x1800174a9  jz      loc_18001755F
0x1800174af  jle     short loc_1800174BA
0x1800174b1  movzx   ebx, ax
0x1800174b4  or      ebx, 80070000h
0x1800174ba  test    ebx, ebx
0x1800174bc  jns     short loc_1800174F8
0x1800174be  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800174c5  jz      short loc_1800174F8
0x1800174c7  mov     rcx, cs:g_pDebug
0x1800174ce  lea     rax, aDllregisterser_1; "DllRegisterServer failed\n"
0x1800174d5  mov     qword ptr [rsp+310h+samDesired], rax
0x1800174da  lea     r9, aDllregisterser_0; "DllRegisterServer"
0x1800174e1  mov     r8d, 22Fh
0x1800174e7  mov     [rsp+310h+dwOptions], ebx
0x1800174eb  lea     rdx, aInetsrvIisIisr_14; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800174f2  call    cs:__imp_PuDbgPrintError
0x1800174f8  mov     rcx, [rsp+310h+hKey]; hKey
0x1800174fd  test    rcx, rcx
0x180017500  jz      short loc_18001750D
0x180017502  call    cs:__imp_RegCloseKey
0x180017508  mov     [rsp+310h+hKey], rsi
0x18001750d  mov     rcx, [rsp+310h+var_2B8]; hKey
0x180017512  test    rcx, rcx
0x180017515  jz      short loc_180017522
0x180017517  call    cs:__imp_RegCloseKey
0x18001751d  mov     [rsp+310h+var_2B8], rsi
0x180017522  call    FreeGlobalGUIDStrings
0x180017527  lea     rcx, [rsp+310h+var_2A8]
0x18001752c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017532  lea     rcx, [rbp+210h+var_270]
0x180017536  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001753c  mov     eax, ebx
0x18001753e  mov     rcx, [rbp+210h+var_40]
0x180017545  xor     rcx, rsp; StackCookie
0x180017548  call    __security_check_cookie
0x18001754d  add     rsp, 2E0h
0x180017554  pop     r15
0x180017556  pop     r14
0x180017558  pop     r13
0x18001755a  pop     rdi
0x18001755b  pop     rsi
0x18001755c  pop     rbx
0x18001755d  pop     rbp
0x18001755e  retn
0x18001755f  mov     rcx, [rsp+310h+hKey]; hKey
0x180017564  lea     rax, Data; "IIS Ftp Control"
0x18001756b  lea     r15, WideCharStr
0x180017572  mov     [rsp+310h+samDesired], 20h ; ' '; cbData
0x18001757a  mov     rdx, r15; lpValueName
0x18001757d  mov     qword ptr [rsp+310h+dwOptions], rax; int
0x180017582  mov     r9d, r14d; dwType
0x180017585  xor     r8d, r8d; Reserved
0x180017588  call    cs:__imp_RegSetValueExW
0x18001758e  mov     ebx, eax
0x180017590  test    eax, eax
0x180017592  jnz     loc_1800174AF
0x180017598  lea     r8d, [rax+9]; unsigned int
0x18001759c  lea     rdx, [rsp+310h+cbData]; unsigned int *
0x1800175a1  lea     rcx, [rbp+210h+var_270]; struct BUFFER *
0x1800175a5  call    ?CreateSecurityDescriptorForCom@@YAJPEAVBUFFER@@PEAKKHH@Z; CreateSecurityDescriptorForCom(BUFFER *,ulong *,ulong,int,int)
0x1800175aa  mov     ebx, eax
0x1800175ac  test    eax, eax
0x1800175ae  js      loc_1800174BE
0x1800175b4  mov     rcx, [rbp+210h+lpData]
0x1800175b8  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x1800175bf  mov     eax, [rsp+310h+cbData]
0x1800175c3  mov     edi, 3
0x1800175c8  mov     [rsp+310h+samDesired], eax; cbData
0x1800175cc  mov     r9d, edi; dwType
0x1800175cf  mov     qword ptr [rsp+310h+dwOptions], rcx; int
0x1800175d4  xor     r8d, r8d; Reserved
0x1800175d7  mov     rcx, [rsp+310h+hKey]; hKey
0x1800175dc  call    cs:__imp_RegSetValueExW
0x1800175e2  mov     ebx, eax
0x1800175e4  test    eax, eax
0x1800175e6  jnz     loc_1800174AF
0x1800175ec  mov     r8d, edi; unsigned int
0x1800175ef  lea     rdx, [rsp+310h+cbData]; unsigned int *
0x1800175f4  lea     rcx, [rbp+210h+var_270]; struct BUFFER *
0x1800175f8  call    ?CreateSecurityDescriptorForCom@@YAJPEAVBUFFER@@PEAKKHH@Z; CreateSecurityDescriptorForCom(BUFFER *,ulong *,ulong,int,int)
0x1800175fd  mov     ebx, eax
0x1800175ff  test    eax, eax
0x180017601  js      loc_1800174BE
0x180017607  mov     rcx, [rbp+210h+lpData]
0x18001760b  lea     rdx, aAccesspermissi; "AccessPermission"
0x180017612  mov     eax, [rsp+310h+cbData]
0x180017616  mov     r9d, edi; dwType
0x180017619  mov     [rsp+310h+samDesired], eax; cbData
0x18001761d  xor     r8d, r8d; Reserved
0x180017620  mov     qword ptr [rsp+310h+dwOptions], rcx; lpData
0x180017625  mov     rcx, [rsp+310h+hKey]; hKey
0x18001762a  call    cs:__imp_RegSetValueExW
0x180017630  test    eax, eax
0x180017632  jnz     loc_180017A17
0x180017638  mov     rcx, [rsp+310h+hKey]; hKey
0x18001763d  lea     rax, aFtpsvc; "FTPSVC"
0x180017644  mov     [rsp+310h+samDesired], 0Eh; cbData
0x18001764c  lea     rdx, aLocalservice; "LocalService"
0x180017653  mov     r9d, r14d; dwType
0x180017656  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x18001765b  xor     r8d, r8d; Reserved
0x18001765e  call    cs:__imp_RegSetValueExW
0x180017664  test    eax, eax
0x180017666  jnz     loc_180017A17
0x18001766c  mov     rcx, [rsp+310h+hKey]; hKey
0x180017671  lea     r9d, [rdi+1]; dwType
0x180017675  lea     rax, [rsp+310h+Data]
0x18001767a  mov     [rsp+310h+samDesired], r9d; cbData
0x18001767f  xor     r8d, r8d; Reserved
0x180017682  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x180017687  lea     rdx, aAuthentication_0; "AuthenticationLevel"
0x18001768e  call    cs:__imp_RegSetValueExW
0x180017694  test    eax, eax
0x180017696  jnz     loc_180017A17
0x18001769c  mov     rcx, [rsp+310h+hKey]; hKey
0x1800176a1  call    cs:__imp_RegCloseKey
0x1800176a7  lea     rdx, aClsid_0; "CLSID"
0x1800176ae  mov     [rsp+310h+hKey], rsi
0x1800176b3  lea     rcx, [rsp+310h+var_2A8]
0x1800176b8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800176be  lea     rdx, asc_18004BD10; "\\"
0x1800176c5  lea     rcx, [rsp+310h+var_2A8]
0x1800176ca  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800176d0  mov     rdx, cs:lpData
0x1800176d7  lea     rcx, [rsp+310h+var_2A8]
0x1800176dc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800176e2  mov     rdx, [rbp+210h+lpSubKey]; lpSubKey
0x1800176e6  lea     rax, [rsp+310h+hKey]
0x1800176eb  mov     [rsp+310h+lpdwDisposition], rsi; lpdwDisposition
0x1800176f0  xor     r9d, r9d; lpClass
0x1800176f3  mov     [rsp+310h+phkResult], rax; phkResult
0x1800176f8  xor     r8d, r8d; Reserved
0x1800176fb  mov     [rsp+310h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180017700  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180017707  mov     [rsp+310h+samDesired], r13d; samDesired
0x18001770c  mov     [rsp+310h+dwOptions], esi; dwOptions
0x180017710  call    cs:__imp_RegCreateKeyExW
0x180017716  test    eax, eax
0x180017718  jnz     loc_180017A17
0x18001771e  mov     rcx, [rsp+310h+hKey]; hKey
0x180017723  lea     rax, Data; "IIS Ftp Control"
0x18001772a  mov     [rsp+310h+samDesired], 20h ; ' '; cbData
0x180017732  mov     r9d, r14d; dwType
0x180017735  xor     r8d, r8d; Reserved
0x180017738  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x18001773d  mov     rdx, r15; lpValueName
0x180017740  call    cs:__imp_RegSetValueExW
0x180017746  test    eax, eax
0x180017748  jnz     loc_180017A17
0x18001774e  mov     rcx, cs:lpData
0x180017755  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017759  mov     rax, rdi
0x18001775c  inc     rax
0x18001775f  cmp     [rcx+rax*2], si
0x180017763  jnz     short loc_18001775C
0x180017765  lea     eax, ds:2[rax*2]
0x18001776c  mov     r9d, r14d; dwType
0x18001776f  mov     [rsp+310h+samDesired], eax; cbData
0x180017773  lea     rdx, aAppid; "AppID"
0x18001777a  mov     qword ptr [rsp+310h+dwOptions], rcx; lpData
0x18001777f  xor     r8d, r8d; Reserved
0x180017782  mov     rcx, [rsp+310h+hKey]; hKey
0x180017787  call    cs:__imp_RegSetValueExW
0x18001778d  test    eax, eax
0x18001778f  jnz     loc_180017A17
0x180017795  mov     rcx, [rsp+310h+hKey]; hKey
0x18001779a  call    cs:__imp_RegCloseKey
0x1800177a0  lea     rdx, aClsid_0; "CLSID"
0x1800177a7  mov     [rsp+310h+hKey], rsi
0x1800177ac  lea     rcx, [rsp+310h+var_2A8]
0x1800177b1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800177b7  lea     rdx, asc_18004BD10; "\\"
0x1800177be  lea     rcx, [rsp+310h+var_2A8]
0x1800177c3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800177c9  mov     rdx, cs:qword_1800614E8
0x1800177d0  lea     rcx, [rsp+310h+var_2A8]
0x1800177d5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800177db  mov     rdx, [rbp+210h+lpSubKey]; lpSubKey
0x1800177df  lea     rax, [rsp+310h+hKey]
0x1800177e4  mov     [rsp+310h+lpdwDisposition], rsi; lpdwDisposition
0x1800177e9  xor     r9d, r9d; lpClass
0x1800177ec  mov     [rsp+310h+phkResult], rax; phkResult
0x1800177f1  xor     r8d, r8d; Reserved
0x1800177f4  mov     [rsp+310h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800177f9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180017800  mov     [rsp+310h+samDesired], r13d; samDesired
0x180017805  mov     [rsp+310h+dwOptions], esi; dwOptions
0x180017809  call    cs:__imp_RegCreateKeyExW
0x18001780f  test    eax, eax
0x180017811  jnz     loc_180017A17
0x180017817  mov     rcx, [rsp+310h+hKey]; hKey
0x18001781c  lea     rax, aIisFtpControlI; "IIS Ftp Control Interface ProxyStub"
0x180017823  mov     [rsp+310h+samDesired], 48h ; 'H'; cbData
0x18001782b  mov     r9d, r14d; dwType
0x18001782e  xor     r8d, r8d; Reserved
0x180017831  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x180017836  mov     rdx, r15; lpValueName
0x180017839  call    cs:__imp_RegSetValueExW
0x18001783f  test    eax, eax
0x180017841  jnz     loc_180017A17
0x180017847  mov     rcx, [rsp+310h+hKey]; hKey
0x18001784c  lea     rax, [rsp+310h+var_2B8]
0x180017851  mov     [rsp+310h+lpdwDisposition], rsi; lpdwDisposition
0x180017856  lea     rdx, aInprocserver32; "InprocServer32"
0x18001785d  mov     [rsp+310h+phkResult], rax; phkResult
0x180017862  xor     r9d, r9d; lpClass
0x180017865  mov     [rsp+310h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001786a  xor     r8d, r8d; Reserved
0x18001786d  mov     [rsp+310h+samDesired], r13d; samDesired
0x180017872  mov     [rsp+310h+dwOptions], esi; dwOptions
0x180017876  call    cs:__imp_RegCreateKeyExW
0x18001787c  test    eax, eax
0x18001787e  jnz     loc_180017A17
0x180017884  mov     rcx, [rsp+310h+var_2B8]; hKey
0x180017889  lea     rax, aInetsrvFtpctrl; "inetsrv\\ftpctrlps.dll"
0x180017890  mov     [rsp+310h+samDesired], 2Ch ; ','; cbData
0x180017898  mov     r9d, r14d; dwType
0x18001789b  xor     r8d, r8d; Reserved
0x18001789e  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x1800178a3  mov     rdx, r15; lpValueName
0x1800178a6  call    cs:__imp_RegSetValueExW
0x1800178ac  test    eax, eax
0x1800178ae  jnz     loc_180017A17
0x1800178b4  mov     rcx, [rsp+310h+var_2B8]; hKey
0x1800178b9  lea     rax, aBoth; "Both"
0x1800178c0  mov     [rsp+310h+samDesired], 0Ah; cbData
0x1800178c8  lea     rdx, aThreadingmodel; "ThreadingModel"
0x1800178cf  mov     r9d, r14d; dwType
0x1800178d2  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x1800178d7  xor     r8d, r8d; Reserved
0x1800178da  call    cs:__imp_RegSetValueExW
0x1800178e0  test    eax, eax
0x1800178e2  jnz     loc_180017A17
0x1800178e8  mov     rcx, [rsp+310h+var_2B8]; hKey
0x1800178ed  call    cs:__imp_RegCloseKey
0x1800178f3  mov     rcx, [rsp+310h+hKey]; hKey
0x1800178f8  mov     [rsp+310h+var_2B8], rsi
0x1800178fd  call    cs:__imp_RegCloseKey
0x180017903  lea     rdx, aInterface; "Interface"
0x18001790a  mov     [rsp+310h+hKey], rsi
0x18001790f  lea     rcx, [rsp+310h+var_2A8]
0x180017914  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
  ... truncated ...
```
