# Csl::TemporaryDacl::Acquire(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)

- ea: `0x18002e4ac`
- end: `0x18002e954`
- name: `?Acquire@TemporaryDacl@Csl@@QEAAJAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z`
- size: `1192`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180183108`
- `0x180183408`

## callees

- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180016774`
- `0x18002d4ac`
- `0x18002dc8c`
- `0x18002e2b4`
- `0x18002e4ac`
- `0x18002f1f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e651`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e703`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e78f`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e887`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e8c0`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e8f6`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e651`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e703`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e78f`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e887`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e8c0`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002e8f6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002e7e6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002e7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e871`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e895`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e895`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e584`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e584`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e717`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e717`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e910`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e757`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e757`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002e616`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18002e616`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002e81e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002e81e`

## string_xrefs

- `0x18002e52e`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002e5ab`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002e62a`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002e6c2`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002e770`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002e832`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002e5a0`: `Path: %ws`

## pseudocode

```c
__int64 __fastcall Csl::TemporaryDacl::Acquire(__int64 a1, const char **a2, __int64 *a3)
{
  __int64 v6; // rdx
  PSECURITY_DESCRIPTOR v7; // rbx
  unsigned int LastErrorMsg; // ebx
  DWORD SecurityInfo; // eax
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // rdx
  const char *v14; // r9
  __int64 v15; // rdx
  int LastError; // eax
  DWORD v17; // eax
  void **v18; // rdi
  void *v19; // rsi
  PSECURITY_DESCRIPTOR v20; // r15
  DWORD v21; // eax
  DWORD v22; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-69h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-69h]
  unsigned int dwCreationDispositionb; // [rsp+20h] [rbp-69h]
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+40h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+48h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-39h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp-31h] BYREF
  _WORD v30[8]; // [rsp+68h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR v31[2]; // [rsp+78h] [rbp-11h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+88h] [rbp-1h] BYREF
  _WORD v33[8]; // [rsp+98h] [rbp+Fh] BYREF
  WINBOOL bDaclPresent; // [rsp+A8h] [rbp+1Fh] BYREF
  PACL pDacl; // [rsp+B0h] [rbp+27h] BYREF
  PACL ppDacl; // [rsp+B8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  WINBOOL bDaclDefaulted; // [rsp+108h] [rbp+7Fh] BYREF

  lpFileName[0] = v30;
  v30[0] = 0;
  lpFileName[1] = v30;
  v31[0] = (PSECURITY_DESCRIPTOR)L"\\\\?\\";
  v31[1] = (PSECURITY_DESCRIPTOR)4;
  if ( !(unsigned __int8)Csl::StringStartsWith(a2, v31, 0)
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpFileName,
                           L"\\\\?\\",
                           4) )
  {
    v6 = 676;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
LABEL_27:
    if ( lpFileName[0] != v30 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           lpFileName,
                           *a2,
                           a2[1]) )
  {
    v6 = 679;
    goto LABEL_4;
  }
  ObjectDescriptor = CreateFileW(lpFileName[0], 0x60000u, 3u, 0, 3u, 0x2200000u, 0);
  v7 = ObjectDescriptor;
  if ( ObjectDescriptor == (PSECURITY_DESCRIPTOR)-1LL )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x2B4,
                     (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                     "Path: %ws",
                     *a2);
    if ( lpFileName[0] != v30 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return LastErrorMsg;
  }
  ppDacl = 0;
  ppSecurityDescriptor = 0;
  SecurityInfo = GetSecurityInfo(ObjectDescriptor, SE_FILE_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2C2,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
            (const char *)SecurityInfo,
            dwCreationDispositiona);
    if ( !ppSecurityDescriptor )
    {
LABEL_15:
      if ( v7 )
        CloseHandle(v7);
      if ( lpFileName[0] != v30 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      return v11;
    }
    ObjectDescriptor = ppSecurityDescriptor;
LABEL_14:
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
    goto LABEL_15;
  }
  v12 = a3[1];
  v13 = *a3;
  StringSecurityDescriptor[0] = v33;
  StringSecurityDescriptor[1] = v33;
  v33[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           StringSecurityDescriptor,
                           v13,
                           v12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
    if ( StringSecurityDescriptor[0] != v33 )
      operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( ppSecurityDescriptor )
    {
      ObjectDescriptor = ppSecurityDescriptor;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
    }
    if ( v7 )
      CloseHandle(v7);
    goto LABEL_27;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, &SecurityDescriptor, 0) )
  {
    v15 = 718;
LABEL_32:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                  v14);
LABEL_33:
    v11 = LastError;
    if ( SecurityDescriptor )
    {
      ObjectDescriptor = SecurityDescriptor;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
    }
    if ( StringSecurityDescriptor[0] != v33 )
      operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( !ppSecurityDescriptor )
      goto LABEL_15;
    ObjectDescriptor = ppSecurityDescriptor;
    goto LABEL_14;
  }
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v15 = 727;
    goto LABEL_32;
  }
  v17 = SetSecurityInfo(ObjectDescriptor, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v17 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x2E0,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                  (const char *)v17,
                  dwCreationDispositionb);
    goto LABEL_33;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1 + 16,
    &ObjectDescriptor);
  v18 = (void **)(a1 + 8);
  if ( (PSECURITY_DESCRIPTOR *)(a1 + 8) != &ppSecurityDescriptor )
  {
    v19 = *v18;
    v20 = ppSecurityDescriptor;
    if ( *v18 )
    {
      v21 = GetLastError();
      v31[0] = v19;
      v22 = v21;
      DestroyPrivateObjectSecurity(v31);
      SetLastError(v22);
    }
    *v18 = v20;
    ppSecurityDescriptor = 0;
  }
  *(_QWORD *)a1 = ppDacl;
  if ( SecurityDescriptor )
  {
    v31[0] = SecurityDescriptor;
    DestroyPrivateObjectSecurity(v31);
  }
  if ( StringSecurityDescriptor[0] != v33 )
    operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( ppSecurityDescriptor )
  {
    v31[0] = ppSecurityDescriptor;
    DestroyPrivateObjectSecurity(v31);
  }
  if ( (char *)ObjectDescriptor - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(ObjectDescriptor);
  if ( lpFileName[0] != v30 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x18002e4ac  mov     [rsp-8+arg_0], rbx
0x18002e4b1  mov     [rsp-8+arg_8], rsi
0x18002e4b6  push    rbp
0x18002e4b7  push    rdi
0x18002e4b8  push    r12
0x18002e4ba  push    r14
0x18002e4bc  push    r15
0x18002e4be  lea     rbp, [rsp-37h]
0x18002e4c3  sub     rsp, 0C0h
0x18002e4ca  mov     rdi, rdx
0x18002e4cd  lea     rax, [rbp+57h+var_78]
0x18002e4d1  xor     r12d, r12d
0x18002e4d4  mov     [rbp+57h+lpFileName], rax
0x18002e4d8  mov     rsi, r8
0x18002e4db  mov     [rbp+57h+var_78], r12w
0x18002e4e0  mov     r14, rcx
0x18002e4e3  lea     rax, [rbp+57h+var_78]
0x18002e4e7  lea     rbx, String2; "\\\\?\\"
0x18002e4ee  mov     [rbp+57h+var_80], rax
0x18002e4f2  lea     r15d, [r12+4]
0x18002e4f7  mov     [rbp+57h+var_68], rbx
0x18002e4fb  xor     r8d, r8d
0x18002e4fe  mov     [rbp+57h+var_60], r15
0x18002e502  lea     rdx, [rbp+57h+var_68]
0x18002e506  mov     rcx, rdi
0x18002e509  call    ?StringStartsWith@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0_N@Z; Csl::StringStartsWith(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,bool)
0x18002e50e  test    al, al
0x18002e510  jnz     short loc_18002E545
0x18002e512  mov     r8d, r15d
0x18002e515  lea     rcx, [rbp+57h+lpFileName]
0x18002e519  mov     rdx, rbx
0x18002e51c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002e521  test    al, al
0x18002e523  jnz     short loc_18002E545
0x18002e525  mov     edx, 2A4h; void *
0x18002e52a  mov     rcx, [rbp+5Fh]; this
0x18002e52e  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e535  mov     r9d, 8007000Eh; char *
0x18002e53b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e540  jmp     loc_18002E723
0x18002e545  mov     r8, [rdi+8]
0x18002e549  lea     rcx, [rbp+57h+lpFileName]
0x18002e54d  mov     rdx, [rdi]
0x18002e550  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002e555  test    al, al
0x18002e557  jnz     short loc_18002E560
0x18002e559  mov     edx, 2A7h
0x18002e55e  jmp     short loc_18002E52A
0x18002e560  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18002e564  mov     r8d, 3; dwShareMode
0x18002e56a  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x18002e56f  xor     r9d, r9d; lpSecurityAttributes
0x18002e572  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002e57a  mov     edx, 60000h; dwDesiredAccess
0x18002e57f  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002e584  call    cs:__imp_CreateFileW
0x18002e58b  nop     dword ptr [rax+rax+00h]
0x18002e590  mov     [rbp+57h+ObjectDescriptor], rax
0x18002e594  mov     rbx, rax
0x18002e597  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e59b  jnz     short loc_18002E5E3
0x18002e59d  mov     rax, [rdi]
0x18002e5a0  lea     r9, aPathWs; "Path: %ws"
0x18002e5a7  mov     rcx, [rbp+5Fh]; this
0x18002e5ab  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e5b2  mov     edx, 2B4h; void *
0x18002e5b7  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; char *
0x18002e5bc  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002e5c1  mov     rcx, [rbp+57h+lpFileName]; void *
0x18002e5c5  mov     ebx, eax
0x18002e5c7  lea     rax, [rbp+57h+var_78]
0x18002e5cb  cmp     rcx, rax
0x18002e5ce  jz      short loc_18002E5DC
0x18002e5d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e5d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e5dc  mov     eax, ebx
0x18002e5de  jmp     loc_18002E937
0x18002e5e3  xor     r9d, r9d; ppsidOwner
0x18002e5e6  mov     [rbp+57h+ppDacl], r12
0x18002e5ea  lea     rax, [rbp+57h+var_98]
0x18002e5ee  mov     [rbp+57h+var_98], r12
0x18002e5f2  mov     [rsp+0E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002e5f7  mov     r8d, r15d; SecurityInfo
0x18002e5fa  lea     rax, [rbp+57h+ppDacl]
0x18002e5fe  mov     [rsp+0E0h+hTemplateFile], r12; ppSacl
0x18002e603  lea     edi, [r9+1]
0x18002e607  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; ppDacl
0x18002e60c  mov     edx, edi; ObjectType
0x18002e60e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r12; int
0x18002e613  mov     rcx, rbx; handle
0x18002e616  call    cs:__imp_GetSecurityInfo
0x18002e61d  nop     dword ptr [rax+rax+00h]
0x18002e622  test    eax, eax
0x18002e624  jz      short loc_18002E691
0x18002e626  mov     rcx, [rbp+5Fh]; this
0x18002e62a  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e631  mov     r9d, eax; char *
0x18002e634  mov     edx, 2C2h; void *
0x18002e639  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e63e  mov     rcx, [rbp+57h+var_98]
0x18002e642  mov     edi, eax
0x18002e644  test    rcx, rcx
0x18002e647  jz      short loc_18002E65D
0x18002e649  mov     [rbp+57h+ObjectDescriptor], rcx
0x18002e64d  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18002e651  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002e658  nop     dword ptr [rax+rax+00h]
0x18002e65d  test    rbx, rbx
0x18002e660  jz      short loc_18002E671
0x18002e662  mov     rcx, rbx; hObject
0x18002e665  call    cs:__imp_CloseHandle
0x18002e66c  nop     dword ptr [rax+rax+00h]
0x18002e671  mov     rcx, [rbp+57h+lpFileName]; void *
0x18002e675  lea     rax, [rbp+57h+var_78]
0x18002e679  cmp     rcx, rax
0x18002e67c  jz      short loc_18002E68A
0x18002e67e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e685  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e68a  mov     eax, edi
0x18002e68c  jmp     loc_18002E937
0x18002e691  mov     r8, [rsi+8]
0x18002e695  lea     rax, [rbp+57h+var_48]
0x18002e699  mov     rdx, [rsi]
0x18002e69c  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x18002e6a0  mov     [rbp+57h+StringSecurityDescriptor], rax
0x18002e6a4  lea     rax, [rbp+57h+var_48]
0x18002e6a8  mov     [rbp+57h+var_50], rax
0x18002e6ac  mov     [rbp+57h+var_48], r12w
0x18002e6b1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002e6b6  test    al, al
0x18002e6b8  jnz     loc_18002E746
0x18002e6be  mov     rcx, [rbp+5Fh]; this
0x18002e6c2  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e6c9  mov     r9d, 8007000Eh; char *
0x18002e6cf  mov     edx, 2C6h; void *
0x18002e6d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6d9  mov     rcx, [rbp+57h+StringSecurityDescriptor]; void *
0x18002e6dd  lea     rax, [rbp+57h+var_48]
0x18002e6e1  cmp     rcx, rax
0x18002e6e4  jz      short loc_18002E6F2
0x18002e6e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e6ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e6f2  mov     rax, [rbp+57h+var_98]
0x18002e6f6  test    rax, rax
0x18002e6f9  jz      short loc_18002E70F
0x18002e6fb  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18002e6ff  mov     [rbp+57h+ObjectDescriptor], rax
0x18002e703  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002e70a  nop     dword ptr [rax+rax+00h]
0x18002e70f  test    rbx, rbx
0x18002e712  jz      short loc_18002E723
0x18002e714  mov     rcx, rbx; hObject
0x18002e717  call    cs:__imp_CloseHandle
0x18002e71e  nop     dword ptr [rax+rax+00h]
0x18002e723  mov     rcx, [rbp+57h+lpFileName]; void *
0x18002e727  lea     rax, [rbp+57h+var_78]
0x18002e72b  cmp     rcx, rax
0x18002e72e  jz      short loc_18002E73C
0x18002e730  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e737  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e73c  mov     eax, 8007000Eh
0x18002e741  jmp     loc_18002E937
0x18002e746  mov     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002e74a  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18002e74e  xor     r9d, r9d; SecurityDescriptorSize
0x18002e751  mov     [rbp+57h+SecurityDescriptor], r12
0x18002e755  mov     edx, edi; StringSDRevision
0x18002e757  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002e75e  nop     dword ptr [rax+rax+00h]
0x18002e763  test    eax, eax
0x18002e765  jnz     short loc_18002E7CA
0x18002e767  mov     edx, 2CEh; void *
0x18002e76c  mov     rcx, [rbp+5Fh]; this
0x18002e770  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e777  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002e77c  mov     rcx, [rbp+57h+SecurityDescriptor]
0x18002e780  mov     edi, eax
0x18002e782  test    rcx, rcx
0x18002e785  jz      short loc_18002E79B
0x18002e787  mov     [rbp+57h+ObjectDescriptor], rcx
0x18002e78b  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18002e78f  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002e796  nop     dword ptr [rax+rax+00h]
0x18002e79b  mov     rcx, [rbp+57h+StringSecurityDescriptor]; void *
0x18002e79f  lea     rax, [rbp+57h+var_48]
0x18002e7a3  cmp     rcx, rax
0x18002e7a6  jz      short loc_18002E7B4
0x18002e7a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e7af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e7b4  mov     rax, [rbp+57h+var_98]
0x18002e7b8  test    rax, rax
0x18002e7bb  jz      loc_18002E65D
0x18002e7c1  mov     [rbp+57h+ObjectDescriptor], rax
0x18002e7c5  jmp     loc_18002E64D
0x18002e7ca  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18002e7ce  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18002e7d2  lea     r8, [rbp+57h+pDacl]; pDacl
0x18002e7d6  mov     [rbp+57h+pDacl], r12
0x18002e7da  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18002e7de  mov     [rbp+57h+bDaclPresent], r12d
0x18002e7e2  mov     [rbp+57h+bDaclDefaulted], r12d
0x18002e7e6  call    cs:__imp_GetSecurityDescriptorDacl
0x18002e7ed  nop     dword ptr [rax+rax+00h]
0x18002e7f2  test    eax, eax
0x18002e7f4  jnz     short loc_18002E800
0x18002e7f6  mov     edx, 2D7h
0x18002e7fb  jmp     loc_18002E76C
0x18002e800  mov     rax, [rbp+57h+pDacl]
0x18002e804  xor     r9d, r9d; psidOwner
0x18002e807  mov     [rsp+0E0h+hTemplateFile], r12; pSacl
0x18002e80c  mov     r8d, r15d; SecurityInfo
0x18002e80f  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; pDacl
0x18002e814  mov     edx, edi; ObjectType
0x18002e816  mov     rcx, rbx; handle
0x18002e819  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r12; unsigned int
0x18002e81e  call    cs:__imp_SetSecurityInfo
0x18002e825  nop     dword ptr [rax+rax+00h]
0x18002e82a  test    eax, eax
0x18002e82c  jz      short loc_18002E84B
0x18002e82e  mov     rcx, [rbp+5Fh]; this
0x18002e832  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e839  mov     r9d, eax; char *
0x18002e83c  mov     edx, 2E0h; void *
0x18002e841  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e846  jmp     loc_18002E77C
0x18002e84b  lea     rcx, [r14+10h]
0x18002e84f  lea     rdx, [rbp+57h+ObjectDescriptor]
0x18002e853  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18002e858  lea     rax, [rbp+57h+var_98]
0x18002e85c  lea     rdi, [r14+8]
0x18002e860  cmp     rdi, rax
0x18002e863  jz      short loc_18002E8A8
0x18002e865  mov     rsi, [rdi]
0x18002e868  mov     r15, [rbp+57h+var_98]
0x18002e86c  test    rsi, rsi
0x18002e86f  jz      short loc_18002E8A1
0x18002e871  call    cs:__imp_GetLastError
0x18002e878  nop     dword ptr [rax+rax+00h]
0x18002e87d  lea     rcx, [rbp+57h+var_68]; ObjectDescriptor
0x18002e881  mov     [rbp+57h+var_68], rsi
0x18002e885  mov     ebx, eax
0x18002e887  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002e88e  nop     dword ptr [rax+rax+00h]
0x18002e893  mov     ecx, ebx; dwErrCode
0x18002e895  call    cs:__imp_SetLastError
0x18002e89c  nop     dword ptr [rax+rax+00h]
0x18002e8a1  mov     [rdi], r15
0x18002e8a4  mov     [rbp+57h+var_98], r12
0x18002e8a8  mov     rax, [rbp+57h+ppDacl]
0x18002e8ac  mov     [r14], rax
0x18002e8af  mov     rax, [rbp+57h+SecurityDescriptor]
0x18002e8b3  test    rax, rax
0x18002e8b6  jz      short loc_18002E8CC
0x18002e8b8  lea     rcx, [rbp+57h+var_68]; ObjectDescriptor
0x18002e8bc  mov     [rbp+57h+var_68], rax
0x18002e8c0  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002e8c7  nop     dword ptr [rax+rax+00h]
0x18002e8cc  mov     rcx, [rbp+57h+StringSecurityDescriptor]; void *
0x18002e8d0  lea     rax, [rbp+57h+var_48]
0x18002e8d4  cmp     rcx, rax
0x18002e8d7  jz      short loc_18002E8E5
0x18002e8d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e8e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e8e5  mov     rax, [rbp+57h+var_98]
0x18002e8e9  test    rax, rax
0x18002e8ec  jz      short loc_18002E902
0x18002e8ee  lea     rcx, [rbp+57h+var_68]; ObjectDescriptor
0x18002e8f2  mov     [rbp+57h+var_68], rax
0x18002e8f6  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002e8fd  nop     dword ptr [rax+rax+00h]
0x18002e902  mov     rcx, [rbp+57h+ObjectDescriptor]; hObject
0x18002e906  lea     rax, [rcx-1]
0x18002e90a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e90e  ja      short loc_18002E91C
0x18002e910  call    cs:__imp_CloseHandle
0x18002e917  nop     dword ptr [rax+rax+00h]
0x18002e91c  mov     rcx, [rbp+57h+lpFileName]; void *
0x18002e920  lea     rax, [rbp+57h+var_78]
0x18002e924  cmp     rcx, rax
0x18002e927  jz      short loc_18002E935
0x18002e929  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e930  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e935  xor     eax, eax
0x18002e937  lea     r11, [rsp+0E0h+var_20]
0x18002e93f  mov     rbx, [r11+30h]
0x18002e943  mov     rsi, [r11+38h]
0x18002e947  mov     rsp, r11
0x18002e94a  pop     r15
0x18002e94c  pop     r14
0x18002e94e  pop     r12
0x18002e950  pop     rdi
0x18002e951  pop     rbp
0x18002e952  retn
```
