# DsrHKeyUserHandle::ReadHKeyUserInfo(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,DsrHKeyUserHandle &)

- ea: `0x1800394a8`
- end: `0x180039939`
- name: `?ReadHKeyUserInfo@DsrHKeyUserHandle@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV1@@Z`
- size: `1169`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR StringSid)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b9ab0`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012cf0`
- `0x18001378c`
- `0x180016190`
- `0x180016ae0`
- `0x180016b90`
- `0x1800292ac`
- `0x180029554`
- `0x18002b9b4`
- `0x18003334c`
- `0x1800394a8`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039748`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800398ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800398dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800398ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800398dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039535`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039535`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003959b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039662`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800396aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800397f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003959b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039662`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800396aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800397f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800398ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800398ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003973a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003973a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039712`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039712`

## string_xrefs

- `0x18003954f`: `RegOpenKeyExW`
- `0x180039765`: `ConvertSidToStringSidW`
- `0x18003958f`: `ProfileImagePath`
- `0x1800395ec`: `ProfileImagePath`
- `0x180039656`: `ProfileImagePath`
- `0x180039556`: `DsrHKeyUserHandle::ReadHKeyUserInfo`
- `0x1800395f3`: `DsrHKeyUserHandle::ReadHKeyUserInfo`
- `0x18003961f`: `DsrHKeyUserHandle::ReadHKeyUserInfo`
- `0x1800396bb`: `DsrHKeyUserHandle::ReadHKeyUserInfo`
- `0x1800397ac`: `%s: Unexpected type found while reading sid value from %s\%s.`
- `0x1800396f2`: `%s: Sid value is not present at %s\%s. Falling back to checking if '%s' is a SID.`
- `0x1800395b8`: `RegQueryValueExW(REG_PROFILE_PATH_VALUE)`
- `0x180039722`: `RegQueryValueExW(REG_SID_VALUE)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DsrHKeyUserHandle::ReadHKeyUserInfo(HKEY hKey, LPCWSTR StringSid, __int64 a3)
{
  BYTE *v6; // r15
  BYTE *v7; // r14
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  signed int v10; // ebx
  const wchar_t *v11; // r8
  __int64 v12; // r9
  int v13; // eax
  LPCWSTR v14; // rax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  LPCWSTR v17; // rax
  LPCWSTR v18; // r9
  const WCHAR *v19; // rcx
  PSID v20; // rcx
  signed int LastError; // eax
  int v22; // eax
  LPCWSTR v23; // r9
  LSTATUS v24; // eax
  _QWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSida; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v34[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[232]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v36[4]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v37[32]; // [rsp+160h] [rbp+60h] BYREF

  hKeya = 0;
  Type = 1;
  cbData = 0;
  v6 = 0;
  StringSida = 0;
  v7 = 0;
  Sid = 0;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v34);
  if ( *((_QWORD *)StringSid + 3) <= 7u )
    v8 = StringSid;
  else
    v8 = *(const WCHAR **)StringSid;
  v9 = RegOpenKeyExW(hKey, v8, 0, 0x20019u, &hKeya);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
  {
    v11 = L"RegOpenKeyExW";
LABEL_8:
    v12 = (unsigned int)v10;
LABEL_9:
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"DsrHKeyUserHandle::ReadHKeyUserInfo", v11, v12);
    goto LABEL_62;
  }
  v13 = RegQueryValueExW(hKeya, L"ProfileImagePath", 0, &Type, 0, &cbData);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  v10 = 0;
  if ( v13 != -2147024662 )
    v10 = v13;
  if ( v10 < 0 )
  {
LABEL_15:
    v11 = L"RegQueryValueExW(REG_PROFILE_PATH_VALUE)";
    goto LABEL_8;
  }
  if ( Type - 1 > 1 )
  {
    v10 = -2147024809;
    if ( *((_QWORD *)StringSid + 3) <= 7u )
      v14 = StringSid;
    else
      v14 = *(LPCWSTR *)StringSid;
    Logger::TraceError(
      L"%s: Unexpected type of value '%s' found at %s\\%s.",
      L"DsrHKeyUserHandle::ReadHKeyUserInfo",
      L"ProfileImagePath",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
      v14);
    goto LABEL_62;
  }
  v6 = (BYTE *)SafeAlloc(cbData);
  if ( !v6 )
  {
LABEL_22:
    v10 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DsrHKeyUserHandle::ReadHKeyUserInfo");
    goto LABEL_62;
  }
  v15 = RegQueryValueExW(hKeya, L"ProfileImagePath", 0, &Type, v6, &cbData);
  v10 = v15;
  if ( v15 > 0 )
    v10 = (unsigned __int16)v15 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_15;
  cbData = 0;
  v16 = RegQueryValueExW(hKeya, L"Sid", 0, &Type, 0, &cbData);
  v10 = v16;
  if ( v16 > 0 )
    v10 = (unsigned __int16)v16 | 0x80070000;
  if ( v10 == -2147024894 )
  {
    if ( *((_QWORD *)StringSid + 3) <= 7u )
    {
      v17 = StringSid;
      v18 = StringSid;
    }
    else
    {
      v17 = *(LPCWSTR *)StringSid;
      v18 = *(LPCWSTR *)StringSid;
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: Sid value is not present at %s\\%s. Falling back to checking if '%s' is a SID.",
      L"DsrHKeyUserHandle::ReadHKeyUserInfo",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
      v18,
      v17);
    if ( *((_QWORD *)StringSid + 3) <= 7u )
      v19 = StringSid;
    else
      v19 = *(const WCHAR **)StringSid;
    if ( !ConvertStringSidToSidW(v19, &Sid) )
    {
      v12 = 2147942402LL;
LABEL_37:
      v11 = L"RegQueryValueExW(REG_SID_VALUE)";
      goto LABEL_9;
    }
    v10 = 0;
    v20 = Sid;
  }
  else
  {
    v22 = 0;
    if ( v10 != -2147024662 )
      v22 = v10;
    v10 = v22;
    if ( v22 < 0 )
    {
      v12 = (unsigned int)v22;
      goto LABEL_37;
    }
    if ( Type != 3 )
    {
      v10 = -2147024809;
      if ( *((_QWORD *)StringSid + 3) <= 7u )
        v23 = StringSid;
      else
        v23 = *(LPCWSTR *)StringSid;
      Logger::TraceError(
        L"%s: Unexpected type found while reading sid value from %s\\%s.",
        L"DsrHKeyUserHandle::ReadHKeyUserInfo",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
        v23);
      goto LABEL_62;
    }
    v7 = (BYTE *)SafeAlloc(cbData);
    if ( !v7 )
      goto LABEL_22;
    v24 = RegQueryValueExW(hKeya, L"Sid", 0, &Type, v7, &cbData);
    v10 = v24;
    if ( v24 > 0 )
      v10 = (unsigned __int16)v24 | 0x80070000;
    if ( v10 < 0 )
    {
      v12 = (unsigned int)v10;
      goto LABEL_37;
    }
    v20 = v7;
  }
  if ( !ConvertSidToStringSidW(v20, &StringSida) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
    {
      v11 = L"ConvertSidToStringSidW";
      goto LABEL_8;
    }
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v34, (__int64)v6);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v34, (__int64)L"\\NtUser.dat");
  std::basic_stringbuf<unsigned short>::str(v35, v36);
  v25 = v36;
  if ( v36[3] > 7u )
    v25 = (_QWORD *)v36[0];
  v26 = std::wstring::wstring((__int64)v37, (__int64)v25);
  std::wstring::operator=(a3 + 48, v26);
  std::wstring::_Tidy_deallocate((__int64)v37);
  std::wstring::_Tidy_deallocate((__int64)v36);
  v27 = std::wstring::wstring((__int64)v37, (__int64)StringSida);
  std::wstring::operator=(a3 + 16, v27);
  std::wstring::_Tidy_deallocate((__int64)v37);
LABEL_62:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  SafeFree(v7);
  LocalFree(StringSida);
  SafeFree(v6);
  LocalFree(Sid);
  if ( *((_QWORD *)StringSid + 3) > 7u )
    StringSid = *(LPCWSTR *)StringSid;
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x. %s: %s.",
    L"DsrHKeyUserHandle::ReadHKeyUserInfo",
    (unsigned int)v10,
    L"profileName",
    StringSid);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800394a8  push    rbp
0x1800394aa  push    rbx
0x1800394ab  push    rsi
0x1800394ac  push    rdi
0x1800394ad  push    r13
0x1800394af  push    r14
0x1800394b1  push    r15
0x1800394b3  lea     rbp, [rsp-90h]
0x1800394bb  sub     rsp, 190h
0x1800394c2  mov     rax, cs:__security_cookie
0x1800394c9  xor     rax, rsp
0x1800394cc  mov     [rbp+0C0h+var_40], rax
0x1800394d3  mov     r13, r8
0x1800394d6  mov     rdi, rdx
0x1800394d9  mov     rbx, rcx
0x1800394dc  mov     [rsp+1C0h+hKey], 0
0x1800394e5  mov     [rsp+1C0h+Type], 1
0x1800394ed  mov     [rsp+1C0h+cbData], 0
0x1800394f5  xor     r15d, r15d
0x1800394f8  mov     [rsp+1C0h+StringSid], r15
0x1800394fd  xor     r14d, r14d
0x180039500  mov     [rsp+1C0h+Sid], r14
0x180039505  lea     rcx, [rsp+1C0h+var_170]
0x18003950a  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18003950f  nop
0x180039510  cmp     qword ptr [rdi+18h], 7
0x180039515  jbe     short loc_18003951C
0x180039517  mov     rdx, [rdi]
0x18003951a  jmp     short loc_18003951F
0x18003951c  mov     rdx, rdi; lpSubKey
0x18003951f  lea     rax, [rsp+1C0h+hKey]
0x180039524  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180039529  mov     r9d, 20019h; samDesired
0x18003952f  xor     r8d, r8d; ulOptions
0x180039532  mov     rcx, rbx; hKey
0x180039535  call    cs:__imp_RegOpenKeyExW
0x18003953b  mov     ebx, eax
0x18003953d  mov     esi, 80070000h
0x180039542  test    eax, eax
0x180039544  jle     short loc_18003954B
0x180039546  movzx   ebx, ax
0x180039549  or      ebx, esi
0x18003954b  test    ebx, ebx
0x18003954d  jns     short loc_180039574
0x18003954f  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x180039556  lea     rsi, aDsrhkeyuserhan_4; "DsrHKeyUserHandle::ReadHKeyUserInfo"
0x18003955d  mov     r9d, ebx
0x180039560  mov     rdx, rsi
0x180039563  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003956a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003956f  jmp     loc_1800398A4
0x180039574  lea     rax, [rsp+1C0h+cbData]
0x180039579  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18003957e  mov     [rsp+1C0h+phkResult], 0; lpData
0x180039587  lea     r9, [rsp+1C0h+Type]; lpType
0x18003958c  xor     r8d, r8d; lpReserved
0x18003958f  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x180039596  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18003959b  call    cs:__imp_RegQueryValueExW
0x1800395a1  test    eax, eax
0x1800395a3  jle     short loc_1800395AA
0x1800395a5  movzx   eax, ax
0x1800395a8  or      eax, esi
0x1800395aa  xor     ebx, ebx
0x1800395ac  cmp     eax, 800700EAh
0x1800395b1  cmovnz  ebx, eax
0x1800395b4  test    ebx, ebx
0x1800395b6  jns     short loc_1800395C1
0x1800395b8  lea     r8, aRegqueryvaluee_1; "RegQueryValueExW(REG_PROFILE_PATH_VALUE"...
0x1800395bf  jmp     short loc_180039556
0x1800395c1  mov     eax, [rsp+1C0h+Type]
0x1800395c5  dec     eax
0x1800395c7  cmp     eax, 1
0x1800395ca  jbe     short loc_18003960E
0x1800395cc  mov     ebx, 80070057h
0x1800395d1  cmp     qword ptr [rdi+18h], 7
0x1800395d6  jbe     short loc_1800395DD
0x1800395d8  mov     rax, [rdi]
0x1800395db  jmp     short loc_1800395E0
0x1800395dd  mov     rax, rdi
0x1800395e0  mov     [rsp+1C0h+phkResult], rax
0x1800395e5  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800395ec  lea     r8, aProfileimagepa; "ProfileImagePath"
0x1800395f3  lea     rsi, aDsrhkeyuserhan_4; "DsrHKeyUserHandle::ReadHKeyUserInfo"
0x1800395fa  mov     rdx, rsi
0x1800395fd  lea     rcx, aSUnexpectedTyp_0; "%s: Unexpected type of value '%s' found"...
0x180039604  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180039609  jmp     loc_1800398A4
0x18003960e  mov     ecx, [rsp+1C0h+cbData]; unsigned __int64
0x180039612  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180039617  mov     r15, rax
0x18003961a  test    rax, rax
0x18003961d  jnz     short loc_18003963F
0x18003961f  lea     rsi, aDsrhkeyuserhan_4; "DsrHKeyUserHandle::ReadHKeyUserInfo"
0x180039626  mov     ebx, 8007000Eh
0x18003962b  mov     rdx, rsi
0x18003962e  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180039635  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18003963a  jmp     loc_1800398A4
0x18003963f  lea     rax, [rsp+1C0h+cbData]
0x180039644  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x180039649  mov     [rsp+1C0h+phkResult], r15; lpData
0x18003964e  lea     r9, [rsp+1C0h+Type]; lpType
0x180039653  xor     r8d, r8d; lpReserved
0x180039656  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18003965d  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180039662  call    cs:__imp_RegQueryValueExW
0x180039668  mov     ebx, eax
0x18003966a  test    eax, eax
0x18003966c  jle     short loc_180039673
0x18003966e  movzx   ebx, ax
0x180039671  or      ebx, esi
0x180039673  test    ebx, ebx
0x180039675  js      loc_1800395B8
0x18003967b  mov     [rsp+1C0h+cbData], 0
0x180039683  lea     rax, [rsp+1C0h+cbData]
0x180039688  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18003968d  mov     [rsp+1C0h+phkResult], 0; lpData
0x180039696  lea     r9, [rsp+1C0h+Type]; lpType
0x18003969b  xor     r8d, r8d; lpReserved
0x18003969e  lea     rdx, aSid; "Sid"
0x1800396a5  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800396aa  call    cs:__imp_RegQueryValueExW
0x1800396b0  mov     ebx, eax
0x1800396b2  test    eax, eax
0x1800396b4  jle     short loc_1800396BB
0x1800396b6  movzx   ebx, ax
0x1800396b9  or      ebx, esi
0x1800396bb  lea     rsi, aDsrhkeyuserhan_4; "DsrHKeyUserHandle::ReadHKeyUserInfo"
0x1800396c2  cmp     ebx, 80070002h
0x1800396c8  jnz     loc_180039771
0x1800396ce  cmp     qword ptr [rdi+18h], 7
0x1800396d3  jbe     short loc_1800396DD
0x1800396d5  mov     rax, [rdi]
0x1800396d8  mov     r9, rax
0x1800396db  jmp     short loc_1800396E3
0x1800396dd  mov     rax, rdi
0x1800396e0  mov     r9, rdi
0x1800396e3  mov     [rsp+1C0h+phkResult], rax
0x1800396e8  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800396ef  mov     rdx, rsi
0x1800396f2  lea     rcx, aSSidValueIsNot; "%s: Sid value is not present at %s\\%s."...
0x1800396f9  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800396fe  cmp     qword ptr [rdi+18h], 7
0x180039703  jbe     short loc_18003970A
0x180039705  mov     rcx, [rdi]
0x180039708  jmp     short loc_18003970D
0x18003970a  mov     rcx, rdi; StringSid
0x18003970d  lea     rdx, [rsp+1C0h+Sid]; Sid
0x180039712  call    cs:__imp_ConvertStringSidToSidW
0x180039718  test    eax, eax
0x18003971a  jnz     short loc_18003972E
0x18003971c  mov     r9d, 80070002h
0x180039722  lea     r8, aRegqueryvaluee; "RegQueryValueExW(REG_SID_VALUE)"
0x180039729  jmp     loc_180039560
0x18003972e  xor     ebx, ebx
0x180039730  mov     rcx, [rsp+1C0h+Sid]; Sid
0x180039735  lea     rdx, [rsp+1C0h+StringSid]; StringSid
0x18003973a  call    cs:__imp_ConvertSidToStringSidW
0x180039740  test    eax, eax
0x180039742  jnz     loc_18003981E
0x180039748  call    cs:__imp_GetLastError
0x18003974e  test    eax, eax
0x180039750  mov     ebx, eax
0x180039752  jle     short loc_18003975D
0x180039754  movzx   ebx, ax
0x180039757  or      ebx, 80070000h
0x18003975d  test    ebx, ebx
0x18003975f  jns     loc_18003981E
0x180039765  lea     r8, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18003976c  jmp     loc_18003955D
0x180039771  xor     eax, eax
0x180039773  cmp     ebx, 800700EAh
0x180039779  cmovnz  eax, ebx
0x18003977c  mov     ebx, eax
0x18003977e  test    eax, eax
0x180039780  jns     short loc_180039787
0x180039782  mov     r9d, eax
0x180039785  jmp     short loc_180039722
0x180039787  cmp     [rsp+1C0h+Type], 3
0x18003978c  jz      short loc_1800397BD
0x18003978e  mov     ebx, 80070057h
0x180039793  cmp     qword ptr [rdi+18h], 7
0x180039798  jbe     short loc_18003979F
0x18003979a  mov     r9, [rdi]
0x18003979d  jmp     short loc_1800397A2
0x18003979f  mov     r9, rdi
0x1800397a2  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800397a9  mov     rdx, rsi
0x1800397ac  lea     rcx, aSUnexpectedTyp; "%s: Unexpected type found while reading"...
0x1800397b3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800397b8  jmp     loc_1800398A4
0x1800397bd  mov     ecx, [rsp+1C0h+cbData]; unsigned __int64
0x1800397c1  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800397c6  mov     r14, rax
0x1800397c9  test    rax, rax
0x1800397cc  jz      loc_180039626
0x1800397d2  lea     rax, [rsp+1C0h+cbData]
0x1800397d7  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800397dc  mov     [rsp+1C0h+phkResult], r14; lpData
0x1800397e1  lea     r9, [rsp+1C0h+Type]; lpType
0x1800397e6  xor     r8d, r8d; lpReserved
0x1800397e9  lea     rdx, aSid; "Sid"
0x1800397f0  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800397f5  call    cs:__imp_RegQueryValueExW
0x1800397fb  mov     ebx, eax
0x1800397fd  test    eax, eax
0x1800397ff  jle     short loc_18003980A
0x180039801  movzx   ebx, ax
0x180039804  or      ebx, 80070000h
0x18003980a  test    ebx, ebx
0x18003980c  jns     short loc_180039816
0x18003980e  mov     r9d, ebx
0x180039811  jmp     loc_180039722
0x180039816  mov     rcx, r14
0x180039819  jmp     loc_180039735
0x18003981e  mov     rdx, r15
0x180039821  lea     rcx, [rsp+1C0h+var_170]
0x180039826  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003982b  lea     rdx, aNtuserDat; "\\NtUser.dat"
0x180039832  lea     rcx, [rsp+1C0h+var_170]
0x180039837  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003983c  lea     rdx, [rbp+0C0h+var_80]
0x180039840  lea     rcx, [rsp+1C0h+var_168]
0x180039845  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18003984a  nop
0x18003984b  lea     rdx, [rbp+0C0h+var_80]
0x18003984f  cmp     [rbp+0C0h+var_68], 7
0x180039854  cmova   rdx, [rbp+0C0h+var_80]
0x180039859  lea     rcx, [rbp+0C0h+var_60]
0x18003985d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180039862  lea     rcx, [r13+30h]
0x180039866  mov     rdx, rax
0x180039869  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003986e  lea     rcx, [rbp+0C0h+var_60]
0x180039872  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039877  nop
0x180039878  lea     rcx, [rbp+0C0h+var_80]
0x18003987c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039881  mov     rdx, [rsp+1C0h+StringSid]
0x180039886  lea     rcx, [rbp+0C0h+var_60]
0x18003988a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003988f  lea     rcx, [r13+10h]
0x180039893  mov     rdx, rax
0x180039896  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003989b  lea     rcx, [rbp+0C0h+var_60]
0x18003989f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800398a4  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800398a9  test    rcx, rcx
0x1800398ac  jz      short loc_1800398BD
0x1800398ae  call    cs:__imp_RegCloseKey
0x1800398b4  mov     [rsp+1C0h+hKey], 0
0x1800398bd  mov     rcx, r14; lpMem
0x1800398c0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800398c5  mov     rcx, [rsp+1C0h+StringSid]; hMem
0x1800398ca  call    cs:__imp_LocalFree
0x1800398d0  mov     rcx, r15; lpMem
0x1800398d3  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800398d8  mov     rcx, [rsp+1C0h+Sid]; hMem
0x1800398dd  call    cs:__imp_LocalFree
0x1800398e3  cmp     qword ptr [rdi+18h], 7
0x1800398e8  jbe     short loc_1800398ED
0x1800398ea  mov     rdi, [rdi]
0x1800398ed  mov     [rsp+1C0h+phkResult], rdi
0x1800398f2  lea     r9, aProfilename; "profileName"
0x1800398f9  mov     r8d, ebx
0x1800398fc  mov     rdx, rsi
0x1800398ff  lea     rcx, aSHr0x08xSS; "%s - hr: 0x%08x. %s: %s."
0x180039906  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003990b  nop
0x18003990c  lea     rcx, [rsp+1C0h+var_170]
0x180039911  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180039916  mov     eax, ebx
0x180039918  mov     rcx, [rbp+0C0h+var_40]
0x18003991f  xor     rcx, rsp; StackCookie
0x180039922  call    __security_check_cookie
0x180039927  add     rsp, 190h
0x18003992e  pop     r15
0x180039930  pop     r14
0x180039932  pop     r13
0x180039934  pop     rdi
0x180039935  pop     rsi
0x180039936  pop     rbx
0x180039937  pop     rbp
0x180039938  retn
```
