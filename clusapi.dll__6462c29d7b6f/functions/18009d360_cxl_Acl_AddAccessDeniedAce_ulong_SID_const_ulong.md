# cxl::Acl::AddAccessDeniedAce(ulong,_SID const *,ulong)

- ea: `0x18009d360`
- end: `0x18009d50a`
- name: `?AddAccessDeniedAce@Acl@cxl@@QEAAXKPEBU_SID@@K@Z`
- size: `426`
- prototype: `void __fastcall(cxl::Acl *__hidden this, DWORD AccessMask, const struct _SID *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3d68`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc08`
- `0x18001d284`
- `0x180027494`
- `0x180091b20`
- `0x180091c74`
- `0x180092d1c`
- `0x18009c728`
- `0x18009c784`
- `0x18009c85c`
- `0x18009d360`
- `0x18009d6dc`
- `0x18009d8ec`
- `0x18009da8c`
- `0x18009dad0`
- `0x18009db28`
- `0x18009dbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d4d6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d3d8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d3d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d3b6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d3b6`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x18009d3f7`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x18009d3f7`

## string_xrefs

- `0x18009d46c`: `AddAccessDeniedAceEx failed`

## pseudocode

```c
void __fastcall cxl::Acl::AddAccessDeniedAce(cxl::Acl *this, DWORD AccessMask, struct _SID *a3)
{
  DWORD AclRevision; // r15d
  unsigned int AclUsedBytes; // ebx
  DWORD v8; // ebx
  unsigned int v9; // edx
  struct _ACL *v10; // rdi
  DWORD v11; // eax
  __int64 v12; // rax
  DWORD LastError; // eax
  __int64 v14; // rax
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  struct _ACL *v17; // [rsp+40h] [rbp-C0h]
  _BYTE v18[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-70h] BYREF

  cxl::SidBase::VerifySid(a3);
  cxl::AclBase::ReportErrorIfEmpty(this);
  AclRevision = cxl::AclBase::GetAclRevision(this);
  AclUsedBytes = cxl::AclBase::GetAclUsedBytes(this);
  v8 = GetLengthSid(a3) + 16 + AclUsedBytes;
  v10 = (struct _ACL *)cxl::LocalHeap::Alloc(v8, v9);
  v17 = v10;
  if ( !InitializeAcl(v10, v8, AclRevision) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<21>(v18);
    LastError = GetLastError();
    v14 = cxl::WinError(v15, LastError);
    cxl::Exception::Exception(pExceptionObject, v14, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !AddAccessDeniedAceEx(v10, AclRevision, 0, AccessMask, a3) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<28>(v18, "AddAccessDeniedAceEx failed");
    v11 = GetLastError();
    v12 = cxl::WinError(v15, v11);
    cxl::Exception::Exception(pExceptionObject, v12, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::AclBase::CopyAclTo(this, v10);
  cxl::AclBase::VerifyAcl(v10);
  v17 = 0;
  cxl::Acl::Attach(this, v10);
  cxl::LocalHeapPtr<void>::Clear(v16);
}

```

## disassembly

```asm
0x18009d360  push    rbp
0x18009d362  push    rbx
0x18009d363  push    rsi
0x18009d364  push    rdi
0x18009d365  push    r12
0x18009d367  push    r14
0x18009d369  push    r15
0x18009d36b  lea     rbp, [rsp-10h]
0x18009d370  sub     rsp, 110h
0x18009d377  mov     rax, cs:__security_cookie
0x18009d37e  xor     rax, rsp
0x18009d381  mov     [rbp+40h+var_40], rax
0x18009d385  mov     r14, r8
0x18009d388  mov     r12d, edx
0x18009d38b  mov     rsi, rcx
0x18009d38e  mov     rcx, r8; struct _SID *
0x18009d391  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18009d396  mov     rcx, rsi; this
0x18009d399  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18009d39e  mov     rcx, rsi; this
0x18009d3a1  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x18009d3a6  mov     r15d, eax
0x18009d3a9  mov     rcx, rsi; this
0x18009d3ac  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x18009d3b1  mov     ebx, eax
0x18009d3b3  mov     rcx, r14; pSid
0x18009d3b6  call    cs:__imp_GetLengthSid
0x18009d3bc  add     eax, 10h
0x18009d3bf  add     ebx, eax
0x18009d3c1  mov     ecx, ebx; uBytes
0x18009d3c3  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x18009d3c8  mov     rdi, rax
0x18009d3cb  mov     [rsp+140h+var_100], rax
0x18009d3d0  mov     r8d, r15d; dwAclRevision
0x18009d3d3  mov     edx, ebx; nAclLength
0x18009d3d5  mov     rcx, rax; pAcl
0x18009d3d8  call    cs:__imp_InitializeAcl
0x18009d3de  test    eax, eax
0x18009d3e0  jz      loc_18009D4B1
0x18009d3e6  mov     [rsp+140h+pSid], r14; pSid
0x18009d3eb  mov     r9d, r12d; AccessMask
0x18009d3ee  xor     r8d, r8d; AceFlags
0x18009d3f1  mov     edx, r15d; dwAceRevision
0x18009d3f4  mov     rcx, rdi; pAcl
0x18009d3f7  call    cs:__imp_AddAccessDeniedAceEx
0x18009d3fd  test    eax, eax
0x18009d3ff  jz      short loc_18009D451
0x18009d401  mov     rdx, rdi; pAcl
0x18009d404  mov     rcx, rsi; this
0x18009d407  call    ?CopyAclTo@AclBase@cxl@@QEAAXPEAU_ACL@@@Z; cxl::AclBase::CopyAclTo(_ACL *)
0x18009d40c  mov     rcx, rdi; struct _ACL *
0x18009d40f  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x18009d414  mov     [rsp+140h+var_100], 0
0x18009d41d  mov     rdx, rdi; struct _ACL *
0x18009d420  mov     rcx, rsi; this
0x18009d423  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x18009d428  nop
0x18009d429  lea     rcx, [rsp+140h+var_108]
0x18009d42e  call    ?Clear@?$LocalHeapPtr@X@cxl@@QEAAXXZ; cxl::LocalHeapPtr<void>::Clear(void)
0x18009d433  mov     rcx, [rbp+40h+var_40]
0x18009d437  xor     rcx, rsp; StackCookie
0x18009d43a  call    __security_check_cookie
0x18009d43f  add     rsp, 110h
0x18009d446  pop     r15
0x18009d448  pop     r14
0x18009d44a  pop     r12
0x18009d44c  pop     rdi
0x18009d44d  pop     rsi
0x18009d44e  pop     rbx
0x18009d44f  pop     rbp
0x18009d450  retn
0x18009d451  lea     rcx, [rsp+140h+var_D8]
0x18009d456  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d45b  nop
0x18009d45c  lea     rdx, [rsp+140h+var_D8]
0x18009d461  lea     rcx, [rsp+140h+var_F8]
0x18009d466  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d46b  nop
0x18009d46c  lea     rdx, aAddaccessdenie_0; "AddAccessDeniedAceEx failed"
0x18009d473  lea     rcx, [rsp+140h+var_F8]
0x18009d478  call    ??$Write@$0BM@@TextWriter@cxl@@QEAAAEAV01@AEAY0BM@$$CBD@Z; cxl::TextWriter::Write<28>(char const (&)[28])
0x18009d47d  call    cs:__imp_GetLastError
0x18009d483  mov     edx, eax
0x18009d485  lea     rcx, [rsp+140h+var_110]
0x18009d48a  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d48f  mov     rdx, rax
0x18009d492  lea     r8, [rsp+140h+var_D8]
0x18009d497  lea     rcx, [rbp+40h+pExceptionObject]
0x18009d49b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d4a0  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d4a7  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18009d4ab  call    _CxxThrowException_0
0x18009d4b1  lea     rcx, [rsp+140h+var_D8]
0x18009d4b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d4bb  nop
0x18009d4bc  lea     rdx, [rsp+140h+var_D8]
0x18009d4c1  lea     rcx, [rsp+140h+var_F8]
0x18009d4c6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d4cb  nop
0x18009d4cc  lea     rcx, [rsp+140h+var_F8]
0x18009d4d1  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x18009d4d6  call    cs:__imp_GetLastError
0x18009d4dc  mov     edx, eax
0x18009d4de  lea     rcx, [rsp+140h+var_110]
0x18009d4e3  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d4e8  mov     rdx, rax
0x18009d4eb  lea     r8, [rsp+140h+var_D8]
0x18009d4f0  lea     rcx, [rbp+40h+pExceptionObject]
0x18009d4f4  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d4f9  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d500  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18009d504  call    _CxxThrowException_0
```
