# cxl::SecurityDescriptor::SetDacl(_ACL *,bool)

- ea: `0x18009ce28`
- end: `0x18009ceed`
- name: `?SetDacl@SecurityDescriptor@cxl@@QEAAXPEAU_ACL@@_N@Z`
- size: `197`
- prototype: `void(cxl::SecurityDescriptor *__hidden this, struct _ACL *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3a0c`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc08`
- `0x18001d284`
- `0x180027494`
- `0x180091d60`
- `0x180092d1c`
- `0x18009cd90`
- `0x18009ce28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ceb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ceb7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009ce60`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009ce60`

## string_xrefs

- `0x18009cea6`: `SetSecurityDescriptorDacl failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::SecurityDescriptor::SetDacl(PSECURITY_DESCRIPTOR *this, struct _ACL *a2)
{
  DWORD LastError; // eax
  __int64 v5; // rax
  _BYTE v6[8]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v7[32]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v8[40]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  cxl::SecurityDescriptorBase::ReportErrorIfEmpty((cxl::SecurityDescriptorBase *)this);
  if ( !SetSecurityDescriptorDacl(this[2], 1, a2, 0) )
  {
    std::wstring::wstring(v8);
    cxl::StringWriter::StringWriter(v7, v8);
    cxl::TextWriter::Write<33>(v7, "SetSecurityDescriptorDacl failed");
    LastError = GetLastError();
    v5 = cxl::WinError(v6, LastError);
    cxl::Exception::Exception(pExceptionObject, v5, v8);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18009ce28  mov     [rsp+arg_10], rbx
0x18009ce2d  push    rdi
0x18009ce2e  sub     rsp, 0F0h
0x18009ce35  mov     rax, cs:__security_cookie
0x18009ce3c  xor     rax, rsp
0x18009ce3f  mov     [rsp+0F8h+var_18], rax
0x18009ce47  mov     rbx, rdx
0x18009ce4a  mov     rdi, rcx
0x18009ce4d  call    ?ReportErrorIfEmpty@SecurityDescriptorBase@cxl@@IEBAXXZ; cxl::SecurityDescriptorBase::ReportErrorIfEmpty(void)
0x18009ce52  xor     r9d, r9d; bDaclDefaulted
0x18009ce55  mov     r8, rbx; pDacl
0x18009ce58  lea     edx, [r9+1]; bDaclPresent
0x18009ce5c  mov     rcx, [rdi+10h]; pSecurityDescriptor
0x18009ce60  call    cs:__imp_SetSecurityDescriptorDacl
0x18009ce66  test    eax, eax
0x18009ce68  jz      short loc_18009CE8B
0x18009ce6a  mov     rcx, [rsp+0F8h+var_18]
0x18009ce72  xor     rcx, rsp; StackCookie
0x18009ce75  call    __security_check_cookie
0x18009ce7a  mov     rbx, [rsp+0F8h+arg_10]
0x18009ce82  add     rsp, 0F0h
0x18009ce89  pop     rdi
0x18009ce8a  retn
0x18009ce8b  lea     rcx, [rsp+0F8h+var_B0]
0x18009ce90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009ce95  nop
0x18009ce96  lea     rdx, [rsp+0F8h+var_B0]
0x18009ce9b  lea     rcx, [rsp+0F8h+var_D0]
0x18009cea0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009cea5  nop
0x18009cea6  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorDacl failed"
0x18009cead  lea     rcx, [rsp+0F8h+var_D0]
0x18009ceb2  call    ??$Write@$0CB@@TextWriter@cxl@@QEAAAEAV01@AEAY0CB@$$CBD@Z; cxl::TextWriter::Write<33>(char const (&)[33])
0x18009ceb7  call    cs:__imp_GetLastError
0x18009cebd  mov     edx, eax
0x18009cebf  lea     rcx, [rsp+0F8h+var_D8]
0x18009cec4  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009cec9  mov     rdx, rax
0x18009cecc  lea     r8, [rsp+0F8h+var_B0]
0x18009ced1  lea     rcx, [rsp+0F8h+pExceptionObject]
0x18009ced6  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009cedb  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009cee2  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18009cee7  call    _CxxThrowException_0
```
