# IkeGetUserNameFromToken

- ea: `0x18007f760`
- end: `0x18007f94b`
- name: `IkeGetUserNameFromToken`
- size: `491`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e36c`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x180016730`
- `0x18004aa3c`
- `0x180050850`
- `0x180054730`
- `0x18007f760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f871`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18007f7fb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18007f867`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18007f7fb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18007f867`

## string_xrefs

- `0x18007f791`: `IkeGetUserNameFromToken`
- `0x18007f90c`: `IkeGetUserNameFromToken`
- `0x18007f918`: `IkeGetUserNameFromToken`
- `0x18007f87e`: `LookupAccountSidW`

## pseudocode

```c
__int64 __fastcall IkeGetUserNameFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  __int64 SidFromToken; // rbx
  DWORD LastError; // eax
  __int64 v6; // rcx
  LPCVOID v7; // rdi
  PSID Sid; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+48h] [rbp-38h] BYREF
  LPWSTR Name; // [rsp+50h] [rbp-30h] BYREF
  LPCVOID v12; // [rsp+58h] [rbp-28h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-20h] BYREF
  DWORD cchReferencedDomainName; // [rsp+64h] [rbp-1Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp-18h] BYREF

  SidFromToken = 0;
  peUse = 0;
  Name = 0;
  ReferencedDomainName = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  Sid = 0;
  v12 = 0;
  TraceLogHelper("IkeGetUserNameFromToken", 1);
  if ( TokenHandle )
  {
    SidFromToken = GetSidFromToken(TokenHandle, &Sid);
    if ( !SidFromToken )
    {
      LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
      SidFromToken = WfpMemAlloc(2LL * cchName, 0, &Name);
      if ( !SidFromToken )
      {
        SidFromToken = WfpMemAlloc(2LL * cchReferencedDomainName, 0, &ReferencedDomainName);
        if ( !SidFromToken )
        {
          if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          {
            SidFromToken = WfpMemAlloc(2LL * (cchReferencedDomainName + 2 + cchName), 0, &v12);
            if ( !SidFromToken )
            {
              v7 = v12;
              SidFromToken = WfpStringCchPrintfW(L"%s\\%s");
              if ( !SidFromToken )
                *a2 = v7;
            }
          }
          else
          {
            LastError = GetLastError();
            SidFromToken = WfpReportSysErrorAsWinError(v6, "LookupAccountSidW", LastError, 1);
          }
        }
      }
    }
  }
  WfpMemFree((LPCVOID *)&Sid);
  WfpMemFree((LPCVOID *)&ReferencedDomainName);
  WfpMemFree((LPCVOID *)&Name);
  if ( SidFromToken )
    WfpMemFree(&v12);
  TraceLogHelper("IkeGetUserNameFromToken", 0);
  return IkeReturnError(SidFromToken, "IkeGetUserNameFromToken");
}

```

## disassembly

```asm
0x18007f760  mov     [rsp-18h+arg_10], rbx
0x18007f765  mov     [rsp-18h+arg_18], rsi
0x18007f76a  push    rbp
0x18007f76b  push    rdi
0x18007f76c  push    r14
0x18007f76e  mov     rbp, rsp
0x18007f771  sub     rsp, 80h
0x18007f778  mov     rax, cs:__security_cookie
0x18007f77f  xor     rax, rsp
0x18007f782  mov     [rbp+var_10], rax
0x18007f786  xor     ebx, ebx
0x18007f788  mov     r14, rdx
0x18007f78b  mov     rdi, rcx
0x18007f78e  mov     [rbp+var_18], ebx
0x18007f791  lea     rcx, aIkegetusername; "IkeGetUserNameFromToken"
0x18007f798  mov     [rbp+Name], rbx
0x18007f79c  mov     [rbp+var_38], rbx
0x18007f7a0  lea     edx, [rbx+1]
0x18007f7a3  mov     [rbp+cchName], ebx
0x18007f7a6  mov     [rbp+var_1C], ebx
0x18007f7a9  mov     [rbp+Sid], rbx
0x18007f7ad  mov     [rbp+var_28], rbx
0x18007f7b1  call    TraceLogHelper
0x18007f7b6  test    rdi, rdi
0x18007f7b9  jz      loc_18007F8E1
0x18007f7bf  lea     rdx, [rbp+Sid]
0x18007f7c3  mov     rcx, rdi; TokenHandle
0x18007f7c6  call    GetSidFromToken
0x18007f7cb  mov     rbx, rax
0x18007f7ce  test    rax, rax
0x18007f7d1  jnz     loc_18007F8E1
0x18007f7d7  mov     rdx, [rbp+Sid]; Sid
0x18007f7db  lea     rax, [rbp+var_18]
0x18007f7df  mov     [rsp+80h+peUse], rax; peUse
0x18007f7e4  lea     r9, [rbp+cchName]; cchName
0x18007f7e8  lea     rax, [rbp+var_1C]
0x18007f7ec  xor     r8d, r8d; Name
0x18007f7ef  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18007f7f4  xor     ecx, ecx; lpSystemName
0x18007f7f6  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x18007f7fb  call    cs:__imp_LookupAccountSidW
0x18007f801  mov     ecx, [rbp+cchName]
0x18007f804  lea     r8, [rbp+Name]
0x18007f808  add     rcx, rcx; dwBytes
0x18007f80b  xor     edx, edx; dwFlags
0x18007f80d  call    WfpMemAlloc
0x18007f812  mov     rbx, rax
0x18007f815  test    rax, rax
0x18007f818  jnz     loc_18007F8E1
0x18007f81e  mov     ecx, [rbp+var_1C]
0x18007f821  lea     r8, [rbp+var_38]
0x18007f825  add     rcx, rcx; dwBytes
0x18007f828  xor     edx, edx; dwFlags
0x18007f82a  call    WfpMemAlloc
0x18007f82f  mov     rbx, rax
0x18007f832  test    rax, rax
0x18007f835  jnz     loc_18007F8E1
0x18007f83b  mov     rsi, [rbp+Name]
0x18007f83f  lea     rax, [rbp+var_18]
0x18007f843  mov     rdi, [rbp+var_38]
0x18007f847  lea     r9, [rbp+cchName]; cchName
0x18007f84b  mov     rdx, [rbp+Sid]; Sid
0x18007f84f  mov     r8, rsi; Name
0x18007f852  mov     [rsp+80h+peUse], rax; peUse
0x18007f857  xor     ecx, ecx; lpSystemName
0x18007f859  lea     rax, [rbp+var_1C]
0x18007f85d  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18007f862  mov     [rsp+80h+ReferencedDomainName], rdi; ReferencedDomainName
0x18007f867  call    cs:__imp_LookupAccountSidW
0x18007f86d  test    eax, eax
0x18007f86f  jnz     short loc_18007F88F
0x18007f871  call    cs:__imp_GetLastError
0x18007f877  mov     r8d, eax
0x18007f87a  lea     r9d, [rbx+1]
0x18007f87e  lea     rdx, aLookupaccounts_0; "LookupAccountSidW"
0x18007f885  call    WfpReportSysErrorAsWinError
0x18007f88a  mov     rbx, rax
0x18007f88d  jmp     short loc_18007F8E1
0x18007f88f  mov     ecx, [rbp+cchName]
0x18007f892  lea     r8, [rbp+var_28]
0x18007f896  mov     eax, [rbp+var_1C]
0x18007f899  xor     edx, edx; dwFlags
0x18007f89b  add     eax, 2
0x18007f89e  add     ecx, eax
0x18007f8a0  add     rcx, rcx; dwBytes
0x18007f8a3  call    WfpMemAlloc
0x18007f8a8  mov     rbx, rax
0x18007f8ab  test    rax, rax
0x18007f8ae  jnz     short loc_18007F8E1
0x18007f8b0  mov     eax, [rbp+var_1C]
0x18007f8b3  lea     rcx, aSS; "%s\\%s"
0x18007f8ba  mov     edx, [rbp+cchName]
0x18007f8bd  mov     r9, rdi
0x18007f8c0  mov     rdi, [rbp+var_28]
0x18007f8c4  add     eax, 2
0x18007f8c7  add     edx, eax
0x18007f8c9  mov     [rsp+80h+ReferencedDomainName], rsi
0x18007f8ce  mov     r8, rdi
0x18007f8d1  call    WfpStringCchPrintfW
0x18007f8d6  mov     rbx, rax
0x18007f8d9  test    rax, rax
0x18007f8dc  jnz     short loc_18007F8E1
0x18007f8de  mov     [r14], rdi
0x18007f8e1  lea     rcx, [rbp+Sid]
0x18007f8e5  call    WfpMemFree
0x18007f8ea  lea     rcx, [rbp+var_38]
0x18007f8ee  call    WfpMemFree
0x18007f8f3  lea     rcx, [rbp+Name]
0x18007f8f7  call    WfpMemFree
0x18007f8fc  test    rbx, rbx
0x18007f8ff  jz      short loc_18007F90A
0x18007f901  lea     rcx, [rbp+var_28]
0x18007f905  call    WfpMemFree
0x18007f90a  xor     edx, edx
0x18007f90c  lea     rcx, aIkegetusername; "IkeGetUserNameFromToken"
0x18007f913  call    TraceLogHelper
0x18007f918  lea     rdx, aIkegetusername; "IkeGetUserNameFromToken"
0x18007f91f  mov     rcx, rbx
0x18007f922  call    IkeReturnError
0x18007f927  mov     rcx, [rbp+var_10]
0x18007f92b  xor     rcx, rsp; StackCookie
0x18007f92e  call    __security_check_cookie
0x18007f933  lea     r11, [rsp+80h+var_s0]
0x18007f93b  mov     rbx, [r11+30h]
0x18007f93f  mov     rsi, [r11+38h]
0x18007f943  mov     rsp, r11
0x18007f946  pop     r14
0x18007f948  pop     rdi
0x18007f949  pop     rbp
0x18007f94a  retn
```
