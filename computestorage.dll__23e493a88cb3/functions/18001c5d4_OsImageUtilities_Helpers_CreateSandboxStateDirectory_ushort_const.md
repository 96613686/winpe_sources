# OsImageUtilities::Helpers::CreateSandboxStateDirectory(ushort const *)

- ea: `0x18001c5d4`
- end: `0x18001c75d`
- name: `?CreateSandboxStateDirectory@Helpers@OsImageUtilities@@YAXPEBG@Z`
- size: `393`
- prototype: `void __fastcall(PCWSTR pszPathIn, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014c20`
- `0x18001ea88`

## callees

- `0x180002690`
- `0x180008a8c`
- `0x180008fac`
- `0x18000971c`
- `0x18000a578`
- `0x1800136f8`
- `0x18001c5d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001c6c2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001c6c2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001c697`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001c697`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c611`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c611`

## string_xrefs

- `0x18001c727`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001c739`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001c74b`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
void __fastcall OsImageUtilities::Helpers::CreateSandboxStateDirectory(PCWSTR pszPathIn, const unsigned __int16 *a2)
{
  const char *v3; // r9
  const WCHAR *v4; // rcx
  const char *v5; // r9
  const WCHAR *v6; // rcx
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v13; // r9
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-11h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp+Fh]
  __int128 v18; // [rsp+60h] [rbp+17h] BYREF
  __int64 v19; // [rsp+70h] [rbp+27h]
  __int128 v20; // [rsp+78h] [rbp+2Fh] BYREF
  __int64 v21; // [rsp+88h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v3);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  v20 = 0;
  v21 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v20, 17);
  v18 = 0;
  v19 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v18, 18);
  Vml::CombineFilePath(lpPathName, pszPathIn, L"WcSandboxState");
  v4 = (const WCHAR *)lpPathName;
  if ( v17 > 7 )
    v4 = lpPathName[0];
  if ( !CreateDirectoryW(v4, &SecurityAttributes) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v5);
  v6 = (const WCHAR *)lpPathName;
  if ( v17 > 7 )
    v6 = lpPathName[0];
  if ( !SetFileAttributesW(v6, 6u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v7);
  std::wstring::~wstring((char **)lpPathName);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v18, v8, v9, v10);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v20, v11, v12, v13);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x18001c5d4  mov     [rsp-8+arg_8], rbx
0x18001c5d9  push    rbp
0x18001c5da  lea     rbp, [rsp-57h]
0x18001c5df  sub     rsp, 0A0h
0x18001c5e6  mov     rax, cs:__security_cookie
0x18001c5ed  xor     rax, rsp
0x18001c5f0  mov     [rbp+57h+var_10], rax
0x18001c5f4  mov     rbx, rcx
0x18001c5f7  mov     [rbp+57h+SecurityDescriptor], 0
0x18001c5ff  xor     r9d, r9d; SecurityDescriptorSize
0x18001c602  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001c606  lea     edx, [r9+1]; StringSDRevision
0x18001c60a  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;SY)"
0x18001c611  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c618  nop     dword ptr [rax+rax+00h]
0x18001c61d  mov     rcx, [rbp+5Fh]; this
0x18001c621  test    eax, eax
0x18001c623  jz      loc_18001C739
0x18001c629  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18001c631  mov     rax, [rbp+57h+SecurityDescriptor]
0x18001c635  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001c639  xor     eax, eax
0x18001c63b  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18001c63f  xorps   xmm0, xmm0
0x18001c642  movups  [rbp+57h+var_28], xmm0
0x18001c646  mov     [rbp+57h+var_18], rax
0x18001c64a  lea     edx, [rax+11h]; int
0x18001c64d  lea     rcx, [rbp+57h+var_28]; this
0x18001c651  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001c656  nop
0x18001c657  xorps   xmm0, xmm0
0x18001c65a  xor     eax, eax
0x18001c65c  movups  [rbp+57h+var_40], xmm0
0x18001c660  mov     [rbp+57h+var_30], rax
0x18001c664  lea     edx, [rax+12h]; int
0x18001c667  lea     rcx, [rbp+57h+var_40]; this
0x18001c66b  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001c670  nop
0x18001c671  lea     r8, aWcsandboxstate; "WcSandboxState"
0x18001c678  mov     rdx, rbx; pszPathIn
0x18001c67b  lea     rcx, [rbp+57h+lpPathName]; Src
0x18001c67f  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001c684  nop
0x18001c685  lea     rcx, [rbp+57h+lpPathName]
0x18001c689  cmp     [rbp+57h+var_48], 7
0x18001c68e  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x18001c693  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18001c697  call    cs:__imp_CreateDirectoryW
0x18001c69e  nop     dword ptr [rax+rax+00h]
0x18001c6a3  mov     rcx, [rbp+5Fh]; this
0x18001c6a7  test    eax, eax
0x18001c6a9  jz      loc_18001C74B
0x18001c6af  lea     rcx, [rbp+57h+lpPathName]
0x18001c6b3  cmp     [rbp+57h+var_48], 7
0x18001c6b8  cmova   rcx, [rbp+57h+lpPathName]; lpFileName
0x18001c6bd  mov     edx, 6; dwFileAttributes
0x18001c6c2  call    cs:__imp_SetFileAttributesW
0x18001c6c9  nop     dword ptr [rax+rax+00h]
0x18001c6ce  mov     rcx, [rbp+5Fh]; this
0x18001c6d2  test    eax, eax
0x18001c6d4  jz      short loc_18001C727
0x18001c6d6  lea     rcx, [rbp+57h+lpPathName]
0x18001c6da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c6df  nop
0x18001c6e0  lea     rcx, [rbp+57h+var_40]; this
0x18001c6e4  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001c6e9  nop
0x18001c6ea  lea     rcx, [rbp+57h+var_28]; this
0x18001c6ee  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001c6f3  nop
0x18001c6f4  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18001c6f8  test    rcx, rcx
0x18001c6fb  jz      short loc_18001C709
0x18001c6fd  call    cs:__imp_LocalFree
0x18001c704  nop     dword ptr [rax+rax+00h]
0x18001c709  mov     rcx, [rbp+57h+var_10]
0x18001c70d  xor     rcx, rsp; StackCookie
0x18001c710  call    __security_check_cookie
0x18001c715  mov     rbx, [rsp+0A0h+arg_8]
0x18001c71d  add     rsp, 0A0h
0x18001c724  pop     rbp
0x18001c725  retn
0x18001c727  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001c72e  mov     edx, 14Fh; void *
0x18001c733  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001c739  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001c740  mov     edx, 146h; void *
0x18001c745  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001c74b  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001c752  mov     edx, 14Eh; void *
0x18001c757  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
