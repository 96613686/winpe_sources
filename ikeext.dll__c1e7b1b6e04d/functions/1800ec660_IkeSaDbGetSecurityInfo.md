# IkeSaDbGetSecurityInfo

- ea: `0x1800ec660`
- end: `0x1800ec7bc`
- name: `IkeSaDbGetSecurityInfo`
- size: `348`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, SECURITY_INFORMATION, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006f280`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x1800ec38c`
- `0x1800ec660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec755`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x1800ec6ff`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x1800ec747`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x1800ec6ff`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x1800ec747`

## string_xrefs

- `0x1800ec762`: `GetPrivateObjectSecurity`
- `0x1800ec68a`: `IkeSaDbGetSecurityInfo`
- `0x1800ec787`: `IkeSaDbGetSecurityInfo`
- `0x1800ec793`: `IkeSaDbGetSecurityInfo`

## pseudocode

```c
__int64 __fastcall IkeSaDbGetSecurityInfo(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 a2,
        SECURITY_INFORMATION a3,
        _QWORD *a4)
{
  __int64 v4; // rbx
  PSECURITY_DESCRIPTOR v7; // rsi
  BOOL PrivateObjectSecurity; // r14d
  DWORD LastError; // eax
  __int64 v12; // rcx
  PSECURITY_DESCRIPTOR ResultantDescriptor; // [rsp+30h] [rbp-58h] BYREF
  DWORD DescriptorLength; // [rsp+38h] [rbp-50h] BYREF

  v4 = 0;
  DescriptorLength = 0;
  v7 = 0;
  ResultantDescriptor = 0;
  TraceLogHelper("IkeSaDbGetSecurityInfo", 1);
  if ( (a3 & 7) != 0 )
  {
    v4 = IkeAuthzAccessCheck(pSecurityDescriptor, a2, 0x20000u);
    if ( v4 )
      goto LABEL_12;
  }
  if ( (a3 & 8) != 0 )
  {
    v4 = IkeAuthzAccessCheck(pSecurityDescriptor, a2, 0x1000000u);
    if ( v4 )
      goto LABEL_12;
  }
  PrivateObjectSecurity = GetPrivateObjectSecurity(pSecurityDescriptor, a3, 0, 0, &DescriptorLength);
  if ( GetLastError() == 122 )
  {
    v4 = WfpMemAlloc(DescriptorLength, 0, &ResultantDescriptor);
    if ( v4 )
    {
LABEL_12:
      WfpMemFree((LPCVOID *)&ResultantDescriptor);
      goto LABEL_13;
    }
    v7 = ResultantDescriptor;
    PrivateObjectSecurity = GetPrivateObjectSecurity(
                              pSecurityDescriptor,
                              a3,
                              ResultantDescriptor,
                              DescriptorLength,
                              &DescriptorLength);
  }
  if ( PrivateObjectSecurity )
  {
    *a4 = v7;
  }
  else
  {
    LastError = GetLastError();
    v4 = WfpReportSysErrorAsWinError(v12, "GetPrivateObjectSecurity", LastError, 1);
  }
  if ( v4 )
    goto LABEL_12;
LABEL_13:
  TraceLogHelper("IkeSaDbGetSecurityInfo", 0);
  return IkeReturnError(v4, "IkeSaDbGetSecurityInfo");
}

```

## disassembly

```asm
0x1800ec660  push    rbx
0x1800ec662  push    rbp
0x1800ec663  push    rsi
0x1800ec664  push    rdi
0x1800ec665  push    r14
0x1800ec667  push    r15
0x1800ec669  sub     rsp, 58h
0x1800ec66d  mov     rax, cs:__security_cookie
0x1800ec674  xor     rax, rsp
0x1800ec677  mov     [rsp+88h+var_48], rax
0x1800ec67c  xor     ebx, ebx
0x1800ec67e  mov     r14, rdx
0x1800ec681  mov     rdi, rcx
0x1800ec684  mov     [rsp+88h+DescriptorLength], ebx
0x1800ec688  xor     esi, esi
0x1800ec68a  lea     rcx, aIkesadbgetsecu; "IkeSaDbGetSecurityInfo"
0x1800ec691  mov     r15, r9
0x1800ec694  mov     [rsp+88h+ResultantDescriptor], rsi
0x1800ec699  lea     edx, [rbx+1]
0x1800ec69c  mov     ebp, r8d
0x1800ec69f  call    TraceLogHelper
0x1800ec6a4  test    bpl, 7
0x1800ec6a8  jz      short loc_1800EC6C7
0x1800ec6aa  mov     r8d, 20000h
0x1800ec6b0  mov     rdx, r14
0x1800ec6b3  mov     rcx, rdi; pSecurityDescriptor
0x1800ec6b6  call    IkeAuthzAccessCheck
0x1800ec6bb  mov     rbx, rax
0x1800ec6be  test    rax, rax
0x1800ec6c1  jnz     loc_1800EC77B
0x1800ec6c7  test    bpl, 8
0x1800ec6cb  jz      short loc_1800EC6EA
0x1800ec6cd  mov     r8d, 1000000h
0x1800ec6d3  mov     rdx, r14
0x1800ec6d6  mov     rcx, rdi; pSecurityDescriptor
0x1800ec6d9  call    IkeAuthzAccessCheck
0x1800ec6de  mov     rbx, rax
0x1800ec6e1  test    rax, rax
0x1800ec6e4  jnz     loc_1800EC77B
0x1800ec6ea  lea     rax, [rsp+88h+DescriptorLength]
0x1800ec6ef  xor     r9d, r9d; DescriptorLength
0x1800ec6f2  xor     r8d, r8d; ResultantDescriptor
0x1800ec6f5  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800ec6fa  mov     edx, ebp; SecurityInformation
0x1800ec6fc  mov     rcx, rdi; ObjectDescriptor
0x1800ec6ff  call    cs:__imp_GetPrivateObjectSecurity
0x1800ec705  mov     r14d, eax
0x1800ec708  call    cs:__imp_GetLastError
0x1800ec70e  cmp     eax, 7Ah ; 'z'
0x1800ec711  jnz     short loc_1800EC750
0x1800ec713  mov     ecx, [rsp+88h+DescriptorLength]; dwBytes
0x1800ec717  lea     r8, [rsp+88h+ResultantDescriptor]
0x1800ec71c  xor     edx, edx; dwFlags
0x1800ec71e  call    WfpMemAlloc
0x1800ec723  mov     rbx, rax
0x1800ec726  test    rax, rax
0x1800ec729  jnz     short loc_1800EC77B
0x1800ec72b  mov     rsi, [rsp+88h+ResultantDescriptor]
0x1800ec730  lea     rax, [rsp+88h+DescriptorLength]
0x1800ec735  mov     r9d, [rsp+88h+DescriptorLength]; DescriptorLength
0x1800ec73a  mov     r8, rsi; ResultantDescriptor
0x1800ec73d  mov     edx, ebp; SecurityInformation
0x1800ec73f  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800ec744  mov     rcx, rdi; ObjectDescriptor
0x1800ec747  call    cs:__imp_GetPrivateObjectSecurity
0x1800ec74d  mov     r14d, eax
0x1800ec750  test    r14d, r14d
0x1800ec753  jnz     short loc_1800EC773
0x1800ec755  call    cs:__imp_GetLastError
0x1800ec75b  mov     r8d, eax
0x1800ec75e  lea     r9d, [r14+1]
0x1800ec762  lea     rdx, aGetprivateobje; "GetPrivateObjectSecurity"
0x1800ec769  call    WfpReportSysErrorAsWinError
0x1800ec76e  mov     rbx, rax
0x1800ec771  jmp     short loc_1800EC776
0x1800ec773  mov     [r15], rsi
0x1800ec776  test    rbx, rbx
0x1800ec779  jz      short loc_1800EC785
0x1800ec77b  lea     rcx, [rsp+88h+ResultantDescriptor]
0x1800ec780  call    WfpMemFree
0x1800ec785  xor     edx, edx
0x1800ec787  lea     rcx, aIkesadbgetsecu; "IkeSaDbGetSecurityInfo"
0x1800ec78e  call    TraceLogHelper
0x1800ec793  lea     rdx, aIkesadbgetsecu; "IkeSaDbGetSecurityInfo"
0x1800ec79a  mov     rcx, rbx
0x1800ec79d  call    IkeReturnError
0x1800ec7a2  mov     rcx, [rsp+88h+var_48]
0x1800ec7a7  xor     rcx, rsp; StackCookie
0x1800ec7aa  call    __security_check_cookie
0x1800ec7af  add     rsp, 58h
0x1800ec7b3  pop     r15
0x1800ec7b5  pop     r14
0x1800ec7b7  pop     rdi
0x1800ec7b8  pop     rsi
0x1800ec7b9  pop     rbp
0x1800ec7ba  pop     rbx
0x1800ec7bb  retn
```
