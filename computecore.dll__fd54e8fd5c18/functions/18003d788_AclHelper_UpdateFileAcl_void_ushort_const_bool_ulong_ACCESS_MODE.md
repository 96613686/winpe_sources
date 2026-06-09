# AclHelper::UpdateFileAcl(void *,ushort const *,bool,ulong,_ACCESS_MODE)

- ea: `0x18003d788`
- end: `0x18003d9d9`
- name: `?UpdateFileAcl@AclHelper@@YAXPEAXPEBG_NKW4_ACCESS_MODE@@@Z`
- size: `593`
- prototype: `void __usercall(AclHelper *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, unsigned int, enum _ACCESS_MODE)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ae9c`
- `0x18003b0dc`
- `0x18003ba60`
- `0x18003bc98`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x18001017c`
- `0x180027380`
- `0x180039b54`
- `0x180039be4`
- `0x18003ae18`
- `0x18003d6cc`
- `0x18003d788`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d97d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d97d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d959`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d959`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d969`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d7e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d7e3`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18003d920`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18003d920`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18003d849`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18003d849`

## string_xrefs

- `0x18003d9a0`: `onecore\vm\compute\dll\lib\inc\AclHelper.h`
- `0x18003d9b2`: `onecore\vm\compute\dll\lib\inc\AclHelper.h`
- `0x18003d9c7`: `onecore\vm\compute\dll\lib\inc\AclHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AclHelper::UpdateFileAcl(
        AclHelper *this,
        LPCWSTR lpFileName,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  char v6; // di
  char *FileW; // rbx
  const char *v9; // r9
  DWORD SecurityInfo; // eax
  const struct _ACL *Dacl; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // edi
  DWORD v14; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-81h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-81h]
  HLOCAL hMem[2]; // [rsp+50h] [rbp-51h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-41h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-21h] BYREF
  PACL pDacl[2]; // [rsp+A0h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+B0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v6 = (char)a3;
  FileW = (char *)CreateFileW(lpFileName, 0x60000u, 3u, 0, 3u, ((unsigned __int8)a3 << 25) | 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\inc\\AclHelper.h",
      v9);
  *(_OWORD *)ppSecurityDescriptor = 0;
  SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, ppSecurityDescriptor);
  if ( SecurityInfo )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\inc\\AclHelper.h",
      (const char *)SecurityInfo,
      dwCreationDisposition);
  *(_OWORD *)pDacl = 0;
  Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)ppSecurityDescriptor);
  Vml::VmDacl::VmDacl((Vml::VmDacl *)pDacl, Dacl);
  memset_0(hMem, 0, 0x50u);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, v12);
  if ( a5 == 1 )
  {
    v13 = v6 != 0 ? 3 : 0;
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, this, a4, v13, GRANT_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], a4, v13, GRANT_ACCESS);
  }
  else
  {
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, this, 0, 0, REVOKE_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, hMem[0], 0, 0, REVOKE_ACCESS);
  }
  v14 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, pDacl[0], 0);
  if ( v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\inc\\AclHelper.h",
      (const char *)v14,
      dwCreationDispositiona);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  std::wstring::~wstring(v19);
  std::wstring::~wstring(v18);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  if ( ppSecurityDescriptor[0] )
    LocalFree(ppSecurityDescriptor[0]);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
}

```

## disassembly

```asm
0x18003d788  push    rbp
0x18003d78a  push    rbx
0x18003d78b  push    rsi
0x18003d78c  push    rdi
0x18003d78d  push    r14
0x18003d78f  lea     rbp, [rsp-2Fh]
0x18003d794  sub     rsp, 0D0h
0x18003d79b  mov     rax, cs:__security_cookie
0x18003d7a2  xor     rax, rsp
0x18003d7a5  mov     [rbp+4Fh+var_30], rax
0x18003d7a9  mov     r14d, r9d
0x18003d7ac  movzx   edi, r8b
0x18003d7b0  mov     r10, rdx
0x18003d7b3  mov     rsi, rcx
0x18003d7b6  mov     eax, edi
0x18003d7b8  shl     eax, 19h
0x18003d7bb  bts     eax, 7
0x18003d7bf  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18003d7c8  mov     [rsp+0F0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18003d7cc  mov     eax, 3
0x18003d7d1  mov     [rsp+0F0h+dwCreationDisposition], eax; dwCreationDisposition
0x18003d7d5  xor     r9d, r9d; lpSecurityAttributes
0x18003d7d8  mov     r8d, eax; dwShareMode
0x18003d7db  mov     edx, 60000h; dwDesiredAccess
0x18003d7e0  mov     rcx, r10; lpFileName
0x18003d7e3  call    cs:__imp_CreateFileW
0x18003d7e9  mov     rbx, rax
0x18003d7ec  mov     [rbp+4Fh+var_B0], rax
0x18003d7f0  inc     rax
0x18003d7f3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003d7f9  setz    al
0x18003d7fc  mov     rcx, [rbp+57h]; this
0x18003d800  test    al, al
0x18003d802  jnz     loc_18003D9B2
0x18003d808  xorps   xmm0, xmm0
0x18003d80b  movups  xmmword ptr [rbp+4Fh+var_40], xmm0
0x18003d80f  mov     [rbp+4Fh+var_40], 0
0x18003d817  lea     rax, [rbp+4Fh+var_40]
0x18003d81b  mov     [rsp+0F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18003d820  mov     [rsp+0F0h+hTemplateFile], 0; ppSacl
0x18003d829  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], 0; ppDacl
0x18003d832  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; unsigned int
0x18003d83b  xor     r9d, r9d; ppsidOwner
0x18003d83e  lea     edx, [r9+1]; ObjectType
0x18003d842  lea     r8d, [r9+4]; SecurityInfo
0x18003d846  mov     rcx, rbx; handle
0x18003d849  call    cs:__imp_GetSecurityInfo
0x18003d84f  mov     rcx, [rbp+57h]; this
0x18003d853  test    eax, eax
0x18003d855  jnz     loc_18003D9C4
0x18003d85b  xorps   xmm0, xmm0
0x18003d85e  movups  xmmword ptr [rbp+4Fh+pDacl], xmm0
0x18003d862  lea     rcx, [rbp+4Fh+var_40]; this
0x18003d866  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x18003d86b  mov     rdx, rax; struct _ACL *
0x18003d86e  lea     rcx, [rbp+4Fh+pDacl]; this
0x18003d872  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x18003d877  nop
0x18003d878  xor     edx, edx; Val
0x18003d87a  lea     r8d, [rdx+50h]; Size
0x18003d87e  lea     rcx, [rbp+4Fh+hMem]; void *
0x18003d882  call    memset_0
0x18003d887  lea     rcx, [rbp+4Fh+hMem]; this
0x18003d88b  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x18003d890  nop
0x18003d891  mov     rdx, rsi; void *
0x18003d894  lea     rcx, [rbp+4Fh+pDacl]; this
0x18003d898  cmp     [rbp+4Fh+arg_20], 1
0x18003d89c  jnz     short loc_18003D8C9
0x18003d89e  neg     dil
0x18003d8a1  sbb     edi, edi
0x18003d8a3  and     edi, 3
0x18003d8a6  mov     [rsp+0F0h+dwCreationDisposition], 1; enum _ACCESS_MODE
0x18003d8ae  mov     r9d, edi; unsigned int
0x18003d8b1  mov     r8d, r14d; unsigned int
0x18003d8b4  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x18003d8b9  mov     [rsp+0F0h+dwCreationDisposition], 1
0x18003d8c1  mov     r9d, edi
0x18003d8c4  mov     r8d, r14d
0x18003d8c7  jmp     short loc_18003D8EA
0x18003d8c9  mov     [rsp+0F0h+dwCreationDisposition], 4; enum _ACCESS_MODE
0x18003d8d1  xor     r9d, r9d; unsigned int
0x18003d8d4  xor     r8d, r8d; unsigned int
0x18003d8d7  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x18003d8dc  mov     [rsp+0F0h+dwCreationDisposition], 4; enum _ACCESS_MODE
0x18003d8e4  xor     r9d, r9d; unsigned int
0x18003d8e7  xor     r8d, r8d; unsigned int
0x18003d8ea  mov     rdx, [rbp+4Fh+hMem]; void *
0x18003d8ee  lea     rcx, [rbp+4Fh+pDacl]; this
0x18003d8f2  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x18003d8f7  mov     rax, [rbp+4Fh+pDacl]
0x18003d8fb  mov     [rsp+0F0h+hTemplateFile], 0; pSacl
0x18003d904  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; pDacl
0x18003d909  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; unsigned int
0x18003d912  xor     r9d, r9d; psidOwner
0x18003d915  lea     edx, [r9+1]; ObjectType
0x18003d919  lea     r8d, [r9+4]; SecurityInfo
0x18003d91d  mov     rcx, rbx; handle
0x18003d920  call    cs:__imp_SetSecurityInfo
0x18003d926  mov     rcx, [rbp+57h]; this
0x18003d92a  test    eax, eax
0x18003d92c  jnz     short loc_18003D99D
0x18003d92e  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18003d932  test    rcx, rcx
0x18003d935  jz      short loc_18003D93D
0x18003d937  call    cs:__imp_LocalFree
0x18003d93d  lea     rcx, [rbp+4Fh+var_70]
0x18003d941  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d946  lea     rcx, [rbp+4Fh+var_90]
0x18003d94a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d94f  nop
0x18003d950  mov     rcx, [rbp+4Fh+pDacl]; hMem
0x18003d954  test    rcx, rcx
0x18003d957  jz      short loc_18003D960
0x18003d959  call    cs:__imp_LocalFree
0x18003d95f  nop
0x18003d960  mov     rcx, [rbp+4Fh+var_40]; hMem
0x18003d964  test    rcx, rcx
0x18003d967  jz      short loc_18003D970
0x18003d969  call    cs:__imp_LocalFree
0x18003d96f  nop
0x18003d970  lea     rax, [rbx-1]
0x18003d974  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d978  ja      short loc_18003D983
0x18003d97a  mov     rcx, rbx; hObject
0x18003d97d  call    cs:__imp_CloseHandle
0x18003d983  mov     rcx, [rbp+4Fh+var_30]
0x18003d987  xor     rcx, rsp; StackCookie
0x18003d98a  call    __security_check_cookie
0x18003d98f  add     rsp, 0D0h
0x18003d996  pop     r14
0x18003d998  pop     rdi
0x18003d999  pop     rsi
0x18003d99a  pop     rbx
0x18003d99b  pop     rbp
0x18003d99c  retn
0x18003d99d  mov     r9d, eax; char *
0x18003d9a0  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\dll\\lib\\inc\\Ac"...
0x18003d9a7  mov     edx, 47h ; 'G'; void *
0x18003d9ac  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003d9b2  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\dll\\lib\\inc\\Ac"...
0x18003d9b9  mov     edx, 24h ; '$'; void *
0x18003d9be  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003d9c4  mov     r9d, eax; char *
0x18003d9c7  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\dll\\lib\\inc\\Ac"...
0x18003d9ce  mov     edx, 2Fh ; '/'; void *
0x18003d9d3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
