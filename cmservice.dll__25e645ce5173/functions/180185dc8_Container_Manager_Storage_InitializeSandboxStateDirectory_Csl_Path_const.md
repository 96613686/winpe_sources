# Container::Manager::Storage::InitializeSandboxStateDirectory(Csl::Path const &)

- ea: `0x180185dc8`
- end: `0x180186467`
- name: `?InitializeSandboxStateDirectory@Storage@Manager@Container@@YAJAEBVPath@Csl@@@Z`
- size: `1695`
- prototype: `__int64 __fastcall(Container::Manager::Storage *__hidden this, const struct Path *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180186470`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x180016774`
- `0x18002c1f4`
- `0x18002fae4`
- `0x18002fd88`
- `0x180185dc8`
- `0x180197498`
- `0x1801a2a90`
- `0x1801a2b8c`
- `0x1801a3188`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180185e90`
- `ntdll!RtlAcquirePrivilege` at `0x180185e90`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180185fe6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180185fe6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185e36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180186241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801862da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801863bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018644a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185e36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180186241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801862da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801863bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18018644a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180185e00`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180185e00`

## string_xrefs

- `0x180185eaa`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Container::Manager::Storage::InitializeSandboxStateDirectory(
        Container::Manager::Storage *this,
        const struct Path *a2)
{
  const char *v3; // r9
  unsigned int LastError; // ebx
  NTSTATUS v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  struct _SECURITY_ATTRIBUTES *v10; // r8
  int DirectoryRecursive; // eax
  int OsVersionInfo; // edi
  WCHAR *v13; // rcx
  const char *v14; // r9
  __int64 v15; // rdx
  struct _SECURITY_ATTRIBUTES *v16; // r8
  __int64 v17; // rdx
  struct _OSVERSIONINFOW *v18; // rdx
  __int64 *v19; // rsi
  unsigned int v20; // eax
  const wchar_t *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdi
  unsigned int v24; // eax
  unsigned int v25; // esi
  __int64 v26; // rcx
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v29; // [rsp+38h] [rbp-C8h]
  _WORD v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *v31; // [rsp+50h] [rbp-B0h] BYREF
  char *v32; // [rsp+58h] [rbp-A8h]
  _WORD v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  void *v36[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v37[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v40; // [rsp+C4h] [rbp-3Ch]
  int v41; // [rsp+C8h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+218h] [rbp+118h] BYREF
  PVOID ReturnedState; // [rsp+220h] [rbp+120h] BYREF
  __int64 Privilege; // [rsp+228h] [rbp+128h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x16F,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                  v3);
LABEL_3:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return LastError;
  }
  v38[0] = 24;
  v38[2] = 0;
  v38[1] = SecurityDescriptor;
  ReturnedState = 0;
  Privilege = 0x1200000011LL;
  v6 = RtlAcquirePrivilege((PULONG)&Privilege, 2u, 0, &ReturnedState);
  if ( v6 < 0 )
  {
    v7 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x52,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
           (const char *)(unsigned int)v6,
           v27);
    LastError = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)(unsigned int)v7,
        v27);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      goto LABEL_3;
    }
  }
  lpFileName = v30;
  v29 = v30;
  v30[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpFileName,
                           *(_QWORD *)this,
                           (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 1) )
  {
    v8 = 383;
    goto LABEL_11;
  }
  v34 = L"WcSandboxState";
  v35 = 14;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&lpFileName) )
  {
    v8 = 384;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)0x8007000ELL,
      v27);
    v9 = (WCHAR *)lpFileName;
    if ( lpFileName != v30 )
      goto LABEL_72;
    goto LABEL_73;
  }
  DirectoryRecursive = Csl::CreateDirectoryRecursive((Csl *)&lpFileName, (const struct Path *)v38, v10);
  OsVersionInfo = DirectoryRecursive;
  if ( DirectoryRecursive < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)(unsigned int)DirectoryRecursive,
      v27);
    goto LABEL_17;
  }
  if ( !SetFileAttributesW(lpFileName, 6u) )
  {
    OsVersionInfo = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x186,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                      v14);
LABEL_17:
    v13 = (WCHAR *)lpFileName;
    if ( lpFileName == v30 )
    {
LABEL_82:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return (unsigned int)OsVersionInfo;
    }
LABEL_81:
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_82;
  }
  v31 = v33;
  v32 = (char *)v33;
  v33[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v31,
                           lpFileName,
                           v29 - lpFileName) )
  {
    v15 = 395;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)0x8007000ELL,
      v27);
    goto LABEL_69;
  }
  v34 = L"Hives";
  v35 = 5;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&v31) )
  {
    v15 = 396;
    goto LABEL_23;
  }
  OsVersionInfo = Csl::CreateDirectoryRecursive((Csl *)&v31, 0, v16);
  if ( OsVersionInfo < 0 )
  {
    v17 = 398;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)(unsigned int)OsVersionInfo,
      v27);
    goto LABEL_78;
  }
  memset_0(v39, 0, 0x114u);
  OsVersionInfo = Csl::GetOsVersionInfo((Csl *)v39, v18);
  if ( OsVersionInfo < 0 )
  {
    v17 = 401;
    goto LABEL_28;
  }
  v19 = (__int64 *)off_1801C8800;
  while ( 1 )
  {
    Privilege = 0;
    v20 = ORCreateHiveEx(&Privilege, 1);
    if ( v20 )
    {
      OsVersionInfo = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x199,
                        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                        (const char *)v20,
                        v27);
      if ( Privilege )
        ORCloseHive(Privilege);
LABEL_78:
      if ( v31 != v33 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      v13 = (WCHAR *)lpFileName;
      if ( lpFileName == v30 )
        goto LABEL_82;
      goto LABEL_81;
    }
    v36[0] = v37;
    v36[1] = v37;
    v37[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v36,
                             v31,
                             (v32 - (_BYTE *)v31) >> 1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)0x8007000ELL,
        v27);
      if ( v36[0] != v37 )
        operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
      v26 = Privilege;
      if ( Privilege )
        goto LABEL_68;
      goto LABEL_69;
    }
    v21 = (const wchar_t *)v19[2];
    v34 = v21;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v35 = v22;
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v36) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
        (const char *)0x8007000ELL,
        v27);
      if ( v36[0] != v37 )
        operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
      v26 = Privilege;
      if ( Privilege )
LABEL_68:
        ORCloseHive(v26);
LABEL_69:
      if ( v31 != v33 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      v9 = (WCHAR *)lpFileName;
      if ( lpFileName != v30 )
LABEL_72:
        operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
LABEL_73:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return 2147942414LL;
    }
    v23 = Privilege;
    v24 = ORSaveHiveEx(Privilege, v36[0], v40, v41, 1);
    if ( v24 )
      break;
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 )
      ORCloseHive(v23);
    v19 += 3;
    if ( v19 == &qword_1801C8878 )
    {
      if ( v31 != v33 )
        operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
      if ( lpFileName != v30 )
        operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return 0;
    }
  }
  v25 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
          (const char *)v24,
          v27);
  if ( v36[0] != v37 )
    operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v23 )
    ORCloseHive(v23);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v30 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v25;
}

```

## disassembly

```asm
0x180185dc8  push    rbp
0x180185dca  push    rbx
0x180185dcb  push    rsi
0x180185dcc  push    rdi
0x180185dcd  push    r14
0x180185dcf  lea     rbp, [rsp-0E0h]
0x180185dd7  sub     rsp, 1E0h
0x180185dde  mov     rdi, rcx
0x180185de1  xor     r14d, r14d
0x180185de4  mov     [rbp+100h+SecurityDescriptor], r14
0x180185deb  xor     r9d, r9d; SecurityDescriptorSize
0x180185dee  lea     r8, [rbp+100h+SecurityDescriptor]; SecurityDescriptor
0x180185df5  lea     edx, [r14+1]; StringSDRevision
0x180185df9  lea     rcx, aDPAOiciGaSy; "D:P(A;OICI;GA;;;SY)"
0x180185e00  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180185e07  nop     dword ptr [rax+rax+00h]
0x180185e0c  test    eax, eax
0x180185e0e  jnz     short loc_180185E49
0x180185e10  mov     rcx, [rbp+108h]; this
0x180185e17  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180185e1e  mov     edx, 16Fh; void *
0x180185e23  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180185e28  mov     ebx, eax
0x180185e2a  mov     rcx, [rbp+100h+SecurityDescriptor]; hMem
0x180185e31  test    rcx, rcx
0x180185e34  jz      short loc_180185E42
0x180185e36  call    cs:__imp_LocalFree
0x180185e3d  nop     dword ptr [rax+rax+00h]
0x180185e42  mov     eax, ebx
0x180185e44  jmp     loc_180186458
0x180185e49  mov     [rbp+100h+var_160], 18h
0x180185e51  mov     [rbp+100h+var_150], r14
0x180185e55  mov     rax, [rbp+100h+SecurityDescriptor]
0x180185e5c  mov     [rbp+100h+var_158], rax
0x180185e60  mov     [rbp+100h+ReturnedState], r14
0x180185e67  mov     dword ptr [rbp+100h+Privilege], 11h
0x180185e71  mov     dword ptr [rbp+100h+Privilege+4], 12h
0x180185e7b  lea     r9, [rbp+100h+ReturnedState]; ReturnedState
0x180185e82  xor     r8d, r8d; Flags
0x180185e85  lea     edx, [r8+2]; NumPriv
0x180185e89  lea     rcx, [rbp+100h+Privilege]; Privilege
0x180185e90  call    cs:__imp_RtlAcquirePrivilege
0x180185e97  nop     dword ptr [rax+rax+00h]
0x180185e9c  test    eax, eax
0x180185e9e  jns     short loc_180185EED
0x180185ea0  mov     rcx, [rbp+108h]; this
0x180185ea7  mov     r9d, eax; char *
0x180185eaa  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180185eb1  mov     edx, 52h ; 'R'; void *
0x180185eb6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180185ebb  mov     ebx, eax
0x180185ebd  test    eax, eax
0x180185ebf  jns     short loc_180185EED
0x180185ec1  mov     rcx, [rbp+108h]; this
0x180185ec8  mov     r9d, eax; char *
0x180185ecb  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180185ed2  mov     edx, 17Bh; void *
0x180185ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180185edc  lea     rcx, [rbp+100h+ReturnedState]; this
0x180185ee3  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x180185ee8  jmp     loc_180185E2A
0x180185eed  lea     rax, [rsp+200h+var_1C0]
0x180185ef2  mov     [rsp+200h+lpFileName], rax
0x180185ef7  lea     rax, [rsp+200h+var_1C0]
0x180185efc  mov     [rsp+200h+var_1C8], rax
0x180185f01  mov     [rsp+200h+var_1C0], r14w
0x180185f07  mov     r8, [rdi+8]
0x180185f0b  sub     r8, [rdi]
0x180185f0e  sar     r8, 1
0x180185f11  mov     rdx, [rdi]
0x180185f14  lea     rcx, [rsp+200h+lpFileName]
0x180185f19  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180185f1e  test    al, al
0x180185f20  jnz     short loc_180185F5F
0x180185f22  mov     edx, 17Fh; void *
0x180185f27  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180185f2e  mov     r9d, 8007000Eh; char *
0x180185f34  mov     rcx, [rbp+108h]; this
0x180185f3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180185f40  mov     rcx, [rsp+200h+lpFileName]
0x180185f45  lea     rax, [rsp+200h+var_1C0]
0x180185f4a  cmp     rcx, rax
0x180185f4d  jz      loc_1801863A7
0x180185f53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180185f5a  jmp     loc_1801863A2
0x180185f5f  lea     rax, aWcsandboxstate; "WcSandboxState"
0x180185f66  mov     [rsp+200h+var_190], rax
0x180185f6b  mov     [rsp+200h+var_188], 0Eh
0x180185f74  lea     rdx, [rsp+200h+var_190]
0x180185f79  lea     rcx, [rsp+200h+lpFileName]; this
0x180185f7e  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180185f83  test    al, al
0x180185f85  jnz     short loc_180185F8E
0x180185f87  mov     edx, 180h
0x180185f8c  jmp     short loc_180185F27
0x180185f8e  lea     rdx, [rbp+100h+var_160]; struct Path *
0x180185f92  lea     rcx, [rsp+200h+lpFileName]; this
0x180185f97  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x180185f9c  mov     edi, eax
0x180185f9e  test    eax, eax
0x180185fa0  jns     short loc_180185FDC
0x180185fa2  mov     rcx, [rbp+108h]; this
0x180185fa9  mov     r9d, eax; char *
0x180185fac  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180185fb3  mov     edx, 182h; void *
0x180185fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180185fbd  mov     rcx, [rsp+200h+lpFileName]
0x180185fc2  lea     rax, [rsp+200h+var_1C0]
0x180185fc7  cmp     rcx, rax
0x180185fca  jz      loc_180186432
0x180185fd0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180185fd7  jmp     loc_18018642D
0x180185fdc  mov     edx, 6; dwFileAttributes
0x180185fe1  mov     rcx, [rsp+200h+lpFileName]; lpFileName
0x180185fe6  call    cs:__imp_SetFileAttributesW
0x180185fed  nop     dword ptr [rax+rax+00h]
0x180185ff2  test    eax, eax
0x180185ff4  jnz     short loc_180186012
0x180185ff6  mov     rcx, [rbp+108h]; this
0x180185ffd  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186004  mov     edx, 186h; void *
0x180186009  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018600e  mov     edi, eax
0x180186010  jmp     short loc_180185FBD
0x180186012  lea     rax, [rsp+200h+var_1A0]
0x180186017  mov     [rsp+200h+var_1B0], rax
0x18018601c  lea     rax, [rsp+200h+var_1A0]
0x180186021  mov     [rsp+200h+var_1A8], rax
0x180186026  mov     [rsp+200h+var_1A0], r14w
0x18018602c  mov     rdx, [rsp+200h+lpFileName]
0x180186031  mov     r8, [rsp+200h+var_1C8]
0x180186036  sub     r8, rdx
0x180186039  sar     r8, 1
0x18018603c  lea     rcx, [rsp+200h+var_1B0]
0x180186041  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180186046  test    al, al
0x180186048  jnz     short loc_180186074
0x18018604a  mov     edx, 18Bh; void *
0x18018604f  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186056  mov     r9d, 8007000Eh; char *
0x18018605c  mov     rcx, [rbp+108h]; this
0x180186063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186068  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18018606f  jmp     loc_180186379
0x180186074  lea     rax, aHives; "Hives"
0x18018607b  mov     [rsp+200h+var_190], rax
0x180186080  mov     [rsp+200h+var_188], 5
0x180186089  lea     rdx, [rsp+200h+var_190]
0x18018608e  lea     rcx, [rsp+200h+var_1B0]; this
0x180186093  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180186098  test    al, al
0x18018609a  jnz     short loc_1801860A3
0x18018609c  mov     edx, 18Ch
0x1801860a1  jmp     short loc_18018604F
0x1801860a3  xor     edx, edx; struct Path *
0x1801860a5  lea     rcx, [rsp+200h+var_1B0]; this
0x1801860aa  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x1801860af  mov     edi, eax
0x1801860b1  test    eax, eax
0x1801860b3  jns     short loc_1801860DC
0x1801860b5  mov     edx, 18Eh; void *
0x1801860ba  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x1801860c1  mov     r9d, edi; char *
0x1801860c4  mov     rcx, [rbp+108h]; this
0x1801860cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801860d0  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801860d7  jmp     loc_180186404
0x1801860dc  xor     edx, edx; Val
0x1801860de  mov     r8d, 114h; Size
0x1801860e4  lea     rcx, [rbp+100h+var_140]; void *
0x1801860e8  call    memset_0
0x1801860ed  lea     rcx, [rbp+100h+var_140]; this
0x1801860f1  call    ?GetOsVersionInfo@Csl@@YAJAEAU_OSVERSIONINFOW@@@Z; Csl::GetOsVersionInfo(_OSVERSIONINFOW &)
0x1801860f6  mov     edi, eax
0x1801860f8  test    eax, eax
0x1801860fa  jns     short loc_180186103
0x1801860fc  mov     edx, 191h
0x180186101  jmp     short loc_1801860BA
0x180186103  lea     rsi, off_1801C8800; "SYSTEM"
0x18018610a  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180186111  mov     [rbp+100h+Privilege], r14
0x180186118  mov     edx, 1
0x18018611d  lea     rcx, [rbp+100h+Privilege]
0x180186124  call    ORCreateHiveEx
0x180186129  test    eax, eax
0x18018612b  jnz     loc_1801863D5
0x180186131  lea     rax, [rbp+100h+var_170]
0x180186135  mov     [rbp+100h+var_180], rax
0x180186139  lea     rax, [rbp+100h+var_170]
0x18018613d  mov     [rbp+100h+var_178], rax
0x180186141  mov     [rbp+100h+var_170], r14w
0x180186146  mov     rdx, [rsp+200h+var_1B0]
0x18018614b  mov     r8, [rsp+200h+var_1A8]
0x180186150  sub     r8, rdx
0x180186153  sar     r8, 1
0x180186156  lea     rcx, [rbp+100h+var_180]
0x18018615a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18018615f  test    al, al
0x180186161  jz      loc_180186334
0x180186167  mov     rcx, [rsi+10h]
0x18018616b  mov     [rsp+200h+var_190], rcx
0x180186170  or      rax, 0FFFFFFFFFFFFFFFFh
0x180186174  inc     rax
0x180186177  cmp     [rcx+rax*2], r14w
0x18018617c  jnz     short loc_180186174
0x18018617e  mov     [rsp+200h+var_188], rax
0x180186183  lea     rdx, [rsp+200h+var_190]
0x180186188  lea     rcx, [rbp+100h+var_180]; this
0x18018618c  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180186191  test    al, al
0x180186193  jz      loc_1801862ED
0x180186199  mov     [rsp+200h+var_1E0], 1; unsigned int
0x1801861a1  mov     r9d, [rbp+100h+var_138]
0x1801861a5  mov     r8d, [rbp+100h+var_13C]
0x1801861a9  mov     rdx, [rbp+100h+var_180]
0x1801861ad  mov     rdi, [rbp+100h+Privilege]
0x1801861b4  mov     rcx, rdi
0x1801861b7  call    ORSaveHiveEx
0x1801861bc  test    eax, eax
0x1801861be  jnz     loc_180186254
0x1801861c4  mov     rcx, [rbp+100h+var_180]; void *
0x1801861c8  lea     rax, [rbp+100h+var_170]
0x1801861cc  cmp     rcx, rax
0x1801861cf  jz      short loc_1801861D9
0x1801861d1  mov     rdx, rbx; struct std::nothrow_t *
0x1801861d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801861d9  test    rdi, rdi
0x1801861dc  jz      short loc_1801861E7
0x1801861de  mov     rcx, rdi
0x1801861e1  call    ORCloseHive
0x1801861e6  nop
0x1801861e7  add     rsi, 18h
0x1801861eb  lea     rax, qword_1801C8878
0x1801861f2  cmp     rsi, rax
0x1801861f5  jnz     loc_180186111
0x1801861fb  mov     rcx, [rsp+200h+var_1B0]; void *
0x180186200  lea     rax, [rsp+200h+var_1A0]
0x180186205  cmp     rcx, rax
0x180186208  jz      short loc_180186212
0x18018620a  mov     rdx, rbx; struct std::nothrow_t *
0x18018620d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186212  mov     rcx, [rsp+200h+lpFileName]; void *
0x180186217  lea     rax, [rsp+200h+var_1C0]
0x18018621c  cmp     rcx, rax
0x18018621f  jz      short loc_180186229
0x180186221  mov     rdx, rbx; struct std::nothrow_t *
0x180186224  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186229  lea     rcx, [rbp+100h+ReturnedState]; this
0x180186230  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x180186235  mov     rcx, [rbp+100h+SecurityDescriptor]; hMem
0x18018623c  test    rcx, rcx
0x18018623f  jz      short loc_18018624D
0x180186241  call    cs:__imp_LocalFree
0x180186248  nop     dword ptr [rax+rax+00h]
0x18018624d  xor     eax, eax
0x18018624f  jmp     loc_180186458
0x180186254  mov     rcx, [rbp+108h]; this
0x18018625b  mov     r9d, eax; char *
0x18018625e  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186265  mov     edx, 1A5h; void *
0x18018626a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018626f  mov     esi, eax
0x180186271  mov     rcx, [rbp+100h+var_180]; void *
0x180186275  lea     rax, [rbp+100h+var_170]
0x180186279  cmp     rcx, rax
0x18018627c  jz      short loc_180186286
0x18018627e  mov     rdx, rbx; struct std::nothrow_t *
0x180186281  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180186286  test    rdi, rdi
0x180186289  jz      short loc_180186294
0x18018628b  mov     rcx, rdi
0x18018628e  call    ORCloseHive
0x180186293  nop
0x180186294  mov     rcx, [rsp+200h+var_1B0]; void *
0x180186299  lea     rax, [rsp+200h+var_1A0]
0x18018629e  cmp     rcx, rax
0x1801862a1  jz      short loc_1801862AB
0x1801862a3  mov     rdx, rbx; struct std::nothrow_t *
0x1801862a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801862ab  mov     rcx, [rsp+200h+lpFileName]; void *
0x1801862b0  lea     rax, [rsp+200h+var_1C0]
0x1801862b5  cmp     rcx, rax
0x1801862b8  jz      short loc_1801862C2
0x1801862ba  mov     rdx, rbx; struct std::nothrow_t *
0x1801862bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801862c2  lea     rcx, [rbp+100h+ReturnedState]; this
0x1801862c9  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1801862ce  mov     rcx, [rbp+100h+SecurityDescriptor]; hMem
0x1801862d5  test    rcx, rcx
0x1801862d8  jz      short loc_1801862E6
0x1801862da  call    cs:__imp_LocalFree
0x1801862e1  nop     dword ptr [rax+rax+00h]
0x1801862e6  mov     eax, esi
0x1801862e8  jmp     loc_180186458
0x1801862ed  mov     rcx, [rbp+108h]; this
0x1801862f4  mov     r9d, 8007000Eh; char *
0x1801862fa  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186301  mov     edx, 19Eh; void *
0x180186306  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018630b  mov     rcx, [rbp+100h+var_180]; void *
  ... truncated ...
```
