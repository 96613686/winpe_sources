# CSecurityAdmin2::CanonicalizeUserName(ushort *,ushort * *,int)

- ea: `0x180037880`
- end: `0x180037d2a`
- name: `?CanonicalizeUserName@CSecurityAdmin2@@UEAAJPEAGPEAPEAGH@Z`
- size: `1194`
- prototype: `int __fastcall(CSecurityAdmin2 *this, unsigned __int16 *, LPVOID *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000a01c`
- `0x18000b6a0`
- `0x18001a6c8`
- `0x180027418`
- `0x180037880`
- `0x180038078`
- `0x18003821c`
- `0x180038274`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180037b22`
- `msvcrt!_wcsicmp` at `0x180037bd7`
- `msvcrt!_wcsicmp` at `0x180037c37`
- `msvcrt!_wcsicmp` at `0x180037b22`
- `msvcrt!_wcsicmp` at `0x180037bd7`
- `msvcrt!_wcsicmp` at `0x180037c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ad7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037966`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037966`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003793e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003793e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037c7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180037916`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180037916`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180037a6a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180037aba`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180037a6a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180037aba`

## pseudocode

```c
int __fastcall CSecurityAdmin2::CanonicalizeUserName(CSecurityAdmin2 *this, unsigned __int16 *a2, LPVOID *a3, int a4)
{
  CGetAccountDomain *v7; // rcx
  int result; // eax
  const WCHAR *v9; // rcx
  SIZE_T v10; // rdi
  unsigned __int16 *v11; // rax
  int v12; // ebx
  void *v13; // r11
  int v14; // eax
  const unsigned __int16 *v15; // rcx
  int v16; // r11d
  __int64 v17; // rdi
  unsigned __int16 v18; // r14
  void *v19; // rbx
  BOOL v20; // edi
  __int64 v21; // rax
  __int64 v22; // rcx
  SIZE_T v23; // rbx
  unsigned __int16 *v24; // rax
  int v25; // eax
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbSid; // [rsp+3Ch] [rbp-C4h] BYREF
  wchar_t ReferencedDomainName[280]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR AccountName[280]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(ReferencedDomainName, 0, 0x222u);
  memset_0(AccountName, 0, 0x222u);
  *a3 = 0;
  result = CGetAccountDomain::Init(v7);
  if ( result < 0 )
    return result;
  if ( (int)safe_lstrlenW(a2) >= 273 )
    return -2147024809;
  if ( a4 || (Sid = 0, !ConvertStringSidToSidW(v9, &Sid)) )
  {
    while ( 1 )
    {
      v14 = safe_lstrlenW(a2);
      if ( v16 >= v14 )
        break;
      v17 = v16;
      v18 = a2[v16];
      if ( v18 == 92 || v18 == 47 )
      {
        a2[v16] = 0;
        result = StringCchCopyW(ReferencedDomainName, 0x111u, a2);
        a2[v17] = v18;
        if ( result < 0 )
          return result;
        result = StringCchCopyW(AccountName, 0x111u, &a2[v17 + 1]);
        if ( result < 0 )
          return result;
      }
    }
    if ( ReferencedDomainName[0] )
      goto LABEL_29;
    if ( AccountName[0] )
    {
LABEL_20:
      cbSid = 0;
      LODWORD(Sid) = 0;
      cchReferencedDomainName = 16;
      if ( LookupAccountNameLocalW(
             AccountName,
             0,
             &cbSid,
             ReferencedDomainName,
             &cchReferencedDomainName,
             (PSID_NAME_USE)&Sid) )
      {
        goto LABEL_42;
      }
      v19 = CoTaskMemAlloc(cbSid);
      if ( !v19 )
        return -2147024882;
      cchReferencedDomainName = 16;
      v20 = LookupAccountNameLocalW(
              AccountName,
              v19,
              &cbSid,
              ReferencedDomainName,
              &cchReferencedDomainName,
              (PSID_NAME_USE)&Sid);
      CoTaskMemFree(v19);
      if ( a4 )
      {
        if ( !v20 )
          goto LABEL_24;
LABEL_42:
        if ( _wcsicmp(ReferencedDomainName, qword_1800732E8) )
        {
LABEL_43:
          v21 = -1;
          v22 = -1;
          do
            ++v22;
          while ( ReferencedDomainName[v22] );
          do
            ++v21;
          while ( AccountName[v21] );
          v23 = (unsigned int)(2 * (v22 + v21) + 4);
          v24 = (unsigned __int16 *)CoTaskMemAlloc(v23);
          *a3 = v24;
          if ( v24 )
          {
            if ( ReferencedDomainName[0] )
              v25 = StringCbPrintfW(v24, v23, L"%s/%s", ReferencedDomainName, AccountName);
            else
              v25 = StringCbCopyW(v24, v23, AccountName);
            v12 = v25;
            if ( v25 < 0 )
            {
              CoTaskMemFree(*a3);
              *a3 = 0;
            }
            return v12;
          }
          return -2147024882;
        }
LABEL_35:
        result = StringCchCopyW(ReferencedDomainName, 0x111u, L".");
        if ( result < 0 )
          return result;
        goto LABEL_43;
      }
      if ( v20 && !ReferencedDomainName[0] )
        goto LABEL_42;
      result = StringCchCopyW(ReferencedDomainName, 0x111u, L".");
      if ( result < 0 )
        return result;
LABEL_29:
      if ( _wcsicmp(ReferencedDomainName, L".") )
      {
        if ( (unsigned int)IsValidUserName(ReferencedDomainName, AccountName) )
          goto LABEL_42;
        if ( _wcsicmp(ReferencedDomainName, qword_1800732E8) )
        {
          if ( a4 )
            return -2147023564;
          goto LABEL_42;
        }
        Sid = 0;
        result = GetLocalizedBUILTIN((unsigned __int16 **)&Sid);
        if ( result < 0 )
          return result;
        if ( (unsigned int)IsValidUserName(Sid, AccountName) )
        {
          result = StringCchCopyW(ReferencedDomainName, 0x111u, (const unsigned __int16 *)Sid);
          if ( result < 0 )
            return result;
          goto LABEL_42;
        }
        if ( !a4 )
          goto LABEL_42;
      }
      else
      {
        Sid = 0;
        result = GetLocalizedBUILTIN((unsigned __int16 **)&Sid);
        if ( result < 0 )
          return result;
        result = StringCchCopyW(ReferencedDomainName, 0x111u, (const unsigned __int16 *)Sid);
        if ( result < 0 )
          return result;
        if ( (unsigned int)IsValidUserName(ReferencedDomainName, AccountName) )
          goto LABEL_43;
        if ( !a4 || (unsigned int)IsValidUserName(qword_1800732E8, AccountName) )
          goto LABEL_35;
      }
LABEL_24:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( (int)safe_lstrlenW(v15) <= 256 )
    {
      result = StringCchCopyW(AccountName, 0x111u, a2);
      if ( result < 0 )
        return result;
      goto LABEL_20;
    }
    return -2147024809;
  }
  LocalFree(Sid);
  v10 = 2 * (unsigned int)safe_lstrlenW(a2) + 2;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(v10);
  if ( !v11 )
    return -2147024882;
  v12 = StringCbCopyW(v11, (unsigned int)v10, a2);
  if ( v12 < 0 )
  {
    CoTaskMemFree(v13);
    return v12;
  }
  *a3 = v13;
  return 0;
}

```

## disassembly

```asm
0x180037880  mov     [rsp-8+arg_0], rbx
0x180037885  push    rbp
0x180037886  push    rsi
0x180037887  push    rdi
0x180037888  push    r12
0x18003788a  push    r13
0x18003788c  push    r14
0x18003788e  push    r15
0x180037890  lea     rbp, [rsp-3B0h]
0x180037898  sub     rsp, 4B0h
0x18003789f  mov     rax, cs:__security_cookie
0x1800378a6  xor     rax, rsp
0x1800378a9  mov     [rbp+3E0h+var_40], rax
0x1800378b0  mov     r15, r8
0x1800378b3  lea     rcx, [rsp+4E0h+ReferencedDomainName]; void *
0x1800378b8  mov     rbx, rdx
0x1800378bb  mov     edi, 222h
0x1800378c0  mov     r8d, edi; Size
0x1800378c3  xor     edx, edx; Val
0x1800378c5  mov     esi, r9d
0x1800378c8  call    memset_0
0x1800378cd  mov     r8d, edi; Size
0x1800378d0  lea     rcx, [rbp+3E0h+AccountName]; void *
0x1800378d7  xor     edx, edx; Val
0x1800378d9  call    memset_0
0x1800378de  xor     r12d, r12d
0x1800378e1  mov     [r15], r12
0x1800378e4  call    ?Init@CGetAccountDomain@@QEAAJXZ; CGetAccountDomain::Init(void)
0x1800378e9  test    eax, eax
0x1800378eb  js      loc_180037D00
0x1800378f1  mov     rcx, rbx; unsigned __int16 *
0x1800378f4  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800378f9  mov     r13d, 111h
0x1800378ff  cmp     eax, r13d
0x180037902  jge     loc_180037CFB
0x180037908  test    esi, esi
0x18003790a  jnz     short loc_18003797D
0x18003790c  lea     rdx, [rsp+4E0h+Sid]; Sid
0x180037911  mov     [rsp+4E0h+Sid], r12
0x180037916  call    cs:__imp_ConvertStringSidToSidW
0x18003791c  test    eax, eax
0x18003791e  jz      short loc_18003797D
0x180037920  mov     rcx, [rsp+4E0h+Sid]; hMem
0x180037925  call    cs:__imp_LocalFree
0x18003792b  mov     rcx, rbx; unsigned __int16 *
0x18003792e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180037933  lea     eax, ds:2[rax*2]
0x18003793a  mov     ecx, eax; cb
0x18003793c  mov     edi, eax
0x18003793e  call    cs:__imp_CoTaskMemAlloc
0x180037944  mov     r11, rax
0x180037947  test    rax, rax
0x18003794a  jz      loc_180037C89
0x180037950  mov     r8, rbx; unsigned __int16 *
0x180037953  mov     edx, edi; unsigned __int64
0x180037955  mov     rcx, rax; unsigned __int16 *
0x180037958  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003795d  mov     ebx, eax
0x18003795f  test    eax, eax
0x180037961  jns     short loc_180037973
0x180037963  mov     rcx, r11; pv
0x180037966  call    cs:__imp_CoTaskMemFree
0x18003796c  mov     eax, ebx
0x18003796e  jmp     loc_180037D00
0x180037973  mov     [r15], r11
0x180037976  xor     eax, eax
0x180037978  jmp     loc_180037D00
0x18003797d  mov     r11d, r12d
0x180037980  mov     rcx, rbx; unsigned __int16 *
0x180037983  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180037988  cmp     r11d, eax
0x18003798b  jge     short loc_1800379E9
0x18003798d  movsxd  rdi, r11d
0x180037990  movzx   r14d, word ptr [rbx+rdi*2]
0x180037995  cmp     r14w, 5Ch ; '\'
0x18003799a  jz      short loc_1800379A3
0x18003799c  cmp     r14w, 2Fh ; '/'
0x1800379a1  jnz     short loc_1800379E4
0x1800379a3  mov     r8, rbx; unsigned __int16 *
0x1800379a6  mov     [rbx+rdi*2], r12w
0x1800379ab  mov     rdx, r13; unsigned __int64
0x1800379ae  lea     rcx, [rsp+4E0h+ReferencedDomainName]; unsigned __int16 *
0x1800379b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800379b8  mov     [rbx+rdi*2], r14w
0x1800379bd  test    eax, eax
0x1800379bf  js      loc_180037D00
0x1800379c5  lea     r8, [rbx+2]
0x1800379c9  mov     rdx, r13; unsigned __int64
0x1800379cc  lea     r8, [r8+rdi*2]; unsigned __int16 *
0x1800379d0  lea     rcx, [rbp+3E0h+AccountName]; unsigned __int16 *
0x1800379d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800379dc  test    eax, eax
0x1800379de  js      loc_180037D00
0x1800379e4  inc     r11d
0x1800379e7  jmp     short loc_180037980
0x1800379e9  lea     r14, asc_18005EA94; "."
0x1800379f0  cmp     [rsp+4E0h+ReferencedDomainName], r12w
0x1800379f6  jnz     loc_180037B1A
0x1800379fc  cmp     [rbp+3E0h+AccountName], r12w
0x180037a04  jnz     short loc_180037A30
0x180037a06  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180037a0b  cmp     eax, 100h
0x180037a10  jg      loc_180037CFB
0x180037a16  mov     r8, rbx; unsigned __int16 *
0x180037a19  lea     rcx, [rbp+3E0h+AccountName]; unsigned __int16 *
0x180037a20  mov     rdx, r13; unsigned __int64
0x180037a23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037a28  test    eax, eax
0x180037a2a  js      loc_180037D00
0x180037a30  lea     rax, [rsp+4E0h+Sid]
0x180037a35  mov     [rsp+4E0h+cbSid], r12d
0x180037a3a  mov     [rsp+4E0h+peUse], rax; peUse
0x180037a3f  lea     r9, [rsp+4E0h+ReferencedDomainName]; ReferencedDomainName
0x180037a44  lea     rax, [rsp+4E0h+var_4A8]
0x180037a49  mov     dword ptr [rsp+4E0h+Sid], r12d
0x180037a4e  mov     edi, 10h
0x180037a53  mov     [rsp+4E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180037a58  lea     r8, [rsp+4E0h+cbSid]; cbSid
0x180037a5d  mov     [rsp+4E0h+var_4A8], edi
0x180037a61  xor     edx, edx; Sid
0x180037a63  lea     rcx, [rbp+3E0h+AccountName]; lpAccountName
0x180037a6a  call    cs:__imp_LookupAccountNameLocalW
0x180037a70  test    eax, eax
0x180037a72  jnz     loc_180037C2B
0x180037a78  mov     ecx, [rsp+4E0h+cbSid]; cb
0x180037a7c  call    cs:__imp_CoTaskMemAlloc
0x180037a82  mov     rbx, rax
0x180037a85  test    rax, rax
0x180037a88  jz      loc_180037C89
0x180037a8e  lea     rax, [rsp+4E0h+Sid]
0x180037a93  mov     [rsp+4E0h+var_4A8], edi
0x180037a97  mov     [rsp+4E0h+peUse], rax; peUse
0x180037a9c  lea     r9, [rsp+4E0h+ReferencedDomainName]; ReferencedDomainName
0x180037aa1  lea     rax, [rsp+4E0h+var_4A8]
0x180037aa6  mov     rdx, rbx; Sid
0x180037aa9  lea     r8, [rsp+4E0h+cbSid]; cbSid
0x180037aae  mov     [rsp+4E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180037ab3  lea     rcx, [rbp+3E0h+AccountName]; lpAccountName
0x180037aba  call    cs:__imp_LookupAccountNameLocalW
0x180037ac0  mov     rcx, rbx; pv
0x180037ac3  mov     edi, eax
0x180037ac5  call    cs:__imp_CoTaskMemFree
0x180037acb  test    esi, esi
0x180037acd  jz      short loc_180037AF2
0x180037acf  test    edi, edi
0x180037ad1  jnz     loc_180037C2B
0x180037ad7  call    cs:__imp_GetLastError
0x180037add  test    eax, eax
0x180037adf  jle     loc_180037D00
0x180037ae5  movzx   eax, ax
0x180037ae8  or      eax, 80070000h
0x180037aed  jmp     loc_180037D00
0x180037af2  test    edi, edi
0x180037af4  jz      short loc_180037B02
0x180037af6  cmp     [rsp+4E0h+ReferencedDomainName], r12w
0x180037afc  jz      loc_180037C2B
0x180037b02  mov     r8, r14; unsigned __int16 *
0x180037b05  lea     rcx, [rsp+4E0h+ReferencedDomainName]; unsigned __int16 *
0x180037b0a  mov     rdx, r13; unsigned __int64
0x180037b0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037b12  test    eax, eax
0x180037b14  js      loc_180037D00
0x180037b1a  mov     rdx, r14; String2
0x180037b1d  lea     rcx, [rsp+4E0h+ReferencedDomainName]; String1
0x180037b22  call    cs:__imp__wcsicmp
0x180037b28  test    eax, eax
0x180037b2a  jnz     loc_180037BB6
0x180037b30  lea     rcx, [rsp+4E0h+Sid]; unsigned __int16 **
0x180037b35  mov     [rsp+4E0h+Sid], r12
0x180037b3a  call    ?GetLocalizedBUILTIN@@YAJPEAPEAG@Z; GetLocalizedBUILTIN(ushort * *)
0x180037b3f  test    eax, eax
0x180037b41  js      loc_180037D00
0x180037b47  mov     r8, [rsp+4E0h+Sid]; unsigned __int16 *
0x180037b4c  lea     rcx, [rsp+4E0h+ReferencedDomainName]; unsigned __int16 *
0x180037b51  mov     rdx, r13; unsigned __int64
0x180037b54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037b59  test    eax, eax
0x180037b5b  js      loc_180037D00
0x180037b61  lea     rdx, [rbp+3E0h+AccountName]
0x180037b68  lea     rcx, [rsp+4E0h+ReferencedDomainName]
0x180037b6d  call    IsValidUserName
0x180037b72  test    eax, eax
0x180037b74  jnz     loc_180037C45
0x180037b7a  test    esi, esi
0x180037b7c  jz      short loc_180037B99
0x180037b7e  mov     rcx, cs:qword_1800732E8
0x180037b85  lea     rdx, [rbp+3E0h+AccountName]
0x180037b8c  call    IsValidUserName
0x180037b91  test    eax, eax
0x180037b93  jz      loc_180037AD7
0x180037b99  mov     r8, r14; unsigned __int16 *
0x180037b9c  lea     rcx, [rsp+4E0h+ReferencedDomainName]; unsigned __int16 *
0x180037ba1  mov     rdx, r13; unsigned __int64
0x180037ba4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037ba9  test    eax, eax
0x180037bab  jns     loc_180037C45
0x180037bb1  jmp     loc_180037D00
0x180037bb6  lea     rdx, [rbp+3E0h+AccountName]
0x180037bbd  lea     rcx, [rsp+4E0h+ReferencedDomainName]
0x180037bc2  call    IsValidUserName
0x180037bc7  test    eax, eax
0x180037bc9  jnz     short loc_180037C2B
0x180037bcb  mov     rdx, cs:qword_1800732E8; String2
0x180037bd2  lea     rcx, [rsp+4E0h+ReferencedDomainName]; String1
0x180037bd7  call    cs:__imp__wcsicmp
0x180037bdd  test    eax, eax
0x180037bdf  jnz     loc_180037C99
0x180037be5  lea     rcx, [rsp+4E0h+Sid]; unsigned __int16 **
0x180037bea  mov     [rsp+4E0h+Sid], r12
0x180037bef  call    ?GetLocalizedBUILTIN@@YAJPEAPEAG@Z; GetLocalizedBUILTIN(ushort * *)
0x180037bf4  test    eax, eax
0x180037bf6  js      loc_180037D00
0x180037bfc  mov     rcx, [rsp+4E0h+Sid]
0x180037c01  lea     rdx, [rbp+3E0h+AccountName]
0x180037c08  call    IsValidUserName
0x180037c0d  test    eax, eax
0x180037c0f  jz      short loc_180037C90
0x180037c11  mov     r8, [rsp+4E0h+Sid]; unsigned __int16 *
0x180037c16  lea     rcx, [rsp+4E0h+ReferencedDomainName]; unsigned __int16 *
0x180037c1b  mov     rdx, r13; unsigned __int64
0x180037c1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037c23  test    eax, eax
0x180037c25  js      loc_180037D00
0x180037c2b  mov     rdx, cs:qword_1800732E8; String2
0x180037c32  lea     rcx, [rsp+4E0h+ReferencedDomainName]; String1
0x180037c37  call    cs:__imp__wcsicmp
0x180037c3d  test    eax, eax
0x180037c3f  jz      loc_180037B99
0x180037c45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037c49  lea     rdx, [rsp+4E0h+ReferencedDomainName]
0x180037c4e  mov     rcx, rax
0x180037c51  inc     rcx
0x180037c54  cmp     [rdx+rcx*2], r12w
0x180037c59  jnz     short loc_180037C51
0x180037c5b  lea     rdx, [rbp+3E0h+AccountName]
0x180037c62  inc     rax
0x180037c65  cmp     [rdx+rax*2], r12w
0x180037c6a  jnz     short loc_180037C62
0x180037c6c  add     rax, rcx
0x180037c6f  lea     rax, ds:4[rax*2]
0x180037c77  mov     ecx, eax; cb
0x180037c79  mov     ebx, eax
0x180037c7b  call    cs:__imp_CoTaskMemAlloc
0x180037c81  mov     [r15], rax
0x180037c84  test    rax, rax
0x180037c87  jnz     short loc_180037CA4
0x180037c89  mov     eax, 8007000Eh
0x180037c8e  jmp     short loc_180037D00
0x180037c90  test    esi, esi
0x180037c92  jz      short loc_180037C2B
0x180037c94  jmp     loc_180037AD7
0x180037c99  test    esi, esi
0x180037c9b  jz      short loc_180037C2B
0x180037c9d  mov     eax, 80070534h
0x180037ca2  jmp     short loc_180037D00
0x180037ca4  mov     rdx, rbx; unsigned __int64
0x180037ca7  cmp     [rsp+4E0h+ReferencedDomainName], r12w
0x180037cad  jz      short loc_180037CD1
0x180037caf  lea     rcx, [rbp+3E0h+AccountName]
0x180037cb6  mov     [rsp+4E0h+cchReferencedDomainName], rcx
0x180037cbb  lea     r9, [rsp+4E0h+ReferencedDomainName]
0x180037cc0  mov     rcx, rax; unsigned __int16 *
0x180037cc3  lea     r8, aSS_2; "%s/%s"
0x180037cca  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037ccf  jmp     short loc_180037CE0
0x180037cd1  lea     r8, [rbp+3E0h+AccountName]; unsigned __int16 *
0x180037cd8  mov     rcx, rax; unsigned __int16 *
0x180037cdb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180037ce0  mov     ebx, eax
0x180037ce2  test    eax, eax
0x180037ce4  jns     loc_18003796C
0x180037cea  mov     rcx, [r15]; pv
0x180037ced  call    cs:__imp_CoTaskMemFree
0x180037cf3  mov     [r15], r12
0x180037cf6  jmp     loc_18003796C
0x180037cfb  mov     eax, 80070057h
0x180037d00  mov     rcx, [rbp+3E0h+var_40]
0x180037d07  xor     rcx, rsp; StackCookie
0x180037d0a  call    __security_check_cookie
0x180037d0f  mov     rbx, [rsp+4E0h+arg_0]
0x180037d17  add     rsp, 4B0h
0x180037d1e  pop     r15
0x180037d20  pop     r14
0x180037d22  pop     r13
0x180037d24  pop     r12
0x180037d26  pop     rdi
0x180037d27  pop     rsi
0x180037d28  pop     rbp
0x180037d29  retn
```
