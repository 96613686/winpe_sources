# LogSecurityMessage(bool,uint)

- ea: `0x1400046bc`
- end: `0x140004a82`
- name: `?LogSecurityMessage@@YAX_NI@Z`
- size: `966`
- prototype: `void __fastcall(bool, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400043bc`

## callees

- `0x140002180`
- `0x1400046bc`
- `0x140004a90`
- `0x140004b50`
- `0x140009c70`
- `0x140009cb0`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140004a3b`
- `OLEAUT32!__imp_SysFreeString` at `0x140004a3b`
- `KERNEL32!WideCharToMultiByte` at `0x14000479f`
- `KERNEL32!WideCharToMultiByte` at `0x1400047ed`
- `KERNEL32!WideCharToMultiByte` at `0x14000479f`
- `KERNEL32!WideCharToMultiByte` at `0x1400047ed`
- `KERNEL32!GetLastError` at `0x140004818`
- `KERNEL32!GetLastError` at `0x140004818`
- `ADVAPI32!GetUserNameW` at `0x140004910`
- `ADVAPI32!GetUserNameW` at `0x140004910`
- `ADVAPI32!RegisterEventSourceW` at `0x1400048f2`
- `ADVAPI32!RegisterEventSourceW` at `0x1400048f2`
- `ADVAPI32!ReportEventW` at `0x140004a0f`
- `ADVAPI32!ReportEventW` at `0x140004a0f`
- `ADVAPI32!LookupAccountNameW` at `0x140004942`
- `ADVAPI32!LookupAccountNameW` at `0x1400049a8`
- `ADVAPI32!LookupAccountNameW` at `0x140004942`
- `ADVAPI32!LookupAccountNameW` at `0x1400049a8`
- `ADVAPI32!RegOpenKeyExA` at `0x140004810`
- `ADVAPI32!RegOpenKeyExA` at `0x140004810`
- `ADVAPI32!RegOpenKeyExW` at `0x14000474a`
- `ADVAPI32!RegOpenKeyExW` at `0x140004776`
- `ADVAPI32!RegOpenKeyExW` at `0x14000474a`
- `ADVAPI32!RegOpenKeyExW` at `0x140004776`
- `ADVAPI32!RegCloseKey` at `0x140004a4a`
- `ADVAPI32!RegCloseKey` at `0x140004a59`
- `ADVAPI32!RegCloseKey` at `0x140004a4a`
- `ADVAPI32!RegCloseKey` at `0x140004a59`
- `ADVAPI32!DeregisterEventSource` at `0x140004a18`
- `ADVAPI32!DeregisterEventSource` at `0x140004a18`

## string_xrefs

- `0x140004899`: `LogSecuritySuccesses`
- `0x1400048be`: `LogSecuritySuccesses`
- `0x14000482b`: `LogSecurityFailures`

## pseudocode

```c
void __fastcall LogSecurityMessage(char a1, unsigned int a2)
{
  unsigned __int16 *v3; // r14
  int v4; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v6; // rax
  void *v7; // rsp
  WORD v8; // si
  DWORD v9; // r12d
  WORD v10; // r13
  HKEY v11; // rdi
  HKEY v12; // rbx
  char v13; // al
  bool v14; // al
  HANDLE v15; // r15
  WCHAR *v16; // rdi
  void *v17; // rbx
  WCHAR *v18; // rax
  CHAR MultiByteStr; // [rsp+50h] [rbp+0h] BYREF
  bool v20; // [rsp+51h] [rbp+1h] BYREF
  bool v21; // [rsp+52h] [rbp+2h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp+4h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp+8h] BYREF
  _SID_NAME_USE peUse; // [rsp+5Ch] [rbp+Ch] BYREF
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+18h] BYREF
  DWORD pcbBuffer; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v28; // [rsp+74h] [rbp+24h]
  unsigned __int16 *v29; // [rsp+78h] [rbp+28h] BYREF
  LPCWSTR Strings[4]; // [rsp+80h] [rbp+30h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp+50h] BYREF

  v28 = a2;
  if ( !Global::g_fWindowsNT )
    return;
  pcbBuffer = 256;
  cchReferencedDomainName = 0;
  cbSid = 0;
  peUse = 0;
  v29 = 0;
  phkResult = 0;
  hKey = 0;
  *(_OWORD *)Strings = 0;
  v3 = 0;
  RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0, 0x20019u, &phkResult);
  if ( Global::g_fWindowsNT )
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0, 0x20019u, &hKey);
  }
  else
  {
    v4 = WideCharToMultiByte(0, 0, L"Software\\Microsoft\\Windows Script Host\\Settings", -1, 0, 0, 0, 0);
    cbMultiByte = v4;
    if ( !v4 )
      goto LABEL_9;
    v6 = v4 + 15LL;
    if ( cbMultiByte + 15 < cbMultiByte )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
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
      RegOpenKeyExA(HKEY_LOCAL_MACHINE, &MultiByteStr, 0, 0x20019u, &hKey);
    }
    else
    {
LABEL_9:
      GetLastError();
    }
  }
  v8 = 1;
  if ( a1 )
  {
    if ( CheckWSHFlag(L"LogSecurityFailures", phkResult, hKey, 1) )
    {
      v9 = -1057029144;
      v10 = 16;
      goto LABEL_24;
    }
  }
  else
  {
    v11 = phkResult;
    v12 = hKey;
    v20 = 1;
    v13 = phkResult == 0;
    v21 = 1;
    MultiByteStr = phkResult == 0;
    if ( hKey && phkResult )
    {
      GetRegSettingsBool(hKey, L"IgnoreUserSettings", (bool *)&MultiByteStr);
      v13 = MultiByteStr;
    }
    if ( v13 || (int)GetRegSettingsBool(v11, L"LogSecuritySuccesses", &v20) < 0 )
    {
      if ( !v12 || (int)GetRegSettingsBool(v12, L"LogSecuritySuccesses", &v21) < 0 )
        goto LABEL_39;
      v14 = v21;
    }
    else
    {
      v14 = v20;
    }
    if ( v14 )
    {
      v9 = 16712681;
      v10 = 8;
LABEL_24:
      v15 = RegisterEventSourceW(0, L"Windows Script Host");
      if ( v15 )
      {
        v16 = 0;
        v17 = 0;
        if ( GetUserNameW(Buffer, &pcbBuffer) )
        {
          LookupAccountNameW(0, Buffer, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
          if ( cbSid )
          {
            if ( cchReferencedDomainName )
            {
              v17 = operator new(cbSid);
              v18 = (WCHAR *)operator new(saturated_mul(cchReferencedDomainName, 2u));
              v16 = v18;
              if ( v17 )
              {
                if ( !v18 || !LookupAccountNameW(0, Buffer, v17, &cbSid, v18, &cchReferencedDomainName, &peUse) )
                {
                  operator delete(v17);
                  v17 = 0;
                }
              }
            }
          }
        }
        LoadStr(&v29, v28);
        v3 = v29;
        if ( v29 )
        {
          Strings[0] = v29;
          Strings[1] = 0;
        }
        else
        {
          Strings[0] = 0;
          v8 = 0;
        }
        ReportEventW(v15, v10, 0, v9, v17, v8, 0, Strings, 0);
        DeregisterEventSource(v15);
        if ( v17 )
          operator delete(v17);
        if ( v16 )
          operator delete(v16);
      }
    }
  }
LABEL_39:
  SysFreeString(v3);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x1400046bc  push    rbp
0x1400046be  push    rbx
0x1400046bf  push    rsi
0x1400046c0  push    rdi
0x1400046c1  push    r12
0x1400046c3  push    r13
0x1400046c5  push    r14
0x1400046c7  push    r15
0x1400046c9  sub     rsp, 2C8h
0x1400046d0  lea     rbp, [rsp+50h]
0x1400046d5  mov     rax, cs:__security_cookie
0x1400046dc  xor     rax, rbp
0x1400046df  mov     [rbp+2B0h+var_50], rax
0x1400046e6  xor     r15d, r15d
0x1400046e9  mov     [rbp+2B0h+var_28C], edx
0x1400046ec  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x1400046f3  mov     bl, cl
0x1400046f5  jz      loc_140004A5F
0x1400046fb  xorps   xmm0, xmm0
0x1400046fe  mov     [rbp+2B0h+pcbBuffer], 100h
0x140004705  lea     rax, [rbp+2B0h+var_298]
0x140004709  mov     [rbp+2B0h+cchReferencedDomainName], r15d
0x14000470d  mov     r12d, 20019h
0x140004713  mov     [rbp+2B0h+cbSid], r15d
0x140004717  lea     rsi, WideCharStr; "Software\\Microsoft\\Windows Script Hos"...
0x14000471e  mov     [rbp+2B0h+peUse], r15d
0x140004722  mov     r9d, r12d; samDesired
0x140004725  mov     [rbp+2B0h+var_288], r15
0x140004729  mov     rdx, rsi; lpSubKey
0x14000472c  mov     [rbp+2B0h+var_298], r15
0x140004730  xor     r8d, r8d; ulOptions
0x140004733  mov     [rbp+2B0h+hKey], r15
0x140004737  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000473e  mov     [rsp+300h+phkResult], rax; phkResult
0x140004743  movups  xmmword ptr [rbp+2B0h+Strings], xmm0
0x140004747  mov     r14d, r15d
0x14000474a  call    cs:__imp_RegOpenKeyExW
0x140004750  or      r13, 0FFFFFFFFFFFFFFFFh
0x140004754  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x14000475b  jz      short loc_140004781
0x14000475d  lea     rax, [rbp+2B0h+hKey]
0x140004761  mov     r9d, r12d; samDesired
0x140004764  xor     r8d, r8d; ulOptions
0x140004767  mov     [rsp+300h+phkResult], rax; phkResult
0x14000476c  mov     rdx, rsi; lpSubKey
0x14000476f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004776  call    cs:__imp_RegOpenKeyExW
0x14000477c  jmp     loc_14000481E
0x140004781  mov     [rsp+300h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x140004786  mov     r9d, r13d; cchWideChar
0x140004789  mov     [rsp+300h+lpDefaultChar], r15; lpDefaultChar
0x14000478e  mov     r8, rsi; lpWideCharStr
0x140004791  mov     [rsp+300h+cbMultiByte], r15d; cbMultiByte
0x140004796  xor     edx, edx; dwFlags
0x140004798  xor     ecx, ecx; CodePage
0x14000479a  mov     [rsp+300h+phkResult], r15; lpMultiByteStr
0x14000479f  call    cs:__imp_WideCharToMultiByte
0x1400047a5  movsxd  rdx, eax
0x1400047a8  test    eax, eax
0x1400047aa  jz      short loc_140004818
0x1400047ac  lea     rax, [rdx+0Fh]
0x1400047b0  cmp     rax, rdx
0x1400047b3  ja      short loc_1400047BF
0x1400047b5  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400047bf  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400047c3  call    _alloca_probe
0x1400047c8  sub     rsp, rax
0x1400047cb  mov     r9d, r13d; cchWideChar
0x1400047ce  mov     r8, rsi; lpWideCharStr
0x1400047d1  xor     ecx, ecx; CodePage
0x1400047d3  mov     [rsp+300h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1400047d8  lea     rdi, [rsp+300h+MultiByteStr]
0x1400047dd  mov     [rsp+300h+lpDefaultChar], r15; lpDefaultChar
0x1400047e2  mov     [rsp+300h+cbMultiByte], edx; cbMultiByte
0x1400047e6  xor     edx, edx; dwFlags
0x1400047e8  mov     [rsp+300h+phkResult], rdi; lpMultiByteStr
0x1400047ed  call    cs:__imp_WideCharToMultiByte
0x1400047f3  test    eax, eax
0x1400047f5  jz      short loc_140004818
0x1400047f7  lea     rax, [rbp+2B0h+hKey]
0x1400047fb  mov     r9d, r12d; samDesired
0x1400047fe  xor     r8d, r8d; ulOptions
0x140004801  mov     [rsp+300h+phkResult], rax; phkResult
0x140004806  mov     rdx, rdi; lpSubKey
0x140004809  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004810  call    cs:__imp_RegOpenKeyExA
0x140004816  jmp     short loc_14000481E
0x140004818  call    cs:__imp_GetLastError
0x14000481e  mov     esi, 1
0x140004823  test    bl, bl
0x140004825  jz      short loc_140004855
0x140004827  mov     r8, [rbp+2B0h+hKey]; HKEY
0x14000482b  lea     rcx, aLogsecurityfai; "LogSecurityFailures"
0x140004832  mov     rdx, [rbp+2B0h+var_298]; hKey
0x140004836  mov     r9b, sil; bool
0x140004839  call    ?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z; CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)
0x14000483e  test    al, al
0x140004840  jz      loc_140004A38
0x140004846  mov     r12d, 0C0FF03E8h
0x14000484c  lea     r13d, [rsi+0Fh]
0x140004850  jmp     loc_1400048E9
0x140004855  mov     rdi, [rbp+2B0h+var_298]
0x140004859  mov     rbx, [rbp+2B0h+hKey]
0x14000485d  test    rdi, rdi
0x140004860  mov     [rbp+2B0h+var_2AF], sil
0x140004864  setz    al
0x140004867  mov     [rbp+2B0h+var_2AE], sil
0x14000486b  mov     [rbp+2B0h+MultiByteStr], al
0x14000486e  test    rbx, rbx
0x140004871  jz      short loc_14000488E
0x140004873  test    rdi, rdi
0x140004876  jz      short loc_14000488E
0x140004878  lea     r8, [rbp+2B0h+MultiByteStr]; bool *
0x14000487c  mov     rcx, rbx; hKey
0x14000487f  lea     rdx, aIgnoreusersett; "IgnoreUserSettings"
0x140004886  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000488b  mov     al, [rbp+2B0h+MultiByteStr]
0x14000488e  test    al, al
0x140004890  jnz     short loc_1400048AE
0x140004892  lea     r8, [rbp+2B0h+var_2AF]; bool *
0x140004896  mov     rcx, rdi; hKey
0x140004899  lea     rdx, aLogsecuritysuc; "LogSecuritySuccesses"
0x1400048a0  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400048a5  test    eax, eax
0x1400048a7  js      short loc_1400048AE
0x1400048a9  mov     al, [rbp+2B0h+var_2AF]
0x1400048ac  jmp     short loc_1400048D5
0x1400048ae  test    rbx, rbx
0x1400048b1  jz      loc_140004A38
0x1400048b7  lea     r8, [rbp+2B0h+var_2AE]; bool *
0x1400048bb  mov     rcx, rbx; hKey
0x1400048be  lea     rdx, aLogsecuritysuc; "LogSecuritySuccesses"
0x1400048c5  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x1400048ca  test    eax, eax
0x1400048cc  js      loc_140004A38
0x1400048d2  mov     al, [rbp+2B0h+var_2AE]
0x1400048d5  test    al, al
0x1400048d7  jz      loc_140004A38
0x1400048dd  mov     r12d, 0FF03E9h
0x1400048e3  mov     r13d, 8
0x1400048e9  lea     rdx, SourceName; "Windows Script Host"
0x1400048f0  xor     ecx, ecx; lpUNCServerName
0x1400048f2  call    cs:__imp_RegisterEventSourceW
0x1400048f8  mov     r15, rax
0x1400048fb  test    rax, rax
0x1400048fe  jz      loc_140004A38
0x140004904  lea     rdx, [rbp+2B0h+pcbBuffer]; pcbBuffer
0x140004908  xor     edi, edi
0x14000490a  lea     rcx, [rbp+2B0h+Buffer]; lpBuffer
0x14000490e  xor     ebx, ebx
0x140004910  call    cs:__imp_GetUserNameW
0x140004916  test    eax, eax
0x140004918  jz      loc_1400049BC
0x14000491e  lea     rax, [rbp+2B0h+peUse]
0x140004922  xor     r8d, r8d; Sid
0x140004925  mov     [rsp+300h+lpDefaultChar], rax; peUse
0x14000492a  lea     r9, [rbp+2B0h+cbSid]; cbSid
0x14000492e  lea     rax, [rbp+2B0h+cchReferencedDomainName]
0x140004932  xor     ecx, ecx; lpSystemName
0x140004934  mov     qword ptr [rsp+300h+cbMultiByte], rax; cchReferencedDomainName
0x140004939  lea     rdx, [rbp+2B0h+Buffer]; lpAccountName
0x14000493d  mov     [rsp+300h+phkResult], rbx; ReferencedDomainName
0x140004942  call    cs:__imp_LookupAccountNameW
0x140004948  mov     eax, [rbp+2B0h+cbSid]
0x14000494b  test    eax, eax
0x14000494d  jz      short loc_1400049BC
0x14000494f  cmp     [rbp+2B0h+cchReferencedDomainName], ebx
0x140004952  jbe     short loc_1400049BC
0x140004954  mov     ecx, eax; Size
0x140004956  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000495b  mov     ecx, [rbp+2B0h+cchReferencedDomainName]
0x14000495e  mov     rbx, rax
0x140004961  lea     eax, [rdi+2]
0x140004964  mul     rcx
0x140004967  lea     rcx, [rdi-1]
0x14000496b  cmovb   rax, rcx
0x14000496f  mov     rcx, rax; Size
0x140004972  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004977  mov     rdi, rax
0x14000497a  test    rbx, rbx
0x14000497d  jz      short loc_1400049BC
0x14000497f  test    rax, rax
0x140004982  jz      short loc_1400049B2
0x140004984  lea     rax, [rbp+2B0h+peUse]
0x140004988  mov     r8, rbx; Sid
0x14000498b  mov     [rsp+300h+lpDefaultChar], rax; peUse
0x140004990  lea     r9, [rbp+2B0h+cbSid]; cbSid
0x140004994  lea     rax, [rbp+2B0h+cchReferencedDomainName]
0x140004998  xor     ecx, ecx; lpSystemName
0x14000499a  mov     qword ptr [rsp+300h+cbMultiByte], rax; cchReferencedDomainName
0x14000499f  lea     rdx, [rbp+2B0h+Buffer]; lpAccountName
0x1400049a3  mov     [rsp+300h+phkResult], rdi; ReferencedDomainName
0x1400049a8  call    cs:__imp_LookupAccountNameW
0x1400049ae  test    eax, eax
0x1400049b0  jnz     short loc_1400049BC
0x1400049b2  mov     rcx, rbx; Block
0x1400049b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400049ba  xor     ebx, ebx
0x1400049bc  mov     edx, [rbp+2B0h+var_28C]; unsigned int
0x1400049bf  lea     rcx, [rbp+2B0h+var_288]; unsigned __int16 **
0x1400049c3  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x1400049c8  mov     r14, [rbp+2B0h+var_288]
0x1400049cc  test    r14, r14
0x1400049cf  jnz     short loc_1400049D9
0x1400049d1  mov     [rbp+2B0h+Strings], r14
0x1400049d5  xor     esi, esi
0x1400049d7  jmp     short loc_1400049E5
0x1400049d9  mov     [rbp+2B0h+Strings], r14
0x1400049dd  mov     [rbp+2B0h+Strings+8], 0
0x1400049e5  xor     r8d, r8d; wCategory
0x1400049e8  lea     rax, [rbp+2B0h+Strings]
0x1400049ec  mov     [rsp+300h+lpRawData], r8; lpRawData
0x1400049f1  mov     r9d, r12d; dwEventID
0x1400049f4  mov     [rsp+300h+lpUsedDefaultChar], rax; lpStrings
0x1400049f9  movzx   edx, r13w; wType
0x1400049fd  mov     dword ptr [rsp+300h+lpDefaultChar], r8d; dwDataSize
0x140004a02  mov     rcx, r15; hEventLog
0x140004a05  mov     word ptr [rsp+300h+cbMultiByte], si; wNumStrings
0x140004a0a  mov     [rsp+300h+phkResult], rbx; lpUserSid
0x140004a0f  call    cs:__imp_ReportEventW
0x140004a15  mov     rcx, r15; hEventLog
0x140004a18  call    cs:__imp_DeregisterEventSource
0x140004a1e  test    rbx, rbx
0x140004a21  jz      short loc_140004A2B
0x140004a23  mov     rcx, rbx; Block
0x140004a26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004a2b  test    rdi, rdi
0x140004a2e  jz      short loc_140004A38
0x140004a30  mov     rcx, rdi; Block
0x140004a33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004a38  mov     rcx, r14; bstrString
0x140004a3b  call    cs:__imp_SysFreeString
0x140004a41  mov     rcx, [rbp+2B0h+hKey]; hKey
0x140004a45  test    rcx, rcx
0x140004a48  jz      short loc_140004A50
0x140004a4a  call    cs:__imp_RegCloseKey
0x140004a50  mov     rcx, [rbp+2B0h+var_298]; hKey
0x140004a54  test    rcx, rcx
0x140004a57  jz      short loc_140004A5F
0x140004a59  call    cs:__imp_RegCloseKey
0x140004a5f  mov     rcx, [rbp+2B0h+var_50]
0x140004a66  xor     rcx, rbp; StackCookie
0x140004a69  call    __security_check_cookie
0x140004a6e  lea     rsp, [rbp+278h]
0x140004a75  pop     r15
0x140004a77  pop     r14
0x140004a79  pop     r13
0x140004a7b  pop     r12
0x140004a7d  pop     rdi
0x140004a7e  pop     rsi
0x140004a7f  pop     rbx
0x140004a80  pop     rbp
0x140004a81  retn
```
