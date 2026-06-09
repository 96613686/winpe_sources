# BulkFilenameEnumerator::GetSecurityDescriptorFromPath(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1801d41ec`
- end: `0x1801d438c`
- name: `?GetSecurityDescriptorFromPath@BulkFilenameEnumerator@@CA?AV?$vector@EV?$allocator@E@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801d4a20`

## callees

- `0x180012120`
- `0x18004e5d8`
- `0x18006f100`
- `0x1801244c0`
- `0x1801906ec`
- `0x1801d3334`
- `0x1801d41ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d42d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d42d0`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1801d430e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1801d430e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801d4247`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801d42c6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801d4247`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801d42c6`

## string_xrefs

- `0x1801d4318`: `BulkFilenameEnumerator::GetSecurityDescriptorFromPath - Invalid security descriptor`
- `0x1801d426b`: `BulkFilenameEnumerator::GetSecurityDescriptorFromPath - First call failed: 0x%08x`
- `0x1801d42e5`: `BulkFilenameEnumerator::GetSecurityDescriptorFromPath - Second call failed: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall BulkFilenameEnumerator::GetSecurityDescriptorFromPath(_QWORD *a1, __int64 a2)
{
  const WCHAR *v3; // rcx
  signed int v4; // eax
  const WCHAR *v5; // rcx
  signed int LastError; // eax
  const wchar_t *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  PSECURITY_DESCRIPTOR v10; // rax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+38h] [rbp-1h] BYREF
  __int64 v14; // [rsp+40h] [rbp+7h]
  __int64 v15; // [rsp+48h] [rbp+Fh]
  DWORD lpnLengthNeeded[4]; // [rsp+50h] [rbp+17h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+60h] [rbp+27h] BYREF
  unsigned __int64 v18; // [rsp+78h] [rbp+3Fh]

  *(_QWORD *)lpnLengthNeeded = a1;
  nLengthNeeded = 0;
  std::wstring::wstring(lpFileName, a2);
  v3 = (const WCHAR *)lpFileName;
  if ( v18 > 7 )
    v3 = lpFileName[0];
  if ( GetFileSecurityW(v3, 7u, 0, 0, &nLengthNeeded) || (v4 = GetLastError(), v4 == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(&pSecurityDescriptor, nLengthNeeded);
    lpnLengthNeeded[0] = 0;
    v5 = (const WCHAR *)lpFileName;
    if ( v18 > 7 )
      v5 = lpFileName[0];
    if ( GetFileSecurityW(v5, 7u, pSecurityDescriptor, nLengthNeeded, lpnLengthNeeded) )
    {
      if ( IsValidSecurityDescriptor(pSecurityDescriptor) )
      {
        v8 = v15;
        v15 = 0;
        v9 = v14;
        v14 = 0;
        v10 = pSecurityDescriptor;
        pSecurityDescriptor = 0;
        *a1 = v10;
        a1[1] = v9;
        a1[2] = v8;
        goto LABEL_18;
      }
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\bulkfilenameenumerator.cpp\"",
        (const wchar_t *)0x219,
        (unsigned int)L"BulkFilenameEnumerator::GetSecurityDescriptorFromPath - Invalid security descriptor",
        v7);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\bulkfilenameenumerator.cpp\"",
        (const wchar_t *)0x211,
        (unsigned int)L"BulkFilenameEnumerator::GetSecurityDescriptorFromPath - Second call failed: 0x%08x",
        (const wchar_t *)(unsigned int)LastError);
    }
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
LABEL_18:
    std::vector<unsigned char>::_Tidy(&pSecurityDescriptor);
    goto LABEL_19;
  }
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\bulkfilenameenumerator.cpp\"",
    (const wchar_t *)0x1FD,
    (unsigned int)L"BulkFilenameEnumerator::GetSecurityDescriptorFromPath - First call failed: 0x%08x",
    (const wchar_t *)(unsigned int)v4);
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
LABEL_19:
  ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpFileName);
  return a1;
}

```

## disassembly

```asm
0x1801d41ec  mov     [rsp-8+arg_10], rbx
0x1801d41f1  mov     [rsp-8+arg_18], rdi
0x1801d41f6  push    rbp
0x1801d41f7  lea     rbp, [rsp-57h]
0x1801d41fc  sub     rsp, 90h
0x1801d4203  mov     rax, cs:__security_cookie
0x1801d420a  xor     rax, rsp
0x1801d420d  mov     [rbp+57h+var_10], rax
0x1801d4211  mov     rbx, rcx
0x1801d4214  mov     qword ptr [rbp+57h+var_40], rcx
0x1801d4218  xor     edi, edi
0x1801d421a  mov     [rbp+57h+nLengthNeeded], edi
0x1801d421d  lea     rcx, [rbp+57h+lpFileName]
0x1801d4221  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x1801d4226  nop
0x1801d4227  lea     rcx, [rbp+57h+lpFileName]
0x1801d422b  cmp     [rbp+57h+var_18], 7
0x1801d4230  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801d4235  lea     rax, [rbp+57h+nLengthNeeded]
0x1801d4239  mov     [rsp+90h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1801d423e  xor     r9d, r9d; nLength
0x1801d4241  xor     r8d, r8d; pSecurityDescriptor
0x1801d4244  lea     edx, [rdi+7]; RequestedInformation
0x1801d4247  call    cs:__imp_GetFileSecurityW
0x1801d424d  test    eax, eax
0x1801d424f  jnz     short loc_1801D4293
0x1801d4251  call    cs:__imp_GetLastError
0x1801d4257  cmp     eax, 7Ah ; 'z'
0x1801d425a  jz      short loc_1801D4293
0x1801d425c  test    eax, eax
0x1801d425e  jle     short loc_1801D4268
0x1801d4260  movzx   eax, ax
0x1801d4263  or      eax, 80070000h
0x1801d4268  mov     r9d, eax; wchar_t *
0x1801d426b  lea     r8, aBulkfilenameen_3; "BulkFilenameEnumerator::GetSecurityDesc"...
0x1801d4272  mov     edx, 1FDh; wchar_t *
0x1801d4277  lea     rcx, aOnecoreuapBase_142; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1801d427e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1801d4283  mov     [rbx], rdi
0x1801d4286  mov     [rbx+8], rdi
0x1801d428a  mov     [rbx+10h], rdi
0x1801d428e  jmp     loc_1801D435F
0x1801d4293  mov     edx, [rbp+57h+nLengthNeeded]
0x1801d4296  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1801d429a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1801d429f  mov     [rbp+57h+var_40], edi
0x1801d42a2  lea     rcx, [rbp+57h+lpFileName]
0x1801d42a6  cmp     [rbp+57h+var_18], 7
0x1801d42ab  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801d42b0  lea     rax, [rbp+57h+var_40]
0x1801d42b4  mov     [rsp+90h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1801d42b9  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1801d42bd  mov     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1801d42c1  mov     edx, 7; RequestedInformation
0x1801d42c6  call    cs:__imp_GetFileSecurityW
0x1801d42cc  test    eax, eax
0x1801d42ce  jnz     short loc_1801D430A
0x1801d42d0  call    cs:__imp_GetLastError
0x1801d42d6  test    eax, eax
0x1801d42d8  jle     short loc_1801D42E2
0x1801d42da  movzx   eax, ax
0x1801d42dd  or      eax, 80070000h
0x1801d42e2  mov     r9d, eax; wchar_t *
0x1801d42e5  lea     r8, aBulkfilenameen_6; "BulkFilenameEnumerator::GetSecurityDesc"...
0x1801d42ec  mov     edx, 211h; wchar_t *
0x1801d42f1  lea     rcx, aOnecoreuapBase_142; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1801d42f8  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1801d42fd  mov     [rbx], rdi
0x1801d4300  mov     [rbx+8], rdi
0x1801d4304  mov     [rbx+10h], rdi
0x1801d4308  jmp     short loc_1801D4355
0x1801d430a  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1801d430e  call    cs:__imp_IsValidSecurityDescriptor
0x1801d4314  test    eax, eax
0x1801d4316  jnz     short loc_1801D4332
0x1801d4318  lea     r8, aBulkfilenameen; "BulkFilenameEnumerator::GetSecurityDesc"...
0x1801d431f  mov     edx, 219h; wchar_t *
0x1801d4324  lea     rcx, aOnecoreuapBase_142; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1801d432b  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1801d4330  jmp     short loc_1801D42FD
0x1801d4332  mov     rdx, [rbp+57h+var_48]
0x1801d4336  mov     [rbp+57h+var_48], rdi
0x1801d433a  mov     rcx, [rbp+57h+var_50]
0x1801d433e  mov     [rbp+57h+var_50], rdi
0x1801d4342  mov     rax, [rbp+57h+pSecurityDescriptor]
0x1801d4346  mov     [rbp+57h+pSecurityDescriptor], rdi
0x1801d434a  mov     [rbx], rax
0x1801d434d  mov     [rbx+8], rcx
0x1801d4351  mov     [rbx+10h], rdx
0x1801d4355  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1801d4359  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801d435e  nop
0x1801d435f  lea     rcx, [rbp+57h+lpFileName]; this
0x1801d4363  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1801d4368  mov     rax, rbx
0x1801d436b  mov     rcx, [rbp+57h+var_10]
0x1801d436f  xor     rcx, rsp; StackCookie
0x1801d4372  call    __security_check_cookie
0x1801d4377  lea     r11, [rsp+90h+var_s0]
0x1801d437f  mov     rbx, [r11+20h]
0x1801d4383  mov     rdi, [r11+28h]
0x1801d4387  mov     rsp, r11
0x1801d438a  pop     rbp
0x1801d438b  retn
```
