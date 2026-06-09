# LookupTokenAccountName(void *,BUFFER *,BUFFER *)

- ea: `0x180023df0`
- end: `0x180023f36`
- name: `?LookupTokenAccountName@@YAJPEAXPEAVBUFFER@@1@Z`
- size: `326`
- prototype: `int __fastcall(void *, struct BUFFER *, struct BUFFER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002da0`
- `0x180023df0`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023e47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023e47`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023ead`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023f08`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023ead`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180023f08`

## pseudocode

```c
int __fastcall LookupTokenAccountName(void *a1, struct BUFFER *a2, struct BUFFER *a3)
{
  int result; // eax
  WCHAR *v6; // r8
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-39h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-35h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+4Ch] [rbp-2Dh] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-29h] BYREF

  ReturnLength = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
  {
    v6 = (WCHAR *)*((_QWORD *)a2 + 4);
    cchName = *((_DWORD *)a2 + 10);
    cchReferencedDomainName = *((_DWORD *)a3 + 10);
    if ( LookupAccountSidW(0, TokenInformation[0], v6, &cchName, *((LPWSTR *)a3 + 4), &cchReferencedDomainName, &peUse)
      || BUFFER::Resize(a2, cchName)
      && BUFFER::Resize(a3, cchReferencedDomainName)
      && LookupAccountSidW(
           0,
           TokenInformation[0],
           *((LPWSTR *)a2 + 4),
           &cchName,
           *((LPWSTR *)a3 + 4),
           &cchReferencedDomainName,
           &peUse) )
    {
      return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180023df0  push    rbp
0x180023df2  push    rbx
0x180023df3  push    rdi
0x180023df4  lea     rbp, [rsp-47h]
0x180023df9  sub     rsp, 0C0h
0x180023e00  mov     rax, cs:__security_cookie
0x180023e07  xor     rax, rsp
0x180023e0a  mov     [rbp+57h+var_20], rax
0x180023e0e  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180023e14  mov     [rbp+57h+var_84], 0
0x180023e1b  mov     rbx, r8
0x180023e1e  mov     [rbp+57h+cchName], 0
0x180023e25  mov     rdi, rdx
0x180023e28  mov     [rbp+57h+var_90], 0
0x180023e2f  lea     rax, [rbp+57h+var_84]
0x180023e33  mov     [rbp+57h+var_88], 0
0x180023e3a  lea     edx, [r9-53h]; TokenInformationClass
0x180023e3e  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180023e43  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180023e47  call    cs:__imp_GetTokenInformation
0x180023e4e  nop     dword ptr [rax+rax+00h]
0x180023e53  test    eax, eax
0x180023e55  jnz     short loc_180023E78
0x180023e57  call    cs:__imp_GetLastError
0x180023e5e  nop     dword ptr [rax+rax+00h]
0x180023e63  test    eax, eax
0x180023e65  jle     loc_180023F1E
0x180023e6b  movzx   eax, ax
0x180023e6e  or      eax, 80070000h
0x180023e73  jmp     loc_180023F1E
0x180023e78  mov     eax, [rdi+28h]
0x180023e7b  lea     r9, [rbp+57h+cchName]; cchName
0x180023e7f  mov     r8, [rdi+20h]; Name
0x180023e83  xor     ecx, ecx; lpSystemName
0x180023e85  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x180023e89  mov     [rbp+57h+cchName], eax
0x180023e8c  mov     eax, [rbx+28h]
0x180023e8f  mov     [rbp+57h+var_90], eax
0x180023e92  lea     rax, [rbp+57h+var_88]
0x180023e96  mov     [rsp+0D0h+peUse], rax; peUse
0x180023e9b  lea     rax, [rbp+57h+var_90]
0x180023e9f  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023ea4  mov     rax, [rbx+20h]
0x180023ea8  mov     [rsp+0D0h+ReturnLength], rax; ReferencedDomainName
0x180023ead  call    cs:__imp_LookupAccountSidW
0x180023eb4  nop     dword ptr [rax+rax+00h]
0x180023eb9  test    eax, eax
0x180023ebb  jnz     short loc_180023F1C
0x180023ebd  mov     edx, [rbp+57h+cchName]; unsigned int
0x180023ec0  mov     rcx, rdi; this
0x180023ec3  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180023ec8  test    al, al
0x180023eca  jz      short loc_180023E57
0x180023ecc  mov     edx, [rbp+57h+var_90]; unsigned int
0x180023ecf  mov     rcx, rbx; this
0x180023ed2  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180023ed7  test    al, al
0x180023ed9  jz      loc_180023E57
0x180023edf  mov     r8, [rdi+20h]; Name
0x180023ee3  lea     rax, [rbp+57h+var_88]
0x180023ee7  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x180023eeb  lea     r9, [rbp+57h+cchName]; cchName
0x180023eef  mov     [rsp+0D0h+peUse], rax; peUse
0x180023ef4  xor     ecx, ecx; lpSystemName
0x180023ef6  lea     rax, [rbp+57h+var_90]
0x180023efa  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180023eff  mov     rax, [rbx+20h]
0x180023f03  mov     [rsp+0D0h+ReturnLength], rax; ReferencedDomainName
0x180023f08  call    cs:__imp_LookupAccountSidW
0x180023f0f  nop     dword ptr [rax+rax+00h]
0x180023f14  test    eax, eax
0x180023f16  jz      loc_180023E57
0x180023f1c  xor     eax, eax
0x180023f1e  mov     rcx, [rbp+57h+var_20]
0x180023f22  xor     rcx, rsp; StackCookie
0x180023f25  call    __security_check_cookie
0x180023f2a  add     rsp, 0C0h
0x180023f31  pop     rdi
0x180023f32  pop     rbx
0x180023f33  pop     rbp
0x180023f34  retn
```
