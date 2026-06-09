# CCsrMgr::CreatePortSecurityDescriptor(void * *)

- ea: `0x180074094`
- end: `0x180074267`
- name: `?CreatePortSecurityDescriptor@CCsrMgr@@AEAAJPEAPEAX@Z`
- size: `467`
- prototype: `__int64 __fastcall(CCsrMgr *__hidden this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073f4c`

## callees

- `0x1800077a0`
- `0x18004e850`
- `0x18004ec20`
- `0x18004ec80`
- `0x180074094`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180074238`
- `ntdll!RtlFreeSid` at `0x180074238`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800741ef`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800741ef`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180074169`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180074169`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800741c8`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800741c8`
- `ntdll!RtlCreateAcl` at `0x18007419c`
- `ntdll!RtlCreateAcl` at `0x18007419c`
- `ntdll!RtlLengthSid` at `0x180074130`
- `ntdll!RtlLengthSid` at `0x180074130`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180074104`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180074104`

## string_xrefs

- `0x1800741af`: `RtlCreateAcl failed: 0x%x in %s`
- `0x18007417c`: `RtlCreateSecurityDescriptor failed: 0x%x in %s`
- `0x180074202`: `RtlSetDaclSecurityDescriptor failed: 0x%x in %s`
- `0x18007420e`: `CCsrMgr::CreatePortSecurityDescriptor`
- `0x180074120`: `RtlAllocateAndInitializeSid( system ) failed: 0x%x in %s`
- `0x1800741db`: `RtlAddAccessAllowedAce failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CCsrMgr::CreatePortSecurityDescriptor(CCsrMgr *this, struct _ACL **a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  struct _ACL *v5; // rdi
  const struct std::nothrow_t *v6; // rdx
  unsigned __int64 v7; // r14
  struct _ACL *v8; // rax
  NTSTATUS SecurityDescriptor; // eax
  NTSTATUS Acl; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  PSID Sid; // [rsp+60h] [rbp-9h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-1h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  v4 = v3 | 0x10000000;
  if ( v3 >= 0 )
  {
    v7 = RtlLengthSid(Sid) + 60;
    v8 = (struct _ACL *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v8;
    if ( !v8 )
    {
      v4 = -2147024882;
      goto LABEL_16;
    }
    SecurityDescriptor = RtlCreateSecurityDescriptor(v8, 1u);
    v4 = SecurityDescriptor | 0x10000000;
    if ( SecurityDescriptor >= 0 )
    {
      Acl = RtlCreateAcl(v5 + 5, v7 - 40, 2u);
      v4 = Acl | 0x10000000;
      if ( Acl >= 0 )
      {
        v11 = RtlAddAccessAllowedAce(v5 + 5, 2u, 0x1F0001u, Sid);
        v4 = v11 | 0x10000000;
        if ( v11 >= 0 )
        {
          v12 = RtlSetDaclSecurityDescriptor(v5, 1u, v5 + 5, 0);
          v4 = v12 | 0x10000000;
          if ( v12 >= 0 )
          {
            *a2 = v5;
            goto LABEL_16;
          }
          _DbgPrintMessage(
            8,
            "RtlSetDaclSecurityDescriptor failed: 0x%x in %s",
            v4,
            "CCsrMgr::CreatePortSecurityDescriptor");
        }
        else
        {
          _DbgPrintMessage(8, "RtlAddAccessAllowedAce failed: 0x%x in %s", v4, "CCsrMgr::CreatePortSecurityDescriptor");
        }
      }
      else
      {
        _DbgPrintMessage(8, "RtlCreateAcl failed: 0x%x in %s", v4, "CCsrMgr::CreatePortSecurityDescriptor");
      }
    }
    else
    {
      _DbgPrintMessage(8, "RtlCreateSecurityDescriptor failed: 0x%x in %s", v4, "CCsrMgr::CreatePortSecurityDescriptor");
    }
  }
  else
  {
    v5 = 0;
    _DbgPrintMessage(
      8,
      "RtlAllocateAndInitializeSid( system ) failed: 0x%x in %s",
      v4,
      "CCsrMgr::CreatePortSecurityDescriptor");
  }
  if ( v5 )
    operator delete(v5, v6);
LABEL_16:
  if ( Sid )
    RtlFreeSid(Sid);
  return v4;
}

```

## disassembly

```asm
0x180074094  push    rbp
0x180074096  push    rbx
0x180074097  push    rsi
0x180074098  push    rdi
0x180074099  push    r12
0x18007409b  push    r13
0x18007409d  push    r14
0x18007409f  push    r15
0x1800740a1  lea     rbp, [rsp-1Fh]
0x1800740a6  sub     rsp, 88h
0x1800740ad  mov     rax, cs:__security_cookie
0x1800740b4  xor     rax, rsp
0x1800740b7  mov     [rbp+57h+var_50], rax
0x1800740bb  xor     r12d, r12d
0x1800740be  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800740c4  lea     rax, [rbp+57h+var_60]
0x1800740c8  mov     [rbp+57h+var_60], r12
0x1800740cc  mov     [rsp+0C0h+Sid], rax; Sid
0x1800740d1  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800740d5  mov     [rsp+0C0h+SubAuthority7], r12d; SubAuthority7
0x1800740da  mov     r15, rdx
0x1800740dd  mov     [rsp+0C0h+SubAuthority6], r12d; SubAuthority6
0x1800740e2  lea     r8d, [r12+12h]; SubAuthority0
0x1800740e7  mov     [rsp+0C0h+SubAuthority5], r12d; SubAuthority5
0x1800740ec  xor     r9d, r9d; SubAuthority1
0x1800740ef  mov     [rsp+0C0h+SubAuthority4], r12d; SubAuthority4
0x1800740f4  mov     dl, 1; SubAuthorityCount
0x1800740f6  mov     [rsp+0C0h+SubAuthority3], r12d; SubAuthority3
0x1800740fb  mov     [rsp+0C0h+SubAuthority2], r12d; SubAuthority2
0x180074100  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x180074104  call    cs:__imp_RtlAllocateAndInitializeSid
0x18007410b  nop     dword ptr [rax+rax+00h]
0x180074110  mov     ebx, eax
0x180074112  mov     r13d, 10000000h
0x180074118  or      ebx, r13d
0x18007411b  jge     short loc_18007412C
0x18007411d  mov     edi, r12d
0x180074120  lea     rdx, aRtlallocateand_2; "RtlAllocateAndInitializeSid( system ) f"...
0x180074127  jmp     loc_180074209
0x18007412c  mov     rcx, [rbp+57h+var_60]; Sid
0x180074130  call    cs:__imp_RtlLengthSid
0x180074137  nop     dword ptr [rax+rax+00h]
0x18007413c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180074143  lea     r14d, [rax+3Ch]
0x180074147  mov     ecx, r14d; unsigned __int64
0x18007414a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007414f  mov     rdi, rax
0x180074152  test    rax, rax
0x180074155  jnz     short loc_180074161
0x180074157  mov     ebx, 8007000Eh
0x18007415c  jmp     loc_18007422F
0x180074161  mov     edx, 1; Revision
0x180074166  mov     rcx, rdi; SecurityDescriptor
0x180074169  call    cs:__imp_RtlCreateSecurityDescriptor
0x180074170  nop     dword ptr [rax+rax+00h]
0x180074175  mov     ebx, eax
0x180074177  or      ebx, r13d
0x18007417a  jge     short loc_180074188
0x18007417c  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor failed: 0x%"...
0x180074183  jmp     loc_180074209
0x180074188  lea     edx, [r14-28h]; AclSize
0x18007418c  mov     r14d, 2
0x180074192  lea     rsi, [rdi+28h]
0x180074196  mov     r8d, r14d; AclRevision
0x180074199  mov     rcx, rsi; Acl
0x18007419c  call    cs:__imp_RtlCreateAcl
0x1800741a3  nop     dword ptr [rax+rax+00h]
0x1800741a8  mov     ebx, eax
0x1800741aa  or      ebx, r13d
0x1800741ad  jge     short loc_1800741B8
0x1800741af  lea     rdx, aRtlcreateaclFa; "RtlCreateAcl failed: 0x%x in %s"
0x1800741b6  jmp     short loc_180074209
0x1800741b8  mov     r9, [rbp+57h+var_60]; Sid
0x1800741bc  mov     r8d, 1F0001h; AccessMask
0x1800741c2  mov     edx, r14d; Revision
0x1800741c5  mov     rcx, rsi; Acl
0x1800741c8  call    cs:__imp_RtlAddAccessAllowedAce
0x1800741cf  nop     dword ptr [rax+rax+00h]
0x1800741d4  mov     ebx, eax
0x1800741d6  or      ebx, r13d
0x1800741d9  jge     short loc_1800741E4
0x1800741db  lea     rdx, aRtladdaccessal_0; "RtlAddAccessAllowedAce failed: 0x%x in "...
0x1800741e2  jmp     short loc_180074209
0x1800741e4  xor     r9d, r9d; DaclDefaulted
0x1800741e7  mov     r8, rsi; Dacl
0x1800741ea  mov     dl, 1; DaclPresent
0x1800741ec  mov     rcx, rdi; SecurityDescriptor
0x1800741ef  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800741f6  nop     dword ptr [rax+rax+00h]
0x1800741fb  mov     ebx, eax
0x1800741fd  or      ebx, r13d
0x180074200  jge     short loc_18007422C
0x180074202  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor failed: 0x"...
0x180074209  mov     ecx, 8; int
0x18007420e  lea     r9, aCcsrmgrCreatep; "CCsrMgr::CreatePortSecurityDescriptor"
0x180074215  mov     r8d, ebx
0x180074218  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007421d  test    rdi, rdi
0x180074220  jz      short loc_18007422F
0x180074222  mov     rcx, rdi; void *
0x180074225  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007422a  jmp     short loc_18007422F
0x18007422c  mov     [r15], rdi
0x18007422f  mov     rcx, [rbp+57h+var_60]; Sid
0x180074233  test    rcx, rcx
0x180074236  jz      short loc_180074244
0x180074238  call    cs:__imp_RtlFreeSid
0x18007423f  nop     dword ptr [rax+rax+00h]
0x180074244  mov     eax, ebx
0x180074246  mov     rcx, [rbp+57h+var_50]
0x18007424a  xor     rcx, rsp; StackCookie
0x18007424d  call    __security_check_cookie
0x180074252  add     rsp, 88h
0x180074259  pop     r15
0x18007425b  pop     r14
0x18007425d  pop     r13
0x18007425f  pop     r12
0x180074261  pop     rdi
0x180074262  pop     rsi
0x180074263  pop     rbx
0x180074264  pop     rbp
0x180074265  retn
```
