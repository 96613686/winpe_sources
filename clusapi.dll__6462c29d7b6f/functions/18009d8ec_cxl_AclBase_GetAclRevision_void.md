# cxl::AclBase::GetAclRevision(void)

- ea: `0x18009d8ec`
- end: `0x18009d9b3`
- name: `?GetAclRevision@AclBase@cxl@@QEBAKXZ`
- size: `199`
- prototype: `unsigned int __fastcall(cxl::AclBase *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009cfe0`
- `0x18009d190`
- `0x18009d360`
- `0x18009d510`
- `0x18009d6dc`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc08`
- `0x18001d284`
- `0x180027494`
- `0x180091be8`
- `0x180092d1c`
- `0x18009d8ec`
- `0x18009dad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d97d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d97d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18009d92a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18009d92a`

## string_xrefs

- `0x18009d96c`: `GetAclInformation failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall cxl::AclBase::GetAclRevision(PACL *this)
{
  DWORD LastError; // eax
  __int64 v4; // rax
  unsigned int pAclInformation; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v6[12]; // [rsp+24h] [rbp-D4h] BYREF
  _BYTE v7[32]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v8[32]; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  pAclInformation = 0;
  cxl::AclBase::ReportErrorIfEmpty((cxl::AclBase *)this);
  if ( !GetAclInformation(this[2], &pAclInformation, 4u, AclRevisionInformation) )
  {
    std::wstring::wstring(v8);
    cxl::StringWriter::StringWriter(v7, v8);
    cxl::TextWriter::Write<25>(v7, "GetAclInformation failed");
    LastError = GetLastError();
    v4 = cxl::WinError(v6, LastError);
    cxl::Exception::Exception(pExceptionObject, v4, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
  return pAclInformation;
}

```

## disassembly

```asm
0x18009d8ec  push    rbx
0x18009d8ee  sub     rsp, 0F0h
0x18009d8f5  mov     rax, cs:__security_cookie
0x18009d8fc  xor     rax, rsp
0x18009d8ff  mov     [rsp+0F8h+var_18], rax
0x18009d907  mov     rbx, rcx
0x18009d90a  mov     [rsp+0F8h+pAclInformation], 0
0x18009d912  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x18009d917  mov     r9d, 1; dwAclInformationClass
0x18009d91d  lea     r8d, [r9+3]; nAclInformationLength
0x18009d921  lea     rdx, [rsp+0F8h+pAclInformation]; pAclInformation
0x18009d926  mov     rcx, [rbx+10h]; pAcl
0x18009d92a  call    cs:__imp_GetAclInformation
0x18009d930  test    eax, eax
0x18009d932  jz      short loc_18009D951
0x18009d934  mov     eax, [rsp+0F8h+pAclInformation]
0x18009d938  mov     rcx, [rsp+0F8h+var_18]
0x18009d940  xor     rcx, rsp; StackCookie
0x18009d943  call    __security_check_cookie
0x18009d948  add     rsp, 0F0h
0x18009d94f  pop     rbx
0x18009d950  retn
0x18009d951  lea     rcx, [rsp+0F8h+var_A8]
0x18009d956  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009d95b  nop
0x18009d95c  lea     rdx, [rsp+0F8h+var_A8]
0x18009d961  lea     rcx, [rsp+0F8h+var_C8]
0x18009d966  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009d96b  nop
0x18009d96c  lea     rdx, aGetaclinformat; "GetAclInformation failed"
0x18009d973  lea     rcx, [rsp+0F8h+var_C8]
0x18009d978  call    ??$Write@$0BJ@@TextWriter@cxl@@QEAAAEAV01@AEAY0BJ@$$CBD@Z; cxl::TextWriter::Write<25>(char const (&)[25])
0x18009d97d  call    cs:__imp_GetLastError
0x18009d983  mov     edx, eax
0x18009d985  lea     rcx, [rsp+0F8h+var_D4]
0x18009d98a  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009d98f  mov     rdx, rax
0x18009d992  lea     r8, [rsp+0F8h+var_A8]
0x18009d997  lea     rcx, [rsp+0F8h+pExceptionObject]
0x18009d99c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009d9a1  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009d9a8  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18009d9ad  call    _CxxThrowException_0
```
