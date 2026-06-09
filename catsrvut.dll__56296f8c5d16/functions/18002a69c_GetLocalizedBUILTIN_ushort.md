# GetLocalizedBUILTIN(ushort * *)

- ea: `0x18002a69c`
- end: `0x18002a847`
- name: `?GetLocalizedBUILTIN@@YAJPEAPEAG@Z`
- size: `427`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029e90`
- `0x18002a350`

## callees

- `0x18002a69c`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a6ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a81a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002a7d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002a7d3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002a74b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002a74b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002a780`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002a7b8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002a780`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002a7b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    CoTaskMemFree(v4);
  }
  else
  {
    CoTaskMemFree(v4);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002a69c  push    rbp
0x18002a69e  push    rbx
0x18002a69f  push    rsi
0x18002a6a0  push    rdi
0x18002a6a1  lea     rbp, [rsp-1C8h]
0x18002a6a9  sub     rsp, 2C8h
0x18002a6b0  mov     rax, cs:__security_cookie
0x18002a6b7  xor     rax, rsp
0x18002a6ba  mov     [rbp+1E0h+var_30], rax
0x18002a6c1  mov     rdi, rcx
0x18002a6c4  mov     rax, cs:?g_pwzBUILTIN@@3PEAGEA; ushort * g_pwzBUILTIN
0x18002a6cb  xor     esi, esi
0x18002a6cd  test    rax, rax
0x18002a6d0  jz      short loc_18002A6DC
0x18002a6d2  mov     [rcx], rax
0x18002a6d5  xor     eax, eax
0x18002a6d7  jmp     loc_18002A82C
0x18002a6dc  mov     [rcx], rsi
0x18002a6df  mov     [rsp+2E0h+cchName], esi
0x18002a6e3  mov     [rsp+2E0h+cchReferencedDomainName], esi
0x18002a6e7  mov     ecx, 20h ; ' '; cb
0x18002a6ec  call    cs:__imp_CoTaskMemAlloc
0x18002a6f2  mov     rbx, rax
0x18002a6f5  test    rax, rax
0x18002a6f8  jnz     short loc_18002A704
0x18002a6fa  mov     eax, 8007000Eh
0x18002a6ff  jmp     loc_18002A82C
0x18002a704  mov     [rax], si
0x18002a707  mov     [rsp+2E0h+var_26C], esi
0x18002a70b  mov     dword ptr [rsp+2E0h+pIdentifierAuthority.Value], esi
0x18002a70f  mov     word ptr [rsp+2E0h+pIdentifierAuthority.Value+4], 500h
0x18002a716  mov     [rsp+2E0h+Sid], rsi
0x18002a71b  lea     rax, [rsp+2E0h+Sid]
0x18002a720  mov     [rsp+2E0h+pSid], rax; pSid
0x18002a725  mov     [rsp+2E0h+nSubAuthority7], esi; nSubAuthority7
0x18002a729  mov     [rsp+2E0h+nSubAuthority6], esi; nSubAuthority6
0x18002a72d  mov     [rsp+2E0h+nSubAuthority5], esi; nSubAuthority5
0x18002a731  mov     [rsp+2E0h+nSubAuthority4], esi; nSubAuthority4
0x18002a735  mov     [rsp+2E0h+nSubAuthority3], esi; nSubAuthority3
0x18002a739  mov     [rsp+2E0h+nSubAuthority2], esi; nSubAuthority2
0x18002a73d  xor     r9d, r9d; nSubAuthority1
0x18002a740  lea     r8d, [r9+20h]; nSubAuthority0
0x18002a744  mov     dl, 1; nSubAuthorityCount
0x18002a746  lea     rcx, [rsp+2E0h+pIdentifierAuthority]; pIdentifierAuthority
0x18002a74b  call    cs:__imp_AllocateAndInitializeSid
0x18002a751  test    eax, eax
0x18002a753  jz      loc_18002A810
0x18002a759  mov     [rsp+2E0h+peUse], esi
0x18002a75d  lea     rax, [rsp+2E0h+peUse]
0x18002a762  mov     qword ptr [rsp+2E0h+nSubAuthority3], rax; peUse
0x18002a767  lea     rax, [rsp+2E0h+cchReferencedDomainName]
0x18002a76c  mov     qword ptr [rsp+2E0h+nSubAuthority2], rax; cchReferencedDomainName
0x18002a771  xor     r9d, r9d; ReferencedDomainName
0x18002a774  lea     r8, [rsp+2E0h+cchName]; cchName
0x18002a779  xor     edx, edx; Name
0x18002a77b  mov     rcx, [rsp+2E0h+Sid]; Sid
0x18002a780  call    cs:__imp_LookupAccountSidLocalW
0x18002a786  mov     eax, [rsp+2E0h+cchName]
0x18002a78a  dec     eax
0x18002a78c  cmp     eax, 110h
0x18002a791  ja      short loc_18002A7FF
0x18002a793  lea     rax, [rsp+2E0h+var_26C]
0x18002a798  mov     qword ptr [rsp+2E0h+nSubAuthority3], rax; peUse
0x18002a79d  lea     rax, [rsp+2E0h+cchReferencedDomainName]
0x18002a7a2  mov     qword ptr [rsp+2E0h+nSubAuthority2], rax; cchReferencedDomainName
0x18002a7a7  mov     r9, rbx; ReferencedDomainName
0x18002a7aa  lea     r8, [rsp+2E0h+cchName]; cchName
0x18002a7af  lea     rdx, [rbp+1E0h+Name]; Name
0x18002a7b3  mov     rcx, [rsp+2E0h+Sid]; Sid
0x18002a7b8  call    cs:__imp_LookupAccountSidLocalW
0x18002a7be  test    eax, eax
0x18002a7c0  jnz     short loc_18002A7CE
0x18002a7c2  mov     rcx, rbx; pv
0x18002a7c5  call    cs:__imp_CoTaskMemFree
0x18002a7cb  nop
0x18002a7cc  jmp     short loc_18002A81A
0x18002a7ce  mov     rcx, [rsp+2E0h+Sid]; pSid
0x18002a7d3  call    cs:__imp_FreeSid
0x18002a7d9  xor     eax, eax
0x18002a7db  lock cmpxchg cs:?g_pwzBUILTIN@@3PEAGEA, rbx; ushort * g_pwzBUILTIN
0x18002a7e4  jz      short loc_18002A7F0
0x18002a7e6  mov     rcx, rbx; pv
0x18002a7e9  call    cs:__imp_CoTaskMemFree
0x18002a7ef  nop
0x18002a7f0  mov     rax, cs:?g_pwzBUILTIN@@3PEAGEA; ushort * g_pwzBUILTIN
0x18002a7f7  mov     [rdi], rax
0x18002a7fa  jmp     loc_18002A6D5
0x18002a7ff  mov     rcx, rbx; pv
0x18002a802  call    cs:__imp_CoTaskMemFree
0x18002a808  nop
0x18002a809  mov     eax, 8000FFFFh
0x18002a80e  jmp     short loc_18002A82C
0x18002a810  mov     rcx, rbx; pv
0x18002a813  call    cs:__imp_CoTaskMemFree
0x18002a819  nop
0x18002a81a  call    cs:__imp_GetLastError
0x18002a820  test    eax, eax
0x18002a822  jle     short loc_18002A82C
0x18002a824  movzx   eax, ax
0x18002a827  or      eax, 80070000h
0x18002a82c  mov     rcx, [rbp+1E0h+var_30]
0x18002a833  xor     rcx, rsp; StackCookie
0x18002a836  call    __security_check_cookie
0x18002a83b  add     rsp, 2C8h
0x18002a842  pop     rdi
0x18002a843  pop     rsi
0x18002a844  pop     rbx
0x18002a845  pop     rbp
0x18002a846  retn
```
