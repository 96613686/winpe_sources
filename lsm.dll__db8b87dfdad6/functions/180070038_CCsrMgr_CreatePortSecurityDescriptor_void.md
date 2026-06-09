# CCsrMgr::CreatePortSecurityDescriptor(void * *)

- ea: `0x180070038`
- end: `0x1800701dd`
- name: `?CreatePortSecurityDescriptor@CCsrMgr@@AEAAJPEAPEAX@Z`
- size: `421`
- prototype: `__int64 __fastcall(CCsrMgr *this, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006fefc`

## callees

- `0x1800074c0`
- `0x18004b460`
- `0x18004b830`
- `0x18004b890`
- `0x180070038`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800701b5`
- `ntdll!RtlFreeSid` at `0x1800701b5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180070172`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180070172`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180070101`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180070101`
- `ntdll!RtlAddAccessAllowedAce` at `0x180070151`
- `ntdll!RtlAddAccessAllowedAce` at `0x180070151`
- `ntdll!RtlCreateAcl` at `0x18007012b`
- `ntdll!RtlCreateAcl` at `0x18007012b`
- `ntdll!RtlLengthSid` at `0x1800700ce`
- `ntdll!RtlLengthSid` at `0x1800700ce`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800700a8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800700a8`

## string_xrefs

- `0x180070138`: `RtlCreateAcl failed: 0x%x in %s`
- `0x18007010e`: `RtlCreateSecurityDescriptor failed: 0x%x in %s`
- `0x18007017f`: `RtlSetDaclSecurityDescriptor failed: 0x%x in %s`
- `0x18007018b`: `CCsrMgr::CreatePortSecurityDescriptor`
- `0x1800700be`: `RtlAllocateAndInitializeSid( system ) failed: 0x%x in %s`
- `0x18007015e`: `RtlAddAccessAllowedAce failed: 0x%x in %s`

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
0x180070038  push    rbp
0x18007003a  push    rbx
0x18007003b  push    rsi
0x18007003c  push    rdi
0x18007003d  push    r12
0x18007003f  push    r13
0x180070041  push    r14
0x180070043  push    r15
0x180070045  lea     rbp, [rsp-1Fh]
0x18007004a  sub     rsp, 88h
0x180070051  mov     rax, cs:__security_cookie
0x180070058  xor     rax, rsp
0x18007005b  mov     [rbp+57h+var_50], rax
0x18007005f  xor     r12d, r12d
0x180070062  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180070068  lea     rax, [rbp+57h+var_60]
0x18007006c  mov     [rbp+57h+var_60], r12
0x180070070  mov     [rsp+0C0h+Sid], rax; Sid
0x180070075  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180070079  mov     [rsp+0C0h+SubAuthority7], r12d; SubAuthority7
0x18007007e  mov     r15, rdx
0x180070081  mov     [rsp+0C0h+SubAuthority6], r12d; SubAuthority6
0x180070086  lea     r8d, [r12+12h]; SubAuthority0
0x18007008b  mov     [rsp+0C0h+SubAuthority5], r12d; SubAuthority5
0x180070090  xor     r9d, r9d; SubAuthority1
0x180070093  mov     [rsp+0C0h+SubAuthority4], r12d; SubAuthority4
0x180070098  mov     dl, 1; SubAuthorityCount
0x18007009a  mov     [rsp+0C0h+SubAuthority3], r12d; SubAuthority3
0x18007009f  mov     [rsp+0C0h+SubAuthority2], r12d; SubAuthority2
0x1800700a4  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x1800700a8  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800700ae  mov     ebx, eax
0x1800700b0  mov     r13d, 10000000h
0x1800700b6  or      ebx, r13d
0x1800700b9  jge     short loc_1800700CA
0x1800700bb  mov     edi, r12d
0x1800700be  lea     rdx, aRtlallocateand_2; "RtlAllocateAndInitializeSid( system ) f"...
0x1800700c5  jmp     loc_180070186
0x1800700ca  mov     rcx, [rbp+57h+var_60]; Sid
0x1800700ce  call    cs:__imp_RtlLengthSid
0x1800700d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800700db  lea     r14d, [rax+3Ch]
0x1800700df  mov     ecx, r14d; unsigned __int64
0x1800700e2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800700e7  mov     rdi, rax
0x1800700ea  test    rax, rax
0x1800700ed  jnz     short loc_1800700F9
0x1800700ef  mov     ebx, 8007000Eh
0x1800700f4  jmp     loc_1800701AC
0x1800700f9  mov     edx, 1; Revision
0x1800700fe  mov     rcx, rdi; SecurityDescriptor
0x180070101  call    cs:__imp_RtlCreateSecurityDescriptor
0x180070107  mov     ebx, eax
0x180070109  or      ebx, r13d
0x18007010c  jge     short loc_180070117
0x18007010e  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor failed: 0x%"...
0x180070115  jmp     short loc_180070186
0x180070117  lea     edx, [r14-28h]; AclSize
0x18007011b  mov     r14d, 2
0x180070121  lea     rsi, [rdi+28h]
0x180070125  mov     r8d, r14d; AclRevision
0x180070128  mov     rcx, rsi; Acl
0x18007012b  call    cs:__imp_RtlCreateAcl
0x180070131  mov     ebx, eax
0x180070133  or      ebx, r13d
0x180070136  jge     short loc_180070141
0x180070138  lea     rdx, aRtlcreateaclFa; "RtlCreateAcl failed: 0x%x in %s"
0x18007013f  jmp     short loc_180070186
0x180070141  mov     r9, [rbp+57h+var_60]; Sid
0x180070145  mov     r8d, 1F0001h; AccessMask
0x18007014b  mov     edx, r14d; Revision
0x18007014e  mov     rcx, rsi; Acl
0x180070151  call    cs:__imp_RtlAddAccessAllowedAce
0x180070157  mov     ebx, eax
0x180070159  or      ebx, r13d
0x18007015c  jge     short loc_180070167
0x18007015e  lea     rdx, aRtladdaccessal_0; "RtlAddAccessAllowedAce failed: 0x%x in "...
0x180070165  jmp     short loc_180070186
0x180070167  xor     r9d, r9d; DaclDefaulted
0x18007016a  mov     r8, rsi; Dacl
0x18007016d  mov     dl, 1; DaclPresent
0x18007016f  mov     rcx, rdi; SecurityDescriptor
0x180070172  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180070178  mov     ebx, eax
0x18007017a  or      ebx, r13d
0x18007017d  jge     short loc_1800701A9
0x18007017f  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor failed: 0x"...
0x180070186  mov     ecx, 8; int
0x18007018b  lea     r9, aCcsrmgrCreatep; "CCsrMgr::CreatePortSecurityDescriptor"
0x180070192  mov     r8d, ebx
0x180070195  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007019a  test    rdi, rdi
0x18007019d  jz      short loc_1800701AC
0x18007019f  mov     rcx, rdi; void *
0x1800701a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800701a7  jmp     short loc_1800701AC
0x1800701a9  mov     [r15], rdi
0x1800701ac  mov     rcx, [rbp+57h+var_60]; Sid
0x1800701b0  test    rcx, rcx
0x1800701b3  jz      short loc_1800701BB
0x1800701b5  call    cs:__imp_RtlFreeSid
0x1800701bb  mov     eax, ebx
0x1800701bd  mov     rcx, [rbp+57h+var_50]
0x1800701c1  xor     rcx, rsp; StackCookie
0x1800701c4  call    __security_check_cookie
0x1800701c9  add     rsp, 88h
0x1800701d0  pop     r15
0x1800701d2  pop     r14
0x1800701d4  pop     r13
0x1800701d6  pop     r12
0x1800701d8  pop     rdi
0x1800701d9  pop     rsi
0x1800701da  pop     rbx
0x1800701db  pop     rbp
0x1800701dc  retn
```
