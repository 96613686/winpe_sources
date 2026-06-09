# win_musl::DataBuffer::LogicalFileIterator::LogicalFileIterator(win_musl::DataBuffer const &,win_musl::DataBuffer::IteratorType)

- ea: `0x18008a9d0`
- end: `0x18008aba8`
- name: `??0LogicalFileIterator@DataBuffer@win_musl@@QEAA@AEBV12@W4IteratorType@12@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18008a96c`

## callees

- `0x180015660`
- `0x18002db70`
- `0x1800646e8`
- `0x18006554c`
- `0x18008a9d0`
- `0x18008f584`
- `0x1800b6df8`
- `0x1800c0a64`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008aaf6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008aaf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall win_musl::DataBuffer::LogicalFileIterator::LogicalFileIterator(__int64 a1, _QWORD *a2, int a3)
{
  HANDLE FileW; // rax
  __int128 *v6; // rax
  const char *v7; // rdx
  win_musl::detail *v8; // rcx
  unsigned int v9; // r8d
  __int128 v10; // xmm1
  const WCHAR *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  void *v15; // rax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-F0h]
  _QWORD v17[4]; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  v17[2] = -2;
  v17[3] = a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = -1;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = a2[9];
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  if ( a2[9] && !a2[2] && a3 != 1 )
  {
    v11 = (const WCHAR *)(a2 + 4);
    if ( a2[7] >= 8u )
      v11 = *(const WCHAR **)v11;
    FileW = CreateFileW(v11, 0x80000000, 7u, 0, 3u, 0x8000100u, 0);
    v6 = (__int128 *)win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(
                       v17,
                       FileW);
    v10 = *v6;
    *v6 = *(_OWORD *)a1;
    *(_OWORD *)a1 = v10;
    if ( v17[1] != -1 && v17[0] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&int CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<void *>(v17);
    if ( !*(_QWORD *)a1 || *(_QWORD *)(a1 + 8) == -1 )
    {
      dwFlagsAndAttributes = win_musl::detail::GetLastErrorAsFailHR(v8);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x2B9u,
        dwFlagsAndAttributes,
        (struct win_musl::TStringEllipseBase *)L"Unspecified error");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 24);
    v15 = operator new(0x20u, v7, v9);
    v17[0] = v15;
    if ( v15 )
      v15 = (void *)std::vector<unsigned char>::vector<unsigned char>(v15, 28672);
    win_scope::detail::scope_helper<std::vector<unsigned char> *,win_scope::const_policies<win_scope::shared_policies>>::reset(
      a1 + 40,
      v15);
    v12 = *(_QWORD *)(a1 + 48);
    v13 = *(_QWORD *)(v12 + 8);
    if ( v13 )
      v14 = *(_QWORD *)(v12 + 16) - v13;
    else
      v14 = 0;
    *(_DWORD *)(a1 + 56) = v14;
  }
  return a1;
}

```

## disassembly

```asm
0x18008a9d0  mov     rax, rsp
0x18008a9d3  push    rdi
0x18008a9d4  sub     rsp, 110h
0x18008a9db  mov     [rsp+118h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18008a9e4  mov     [rax+18h], rbx
0x18008a9e8  mov     rax, cs:__security_cookie
0x18008a9ef  xor     rax, rsp
0x18008a9f2  mov     [rsp+118h+var_18], rax
0x18008a9fa  mov     rbx, rcx
0x18008a9fd  mov     [rsp+118h+var_C0], rcx
0x18008aa02  mov     qword ptr [rcx], 0
0x18008aa09  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x18008aa11  mov     qword ptr [rcx+10h], 0
0x18008aa19  mov     rax, [rdx+48h]
0x18008aa1d  mov     [rcx+18h], rax
0x18008aa21  mov     qword ptr [rcx+28h], 0
0x18008aa29  mov     qword ptr [rcx+30h], 0
0x18008aa31  mov     dword ptr [rcx+38h], 0
0x18008aa38  cmp     qword ptr [rdx+48h], 0
0x18008aa3d  jz      short loc_18008AA4A
0x18008aa3f  cmp     qword ptr [rdx+10h], 0
0x18008aa44  jz      loc_18008AB70
0x18008aa4a  mov     rax, rbx
0x18008aa4d  mov     rcx, [rsp+118h+var_18]
0x18008aa55  xor     rcx, rsp; StackCookie
0x18008aa58  call    __security_check_cookie
0x18008aa5d  mov     rbx, [rsp+118h+arg_10]
0x18008aa65  add     rsp, 110h
0x18008aa6c  pop     rdi
0x18008aa6d  retn
0x18008aa6e  lea     rcx, [rsp+118h+var_D8]
0x18008aa73  call    ??$close@PEAX@?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@U?$value_const@PEAX$0?0@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAX@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::close<void *>(win_scope::counted_store<void *> *)
0x18008aa78  nop
0x18008aa79  cmp     qword ptr [rbx], 0
0x18008aa7d  jz      short loc_18008AA8A
0x18008aa7f  cmp     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18008aa84  jnz     loc_18008AB7C
0x18008aa8a  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008aa8f  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x18008aa96  mov     [rsp+118h+hTemplateFile], rcx; struct win_musl::TStringEllipseBase *
0x18008aa9b  mov     [rsp+118h+dwFlagsAndAttributes], eax; unsigned int
0x18008aa9f  mov     [rsp+118h+dwCreationDisposition], 2B9h; unsigned int
0x18008aaa7  lea     r9, word_180139126
0x18008aaae  lea     r8, aNoFilename; "(no filename)"
0x18008aab5  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18008aaba  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18008aabf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18008aac6  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18008aacb  call    _CxxThrowException_0
0x18008aad1  mov     [rsp+118h+hTemplateFile], 0; hTemplateFile
0x18008aada  mov     [rsp+118h+dwFlagsAndAttributes], 8000100h; dwFlagsAndAttributes
0x18008aae2  mov     [rsp+118h+dwCreationDisposition], 3; dwCreationDisposition
0x18008aaea  xor     r9d, r9d; lpSecurityAttributes
0x18008aaed  mov     edx, 80000000h; dwDesiredAccess
0x18008aaf2  lea     r8d, [r9+7]; dwShareMode
0x18008aaf6  call    cs:__imp_CreateFileW
0x18008aafc  mov     rdx, rax
0x18008aaff  lea     rcx, [rsp+118h+var_D8]
0x18008ab04  call    ??0?$scope@PEAXU?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@U?$value_const@PEAX$0?0@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@PEAX@Z; win_scope::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>::scope<void *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::value_const<void *,-1>>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>>>>(void *)
0x18008ab09  movups  xmm1, xmmword ptr [rax]
0x18008ab0c  movups  xmm0, xmmword ptr [rbx]
0x18008ab0f  movdqu  xmmword ptr [rax], xmm0
0x18008ab13  movdqu  xmmword ptr [rbx], xmm1
0x18008ab17  cmp     [rsp+118h+var_D0], 0FFFFFFFFFFFFFFFFh
0x18008ab1d  jz      loc_18008AA79
0x18008ab23  cmp     [rsp+118h+var_D8], 0
0x18008ab29  jz      loc_18008AA79
0x18008ab2f  jmp     loc_18008AA6E
0x18008ab34  lea     rcx, [rdx+20h]; lpFileName
0x18008ab38  cmp     qword ptr [rdx+38h], 8
0x18008ab3d  jb      short loc_18008AAD1
0x18008ab3f  mov     rcx, [rcx]
0x18008ab42  jmp     short loc_18008AAD1
0x18008ab44  mov     rdx, rax
0x18008ab47  lea     rcx, [rbx+28h]
0x18008ab4b  call    ?reset@?$scope_helper@PEAV?$vector@EV?$allocator@E@std@@@std@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$vector@EV?$allocator@E@std@@@std@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; win_scope::detail::scope_helper<std::vector<uchar> *,win_scope::const_policies<win_scope::shared_policies>>::reset(win_scope::scope<std::vector<uchar> *,win_scope::const_policies<win_scope::shared_policies>> &,std::vector<uchar> *)
0x18008ab50  mov     rax, [rbx+30h]
0x18008ab54  mov     rcx, [rax+8]
0x18008ab58  test    rcx, rcx
0x18008ab5b  jnz     short loc_18008AB67
0x18008ab5d  xor     eax, eax
0x18008ab5f  mov     [rbx+38h], eax
0x18008ab62  jmp     loc_18008AA4A
0x18008ab67  mov     rax, [rax+10h]
0x18008ab6b  sub     rax, rcx
0x18008ab6e  jmp     short loc_18008AB5F
0x18008ab70  cmp     r8d, 1
0x18008ab74  jz      loc_18008AA4A
0x18008ab7a  jmp     short loc_18008AB34
0x18008ab7c  mov     rax, [rbx+18h]
0x18008ab80  mov     [rbx+20h], rax
0x18008ab84  mov     ecx, 20h ; ' '; unsigned __int64
0x18008ab89  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18008ab8e  mov     [rsp+118h+var_D8], rax
0x18008ab93  test    rax, rax
0x18008ab96  jz      short loc_18008AB44
0x18008ab98  mov     edx, 7000h
0x18008ab9d  mov     rcx, rax
0x18008aba0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z; std::vector<uchar>::vector<uchar>(unsigned __int64)
0x18008aba5  jmp     short loc_18008AB44
```
