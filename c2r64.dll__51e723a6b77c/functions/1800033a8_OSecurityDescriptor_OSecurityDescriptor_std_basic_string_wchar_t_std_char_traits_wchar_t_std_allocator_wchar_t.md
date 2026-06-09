# OSecurityDescriptor::OSecurityDescriptor(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800033a8`
- end: `0x180003473`
- name: `??0OSecurityDescriptor@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000386c`

## callees

- `0x1800033a8`
- `0x18000c5f8`
- `0x18003e690`
- `0x1800409e0`
- `0x180133e70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003430`
- `KERNEL32!GetLastError` at `0x18000343a`
- `KERNEL32!GetLastError` at `0x180003430`
- `KERNEL32!GetLastError` at `0x18000343a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800033f9`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800033f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSECURITY_DESCRIPTOR *__fastcall OSecurityDescriptor::OSecurityDescriptor(
        PSECURITY_DESCRIPTOR *SecurityDescriptor,
        __int64 a2)
{
  PSECURITY_DESCRIPTOR *v3; // rdi
  const WCHAR *v4; // rcx
  DWORD v6; // eax
  __int64 v7; // r8
  int v8; // [rsp+20h] [rbp-3D8h]
  DWORD LastError; // [rsp+40h] [rbp-3B8h] BYREF
  PSECURITY_DESCRIPTOR *v10; // [rsp+48h] [rbp-3B0h]
  _BYTE pExceptionObject[912]; // [rsp+50h] [rbp-3A8h] BYREF

  v10 = SecurityDescriptor;
  v3 = SecurityDescriptor + 1;
  std::wstring::wstring(SecurityDescriptor + 1, a2);
  if ( SecurityDescriptor[3] )
  {
    v4 = (const WCHAR *)v3;
    if ( (unsigned __int64)v3[3] > 7 )
      v4 = (const WCHAR *)*v3;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      v6 = GetLastError();
      OException::OException((__int64)pExceptionObject, 808464432, v7, v6, v8, (__int64)v3, (__int64)&LastError);
      throw (OException *)pExceptionObject;
    }
  }
  else
  {
    *SecurityDescriptor = 0;
  }
  return SecurityDescriptor;
}

```

## disassembly

```asm
0x1800033a8  mov     [rsp+arg_10], rbx
0x1800033ad  push    rdi
0x1800033ae  sub     rsp, 3F0h
0x1800033b5  mov     rax, cs:__security_cookie
0x1800033bc  xor     rax, rsp
0x1800033bf  mov     [rsp+3F8h+var_18], rax
0x1800033c7  mov     rbx, rcx
0x1800033ca  mov     [rsp+3F8h+var_3B0], rcx
0x1800033cf  lea     rdi, [rcx+8]
0x1800033d3  mov     rcx, rdi
0x1800033d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800033db  cmp     qword ptr [rbx+18h], 0
0x1800033e0  jz      short loc_180003427
0x1800033e2  mov     rcx, rdi
0x1800033e5  cmp     qword ptr [rdi+18h], 7
0x1800033ea  jbe     short loc_1800033EF
0x1800033ec  mov     rcx, [rdi]; StringSecurityDescriptor
0x1800033ef  xor     r9d, r9d; SecurityDescriptorSize
0x1800033f2  mov     r8, rbx; SecurityDescriptor
0x1800033f5  lea     edx, [r9+1]; StringSDRevision
0x1800033f9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800033ff  test    eax, eax
0x180003401  jz      short loc_180003430
0x180003403  mov     rax, rbx
0x180003406  mov     rcx, [rsp+3F8h+var_18]
0x18000340e  xor     rcx, rsp; StackCookie
0x180003411  call    __security_check_cookie
0x180003416  mov     rbx, [rsp+3F8h+arg_10]
0x18000341e  add     rsp, 3F0h
0x180003425  pop     rdi
0x180003426  retn
0x180003427  mov     qword ptr [rbx], 0
0x18000342e  jmp     short loc_180003403
0x180003430  call    cs:__imp_GetLastError
0x180003436  mov     [rsp+3F8h+var_3B8], eax
0x18000343a  call    cs:__imp_GetLastError
0x180003440  lea     rcx, [rsp+3F8h+var_3B8]
0x180003445  mov     [rsp+3F8h+var_3C8], rcx
0x18000344a  mov     [rsp+3F8h+var_3D0], rdi
0x18000344f  mov     r9d, eax
0x180003452  mov     edx, 30303030h
0x180003457  lea     rcx, [rsp+3F8h+pExceptionObject]
0x18000345c  call    ??$?0$0EA@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@OException@@QEAA@Utag_t@0@W4exceptionType@et@@IAEAY0EA@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; OException::OException(OException::tag_t,et::exceptionType,uint,wchar_t const (&)[64],std::wstring const &,ulong const &)
0x180003461  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180003468  lea     rcx, [rsp+3F8h+pExceptionObject]; pExceptionObject
0x18000346d  call    _CxxThrowException
```
