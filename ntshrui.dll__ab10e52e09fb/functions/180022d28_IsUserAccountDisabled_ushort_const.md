# IsUserAccountDisabled(ushort const *)

- ea: `0x180022d28`
- end: `0x180022e21`
- name: `?IsUserAccountDisabled@@YA_NPEBG@Z`
- size: `249`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019068`
- `0x18006a258`

## callees

- `0x180022d28`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022df9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022df9`
- `netutils!NetApiBufferFree` at `0x180022dee`
- `netutils!NetApiBufferFree` at `0x180022dee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180022d5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180022d5e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022db2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180022db2`
- `samcli!NetUserGetInfo` at `0x180022dd7`
- `samcli!NetUserGetInfo` at `0x180022dd7`

## pseudocode

```c
bool __fastcall IsUserAccountDisabled(const unsigned __int16 *a1)
{
  bool v1; // bl
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  LPBYTE bufptr; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+270h] [rbp+170h] BYREF

  Sid = 0;
  v1 = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    peUse = 0;
    cchName = 260;
    cchReferencedDomainName = 260;
    if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      bufptr = 0;
      if ( !NetUserGetInfo(0, Name, 1u, &bufptr) )
      {
        v1 = (*((_DWORD *)bufptr + 10) & 2) != 0;
        NetApiBufferFree(bufptr);
      }
    }
    LocalFree(Sid);
  }
  return v1;
}

```

## disassembly

```asm
0x180022d28  mov     [rsp-8+arg_8], rbx
0x180022d2d  push    rbp
0x180022d2e  lea     rbp, [rsp-390h]
0x180022d36  sub     rsp, 490h
0x180022d3d  mov     rax, cs:__security_cookie
0x180022d44  xor     rax, rsp
0x180022d47  mov     [rbp+390h+var_10], rax
0x180022d4e  lea     rdx, [rsp+490h+Sid]; Sid
0x180022d53  mov     [rsp+490h+Sid], 0
0x180022d5c  xor     bl, bl
0x180022d5e  call    cs:__imp_ConvertStringSidToSidW
0x180022d64  test    eax, eax
0x180022d66  jz      loc_180022DFF
0x180022d6c  mov     rdx, [rsp+490h+Sid]; Sid
0x180022d71  lea     r9, [rsp+490h+cchName]; cchName
0x180022d76  mov     eax, 104h
0x180022d7b  mov     [rsp+490h+var_450], 0
0x180022d83  mov     [rsp+490h+cchName], eax
0x180022d87  lea     r8, [rsp+490h+Name]; Name
0x180022d8c  mov     [rsp+490h+var_44C], eax
0x180022d90  xor     ecx, ecx; lpSystemName
0x180022d92  lea     rax, [rsp+490h+var_450]
0x180022d97  mov     [rsp+490h+peUse], rax; peUse
0x180022d9c  lea     rax, [rsp+490h+var_44C]
0x180022da1  mov     [rsp+490h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180022da6  lea     rax, [rbp+390h+var_220]
0x180022dad  mov     [rsp+490h+ReferencedDomainName], rax; ReferencedDomainName
0x180022db2  call    cs:__imp_LookupAccountSidW
0x180022db8  test    eax, eax
0x180022dba  jz      short loc_180022DF4
0x180022dbc  lea     r9, [rsp+490h+bufptr]; bufptr
0x180022dc1  mov     [rsp+490h+bufptr], 0
0x180022dca  mov     r8d, 1; level
0x180022dd0  lea     rdx, [rsp+490h+Name]; username
0x180022dd5  xor     ecx, ecx; servername
0x180022dd7  call    cs:__imp_NetUserGetInfo
0x180022ddd  test    eax, eax
0x180022ddf  jnz     short loc_180022DF4
0x180022de1  mov     rcx, [rsp+490h+bufptr]; Buffer
0x180022de6  mov     ebx, [rcx+28h]
0x180022de9  shr     ebx, 1
0x180022deb  and     bl, 1
0x180022dee  call    cs:__imp_NetApiBufferFree
0x180022df4  mov     rcx, [rsp+490h+Sid]; hMem
0x180022df9  call    cs:__imp_LocalFree
0x180022dff  mov     al, bl
0x180022e01  mov     rcx, [rbp+390h+var_10]
0x180022e08  xor     rcx, rsp; StackCookie
0x180022e0b  call    __security_check_cookie
0x180022e10  mov     rbx, [rsp+490h+arg_8]
0x180022e18  add     rsp, 490h
0x180022e1f  pop     rbp
0x180022e20  retn
```
