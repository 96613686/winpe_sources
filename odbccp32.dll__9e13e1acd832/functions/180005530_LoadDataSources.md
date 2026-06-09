# LoadDataSources

- ea: `0x180005530`
- end: `0x180005ae5`
- name: `LoadDataSources`
- size: `1461`
- prototype: `LSTATUS __fastcall(HWND)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000b9c0`

## callees

- `0x1800017c0`
- `0x180002940`
- `0x180002e4c`
- `0x180005108`
- `0x180005530`
- `0x1800074c4`
- `0x1800080c4`
- `0x18000a378`
- `0x18000ac40`
- `0x18000d5a8`
- `0x18001463c`
- `0x180014ae0`
- `0x180014b70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005a42`
- `msvcrt!_wcsicmp` at `0x180005a5a`
- `msvcrt!_wcsicmp` at `0x180005a42`
- `msvcrt!_wcsicmp` at `0x180005a5a`
- `msvcrt!_wsplitpath_s` at `0x1800059f2`
- `msvcrt!_wsplitpath_s` at `0x180005a2e`
- `msvcrt!_wsplitpath_s` at `0x1800059f2`
- `msvcrt!_wsplitpath_s` at `0x180005a2e`
- `msvcrt!malloc` at `0x180005573`
- `msvcrt!malloc` at `0x1800055cd`
- `msvcrt!malloc` at `0x180005573`
- `msvcrt!malloc` at `0x1800055cd`
- `USER32!EnableWindow` at `0x180005ad2`
- `USER32!EnableWindow` at `0x180005ad2`
- `USER32!SendMessageW` at `0x18000565d`
- `USER32!SendMessageW` at `0x18000565d`
- `ADVAPI32!RegCloseKey` at `0x1800058f3`
- `ADVAPI32!RegCloseKey` at `0x180005903`
- `ADVAPI32!RegCloseKey` at `0x1800058f3`
- `ADVAPI32!RegCloseKey` at `0x180005903`
- `ADVAPI32!RegOpenKeyExW` at `0x180005838`
- `ADVAPI32!RegOpenKeyExW` at `0x180005838`
- `ADVAPI32!RegEnumValueW` at `0x180005891`
- `ADVAPI32!RegEnumValueW` at `0x180005891`

## pseudocode

```c
LSTATUS __fastcall LoadDataSources(HWND a1)
{
  int v2; // r13d
  _WORD *v3; // rax
  _WORD *v4; // rdi
  int v5; // ebx
  LSTATUS result; // eax
  int v7; // r14d
  BOOL v8; // r15d
  int v9; // r12d
  _WORD *i; // rbx
  unsigned __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  DWORD j; // ebx
  int v16; // eax
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Data[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[128]; // [rsp+170h] [rbp+70h] BYREF
  __int16 v25[128]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t pszFormat[264]; // [rsp+370h] [rbp+270h] BYREF
  wchar_t pszDest[264]; // [rsp+580h] [rbp+480h] BYREF
  wchar_t FullPath[264]; // [rsp+790h] [rbp+690h] BYREF
  wchar_t v29[264]; // [rsp+9A0h] [rbp+8A0h] BYREF
  wchar_t Filename[264]; // [rsp+BB0h] [rbp+AB0h] BYREF
  wchar_t String2[264]; // [rsp+DC0h] [rbp+CC0h] BYREF
  wchar_t Ext[264]; // [rsp+FD0h] [rbp+ED0h] BYREF

  v2 = 0;
  v22 = 0;
  v3 = malloc(0x2000u);
  v4 = v3;
  if ( !v3 )
    return MemError();
  v5 = 4096;
  while ( (int)SQLGetPrivateProfileStringCover(L"ODBC Data Sources", 0, &SubKey, v3, v5, L"ODBC.INI") >= v5 - 2
       && v5 < 0x100000 )
  {
    v5 *= 2;
    OFree(v4);
    v3 = malloc(2LL * v5);
    v4 = v3;
    if ( !v3 )
      return MemError();
  }
  v25[0] = 0;
  Data[0] = 0;
  v7 = 0;
  ValueName[0] = 0;
  v8 = 0;
  v9 = 0;
  DetermineSel2(a1, (__int64)v25, 128, 0, 0, 0, 0, &v22);
  SendMessageW(a1, 0x1009u, 0, 0);
  for ( i = v4; *i; i += v14 + 1 )
  {
    v11 = -1;
    do
      ++v11;
    while ( i[v11] );
    if ( v11 <= 0x20 )
    {
      SQLGetPrivateProfileStringCover(L"ODBC Data Sources", i, &SubKey, Data, 128, L"ODBC.INI");
      v12 = -1;
      do
        ++v12;
      while ( Data[v12] );
      if ( v12 )
      {
        v13 = 12;
        if ( g_wSystemDSN == 2 )
          v13 = 4;
        v17 = v13;
        DetectDriverAvailbility(Data, &v17);
        result = AddLvDsnInfo(a1, v17);
        if ( result )
          return result;
        v8 = 1;
        ++v7;
      }
      else if ( !v2 )
      {
        SetString(pszFormat, 260);
        StringCchPrintfW(pszDest, 0x104u, pszFormat, i);
        DoMessage(a1, pszDest, 0x30u);
        v2 = 1;
      }
    }
    else if ( !v9 )
    {
      SetString(pszFormat, 260);
      StringCchPrintfW(pszDest, 0x104u, pszFormat, i);
      DoMessage(a1, pszDest, 0x30u);
      v9 = 1;
    }
    v14 = -1;
    do
      ++v14;
    while ( i[v14] );
  }
  if ( g_wSystemDSN == 1 && !g_fRunningOn32bitOS )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\ODBC\\ODBC.INI\\ODBC Data Sources", 0, 0x20219u, &hKey) )
    {
      Type = 0;
      for ( j = 0; ; ++j )
      {
        cchValueName = 128;
        cbData = 256;
        if ( RegEnumValueW(hKey, j, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
          break;
        if ( ValueName[0] && Type == 1 )
        {
          v17 = 8;
          DetectDriverAvailbility(Data, &v17);
          if ( (unsigned int)AddLvDsnInfo(a1, v17) )
            return RegCloseKey(hKey);
          v8 = 1;
          ++v7;
        }
      }
      RegCloseKey(hKey);
    }
  }
  if ( (int)SQLGetPrivateProfileStringCover(L"Default", L"Driver", &SubKey, Data, 128, L"ODBCINST.INI") <= 0 )
    goto LABEL_48;
  if ( (int)SQLGetPrivateProfileStringCover(Data, L"Driver", &SubKey, FullPath, 260, L"ODBCINST.INI") <= 0 )
    goto LABEL_48;
  if ( (int)SQLGetPrivateProfileStringCover(L"Default", L"Driver", &SubKey, v29, 260, L"ODBC.INI") <= 0 )
    goto LABEL_48;
  _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
  _wsplitpath_s(v29, 0, 0, 0, 0, FullPath, 0x104u, String2, 0x104u);
  if ( _wcsicmp(Filename, FullPath) || _wcsicmp(Ext, String2) )
    goto LABEL_48;
  v16 = 12;
  if ( g_wSystemDSN == 2 )
    v16 = 4;
  v17 = v16;
  DetectDriverAvailbility(Data, &v17);
  result = AddLvDsnInfo(a1, v17);
  if ( !result )
  {
    v8 = 1;
LABEL_48:
    LvSelectByNameParam(a1);
    EnableWindow(a1, v8);
    return OFree(v4);
  }
  return result;
}

```

## disassembly

```asm
0x180005530  push    rbp
0x180005532  push    rbx
0x180005533  push    rsi
0x180005534  push    rdi
0x180005535  push    r12
0x180005537  push    r13
0x180005539  push    r14
0x18000553b  push    r15
0x18000553d  lea     rbp, [rsp-10F8h]
0x180005545  mov     eax, 11F8h
0x18000554a  call    _alloca_probe
0x18000554f  sub     rsp, rax
0x180005552  mov     rax, cs:__security_cookie
0x180005559  xor     rax, rsp
0x18000555c  mov     [rbp+1130h+var_50], rax
0x180005563  mov     rsi, rcx
0x180005566  xor     r13d, r13d
0x180005569  mov     ecx, 2000h; Size
0x18000556e  mov     [rsp+1230h+var_11C8], r13
0x180005573  call    cs:__imp_malloc
0x180005579  mov     rdi, rax
0x18000557c  test    rax, rax
0x18000557f  jz      short loc_1800055DB
0x180005581  mov     ebx, 1000h
0x180005586  lea     r14, aOdbcIni; "ODBC.INI"
0x18000558d  mov     [rsp+1230h+lpType], r14
0x180005592  lea     r8, SubKey
0x180005599  mov     r9, rax
0x18000559c  mov     dword ptr [rsp+1230h+phkResult], ebx
0x1800055a0  xor     edx, edx
0x1800055a2  lea     rcx, aOdbcDataSource; "ODBC Data Sources"
0x1800055a9  call    SQLGetPrivateProfileStringCover
0x1800055ae  lea     ecx, [rbx-2]
0x1800055b1  cmp     eax, ecx
0x1800055b3  jl      short loc_180005603
0x1800055b5  cmp     ebx, 100000h
0x1800055bb  jge     short loc_180005603
0x1800055bd  mov     rcx, rdi
0x1800055c0  add     ebx, ebx
0x1800055c2  call    OFree
0x1800055c7  movsxd  rcx, ebx
0x1800055ca  add     rcx, rcx; Size
0x1800055cd  call    cs:__imp_malloc
0x1800055d3  mov     rdi, rax
0x1800055d6  test    rax, rax
0x1800055d9  jnz     short loc_18000558D
0x1800055db  call    MemError
0x1800055e0  mov     rcx, [rbp+1130h+var_50]
0x1800055e7  xor     rcx, rsp; StackCookie
0x1800055ea  call    __security_check_cookie
0x1800055ef  add     rsp, 11F8h
0x1800055f6  pop     r15
0x1800055f8  pop     r14
0x1800055fa  pop     r13
0x1800055fc  pop     r12
0x1800055fe  pop     rdi
0x1800055ff  pop     rsi
0x180005600  pop     rbx
0x180005601  pop     rbp
0x180005602  retn
0x180005603  xor     ecx, ecx
0x180005605  mov     [rbp+1130h+var_FC0], r13w
0x18000560d  lea     rax, [rsp+1230h+var_11C8]
0x180005612  mov     [rsp+1230h+Data], cx
0x180005617  mov     [rsp+1230h+lpcbData], rax; __int64
0x18000561c  lea     rdx, [rbp+1130h+var_FC0]
0x180005623  mov     dword ptr [rsp+1230h+lpData], ecx; int
0x180005627  xor     r9d, r9d
0x18000562a  mov     [rsp+1230h+lpType], rcx; __int64
0x18000562f  mov     r8d, 80h
0x180005635  mov     dword ptr [rsp+1230h+phkResult], ecx; int
0x180005639  mov     r14d, r13d
0x18000563c  mov     rcx, rsi; hWnd
0x18000563f  mov     [rbp+1130h+ValueName], r13w
0x180005644  mov     r15d, r13d
0x180005647  mov     r12d, r13d
0x18000564a  call    DetermineSel2
0x18000564f  xor     r9d, r9d; lParam
0x180005652  xor     r8d, r8d; wParam
0x180005655  mov     edx, 1009h; Msg
0x18000565a  mov     rcx, rsi; hWnd
0x18000565d  call    cs:__imp_SendMessageW
0x180005663  xor     ecx, ecx
0x180005665  mov     rbx, rdi
0x180005668  cmp     [rbx], cx
0x18000566b  jz      loc_1800057EE
0x180005671  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005675  inc     rax
0x180005678  cmp     [rbx+rax*2], cx
0x18000567c  jnz     short loc_180005675
0x18000567e  cmp     rax, 20h ; ' '
0x180005682  jbe     short loc_1800056DE
0x180005684  test    r12d, r12d
0x180005687  jnz     loc_1800057D4
0x18000568d  mov     edx, 104h; cchBufferMax
0x180005692  lea     rcx, [rbp+1130h+pszFormat]; lpBuffer
0x180005699  mov     r8d, 77Bh
0x18000569f  call    SetString
0x1800056a4  mov     r9, rbx
0x1800056a7  lea     r8, [rbp+1130h+pszFormat]; pszFormat
0x1800056ae  mov     edx, 104h; cchDest
0x1800056b3  lea     rcx, [rbp+1130h+pszDest]; pszDest
0x1800056ba  call    StringCchPrintfW
0x1800056bf  lea     r8d, [r12+30h]; uType
0x1800056c4  mov     rcx, rsi; hWnd
0x1800056c7  lea     rdx, [rbp+1130h+pszDest]; lpText
0x1800056ce  call    DoMessage
0x1800056d3  xor     ecx, ecx
0x1800056d5  lea     r12d, [rcx+1]
0x1800056d9  jmp     loc_1800057D4
0x1800056de  lea     rax, aOdbcIni; "ODBC.INI"
0x1800056e5  mov     rdx, rbx
0x1800056e8  mov     [rsp+1230h+lpType], rax
0x1800056ed  lea     r9, [rsp+1230h+Data]
0x1800056f2  lea     r8, SubKey
0x1800056f9  mov     dword ptr [rsp+1230h+phkResult], 80h
0x180005701  lea     rcx, aOdbcDataSource; "ODBC Data Sources"
0x180005708  call    SQLGetPrivateProfileStringCover
0x18000570d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005711  lea     rdx, [rsp+1230h+Data]
0x180005716  xor     ecx, ecx
0x180005718  inc     rax
0x18000571b  cmp     [rdx+rax*2], cx
0x18000571f  jnz     short loc_180005718
0x180005721  test    rax, rax
0x180005724  jnz     short loc_180005780
0x180005726  test    r13d, r13d
0x180005729  jnz     loc_1800057D4
0x18000572f  mov     r13d, 104h
0x180005735  lea     rcx, [rbp+1130h+pszFormat]; lpBuffer
0x18000573c  mov     edx, r13d; cchBufferMax
0x18000573f  mov     r8d, 77Ch
0x180005745  call    SetString
0x18000574a  mov     r9, rbx
0x18000574d  lea     r8, [rbp+1130h+pszFormat]; pszFormat
0x180005754  mov     edx, r13d; cchDest
0x180005757  lea     rcx, [rbp+1130h+pszDest]; pszDest
0x18000575e  call    StringCchPrintfW
0x180005763  mov     r8d, 30h ; '0'; uType
0x180005769  lea     rdx, [rbp+1130h+pszDest]; lpText
0x180005770  mov     rcx, rsi; hWnd
0x180005773  call    DoMessage
0x180005778  xor     ecx, ecx
0x18000577a  lea     r13d, [rcx+1]
0x18000577e  jmp     short loc_1800057D4
0x180005780  mov     eax, 0Ch
0x180005785  lea     rdx, [rsp+1230h+var_11E0]
0x18000578a  lea     ecx, [rax-0Ah]
0x18000578d  cmp     cx, cs:g_wSystemDSN
0x180005794  lea     ecx, [rax-8]
0x180005797  cmovz   eax, ecx
0x18000579a  lea     rcx, [rsp+1230h+Data]; lpSubKey
0x18000579f  mov     [rsp+1230h+var_11E0], eax
0x1800057a3  call    DetectDriverAvailbility
0x1800057a8  mov     eax, [rsp+1230h+var_11E0]
0x1800057ac  lea     r9, [rsp+1230h+Data]
0x1800057b1  mov     r8, rbx
0x1800057b4  mov     dword ptr [rsp+1230h+phkResult], eax; int
0x1800057b8  mov     edx, r14d
0x1800057bb  mov     rcx, rsi; hWnd
0x1800057be  call    AddLvDsnInfo
0x1800057c3  xor     ecx, ecx
0x1800057c5  test    eax, eax
0x1800057c7  jnz     loc_1800055E0
0x1800057cd  lea     r15d, [rcx+1]
0x1800057d1  inc     r14d
0x1800057d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800057d8  inc     rax
0x1800057db  cmp     [rbx+rax*2], cx
0x1800057df  jnz     short loc_1800057D8
0x1800057e1  lea     rbx, [rbx+rax*2]
0x1800057e5  add     rbx, 2
0x1800057e9  jmp     loc_180005668
0x1800057ee  mov     r13d, 1
0x1800057f4  xor     r12d, r12d
0x1800057f7  cmp     r13w, cs:g_wSystemDSN
0x1800057ff  jnz     loc_180005909
0x180005805  cmp     cs:g_fRunningOn32bitOS, r12d
0x18000580c  jnz     loc_180005909
0x180005812  lea     rax, [rsp+1230h+hKey]
0x180005817  mov     [rsp+1230h+hKey], r12
0x18000581c  mov     r9d, 20219h; samDesired
0x180005822  mov     [rsp+1230h+phkResult], rax; phkResult
0x180005827  xor     r8d, r8d; ulOptions
0x18000582a  lea     rdx, aSoftwareOdbcOd_0; "SOFTWARE\\ODBC\\ODBC.INI\\ODBC Data Sou"...
0x180005831  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005838  call    cs:__imp_RegOpenKeyExW
0x18000583e  test    eax, eax
0x180005840  jnz     loc_180005909
0x180005846  mov     [rsp+1230h+Type], r12d
0x18000584b  mov     ebx, r12d
0x18000584e  mov     rcx, [rsp+1230h+hKey]; hKey
0x180005853  lea     rax, [rsp+1230h+cbData]
0x180005858  mov     [rsp+1230h+lpcbData], rax; lpcbData
0x18000585d  lea     r9, [rsp+1230h+cchValueName]; lpcchValueName
0x180005862  lea     rax, [rsp+1230h+Data]
0x180005867  mov     [rsp+1230h+cchValueName], 80h
0x18000586f  mov     [rsp+1230h+lpData], rax; lpData
0x180005874  lea     r8, [rbp+1130h+ValueName]; lpValueName
0x180005878  lea     rax, [rsp+1230h+Type]
0x18000587d  mov     [rsp+1230h+cbData], 100h
0x180005885  mov     [rsp+1230h+lpType], rax; lpType
0x18000588a  mov     edx, ebx; dwIndex
0x18000588c  mov     [rsp+1230h+phkResult], r12; lpReserved
0x180005891  call    cs:__imp_RegEnumValueW
0x180005897  test    eax, eax
0x180005899  jnz     short loc_1800058FE
0x18000589b  cmp     [rbp+1130h+ValueName], r12w
0x1800058a0  jz      short loc_1800058E6
0x1800058a2  cmp     [rsp+1230h+Type], r13d
0x1800058a7  jnz     short loc_1800058E6
0x1800058a9  lea     rdx, [rsp+1230h+var_11E0]
0x1800058ae  mov     [rsp+1230h+var_11E0], 8
0x1800058b6  lea     rcx, [rsp+1230h+Data]; lpSubKey
0x1800058bb  call    DetectDriverAvailbility
0x1800058c0  mov     eax, [rsp+1230h+var_11E0]
0x1800058c4  lea     r9, [rsp+1230h+Data]
0x1800058c9  lea     r8, [rbp+1130h+ValueName]
0x1800058cd  mov     dword ptr [rsp+1230h+phkResult], eax; int
0x1800058d1  mov     edx, r14d
0x1800058d4  mov     rcx, rsi; hWnd
0x1800058d7  call    AddLvDsnInfo
0x1800058dc  test    eax, eax
0x1800058de  jnz     short loc_1800058EE
0x1800058e0  mov     r15d, r13d
0x1800058e3  add     r14d, r13d
0x1800058e6  add     ebx, r13d
0x1800058e9  jmp     loc_18000584E
0x1800058ee  mov     rcx, [rsp+1230h+hKey]; hKey
0x1800058f3  call    cs:__imp_RegCloseKey
0x1800058f9  jmp     loc_1800055E0
0x1800058fe  mov     rcx, [rsp+1230h+hKey]; hKey
0x180005903  call    cs:__imp_RegCloseKey
0x180005909  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180005910  mov     [rsp+1230h+lpType], rax
0x180005915  lea     rbx, aDriver_0; "Driver"
0x18000591c  mov     rdx, rbx
0x18000591f  mov     dword ptr [rsp+1230h+phkResult], 80h
0x180005927  lea     r9, [rsp+1230h+Data]
0x18000592c  lea     r8, SubKey
0x180005933  lea     rcx, aDefault; "Default"
0x18000593a  call    SQLGetPrivateProfileStringCover
0x18000593f  test    eax, eax
0x180005941  jle     loc_180005AB8
0x180005947  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x18000594e  mov     rdx, rbx
0x180005951  mov     [rsp+1230h+lpType], rax
0x180005956  lea     r9, [rbp+1130h+FullPath]
0x18000595d  lea     r8, SubKey
0x180005964  mov     dword ptr [rsp+1230h+phkResult], 104h
0x18000596c  lea     rcx, [rsp+1230h+Data]
0x180005971  call    SQLGetPrivateProfileStringCover
0x180005976  test    eax, eax
0x180005978  jle     loc_180005AB8
0x18000597e  lea     rax, aOdbcIni; "ODBC.INI"
0x180005985  mov     rdx, rbx
0x180005988  mov     [rsp+1230h+lpType], rax
0x18000598d  lea     r9, [rbp+1130h+var_890]
0x180005994  lea     r8, SubKey
0x18000599b  mov     dword ptr [rsp+1230h+phkResult], 104h
0x1800059a3  lea     rcx, aDefault; "Default"
0x1800059aa  call    SQLGetPrivateProfileStringCover
0x1800059af  test    eax, eax
0x1800059b1  jle     loc_180005AB8
0x1800059b7  mov     ebx, 104h
0x1800059bc  lea     rax, [rbp+1130h+Ext]
0x1800059c3  mov     [rsp+1230h+ExtCount], rbx; ExtCount
0x1800059c8  lea     rcx, [rbp+1130h+FullPath]; FullPath
0x1800059cf  mov     [rsp+1230h+lpcbData], rax; Ext
0x1800059d4  xor     r9d, r9d; Dir
0x1800059d7  lea     rax, [rbp+1130h+Filename]
0x1800059de  mov     [rsp+1230h+lpData], rbx; FilenameCount
0x1800059e3  mov     [rsp+1230h+lpType], rax; Filename
0x1800059e8  xor     r8d, r8d; DriveCount
0x1800059eb  xor     edx, edx; Drive
0x1800059ed  mov     [rsp+1230h+phkResult], r12; DirCount
0x1800059f2  call    cs:__imp__wsplitpath_s
0x1800059f8  mov     [rsp+1230h+ExtCount], rbx; ExtCount
0x1800059fd  lea     rax, [rbp+1130h+String2]
0x180005a04  mov     [rsp+1230h+lpcbData], rax; Ext
0x180005a09  lea     rcx, [rbp+1130h+var_890]; FullPath
0x180005a10  lea     rax, [rbp+1130h+FullPath]
0x180005a17  mov     [rsp+1230h+lpData], rbx; FilenameCount
0x180005a1c  mov     [rsp+1230h+lpType], rax; Filename
0x180005a21  xor     r9d, r9d; Dir
0x180005a24  xor     r8d, r8d; DriveCount
0x180005a27  mov     [rsp+1230h+phkResult], r12; DirCount
0x180005a2c  xor     edx, edx; Drive
0x180005a2e  call    cs:__imp__wsplitpath_s
0x180005a34  lea     rdx, [rbp+1130h+FullPath]; String2
0x180005a3b  lea     rcx, [rbp+1130h+Filename]; String1
0x180005a42  call    cs:__imp__wcsicmp
0x180005a48  test    eax, eax
0x180005a4a  jnz     short loc_180005AB8
0x180005a4c  lea     rdx, [rbp+1130h+String2]; String2
0x180005a53  lea     rcx, [rbp+1130h+Ext]; String1
0x180005a5a  call    cs:__imp__wcsicmp
0x180005a60  test    eax, eax
0x180005a62  jnz     short loc_180005AB8
0x180005a64  mov     eax, 2
  ... truncated ...
```
