# GetLanListFromRegistry

- ea: `0x140003a48`
- end: `0x140004294`
- name: `GetLanListFromRegistry`
- size: `2124`
- prototype: `void()`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1400088c0`

## callees

- `0x140002bd8`
- `0x140002c40`
- `0x140002fbc`
- `0x140003a48`
- `0x140004374`
- `0x140004868`
- `0x140004e64`
- `0x140004f0c`
- `0x14000fa94`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140003b69`
- `ADVAPI32!RegOpenKeyExW` at `0x140003c1a`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d5d`
- `ADVAPI32!RegOpenKeyExW` at `0x140003b69`
- `ADVAPI32!RegOpenKeyExW` at `0x140003c1a`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d5d`
- `ADVAPI32!RegCloseKey` at `0x140003be8`
- `ADVAPI32!RegCloseKey` at `0x140003e62`
- `ADVAPI32!RegCloseKey` at `0x140003eb5`
- `ADVAPI32!RegCloseKey` at `0x140003f30`
- `ADVAPI32!RegCloseKey` at `0x140003f68`
- `ADVAPI32!RegCloseKey` at `0x140003be8`
- `ADVAPI32!RegCloseKey` at `0x140003e62`
- `ADVAPI32!RegCloseKey` at `0x140003eb5`
- `ADVAPI32!RegCloseKey` at `0x140003f30`
- `ADVAPI32!RegCloseKey` at `0x140003f68`
- `ADVAPI32!RegQueryValueExW` at `0x140003d98`
- `ADVAPI32!RegQueryValueExW` at `0x140003d98`
- `ADVAPI32!RegEnumKeyExW` at `0x140003ea2`
- `ADVAPI32!RegEnumKeyExW` at `0x140003ea2`
- `KERNEL32!GlobalAlloc` at `0x140003d10`
- `KERNEL32!GlobalAlloc` at `0x140003ee3`
- `KERNEL32!GlobalAlloc` at `0x140003d10`
- `KERNEL32!GlobalAlloc` at `0x140003ee3`
- `KERNEL32!EnterCriticalSection` at `0x140003ae0`
- `KERNEL32!EnterCriticalSection` at `0x140003b87`
- `KERNEL32!EnterCriticalSection` at `0x140003ae0`
- `KERNEL32!EnterCriticalSection` at `0x140003b87`
- `KERNEL32!GlobalFree` at `0x140003b9a`
- `KERNEL32!GlobalFree` at `0x140003bbc`
- `KERNEL32!GlobalFree` at `0x140003f3e`
- `KERNEL32!GlobalFree` at `0x140003f50`
- `KERNEL32!GlobalFree` at `0x140003b9a`
- `KERNEL32!GlobalFree` at `0x140003bbc`
- `KERNEL32!GlobalFree` at `0x140003f3e`
- `KERNEL32!GlobalFree` at `0x140003f50`
- `KERNEL32!LeaveCriticalSection` at `0x140003bb3`
- `KERNEL32!LeaveCriticalSection` at `0x140003f75`
- `KERNEL32!LeaveCriticalSection` at `0x14000423f`
- `KERNEL32!LeaveCriticalSection` at `0x140003bb3`
- `KERNEL32!LeaveCriticalSection` at `0x140003f75`
- `KERNEL32!LeaveCriticalSection` at `0x14000423f`
- `KERNEL32!GetLastError` at `0x140003c29`
- `KERNEL32!GetLastError` at `0x140004004`
- `KERNEL32!GetLastError` at `0x140004036`
- `KERNEL32!GetLastError` at `0x140003c29`
- `KERNEL32!GetLastError` at `0x140004004`
- `KERNEL32!GetLastError` at `0x140004036`
- `KERNEL32!WaitForMultipleObjects` at `0x1400041e1`
- `KERNEL32!WaitForMultipleObjects` at `0x1400041e1`
- `KERNEL32!ReleaseMutex` at `0x140003bdb`
- `KERNEL32!ReleaseMutex` at `0x140003bdb`
- `KERNEL32!WaitForSingleObject` at `0x140003b7d`
- `KERNEL32!WaitForSingleObject` at `0x140003b7d`
- `msvcrt!_snwprintf_s` at `0x140003b42`
- `msvcrt!_snwprintf_s` at `0x140003b42`
- `msvcrt!_wcsicmp` at `0x140003cd5`
- `msvcrt!_wcsicmp` at `0x140003cd5`
- `msvcrt!_beginthreadex` at `0x14000414d`
- `msvcrt!_beginthreadex` at `0x14000414d`
- `msvcrt!wcscpy_s` at `0x140003d31`
- `msvcrt!wcscpy_s` at `0x140003d31`

## string_xrefs

- `0x140003d91`: `Configure Mode`
- `0x14000402d`: `Configure Mode`
- `0x140003aed`: `SYSTEM\CurrentControlSet\Services\NfsClnt\NFS LANS`
- `0x140003ba8`: `SYSTEM\CurrentControlSet\Services\NfsClnt\NFS LANS`
- `0x140003a75`: `GetLanListFromRegistry`

## pseudocode

```c
void GetLanListFromRegistry()
{
  char *v0; // rdi
  char *v1; // r14
  char *v2; // rsi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx
  char LastError; // al
  _QWORD *v6; // rdi
  DWORD v7; // r15d
  DWORD i; // edx
  HGLOBAL j; // rbx
  __int64 v10; // rax
  __int64 v11; // r14
  char *v12; // rax
  _DWORD *v13; // rbx
  const WCHAR *v14; // rdx
  int *v15; // r14
  _BYTE *v16; // rcx
  int HostsList; // eax
  int v18; // edx
  unsigned int v19; // eax
  _QWORD *v20; // r15
  _QWORD *v21; // rbx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  char v24; // al
  char v25; // al
  _QWORD *v26; // rcx
  _QWORD *v27; // rbx
  DWORD v28; // r14d
  int v29; // edx
  __int64 v30; // rax
  _QWORD *k; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v33; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int ThrdAddr; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  char v38[32]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String2[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  strcpy(v38, "GetLanListFromRegistry");
  phkResult = 0;
  v33 = 0;
  ftLastWriteTime = 0;
  ThrdAddr = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids);
  EnterCriticalSection(&LanListCS);
  v0 = (char *)pLanHead;
  v1 = 0;
  if ( pLanHead )
  {
    do
    {
      hKey = 0;
      v2 = (char *)*((_QWORD *)v0 + 6);
      memset_0(Buffer, 0, 0x208u);
      _snwprintf_s(
        Buffer,
        0x104u,
        0x103u,
        L"%s\\%s",
        L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS",
        *((_QWORD *)v0 + 1));
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey) )
      {
        WaitForSingleObject(DaUpdateMutex, 0xFFFFFFFF);
        EnterCriticalSection((LPCRITICAL_SECTION)(v0 + 64));
        v3 = (_QWORD *)*((_QWORD *)v0 + 4);
        if ( v3 )
        {
          do
          {
            v4 = (_QWORD *)v3[2];
            GlobalFree(v3);
            v3 = v4;
          }
          while ( v4 );
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(v0 + 64));
        GlobalFree(v0);
        if ( v1 )
          *((_QWORD *)v1 + 6) = v2;
        else
          pLanHead = v2;
        ReleaseMutex(DaUpdateMutex);
      }
      else
      {
        RegCloseKey(hKey);
        v1 = v0;
      }
      v0 = v2;
    }
    while ( v2 );
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS",
         0,
         0x20019u,
         &phkResult) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
        (unsigned int)v38,
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS",
        LastError);
    goto LABEL_64;
  }
  v6 = 0;
  cbData = 261;
  v7 = 0;
  for ( i = 0; !RegEnumKeyExW(phkResult, i, String2, &cbData, 0, 0, 0, &ftLastWriteTime); i = v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
        (unsigned int)v38,
        (__int64)String2);
    if ( String2[0] )
    {
      for ( j = pLanHead; j; j = (HGLOBAL)*((_QWORD *)j + 6) )
      {
        if ( !_wcsicmp(*((const wchar_t **)j + 1), String2) )
          goto LABEL_47;
      }
      v10 = -1;
      do
        ++v10;
      while ( String2[v10] );
      v11 = (unsigned int)(v10 + 1);
      v12 = (char *)GlobalAlloc(0x40u, 2 * v11 + 104);
      v13 = v12;
      if ( !v12 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            76,
            (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
            (unsigned int)v38,
            8);
LABEL_56:
        if ( v33 )
          RegCloseKey(v33);
        if ( v13 )
          GlobalFree(v13);
        if ( v6 )
        {
          do
          {
            v21 = (_QWORD *)v6[6];
            GlobalFree(v6);
            v6 = v21;
          }
          while ( v21 );
        }
        if ( phkResult )
          RegCloseKey(phkResult);
LABEL_64:
        LeaveCriticalSection(&LanListCS);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v23 = 91;
          goto LABEL_115;
        }
        return;
      }
      *((_QWORD *)v12 + 1) = v12 + 104;
      wcscpy_s((wchar_t *)v12 + 52, (unsigned int)v11, String2);
      v14 = (const WCHAR *)*((_QWORD *)v13 + 1);
      *((_QWORD *)v13 + 5) = 0;
      *v13 = 1;
      if ( RegOpenKeyExW(phkResult, v14, 0, 0x20019u, &v33) )
      {
        v25 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
            (unsigned int)v38,
            *((_QWORD *)v13 + 1),
            v25);
        goto LABEL_56;
      }
      v15 = v13 + 4;
      cbData = 4;
      if ( RegQueryValueExW(v33, L"Configure Mode", 0, 0, (LPBYTE)v13 + 16, &cbData) )
      {
        v24 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            78,
            (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
            (unsigned int)v38,
            (__int64)L"Configure Mode",
            v24);
        goto LABEL_56;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
          (unsigned int)v38,
          *v15);
        v16 = WPP_GLOBAL_Control;
      }
      HostsList = *v15;
      if ( *v15 )
      {
        if ( HostsList != 1 )
        {
          if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 2) == 0 )
            goto LABEL_56;
          v18 = 82;
LABEL_40:
          WPP_SF_sd(
            *((_QWORD *)v16 + 2),
            v18,
            (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
            (unsigned int)v38,
            HostsList);
          goto LABEL_56;
        }
        HostsList = ReadHostsList(v13, v33);
        if ( HostsList )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_56;
          v18 = 81;
          goto LABEL_40;
        }
      }
      else
      {
        HostsList = ReadBroadcastOptions(v13, v33);
        if ( HostsList )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_56;
          v18 = 80;
          goto LABEL_40;
        }
      }
      HostsList = SafeInitializeCriticalSection((LPCRITICAL_SECTION)(v13 + 16));
      if ( HostsList )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_56;
        v18 = 83;
        goto LABEL_40;
      }
      if ( v6 )
      {
        v6[7] = v13;
        *((_QWORD *)v13 + 6) = v6;
      }
      v6 = v13;
      RegCloseKey(v33);
      v33 = 0;
    }
LABEL_47:
    ++v7;
    cbData = 260;
  }
  RegCloseKey(phkResult);
  phkResult = 0;
  if ( !v6 )
    goto LABEL_112;
  v13 = v6;
  v19 = 0;
  do
  {
    v13 = (_DWORD *)*((_QWORD *)v13 + 6);
    ++v19;
  }
  while ( v13 );
  hObjects = GlobalAlloc(0x40u, 8LL * v19);
  v20 = hObjects;
  if ( !hObjects )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v38);
    goto LABEL_56;
  }
  v26 = WPP_GLOBAL_Control;
  v27 = v6;
  v28 = 0;
  do
  {
    if ( *((_DWORD *)v27 + 4) == 1 )
    {
      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
      {
        v29 = 85;
LABEL_90:
        WPP_SF_sS(
          v26[2],
          v29,
          (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
          (unsigned int)v38,
          v27[1]);
LABEL_100:
        v26 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v30 = v27[3];
      if ( *(_DWORD *)(v30 + 20) == 2 )
      {
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
        {
          v29 = 86;
          goto LABEL_90;
        }
      }
      else
      {
        *v20 = *(_QWORD *)(v30 + 32);
        if ( _beginthreadex(0, 0, RPCBroadcast, v27, 0, &ThrdAddr) != -1 )
        {
          ++v20;
          ++v28;
          goto LABEL_100;
        }
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v38);
          goto LABEL_100;
        }
      }
    }
    v27 = (_QWORD *)v27[6];
  }
  while ( v27 );
  if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
    WPP_SF_sd(v26[2], 88, (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids, (unsigned int)v38, v28);
  if ( v28 )
  {
    WaitForMultipleObjects(v28, (const HANDLE *)hObjects, 1, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v38);
  }
  for ( k = v6; k[6]; k = (_QWORD *)k[6] )
    ;
  k[6] = pLanHead;
  pLanHead = v6;
LABEL_112:
  LeaveCriticalSection(&LanListCS);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v23 = 90;
LABEL_115:
    WPP_SF_s(v22[2], v23, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v38);
  }
}

```

## disassembly

```asm
0x140003a48  push    rbp
0x140003a4a  push    rbx
0x140003a4b  push    rsi
0x140003a4c  push    rdi
0x140003a4d  push    r12
0x140003a4f  push    r13
0x140003a51  push    r14
0x140003a53  push    r15
0x140003a55  lea     rbp, [rsp-3C8h]
0x140003a5d  sub     rsp, 4C8h
0x140003a64  mov     rax, cs:__security_cookie
0x140003a6b  xor     rax, rsp
0x140003a6e  mov     [rbp+400h+var_50], rax
0x140003a75  movups  xmm0, xmmword ptr cs:aGetlanlistfrom; "GetLanListFromRegistry"
0x140003a7c  xor     r12d, r12d
0x140003a7f  movsd   xmm1, qword ptr cs:aGetlanlistfrom+0Fh; "egistry"
0x140003a87  movups  xmmword ptr [rsp+500h+var_490], xmm0
0x140003a8c  mov     [rsp+500h+var_4B0], r12
0x140003a91  movsd   qword ptr [rsp+500h+var_490+0Fh], xmm1
0x140003a97  mov     [rsp+500h+var_4B8], r12
0x140003a9c  mov     qword ptr [rsp+500h+ftLastWriteTime.dwLowDateTime], r12
0x140003aa1  mov     [rsp+500h+ThrdAddr], r12d
0x140003aa6  mov     [rsp+500h+cbData], r12d
0x140003aab  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ab2  lea     r13, WPP_GLOBAL_Control
0x140003ab9  cmp     rcx, r13
0x140003abc  jz      short loc_140003AD9
0x140003abe  test    byte ptr [rcx+1Ch], 1
0x140003ac2  jz      short loc_140003AD9
0x140003ac4  mov     rcx, [rcx+10h]
0x140003ac8  lea     edx, [r12+49h]
0x140003acd  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140003ad4  call    WPP_SF_
0x140003ad9  lea     rcx, LanListCS; lpCriticalSection
0x140003ae0  call    cs:__imp_EnterCriticalSection
0x140003ae6  mov     rdi, cs:pLanHead
0x140003aed  lea     rbx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x140003af4  mov     r14, r12
0x140003af7  test    rdi, rdi
0x140003afa  jz      loc_140003BFD
0x140003b00  mov     [rsp+500h+hKey], r12
0x140003b05  lea     rcx, [rbp+400h+Buffer]; void *
0x140003b0c  mov     rsi, [rdi+30h]
0x140003b10  xor     edx, edx; Val
0x140003b12  mov     r8d, 208h; Size
0x140003b18  call    memset_0
0x140003b1d  mov     rax, [rdi+8]
0x140003b21  lea     r9, aSS; "%s\\%s"
0x140003b28  mov     edx, 104h; BufferCount
0x140003b2d  mov     [rsp+500h+lpcbData], rax
0x140003b32  lea     rcx, [rbp+400h+Buffer]; Buffer
0x140003b39  mov     [rsp+500h+phkResult], rbx
0x140003b3e  lea     r8d, [rdx-1]; MaxCount
0x140003b42  call    cs:__imp__snwprintf_s
0x140003b48  lea     rax, [rsp+500h+hKey]
0x140003b4d  mov     r9d, 20019h; samDesired
0x140003b53  xor     r8d, r8d; ulOptions
0x140003b56  mov     [rsp+500h+phkResult], rax; phkResult
0x140003b5b  lea     rdx, [rbp+400h+Buffer]; lpSubKey
0x140003b62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003b69  call    cs:__imp_RegOpenKeyExW
0x140003b6f  test    eax, eax
0x140003b71  jz      short loc_140003BE3
0x140003b73  mov     rcx, cs:DaUpdateMutex; hHandle
0x140003b7a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003b7d  call    cs:__imp_WaitForSingleObject
0x140003b83  lea     rcx, [rdi+40h]; lpCriticalSection
0x140003b87  call    cs:__imp_EnterCriticalSection
0x140003b8d  mov     rcx, [rdi+20h]; hMem
0x140003b91  test    rcx, rcx
0x140003b94  jz      short loc_140003BAF
0x140003b96  mov     rbx, [rcx+10h]
0x140003b9a  call    cs:__imp_GlobalFree
0x140003ba0  mov     rcx, rbx
0x140003ba3  test    rbx, rbx
0x140003ba6  jnz     short loc_140003B96
0x140003ba8  lea     rbx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x140003baf  lea     rcx, [rdi+40h]; lpCriticalSection
0x140003bb3  call    cs:__imp_LeaveCriticalSection
0x140003bb9  mov     rcx, rdi; hMem
0x140003bbc  call    cs:__imp_GlobalFree
0x140003bc2  test    r14, r14
0x140003bc5  jz      short loc_140003BCD
0x140003bc7  mov     [r14+30h], rsi
0x140003bcb  jmp     short loc_140003BD4
0x140003bcd  mov     cs:pLanHead, rsi
0x140003bd4  mov     rcx, cs:DaUpdateMutex; hMutex
0x140003bdb  call    cs:__imp_ReleaseMutex
0x140003be1  jmp     short loc_140003BF1
0x140003be3  mov     rcx, [rsp+500h+hKey]; hKey
0x140003be8  call    cs:__imp_RegCloseKey
0x140003bee  mov     r14, rdi
0x140003bf1  mov     rdi, rsi
0x140003bf4  test    rsi, rsi
0x140003bf7  jnz     loc_140003B00
0x140003bfd  lea     rax, [rsp+500h+var_4B0]
0x140003c02  mov     r9d, 20019h; samDesired
0x140003c08  xor     r8d, r8d; ulOptions
0x140003c0b  mov     [rsp+500h+phkResult], rax; phkResult
0x140003c10  mov     rdx, rbx; lpSubKey
0x140003c13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003c1a  call    cs:__imp_RegOpenKeyExW
0x140003c20  mov     esi, 2
0x140003c25  test    eax, eax
0x140003c27  jz      short loc_140003C6F
0x140003c29  call    cs:__imp_GetLastError
0x140003c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c36  cmp     rcx, r13
0x140003c39  jz      loc_140003F6E
0x140003c3f  test    [rcx+1Ch], sil
0x140003c43  jz      loc_140003F6E
0x140003c49  mov     rcx, [rcx+10h]
0x140003c4d  lea     edx, [rsi+48h]
0x140003c50  mov     dword ptr [rsp+500h+lpcbData], eax
0x140003c54  lea     r9, [rsp+500h+var_490]
0x140003c59  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140003c60  mov     [rsp+500h+phkResult], rbx
0x140003c65  call    WPP_SF_sSd
0x140003c6a  jmp     loc_140003F6E
0x140003c6f  mov     rdi, r12
0x140003c72  mov     [rsp+500h+cbData], 105h
0x140003c7a  mov     r15d, r12d
0x140003c7d  xor     edx, edx
0x140003c7f  jmp     loc_140003E7B
0x140003c84  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c8b  cmp     rcx, r13
0x140003c8e  jz      short loc_140003CB9
0x140003c90  test    byte ptr [rcx+1Ch], 10h
0x140003c94  jz      short loc_140003CB9
0x140003c96  mov     rcx, [rcx+10h]
0x140003c9a  lea     rax, [rbp+400h+String2]
0x140003c9e  mov     edx, 4Bh ; 'K'
0x140003ca3  mov     [rsp+500h+phkResult], rax
0x140003ca8  lea     r9, [rsp+500h+var_490]
0x140003cad  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140003cb4  call    WPP_SF_sS
0x140003cb9  cmp     [rbp+400h+String2], r12w
0x140003cbe  jz      loc_140003E6D
0x140003cc4  mov     rbx, cs:pLanHead
0x140003ccb  jmp     short loc_140003CE7
0x140003ccd  mov     rcx, [rbx+8]; String1
0x140003cd1  lea     rdx, [rbp+400h+String2]; String2
0x140003cd5  call    cs:__imp__wcsicmp
0x140003cdb  test    eax, eax
0x140003cdd  jz      loc_140003E6D
0x140003ce3  mov     rbx, [rbx+30h]
0x140003ce7  test    rbx, rbx
0x140003cea  jnz     short loc_140003CCD
0x140003cec  lea     rcx, [rbp+400h+String2]
0x140003cf0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003cf4  inc     rax
0x140003cf7  cmp     [rcx+rax*2], r12w
0x140003cfc  jnz     short loc_140003CF4
0x140003cfe  inc     eax
0x140003d00  mov     ecx, 40h ; '@'; uFlags
0x140003d05  mov     r14d, eax
0x140003d08  lea     rdx, ds:68h[rax*2]; dwBytes
0x140003d10  call    cs:__imp_GlobalAlloc
0x140003d16  mov     rbx, rax
0x140003d19  test    rax, rax
0x140003d1c  jz      loc_140004082
0x140003d22  lea     rcx, [rax+68h]; Destination
0x140003d26  mov     edx, r14d; SizeInWords
0x140003d29  lea     r8, [rbp+400h+String2]; Source
0x140003d2d  mov     [rax+8], rcx
0x140003d31  call    cs:__imp_wcscpy_s
0x140003d37  mov     rdx, [rbx+8]; lpSubKey
0x140003d3b  lea     rax, [rsp+500h+var_4B8]
0x140003d40  mov     [rbx+28h], r12
0x140003d44  mov     r9d, 20019h; samDesired
0x140003d4a  mov     dword ptr [rbx], 1
0x140003d50  xor     r8d, r8d; ulOptions
0x140003d53  mov     rcx, [rsp+500h+var_4B0]; hKey
0x140003d58  mov     [rsp+500h+phkResult], rax; phkResult
0x140003d5d  call    cs:__imp_RegOpenKeyExW
0x140003d63  test    eax, eax
0x140003d65  jnz     loc_140004036
0x140003d6b  mov     rcx, [rsp+500h+var_4B8]; hKey
0x140003d70  lea     rax, [rsp+500h+cbData]
0x140003d75  mov     [rsp+500h+lpcbData], rax; lpcbData
0x140003d7a  lea     r14, [rbx+10h]
0x140003d7e  xor     r9d, r9d; lpType
0x140003d81  mov     [rsp+500h+phkResult], r14; lpData
0x140003d86  xor     r8d, r8d; lpReserved
0x140003d89  mov     [rsp+500h+cbData], 4
0x140003d91  lea     rdx, aConfigureMode; "Configure Mode"
0x140003d98  call    cs:__imp_RegQueryValueExW
0x140003d9e  test    eax, eax
0x140003da0  jnz     loc_140004004
0x140003da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dad  cmp     rcx, r13
0x140003db0  jz      short loc_140003DDE
0x140003db2  test    byte ptr [rcx+1Ch], 8
0x140003db6  jz      short loc_140003DDE
0x140003db8  mov     rcx, [rcx+10h]
0x140003dbc  lea     edx, [rax+4Fh]
0x140003dbf  mov     eax, [r14]
0x140003dc2  lea     r9, [rsp+500h+var_490]
0x140003dc7  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140003dce  mov     dword ptr [rsp+500h+phkResult], eax
0x140003dd2  call    WPP_SF_sd
0x140003dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dde  mov     eax, [r14]
0x140003de1  test    eax, eax
0x140003de3  jnz     short loc_140003E1E
0x140003de5  mov     rdx, [rsp+500h+var_4B8]
0x140003dea  mov     rcx, rbx
0x140003ded  call    ReadBroadcastOptions
0x140003df2  test    eax, eax
0x140003df4  jz      short loc_140003E3C
0x140003df6  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dfd  cmp     rcx, r13
0x140003e00  jz      loc_140003F26
0x140003e06  test    [rcx+1Ch], sil
0x140003e0a  jz      loc_140003F26
0x140003e10  mov     edx, 50h ; 'P'
0x140003e15  mov     dword ptr [rsp+500h+phkResult], eax
0x140003e19  jmp     loc_1400040A9
0x140003e1e  cmp     eax, 1
0x140003e21  jnz     loc_140003FE7
0x140003e27  mov     rdx, [rsp+500h+var_4B8]
0x140003e2c  mov     rcx, rbx
0x140003e2f  call    ReadHostsList
0x140003e34  test    eax, eax
0x140003e36  jnz     loc_140003FC3
0x140003e3c  lea     rcx, [rbx+40h]; lpCriticalSection
0x140003e40  call    SafeInitializeCriticalSection
0x140003e45  test    eax, eax
0x140003e47  jnz     loc_140003F9F
0x140003e4d  test    rdi, rdi
0x140003e50  jz      short loc_140003E5A
0x140003e52  mov     [rdi+38h], rbx
0x140003e56  mov     [rbx+30h], rdi
0x140003e5a  mov     rcx, [rsp+500h+var_4B8]; hKey
0x140003e5f  mov     rdi, rbx
0x140003e62  call    cs:__imp_RegCloseKey
0x140003e68  mov     [rsp+500h+var_4B8], r12
0x140003e6d  inc     r15d
0x140003e70  mov     [rsp+500h+cbData], 104h
0x140003e78  mov     edx, r15d; dwIndex
0x140003e7b  mov     rcx, [rsp+500h+var_4B0]; hKey
0x140003e80  lea     rax, [rsp+500h+ftLastWriteTime]
0x140003e85  mov     [rsp+500h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140003e8a  lea     r9, [rsp+500h+cbData]; lpcchName
0x140003e8f  mov     [rsp+500h+lpcchClass], r12; lpcchClass
0x140003e94  lea     r8, [rbp+400h+String2]; lpName
0x140003e98  mov     [rsp+500h+lpcbData], r12; lpClass
0x140003e9d  mov     [rsp+500h+phkResult], r12; lpReserved
0x140003ea2  call    cs:__imp_RegEnumKeyExW
0x140003ea8  test    eax, eax
0x140003eaa  jz      loc_140003C84
0x140003eb0  mov     rcx, [rsp+500h+var_4B0]; hKey
0x140003eb5  call    cs:__imp_RegCloseKey
0x140003ebb  mov     [rsp+500h+var_4B0], r12
0x140003ec0  test    rdi, rdi
0x140003ec3  jz      loc_140004238
0x140003ec9  mov     rbx, rdi
0x140003ecc  mov     eax, r12d
0x140003ecf  mov     rbx, [rbx+30h]
0x140003ed3  inc     eax
0x140003ed5  test    rbx, rbx
0x140003ed8  jnz     short loc_140003ECF
0x140003eda  mov     edx, eax
0x140003edc  lea     ecx, [rbx+40h]; uFlags
0x140003edf  shl     rdx, 3; dwBytes
0x140003ee3  call    cs:__imp_GlobalAlloc
0x140003ee9  mov     cs:hObjects, rax
0x140003ef0  mov     r15, rax
0x140003ef3  test    rax, rax
0x140003ef6  jnz     loc_1400040C3
0x140003efc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f03  cmp     rcx, r13
0x140003f06  jz      short loc_140003F26
0x140003f08  test    [rcx+1Ch], sil
0x140003f0c  jz      short loc_140003F26
0x140003f0e  mov     rcx, [rcx+10h]
0x140003f12  lea     edx, [rbx+54h]
0x140003f15  lea     r9, [rsp+500h+var_490]
0x140003f1a  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140003f21  call    WPP_SF_s
0x140003f26  mov     rcx, [rsp+500h+var_4B8]; hKey
0x140003f2b  test    rcx, rcx
0x140003f2e  jz      short loc_140003F36
0x140003f30  call    cs:__imp_RegCloseKey
0x140003f36  test    rbx, rbx
0x140003f39  jz      short loc_140003F44
0x140003f3b  mov     rcx, rbx; hMem
0x140003f3e  call    cs:__imp_GlobalFree
0x140003f44  test    rdi, rdi
0x140003f47  jz      short loc_140003F5E
0x140003f49  mov     rbx, [rdi+30h]
0x140003f4d  mov     rcx, rdi; hMem
0x140003f50  call    cs:__imp_GlobalFree
0x140003f56  mov     rdi, rbx
0x140003f59  test    rbx, rbx
0x140003f5c  jnz     short loc_140003F49
0x140003f5e  mov     rcx, [rsp+500h+var_4B0]; hKey
0x140003f63  test    rcx, rcx
0x140003f66  jz      short loc_140003F6E
0x140003f68  call    cs:__imp_RegCloseKey
  ... truncated ...
```
