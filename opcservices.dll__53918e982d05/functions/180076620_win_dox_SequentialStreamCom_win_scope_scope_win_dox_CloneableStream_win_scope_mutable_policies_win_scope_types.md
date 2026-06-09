# win_dox::SequentialStreamCom<win_scope::scope<win_dox::CloneableStream *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>,IStream>::Read_Safe(void *,ulong,ulong *)

- ea: `0x180076620`
- end: `0x180076844`
- name: `?Read_Safe@?$SequentialStreamCom@V?$scope@PEAVCloneableStream@win_dox@@U?$mutable_policies@U?$types_6@Uclose_delete@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@UIStream@@@win_dox@@AEAAXPEAXKPEAK@Z`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800765e0`

## callees

- `0x180012468`
- `0x18002db70`
- `0x180058f20`
- `0x180076620`
- `0x18007684c`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007670d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007670d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076685`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076685`

## string_xrefs

- `0x1800767ef`: `Call to Read failed with HResult 0x%X.`
- `0x180076795`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_dox::SequentialStreamCom<win_scope::scope<win_dox::CloneableStream *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>,IStream>::Read_Safe(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4)
{
  unsigned int v5; // r15d
  __int64 *v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // r12
  int v10; // ecx
  signed int v11; // r14d
  __int64 v12; // r14
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  char v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v20[512]; // [rsp+110h] [rbp+10h] BYREF

  v18 = -2;
  v5 = a3;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 78, L"IStream", L"Read", L"pv", 0);
  HIDWORD(v15) = 0;
  v7 = *(__int64 **)(a1 + 8);
  v8 = v7[2];
  v9 = *v7;
  v15 = v8 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  v10 = *(_DWORD *)(v8 + 52);
  *(_DWORD *)(v8 + 52) = v10 + 1;
  if ( !v10 )
    *(_DWORD *)(v8 + 48) = GetCurrentThreadId();
  v16 = 1;
  v17 = v8;
  if ( !*(_BYTE *)(v8 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(_QWORD *)v8 != v9 )
    win_dox::Stream::Seek(v8 + 64, v9, 0);
  v14 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**(_QWORD **)(v8 + 64) + 24LL))(
          *(_QWORD *)(v8 + 64),
          a2,
          v5,
          &v14);
  if ( v11 < 0 )
  {
    memset_0(v20, 0, sizeof(v20));
    StringCchPrintfW(v20, 0x200u, L"Call to Read failed with HResult 0x%X.", (unsigned int)v11);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x60u,
      v11,
      (struct win_musl::TStringEllipseBase *)v20);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v12 = v14;
  *(_QWORD *)v8 = v14 + v9;
  if ( v8 != -8 )
  {
    if ( (*(_DWORD *)(v8 + 52))-- == 1 )
      *(_DWORD *)(v8 + 48) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  }
  *v7 += v12;
  if ( a4 )
    *a4 = v12;
}

```

## disassembly

```asm
0x180076620  push    rbp
0x180076622  push    rbx
0x180076623  push    rsi
0x180076624  push    rdi
0x180076625  push    r12
0x180076627  push    r13
0x180076629  push    r14
0x18007662b  push    r15
0x18007662d  lea     rbp, [rsp-428h]
0x180076635  sub     rsp, 528h
0x18007663c  mov     [rsp+560h+var_500], 0FFFFFFFFFFFFFFFEh
0x180076645  mov     rax, cs:__security_cookie
0x18007664c  xor     rax, rsp
0x18007664f  mov     [rbp+460h+var_50], rax
0x180076656  mov     r13, r9
0x180076659  mov     r15d, r8d
0x18007665c  mov     r14, rdx
0x18007665f  test    rdx, rdx
0x180076662  jz      loc_180076756
0x180076668  xor     eax, eax
0x18007666a  mov     [rsp+560h+var_514], eax
0x18007666e  mov     rsi, [rcx+8]
0x180076672  mov     rdi, [rsi+10h]
0x180076676  mov     r12, [rsi]
0x180076679  lea     rbx, [rdi+8]
0x18007667d  mov     [rsp+48h], rbx
0x180076682  mov     rcx, rbx; lpCriticalSection
0x180076685  call    cs:__imp_EnterCriticalSection
0x18007668b  mov     ecx, [rbx+2Ch]
0x18007668e  lea     eax, [rcx+1]
0x180076691  mov     [rbx+2Ch], eax
0x180076694  test    ecx, ecx
0x180076696  jnz     short loc_1800766A1
0x180076698  call    cs:__imp_GetCurrentThreadId
0x18007669e  mov     [rbx+28h], eax
0x1800766a1  mov     [rsp+560h+var_510], 1
0x1800766a6  mov     [rsp+560h+var_508], rdi
0x1800766ab  cmp     byte ptr [rdi+48h], 0
0x1800766af  jz      loc_180076795
0x1800766b5  cmp     [rdi], r12
0x1800766b8  jnz     loc_180076742
0x1800766be  mov     [rsp+560h+var_520], 0
0x1800766c6  mov     rcx, [rdi+40h]
0x1800766ca  mov     rax, [rcx]
0x1800766cd  lea     r9, [rsp+560h+var_520]
0x1800766d2  mov     r8d, r15d
0x1800766d5  mov     rdx, r14
0x1800766d8  mov     rax, [rax+18h]
0x1800766dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766e1  mov     r14d, eax
0x1800766e4  test    eax, eax
0x1800766e6  js      loc_1800767DB
0x1800766ec  mov     r14d, [rsp+560h+var_520]
0x1800766f1  lea     rax, [r14+r12]
0x1800766f5  mov     [rdi], rax
0x1800766f8  test    rbx, rbx
0x1800766fb  jz      short loc_180076713
0x1800766fd  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180076701  jnz     short loc_18007670A
0x180076703  mov     dword ptr [rbx+28h], 0
0x18007670a  mov     rcx, rbx; lpCriticalSection
0x18007670d  call    cs:__imp_LeaveCriticalSection
0x180076713  add     [rsi], r14
0x180076716  test    r13, r13
0x180076719  jz      short loc_18007671F
0x18007671b  mov     [r13+0], r14d
0x18007671f  mov     rcx, [rbp+460h+var_50]
0x180076726  xor     rcx, rsp; StackCookie
0x180076729  call    __security_check_cookie
0x18007672e  add     rsp, 528h
0x180076735  pop     r15
0x180076737  pop     r14
0x180076739  pop     r13
0x18007673b  pop     r12
0x18007673d  pop     rdi
0x18007673e  pop     rsi
0x18007673f  pop     rbx
0x180076740  pop     rbp
0x180076741  retn
0x180076742  lea     rcx, [rdi+40h]
0x180076746  xor     r8d, r8d
0x180076749  mov     rdx, r12
0x18007674c  call    ?Seek@Stream@win_dox@@QEAA_K_JW4Enum@SeekOrigin@2@@Z; win_dox::Stream::Seek(__int64,win_dox::SeekOrigin::Enum)
0x180076751  jmp     loc_1800766BE
0x180076756  mov     [rsp+560h+var_528], 0
0x18007675e  lea     rax, aPv; "pv"
0x180076765  mov     [rsp+560h+var_530], rax
0x18007676a  lea     rax, aRead; "Read"
0x180076771  mov     qword ptr [rsp+560h+var_538], rax
0x180076776  lea     rax, aIstream; "IStream"
0x18007677d  mov     qword ptr [rsp+560h+var_540], rax
0x180076782  mov     r9d, 4Eh ; 'N'
0x180076788  lea     rdx, aNoFilename; "(no filename)"
0x18007678f  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180076795  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x18007679c  mov     [rsp+560h+var_530], rax; struct win_musl::TStringEllipseBase *
0x1800767a1  mov     [rsp+560h+var_538], 8000FFFFh; unsigned int
0x1800767a9  mov     [rsp+560h+var_540], 7Fh; unsigned int
0x1800767b1  lea     r9, word_180139126
0x1800767b8  lea     r8, aNoFilename; "(no filename)"
0x1800767bf  lea     rcx, [rsp+560h+pExceptionObject]; this
0x1800767c4  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800767c9  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800767d0  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x1800767d5  call    _CxxThrowException_0
0x1800767db  xor     edx, edx; Val
0x1800767dd  mov     r8d, 400h; Size
0x1800767e3  lea     rcx, [rbp+460h+var_450]; void *
0x1800767e7  call    memset_0
0x1800767ec  mov     r9d, r14d
0x1800767ef  lea     r8, aCallToReadFail; "Call to Read failed with HResult 0x%X."
0x1800767f6  mov     edx, 200h; unsigned __int64
0x1800767fb  lea     rcx, [rbp+460h+var_450]; wchar_t *
0x1800767ff  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180076804  lea     rax, [rbp+460h+var_450]
0x180076808  mov     [rsp+560h+var_530], rax; struct win_musl::TStringEllipseBase *
0x18007680d  mov     [rsp+560h+var_538], r14d; unsigned int
0x180076812  mov     [rsp+560h+var_540], 60h ; '`'; unsigned int
0x18007681a  lea     r9, word_180139126
0x180076821  lea     r8, aNoFilename; "(no filename)"
0x180076828  lea     rcx, [rsp+560h+pExceptionObject]; this
0x18007682d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180076832  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180076839  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18007683e  call    _CxxThrowException_0
```
