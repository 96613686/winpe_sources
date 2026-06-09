# AppxPreprocessXmlForSax

- ea: `0x1800054a0`
- end: `0x180005814`
- name: `AppxPreprocessXmlForSax`
- size: `884`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001de4`
- `0x1800054a0`
- `0x180017320`
- `0x1800275ac`
- `0x18002db70`
- `0x18002dcfc`
- `0x180060c90`
- `0x180084010`
- `0x1800cd6fc`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x1800054da`: `AppxPreprocessXmlForSax parameter inputStream cannot be NULL`
- `0x180005551`: `AppxPreprocessXmlForSax parameter contentHandler cannot be NULL`
- `0x1800055c8`: `AppxPreprocessXmlForSax parameter errorHandler cannot be NULL`
- `0x18000563f`: `AppxPreprocessXmlForSax parameter namespaces cannot be NULL`
- `0x1800056bc`: `AppxPreprocessXmlForSax parameter namespaceCount cannot be 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall AppxPreprocessXmlForSax(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const struct win_musl::consumption::SaxErrorHandler *a4,
        int a5)
{
  win_musl::Formatter *v8; // rcx
  struct win_musl::TStringEllipseBase *v9; // rax
  win_musl::Formatter *v10; // rax
  struct win_musl::TStringEllipseBase *v11; // rax
  win_musl::Formatter *v12; // rax
  struct win_musl::TStringEllipseBase *v13; // rax
  win_musl::Formatter *v14; // rax
  struct win_musl::TStringEllipseBase *v15; // rax
  win_musl::Formatter *v16; // rax
  struct win_musl::TStringEllipseBase *v17; // rax
  unsigned int *v18; // rcx
  wchar_t **v20; // [rsp+20h] [rbp-428h]
  unsigned int *v21; // [rsp+40h] [rbp-408h] BYREF
  __int64 v22; // [rsp+48h] [rbp-400h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-3F8h] BYREF
  _BYTE v24[40]; // [rsp+68h] [rbp-3E0h] BYREF
  _BYTE v25[96]; // [rsp+90h] [rbp-3B8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-358h] BYREF
  _BYTE v27[160]; // [rsp+190h] [rbp-2B8h] BYREF
  _BYTE v28[160]; // [rsp+230h] [rbp-218h] BYREF
  _BYTE v29[160]; // [rsp+2D0h] [rbp-178h] BYREF
  _BYTE v30[160]; // [rsp+370h] [rbp-D8h] BYREF

  v23[1] = -2;
  try
  {
    if ( !a1 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter inputStream cannot be NULL");
      v8 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v9 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v8);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EEu,
        0x80004003,
        v9);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !a2 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter contentHandler cannot be NULL");
      v10 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v11 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v10);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v27,
        0x1F6u,
        0x80004003,
        v11);
      throw (SplException::THResultException *)v27;
    }
    if ( !a3 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter errorHandler cannot be NULL");
      v12 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v13 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v12);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v28,
        0x1FEu,
        0x80004003,
        v13);
      throw (SplException::THResultException *)v28;
    }
    if ( !a4 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter namespaces cannot be NULL");
      v14 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v15 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v14);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v29,
        0x206u,
        0x80004003,
        v15);
      throw (SplException::THResultException *)v29;
    }
    if ( !a5 )
    {
      std::wstring::wstring(v24, L"AppxPreprocessXmlForSax parameter namespaceCount cannot be 0");
      v16 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v25, v24);
      v17 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v16);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v30,
        0x20Eu,
        0x80004003,
        v17);
      throw (SplException::THResultException *)v30;
    }
    v22 = a1;
    v21 = 0;
    win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(
      &v21,
      &v22);
    win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(
      v23,
      a2);
    win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(
      &v22,
      a3);
    v23[2] = 0;
    LODWORD(v20) = a5;
    win_musl::consumption::ParseAndPreprocessXml(
      (win_musl::consumption *)&v21,
      (struct Stream *)v23,
      (const struct win_musl::consumption::SaxContentHandler *)&v22,
      a4,
      (const wchar_t **)v20,
      0,
      0,
      0);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    v18 = v21;
    if ( v21 )
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  catch ( ... )
  {
    win_musl::detail_process_errors((win_musl *)v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1800054a0  push    rbx
0x1800054a2  push    rsi
0x1800054a3  push    rdi
0x1800054a4  push    r14
0x1800054a6  push    r15
0x1800054a8  sub     rsp, 420h
0x1800054af  mov     [rsp+448h+var_3F0], 0FFFFFFFFFFFFFFFEh
0x1800054b8  mov     rax, cs:__security_cookie
0x1800054bf  xor     rax, rsp
0x1800054c2  mov     [rsp+448h+var_38], rax
0x1800054ca  mov     r15, r9
0x1800054cd  mov     r14, r8
0x1800054d0  mov     rsi, rdx
0x1800054d3  xor     edi, edi
0x1800054d5  test    rcx, rcx
0x1800054d8  jnz     short loc_18000554C
0x1800054da  lea     rdx, aAppxpreprocess_8; "AppxPreprocessXmlForSax parameter input"...
0x1800054e1  lea     rcx, [rsp+448h+var_3E0]
0x1800054e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800054eb  nop
0x1800054ec  lea     rdx, [rsp+448h+var_3E0]
0x1800054f1  lea     rcx, [rsp+448h+var_3B8]
0x1800054f9  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800054fe  nop
0x1800054ff  mov     rcx, rax; this
0x180005502  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180005507  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x18000550c  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x180005514  mov     dword ptr [rsp+448h+var_428], 1EEh; unsigned int
0x18000551c  lea     r9, word_180139126
0x180005523  lea     r8, aNoFilename; "(no filename)"
0x18000552a  lea     rcx, [rsp+448h+pExceptionObject]; this
0x180005532  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180005537  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000553e  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x180005546  call    _CxxThrowException_0
0x18000554c  test    rsi, rsi
0x18000554f  jnz     short loc_1800055C3
0x180005551  lea     rdx, aAppxpreprocess_6; "AppxPreprocessXmlForSax parameter conte"...
0x180005558  lea     rcx, [rsp+448h+var_3E0]
0x18000555d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180005562  nop
0x180005563  lea     rdx, [rsp+448h+var_3E0]
0x180005568  lea     rcx, [rsp+448h+var_3B8]
0x180005570  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180005575  nop
0x180005576  mov     rcx, rax; this
0x180005579  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18000557e  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x180005583  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x18000558b  mov     dword ptr [rsp+448h+var_428], 1F6h; unsigned int
0x180005593  lea     r9, word_180139126
0x18000559a  lea     r8, aNoFilename; "(no filename)"
0x1800055a1  lea     rcx, [rsp+448h+var_2B8]; this
0x1800055a9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800055ae  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800055b5  lea     rcx, [rsp+448h+var_2B8]; pExceptionObject
0x1800055bd  call    _CxxThrowException_0
0x1800055c3  test    r14, r14
0x1800055c6  jnz     short loc_18000563A
0x1800055c8  lea     rdx, aAppxpreprocess_7; "AppxPreprocessXmlForSax parameter error"...
0x1800055cf  lea     rcx, [rsp+448h+var_3E0]
0x1800055d4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800055d9  nop
0x1800055da  lea     rdx, [rsp+448h+var_3E0]
0x1800055df  lea     rcx, [rsp+448h+var_3B8]
0x1800055e7  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800055ec  nop
0x1800055ed  mov     rcx, rax; this
0x1800055f0  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800055f5  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x1800055fa  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x180005602  mov     dword ptr [rsp+448h+var_428], 1FEh; unsigned int
0x18000560a  lea     r9, word_180139126
0x180005611  lea     r8, aNoFilename; "(no filename)"
0x180005618  lea     rcx, [rsp+448h+var_218]; this
0x180005620  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180005625  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000562c  lea     rcx, [rsp+448h+var_218]; pExceptionObject
0x180005634  call    _CxxThrowException_0
0x18000563a  test    r15, r15
0x18000563d  jnz     short loc_1800056B1
0x18000563f  lea     rdx, aAppxpreprocess_5; "AppxPreprocessXmlForSax parameter names"...
0x180005646  lea     rcx, [rsp+448h+var_3E0]
0x18000564b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180005650  nop
0x180005651  lea     rdx, [rsp+448h+var_3E0]
0x180005656  lea     rcx, [rsp+448h+var_3B8]
0x18000565e  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180005663  nop
0x180005664  mov     rcx, rax; this
0x180005667  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18000566c  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x180005671  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x180005679  mov     dword ptr [rsp+448h+var_428], 206h; unsigned int
0x180005681  lea     r9, word_180139126
0x180005688  lea     r8, aNoFilename; "(no filename)"
0x18000568f  lea     rcx, [rsp+448h+var_178]; this
0x180005697  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000569c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800056a3  lea     rcx, [rsp+448h+var_178]; pExceptionObject
0x1800056ab  call    _CxxThrowException_0
0x1800056b1  mov     ebx, dword ptr [rsp+448h+arg_20]
0x1800056b8  test    ebx, ebx
0x1800056ba  jnz     short loc_18000572E
0x1800056bc  lea     rdx, aAppxpreprocess_1; "AppxPreprocessXmlForSax parameter names"...
0x1800056c3  lea     rcx, [rsp+448h+var_3E0]
0x1800056c8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800056cd  nop
0x1800056ce  lea     rdx, [rsp+448h+var_3E0]
0x1800056d3  lea     rcx, [rsp+448h+var_3B8]
0x1800056db  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800056e0  nop
0x1800056e1  mov     rcx, rax; this
0x1800056e4  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800056e9  mov     [rsp+448h+var_418], rax; struct win_musl::TStringEllipseBase *
0x1800056ee  mov     [rsp+448h+var_420], 80004003h; unsigned int
0x1800056f6  mov     dword ptr [rsp+448h+var_428], 20Eh; unsigned int
0x1800056fe  lea     r9, word_180139126
0x180005705  lea     r8, aNoFilename; "(no filename)"
0x18000570c  lea     rcx, [rsp+448h+var_D8]; this
0x180005714  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180005719  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180005720  lea     rcx, [rsp+448h+var_D8]; pExceptionObject
0x180005728  call    _CxxThrowException_0
0x18000572e  mov     [rsp+448h+var_400], rcx
0x180005733  mov     [rsp+448h+var_408], 0; unsigned int *
0x18000573c  lea     rdx, [rsp+448h+var_400]
0x180005741  lea     rcx, [rsp+448h+var_408]
0x180005746  call    ??$construct_acquire@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@PEAU1@@?$scope_helper@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUIPackageSettings@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@2@PEAPEAUIPackageSettings@@@Z; win_scope::detail::scope_helper<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>>::construct_acquire<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>,IPackageSettings *>(win_scope::scope<IPackageSettings *,win_scope::const_policies<win_scope::com_policies>> *,IPackageSettings * *)
0x18000574b  nop
0x18000574c  mov     rdx, rsi
0x18000574f  lea     rcx, [rsp+448h+var_3F8]
0x180005754  call    ??0?$scope@PEAUIWin7InternalPartSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAUIWin7InternalPartSender@@@Z; win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(IWin7InternalPartSender *)
0x180005759  nop
0x18000575a  mov     rdx, r14
0x18000575d  lea     rcx, [rsp+448h+var_400]
0x180005762  call    ??0?$scope@PEAUIWin7InternalPartSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAUIWin7InternalPartSender@@@Z; win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(IWin7InternalPartSender *)
0x180005767  nop
0x180005768  mov     [rsp+448h+var_3E8], 0
0x180005771  mov     [rsp+448h+var_410], 0; unsigned int *
0x18000577a  mov     [rsp+448h+var_418], 0; wchar_t **
0x180005783  mov     qword ptr [rsp+448h+var_420], 0; unsigned int
0x18000578c  mov     dword ptr [rsp+448h+var_428], ebx; wchar_t **
0x180005790  mov     r9, r15; struct win_musl::consumption::SaxErrorHandler *
0x180005793  lea     r8, [rsp+448h+var_400]; struct win_musl::consumption::SaxContentHandler *
0x180005798  lea     rdx, [rsp+448h+var_3F8]; struct Stream *
0x18000579d  lea     rcx, [rsp+448h+var_408]; this
0x1800057a2  call    ?ParseAndPreprocessXml@consumption@win_musl@@YAXAEAVStream@win_dox@@AEBVSaxContentHandler@12@AEBVSaxErrorHandler@12@PEAPEB_WKPEAPEA_WPEAK5@Z; win_musl::consumption::ParseAndPreprocessXml(win_dox::Stream &,win_musl::consumption::SaxContentHandler const &,win_musl::consumption::SaxErrorHandler const &,wchar_t const * *,ulong,wchar_t * *,ulong *,ulong *)
0x1800057a7  nop
0x1800057a8  mov     rcx, [rsp+448h+var_400]
0x1800057ad  test    rcx, rcx
0x1800057b0  jz      short loc_1800057BF
0x1800057b2  mov     rax, [rcx]
0x1800057b5  mov     rax, [rax+10h]
0x1800057b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057be  nop
0x1800057bf  mov     rcx, [rsp+448h+var_3F8]
0x1800057c4  test    rcx, rcx
0x1800057c7  jz      short loc_1800057D6
0x1800057c9  mov     rax, [rcx]
0x1800057cc  mov     rax, [rax+10h]
0x1800057d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d5  nop
0x1800057d6  mov     rcx, [rsp+448h+var_408]
0x1800057db  test    rcx, rcx
0x1800057de  jz      short loc_1800057ED
0x1800057e0  mov     rax, [rcx]
0x1800057e3  mov     rax, [rax+10h]
0x1800057e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ec  nop
0x1800057ed  jmp     short loc_1800057F3
0x1800057ef  mov     edi, dword ptr [rsp+448h+var_408]
0x1800057f3  mov     eax, edi
0x1800057f5  mov     rcx, [rsp+448h+var_38]
0x1800057fd  xor     rcx, rsp; StackCookie
0x180005800  call    __security_check_cookie
0x180005805  add     rsp, 420h
0x18000580c  pop     r15
0x18000580e  pop     r14
0x180005810  pop     rdi
0x180005811  pop     rsi
0x180005812  pop     rbx
0x180005813  retn
```
