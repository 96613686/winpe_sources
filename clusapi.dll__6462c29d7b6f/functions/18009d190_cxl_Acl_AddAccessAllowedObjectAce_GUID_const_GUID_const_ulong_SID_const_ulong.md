# cxl::Acl::AddAccessAllowedObjectAce(_GUID const &,_GUID const &,ulong,_SID const *,ulong)

- ea: `0x18009d190`
- end: `0x18009d35a`
- name: `?AddAccessAllowedObjectAce@Acl@cxl@@QEAAXAEBU_GUID@@0KPEBU_SID@@K@Z`
- size: `458`
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
- `0x180091d60`
- `0x180092d1c`
- `0x18009c728`
- `0x18009c784`
- `0x18009c85c`
- `0x18009d190`
- `0x18009d6dc`
- `0x18009d8ec`
- `0x18009da8c`
- `0x18009dad0`
- `0x18009db28`
- `0x18009dbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d326`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d216`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d216`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d1f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d1f4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedObjectAce` at `0x18009d250`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedObjectAce` at `0x18009d250`

## string_xrefs

- `0x18009d2bc`: `AddAccessAllowedObjectAce failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cxl::Acl::AddAccessAllowedObjectAce(
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
  cxl::AclBase::CopyAclTo(this, v13);
  if ( !AddAccessAllowedObjectAce(v13, AclRevision, AceFlags, AccessMask, ObjectTypeGuid, InheritedObjectTypeGuid, pSid) )
  {
    std::wstring::wstring(v22);
    cxl::StringWriter::StringWriter(v21, v22);
    cxl::TextWriter::Write<33>(v21, "AddAccessAllowedObjectAce failed");
    v14 = GetLastError();
    v15 = cxl::WinError(&AccessMask, v14);
    cxl::Exception::Exception(pExceptionObject, v15, v22);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::AclBase::VerifyAcl(v13);
  v20 = 0;
  cxl::Acl::Attach(this, v13);
  cxl::LocalHeapPtr<void>::Clear(v19);
}

```

## disassembly

```asm
0x18009d190  push    rbp
0x18009d192  push    rbx
0x18009d193  push    rsi
0x18009d194  push    rdi
0x18009d195  push    r12
0x18009d197  push    r13
0x18009d199  push    r14
0x18009d19b  push    r15
0x18009d19d  lea     rbp, [rsp-28h]
0x18009d1a2  sub     rsp, 128h
0x18009d1a9  mov     rax, cs:__security_cookie
0x18009d1b0  xor     rax, rsp
0x18009d1b3  mov     [rbp+60h+var_50], rax
0x18009d1b7  mov     [rsp+160h+AccessMask], r9d
0x18009d1bc  mov     r13, r8
0x18009d1bf  mov     r12, rdx
0x18009d1c2  mov     rsi, rcx
0x18009d1c5  mov     r14, [rbp+60h+pSid]
0x18009d1cc  mov     rcx, r14; struct _SID *
0x18009d1cf  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18009d1d4  mov     rcx, rsi; this
0x18009d1d7  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18009d1dc  mov     rcx, rsi; this
0x18009d1df  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x18009d1e4  mov     r15d, eax
0x18009d1e7  mov     rcx, rsi; this
0x18009d1ea  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x18009d1ef  mov     ebx, eax
0x18009d1f1  mov     rcx, r14; pSid
0x18009d1f4  call    cs:__imp_GetLengthSid
0x18009d1fa  add     eax, 54h ; 'T'
0x18009d1fd  add     ebx, eax
0x18009d1ff  mov     ecx, ebx; uBytes
0x18009d201  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x18009d206  mov     rdi, rax
0x18009d209  mov     [rsp+160h+var_110], rax
0x18009d20e  mov     r8d, r15d; dwAclRevision
0x18009d211  mov     edx, ebx; nAclLength
0x18009d213  mov     rcx, rax; pAcl
0x18009d216  call    cs:__imp_InitializeAcl
0x18009d21c  test    eax, eax
0x18009d21e  jz      loc_18009D301
0x18009d224  mov     rdx, rdi; pAcl
0x18009d227  mov     rcx, rsi; this
0x18009d22a  call    ?CopyAclTo@AclBase@cxl@@QEAAXPEAU_ACL@@@Z; cxl::AclBase::CopyAclTo(_ACL *)
0x18009d22f  mov     [rsp+160h+var_130], r14; pSid
0x18009d234  mov     [rsp+160h+InheritedObjectTypeGuid], r13; InheritedObjectTypeGuid
0x18009d239  mov     [rsp+160h+ObjectTypeGuid], r12; ObjectTypeGuid
0x18009d23e  mov     r9d, [rsp+160h+AccessMask]; AccessMask
0x18009d243  mov     r8d, [rbp+60h+AceFlags]; AceFlags
0x18009d24a  mov     edx, r15d; dwAceRevision
0x18009d24d  mov     rcx, rdi; pAcl
0x18009d250  call    cs:__imp_AddAccessAllowedObjectAce
0x18009d256  test    eax, eax
0x18009d258  jz      short loc_18009D2A1
0x18009d25a  mov     rcx, rdi; struct _ACL *
0x18009d25d  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x18009d262  mov     [rsp+160h+var_110], 0
0x18009d26b  mov     rdx, rdi; struct _ACL *
0x18009d26e  mov     rcx, rsi; this
0x18009d271  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x18009d276  nop
0x18009d277  lea     rcx, [rsp+160h+var_118]
0x18009d27c  call    ?Clear@?$LocalHeapPtr@X@cxl@@QEAAXXZ; cxl::LocalHeapPtr<void>::Clear(void)
0x18009d281  mov     rcx, [rbp+60h+var_50]
0x18009d285  xor     rcx, rsp; StackCookie
0x18009d288  call    __security_check_cookie
0x18009d28d  add     rsp, 128h
0x18009d294  pop     r15
0x18009d296  pop     r14
0x18009d298  pop     r13
0x18009d29a  pop     r12
0x18009d29c  pop     rdi
0x18009d29d  pop     rsi
0x18009d29e  pop     rbx
0x18009d29f  pop     rbp
0x18009d2a0  retn
0x18009d2a1  lea     rcx, [rsp+160h+var_E8]
0x18009d2a6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d2ab  nop
0x18009d2ac  lea     rdx, [rsp+160h+var_E8]
0x18009d2b1  lea     rcx, [rsp+160h+var_108]
0x18009d2b6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d2bb  nop
0x18009d2bc  lea     rdx, aAddaccessallow; "AddAccessAllowedObjectAce failed"
0x18009d2c3  lea     rcx, [rsp+160h+var_108]
0x18009d2c8  call    ??$Write@$0CB@@TextWriter@cxl@@QEAAAEAV01@AEAY0CB@$$CBD@Z; cxl::TextWriter::Write<33>(char const (&)[33])
0x18009d2cd  call    cs:__imp_GetLastError
0x18009d2d3  mov     edx, eax
0x18009d2d5  lea     rcx, [rsp+160h+AccessMask]
0x18009d2da  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d2df  mov     rdx, rax
0x18009d2e2  lea     r8, [rsp+160h+var_E8]
0x18009d2e7  lea     rcx, [rbp+60h+pExceptionObject]
0x18009d2eb  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d2f0  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d2f7  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18009d2fb  call    _CxxThrowException_0
0x18009d301  lea     rcx, [rsp+160h+var_E8]
0x18009d306  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d30b  nop
0x18009d30c  lea     rdx, [rsp+160h+var_E8]
0x18009d311  lea     rcx, [rsp+160h+var_108]
0x18009d316  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d31b  nop
0x18009d31c  lea     rcx, [rsp+160h+var_108]
0x18009d321  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x18009d326  call    cs:__imp_GetLastError
0x18009d32c  mov     edx, eax
0x18009d32e  lea     rcx, [rsp+160h+AccessMask]
0x18009d333  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d338  mov     rdx, rax
0x18009d33b  lea     r8, [rsp+160h+var_E8]
0x18009d340  lea     rcx, [rbp+60h+pExceptionObject]
0x18009d344  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d349  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d350  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18009d354  call    _CxxThrowException_0
```
