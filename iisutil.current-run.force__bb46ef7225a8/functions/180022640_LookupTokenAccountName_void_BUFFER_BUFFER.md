# LookupTokenAccountName(void *,BUFFER *,BUFFER *)

- ea: `0x180022640`
- end: `0x180022769`
- name: `?LookupTokenAccountName@@YAJPEAXPEAVBUFFER@@1@Z`
- size: `297`
- prototype: `int(void *, struct BUFFER *, struct BUFFER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002470`
- `0x180022640`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022697`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022697`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800226f1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022742`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800226f1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022742`

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
0x180022640  push    rbp
0x180022642  push    rbx
0x180022643  push    rdi
0x180022644  lea     rbp, [rsp-47h]
0x180022649  sub     rsp, 0C0h
0x180022650  mov     rax, cs:__security_cookie
0x180022657  xor     rax, rsp
0x18002265a  mov     [rbp+57h+var_20], rax
0x18002265e  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180022664  mov     [rbp+57h+var_84], 0
0x18002266b  mov     rbx, r8
0x18002266e  mov     [rbp+57h+cchName], 0
0x180022675  mov     rdi, rdx
0x180022678  mov     [rbp+57h+var_90], 0
0x18002267f  lea     rax, [rbp+57h+var_84]
0x180022683  mov     [rbp+57h+var_88], 0
0x18002268a  lea     edx, [r9-53h]; TokenInformationClass
0x18002268e  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180022693  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180022697  call    cs:__imp_GetTokenInformation
0x18002269d  test    eax, eax
0x18002269f  jnz     short loc_1800226BC
0x1800226a1  call    cs:__imp_GetLastError
0x1800226a7  test    eax, eax
0x1800226a9  jle     loc_180022752
0x1800226af  movzx   eax, ax
0x1800226b2  or      eax, 80070000h
0x1800226b7  jmp     loc_180022752
0x1800226bc  mov     eax, [rdi+28h]
0x1800226bf  lea     r9, [rbp+57h+cchName]; cchName
0x1800226c3  mov     r8, [rdi+20h]; Name
0x1800226c7  xor     ecx, ecx; lpSystemName
0x1800226c9  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x1800226cd  mov     [rbp+57h+cchName], eax
0x1800226d0  mov     eax, [rbx+28h]
0x1800226d3  mov     [rbp+57h+var_90], eax
0x1800226d6  lea     rax, [rbp+57h+var_88]
0x1800226da  mov     [rsp+0D0h+peUse], rax; peUse
0x1800226df  lea     rax, [rbp+57h+var_90]
0x1800226e3  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800226e8  mov     rax, [rbx+20h]
0x1800226ec  mov     [rsp+0D0h+ReturnLength], rax; ReferencedDomainName
0x1800226f1  call    cs:__imp_LookupAccountSidW
0x1800226f7  test    eax, eax
0x1800226f9  jnz     short loc_180022750
0x1800226fb  mov     edx, [rbp+57h+cchName]; unsigned int
0x1800226fe  mov     rcx, rdi; this
0x180022701  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180022706  test    al, al
0x180022708  jz      short loc_1800226A1
0x18002270a  mov     edx, [rbp+57h+var_90]; unsigned int
0x18002270d  mov     rcx, rbx; this
0x180022710  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180022715  test    al, al
0x180022717  jz      short loc_1800226A1
0x180022719  mov     r8, [rdi+20h]; Name
0x18002271d  lea     rax, [rbp+57h+var_88]
0x180022721  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x180022725  lea     r9, [rbp+57h+cchName]; cchName
0x180022729  mov     [rsp+0D0h+peUse], rax; peUse
0x18002272e  xor     ecx, ecx; lpSystemName
0x180022730  lea     rax, [rbp+57h+var_90]
0x180022734  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180022739  mov     rax, [rbx+20h]
0x18002273d  mov     [rsp+0D0h+ReturnLength], rax; ReferencedDomainName
0x180022742  call    cs:__imp_LookupAccountSidW
0x180022748  test    eax, eax
0x18002274a  jz      loc_1800226A1
0x180022750  xor     eax, eax
0x180022752  mov     rcx, [rbp+57h+var_20]
0x180022756  xor     rcx, rsp; StackCookie
0x180022759  call    __security_check_cookie
0x18002275e  add     rsp, 0C0h
0x180022765  pop     rdi
0x180022766  pop     rbx
0x180022767  pop     rbp
0x180022768  retn
```
