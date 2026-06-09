# LuafvBuildSecurityDescriptor

- ea: `0x140017140`
- end: `0x140017271`
- name: `LuafvBuildSecurityDescriptor`
- size: `305`
- prototype: `__int64 __fastcall(__int64, __int64, void *, struct _ACL **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017360`
- `0x14001758c`

## callees

- `0x140017140`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400171a0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400171a0`
- `ntoskrnl!RtlCreateAcl` at `0x1400171c5`
- `ntoskrnl!RtlCreateAcl` at `0x1400171c5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001721e`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001721e`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140017239`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140017239`
- `ntoskrnl!RtlLengthSid` at `0x140017166`
- `ntoskrnl!RtlLengthSid` at `0x140017166`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400171fa`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400171fa`

## pseudocode

```c
__int64 __fastcall LuafvBuildSecurityDescriptor(__int64 a1, __int64 a2, void *a3, struct _ACL **a4)
{
  ULONG v4; // esi
  __int64 i; // rbx
  ULONG v9; // eax
  __int64 v10; // r8
  struct _ACL *Pool; // rax
  struct _ACL *v12; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  unsigned int v14; // esi

  v4 = 0;
  for ( i = 0; i != 3; ++i )
  {
    v9 = RtlLengthSid(*(PSID *)(a1 + 16 * i));
    v4 += v9 + 12;
  }
  LOBYTE(v10) = 4;
  Pool = (struct _ACL *)LuafvAllocatePool(1, v4 + 48, v10);
  v12 = Pool;
  if ( Pool )
  {
    SecurityDescriptor = RtlCreateSecurityDescriptor(Pool, 1u);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlCreateAcl(v12 + 5, v4, 2u);
      if ( SecurityDescriptor >= 0 )
      {
        v14 = 0;
        while ( 1 )
        {
          SecurityDescriptor = RtlAddAccessAllowedAceEx(
                                 v12 + 5,
                                 2u,
                                 *(_DWORD *)(a1 + 16LL * v14 + 8),
                                 *(_DWORD *)(a1 + 16LL * v14 + 12),
                                 *(PSID *)(a1 + 16LL * v14));
          if ( SecurityDescriptor < 0 )
            break;
          if ( ++v14 >= 3 )
          {
            SecurityDescriptor = RtlSetDaclSecurityDescriptor(v12, 1u, v12 + 5, 0);
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v12, a3, 0);
              if ( SecurityDescriptor >= 0 )
              {
                *a4 = v12;
                return (unsigned int)SecurityDescriptor;
              }
            }
            break;
          }
        }
      }
    }
    LuafvFreePool(v12);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140017140  push    rbx
0x140017142  push    rbp
0x140017143  push    rsi
0x140017144  push    rdi
0x140017145  push    r12
0x140017147  push    r14
0x140017149  push    r15
0x14001714b  sub     rsp, 30h
0x14001714f  xor     esi, esi
0x140017151  mov     r15, r9
0x140017154  xor     ebx, ebx
0x140017156  mov     r12, r8
0x140017159  mov     r14, rcx
0x14001715c  mov     rcx, rbx
0x14001715f  add     rcx, rcx
0x140017162  mov     rcx, [r14+rcx*8]; Sid
0x140017166  call    cs:__imp_RtlLengthSid
0x14001716d  nop     dword ptr [rax+rax+00h]
0x140017172  add     esi, 0Ch
0x140017175  inc     rbx
0x140017178  add     esi, eax
0x14001717a  cmp     rbx, 3
0x14001717e  jnz     short loc_14001715C
0x140017180  lea     edx, [rsi+30h]
0x140017183  mov     r8b, 4
0x140017186  lea     ecx, [rbx-2]
0x140017189  call    LuafvAllocatePool
0x14001718e  mov     rdi, rax
0x140017191  test    rax, rax
0x140017194  jz      loc_14001725A
0x14001719a  lea     edx, [rbx-2]; Revision
0x14001719d  mov     rcx, rax; SecurityDescriptor
0x1400171a0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400171a7  nop     dword ptr [rax+rax+00h]
0x1400171ac  mov     ebx, eax
0x1400171ae  test    eax, eax
0x1400171b0  js      loc_140017250
0x1400171b6  lea     rbp, [rdi+28h]
0x1400171ba  mov     r8d, 2; AclRevision
0x1400171c0  mov     rcx, rbp; Acl
0x1400171c3  mov     edx, esi; AclLength
0x1400171c5  call    cs:__imp_RtlCreateAcl
0x1400171cc  nop     dword ptr [rax+rax+00h]
0x1400171d1  mov     ebx, eax
0x1400171d3  test    eax, eax
0x1400171d5  js      short loc_140017250
0x1400171d7  xor     esi, esi
0x1400171d9  mov     r8d, esi
0x1400171dc  mov     edx, 2; AceRevision
0x1400171e1  add     r8, r8
0x1400171e4  mov     rcx, rbp; Acl
0x1400171e7  mov     rax, [r14+r8*8]
0x1400171eb  mov     r9d, [r14+r8*8+0Ch]; AccessMask
0x1400171f0  mov     r8d, [r14+r8*8+8]; AceFlags
0x1400171f5  mov     [rsp+68h+Sid], rax; Sid
0x1400171fa  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140017201  nop     dword ptr [rax+rax+00h]
0x140017206  mov     ebx, eax
0x140017208  test    eax, eax
0x14001720a  js      short loc_140017250
0x14001720c  inc     esi
0x14001720e  cmp     esi, 3
0x140017211  jb      short loc_1400171D9
0x140017213  xor     r9d, r9d; DaclDefaulted
0x140017216  mov     r8, rbp; Dacl
0x140017219  mov     dl, 1; DaclPresent
0x14001721b  mov     rcx, rdi; SecurityDescriptor
0x14001721e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140017225  nop     dword ptr [rax+rax+00h]
0x14001722a  mov     ebx, eax
0x14001722c  test    eax, eax
0x14001722e  js      short loc_140017250
0x140017230  xor     r8d, r8d; OwnerDefaulted
0x140017233  mov     rdx, r12; Owner
0x140017236  mov     rcx, rdi; SecurityDescriptor
0x140017239  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140017240  nop     dword ptr [rax+rax+00h]
0x140017245  mov     ebx, eax
0x140017247  test    eax, eax
0x140017249  js      short loc_140017250
0x14001724b  mov     [r15], rdi
0x14001724e  jmp     short loc_14001725F
0x140017250  mov     rcx, rdi
0x140017253  call    LuafvFreePool
0x140017258  jmp     short loc_14001725F
0x14001725a  mov     ebx, 0C000009Ah
0x14001725f  mov     eax, ebx
0x140017261  add     rsp, 30h
0x140017265  pop     r15
0x140017267  pop     r14
0x140017269  pop     r12
0x14001726b  pop     rdi
0x14001726c  pop     rsi
0x14001726d  pop     rbp
0x14001726e  pop     rbx
0x14001726f  retn
```
