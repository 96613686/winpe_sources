# cxl::Acl::AddAccessDeniedObjectAce(_GUID const &,_GUID const &,ulong,_SID const *,ulong)

- ea: `0x18009d510`
- end: `0x18009d6d3`
- name: `?AddAccessDeniedObjectAce@Acl@cxl@@QEAAXAEBU_GUID@@0KPEBU_SID@@K@Z`
- size: `451`
- prototype: `void __usercall(cxl::Acl *__hidden this@<rcx>, GUID *ObjectTypeGuid@<rdx>, GUID *InheritedObjectTypeGuid@<r8>, unsigned int@<r9d>, PSID pSid, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3e10`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc08`
- `0x18001d284`
- `0x180027494`
- `0x180091b20`
- `0x180091d2c`
- `0x180092d1c`
- `0x18009c728`
- `0x18009c784`
- `0x18009c85c`
- `0x18009d510`
- `0x18009d6dc`
- `0x18009d8ec`
- `0x18009da8c`
- `0x18009dad0`
- `0x18009db28`
- `0x18009dbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d69f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d69f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d596`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d596`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d574`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d574`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedObjectAce` at `0x18009d5c5`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedObjectAce` at `0x18009d5c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cxl::Acl::AddAccessDeniedObjectAce(
        cxl::Acl *this,
        GUID *ObjectTypeGuid,
        GUID *InheritedObjectTypeGuid,
        DWORD a4,
        struct _SID *pSid,
        DWORD AceFlags)
{
  DWORD AclRevision; // r15d
  unsigned int AclUsedBytes; // ebx
  DWORD v11; // ebx
  unsigned int v12; // edx
  struct _ACL *v13; // rdi
  DWORD v14; // eax
  __int64 v15; // rax
  DWORD LastError; // eax
  __int64 v17; // rax
  DWORD AccessMask; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-B8h] BYREF
  struct _ACL *v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  AccessMask = a4;
  cxl::SidBase::VerifySid(pSid);
  cxl::AclBase::ReportErrorIfEmpty(this);
  AclRevision = cxl::AclBase::GetAclRevision(this);
  AclUsedBytes = cxl::AclBase::GetAclUsedBytes(this);
  v11 = GetLengthSid(pSid) + 84 + AclUsedBytes;
  v13 = (struct _ACL *)cxl::LocalHeap::Alloc(v11, v12);
  v20 = v13;
  if ( !InitializeAcl(v13, v11, AclRevision) )
  {
    std::wstring::wstring(v22);
    cxl::StringWriter::StringWriter(v21, v22);
    cxl::TextWriter::Write<21>(v21);
    LastError = GetLastError();
    v17 = cxl::WinError(&AccessMask, LastError);
    cxl::Exception::Exception(pExceptionObject, v17, v22);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !AddAccessDeniedObjectAce(v13, AclRevision, AceFlags, AccessMask, ObjectTypeGuid, InheritedObjectTypeGuid, pSid) )
  {
    std::wstring::wstring(v22);
    cxl::StringWriter::StringWriter(v21, v22);
    cxl::TextWriter::Write<32>(v21);
    v14 = GetLastError();
    v15 = cxl::WinError(&AccessMask, v14);
    cxl::Exception::Exception(pExceptionObject, v15, v22);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::AclBase::CopyAclTo(this, v13);
  cxl::AclBase::VerifyAcl(v13);
  v20 = 0;
  cxl::Acl::Attach(this, v13);
  cxl::LocalHeapPtr<void>::Clear(v19);
}

```

## disassembly

```asm
0x18009d510  push    rbp
0x18009d512  push    rbx
0x18009d513  push    rsi
0x18009d514  push    rdi
0x18009d515  push    r12
0x18009d517  push    r13
0x18009d519  push    r14
0x18009d51b  push    r15
0x18009d51d  lea     rbp, [rsp-28h]
0x18009d522  sub     rsp, 128h
0x18009d529  mov     rax, cs:__security_cookie
0x18009d530  xor     rax, rsp
0x18009d533  mov     [rbp+60h+var_50], rax
0x18009d537  mov     [rsp+160h+AccessMask], r9d
0x18009d53c  mov     r13, r8
0x18009d53f  mov     r12, rdx
0x18009d542  mov     rsi, rcx
0x18009d545  mov     r14, [rbp+60h+pSid]
0x18009d54c  mov     rcx, r14; struct _SID *
0x18009d54f  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18009d554  mov     rcx, rsi; this
0x18009d557  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18009d55c  mov     rcx, rsi; this
0x18009d55f  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x18009d564  mov     r15d, eax
0x18009d567  mov     rcx, rsi; this
0x18009d56a  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x18009d56f  mov     ebx, eax
0x18009d571  mov     rcx, r14; pSid
0x18009d574  call    cs:__imp_GetLengthSid
0x18009d57a  add     eax, 54h ; 'T'
0x18009d57d  add     ebx, eax
0x18009d57f  mov     ecx, ebx; uBytes
0x18009d581  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x18009d586  mov     rdi, rax
0x18009d589  mov     [rsp+160h+var_110], rax
0x18009d58e  mov     r8d, r15d; dwAclRevision
0x18009d591  mov     edx, ebx; nAclLength
0x18009d593  mov     rcx, rax; pAcl
0x18009d596  call    cs:__imp_InitializeAcl
0x18009d59c  test    eax, eax
0x18009d59e  jz      loc_18009D67A
0x18009d5a4  mov     [rsp+160h+var_130], r14; pSid
0x18009d5a9  mov     [rsp+160h+InheritedObjectTypeGuid], r13; InheritedObjectTypeGuid
0x18009d5ae  mov     [rsp+160h+ObjectTypeGuid], r12; ObjectTypeGuid
0x18009d5b3  mov     r9d, [rsp+160h+AccessMask]; AccessMask
0x18009d5b8  mov     r8d, [rbp+60h+AceFlags]; AceFlags
0x18009d5bf  mov     edx, r15d; dwAceRevision
0x18009d5c2  mov     rcx, rdi; pAcl
0x18009d5c5  call    cs:__imp_AddAccessDeniedObjectAce
0x18009d5cb  test    eax, eax
0x18009d5cd  jz      short loc_18009D621
0x18009d5cf  mov     rdx, rdi; pAcl
0x18009d5d2  mov     rcx, rsi; this
0x18009d5d5  call    ?CopyAclTo@AclBase@cxl@@QEAAXPEAU_ACL@@@Z; cxl::AclBase::CopyAclTo(_ACL *)
0x18009d5da  mov     rcx, rdi; struct _ACL *
0x18009d5dd  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x18009d5e2  mov     [rsp+160h+var_110], 0
0x18009d5eb  mov     rdx, rdi; struct _ACL *
0x18009d5ee  mov     rcx, rsi; this
0x18009d5f1  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x18009d5f6  nop
0x18009d5f7  lea     rcx, [rsp+160h+var_118]
0x18009d5fc  call    ?Clear@?$LocalHeapPtr@X@cxl@@QEAAXXZ; cxl::LocalHeapPtr<void>::Clear(void)
0x18009d601  mov     rcx, [rbp+60h+var_50]
0x18009d605  xor     rcx, rsp; StackCookie
0x18009d608  call    __security_check_cookie
0x18009d60d  add     rsp, 128h
0x18009d614  pop     r15
0x18009d616  pop     r14
0x18009d618  pop     r13
0x18009d61a  pop     r12
0x18009d61c  pop     rdi
0x18009d61d  pop     rsi
0x18009d61e  pop     rbx
0x18009d61f  pop     rbp
0x18009d620  retn
0x18009d621  lea     rcx, [rsp+160h+var_E8]
0x18009d626  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d62b  nop
0x18009d62c  lea     rdx, [rsp+160h+var_E8]
0x18009d631  lea     rcx, [rsp+160h+var_108]
0x18009d636  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d63b  nop
0x18009d63c  lea     rcx, [rsp+160h+var_108]
0x18009d641  call    ??$Write@$0CA@@TextWriter@cxl@@QEAAAEAV01@AEAY0CA@$$CBD@Z; cxl::TextWriter::Write<32>(char const (&)[32])
0x18009d646  call    cs:__imp_GetLastError
0x18009d64c  mov     edx, eax
0x18009d64e  lea     rcx, [rsp+160h+AccessMask]
0x18009d653  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d658  mov     rdx, rax
0x18009d65b  lea     r8, [rsp+160h+var_E8]
0x18009d660  lea     rcx, [rbp+60h+pExceptionObject]
0x18009d664  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d669  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d670  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18009d674  call    _CxxThrowException_0
0x18009d67a  lea     rcx, [rsp+160h+var_E8]
0x18009d67f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d684  nop
0x18009d685  lea     rdx, [rsp+160h+var_E8]
0x18009d68a  lea     rcx, [rsp+160h+var_108]
0x18009d68f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d694  nop
0x18009d695  lea     rcx, [rsp+160h+var_108]
0x18009d69a  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x18009d69f  call    cs:__imp_GetLastError
0x18009d6a5  mov     edx, eax
0x18009d6a7  lea     rcx, [rsp+160h+AccessMask]
0x18009d6ac  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d6b1  mov     rdx, rax
0x18009d6b4  lea     r8, [rsp+160h+var_E8]
0x18009d6b9  lea     rcx, [rbp+60h+pExceptionObject]
0x18009d6bd  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d6c2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d6c9  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18009d6cd  call    _CxxThrowException_0
```
