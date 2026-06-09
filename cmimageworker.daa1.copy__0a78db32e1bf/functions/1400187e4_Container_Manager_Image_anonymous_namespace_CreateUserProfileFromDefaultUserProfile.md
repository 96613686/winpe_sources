# Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile

- ea: `0x1400187e4`
- end: `0x140018d53`
- name: `Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile`
- size: `1391`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140018184`

## callees

- `0x1400020b0`
- `0x140002344`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000898c`
- `0x140008f90`
- `0x14000a9b8`
- `0x14000ad64`
- `0x14000c6e4`
- `0x14000cd84`
- `0x140018588`
- `0x1400187e4`
- `0x140022e90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001889f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001889f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018942`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400188b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400188b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140018956`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140018956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001891e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001891e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018b5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018b5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c89`
- `ntdll!RtlAcquirePrivilege` at `0x14001883a`
- `ntdll!RtlAcquirePrivilege` at `0x14001883a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x140018afb`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x140018afb`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x140018c3d`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x140018c3d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140018bc4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140018bc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140018ad0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140018bfd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140018ad0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140018bfd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140018c1e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140018c1e`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x140018a72`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x140018a72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400189a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400189a8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140018906`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140018906`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile(
        __int64 a1,
        __int64 *a2,
        const WCHAR **a3)
{
  NTSTATUS v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  int v8; // eax
  signed int v9; // ebx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // r13
  void *v14; // r15
  __int64 v15; // rcx
  unsigned __int64 v16; // r14
  SIZE_T v17; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v19; // rdi
  signed int LastError; // eax
  HANDLE v21; // rax
  __int64 v22; // rdx
  const char *v23; // r9
  __int64 v24; // rdx
  HANDLE FileW; // rax
  void *v26; // rbx
  const char *v27; // r9
  signed int v28; // edi
  int v29; // eax
  LPCWSTR *i; // rbx
  DWORD FileAttributesW; // eax
  HANDLE v32; // rdi
  const char *v33; // r9
  const char *v34; // r9
  __int64 v35; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-89h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-89h]
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-69h] BYREF
  _WORD v40[8]; // [rsp+50h] [rbp-59h] BYREF
  PVOID ReturnedState; // [rsp+60h] [rbp-49h] BYREF
  __m128i si128; // [rsp+68h] [rbp-41h] BYREF
  __int64 v43; // [rsp+78h] [rbp-31h]
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp-29h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+88h] [rbp-21h] BYREF
  struct _FILETIME CreationTime; // [rsp+90h] [rbp-19h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-11h] BYREF
  ULONG Privilege[4]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  si128.m128i_i64[0] = a1;
  ReturnedState = 0;
  *(__m128i *)Privilege = _mm_load_si128((const __m128i *)&_xmm);
  v5 = RtlAcquirePrivilege(Privilege, 4u, 2u, &ReturnedState);
  if ( v5 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(retaddr, v6, v7, (const char *)(unsigned int)v5, dwCreationDisposition);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = (unsigned int)v8;
      v11 = 677;
LABEL_64:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)v10,
        dwCreationDisposition);
LABEL_65:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      return (unsigned int)v9;
    }
  }
  v12 = *a2;
  v13 = *a3;
  v14 = 0;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v12 + 2 * v15) );
  v16 = v15 + 171;
  *(_QWORD *)Privilege = 0;
  v17 = 2 * (v15 + 171);
  if ( is_mul_ok(v15 + 171, 2u) )
  {
    ProcessHeap = GetProcessHeap();
    v19 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v17);
    v9 = -2147024882;
    if ( v19 )
    {
      v9 = StringCchPrintfW(
             v19,
             v16,
             L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;FA;;;%s)(A;;0x00100020;;;S-1-15-3-65536-599108337-2355189375-1"
              "353122160-3480128286-3345335107-485756383-4087318168-230526575)",
             v12);
      if ( v9 >= 0 )
      {
        *(_QWORD *)Privilege = 0;
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v19, 1u, (PSECURITY_DESCRIPTOR *)Privilege, 0) )
        {
          v14 = *(void **)Privilege;
          v9 = 0;
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          if ( v9 >= 0 )
            v9 = -2147467259;
        }
      }
      v21 = GetProcessHeap();
      if ( !HeapFree(v21, 0, v19) )
        GetLastError();
    }
  }
  else
  {
    v9 = -2147024362;
  }
  if ( v9 < 0
    || (*(_QWORD *)&SecurityAttributes.nLength = 24,
        SecurityAttributes.lpSecurityDescriptor = v14,
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0,
        v9 = CreateNestedDirectory(v13, &SecurityAttributes),
        LocalFree(v14),
        v9 < 0) )
  {
    v10 = (unsigned int)v9;
    v11 = 682;
    goto LABEL_64;
  }
  lpFileName[0] = v40;
  lpFileName[1] = v40;
  v40[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpFileName,
                           *(_QWORD *)si128.m128i_i64[0],
                           (__int64)(*(_QWORD *)(si128.m128i_i64[0] + 8) - *(_QWORD *)si128.m128i_i64[0]) >> 1) )
  {
    v22 = 686;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( lpFileName[0] != v40 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    v9 = -2147024882;
    goto LABEL_65;
  }
  si128.m128i_i64[0] = (__int64)L"Users\\Default";
  si128.m128i_i64[1] = 13;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpFileName) )
  {
    v22 = 687;
    goto LABEL_24;
  }
  if ( !(unsigned int)CopyProfileDirectoryEx2(lpFileName[0], *a3, 32769, 0, 0, 0) )
  {
    v24 = 696;
LABEL_29:
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v24,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
           v23);
LABEL_58:
    if ( lpFileName[0] != v40 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_65;
  }
  CreationTime = 0;
  LastAccessTime = 0;
  LastWriteTime = 0;
  FileW = CreateFileW(lpFileName[0], 1u, 0, 0, 3u, 0x2000080u, 0);
  v26 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v24 = 714;
    goto LABEL_29;
  }
  if ( !GetFileTime(FileW, &CreationTime, &LastAccessTime, &LastWriteTime) )
  {
    v28 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x2CF,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
            v27);
    if ( v26 )
      CloseHandle(v26);
    if ( lpFileName[0] != v40 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    v9 = v28;
    goto LABEL_65;
  }
  if ( v26 )
    CloseHandle(v26);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v43 = -1;
  v29 = Csl::EnumerateDirectory(a3, 5, &si128);
  v9 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v29,
      dwCreationDispositiona);
LABEL_57:
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
    goto LABEL_58;
  }
  for ( i = (LPCWSTR *)si128.m128i_i64[0]; i != (LPCWSTR *)si128.m128i_i64[1]; i += 4 )
  {
    FileAttributesW = GetFileAttributesW(*i);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      v32 = CreateFileW(*i, 0x100u, 0, 0, 3u, 0x80u, 0);
      if ( v32 == (HANDLE)-1LL )
      {
        v9 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2E8,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
               v33);
        goto LABEL_57;
      }
      if ( !SetFileAttributesW(*i, 0x2002u) )
      {
        v35 = 750;
LABEL_53:
        v9 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v35,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
               v34);
        if ( v32 )
          CloseHandle(v32);
        goto LABEL_57;
      }
      if ( !SetFileTime(v32, &CreationTime, &LastAccessTime, &LastWriteTime) )
      {
        v35 = 758;
        goto LABEL_53;
      }
      if ( v32 )
        CloseHandle(v32);
    }
  }
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
  if ( lpFileName[0] != v40 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  return 0;
}

```

## disassembly

```asm
0x1400187e4  mov     [rsp-8+arg_18], rbx
0x1400187e9  push    rbp
0x1400187ea  push    rsi
0x1400187eb  push    rdi
0x1400187ec  push    r12
0x1400187ee  push    r13
0x1400187f0  push    r14
0x1400187f2  push    r15
0x1400187f4  lea     rbp, [rsp-27h]
0x1400187f9  sub     rsp, 0D0h
0x140018800  mov     rax, cs:__security_cookie
0x140018807  xor     rax, rsp
0x14001880a  mov     [rbp+57h+var_40], rax
0x14001880e  mov     r12, r8
0x140018811  mov     rsi, rdx
0x140018814  mov     qword ptr [rbp+57h+var_98], rcx
0x140018818  xor     edi, edi
0x14001881a  mov     [rbp+57h+ReturnedState], rdi
0x14001881e  movdqa  xmm0, cs:__xmm@00000009000000080000001200000011
0x140018826  movdqu  xmmword ptr [rbp+57h+Privilege], xmm0
0x14001882b  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x14001882f  lea     edx, [rdi+4]; NumPriv
0x140018832  lea     r8d, [rdi+2]; Flags
0x140018836  lea     rcx, [rbp+57h+Privilege]; Privilege
0x14001883a  call    cs:__imp_RtlAcquirePrivilege
0x140018841  nop     dword ptr [rax+rax+00h]
0x140018846  test    eax, eax
0x140018848  jns     short loc_140018869
0x14001884a  mov     rcx, [rbp+5Fh]; this
0x14001884e  mov     r9d, eax; char *
0x140018851  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140018856  mov     ebx, eax
0x140018858  test    eax, eax
0x14001885a  jns     short loc_140018869
0x14001885c  mov     r9d, eax
0x14001885f  mov     edx, 2A5h
0x140018864  jmp     loc_140018D10
0x140018869  mov     rsi, [rsi]
0x14001886c  mov     r13, [r12]
0x140018870  mov     r15, rdi
0x140018873  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140018877  inc     rcx
0x14001887a  cmp     [rsi+rcx*2], di
0x14001887e  jnz     short loc_140018877
0x140018880  lea     r14, [rcx+0ABh]
0x140018887  mov     qword ptr [rbp+57h+Privilege], rdi
0x14001888b  mov     eax, 2
0x140018890  mul     r14
0x140018893  mov     rbx, rax
0x140018896  test    rdx, rdx
0x140018899  jnz     loc_140018974
0x14001889f  call    cs:__imp_GetProcessHeap
0x1400188a6  nop     dword ptr [rax+rax+00h]
0x1400188ab  mov     rcx, rax; hHeap
0x1400188ae  mov     r8, rbx; dwBytes
0x1400188b1  mov     edx, 8; dwFlags
0x1400188b6  call    cs:__imp_HeapAlloc
0x1400188bd  nop     dword ptr [rax+rax+00h]
0x1400188c2  mov     rdi, rax
0x1400188c5  mov     ebx, 8007000Eh
0x1400188ca  xor     eax, eax
0x1400188cc  test    rdi, rdi
0x1400188cf  cmovnz  ebx, eax
0x1400188d2  jz      loc_140018979
0x1400188d8  mov     r9, rsi
0x1400188db  lea     r8, aDPaiAOiciFaSyA; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A"...
0x1400188e2  mov     rdx, r14; unsigned __int64
0x1400188e5  mov     rcx, rdi; unsigned __int16 *
0x1400188e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400188ed  mov     ebx, eax
0x1400188ef  xor     esi, esi
0x1400188f1  test    eax, eax
0x1400188f3  js      short loc_140018942
0x1400188f5  mov     qword ptr [rbp+57h+Privilege], rsi
0x1400188f9  xor     r9d, r9d; SecurityDescriptorSize
0x1400188fc  lea     r8, [rbp+57h+Privilege]; SecurityDescriptor
0x140018900  lea     edx, [rsi+1]; StringSDRevision
0x140018903  mov     rcx, rdi; StringSecurityDescriptor
0x140018906  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14001890d  nop     dword ptr [rax+rax+00h]
0x140018912  test    eax, eax
0x140018914  jz      short loc_14001891E
0x140018916  mov     r15, qword ptr [rbp+57h+Privilege]
0x14001891a  mov     ebx, esi
0x14001891c  jmp     short loc_140018942
0x14001891e  call    cs:__imp_GetLastError
0x140018925  nop     dword ptr [rax+rax+00h]
0x14001892a  mov     ebx, eax
0x14001892c  test    eax, eax
0x14001892e  jle     short loc_140018939
0x140018930  movzx   ebx, ax
0x140018933  or      ebx, 80070000h
0x140018939  test    ebx, ebx
0x14001893b  js      short loc_140018942
0x14001893d  mov     ebx, 80004005h
0x140018942  call    cs:__imp_GetProcessHeap
0x140018949  nop     dword ptr [rax+rax+00h]
0x14001894e  mov     rcx, rax; hHeap
0x140018951  mov     r8, rdi; lpMem
0x140018954  xor     edx, edx; dwFlags
0x140018956  call    cs:__imp_HeapFree
0x14001895d  nop     dword ptr [rax+rax+00h]
0x140018962  test    eax, eax
0x140018964  jnz     short loc_14001897B
0x140018966  call    cs:__imp_GetLastError
0x14001896d  nop     dword ptr [rax+rax+00h]
0x140018972  jmp     short loc_14001897B
0x140018974  mov     ebx, 80070216h
0x140018979  xor     esi, esi
0x14001897b  test    ebx, ebx
0x14001897d  js      loc_140018D08
0x140018983  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x14001898b  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r15
0x14001898f  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x140018997  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14001899b  mov     rcx, r13; lpPathName
0x14001899e  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x1400189a3  mov     ebx, eax
0x1400189a5  mov     rcx, r15; hMem
0x1400189a8  call    cs:__imp_LocalFree
0x1400189af  nop     dword ptr [rax+rax+00h]
0x1400189b4  test    ebx, ebx
0x1400189b6  js      loc_140018D08
0x1400189bc  lea     rax, [rbp+57h+var_B0]
0x1400189c0  mov     [rbp+57h+lpFileName], rax
0x1400189c4  lea     rax, [rbp+57h+var_B0]
0x1400189c8  mov     [rbp+57h+var_B8], rax
0x1400189cc  mov     [rbp+57h+var_B0], si
0x1400189d0  mov     rax, qword ptr [rbp+57h+var_98]
0x1400189d4  mov     r8, [rax+8]
0x1400189d8  sub     r8, [rax]
0x1400189db  sar     r8, 1
0x1400189de  mov     rdx, [rax]
0x1400189e1  lea     rcx, [rbp+57h+lpFileName]
0x1400189e5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400189ea  test    al, al
0x1400189ec  jnz     short loc_1400189F5
0x1400189ee  mov     edx, 2AEh
0x1400189f3  jmp     short loc_140018A1E
0x1400189f5  lea     rax, aUsersDefault; "Users\\Default"
0x1400189fc  mov     qword ptr [rbp+57h+var_98], rax
0x140018a00  mov     qword ptr [rbp+57h+var_98+8], 0Dh
0x140018a08  lea     rdx, [rbp+57h+var_98]
0x140018a0c  lea     rcx, [rbp+57h+lpFileName]; this
0x140018a10  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140018a15  test    al, al
0x140018a17  jnz     short loc_140018A57
0x140018a19  mov     edx, 2AFh; void *
0x140018a1e  mov     r9d, 8007000Eh; char *
0x140018a24  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018a2b  mov     rcx, [rbp+5Fh]; this
0x140018a2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018a34  lea     rax, [rbp+57h+var_B0]
0x140018a38  mov     rcx, [rbp+57h+lpFileName]; void *
0x140018a3c  cmp     rcx, rax
0x140018a3f  jz      short loc_140018A4D
0x140018a41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018a48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018a4d  mov     ebx, 8007000Eh
0x140018a52  jmp     loc_140018D20
0x140018a57  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rsi
0x140018a5c  mov     qword ptr [rsp+100h+dwCreationDisposition], rsi
0x140018a61  xor     r9d, r9d
0x140018a64  mov     r8d, 8001h
0x140018a6a  mov     rdx, [r12]
0x140018a6e  mov     rcx, [rbp+57h+lpFileName]
0x140018a72  call    cs:__imp_CopyProfileDirectoryEx2
0x140018a79  nop     dword ptr [rax+rax+00h]
0x140018a7e  test    eax, eax
0x140018a80  jnz     short loc_140018A9E
0x140018a82  mov     edx, 2B8h; void *
0x140018a87  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018a8e  mov     rcx, [rbp+5Fh]; this
0x140018a92  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140018a97  mov     ebx, eax
0x140018a99  jmp     loc_140018CBE
0x140018a9e  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], rsi
0x140018aa2  mov     qword ptr [rbp+57h+LastAccessTime.dwLowDateTime], rsi
0x140018aa6  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], rsi
0x140018aaa  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x140018aaf  mov     [rsp+100h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x140018ab7  mov     r14d, 3
0x140018abd  mov     [rsp+100h+dwCreationDisposition], r14d; int
0x140018ac2  xor     r9d, r9d; lpSecurityAttributes
0x140018ac5  xor     r8d, r8d; dwShareMode
0x140018ac8  lea     edx, [r14-2]; dwDesiredAccess
0x140018acc  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x140018ad0  call    cs:__imp_CreateFileW
0x140018ad7  nop     dword ptr [rax+rax+00h]
0x140018adc  mov     rbx, rax
0x140018adf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140018ae3  jnz     short loc_140018AEC
0x140018ae5  mov     edx, 2CAh
0x140018aea  jmp     short loc_140018A87
0x140018aec  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x140018af0  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x140018af4  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140018af8  mov     rcx, rbx; hFile
0x140018afb  call    cs:__imp_GetFileTime
0x140018b02  nop     dword ptr [rax+rax+00h]
0x140018b07  test    eax, eax
0x140018b09  jnz     short loc_140018B56
0x140018b0b  mov     rcx, [rbp+5Fh]; this
0x140018b0f  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018b16  mov     edx, 2CFh; void *
0x140018b1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140018b20  mov     edi, eax
0x140018b22  test    rbx, rbx
0x140018b25  jz      short loc_140018B36
0x140018b27  mov     rcx, rbx; hObject
0x140018b2a  call    cs:__imp_CloseHandle
0x140018b31  nop     dword ptr [rax+rax+00h]
0x140018b36  mov     rcx, [rbp+57h+lpFileName]; void *
0x140018b3a  lea     rax, [rbp+57h+var_B0]
0x140018b3e  cmp     rcx, rax
0x140018b41  jz      short loc_140018B4F
0x140018b43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018b4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018b4f  mov     ebx, edi
0x140018b51  jmp     loc_140018D20
0x140018b56  test    rbx, rbx
0x140018b59  jz      short loc_140018B6A
0x140018b5b  mov     rcx, rbx; hObject
0x140018b5e  call    cs:__imp_CloseHandle
0x140018b65  nop     dword ptr [rax+rax+00h]
0x140018b6a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140018b72  movdqu  [rbp+57h+var_98], xmm0
0x140018b77  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x140018b7f  lea     r8, [rbp+57h+var_98]
0x140018b83  mov     edx, 5
0x140018b88  mov     rcx, r12
0x140018b8b  call    ?EnumerateDirectory@Csl@@YAJAEBVPath@1@W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectory(Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x140018b90  mov     ebx, eax
0x140018b92  test    eax, eax
0x140018b94  jns     short loc_140018BB3
0x140018b96  mov     rcx, [rbp+5Fh]; this
0x140018b9a  mov     r9d, eax; char *
0x140018b9d  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018ba4  mov     edx, 2D7h; void *
0x140018ba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018bae  jmp     loc_140018CB5
0x140018bb3  mov     rbx, qword ptr [rbp+57h+var_98]
0x140018bb7  cmp     rbx, qword ptr [rbp+57h+var_98+8]
0x140018bbb  jz      loc_140018CD9
0x140018bc1  mov     rcx, [rbx]; lpFileName
0x140018bc4  call    cs:__imp_GetFileAttributesW
0x140018bcb  nop     dword ptr [rax+rax+00h]
0x140018bd0  cmp     eax, 0FFFFFFFFh
0x140018bd3  jz      short loc_140018BDD
0x140018bd5  test    al, 10h
0x140018bd7  jnz     loc_140018C61
0x140018bdd  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x140018be2  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140018bea  mov     [rsp+100h+dwCreationDisposition], r14d; dwCreationDisposition
0x140018bef  xor     r9d, r9d; lpSecurityAttributes
0x140018bf2  xor     r8d, r8d; dwShareMode
0x140018bf5  mov     edx, 100h; dwDesiredAccess
0x140018bfa  mov     rcx, [rbx]; lpFileName
0x140018bfd  call    cs:__imp_CreateFileW
0x140018c04  nop     dword ptr [rax+rax+00h]
0x140018c09  mov     rdi, rax
0x140018c0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140018c10  jz      loc_140018C9E
0x140018c16  mov     edx, 2002h; dwFileAttributes
0x140018c1b  mov     rcx, [rbx]; lpFileName
0x140018c1e  call    cs:__imp_SetFileAttributesW
0x140018c25  nop     dword ptr [rax+rax+00h]
0x140018c2a  test    eax, eax
0x140018c2c  jz      short loc_140018C97
0x140018c2e  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x140018c32  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x140018c36  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140018c3a  mov     rcx, rdi; hFile
0x140018c3d  call    cs:__imp_SetFileTime
0x140018c44  nop     dword ptr [rax+rax+00h]
0x140018c49  test    eax, eax
0x140018c4b  jz      short loc_140018C6A
0x140018c4d  test    rdi, rdi
0x140018c50  jz      short loc_140018C61
0x140018c52  mov     rcx, rdi; hObject
0x140018c55  call    cs:__imp_CloseHandle
0x140018c5c  nop     dword ptr [rax+rax+00h]
0x140018c61  add     rbx, 20h ; ' '
0x140018c65  jmp     loc_140018BB7
0x140018c6a  mov     edx, 2F6h; void *
0x140018c6f  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018c76  mov     rcx, [rbp+5Fh]; this
0x140018c7a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140018c7f  mov     ebx, eax
0x140018c81  test    rdi, rdi
0x140018c84  jz      short loc_140018CB5
0x140018c86  mov     rcx, rdi; hObject
0x140018c89  call    cs:__imp_CloseHandle
0x140018c90  nop     dword ptr [rax+rax+00h]
0x140018c95  jmp     short loc_140018CB5
0x140018c97  mov     edx, 2EEh
0x140018c9c  jmp     short loc_140018C6F
0x140018c9e  mov     rcx, [rbp+5Fh]; this
0x140018ca2  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018ca9  mov     edx, 2E8h; void *
  ... truncated ...
```
