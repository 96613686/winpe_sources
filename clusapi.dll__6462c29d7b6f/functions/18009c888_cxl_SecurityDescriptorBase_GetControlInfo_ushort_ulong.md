# cxl::SecurityDescriptorBase::GetControlInfo(ushort *,ulong *)

- ea: `0x18009c888`
- end: `0x18009c959`
- name: `?GetControlInfo@SecurityDescriptorBase@cxl@@QEBAXPEAGPEAK@Z`
- size: `209`
- prototype: `void(cxl::SecurityDescriptorBase *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a812c`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cc08`
- `0x18001d284`
- `0x180027494`
- `0x180091dec`
- `0x180092d1c`
- `0x18009c888`
- `0x18009cd90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c923`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18009c8c7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18009c8c7`

## string_xrefs

- `0x18009c912`: `GetSecurityDescriptorControl failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::SecurityDescriptorBase::GetControlInfo(
        PSECURITY_DESCRIPTOR *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  DWORD LastError; // eax
  __int64 v7; // rax
  DWORD dwRevision; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v9[12]; // [rsp+24h] [rbp-E4h] BYREF
  _BYTE v10[32]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v11[32]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-98h] BYREF

  cxl::SecurityDescriptorBase::ReportErrorIfEmpty((cxl::SecurityDescriptorBase *)this);
  dwRevision = 0;
  if ( !GetSecurityDescriptorControl(this[2], a2, &dwRevision) )
  {
    std::wstring::wstring(v11);
    cxl::StringWriter::StringWriter(v10, v11);
    cxl::TextWriter::Write<36>(v10, "GetSecurityDescriptorControl failed");
    LastError = GetLastError();
    v7 = cxl::WinError(v9, LastError);
    cxl::Exception::Exception(pExceptionObject, v7, v11);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( a3 )
    *a3 = dwRevision;
}

```

## disassembly

```asm
0x18009c888  push    rbx
0x18009c88a  push    rsi
0x18009c88b  push    rdi
0x18009c88c  sub     rsp, 0F0h
0x18009c893  mov     rax, cs:__security_cookie
0x18009c89a  xor     rax, rsp
0x18009c89d  mov     [rsp+108h+var_28], rax
0x18009c8a5  mov     rsi, r8
0x18009c8a8  mov     rdi, rdx
0x18009c8ab  mov     rbx, rcx
0x18009c8ae  call    ?ReportErrorIfEmpty@SecurityDescriptorBase@cxl@@IEBAXXZ; cxl::SecurityDescriptorBase::ReportErrorIfEmpty(void)
0x18009c8b3  mov     [rsp+108h+dwRevision], 0
0x18009c8bb  lea     r8, [rsp+108h+dwRevision]; lpdwRevision
0x18009c8c0  mov     rdx, rdi; pControl
0x18009c8c3  mov     rcx, [rbx+10h]; pSecurityDescriptor
0x18009c8c7  call    cs:__imp_GetSecurityDescriptorControl
0x18009c8cd  test    eax, eax
0x18009c8cf  jz      short loc_18009C8F7
0x18009c8d1  test    rsi, rsi
0x18009c8d4  jz      short loc_18009C8DC
0x18009c8d6  mov     eax, [rsp+108h+dwRevision]
0x18009c8da  mov     [rsi], eax
0x18009c8dc  mov     rcx, [rsp+108h+var_28]
0x18009c8e4  xor     rcx, rsp; StackCookie
0x18009c8e7  call    __security_check_cookie
0x18009c8ec  add     rsp, 0F0h
0x18009c8f3  pop     rdi
0x18009c8f4  pop     rsi
0x18009c8f5  pop     rbx
0x18009c8f6  retn
0x18009c8f7  lea     rcx, [rsp+108h+var_B8]
0x18009c8fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009c901  nop
0x18009c902  lea     rdx, [rsp+108h+var_B8]
0x18009c907  lea     rcx, [rsp+108h+var_D8]
0x18009c90c  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18009c911  nop
0x18009c912  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorControl failed"
0x18009c919  lea     rcx, [rsp+108h+var_D8]
0x18009c91e  call    ??$Write@$0CE@@TextWriter@cxl@@QEAAAEAV01@AEAY0CE@$$CBD@Z; cxl::TextWriter::Write<36>(char const (&)[36])
0x18009c923  call    cs:__imp_GetLastError
0x18009c929  mov     edx, eax
0x18009c92b  lea     rcx, [rsp+108h+var_E4]
0x18009c930  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18009c935  mov     rdx, rax
0x18009c938  lea     r8, [rsp+108h+var_B8]
0x18009c93d  lea     rcx, [rsp+108h+pExceptionObject]
0x18009c942  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009c947  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009c94e  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18009c953  call    _CxxThrowException_0
```
