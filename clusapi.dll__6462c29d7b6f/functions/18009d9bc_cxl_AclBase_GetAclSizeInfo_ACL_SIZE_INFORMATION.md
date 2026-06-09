# cxl::AclBase::GetAclSizeInfo(_ACL_SIZE_INFORMATION *)

- ea: `0x18009d9bc`
- end: `0x18009da84`
- name: `?GetAclSizeInfo@AclBase@cxl@@QEBAXPEAU_ACL_SIZE_INFORMATION@@@Z`
- size: `200`
- prototype: `void(cxl::AclBase *__hidden this, struct _ACL_SIZE_INFORMATION *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009d8a8`
- `0x18009da8c`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc08`
- `0x18001d284`
- `0x180027494`
- `0x180091be8`
- `0x180092d1c`
- `0x18009d9bc`
- `0x18009dad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009da4e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18009d9f7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18009d9f7`

## string_xrefs

- `0x18009da3d`: `GetAclInformation failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::AclBase::GetAclSizeInfo(PACL *this, struct _ACL_SIZE_INFORMATION *a2)
{
  DWORD LastError; // eax
  __int64 v5; // rax
  _BYTE v6[8]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v7[32]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v8[40]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  cxl::AclBase::ReportErrorIfEmpty((cxl::AclBase *)this);
  if ( !GetAclInformation(this[2], a2, 0xCu, AclSizeInformation) )
  {
    std::wstring::wstring(v8);
    cxl::StringWriter::StringWriter(v7, v8);
    cxl::TextWriter::Write<25>(v7, "GetAclInformation failed");
    LastError = GetLastError();
    v5 = cxl::WinError(v6, LastError);
    cxl::Exception::Exception(pExceptionObject, v5, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18009d9bc  mov     [rsp+arg_10], rbx
0x18009d9c1  push    rdi
0x18009d9c2  sub     rsp, 0F0h
0x18009d9c9  mov     rax, cs:__security_cookie
0x18009d9d0  xor     rax, rsp
0x18009d9d3  mov     [rsp+0F8h+var_18], rax
0x18009d9db  mov     rdi, rdx
0x18009d9de  mov     rbx, rcx
0x18009d9e1  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18009d9e6  mov     r9d, 2; dwAclInformationClass
0x18009d9ec  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18009d9f0  mov     rdx, rdi; pAclInformation
0x18009d9f3  mov     rcx, [rbx+10h]; pAcl
0x18009d9f7  call    cs:__imp_GetAclInformation
0x18009d9fd  test    eax, eax
0x18009d9ff  jz      short loc_18009DA22
0x18009da01  mov     rcx, [rsp+0F8h+var_18]
0x18009da09  xor     rcx, rsp; StackCookie
0x18009da0c  call    __security_check_cookie
0x18009da11  mov     rbx, [rsp+0F8h+arg_10]
0x18009da19  add     rsp, 0F0h
0x18009da20  pop     rdi
0x18009da21  retn
0x18009da22  lea     rcx, [rsp+0F8h+var_B0]
0x18009da27  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009da2c  nop
0x18009da2d  lea     rdx, [rsp+0F8h+var_B0]
0x18009da32  lea     rcx, [rsp+0F8h+var_D0]
0x18009da37  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009da3c  nop
0x18009da3d  lea     rdx, aGetaclinformat; "GetAclInformation failed"
0x18009da44  lea     rcx, [rsp+0F8h+var_D0]
0x18009da49  call    ??$Write@$0BJ@@TextWriter@cxl@@QEAAAEAV01@AEAY0BJ@$$CBD@Z; cxl::TextWriter::Write<25>(char const (&)[25])
0x18009da4e  call    cs:__imp_GetLastError
0x18009da54  mov     edx, eax
0x18009da56  lea     rcx, [rsp+0F8h+var_D8]
0x18009da5b  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009da60  mov     rdx, rax
0x18009da63  lea     r8, [rsp+0F8h+var_B0]
0x18009da68  lea     rcx, [rsp+0F8h+pExceptionObject]
0x18009da6d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009da72  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009da79  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18009da7e  call    _CxxThrowException_0
```
