# GetLocalizedBUILTIN(ushort * *)

- ea: `0x180038078`
- end: `0x180038214`
- name: `?GetLocalizedBUILTIN@@YAJPEAPEAG@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037880`
- `0x180037d30`

## callees

- `0x180038078`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381e7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800381a3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800381a3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180038127`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180038127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800380c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800380c8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003815c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180038194`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003815c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180038194`

## pseudocode

```c
signed int __fastcall GetLocalizedBUILTIN(unsigned __int16 **a1)
{
  signed int result; // eax
  _WORD *v3; // rax
  void *v4; // rbx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+64h] [rbp-9Ch] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-90h] BYREF
  enum _SID_NAME_USE v9; // [rsp+74h] [rbp-8Ch] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[280]; // [rsp+80h] [rbp-80h] BYREF

  if ( g_pwzBUILTIN )
  {
    *a1 = g_pwzBUILTIN;
    return 0;
  }
  *a1 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  v3 = CoTaskMemAlloc(0x20u);
  v4 = v3;
  if ( !v3 )
    return -2147024882;
  *v3 = 0;
  v9 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x20u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    peUse = 0;
    LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
    if ( cchName - 1 > 0x110 )
    {
      CoTaskMemFree(v4);
      return -2147418113;
    }
    if ( LookupAccountSidLocalW(Sid, Name, &cchName, (LPWSTR)v4, &cchReferencedDomainName, &v9) )
    {
      FreeSid(Sid);
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pwzBUILTIN, (signed __int64)v4, 0) )
        CoTaskMemFree(v4);
      *a1 = g_pwzBUILTIN;
      return 0;
    }
  }
  CoTaskMemFree(v4);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180038078  push    rbp
0x18003807a  push    rbx
0x18003807b  push    rsi
0x18003807c  push    rdi
0x18003807d  lea     rbp, [rsp-1C8h]
0x180038085  sub     rsp, 2C8h
0x18003808c  mov     rax, cs:__security_cookie
0x180038093  xor     rax, rsp
0x180038096  mov     [rbp+1E0h+var_30], rax
0x18003809d  mov     rax, cs:?g_pwzBUILTIN@@3PEAGEA; ushort * g_pwzBUILTIN
0x1800380a4  xor     esi, esi
0x1800380a6  mov     rdi, rcx
0x1800380a9  test    rax, rax
0x1800380ac  jz      short loc_1800380B8
0x1800380ae  mov     [rcx], rax
0x1800380b1  xor     eax, eax
0x1800380b3  jmp     loc_1800381F9
0x1800380b8  mov     [rcx], rsi
0x1800380bb  mov     ecx, 20h ; ' '; cb
0x1800380c0  mov     [rsp+2E0h+cchName], esi
0x1800380c4  mov     [rsp+2E0h+cchReferencedDomainName], esi
0x1800380c8  call    cs:__imp_CoTaskMemAlloc
0x1800380ce  mov     rbx, rax
0x1800380d1  test    rax, rax
0x1800380d4  jnz     short loc_1800380E0
0x1800380d6  mov     eax, 8007000Eh
0x1800380db  jmp     loc_1800381F9
0x1800380e0  mov     [rax], si
0x1800380e3  lea     rcx, [rsp+2E0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800380e8  lea     rax, [rsp+2E0h+Sid]
0x1800380ed  mov     [rsp+2E0h+var_26C], esi
0x1800380f1  mov     [rsp+2E0h+pSid], rax; pSid
0x1800380f6  xor     r9d, r9d; nSubAuthority1
0x1800380f9  mov     [rsp+2E0h+nSubAuthority7], esi; nSubAuthority7
0x1800380fd  mov     dl, 1; nSubAuthorityCount
0x1800380ff  mov     [rsp+2E0h+nSubAuthority6], esi; nSubAuthority6
0x180038103  mov     [rsp+2E0h+nSubAuthority5], esi; nSubAuthority5
0x180038107  mov     [rsp+2E0h+nSubAuthority4], esi; nSubAuthority4
0x18003810b  lea     r8d, [r9+20h]; nSubAuthority0
0x18003810f  mov     [rsp+2E0h+nSubAuthority3], esi; nSubAuthority3
0x180038113  mov     [rsp+2E0h+nSubAuthority2], esi; nSubAuthority2
0x180038117  mov     dword ptr [rsp+2E0h+pIdentifierAuthority.Value], esi
0x18003811b  mov     word ptr [rsp+2E0h+pIdentifierAuthority.Value+4], 500h
0x180038122  mov     [rsp+2E0h+Sid], rsi
0x180038127  call    cs:__imp_AllocateAndInitializeSid
0x18003812d  test    eax, eax
0x18003812f  jz      loc_1800381DE
0x180038135  mov     rcx, [rsp+2E0h+Sid]; Sid
0x18003813a  lea     rax, [rsp+2E0h+peUse]
0x18003813f  mov     qword ptr [rsp+2E0h+nSubAuthority3], rax; peUse
0x180038144  lea     r8, [rsp+2E0h+cchName]; cchName
0x180038149  lea     rax, [rsp+2E0h+cchReferencedDomainName]
0x18003814e  mov     [rsp+2E0h+peUse], esi
0x180038152  xor     r9d, r9d; ReferencedDomainName
0x180038155  mov     qword ptr [rsp+2E0h+nSubAuthority2], rax; cchReferencedDomainName
0x18003815a  xor     edx, edx; Name
0x18003815c  call    cs:__imp_LookupAccountSidLocalW
0x180038162  mov     eax, [rsp+2E0h+cchName]
0x180038166  dec     eax
0x180038168  cmp     eax, 110h
0x18003816d  ja      short loc_1800381CE
0x18003816f  mov     rcx, [rsp+2E0h+Sid]; Sid
0x180038174  lea     rax, [rsp+2E0h+var_26C]
0x180038179  mov     qword ptr [rsp+2E0h+nSubAuthority3], rax; peUse
0x18003817e  lea     r8, [rsp+2E0h+cchName]; cchName
0x180038183  lea     rax, [rsp+2E0h+cchReferencedDomainName]
0x180038188  mov     r9, rbx; ReferencedDomainName
0x18003818b  lea     rdx, [rbp+1E0h+Name]; Name
0x18003818f  mov     qword ptr [rsp+2E0h+nSubAuthority2], rax; cchReferencedDomainName
0x180038194  call    cs:__imp_LookupAccountSidLocalW
0x18003819a  test    eax, eax
0x18003819c  jz      short loc_1800381DE
0x18003819e  mov     rcx, [rsp+2E0h+Sid]; pSid
0x1800381a3  call    cs:__imp_FreeSid
0x1800381a9  xor     eax, eax
0x1800381ab  lock cmpxchg cs:?g_pwzBUILTIN@@3PEAGEA, rbx; ushort * g_pwzBUILTIN
0x1800381b4  jz      short loc_1800381BF
0x1800381b6  mov     rcx, rbx; pv
0x1800381b9  call    cs:__imp_CoTaskMemFree
0x1800381bf  mov     rax, cs:?g_pwzBUILTIN@@3PEAGEA; ushort * g_pwzBUILTIN
0x1800381c6  mov     [rdi], rax
0x1800381c9  jmp     loc_1800380B1
0x1800381ce  mov     rcx, rbx; pv
0x1800381d1  call    cs:__imp_CoTaskMemFree
0x1800381d7  mov     eax, 8000FFFFh
0x1800381dc  jmp     short loc_1800381F9
0x1800381de  mov     rcx, rbx; pv
0x1800381e1  call    cs:__imp_CoTaskMemFree
0x1800381e7  call    cs:__imp_GetLastError
0x1800381ed  test    eax, eax
0x1800381ef  jle     short loc_1800381F9
0x1800381f1  movzx   eax, ax
0x1800381f4  or      eax, 80070000h
0x1800381f9  mov     rcx, [rbp+1E0h+var_30]
0x180038200  xor     rcx, rsp; StackCookie
0x180038203  call    __security_check_cookie
0x180038208  add     rsp, 2C8h
0x18003820f  pop     rdi
0x180038210  pop     rsi
0x180038211  pop     rbx
0x180038212  pop     rbp
0x180038213  retn
```
