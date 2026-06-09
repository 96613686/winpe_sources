# GetTSLSGroupNameAndDomainInfo

- ea: `0x18006d4cc`
- end: `0x18006d6be`
- name: `GetTSLSGroupNameAndDomainInfo`
- size: `498`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180058b00`

## callees

- `0x18006d4cc`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18006d619`
- `msvcrt!_wcsdup` at `0x18006d63e`
- `msvcrt!_wcsdup` at `0x18006d657`
- `msvcrt!_wcsdup` at `0x18006d619`
- `msvcrt!_wcsdup` at `0x18006d63e`
- `msvcrt!_wcsdup` at `0x18006d657`
- `ADVAPI32!CreateWellKnownSid` at `0x18006d5b1`
- `ADVAPI32!CreateWellKnownSid` at `0x18006d5b1`
- `ADVAPI32!LookupAccountSidW` at `0x18006d604`
- `ADVAPI32!LookupAccountSidW` at `0x18006d604`
- `NETAPI32!DsGetDcNameW` at `0x18006d586`
- `NETAPI32!DsGetDcNameW` at `0x18006d586`
- `NETAPI32!NetApiBufferFree` at `0x18006d68e`
- `NETAPI32!NetApiBufferFree` at `0x18006d68e`
- `KERNEL32!GetLastError` at `0x18006d5c1`
- `KERNEL32!GetLastError` at `0x18006d5c1`
- `KERNEL32!LocalAlloc` at `0x18006d548`
- `KERNEL32!LocalAlloc` at `0x18006d548`
- `KERNEL32!LocalFree` at `0x18006d673`
- `KERNEL32!LocalFree` at `0x18006d673`

## pseudocode

```c
__int64 __fastcall GetTSLSGroupNameAndDomainInfo(wchar_t **a1, LPCWSTR *a2, wchar_t **a3)
{
  PDOMAIN_CONTROLLER_INFOW v4; // rcx
  HLOCAL v7; // rsi
  DWORD DcNameW; // ebx
  const wchar_t *DomainControllerName; // r12
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName[3]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[520]; // [rsp+270h] [rbp+170h] BYREF

  cchName[0] = 260;
  v4 = 0;
  cchReferencedDomainName = 520;
  peUse = 0;
  DomainControllerInfo = 0;
  cbSid = 68;
  if ( a3 && a1 && a2 )
  {
    *a1 = 0;
    *a3 = 0;
    v7 = LocalAlloc(0x40u, 0x44u);
    if ( v7 )
    {
      DcNameW = DsGetDcNameW(0, *a2, 0, 0, 0x80000020, &DomainControllerInfo);
      if ( !DcNameW )
      {
        DomainControllerName = DomainControllerInfo->DomainControllerName;
        if ( CreateWellKnownSid(WinBuiltinTerminalServerLicenseServersSid, 0, v7, &cbSid)
          && LookupAccountSidW(
               DomainControllerName,
               v7,
               Name,
               cchName,
               ReferencedDomainName,
               &cchReferencedDomainName,
               &peUse) )
        {
          DcNameW = 0;
          v10 = _wcsdup(DomainControllerName);
          *a1 = v10;
          if ( !v10
            || !*a2 && (v11 = _wcsdup(DomainControllerInfo->DomainName), (*a2 = v11) == 0)
            || (v12 = _wcsdup(Name), (*a3 = v12) == 0) )
          {
            DcNameW = 14;
          }
        }
        else
        {
          DcNameW = GetLastError();
        }
      }
      LocalFree(v7);
    }
    else
    {
      DcNameW = 8;
    }
    v4 = DomainControllerInfo;
  }
  else
  {
    DcNameW = 87;
  }
  if ( v4 )
    NetApiBufferFree(v4);
  return DcNameW;
}

```

## disassembly

```asm
0x18006d4cc  push    rbp
0x18006d4ce  push    rbx
0x18006d4cf  push    rsi
0x18006d4d0  push    rdi
0x18006d4d1  push    r12
0x18006d4d3  push    r14
0x18006d4d5  push    r15
0x18006d4d7  lea     rbp, [rsp-590h]
0x18006d4df  sub     rsp, 690h
0x18006d4e6  mov     rax, cs:__security_cookie
0x18006d4ed  xor     rax, rsp
0x18006d4f0  mov     [rbp+5C0h+var_40], rax
0x18006d4f7  mov     r14, rcx
0x18006d4fa  mov     [rsp+6C0h+cchName], 104h
0x18006d502  xor     ecx, ecx; Buffer
0x18006d504  mov     [rsp+6C0h+cchReferencedDomainName], 208h
0x18006d50c  and     [rsp+6C0h+var_674], ecx
0x18006d510  mov     rdi, rdx
0x18006d513  mov     [rsp+6C0h+var_680], rcx
0x18006d518  mov     edx, 44h ; 'D'; uBytes
0x18006d51d  mov     [rsp+6C0h+cbSid], edx
0x18006d521  mov     r15, r8
0x18006d524  test    r8, r8
0x18006d527  jz      loc_18006D684
0x18006d52d  test    r14, r14
0x18006d530  jz      loc_18006D684
0x18006d536  test    rdi, rdi
0x18006d539  jz      loc_18006D684
0x18006d53f  and     [r14], rcx
0x18006d542  and     [r8], rcx
0x18006d545  lea     ecx, [rdx-4]; uFlags
0x18006d548  call    cs:__imp_LocalAlloc
0x18006d54f  nop     dword ptr [rax+rax+00h]
0x18006d554  mov     rsi, rax
0x18006d557  test    rax, rax
0x18006d55a  jnz     short loc_18006D569
0x18006d55c  lea     ebx, [rax+8]
0x18006d55f  mov     rcx, [rsp+6C0h+var_680]
0x18006d564  jmp     loc_18006D689
0x18006d569  mov     rdx, [rdi]; DomainName
0x18006d56c  lea     rax, [rsp+6C0h+var_680]
0x18006d571  mov     [rsp+6C0h+DomainControllerInfo], rax; DomainControllerInfo
0x18006d576  xor     r9d, r9d; SiteName
0x18006d579  xor     r8d, r8d; DomainGuid
0x18006d57c  mov     [rsp+6C0h+Flags], 80000020h; Flags
0x18006d584  xor     ecx, ecx; ComputerName
0x18006d586  call    cs:__imp_DsGetDcNameW
0x18006d58d  nop     dword ptr [rax+rax+00h]
0x18006d592  mov     ebx, eax
0x18006d594  test    eax, eax
0x18006d596  jnz     loc_18006D670
0x18006d59c  mov     rax, [rsp+6C0h+var_680]
0x18006d5a1  lea     r9, [rsp+6C0h+cbSid]; cbSid
0x18006d5a6  mov     r8, rsi; pSid
0x18006d5a9  lea     ecx, [rbx+3Ch]; WellKnownSidType
0x18006d5ac  xor     edx, edx; DomainSid
0x18006d5ae  mov     r12, [rax]
0x18006d5b1  call    cs:__imp_CreateWellKnownSid
0x18006d5b8  nop     dword ptr [rax+rax+00h]
0x18006d5bd  test    eax, eax
0x18006d5bf  jnz     short loc_18006D5D4
0x18006d5c1  call    cs:__imp_GetLastError
0x18006d5c8  nop     dword ptr [rax+rax+00h]
0x18006d5cd  mov     ebx, eax
0x18006d5cf  jmp     loc_18006D670
0x18006d5d4  lea     rax, [rsp+6C0h+var_674]
0x18006d5d9  mov     rdx, rsi; Sid
0x18006d5dc  mov     [rsp+6C0h+peUse], rax; peUse
0x18006d5e1  lea     r9, [rsp+6C0h+cchName]; cchName
0x18006d5e6  lea     rax, [rsp+6C0h+cchReferencedDomainName]
0x18006d5eb  mov     rcx, r12; lpSystemName
0x18006d5ee  mov     [rsp+6C0h+DomainControllerInfo], rax; cchReferencedDomainName
0x18006d5f3  lea     r8, [rsp+6C0h+Name]; Name
0x18006d5f8  lea     rax, [rbp+5C0h+ReferencedDomainName]
0x18006d5ff  mov     qword ptr [rsp+6C0h+Flags], rax; ReferencedDomainName
0x18006d604  call    cs:__imp_LookupAccountSidW
0x18006d60b  nop     dword ptr [rax+rax+00h]
0x18006d610  test    eax, eax
0x18006d612  jz      short loc_18006D5C1
0x18006d614  mov     rcx, r12; String
0x18006d617  xor     ebx, ebx
0x18006d619  call    cs:__imp__wcsdup
0x18006d620  nop     dword ptr [rax+rax+00h]
0x18006d625  mov     [r14], rax
0x18006d628  test    rax, rax
0x18006d62b  jz      short loc_18006D66B
0x18006d62d  mov     rax, [rdi]
0x18006d630  test    rax, rax
0x18006d633  jnz     short loc_18006D652
0x18006d635  mov     rcx, [rsp+6C0h+var_680]
0x18006d63a  mov     rcx, [rcx+28h]; String
0x18006d63e  call    cs:__imp__wcsdup
0x18006d645  nop     dword ptr [rax+rax+00h]
0x18006d64a  mov     [rdi], rax
0x18006d64d  test    rax, rax
0x18006d650  jz      short loc_18006D66B
0x18006d652  lea     rcx, [rsp+6C0h+Name]; String
0x18006d657  call    cs:__imp__wcsdup
0x18006d65e  nop     dword ptr [rax+rax+00h]
0x18006d663  mov     [r15], rax
0x18006d666  test    rax, rax
0x18006d669  jnz     short loc_18006D670
0x18006d66b  mov     ebx, 0Eh
0x18006d670  mov     rcx, rsi; hMem
0x18006d673  call    cs:__imp_LocalFree
0x18006d67a  nop     dword ptr [rax+rax+00h]
0x18006d67f  jmp     loc_18006D55F
0x18006d684  mov     ebx, 57h ; 'W'
0x18006d689  test    rcx, rcx
0x18006d68c  jz      short loc_18006D69A
0x18006d68e  call    cs:__imp_NetApiBufferFree
0x18006d695  nop     dword ptr [rax+rax+00h]
0x18006d69a  mov     eax, ebx
0x18006d69c  mov     rcx, [rbp+5C0h+var_40]
0x18006d6a3  xor     rcx, rsp; StackCookie
0x18006d6a6  call    __security_check_cookie
0x18006d6ab  add     rsp, 690h
0x18006d6b2  pop     r15
0x18006d6b4  pop     r14
0x18006d6b6  pop     r12
0x18006d6b8  pop     rdi
0x18006d6b9  pop     rsi
0x18006d6ba  pop     rbx
0x18006d6bb  pop     rbp
0x18006d6bc  retn
```
