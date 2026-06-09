# cxl::Acl::AddAccessAllowedAce(ulong,_SID const *,ulong)

- ea: `0x18009cfe0`
- end: `0x18009d18a`
- name: `?AddAccessAllowedAce@Acl@cxl@@QEAAXKPEBU_SID@@K@Z`
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
- `0x180091ca0`
- `0x180092d1c`
- `0x18009c728`
- `0x18009c784`
- `0x18009c85c`
- `0x18009cfe0`
- `0x18009d6dc`
- `0x18009d8ec`
- `0x18009da8c`
- `0x18009dad0`
- `0x18009db28`
- `0x18009dbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d156`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d058`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009d058`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d036`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d036`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18009d082`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18009d082`

## string_xrefs

- `0x18009d0ec`: `AddAccessAllowedAceEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cxl::Acl::AddAccessAllowedAce(cxl::Acl *this, DWORD AccessMask, struct _SID *a3)
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
  cxl::AclBase::CopyAclTo(this, v10);
  if ( !AddAccessAllowedAceEx(v10, AclRevision, 0, AccessMask, a3) )
  {
    std::wstring::wstring(v19);
    cxl::StringWriter::StringWriter(v18, v19);
    cxl::TextWriter::Write<29>(v18, "AddAccessAllowedAceEx failed");
    v11 = GetLastError();
    v12 = cxl::WinError(v15, v11);
    cxl::Exception::Exception(pExceptionObject, v12, v19);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::AclBase::VerifyAcl(v10);
  v17 = 0;
  cxl::Acl::Attach(this, v10);
  cxl::LocalHeapPtr<void>::Clear(v16);
}

```

## disassembly

```asm
0x18009cfe0  push    rbp
0x18009cfe2  push    rbx
0x18009cfe3  push    rsi
0x18009cfe4  push    rdi
0x18009cfe5  push    r12
0x18009cfe7  push    r14
0x18009cfe9  push    r15
0x18009cfeb  lea     rbp, [rsp-10h]
0x18009cff0  sub     rsp, 110h
0x18009cff7  mov     rax, cs:__security_cookie
0x18009cffe  xor     rax, rsp
0x18009d001  mov     [rbp+40h+var_40], rax
0x18009d005  mov     r14, r8
0x18009d008  mov     r12d, edx
0x18009d00b  mov     rsi, rcx
0x18009d00e  mov     rcx, r8; struct _SID *
0x18009d011  call    ?VerifySid@SidBase@cxl@@SAXPEBU_SID@@@Z; cxl::SidBase::VerifySid(_SID const *)
0x18009d016  mov     rcx, rsi; this
0x18009d019  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18009d01e  mov     rcx, rsi; this
0x18009d021  call    ?GetAclRevision@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclRevision(void)
0x18009d026  mov     r15d, eax
0x18009d029  mov     rcx, rsi; this
0x18009d02c  call    ?GetAclUsedBytes@AclBase@cxl@@QEBAKXZ; cxl::AclBase::GetAclUsedBytes(void)
0x18009d031  mov     ebx, eax
0x18009d033  mov     rcx, r14; pSid
0x18009d036  call    cs:__imp_GetLengthSid
0x18009d03c  add     eax, 10h
0x18009d03f  add     ebx, eax
0x18009d041  mov     ecx, ebx; uBytes
0x18009d043  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x18009d048  mov     rdi, rax
0x18009d04b  mov     [rsp+140h+var_100], rax
0x18009d050  mov     r8d, r15d; dwAclRevision
0x18009d053  mov     edx, ebx; nAclLength
0x18009d055  mov     rcx, rax; pAcl
0x18009d058  call    cs:__imp_InitializeAcl
0x18009d05e  test    eax, eax
0x18009d060  jz      loc_18009D131
0x18009d066  mov     rdx, rdi; pAcl
0x18009d069  mov     rcx, rsi; this
0x18009d06c  call    ?CopyAclTo@AclBase@cxl@@QEAAXPEAU_ACL@@@Z; cxl::AclBase::CopyAclTo(_ACL *)
0x18009d071  mov     [rsp+140h+pSid], r14; pSid
0x18009d076  mov     r9d, r12d; AccessMask
0x18009d079  xor     r8d, r8d; AceFlags
0x18009d07c  mov     edx, r15d; dwAceRevision
0x18009d07f  mov     rcx, rdi; pAcl
0x18009d082  call    cs:__imp_AddAccessAllowedAceEx
0x18009d088  test    eax, eax
0x18009d08a  jz      short loc_18009D0D1
0x18009d08c  mov     rcx, rdi; struct _ACL *
0x18009d08f  call    ?VerifyAcl@AclBase@cxl@@KAXPEBU_ACL@@@Z; cxl::AclBase::VerifyAcl(_ACL const *)
0x18009d094  mov     [rsp+140h+var_100], 0
0x18009d09d  mov     rdx, rdi; struct _ACL *
0x18009d0a0  mov     rcx, rsi; this
0x18009d0a3  call    ?Attach@Acl@cxl@@QEAAXPEAU_ACL@@@Z; cxl::Acl::Attach(_ACL *)
0x18009d0a8  nop
0x18009d0a9  lea     rcx, [rsp+140h+var_108]
0x18009d0ae  call    ?Clear@?$LocalHeapPtr@X@cxl@@QEAAXXZ; cxl::LocalHeapPtr<void>::Clear(void)
0x18009d0b3  mov     rcx, [rbp+40h+var_40]
0x18009d0b7  xor     rcx, rsp; StackCookie
0x18009d0ba  call    __security_check_cookie
0x18009d0bf  add     rsp, 110h
0x18009d0c6  pop     r15
0x18009d0c8  pop     r14
0x18009d0ca  pop     r12
0x18009d0cc  pop     rdi
0x18009d0cd  pop     rsi
0x18009d0ce  pop     rbx
0x18009d0cf  pop     rbp
0x18009d0d0  retn
0x18009d0d1  lea     rcx, [rsp+140h+var_D8]
0x18009d0d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d0db  nop
0x18009d0dc  lea     rdx, [rsp+140h+var_D8]
0x18009d0e1  lea     rcx, [rsp+140h+var_F8]
0x18009d0e6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d0eb  nop
0x18009d0ec  lea     rdx, aAddaccessallow_0; "AddAccessAllowedAceEx failed"
0x18009d0f3  lea     rcx, [rsp+140h+var_F8]
0x18009d0f8  call    ??$Write@$0BN@@TextWriter@cxl@@QEAAAEAV01@AEAY0BN@$$CBD@Z; cxl::TextWriter::Write<29>(char const (&)[29])
0x18009d0fd  call    cs:__imp_GetLastError
0x18009d103  mov     edx, eax
0x18009d105  lea     rcx, [rsp+140h+var_110]
0x18009d10a  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d10f  mov     rdx, rax
0x18009d112  lea     r8, [rsp+140h+var_D8]
0x18009d117  lea     rcx, [rbp+40h+pExceptionObject]
0x18009d11b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d120  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d127  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18009d12b  call    _CxxThrowException_0
0x18009d131  lea     rcx, [rsp+140h+var_D8]
0x18009d136  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d13b  nop
0x18009d13c  lea     rdx, [rsp+140h+var_D8]
0x18009d141  lea     rcx, [rsp+140h+var_F8]
0x18009d146  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d14b  nop
0x18009d14c  lea     rcx, [rsp+140h+var_F8]
0x18009d151  call    ??$Write@$0BF@@TextWriter@cxl@@QEAAAEAV01@AEAY0BF@$$CBD@Z; cxl::TextWriter::Write<21>(char const (&)[21])
0x18009d156  call    cs:__imp_GetLastError
0x18009d15c  mov     edx, eax
0x18009d15e  lea     rcx, [rsp+140h+var_110]
0x18009d163  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d168  mov     rdx, rax
0x18009d16b  lea     r8, [rsp+140h+var_D8]
0x18009d170  lea     rcx, [rbp+40h+pExceptionObject]
0x18009d174  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d179  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d180  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18009d184  call    _CxxThrowException_0
```
