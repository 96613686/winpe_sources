# Microsoft::Basix::Dct::WindowsNamedPipeDCT::InternalOpen(void)

- ea: `0x180140930`
- end: `0x180140d84`
- name: `?InternalOpen@WindowsNamedPipeDCT@Dct@Basix@Microsoft@@MEAAXXZ`
- size: `1108`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WindowsNamedPipeDCT *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180015bb8`
- `0x180024700`
- `0x180027b84`
- `0x180037690`
- `0x1800d96dc`
- `0x18013ea18`
- `0x180140930`
- `0x1801418b8`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x180313058`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180330b40`
- `0x180344b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180140c5b`
- `KERNEL32!GetLastError` at `0x180140d16`
- `KERNEL32!GetLastError` at `0x180140c5b`
- `KERNEL32!GetLastError` at `0x180140d16`
- `KERNEL32!CreateFileW` at `0x180140a1b`
- `KERNEL32!CreateFileW` at `0x180140a1b`
- `KERNEL32!CreateThreadpoolIo` at `0x180140a6e`
- `KERNEL32!CreateThreadpoolIo` at `0x180140a6e`

## string_xrefs

- `0x180140c42`: `Failed to open a named pipe`
- `0x180140cfd`: `Failed to associate I/O completion with named pipe.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall Microsoft::Basix::Dct::WindowsNamedPipeDCT::InternalOpen(
        Microsoft::Basix::Dct::WindowsNamedPipeDCT *this)
{
  char *v2; // rbx
  HANDLE *v3; // rsi
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  HANDLE FileW; // r14
  PTP_IO ThreadpoolIo; // rax
  volatile signed __int32 *v8; // rbx
  __m128i v9; // xmm6
  _QWORD *v10; // rax
  void *v11; // r9
  volatile signed __int32 *v12; // xmm6_8
  Microsoft::Basix *v13; // rcx
  const struct std::error_category *v14; // rbx
  signed int LastError; // eax
  unsigned int v16; // edx
  Microsoft::Basix *v17; // rcx
  const struct std::error_category *v18; // rbx
  signed int v19; // eax
  unsigned int v20; // edx
  _Thrd_t v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int ThrdAddr_8[4]; // [rsp+50h] [rbp-B0h] BYREF
  _Thrd_t v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v24[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+170h] [rbp+70h] BYREF

  v2 = (char *)this + 1112;
  if ( Mtx_lock((Microsoft::Basix::Dct::WindowsNamedPipeDCT *)((char *)this + 1112)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v3 = (HANDLE *)((char *)this + 1104);
  if ( !*((_QWORD *)this + 138) || *v3 == (HANDLE)-1LL )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 136) + 8LL))(*((_QWORD *)this + 136), v24);
    Microsoft::Basix::ToU16String(lpFileName, v4);
    std::string::_Tidy_deallocate(v24);
    v5 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v5 = lpFileName[0];
    FileW = CreateFileW(v5, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
    v23[0]._Hnd = 0;
    if ( *v3 && *v3 != (HANDLE)-1LL )
      Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free((void **)this + 138);
    *v3 = FileW;
    if ( !FileW || FileW == (HANDLE)-1LL )
    {
      std::string::string(v25, (const char *)&Str1);
      std::string::string(v23, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsnamedpipedct.cpp");
      std::string::string(v26, "Failed to open a named pipe");
      v14 = Microsoft::Basix::WindowsCategory(v13);
      LastError = GetLastError();
      v16 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v16 = LastError;
      v24[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)ThrdAddr_8, v16, v14);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)v24,
        (unsigned int)v26,
        (unsigned int)v23,
        381,
        (__int64)v25);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    std::basic_string<short>::_Tidy_deallocate(lpFileName);
  }
  ThreadpoolIo = CreateThreadpoolIo(
                   *v3,
                   Microsoft::Basix::Dct::WindowsNamedPipeDCT::STATIC_CompleteNamedPipeIo,
                   this,
                   0);
  *((_QWORD *)this + 149) = ThreadpoolIo;
  if ( !ThreadpoolIo )
  {
    std::string::string(lpFileName, (const char *)&Str1);
    std::string::string(v23, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsnamedpipedct.cpp");
    std::string::string(v25, "Failed to associate I/O completion with named pipe.");
    v18 = Microsoft::Basix::WindowsCategory(v17);
    v19 = GetLastError();
    v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v19 <= 0 )
      v20 = v19;
    *(_OWORD *)ThrdAddr_8 = *(_OWORD *)std::error_code::error_code((std::error_code *)v24, v20, v18);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)ThrdAddr_8,
      (unsigned int)v25,
      (unsigned int)v23,
      392,
      (__int64)lpFileName);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  Mtx_unlock((_Mtx_t)v2);
  *(_OWORD *)ThrdAddr_8 = 0;
  Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::WindowsNamedPipeDCT>(
    (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
    ThrdAddr_8);
  v8 = *(volatile signed __int32 **)&ThrdAddr_8[2];
  if ( *(_QWORD *)&ThrdAddr_8[2] )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&ThrdAddr_8[2] + 8LL));
  v9 = *(__m128i *)ThrdAddr_8;
  v24[0] = *(_OWORD *)ThrdAddr_8;
  v10 = operator new(0x10u);
  v11 = v10;
  if ( v10 )
  {
    *v10 = v9.m128i_i64[0];
    v10[1] = v8;
    v9 = 0;
    v24[0] = 0;
  }
  else
  {
    v11 = 0;
  }
  v23[0]._Hnd = v11;
  v21._Hnd = (void *)beginthreadex(
                       0,
                       0,
                       std::thread::_Invoke_std::tuple__lambda_200ae6a6b0066f7b3ce55aa093f1463c____0_,
                       v11,
                       0,
                       &v21._Id);
  if ( !v21._Hnd )
  {
    v21._Id = 0;
    std::_Throw_Cpp_error(6);
  }
  if ( !v21._Id || (v23[0] = v21, Thrd_detach(v23)) )
    std::_Throw_Cpp_error(1);
  v21 = 0;
  v12 = (volatile signed __int32 *)_mm_srli_si128(v9, 8).m128i_u64[0];
  if ( v12 )
  {
    if ( !_InterlockedDecrement(v12 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v8 && !_InterlockedDecrement(v8 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    if ( !_InterlockedDecrement(v8 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  }
}

```

## disassembly

```asm
0x180140930  mov     rax, rsp
0x180140933  mov     [rax+10h], rbx
0x180140937  mov     [rax+18h], rsi
0x18014093b  mov     [rax+20h], rdi
0x18014093f  push    rbp
0x180140940  push    r12
0x180140942  push    r14
0x180140944  lea     rbp, [rax-0C8h]
0x18014094b  mov     eax, 1B0h
0x180140950  call    _alloca_probe
0x180140955  sub     rsp, rax
0x180140958  movaps  [rsp+1C0h+var_28+8], xmm6
0x180140960  mov     rax, cs:__security_cookie
0x180140967  xor     rax, rsp
0x18014096a  mov     [rbp+0C0h+var_30], rax
0x180140971  mov     rdi, rcx
0x180140974  lea     rbx, [rcx+458h]
0x18014097b  mov     qword ptr [rsp+1C0h+var_188+8], rbx
0x180140980  mov     rcx, rbx; _Mtx_t
0x180140983  call    _Mtx_lock
0x180140988  test    eax, eax
0x18014098a  jnz     loc_180140CBD
0x180140990  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180140997  jz      loc_180140CC8
0x18014099d  lea     rsi, [rdi+450h]
0x1801409a4  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801409a8  cmp     qword ptr [rsi], 0
0x1801409ac  jz      short loc_1801409B7
0x1801409ae  cmp     [rsi], r12
0x1801409b1  jnz     loc_180140A5E
0x1801409b7  mov     rcx, [rdi+440h]
0x1801409be  mov     rax, [rcx]
0x1801409c1  lea     rdx, [rbp+0C0h+var_140]
0x1801409c5  mov     rax, [rax+8]
0x1801409c9  call    cs:__guard_dispatch_icall_fptr
0x1801409cf  nop
0x1801409d0  mov     rdx, rax
0x1801409d3  lea     rcx, [rbp+0C0h+lpFileName]
0x1801409d7  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x1801409dc  nop
0x1801409dd  lea     rcx, [rbp+0C0h+var_140]
0x1801409e1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801409e6  lea     rcx, [rbp+0C0h+lpFileName]
0x1801409ea  cmp     [rbp+0C0h+var_38], 7
0x1801409f2  cmova   rcx, [rbp+0C0h+lpFileName]; lpFileName
0x1801409f7  mov     [rsp+1C0h+hTemplateFile], 0; hTemplateFile
0x180140a00  mov     [rsp+1C0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180140a08  mov     [rsp+1C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180140a10  xor     r9d, r9d; lpSecurityAttributes
0x180140a13  xor     r8d, r8d; dwShareMode
0x180140a16  mov     edx, 0C0000000h; dwDesiredAccess
0x180140a1b  call    cs:__imp_CreateFileW
0x180140a21  mov     r14, rax
0x180140a24  mov     qword ptr [rsp+1C0h+var_168._Id], 0
0x180140a2d  cmp     qword ptr [rsi], 0
0x180140a31  jz      short loc_180140A40
0x180140a33  cmp     [rsi], r12
0x180140a36  jz      short loc_180140A40
0x180140a38  mov     rcx, rsi; void **
0x180140a3b  call    ?Free@WindowsGenericHandlePolicy@Details@WinUtils@Basix@Microsoft@@SAXAEAPEAX@Z; Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(void * &)
0x180140a40  mov     [rsi], r14
0x180140a43  test    r14, r14
0x180140a46  jz      loc_180140C1F
0x180140a4c  cmp     r14, r12
0x180140a4f  jz      loc_180140C1F
0x180140a55  lea     rcx, [rbp+0C0h+lpFileName]
0x180140a59  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x180140a5e  xor     r9d, r9d; pcbe
0x180140a61  mov     r8, rdi; pv
0x180140a64  lea     rdx, ?STATIC_CompleteNamedPipeIo@WindowsNamedPipeDCT@Dct@Basix@Microsoft@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180140a6b  mov     rcx, [rsi]; fl
0x180140a6e  call    cs:__imp_CreateThreadpoolIo
0x180140a74  mov     [rdi+4A8h], rax
0x180140a7b  test    rax, rax
0x180140a7e  jz      loc_180140CDA
0x180140a84  mov     rcx, rbx; _Mtx_t
0x180140a87  call    _Mtx_unlock
0x180140a8c  xorps   xmm0, xmm0
0x180140a8f  movups  xmmword ptr [rsp+1C0h+ThrdAddr+8], xmm0
0x180140a94  mov     rax, [rdi+8]
0x180140a98  movsxd  rcx, dword ptr [rax+4]
0x180140a9c  add     rcx, 8
0x180140aa0  add     rcx, rdi
0x180140aa3  lea     rdx, [rsp+1C0h+ThrdAddr+8]
0x180140aa8  call    ??$GetSharedPtr@VWindowsNamedPipeDCT@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VWindowsNamedPipeDCT@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::WindowsNamedPipeDCT>(void)
0x180140aad  nop
0x180140aae  mov     rbx, [rsp+1C0h+var_168._Hnd]
0x180140ab3  test    rbx, rbx
0x180140ab6  jz      short loc_180140ABC
0x180140ab8  lock inc dword ptr [rbx+8]
0x180140abc  movaps  xmm6, xmmword ptr [rsp+1C0h+ThrdAddr+8]
0x180140ac1  movdqa  [rbp+0C0h+var_140], xmm6
0x180140ac6  mov     ecx, 10h; Size
0x180140acb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180140ad0  mov     r9, rax
0x180140ad3  test    rax, rax
0x180140ad6  jz      short loc_180140AEB
0x180140ad8  movq    qword ptr [rax], xmm6
0x180140add  mov     [rax+8], rbx
0x180140ae1  xorps   xmm6, xmm6
0x180140ae4  movdqa  [rbp+0C0h+var_140], xmm6
0x180140ae9  jmp     short loc_180140AEE
0x180140aeb  xor     r9d, r9d; ArgList
0x180140aee  mov     qword ptr [rsp+1C0h+var_168._Id], r9
0x180140af3  lea     rax, [rsp+1C0h+ThrdAddr]
0x180140af8  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rax; ThrdAddr
0x180140afd  mov     [rsp+1C0h+dwCreationDisposition], 0; InitFlag
0x180140b05  lea     r8, std__thread___Invoke_std__tuple__lambda_200ae6a6b0066f7b3ce55aa093f1463c____0_; StartAddress
0x180140b0c  xor     edx, edx; StackSize
0x180140b0e  xor     ecx, ecx; Security
0x180140b10  call    _beginthreadex
0x180140b15  mov     qword ptr [rsp+1C0h+var_188+8], rax
0x180140b1a  test    rax, rax
0x180140b1d  jz      loc_180140C0C
0x180140b23  cmp     [rsp+1C0h+ThrdAddr], 0
0x180140b28  jz      loc_180140D79
0x180140b2e  movaps  xmm0, [rsp+1C0h+var_188+8]
0x180140b33  movdqa  xmmword ptr [rsp+1C0h+var_168._Id], xmm0
0x180140b39  lea     rcx, [rsp+1C0h+var_168._Id]; _Thrd_t
0x180140b3e  call    _Thrd_detach
0x180140b43  test    eax, eax
0x180140b45  jnz     loc_180140D79
0x180140b4b  xorps   xmm0, xmm0
0x180140b4e  movdqa  [rsp+1C0h+var_188+8], xmm0
0x180140b54  psrldq  xmm6, 8
0x180140b59  movq    rdi, xmm6
0x180140b5e  test    rdi, rdi
0x180140b61  jz      short loc_180140B9D
0x180140b63  mov     eax, r12d
0x180140b66  lock xadd [rdi+8], eax
0x180140b6b  add     eax, r12d
0x180140b6e  jnz     short loc_180140B9D
0x180140b70  mov     rax, [rdi]
0x180140b73  mov     rcx, rdi
0x180140b76  mov     rax, [rax]
0x180140b79  call    cs:__guard_dispatch_icall_fptr
0x180140b7f  mov     eax, r12d
0x180140b82  lock xadd [rdi+0Ch], eax
0x180140b87  add     eax, r12d
0x180140b8a  jnz     short loc_180140B9D
0x180140b8c  mov     rax, [rdi]
0x180140b8f  mov     rcx, rdi
0x180140b92  mov     rax, [rax+8]
0x180140b96  call    cs:__guard_dispatch_icall_fptr
0x180140b9c  nop
0x180140b9d  test    rbx, rbx
0x180140ba0  jz      short loc_180140BDB
0x180140ba2  mov     eax, r12d
0x180140ba5  lock xadd [rbx+8], eax
0x180140baa  add     eax, r12d
0x180140bad  jnz     short loc_180140BDB
0x180140baf  mov     rax, [rbx]
0x180140bb2  mov     rcx, rbx
0x180140bb5  mov     rax, [rax]
0x180140bb8  call    cs:__guard_dispatch_icall_fptr
0x180140bbe  mov     eax, r12d
0x180140bc1  lock xadd [rbx+0Ch], eax
0x180140bc6  add     eax, r12d
0x180140bc9  jnz     short loc_180140BDB
0x180140bcb  mov     rax, [rbx]
0x180140bce  mov     rcx, rbx
0x180140bd1  mov     rax, [rax+8]
0x180140bd5  call    cs:__guard_dispatch_icall_fptr
0x180140bdb  mov     rcx, [rbp+0C0h+var_30]
0x180140be2  xor     rcx, rsp; StackCookie
0x180140be5  call    __security_check_cookie
0x180140bea  lea     r11, [rsp+1C0h+var_10]
0x180140bf2  mov     rbx, [r11+28h]
0x180140bf6  mov     rsi, [r11+30h]
0x180140bfa  mov     rdi, [r11+38h]
0x180140bfe  movaps  xmm6, xmmword ptr [r11-10h]
0x180140c03  mov     rsp, r11
0x180140c06  pop     r14
0x180140c08  pop     r12
0x180140c0a  pop     rbp
0x180140c0b  retn
0x180140c0c  mov     [rsp+1C0h+ThrdAddr], 0
0x180140c14  mov     ecx, 6; int
0x180140c19  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180140c1f  lea     rdx, Str1
0x180140c26  lea     rcx, [rbp+0C0h+var_120]
0x180140c2a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180140c2f  nop
0x180140c30  lea     rdx, aCW1SSrcLibbasi_54; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180140c37  lea     rcx, [rsp+1C0h+var_168._Id]
0x180140c3c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180140c41  nop
0x180140c42  lea     rdx, aFailedToOpenAN; "Failed to open a named pipe"
0x180140c49  lea     rcx, [rbp+0C0h+var_100]
0x180140c4d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180140c52  nop
0x180140c53  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180140c58  mov     rbx, rax
0x180140c5b  call    cs:__imp_GetLastError
0x180140c61  movzx   edx, ax
0x180140c64  or      edx, 80070000h
0x180140c6a  test    eax, eax
0x180140c6c  cmovle  edx, eax; int
0x180140c6f  mov     r8, rbx; struct std::error_category *
0x180140c72  lea     rcx, [rsp+1C0h+ThrdAddr+8]; this
0x180140c77  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180140c7c  movups  xmm0, xmmword ptr [rax]
0x180140c7f  movdqu  [rbp+0C0h+var_140], xmm0
0x180140c84  lea     rax, [rbp+0C0h+var_120]
0x180140c88  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rax
0x180140c8d  mov     qword ptr [rsp+1C0h+dwCreationDisposition], 17Dh
0x180140c96  lea     r9, [rsp+1C0h+var_168._Id]
0x180140c9b  lea     r8, [rbp+0C0h+var_100]
0x180140c9f  lea     rdx, [rbp+0C0h+var_140]
0x180140ca3  lea     rcx, [rbp+0C0h+pExceptionObject]
0x180140ca7  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180140cac  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180140cb3  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x180140cb7  call    _CxxThrowException
0x180140cbd  mov     ecx, 5; int
0x180140cc2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180140cc8  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180140ccf  mov     ecx, 6; int
0x180140cd4  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180140cda  lea     rdx, Str1
0x180140ce1  lea     rcx, [rbp+0C0h+lpFileName]
0x180140ce5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180140cea  nop
0x180140ceb  lea     rdx, aCW1SSrcLibbasi_54; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180140cf2  lea     rcx, [rsp+1C0h+var_168._Id]
0x180140cf7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180140cfc  nop
0x180140cfd  lea     rdx, aFailedToAssoci_0; "Failed to associate I/O completion with"...
0x180140d04  lea     rcx, [rbp+0C0h+var_120]
0x180140d08  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180140d0d  nop
0x180140d0e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180140d13  mov     rbx, rax
0x180140d16  call    cs:__imp_GetLastError
0x180140d1c  movzx   edx, ax
0x180140d1f  or      edx, 80070000h
0x180140d25  test    eax, eax
0x180140d27  cmovle  edx, eax; int
0x180140d2a  mov     r8, rbx; struct std::error_category *
0x180140d2d  lea     rcx, [rbp+0C0h+var_140]; this
0x180140d31  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180140d36  movups  xmm0, xmmword ptr [rax]
0x180140d39  movdqu  xmmword ptr [rsp+1C0h+ThrdAddr+8], xmm0
0x180140d3f  lea     rax, [rbp+0C0h+lpFileName]
0x180140d43  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rax
0x180140d48  mov     qword ptr [rsp+1C0h+dwCreationDisposition], 188h
0x180140d51  lea     r9, [rsp+1C0h+var_168._Id]
0x180140d56  lea     r8, [rbp+0C0h+var_120]
0x180140d5a  lea     rdx, [rsp+1C0h+ThrdAddr+8]
0x180140d5f  lea     rcx, [rbp+0C0h+pExceptionObject]
0x180140d63  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180140d68  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180140d6f  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x180140d73  call    _CxxThrowException
0x180140d79  mov     ecx, 1; int
0x180140d7e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
