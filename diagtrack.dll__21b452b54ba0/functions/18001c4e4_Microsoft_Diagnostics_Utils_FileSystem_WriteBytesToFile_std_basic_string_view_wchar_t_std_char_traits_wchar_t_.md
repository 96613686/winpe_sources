# Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,gsl::span<gsl::byte const,-1>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18001c4e4`
- end: `0x18001c7fd`
- name: `?WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z`
- size: `793`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b434`
- `0x18001dc38`
- `0x18018c9e4`
- `0x18018cce4`
- `0x1802549f8`

## callees

- `0x18001c4e4`
- `0x18001c804`
- `0x18002be90`
- `0x18002df00`
- `0x180064e34`
- `0x180064e8c`
- `0x18008abf4`
- `0x1800bc658`
- `0x1800f9c3c`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c69e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c767`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c58e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c7ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c58e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c7ba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c6fb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c6fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c67d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c67d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c63e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c63e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v5; // r8
  const WCHAR *v6; // rcx
  char *FileW; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // rcx
  BOOL v11; // ebx
  signed int v12; // eax
  const WCHAR *v14; // rcx
  HANDLE v15; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-79h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-79h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-79h]
  unsigned int v19; // [rsp+40h] [rbp-59h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-51h] BYREF
  __int64 v21; // [rsp+50h] [rbp-49h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-39h] BYREF
  char v24; // [rsp+70h] [rbp-29h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-21h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+90h] [rbp-9h] BYREF
  __int128 v27; // [rsp+A0h] [rbp+7h]
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+B0h] [rbp+17h] BYREF
  __int128 v29; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v19 = 0;
  NumberOfBytesWritten = 0;
  v21 = -1;
  *(_OWORD *)lpFileName = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t *>(lpFileName, *(const void **)a1, *(_QWORD *)(a1 + 8));
  v23[0] = &v19;
  v23[1] = lpFileName;
  v24 = 1;
  v5 = *(_QWORD *)(a3 + 8);
  if ( v5 )
  {
    SecurityDescriptor = 0;
    *(_OWORD *)StringSecurityDescriptor = 0;
    v29 = 0;
    std::wstring::_Construct<1,wchar_t *>(StringSecurityDescriptor, *(const void **)a3, v5);
    v10 = (const WCHAR *)StringSecurityDescriptor;
    if ( *((_QWORD *)&v29 + 1) > 7u )
      v10 = StringSecurityDescriptor[0];
    v11 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v10, 1u, &SecurityDescriptor, 0);
    std::wstring::_Tidy_deallocate(StringSecurityDescriptor);
    if ( !v11 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x257,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
             (const char *)0x53A,
             dwCreationDisposition);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      v24 = 0;
      `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile'::`2'::_lambda_1_::operator()(v23);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v9;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v14 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v27 + 1) > 7u )
      v14 = lpFileName[0];
    v15 = CreateFileW(v14, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v21,
      v15);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&SecurityDescriptor);
    FileW = (char *)v21;
  }
  else
  {
    v6 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v27 + 1) > 7u )
      v6 = lpFileName[0];
    FileW = (char *)CreateFileW(v6, 0x40000000u, 0, 0, 2u, 0x80u, *(HANDLE *)(a3 + 8));
    v21 = (__int64)FileW;
  }
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v19 = v9;
    if ( (v9 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)v9,
        dwCreationDispositiona);
    v24 = 0;
    `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile'::`2'::_lambda_1_::operator()(v23);
    std::wstring::_Tidy_deallocate(lpFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
    return v9;
  }
  if ( !WriteFile(FileW, *(LPCVOID *)(a2 + 8), *(_DWORD *)a2, &NumberOfBytesWritten, 0) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    v19 = v9;
    if ( (v9 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x281,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)v9,
        dwCreationDispositionb);
    v24 = 0;
    `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile'::`2'::_lambda_1_::operator()(v23);
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    return v9;
  }
  v24 = 0;
  `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile'::`2'::_lambda_1_::operator()(v23);
  std::wstring::_Tidy_deallocate(lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x18001c4e4  mov     [rsp-8+arg_18], rbx
0x18001c4e9  push    rbp
0x18001c4ea  push    rsi
0x18001c4eb  push    rdi
0x18001c4ec  lea     rbp, [rsp-47h]
0x18001c4f1  sub     rsp, 0E0h
0x18001c4f8  mov     rax, cs:__security_cookie
0x18001c4ff  xor     rax, rsp
0x18001c502  mov     [rbp+57h+var_20], rax
0x18001c506  mov     rbx, r8
0x18001c509  mov     rsi, rdx
0x18001c50c  mov     [rbp+57h+var_B0], 0
0x18001c513  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18001c51a  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x18001c522  xorps   xmm0, xmm0
0x18001c525  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18001c529  xorps   xmm1, xmm1
0x18001c52c  movdqu  [rbp+57h+var_50], xmm1
0x18001c531  mov     r8, [rcx+8]
0x18001c535  mov     rdx, [rcx]
0x18001c538  lea     rcx, [rbp+57h+lpFileName]
0x18001c53c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18001c541  nop
0x18001c542  lea     rax, [rbp+57h+var_B0]
0x18001c546  mov     [rbp+57h+var_90], rax
0x18001c54a  lea     rax, [rbp+57h+lpFileName]
0x18001c54e  mov     [rbp+57h+var_88], rax
0x18001c552  mov     [rbp+57h+var_80], 1
0x18001c556  mov     r8, [rbx+8]; dwShareMode
0x18001c55a  test    r8, r8
0x18001c55d  jnz     loc_18001C602
0x18001c563  lea     rcx, [rbp+57h+lpFileName]
0x18001c567  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18001c56c  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18001c571  mov     [rsp+0F0h+hTemplateFile], r8; hTemplateFile
0x18001c576  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001c57e  mov     [rsp+0F0h+dwCreationDisposition], 2; int
0x18001c586  xor     r9d, r9d; lpSecurityAttributes
0x18001c589  mov     edx, 40000000h; dwDesiredAccess
0x18001c58e  call    cs:__imp_CreateFileW
0x18001c594  mov     rdi, rax
0x18001c597  mov     [rbp+57h+var_A0], rax
0x18001c59b  lea     rcx, [rdi+1]
0x18001c59f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001c5a6  jnz     loc_18001C6E4
0x18001c5ac  call    cs:__imp_GetLastError
0x18001c5b2  mov     ebx, eax
0x18001c5b4  test    eax, eax
0x18001c5b6  jg      loc_18001C748
0x18001c5bc  mov     [rbp+57h+var_B0], ebx
0x18001c5bf  test    ebx, ebx
0x18001c5c1  jns     short loc_18001C5DC
0x18001c5c3  mov     rcx, [rbp+5Fh]; this
0x18001c5c7  mov     r9d, ebx; char *
0x18001c5ca  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18001c5d1  mov     edx, 27Bh; void *
0x18001c5d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5db  nop
0x18001c5dc  mov     [rbp+57h+var_80], 0
0x18001c5e0  lea     rcx, [rbp+57h+var_90]
0x18001c5e4  call    ??R_lambda_1_@?1??WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::wstring_view,gsl::span<gsl::byte const,-1>,std::wstring_view)'::`2'::_lambda_1_::operator()(void)
0x18001c5e9  nop
0x18001c5ea  lea     rcx, [rbp+57h+lpFileName]
0x18001c5ee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c5f3  nop
0x18001c5f4  lea     rcx, [rbp+57h+var_A0]
0x18001c5f8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001c5fd  jmp     loc_18001C6E0
0x18001c602  mov     [rbp+57h+SecurityDescriptor], 0
0x18001c60a  xorps   xmm0, xmm0
0x18001c60d  movups  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x18001c611  xorps   xmm1, xmm1
0x18001c614  movdqu  [rbp+57h+var_30], xmm1
0x18001c619  mov     rdx, [rbx]
0x18001c61c  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x18001c620  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18001c625  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x18001c629  cmp     qword ptr [rbp+57h+var_30+8], 7
0x18001c62e  cmova   rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001c633  xor     r9d, r9d; SecurityDescriptorSize
0x18001c636  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001c63a  lea     edx, [r9+1]; StringSDRevision
0x18001c63e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c644  mov     ebx, eax
0x18001c646  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x18001c64a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c64f  test    ebx, ebx
0x18001c651  jnz     loc_18001C76F
0x18001c657  mov     rcx, [rbp+5Fh]; this
0x18001c65b  mov     r9d, 53Ah; char *
0x18001c661  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18001c668  mov     edx, 257h; void *
0x18001c66d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c672  mov     ebx, eax
0x18001c674  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18001c678  test    rcx, rcx
0x18001c67b  jz      short loc_18001C684
0x18001c67d  call    cs:__imp_LocalFree
0x18001c683  nop
0x18001c684  mov     [rbp+57h+var_80], 0
0x18001c688  lea     rcx, [rbp+57h+var_90]
0x18001c68c  call    ??R_lambda_1_@?1??WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::wstring_view,gsl::span<gsl::byte const,-1>,std::wstring_view)'::`2'::_lambda_1_::operator()(void)
0x18001c691  nop
0x18001c692  lea     rcx, [rbp+57h+lpFileName]
0x18001c696  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c69b  nop
0x18001c69c  jmp     short loc_18001C6E0
0x18001c69e  call    cs:__imp_GetLastError
0x18001c6a4  mov     ebx, eax
0x18001c6a6  test    eax, eax
0x18001c6a8  jle     short loc_18001C6B3
0x18001c6aa  movzx   ebx, ax
0x18001c6ad  or      ebx, 80070000h
0x18001c6b3  mov     [rbp+57h+var_B0], ebx
0x18001c6b6  test    ebx, ebx
0x18001c6b8  js      loc_18001C7DF
0x18001c6be  mov     [rbp+57h+var_80], 0
0x18001c6c2  lea     rcx, [rbp+57h+var_90]
0x18001c6c6  call    ??R_lambda_1_@?1??WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::wstring_view,gsl::span<gsl::byte const,-1>,std::wstring_view)'::`2'::_lambda_1_::operator()(void)
0x18001c6cb  nop
0x18001c6cc  lea     rcx, [rbp+57h+lpFileName]
0x18001c6d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c6d5  nop
0x18001c6d6  lea     rcx, [rdi-1]
0x18001c6da  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001c6de  jbe     short loc_18001C756
0x18001c6e0  mov     eax, ebx
0x18001c6e2  jmp     short loc_18001C729
0x18001c6e4  mov     r8d, [rsi]; nNumberOfBytesToWrite
0x18001c6e7  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; int
0x18001c6f0  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001c6f4  mov     rdx, [rsi+8]; lpBuffer
0x18001c6f8  mov     rcx, rdi; hFile
0x18001c6fb  call    cs:__imp_WriteFile
0x18001c701  test    eax, eax
0x18001c703  jz      short loc_18001C69E
0x18001c705  mov     [rbp+57h+var_80], 0
0x18001c709  lea     rcx, [rbp+57h+var_90]
0x18001c70d  call    ??R_lambda_1_@?1??WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::wstring_view,gsl::span<gsl::byte const,-1>,std::wstring_view)'::`2'::_lambda_1_::operator()(void)
0x18001c712  nop
0x18001c713  lea     rcx, [rbp+57h+lpFileName]
0x18001c717  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c71c  nop
0x18001c71d  lea     rax, [rdi-1]
0x18001c721  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c725  jbe     short loc_18001C764
0x18001c727  xor     eax, eax
0x18001c729  mov     rcx, [rbp+57h+var_20]
0x18001c72d  xor     rcx, rsp; StackCookie
0x18001c730  call    __security_check_cookie
0x18001c735  mov     rbx, [rsp+0F0h+arg_18]
0x18001c73d  add     rsp, 0E0h
0x18001c744  pop     rdi
0x18001c745  pop     rsi
0x18001c746  pop     rbp
0x18001c747  retn
0x18001c748  movzx   ebx, ax
0x18001c74b  or      ebx, 80070000h
0x18001c751  jmp     loc_18001C5BC
0x18001c756  mov     rcx, rdi; hObject
0x18001c759  call    cs:__imp_CloseHandle
0x18001c75f  jmp     loc_18001C6E0
0x18001c764  mov     rcx, rdi; hObject
0x18001c767  call    cs:__imp_CloseHandle
0x18001c76d  jmp     short loc_18001C727
0x18001c76f  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18001c777  mov     rax, [rbp+57h+SecurityDescriptor]
0x18001c77b  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001c77f  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18001c787  lea     rcx, [rbp+57h+lpFileName]
0x18001c78b  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18001c790  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18001c795  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18001c79e  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001c7a6  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x18001c7ae  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18001c7b2  xor     r8d, r8d; dwShareMode
0x18001c7b5  mov     edx, 40000000h; dwDesiredAccess
0x18001c7ba  call    cs:__imp_CreateFileW
0x18001c7c0  mov     rdx, rax
0x18001c7c3  lea     rcx, [rbp+57h+var_A0]
0x18001c7c7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001c7cc  nop
0x18001c7cd  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18001c7d1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18001c7d6  mov     rdi, [rbp+57h+var_A0]
0x18001c7da  jmp     loc_18001C59B
0x18001c7df  mov     rcx, [rbp+5Fh]; this
0x18001c7e3  mov     r9d, ebx; char *
0x18001c7e6  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18001c7ed  mov     edx, 281h; void *
0x18001c7f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7f7  jmp     loc_18001C6BE
```
