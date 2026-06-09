# AppxPreprocessXml

- ea: `0x180027130`
- end: `0x1800275a5`
- name: `AppxPreprocessXml`
- size: `1141`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017320`
- `0x180027130`
- `0x1800275ac`
- `0x18002db70`
- `0x18002f9a8`
- `0x180060c90`
- `0x180084010`
- `0x1800cd6fc`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x18002727e`: `AppxPreprocessXml parameter inputStream cannot be NULL`
- `0x1800272f0`: `AppxPreprocessXml parameter processedStream cannot be NULL`
- `0x180027362`: `AppxPreprocessXml parameter namespaces cannot be NULL`
- `0x1800273d4`: `AppxPreprocessXml parameter namespaceCount cannot be 0`
- `0x180027446`: `AppxPreprocessXml parameter errorMessage cannot be NULL`
- `0x1800274b8`: `AppxPreprocessXml parameter lineNumber cannot be NULL`
- `0x18002752a`: `AppxPreprocessXml parameter columnNumber cannot be NULL`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall AppxPreprocessXml(
        __int64 a1,
        __int64 a2,
        struct Stream *a3,
        unsigned int a4,
        __int64 a5,
        wchar_t **a6,
        unsigned int *a7)
{
  win_musl *v10; // rcx
  win_musl::Formatter *v12; // rcx
  struct win_musl::TStringEllipseBase *v13; // rax
  win_musl::Formatter *v14; // rax
  struct win_musl::TStringEllipseBase *v15; // rax
  win_musl::Formatter *v16; // rax
  struct win_musl::TStringEllipseBase *v17; // rax
  win_musl::Formatter *v18; // rax
  struct win_musl::TStringEllipseBase *v19; // rax
  win_musl::Formatter *v20; // rax
  struct win_musl::TStringEllipseBase *v21; // rax
  win_musl::Formatter *v22; // rax
  struct win_musl::TStringEllipseBase *v23; // rax
  win_musl::Formatter *v24; // rax
  struct win_musl::TStringEllipseBase *v25; // rax
  unsigned int *v26; // [rsp+38h] [rbp-550h]
  __int64 v27; // [rsp+40h] [rbp-548h] BYREF
  __int64 v28; // [rsp+48h] [rbp-540h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-538h] BYREF
  _BYTE v30[48]; // [rsp+60h] [rbp-528h] BYREF
  _BYTE v31[96]; // [rsp+90h] [rbp-4F8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-498h] BYREF
  _BYTE v33[160]; // [rsp+190h] [rbp-3F8h] BYREF
  _BYTE v34[160]; // [rsp+230h] [rbp-358h] BYREF
  _BYTE v35[160]; // [rsp+2D0h] [rbp-2B8h] BYREF
  _BYTE v36[160]; // [rsp+370h] [rbp-218h] BYREF
  _BYTE v37[160]; // [rsp+410h] [rbp-178h] BYREF
  _BYTE v38[160]; // [rsp+4B0h] [rbp-D8h] BYREF

  v29[1] = -2;
  try
  {
    if ( !a1 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter inputStream cannot be NULL");
      v12 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v13 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v12);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x18Du,
        0x80004003,
        v13);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !a2 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter processedStream cannot be NULL");
      v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v15 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v14);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v33,
        0x195u,
        0x80004003,
        v15);
      throw (SplException::THResultException *)v33;
    }
    if ( !a3 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter namespaces cannot be NULL");
      v16 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v17 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v34,
        0x19Du,
        0x80004003,
        v17);
      throw (SplException::THResultException *)v34;
    }
    if ( !a4 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter namespaceCount cannot be 0");
      v18 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v19 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v18);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v35,
        0x1A5u,
        0x80004003,
        v19);
      throw (SplException::THResultException *)v35;
    }
    if ( !a5 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter errorMessage cannot be NULL");
      v20 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v21 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v20);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v36,
        0x1ADu,
        0x80004003,
        v21);
      throw (SplException::THResultException *)v36;
    }
    if ( !a6 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter lineNumber cannot be NULL");
      v22 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v23 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v22);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v37,
        0x1B5u,
        0x80004003,
        v23);
      throw (SplException::THResultException *)v37;
    }
    if ( !a7 )
    {
      std::wstring::wstring(v30, L"AppxPreprocessXml parameter columnNumber cannot be NULL");
      v24 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v31, v30);
      v25 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v24);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v38,
        0x1BDu,
        0x80004003,
        v25);
      throw (SplException::THResultException *)v38;
    }
    v27 = a1;
    v29[0] = 0;
    win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(
      v29,
      &v27);
    v28 = a2;
    v27 = 0;
    win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(
      &v27,
      &v28);
    win_musl::consumption::InternalAppxPreprocessXml(
      (win_musl::consumption *)v29,
      (struct Stream *)&v27,
      a3,
      (const wchar_t **)a4,
      a5,
      a6,
      a7,
      v26);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v10 = (win_musl *)v29[0];
    if ( v29[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
  }
  catch ( ... )
  {
    win_musl::detail_process_errors(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180027130  mov     rax, rsp
0x180027133  push    rdi
0x180027134  push    r12
0x180027136  push    r13
0x180027138  push    r14
0x18002713a  push    r15
0x18002713c  sub     rsp, 560h
0x180027143  mov     [rsp+588h+var_530], 0FFFFFFFFFFFFFFFEh
0x18002714c  mov     [rax+8], rbx
0x180027150  mov     [rax+10h], rsi
0x180027154  mov     rax, cs:__security_cookie
0x18002715b  xor     rax, rsp
0x18002715e  mov     [rsp+588h+var_38], rax
0x180027166  mov     r14d, r9d
0x180027169  mov     rsi, r8
0x18002716c  mov     rdi, rdx
0x18002716f  mov     r15, [rsp+588h+arg_20]
0x180027177  mov     r12, [rsp+588h+arg_28]
0x18002717f  mov     r13, [rsp+588h+arg_30]
0x180027187  xor     ebx, ebx
0x180027189  test    rcx, rcx
0x18002718c  jz      loc_18002727E
0x180027192  test    rdx, rdx
0x180027195  jz      loc_1800272F0
0x18002719b  test    r8, r8
0x18002719e  jz      loc_180027362
0x1800271a4  test    r9d, r9d
0x1800271a7  jz      loc_1800273D4
0x1800271ad  test    r15, r15
0x1800271b0  jz      loc_180027446
0x1800271b6  test    r12, r12
0x1800271b9  jz      loc_1800274B8
0x1800271bf  test    r13, r13
0x1800271c2  jz      loc_18002752A
0x1800271c8  mov     [rsp+588h+var_548], rcx
0x1800271cd  mov     [rsp+588h+var_538], rbx
0x1800271d2  lea     rdx, [rsp+588h+var_548]
0x1800271d7  lea     rcx, [rsp+588h+var_538]
0x1800271dc  call    ??$construct_acquire@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIPackageSettings@@@Z; win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(win_scope::scope<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>> *,IPackageSettings * *)
0x1800271e1  nop
0x1800271e2  mov     [rsp+588h+var_540], rdi
0x1800271e7  mov     [rsp+588h+var_548], rbx
0x1800271ec  lea     rdx, [rsp+588h+var_540]
0x1800271f1  lea     rcx, [rsp+588h+var_548]
0x1800271f6  call    ??$construct_acquire@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIPackageSettings@@@Z; win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(win_scope::scope<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>> *,IPackageSettings * *)
0x1800271fb  nop
0x1800271fc  mov     [rsp+588h+var_558], r13; unsigned int *
0x180027201  mov     [rsp+588h+var_560], r12; wchar_t **
0x180027206  mov     qword ptr [rsp+588h+var_568], r15; unsigned int
0x18002720b  mov     r9d, r14d; wchar_t **
0x18002720e  mov     r8, rsi; struct Stream *
0x180027211  lea     rdx, [rsp+588h+var_548]; struct Stream *
0x180027216  lea     rcx, [rsp+588h+var_538]; this
0x18002721b  call    ?InternalAppxPreprocessXml@consumption@win_musl@@YAXAEAVStream@win_dox@@0PEAPEB_WKPEAPEA_WPEAK3@Z; win_musl::consumption::InternalAppxPreprocessXml(win_dox::Stream &,win_dox::Stream &,wchar_t const * *,ulong,wchar_t * *,ulong *,ulong *)
0x180027220  nop
0x180027221  mov     rcx, [rsp+588h+var_548]
0x180027226  test    rcx, rcx
0x180027229  jz      short loc_180027238
0x18002722b  mov     rax, [rcx]
0x18002722e  mov     rax, [rax+10h]
0x180027232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027237  nop
0x180027238  mov     rcx, [rsp+588h+var_538]
0x18002723d  test    rcx, rcx
0x180027240  jz      short loc_18002724F
0x180027242  mov     rax, [rcx]
0x180027245  mov     rax, [rax+10h]
0x180027249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002724e  nop
0x18002724f  mov     eax, ebx
0x180027251  mov     rcx, [rsp+588h+var_38]
0x180027259  xor     rcx, rsp; StackCookie
0x18002725c  call    __security_check_cookie
0x180027261  lea     r11, [rsp+588h+var_28]
0x180027269  mov     rbx, [r11+30h]
0x18002726d  mov     rsi, [r11+38h]
0x180027271  mov     rsp, r11
0x180027274  pop     r15
0x180027276  pop     r14
0x180027278  pop     r13
0x18002727a  pop     r12
0x18002727c  pop     rdi
0x18002727d  retn
0x18002727e  lea     rdx, aAppxpreprocess_3; "AppxPreprocessXml parameter inputStream"...
0x180027285  lea     rcx, [rsp+588h+var_528]
0x18002728a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002728f  nop
0x180027290  lea     rdx, [rsp+588h+var_528]
0x180027295  lea     rcx, [rsp+588h+var_4F8]
0x18002729d  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800272a2  nop
0x1800272a3  mov     rcx, rax; this
0x1800272a6  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800272ab  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x1800272b0  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x1800272b8  mov     [rsp+588h+var_568], 18Dh; unsigned int
0x1800272c0  lea     r9, word_180139126
0x1800272c7  lea     r8, aNoFilename; "(no filename)"
0x1800272ce  lea     rcx, [rsp+588h+pExceptionObject]; this
0x1800272d6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800272db  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800272e2  lea     rcx, [rsp+588h+pExceptionObject]; pExceptionObject
0x1800272ea  call    _CxxThrowException_0
0x1800272f0  lea     rdx, aAppxpreprocess; "AppxPreprocessXml parameter processedSt"...
0x1800272f7  lea     rcx, [rsp+588h+var_528]
0x1800272fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180027301  nop
0x180027302  lea     rdx, [rsp+588h+var_528]
0x180027307  lea     rcx, [rsp+588h+var_4F8]
0x18002730f  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180027314  nop
0x180027315  mov     rcx, rax; this
0x180027318  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18002731d  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x180027322  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18002732a  mov     [rsp+588h+var_568], 195h; unsigned int
0x180027332  lea     r9, word_180139126
0x180027339  lea     r8, aNoFilename; "(no filename)"
0x180027340  lea     rcx, [rsp+588h+var_3F8]; this
0x180027348  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18002734d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180027354  lea     rcx, [rsp+588h+var_3F8]; pExceptionObject
0x18002735c  call    _CxxThrowException_0
0x180027362  lea     rdx, aAppxpreprocess_0; "AppxPreprocessXml parameter namespaces "...
0x180027369  lea     rcx, [rsp+588h+var_528]
0x18002736e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180027373  nop
0x180027374  lea     rdx, [rsp+588h+var_528]
0x180027379  lea     rcx, [rsp+588h+var_4F8]
0x180027381  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180027386  nop
0x180027387  mov     rcx, rax; this
0x18002738a  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18002738f  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x180027394  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18002739c  mov     [rsp+588h+var_568], 19Dh; unsigned int
0x1800273a4  lea     r9, word_180139126
0x1800273ab  lea     r8, aNoFilename; "(no filename)"
0x1800273b2  lea     rcx, [rsp+588h+var_358]; this
0x1800273ba  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800273bf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800273c6  lea     rcx, [rsp+588h+var_358]; pExceptionObject
0x1800273ce  call    _CxxThrowException_0
0x1800273d4  lea     rdx, aAppxpreprocess_2; "AppxPreprocessXml parameter namespaceCo"...
0x1800273db  lea     rcx, [rsp+588h+var_528]
0x1800273e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800273e5  nop
0x1800273e6  lea     rdx, [rsp+588h+var_528]
0x1800273eb  lea     rcx, [rsp+588h+var_4F8]
0x1800273f3  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800273f8  nop
0x1800273f9  mov     rcx, rax; this
0x1800273fc  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180027401  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x180027406  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x18002740e  mov     [rsp+588h+var_568], 1A5h; unsigned int
0x180027416  lea     r9, word_180139126
0x18002741d  lea     r8, aNoFilename; "(no filename)"
0x180027424  lea     rcx, [rsp+588h+var_2B8]; this
0x18002742c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180027431  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180027438  lea     rcx, [rsp+588h+var_2B8]; pExceptionObject
0x180027440  call    _CxxThrowException_0
0x180027446  lea     rdx, aAppxpreprocess_9; "AppxPreprocessXml parameter errorMessag"...
0x18002744d  lea     rcx, [rsp+588h+var_528]
0x180027452  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180027457  nop
0x180027458  lea     rdx, [rsp+588h+var_528]
0x18002745d  lea     rcx, [rsp+588h+var_4F8]
0x180027465  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18002746a  nop
0x18002746b  mov     rcx, rax; this
0x18002746e  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180027473  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x180027478  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x180027480  mov     [rsp+588h+var_568], 1ADh; unsigned int
0x180027488  lea     r9, word_180139126
0x18002748f  lea     r8, aNoFilename; "(no filename)"
0x180027496  lea     rcx, [rsp+588h+var_218]; this
0x18002749e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800274a3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800274aa  lea     rcx, [rsp+588h+var_218]; pExceptionObject
0x1800274b2  call    _CxxThrowException_0
0x1800274b8  lea     rdx, aAppxpreprocess_10; "AppxPreprocessXml parameter lineNumber "...
0x1800274bf  lea     rcx, [rsp+588h+var_528]
0x1800274c4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800274c9  nop
0x1800274ca  lea     rdx, [rsp+588h+var_528]
0x1800274cf  lea     rcx, [rsp+588h+var_4F8]
0x1800274d7  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800274dc  nop
0x1800274dd  mov     rcx, rax; this
0x1800274e0  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800274e5  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x1800274ea  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x1800274f2  mov     [rsp+588h+var_568], 1B5h; unsigned int
0x1800274fa  lea     r9, word_180139126
0x180027501  lea     r8, aNoFilename; "(no filename)"
0x180027508  lea     rcx, [rsp+588h+var_178]; this
0x180027510  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180027515  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18002751c  lea     rcx, [rsp+588h+var_178]; pExceptionObject
0x180027524  call    _CxxThrowException_0
0x18002752a  lea     rdx, aAppxpreprocess_4; "AppxPreprocessXml parameter columnNumbe"...
0x180027531  lea     rcx, [rsp+588h+var_528]
0x180027536  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002753b  nop
0x18002753c  lea     rdx, [rsp+588h+var_528]
0x180027541  lea     rcx, [rsp+588h+var_4F8]
0x180027549  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18002754e  nop
0x18002754f  mov     rcx, rax; this
0x180027552  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180027557  mov     [rsp+588h+var_558], rax; struct win_musl::TStringEllipseBase *
0x18002755c  mov     dword ptr [rsp+588h+var_560], 80004003h; unsigned int
0x180027564  mov     [rsp+588h+var_568], 1BDh; unsigned int
0x18002756c  lea     r9, word_180139126
0x180027573  lea     r8, aNoFilename; "(no filename)"
0x18002757a  lea     rcx, [rsp+588h+var_D8]; this
0x180027582  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180027587  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18002758e  lea     rcx, [rsp+588h+var_D8]; pExceptionObject
0x180027596  call    _CxxThrowException_0
0x18002759c  mov     ebx, dword ptr [rsp+588h+var_548]
0x1800275a0  jmp     loc_18002724F
```
