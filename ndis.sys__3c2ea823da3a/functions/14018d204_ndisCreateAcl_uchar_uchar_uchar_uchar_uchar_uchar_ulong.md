# ndisCreateAcl(uchar,uchar,uchar,uchar,uchar,uchar,ulong)

- ea: `0x14018d204`
- end: `0x14018d506`
- name: `?ndisCreateAcl@@YAPEAU_ACL@@EEEEEEK@Z`
- size: `770`
- prototype: `struct _ACL *__fastcall(unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int8, char, ACCESS_MASK AccessMask)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14018b240`

## callees

- `0x1400e6160`
- `0x14018d204`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14018d4b3`
- `ntoskrnl!DbgPrint` at `0x14018d4b3`
- `ntoskrnl!RtlInitializeSid` at `0x14018d2f0`
- `ntoskrnl!RtlInitializeSid` at `0x14018d2f0`
- `ntoskrnl!RtlLengthSid` at `0x14018d242`
- `ntoskrnl!RtlLengthSid` at `0x14018d261`
- `ntoskrnl!RtlLengthSid` at `0x14018d280`
- `ntoskrnl!RtlLengthSid` at `0x14018d29f`
- `ntoskrnl!RtlLengthSid` at `0x14018d315`
- `ntoskrnl!RtlLengthSid` at `0x14018d34b`
- `ntoskrnl!RtlLengthSid` at `0x14018d242`
- `ntoskrnl!RtlLengthSid` at `0x14018d261`
- `ntoskrnl!RtlLengthSid` at `0x14018d280`
- `ntoskrnl!RtlLengthSid` at `0x14018d29f`
- `ntoskrnl!RtlLengthSid` at `0x14018d315`
- `ntoskrnl!RtlLengthSid` at `0x14018d34b`
- `ntoskrnl!SeExports` at `0x14018d222`
- `ntoskrnl!SeExports` at `0x14018d250`
- `ntoskrnl!SeExports` at `0x14018d26f`
- `ntoskrnl!SeExports` at `0x14018d28e`
- `ntoskrnl!SeExports` at `0x14018d33a`
- `ntoskrnl!SeExports` at `0x14018d3a5`
- `ntoskrnl!SeExports` at `0x14018d3d8`
- `ntoskrnl!SeExports` at `0x14018d406`
- `ntoskrnl!SeExports` at `0x14018d430`
- `ntoskrnl!SeExports` at `0x14018d47b`
- `ntoskrnl!RtlCreateAcl` at `0x14018d389`
- `ntoskrnl!RtlCreateAcl` at `0x14018d389`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d3c4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d3f2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d420`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d44a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d466`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d49a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d3c4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d3f2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d420`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d44a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d466`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018d49a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d4c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d4da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d4c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d4da`
- `ntoskrnl!ExAllocatePool2` at `0x14018d2cd`
- `ntoskrnl!ExAllocatePool2` at `0x14018d369`
- `ntoskrnl!ExAllocatePool2` at `0x14018d2cd`
- `ntoskrnl!ExAllocatePool2` at `0x14018d369`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14018d2b5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14018d2b5`

## string_xrefs

- `0x14018d399`: `RtlCreateAcl failed, Status %lx.\n`
- `0x14018d4aa`: `RtlAddAccessAllowedAce failed, Status %lx.\n`

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
0x14018d204  push    rbx
0x14018d206  push    rbp
0x14018d207  push    rsi
0x14018d208  push    rdi
0x14018d209  push    r13
0x14018d20b  push    r14
0x14018d20d  push    r15
0x14018d20f  sub     rsp, 30h
0x14018d213  mov     rax, cs:__security_cookie
0x14018d21a  xor     rax, rsp
0x14018d21d  mov     [rsp+68h+var_40], rax
0x14018d222  mov     rax, cs:__imp_SeExports
0x14018d229  xor     r14d, r14d
0x14018d22c  mov     dword ptr [rsp+68h+IdentifierAuthority.Value], r14d
0x14018d231  mov     word ptr [rsp+68h+IdentifierAuthority.Value+4], 500h
0x14018d238  mov     rcx, [rax]
0x14018d23b  mov     rcx, [rcx+110h]; Sid
0x14018d242  call    cs:__imp_RtlLengthSid
0x14018d249  nop     dword ptr [rax+rax+00h]
0x14018d24e  mov     ebx, eax
0x14018d250  mov     rax, cs:__imp_SeExports
0x14018d257  mov     rcx, [rax]
0x14018d25a  mov     rcx, [rcx+108h]; Sid
0x14018d261  call    cs:__imp_RtlLengthSid
0x14018d268  nop     dword ptr [rax+rax+00h]
0x14018d26d  mov     esi, eax
0x14018d26f  mov     rax, cs:__imp_SeExports
0x14018d276  mov     rcx, [rax]
0x14018d279  mov     rcx, [rcx+180h]; Sid
0x14018d280  call    cs:__imp_RtlLengthSid
0x14018d287  nop     dword ptr [rax+rax+00h]
0x14018d28c  mov     ebp, eax
0x14018d28e  mov     rax, cs:__imp_SeExports
0x14018d295  mov     rcx, [rax]
0x14018d298  mov     rcx, [rcx+188h]; Sid
0x14018d29f  call    cs:__imp_RtlLengthSid
0x14018d2a6  nop     dword ptr [rax+rax+00h]
0x14018d2ab  lea     r13d, [r14+2]
0x14018d2af  mov     r15d, eax
0x14018d2b2  mov     ecx, r13d; SubAuthorityCount
0x14018d2b5  call    cs:__imp_RtlLengthRequiredSid
0x14018d2bc  nop     dword ptr [rax+rax+00h]
0x14018d2c1  mov     edx, eax
0x14018d2c3  lea     ecx, [r14+40h]
0x14018d2c7  mov     r8d, 7363444Eh
0x14018d2cd  call    cs:__imp_ExAllocatePool2
0x14018d2d4  nop     dword ptr [rax+rax+00h]
0x14018d2d9  mov     rdi, rax
0x14018d2dc  test    rax, rax
0x14018d2df  jz      loc_14018D4E6
0x14018d2e5  mov     r8b, r13b; SubAuthorityCount
0x14018d2e8  lea     rdx, [rsp+68h+IdentifierAuthority]; IdentifierAuthority
0x14018d2ed  mov     rcx, rax; Sid
0x14018d2f0  call    cs:__imp_RtlInitializeSid
0x14018d2f7  nop     dword ptr [rax+rax+00h]
0x14018d2fc  test    eax, eax
0x14018d2fe  jnz     loc_14018D4D5
0x14018d304  mov     rcx, rdi; Sid
0x14018d307  mov     dword ptr [rdi+8], 20h ; ' '
0x14018d30e  mov     dword ptr [rdi+0Ch], 22Ch
0x14018d315  call    cs:__imp_RtlLengthSid
0x14018d31c  nop     dword ptr [rax+rax+00h]
0x14018d321  add     eax, ebx
0x14018d323  add     esi, 50h ; 'P'
0x14018d326  add     eax, r15d
0x14018d329  add     eax, ebp
0x14018d32b  mov     bpl, [rsp+68h+arg_28]
0x14018d333  add     esi, eax
0x14018d335  test    bpl, bpl
0x14018d338  jz      short loc_14018D35C
0x14018d33a  mov     rax, cs:__imp_SeExports
0x14018d341  mov     rcx, [rax]
0x14018d344  mov     rcx, [rcx+118h]; Sid
0x14018d34b  call    cs:__imp_RtlLengthSid
0x14018d352  nop     dword ptr [rax+rax+00h]
0x14018d357  add     esi, 10h
0x14018d35a  add     esi, eax
0x14018d35c  mov     edx, esi
0x14018d35e  mov     ecx, 100h
0x14018d363  mov     r8d, 6573444Eh
0x14018d369  call    cs:__imp_ExAllocatePool2
0x14018d370  nop     dword ptr [rax+rax+00h]
0x14018d375  mov     rbx, rax
0x14018d378  test    rax, rax
0x14018d37b  jz      loc_14018D4D5
0x14018d381  mov     r8d, r13d; AclRevision
0x14018d384  mov     edx, esi; AclLength
0x14018d386  mov     rcx, rax; Acl
0x14018d389  call    cs:__imp_RtlCreateAcl
0x14018d390  nop     dword ptr [rax+rax+00h]
0x14018d395  test    eax, eax
0x14018d397  jns     short loc_14018D3A5
0x14018d399  lea     rcx, aRtlcreateaclFa; "RtlCreateAcl failed, Status %lx.\n"
0x14018d3a0  jmp     loc_14018D4B1
0x14018d3a5  mov     rax, cs:__imp_SeExports
0x14018d3ac  mov     esi, 1FFFFFh
0x14018d3b1  mov     r8d, esi; AccessMask
0x14018d3b4  mov     edx, r13d; AceRevision
0x14018d3b7  mov     rcx, rbx; Acl
0x14018d3ba  mov     r9, [rax]
0x14018d3bd  mov     r9, [r9+110h]; Sid
0x14018d3c4  call    cs:__imp_RtlAddAccessAllowedAce
0x14018d3cb  nop     dword ptr [rax+rax+00h]
0x14018d3d0  test    eax, eax
0x14018d3d2  js      loc_14018D4AA
0x14018d3d8  mov     rax, cs:__imp_SeExports
0x14018d3df  mov     r8d, esi; AccessMask
0x14018d3e2  mov     edx, r13d; AceRevision
0x14018d3e5  mov     rcx, rbx; Acl
0x14018d3e8  mov     r9, [rax]
0x14018d3eb  mov     r9, [r9+108h]; Sid
0x14018d3f2  call    cs:__imp_RtlAddAccessAllowedAce
0x14018d3f9  nop     dword ptr [rax+rax+00h]
0x14018d3fe  test    eax, eax
0x14018d400  js      loc_14018D4AA
0x14018d406  mov     rax, cs:__imp_SeExports
0x14018d40d  mov     r8d, esi; AccessMask
0x14018d410  mov     edx, r13d; AceRevision
0x14018d413  mov     rcx, rbx; Acl
0x14018d416  mov     r9, [rax]
0x14018d419  mov     r9, [r9+180h]; Sid
0x14018d420  call    cs:__imp_RtlAddAccessAllowedAce
0x14018d427  nop     dword ptr [rax+rax+00h]
0x14018d42c  test    eax, eax
0x14018d42e  js      short loc_14018D4AA
0x14018d430  mov     rax, cs:__imp_SeExports
0x14018d437  mov     r8d, esi; AccessMask
0x14018d43a  mov     edx, r13d; AceRevision
0x14018d43d  mov     rcx, rbx; Acl
0x14018d440  mov     r9, [rax]
0x14018d443  mov     r9, [r9+188h]; Sid
0x14018d44a  call    cs:__imp_RtlAddAccessAllowedAce
0x14018d451  nop     dword ptr [rax+rax+00h]
0x14018d456  test    eax, eax
0x14018d458  js      short loc_14018D4AA
0x14018d45a  mov     r9, rdi; Sid
0x14018d45d  mov     r8d, esi; AccessMask
0x14018d460  mov     edx, r13d; AceRevision
0x14018d463  mov     rcx, rbx; Acl
0x14018d466  call    cs:__imp_RtlAddAccessAllowedAce
0x14018d46d  nop     dword ptr [rax+rax+00h]
0x14018d472  test    eax, eax
0x14018d474  js      short loc_14018D4AA
0x14018d476  test    bpl, bpl
0x14018d479  jz      short loc_14018D4D2
0x14018d47b  mov     rax, cs:__imp_SeExports
0x14018d482  mov     edx, r13d; AceRevision
0x14018d485  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14018d48d  mov     rcx, rbx; Acl
0x14018d490  mov     r9, [rax]
0x14018d493  mov     r9, [r9+118h]; Sid
0x14018d49a  call    cs:__imp_RtlAddAccessAllowedAce
0x14018d4a1  nop     dword ptr [rax+rax+00h]
0x14018d4a6  test    eax, eax
0x14018d4a8  jns     short loc_14018D4D2
0x14018d4aa  lea     rcx, aRtladdaccessal; "RtlAddAccessAllowedAce failed, Status %"...
0x14018d4b1  mov     edx, eax
0x14018d4b3  call    cs:__imp_DbgPrint
0x14018d4ba  nop     dword ptr [rax+rax+00h]
0x14018d4bf  xor     edx, edx; Tag
0x14018d4c1  mov     rcx, rbx; P
0x14018d4c4  call    cs:__imp_ExFreePoolWithTag
0x14018d4cb  nop     dword ptr [rax+rax+00h]
0x14018d4d0  jmp     short loc_14018D4D5
0x14018d4d2  mov     r14, rbx
0x14018d4d5  xor     edx, edx; Tag
0x14018d4d7  mov     rcx, rdi; P
0x14018d4da  call    cs:__imp_ExFreePoolWithTag
0x14018d4e1  nop     dword ptr [rax+rax+00h]
0x14018d4e6  mov     rax, r14
0x14018d4e9  mov     rcx, [rsp+68h+var_40]
0x14018d4ee  xor     rcx, rsp; StackCookie
0x14018d4f1  call    __security_check_cookie
0x14018d4f6  add     rsp, 30h
0x14018d4fa  pop     r15
0x14018d4fc  pop     r14
0x14018d4fe  pop     r13
0x14018d500  pop     rdi
0x14018d501  pop     rsi
0x14018d502  pop     rbp
0x14018d503  pop     rbx
0x14018d504  retn
```
