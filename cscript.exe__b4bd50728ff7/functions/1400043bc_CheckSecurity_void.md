# CheckSecurity(void)

- ea: `0x1400043bc`
- end: `0x1400046b3`
- name: `?CheckSecurity@@YAJXZ`
- size: `759`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400034b4`

## callees

- `0x1400043bc`
- `0x1400046bc`
- `0x140004b50`
- `0x14000d480`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x14000444b`
- `KERNEL32!WideCharToMultiByte` at `0x140004492`
- `KERNEL32!WideCharToMultiByte` at `0x140004513`
- `KERNEL32!WideCharToMultiByte` at `0x14000455a`
- `KERNEL32!WideCharToMultiByte` at `0x14000444b`
- `KERNEL32!WideCharToMultiByte` at `0x140004492`
- `KERNEL32!WideCharToMultiByte` at `0x140004513`
- `KERNEL32!WideCharToMultiByte` at `0x14000455a`
- `KERNEL32!GetLastError` at `0x1400044c0`
- `KERNEL32!GetLastError` at `0x140004588`
- `KERNEL32!GetLastError` at `0x1400044c0`
- `KERNEL32!GetLastError` at `0x140004588`
- `ole32!CoInitializeSecurity` at `0x140004657`
- `ole32!CoInitializeSecurity` at `0x140004657`
- `ADVAPI32!RegOpenKeyExA` at `0x1400044b8`
- `ADVAPI32!RegOpenKeyExA` at `0x140004580`
- `ADVAPI32!RegOpenKeyExA` at `0x1400044b8`
- `ADVAPI32!RegOpenKeyExA` at `0x140004580`
- `ADVAPI32!RegOpenKeyExW` at `0x140004423`
- `ADVAPI32!RegOpenKeyExW` at `0x1400044eb`
- `ADVAPI32!RegOpenKeyExW` at `0x140004423`
- `ADVAPI32!RegOpenKeyExW` at `0x1400044eb`
- `ADVAPI32!RegCloseKey` at `0x140004668`
- `ADVAPI32!RegCloseKey` at `0x140004677`
- `ADVAPI32!RegCloseKey` at `0x140004668`
- `ADVAPI32!RegCloseKey` at `0x140004677`

## pseudocode

```c
__int64 CheckSecurity(void)
{
  int v0; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v2; // rax
  void *v3; // rsp
  int v4; // eax
  unsigned __int64 v5; // rdx
  __int64 v6; // rax
  void *v7; // rsp
  HKEY v8; // rdi
  HKEY v9; // rbx
  char v10; // al
  bool v11; // al
  HRESULT v12; // eax
  int v13; // ebx
  CHAR MultiByteStr; // [rsp+50h] [rbp+0h] BYREF
  bool v16; // [rsp+51h] [rbp+1h] BYREF
  bool v17; // [rsp+52h] [rbp+2h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  HKEY phkResult[2]; // [rsp+60h] [rbp+10h] BYREF

  phkResult[0] = 0;
  hKey = 0;
  if ( Global::g_fWindowsNT )
  {
    RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0, 0x20019u, phkResult);
  }
  else
  {
    v0 = WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, 0, 0, 0, 0);
    cbMultiByte = v0;
    if ( !v0 )
      goto LABEL_8;
    v2 = v0 + 15LL;
    if ( cbMultiByte + 15 < cbMultiByte )
      v2 = 0xFFFFFFFFFFFFFF0LL;
    v3 = alloca(v2 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( WideCharToMultiByte(
           0,
           0,
           L"Software\\Microsoft\\Windows Script Host\\Settings",
           -1,
           &MultiByteStr,
           cbMultiByte,
           0,
           0) )
    {
      RegOpenKeyExA(HKEY_CURRENT_USER, &MultiByteStr, 0, 0x20019u, phkResult);
    }
    else
    {
LABEL_8:
      GetLastError();
    }
  }
  if ( Global::g_fWindowsNT )
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0, 0x20019u, &hKey);
  }
  else
  {
    v4 = WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, 0, 0, 0, 0);
    v5 = v4;
    if ( !v4 )
      goto LABEL_16;
    v6 = v4 + 15LL;
    if ( v5 + 15 < v5 )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, &MultiByteStr, v5, 0, 0) )
      RegOpenKeyExA(HKEY_LOCAL_MACHINE, &MultiByteStr, 0, 0x20019u, &hKey);
    else
LABEL_16:
      GetLastError();
  }
  v8 = phkResult[0];
  v9 = hKey;
  v16 = 1;
  v10 = phkResult[0] == 0;
  v17 = 1;
  MultiByteStr = phkResult[0] == 0;
  if ( hKey && phkResult[0] )
  {
    GetRegSettingsBool(hKey, L"IgnoreUserSettings", (bool *)&MultiByteStr);
    v10 = MultiByteStr;
  }
  if ( v10 || (int)GetRegSettingsBool(v8, L"Enabled", &v16) < 0 )
  {
    if ( !v9 || (int)GetRegSettingsBool(v9, L"Enabled", &v17) < 0 )
      goto LABEL_28;
    v11 = v17;
  }
  else
  {
    v11 = v16;
  }
  if ( !v11 )
  {
    v12 = CHost::ReportError(g_pHost, Global::g_lResourceBase + 20, 0xC88u);
    goto LABEL_30;
  }
LABEL_28:
  v13 = 0;
  if ( !Global::g_fWindowsNT )
    goto LABEL_31;
  v12 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
LABEL_30:
  v13 = v12;
LABEL_31:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  LogSecurityMessage(v13 < 0, ((v13 >> 31) & 0x9B) + 3054);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400043bc  push    rbp
0x1400043be  push    rbx
0x1400043bf  push    rsi
0x1400043c0  push    rdi
0x1400043c1  push    r12
0x1400043c3  push    r15
0x1400043c5  sub     rsp, 88h
0x1400043cc  lea     rbp, [rsp+50h]
0x1400043d1  mov     rax, cs:__security_cookie
0x1400043d8  xor     rax, rbp
0x1400043db  mov     [rbp+60h+var_40], rax
0x1400043df  xor     esi, esi
0x1400043e1  lea     rbx, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x1400043e8  or      r15d, 0FFFFFFFFh
0x1400043ec  mov     [rbp+60h+var_50], rsi
0x1400043f0  cmp     cs:?g_fWindowsNT@Global@@2_NA, sil; bool Global::g_fWindowsNT
0x1400043f7  mov     r12, 0FFFFFFFFFFFFFF0h
0x140004401  mov     [rbp+60h+hKey], rsi
0x140004405  jz      short loc_14000442E
0x140004407  lea     rax, [rbp+60h+var_50]
0x14000440b  mov     r9d, 20019h; samDesired
0x140004411  xor     r8d, r8d; ulOptions
0x140004414  mov     [rsp+0B0h+phkResult], rax; phkResult
0x140004419  mov     rdx, rbx; lpSubKey
0x14000441c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140004423  call    cs:__imp_RegOpenKeyExW
0x140004429  jmp     loc_1400044C6
0x14000442e  mov     [rsp+0B0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x140004433  mov     r9d, r15d; cchWideChar
0x140004436  mov     [rsp+0B0h+lpDefaultChar], rsi; lpDefaultChar
0x14000443b  mov     r8, rbx; lpWideCharStr
0x14000443e  mov     [rsp+0B0h+cbMultiByte], esi; cbMultiByte
0x140004442  xor     edx, edx; dwFlags
0x140004444  xor     ecx, ecx; CodePage
0x140004446  mov     [rsp+0B0h+phkResult], rsi; lpMultiByteStr
0x14000444b  call    cs:__imp_WideCharToMultiByte
0x140004451  movsxd  rdx, eax
0x140004454  test    eax, eax
0x140004456  jz      short loc_1400044C0
0x140004458  lea     rax, [rdx+0Fh]
0x14000445c  cmp     rax, rdx
0x14000445f  ja      short loc_140004464
0x140004461  mov     rax, r12
0x140004464  and     rax, 0FFFFFFFFFFFFFFF0h
0x140004468  call    _alloca_probe
0x14000446d  sub     rsp, rax
0x140004470  mov     r9d, r15d; cchWideChar
0x140004473  mov     r8, rbx; lpWideCharStr
0x140004476  xor     ecx, ecx; CodePage
0x140004478  mov     [rsp+0B0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x14000447d  lea     rdi, [rsp+0B0h+MultiByteStr]
0x140004482  mov     [rsp+0B0h+lpDefaultChar], rsi; lpDefaultChar
0x140004487  mov     [rsp+0B0h+cbMultiByte], edx; cbMultiByte
0x14000448b  xor     edx, edx; dwFlags
0x14000448d  mov     [rsp+0B0h+phkResult], rdi; lpMultiByteStr
0x140004492  call    cs:__imp_WideCharToMultiByte
0x140004498  test    eax, eax
0x14000449a  jz      short loc_1400044C0
0x14000449c  lea     rax, [rbp+60h+var_50]
0x1400044a0  mov     r9d, 20019h; samDesired
0x1400044a6  xor     r8d, r8d; ulOptions
0x1400044a9  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1400044ae  mov     rdx, rdi; lpSubKey
0x1400044b1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400044b8  call    cs:__imp_RegOpenKeyExA
0x1400044be  jmp     short loc_1400044C6
0x1400044c0  call    cs:__imp_GetLastError
0x1400044c6  cmp     cs:?g_fWindowsNT@Global@@2_NA, sil; bool Global::g_fWindowsNT
0x1400044cd  jz      short loc_1400044F6
0x1400044cf  lea     rax, [rbp+60h+hKey]
0x1400044d3  mov     r9d, 20019h; samDesired
0x1400044d9  xor     r8d, r8d; ulOptions
0x1400044dc  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1400044e1  mov     rdx, rbx; lpSubKey
0x1400044e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400044eb  call    cs:__imp_RegOpenKeyExW
0x1400044f1  jmp     loc_14000458E
0x1400044f6  mov     [rsp+0B0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x1400044fb  mov     r9d, r15d; cchWideChar
0x1400044fe  mov     [rsp+0B0h+lpDefaultChar], rsi; lpDefaultChar
0x140004503  mov     r8, rbx; lpWideCharStr
0x140004506  mov     [rsp+0B0h+cbMultiByte], esi; cbMultiByte
0x14000450a  xor     edx, edx; dwFlags
0x14000450c  xor     ecx, ecx; CodePage
0x14000450e  mov     [rsp+0B0h+phkResult], rsi; lpMultiByteStr
0x140004513  call    cs:__imp_WideCharToMultiByte
0x140004519  movsxd  rdx, eax
0x14000451c  test    eax, eax
0x14000451e  jz      short loc_140004588
0x140004520  lea     rax, [rdx+0Fh]
0x140004524  cmp     rax, rdx
0x140004527  ja      short loc_14000452C
0x140004529  mov     rax, r12
0x14000452c  and     rax, 0FFFFFFFFFFFFFFF0h
0x140004530  call    _alloca_probe
0x140004535  sub     rsp, rax
0x140004538  mov     r9d, r15d; cchWideChar
0x14000453b  mov     r8, rbx; lpWideCharStr
0x14000453e  xor     ecx, ecx; CodePage
0x140004540  mov     [rsp+0B0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x140004545  lea     rdi, [rsp+0B0h+MultiByteStr]
0x14000454a  mov     [rsp+0B0h+lpDefaultChar], rsi; lpDefaultChar
0x14000454f  mov     [rsp+0B0h+cbMultiByte], edx; cbMultiByte
0x140004553  xor     edx, edx; dwFlags
0x140004555  mov     [rsp+0B0h+phkResult], rdi; lpMultiByteStr
0x14000455a  call    cs:__imp_WideCharToMultiByte
0x140004560  test    eax, eax
0x140004562  jz      short loc_140004588
0x140004564  lea     rax, [rbp+60h+hKey]
0x140004568  mov     r9d, 20019h; samDesired
0x14000456e  xor     r8d, r8d; ulOptions
0x140004571  mov     [rsp+0B0h+phkResult], rax; phkResult
0x140004576  mov     rdx, rdi; lpSubKey
0x140004579  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004580  call    cs:__imp_RegOpenKeyExA
0x140004586  jmp     short loc_14000458E
0x140004588  call    cs:__imp_GetLastError
0x14000458e  mov     rdi, [rbp+60h+var_50]
0x140004592  mov     rbx, [rbp+60h+hKey]
0x140004596  test    rdi, rdi
0x140004599  mov     [rbp+60h+var_5F], 1
0x14000459d  setz    al
0x1400045a0  mov     [rbp+60h+var_5E], 1
0x1400045a4  mov     [rbp+60h+MultiByteStr], al
0x1400045a7  test    rbx, rbx
0x1400045aa  jz      short loc_1400045C7
0x1400045ac  test    rdi, rdi
0x1400045af  jz      short loc_1400045C7
0x1400045b1  lea     r8, [rbp+60h+MultiByteStr]; bool *
0x1400045b5  mov     rcx, rbx; hKey
0x1400045b8  lea     rdx, aIgnoreusersett; "IgnoreUserSettings"
0x1400045bf  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400045c4  mov     al, [rbp+60h+MultiByteStr]
0x1400045c7  test    al, al
0x1400045c9  jnz     short loc_1400045E7
0x1400045cb  lea     r8, [rbp+60h+var_5F]; bool *
0x1400045cf  mov     rcx, rdi; hKey
0x1400045d2  lea     rdx, aEnabled; "Enabled"
0x1400045d9  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400045de  test    eax, eax
0x1400045e0  js      short loc_1400045E7
0x1400045e2  mov     al, [rbp+60h+var_5F]
0x1400045e5  jmp     short loc_140004606
0x1400045e7  test    rbx, rbx
0x1400045ea  jz      short loc_140004627
0x1400045ec  lea     r8, [rbp+60h+var_5E]; bool *
0x1400045f0  mov     rcx, rbx; hKey
0x1400045f3  lea     rdx, aEnabled; "Enabled"
0x1400045fa  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400045ff  test    eax, eax
0x140004601  js      short loc_140004627
0x140004603  mov     al, [rbp+60h+var_5E]
0x140004606  test    al, al
0x140004608  jnz     short loc_140004627
0x14000460a  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140004610  mov     r8d, 0C88h; unsigned int
0x140004616  mov     rcx, cs:?g_pHost@@3PEAVCHost@@EA; this
0x14000461d  add     edx, 14h; unsigned int
0x140004620  call    ?ReportError@CHost@@QEAAJII@Z; CHost::ReportError(uint,uint)
0x140004625  jmp     short loc_14000465D
0x140004627  cmp     cs:?g_fWindowsNT@Global@@2_NA, sil; bool Global::g_fWindowsNT
0x14000462e  mov     ebx, esi
0x140004630  jz      short loc_14000465F
0x140004632  mov     [rsp+0B0h+pReserved3], rsi; pReserved3
0x140004637  xor     r9d, r9d; pReserved1
0x14000463a  mov     dword ptr [rsp+0B0h+lpUsedDefaultChar], esi; dwCapabilities
0x14000463e  xor     r8d, r8d; asAuthSvc
0x140004641  mov     [rsp+0B0h+lpDefaultChar], rsi; pAuthList
0x140004646  mov     edx, r15d; cAuthSvc
0x140004649  mov     [rsp+0B0h+cbMultiByte], 3; dwImpLevel
0x140004651  xor     ecx, ecx; pSecDesc
0x140004653  mov     dword ptr [rsp+0B0h+phkResult], esi; dwAuthnLevel
0x140004657  call    cs:__imp_CoInitializeSecurity
0x14000465d  mov     ebx, eax
0x14000465f  mov     rcx, [rbp+60h+hKey]; hKey
0x140004663  test    rcx, rcx
0x140004666  jz      short loc_14000466E
0x140004668  call    cs:__imp_RegCloseKey
0x14000466e  mov     rcx, [rbp+60h+var_50]; hKey
0x140004672  test    rcx, rcx
0x140004675  jz      short loc_14000467D
0x140004677  call    cs:__imp_RegCloseKey
0x14000467d  mov     edx, ebx
0x14000467f  mov     ecx, ebx
0x140004681  sar     edx, 1Fh
0x140004684  and     edx, 9Bh
0x14000468a  shr     ecx, 1Fh; bool
0x14000468d  add     edx, 0BEEh; unsigned int
0x140004693  call    ?LogSecurityMessage@@YAX_NI@Z; LogSecurityMessage(bool,uint)
0x140004698  mov     eax, ebx
0x14000469a  mov     rcx, [rbp+60h+var_40]
0x14000469e  xor     rcx, rbp; StackCookie
0x1400046a1  call    __security_check_cookie
0x1400046a6  lea     rsp, [rbp+38h]
0x1400046aa  pop     r15
0x1400046ac  pop     r12
0x1400046ae  pop     rdi
0x1400046af  pop     rsi
0x1400046b0  pop     rbx
0x1400046b1  pop     rbp
0x1400046b2  retn
```
