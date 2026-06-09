# ndisCreateAcl(uchar,uchar,uchar,uchar,uchar,uchar,ulong)

- ea: `0x140193214`
- end: `0x140193516`
- name: `?ndisCreateAcl@@YAPEAU_ACL@@EEEEEEK@Z`
- size: `770`
- prototype: `struct _ACL *__fastcall(unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, char, ACCESS_MASK AccessMask)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140191240`

## callees

- `0x1400eb380`
- `0x140193214`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1401934c3`
- `ntoskrnl!DbgPrint` at `0x1401934c3`
- `ntoskrnl!RtlInitializeSid` at `0x140193300`
- `ntoskrnl!RtlInitializeSid` at `0x140193300`
- `ntoskrnl!RtlLengthSid` at `0x140193252`
- `ntoskrnl!RtlLengthSid` at `0x140193271`
- `ntoskrnl!RtlLengthSid` at `0x140193290`
- `ntoskrnl!RtlLengthSid` at `0x1401932af`
- `ntoskrnl!RtlLengthSid` at `0x140193325`
- `ntoskrnl!RtlLengthSid` at `0x14019335b`
- `ntoskrnl!RtlLengthSid` at `0x140193252`
- `ntoskrnl!RtlLengthSid` at `0x140193271`
- `ntoskrnl!RtlLengthSid` at `0x140193290`
- `ntoskrnl!RtlLengthSid` at `0x1401932af`
- `ntoskrnl!RtlLengthSid` at `0x140193325`
- `ntoskrnl!RtlLengthSid` at `0x14019335b`
- `ntoskrnl!SeExports` at `0x140193232`
- `ntoskrnl!SeExports` at `0x140193260`
- `ntoskrnl!SeExports` at `0x14019327f`
- `ntoskrnl!SeExports` at `0x14019329e`
- `ntoskrnl!SeExports` at `0x14019334a`
- `ntoskrnl!SeExports` at `0x1401933b5`
- `ntoskrnl!SeExports` at `0x1401933e8`
- `ntoskrnl!SeExports` at `0x140193416`
- `ntoskrnl!SeExports` at `0x140193440`
- `ntoskrnl!SeExports` at `0x14019348b`
- `ntoskrnl!RtlCreateAcl` at `0x140193399`
- `ntoskrnl!RtlCreateAcl` at `0x140193399`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401933d4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140193402`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140193430`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14019345a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140193476`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401934aa`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401933d4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140193402`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140193430`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14019345a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140193476`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1401934aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401934d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401934ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401934d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401934ea`
- `ntoskrnl!ExAllocatePool2` at `0x1401932dd`
- `ntoskrnl!ExAllocatePool2` at `0x140193379`
- `ntoskrnl!ExAllocatePool2` at `0x1401932dd`
- `ntoskrnl!ExAllocatePool2` at `0x140193379`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401932c5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1401932c5`

## string_xrefs

- `0x1401933a9`: `RtlCreateAcl failed, Status %lx.\n`
- `0x1401934ba`: `RtlAddAccessAllowedAce failed, Status %lx.\n`

## pseudocode

```c
struct _ACL *__fastcall ndisCreateAcl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        char a6,
        ACCESS_MASK AccessMask)
{
  struct _ACL *v7; // r14
  ULONG v8; // ebx
  ULONG v9; // esi
  ULONG v10; // ebp
  ULONG v11; // r15d
  ULONG v12; // eax
  _DWORD *Pool2; // rax
  _DWORD *v14; // rdi
  ULONG v15; // esi
  struct _ACL *v16; // rax
  struct _ACL *v17; // rbx
  NTSTATUS Acl; // eax
  NTSTATUS v19; // eax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-48h] BYREF

  v7 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v8 = RtlLengthSid(SeExports->SeAliasAdminsSid);
  v9 = RtlLengthSid(SeExports->SeLocalSystemSid);
  v10 = RtlLengthSid(SeExports->SeLocalServiceSid);
  v11 = RtlLengthSid(SeExports->SeNetworkServiceSid);
  v12 = RtlLengthRequiredSid(2u);
  Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 1935885390);
  v14 = Pool2;
  if ( Pool2 )
  {
    if ( RtlInitializeSid(Pool2, &IdentifierAuthority, 2u) )
      goto LABEL_18;
    v14[2] = 32;
    v14[3] = 556;
    v15 = v10 + v11 + v8 + RtlLengthSid(v14) + v9 + 80;
    if ( a6 )
      v15 += RtlLengthSid(SeExports->SeAliasUsersSid) + 16;
    v16 = (struct _ACL *)ExAllocatePool2(256, v15, 1702052942);
    v17 = v16;
    if ( !v16 )
      goto LABEL_18;
    Acl = RtlCreateAcl(v16, v15, 2u);
    if ( Acl >= 0 )
    {
      v19 = RtlAddAccessAllowedAce(v17, 2u, 0x1FFFFFu, SeExports->SeAliasAdminsSid);
      if ( v19 >= 0 )
      {
        v19 = RtlAddAccessAllowedAce(v17, 2u, 0x1FFFFFu, SeExports->SeLocalSystemSid);
        if ( v19 >= 0 )
        {
          v19 = RtlAddAccessAllowedAce(v17, 2u, 0x1FFFFFu, SeExports->SeLocalServiceSid);
          if ( v19 >= 0 )
          {
            v19 = RtlAddAccessAllowedAce(v17, 2u, 0x1FFFFFu, SeExports->SeNetworkServiceSid);
            if ( v19 >= 0 )
            {
              v19 = RtlAddAccessAllowedAce(v17, 2u, 0x1FFFFFu, v14);
              if ( v19 >= 0 )
              {
                if ( !a6 || (v19 = RtlAddAccessAllowedAce(v17, 2u, AccessMask, SeExports->SeAliasUsersSid), v19 >= 0) )
                {
                  v7 = v17;
                  goto LABEL_18;
                }
              }
            }
          }
        }
      }
      DbgPrint("RtlAddAccessAllowedAce failed, Status %lx.\n", (unsigned int)v19);
    }
    else
    {
      DbgPrint("RtlCreateAcl failed, Status %lx.\n", (unsigned int)Acl);
    }
    ExFreePoolWithTag(v17, 0);
LABEL_18:
    ExFreePoolWithTag(v14, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x140193214  push    rbx
0x140193216  push    rbp
0x140193217  push    rsi
0x140193218  push    rdi
0x140193219  push    r13
0x14019321b  push    r14
0x14019321d  push    r15
0x14019321f  sub     rsp, 30h
0x140193223  mov     rax, cs:__security_cookie
0x14019322a  xor     rax, rsp
0x14019322d  mov     [rsp+68h+var_40], rax
0x140193232  mov     rax, cs:__imp_SeExports
0x140193239  xor     r14d, r14d
0x14019323c  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], r14d
0x140193241  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x140193248  mov     rcx, [rax]
0x14019324b  mov     rcx, [rcx+110h]; Sid
0x140193252  call    cs:__imp_RtlLengthSid
0x140193259  nop     dword ptr [rax+rax+00h]
0x14019325e  mov     ebx, eax
0x140193260  mov     rax, cs:__imp_SeExports
0x140193267  mov     rcx, [rax]
0x14019326a  mov     rcx, [rcx+108h]; Sid
0x140193271  call    cs:__imp_RtlLengthSid
0x140193278  nop     dword ptr [rax+rax+00h]
0x14019327d  mov     esi, eax
0x14019327f  mov     rax, cs:__imp_SeExports
0x140193286  mov     rcx, [rax]
0x140193289  mov     rcx, [rcx+180h]; Sid
0x140193290  call    cs:__imp_RtlLengthSid
0x140193297  nop     dword ptr [rax+rax+00h]
0x14019329c  mov     ebp, eax
0x14019329e  mov     rax, cs:__imp_SeExports
0x1401932a5  mov     rcx, [rax]
0x1401932a8  mov     rcx, [rcx+188h]; Sid
0x1401932af  call    cs:__imp_RtlLengthSid
0x1401932b6  nop     dword ptr [rax+rax+00h]
0x1401932bb  lea     r13d, [r14+2]
0x1401932bf  mov     r15d, eax
0x1401932c2  mov     ecx, r13d; SubAuthorityCount
0x1401932c5  call    cs:__imp_RtlLengthRequiredSid
0x1401932cc  nop     dword ptr [rax+rax+00h]
0x1401932d1  mov     edx, eax
0x1401932d3  lea     ecx, [r14+40h]
0x1401932d7  mov     r8d, 7363444Eh
0x1401932dd  call    cs:__imp_ExAllocatePool2
0x1401932e4  nop     dword ptr [rax+rax+00h]
0x1401932e9  mov     rdi, rax
0x1401932ec  test    rax, rax
0x1401932ef  jz      loc_1401934F6
0x1401932f5  mov     r8b, r13b; SubAuthorityCount
0x1401932f8  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x1401932fd  mov     rcx, rax; Sid
0x140193300  call    cs:__imp_RtlInitializeSid
0x140193307  nop     dword ptr [rax+rax+00h]
0x14019330c  test    eax, eax
0x14019330e  jnz     loc_1401934E5
0x140193314  mov     rcx, rdi; Sid
0x140193317  mov     dword ptr [rdi+8], 20h ; ' '
0x14019331e  mov     dword ptr [rdi+0Ch], 22Ch
0x140193325  call    cs:__imp_RtlLengthSid
0x14019332c  nop     dword ptr [rax+rax+00h]
0x140193331  add     eax, ebx
0x140193333  add     esi, 50h ; 'P'
0x140193336  add     eax, r15d
0x140193339  add     eax, ebp
0x14019333b  mov     bpl, [rsp+68h+arg_28]
0x140193343  add     esi, eax
0x140193345  test    bpl, bpl
0x140193348  jz      short loc_14019336C
0x14019334a  mov     rax, cs:__imp_SeExports
0x140193351  mov     rcx, [rax]
0x140193354  mov     rcx, [rcx+118h]; Sid
0x14019335b  call    cs:__imp_RtlLengthSid
0x140193362  nop     dword ptr [rax+rax+00h]
0x140193367  add     esi, 10h
0x14019336a  add     esi, eax
0x14019336c  mov     edx, esi
0x14019336e  mov     ecx, 100h
0x140193373  mov     r8d, 6573444Eh
0x140193379  call    cs:__imp_ExAllocatePool2
0x140193380  nop     dword ptr [rax+rax+00h]
0x140193385  mov     rbx, rax
0x140193388  test    rax, rax
0x14019338b  jz      loc_1401934E5
0x140193391  mov     r8d, r13d; AclRevision
0x140193394  mov     edx, esi; AclLength
0x140193396  mov     rcx, rax; Acl
0x140193399  call    cs:__imp_RtlCreateAcl
0x1401933a0  nop     dword ptr [rax+rax+00h]
0x1401933a5  test    eax, eax
0x1401933a7  jns     short loc_1401933B5
0x1401933a9  lea     rcx, aRtlcreateaclFa; "RtlCreateAcl failed, Status %lx.\n"
0x1401933b0  jmp     loc_1401934C1
0x1401933b5  mov     rax, cs:__imp_SeExports
0x1401933bc  mov     esi, 1FFFFFh
0x1401933c1  mov     r8d, esi; AccessMask
0x1401933c4  mov     edx, r13d; AceRevision
0x1401933c7  mov     rcx, rbx; Acl
0x1401933ca  mov     r9, [rax]
0x1401933cd  mov     r9, [r9+110h]; Sid
0x1401933d4  call    cs:__imp_RtlAddAccessAllowedAce
0x1401933db  nop     dword ptr [rax+rax+00h]
0x1401933e0  test    eax, eax
0x1401933e2  js      loc_1401934BA
0x1401933e8  mov     rax, cs:__imp_SeExports
0x1401933ef  mov     r8d, esi; AccessMask
0x1401933f2  mov     edx, r13d; AceRevision
0x1401933f5  mov     rcx, rbx; Acl
0x1401933f8  mov     r9, [rax]
0x1401933fb  mov     r9, [r9+108h]; Sid
0x140193402  call    cs:__imp_RtlAddAccessAllowedAce
0x140193409  nop     dword ptr [rax+rax+00h]
0x14019340e  test    eax, eax
0x140193410  js      loc_1401934BA
0x140193416  mov     rax, cs:__imp_SeExports
0x14019341d  mov     r8d, esi; AccessMask
0x140193420  mov     edx, r13d; AceRevision
0x140193423  mov     rcx, rbx; Acl
0x140193426  mov     r9, [rax]
0x140193429  mov     r9, [r9+180h]; Sid
0x140193430  call    cs:__imp_RtlAddAccessAllowedAce
0x140193437  nop     dword ptr [rax+rax+00h]
0x14019343c  test    eax, eax
0x14019343e  js      short loc_1401934BA
0x140193440  mov     rax, cs:__imp_SeExports
0x140193447  mov     r8d, esi; AccessMask
0x14019344a  mov     edx, r13d; AceRevision
0x14019344d  mov     rcx, rbx; Acl
0x140193450  mov     r9, [rax]
0x140193453  mov     r9, [r9+188h]; Sid
0x14019345a  call    cs:__imp_RtlAddAccessAllowedAce
0x140193461  nop     dword ptr [rax+rax+00h]
0x140193466  test    eax, eax
0x140193468  js      short loc_1401934BA
0x14019346a  mov     r9, rdi; Sid
0x14019346d  mov     r8d, esi; AccessMask
0x140193470  mov     edx, r13d; AceRevision
0x140193473  mov     rcx, rbx; Acl
0x140193476  call    cs:__imp_RtlAddAccessAllowedAce
0x14019347d  nop     dword ptr [rax+rax+00h]
0x140193482  test    eax, eax
0x140193484  js      short loc_1401934BA
0x140193486  test    bpl, bpl
0x140193489  jz      short loc_1401934E2
0x14019348b  mov     rax, cs:__imp_SeExports
0x140193492  mov     edx, r13d; AceRevision
0x140193495  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14019349d  mov     rcx, rbx; Acl
0x1401934a0  mov     r9, [rax]
0x1401934a3  mov     r9, [r9+118h]; Sid
0x1401934aa  call    cs:__imp_RtlAddAccessAllowedAce
0x1401934b1  nop     dword ptr [rax+rax+00h]
0x1401934b6  test    eax, eax
0x1401934b8  jns     short loc_1401934E2
0x1401934ba  lea     rcx, aRtladdaccessal; "RtlAddAccessAllowedAce failed, Status %"...
0x1401934c1  mov     edx, eax
0x1401934c3  call    cs:__imp_DbgPrint
0x1401934ca  nop     dword ptr [rax+rax+00h]
0x1401934cf  xor     edx, edx; Tag
0x1401934d1  mov     rcx, rbx; P
0x1401934d4  call    cs:__imp_ExFreePoolWithTag
0x1401934db  nop     dword ptr [rax+rax+00h]
0x1401934e0  jmp     short loc_1401934E5
0x1401934e2  mov     r14, rbx
0x1401934e5  xor     edx, edx; Tag
0x1401934e7  mov     rcx, rdi; P
0x1401934ea  call    cs:__imp_ExFreePoolWithTag
0x1401934f1  nop     dword ptr [rax+rax+00h]
0x1401934f6  mov     rax, r14
0x1401934f9  mov     rcx, [rsp+68h+var_40]
0x1401934fe  xor     rcx, rsp; StackCookie
0x140193501  call    __security_check_cookie
0x140193506  add     rsp, 30h
0x14019350a  pop     r15
0x14019350c  pop     r14
0x14019350e  pop     r13
0x140193510  pop     rdi
0x140193511  pop     rsi
0x140193512  pop     rbp
0x140193513  pop     rbx
0x140193514  retn
```
