# win_musl::consumption::CreateSaxParser(win_scope::scope<ISAXContentHandler *,win_scope::const_policies<win_scope::com_policies>>,win_scope::scope<ISAXErrorHandler *,win_scope::const_policies<win_scope::com_policies>>)

- ea: `0x180007258`
- end: `0x180007439`
- name: `?CreateSaxParser@consumption@win_musl@@YA?AV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAUISAXContentHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@4@V?$scope@PEAUISAXErrorHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@4@@Z`
- size: `481`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800069bc`
- `0x18000703c`
- `0x18002e488`
- `0x1800b893c`
- `0x1800b9554`

## callees

- `0x180007258`
- `0x18002db70`
- `0x1800cd6fc`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800072d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800072d9`

## string_xrefs

- `0x180007373`: `Sax CoCreate failed for MSXML6 Reader`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LPVOID *__fastcall win_musl::consumption::CreateSaxParser(LPVOID *ppv, _QWORD *a2, _QWORD *a3)
{
  HRESULT Instance; // eax
  signed int v7; // eax
  signed int v8; // eax
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  *ppv = 0;
  *ppv = 0;
  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a0c_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802,
               ppv);
  if ( Instance < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x2Au,
      Instance,
      (struct win_musl::TStringEllipseBase *)L"Sax CoCreate failed for MSXML6 Reader");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 80LL))(*ppv, *a2);
  if ( v7 < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x31u,
      v7,
      (struct win_musl::TStringEllipseBase *)L"Sax putContentHandler failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 112LL))(*ppv, *a3);
  if ( v8 < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x37u,
      v8,
      (struct win_musl::TStringEllipseBase *)L"Sax putErrorHandler failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
  }
  if ( *a3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
    *a3 = 0;
  }
  return ppv;
}

```

## disassembly

```asm
0x180007258  mov     rax, rsp
0x18000725b  push    rbp
0x18000725c  push    rsi
0x18000725d  push    rdi
0x18000725e  lea     rbp, [rax-38h]
0x180007262  sub     rsp, 120h
0x180007269  mov     [rsp+130h+var_E8], 0FFFFFFFFFFFFFFFEh
0x180007272  mov     [rax+20h], rbx
0x180007276  mov     rax, cs:__security_cookie
0x18000727d  xor     rax, rsp
0x180007280  mov     [rbp+30h+var_20], rax
0x180007284  mov     rdi, r8
0x180007287  mov     rsi, rdx
0x18000728a  mov     rbx, rcx
0x18000728d  mov     [rsp+130h+var_E0], rcx
0x180007292  mov     [rsp+130h+var_D8], rdx
0x180007297  mov     [rsp+60h], r8
0x18000729c  mov     dword ptr [rsp+130h+var_F0], 0
0x1800072a4  mov     qword ptr [rcx], 0
0x1800072ab  mov     r8d, 1; dwClsContext
0x1800072b1  mov     dword ptr [rsp+130h+var_F0], r8d
0x1800072b6  mov     qword ptr [rcx], 0
0x1800072bd  mov     qword ptr [rcx], 0
0x1800072c4  mov     [rsp+130h+ppv], rcx; ppv
0x1800072c9  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x1800072d0  xor     edx, edx; pUnkOuter
0x1800072d2  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x1800072d9  call    cs:__imp_CoCreateInstance
0x1800072df  test    eax, eax
0x1800072e1  js      loc_180007373
0x1800072e7  mov     rcx, [rbx]
0x1800072ea  mov     rax, [rcx]
0x1800072ed  mov     rdx, [rsi]
0x1800072f0  mov     rax, [rax+50h]
0x1800072f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f9  test    eax, eax
0x1800072fb  js      loc_1800073B5
0x180007301  mov     rcx, [rbx]
0x180007304  mov     rax, [rcx]
0x180007307  mov     rdx, [rdi]
0x18000730a  mov     rax, [rax+70h]
0x18000730e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007313  test    eax, eax
0x180007315  js      loc_1800073F7
0x18000731b  mov     rcx, [rsi]
0x18000731e  test    rcx, rcx
0x180007321  jz      short loc_180007336
0x180007323  mov     rax, [rcx]
0x180007326  mov     rax, [rax+10h]
0x18000732a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000732f  mov     qword ptr [rsi], 0
0x180007336  mov     rcx, [rdi]
0x180007339  test    rcx, rcx
0x18000733c  jz      short loc_180007351
0x18000733e  mov     rdx, [rcx]
0x180007341  mov     rax, [rdx+10h]
0x180007345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000734a  mov     qword ptr [rdi], 0
0x180007351  mov     rax, rbx
0x180007354  mov     rcx, [rbp+30h+var_20]
0x180007358  xor     rcx, rsp; StackCookie
0x18000735b  call    __security_check_cookie
0x180007360  mov     rbx, [rsp+130h+arg_18]
0x180007368  add     rsp, 120h
0x18000736f  pop     rdi
0x180007370  pop     rsi
0x180007371  pop     rbp
0x180007372  retn
0x180007373  lea     rcx, aSaxCocreateFai; "Sax CoCreate failed for MSXML6 Reader"
0x18000737a  mov     [rsp+30h], rcx; struct win_musl::TStringEllipseBase *
0x18000737f  mov     [rsp+130h+var_108], eax; unsigned int
0x180007383  mov     dword ptr [rsp+130h+ppv], 2Ah ; '*'; unsigned int
0x18000738b  lea     r9, word_180139126
0x180007392  lea     r8, aNoFilename; "(no filename)"
0x180007399  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18000739e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800073a3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800073aa  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1800073af  call    _CxxThrowException_0
0x1800073b5  lea     rcx, aSaxPutcontenth; "Sax putContentHandler failed"
0x1800073bc  mov     [rsp+30h], rcx; struct win_musl::TStringEllipseBase *
0x1800073c1  mov     [rsp+130h+var_108], eax; unsigned int
0x1800073c5  mov     dword ptr [rsp+130h+ppv], 31h ; '1'; unsigned int
0x1800073cd  lea     r9, word_180139126
0x1800073d4  lea     r8, aNoFilename; "(no filename)"
0x1800073db  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1800073e0  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800073e5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800073ec  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1800073f1  call    _CxxThrowException_0
0x1800073f7  lea     rcx, aSaxPuterrorhan; "Sax putErrorHandler failed"
0x1800073fe  mov     [rsp+30h], rcx; struct win_musl::TStringEllipseBase *
0x180007403  mov     [rsp+130h+var_108], eax; unsigned int
0x180007407  mov     dword ptr [rsp+130h+ppv], 37h ; '7'; unsigned int
0x18000740f  lea     r9, word_180139126
0x180007416  lea     r8, aNoFilename; "(no filename)"
0x18000741d  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180007422  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180007427  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000742e  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180007433  call    _CxxThrowException_0
```
