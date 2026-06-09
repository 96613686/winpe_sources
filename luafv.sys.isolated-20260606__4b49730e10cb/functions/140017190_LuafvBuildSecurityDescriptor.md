# LuafvBuildSecurityDescriptor

- ea: `0x140017190`
- end: `0x1400172c1`
- name: `LuafvBuildSecurityDescriptor`
- size: `305`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400173b0`
- `0x1400175dc`

## callees

- `0x140017190`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400171f0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400171f0`
- `ntoskrnl!RtlCreateAcl` at `0x140017215`
- `ntoskrnl!RtlCreateAcl` at `0x140017215`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001726e`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001726e`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140017289`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140017289`
- `ntoskrnl!RtlLengthSid` at `0x1400171b6`
- `ntoskrnl!RtlLengthSid` at `0x1400171b6`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001724a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001724a`

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
0x140017190  push    rbx
0x140017192  push    rbp
0x140017193  push    rsi
0x140017194  push    rdi
0x140017195  push    r12
0x140017197  push    r14
0x140017199  push    r15
0x14001719b  sub     rsp, 30h
0x14001719f  xor     esi, esi
0x1400171a1  mov     r15, r9
0x1400171a4  xor     ebx, ebx
0x1400171a6  mov     r12, r8
0x1400171a9  mov     r14, rcx
0x1400171ac  mov     rcx, rbx
0x1400171af  add     rcx, rcx
0x1400171b2  mov     rcx, [r14+rcx*8]; Sid
0x1400171b6  call    cs:__imp_RtlLengthSid
0x1400171bd  nop     dword ptr [rax+rax+00h]
0x1400171c2  add     esi, 0Ch
0x1400171c5  inc     rbx
0x1400171c8  add     esi, eax
0x1400171ca  cmp     rbx, 3
0x1400171ce  jnz     short loc_1400171AC
0x1400171d0  lea     edx, [rsi+30h]
0x1400171d3  mov     r8b, 4
0x1400171d6  lea     ecx, [rbx-2]
0x1400171d9  call    LuafvAllocatePool
0x1400171de  mov     rdi, rax
0x1400171e1  test    rax, rax
0x1400171e4  jz      loc_1400172AA
0x1400171ea  lea     edx, [rbx-2]; Revision
0x1400171ed  mov     rcx, rax; SecurityDescriptor
0x1400171f0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400171f7  nop     dword ptr [rax+rax+00h]
0x1400171fc  mov     ebx, eax
0x1400171fe  test    eax, eax
0x140017200  js      loc_1400172A0
0x140017206  lea     rbp, [rdi+28h]
0x14001720a  mov     r8d, 2; AclRevision
0x140017210  mov     rcx, rbp; Acl
0x140017213  mov     edx, esi; AclLength
0x140017215  call    cs:__imp_RtlCreateAcl
0x14001721c  nop     dword ptr [rax+rax+00h]
0x140017221  mov     ebx, eax
0x140017223  test    eax, eax
0x140017225  js      short loc_1400172A0
0x140017227  xor     esi, esi
0x140017229  mov     r8d, esi
0x14001722c  mov     edx, 2; AceRevision
0x140017231  add     r8, r8
0x140017234  mov     rcx, rbp; Acl
0x140017237  mov     rax, [r14+r8*8]
0x14001723b  mov     r9d, [r14+r8*8+0Ch]; AccessMask
0x140017240  mov     r8d, [r14+r8*8+8]; AceFlags
0x140017245  mov     [rsp+68h+Sid], rax; Sid
0x14001724a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140017251  nop     dword ptr [rax+rax+00h]
0x140017256  mov     ebx, eax
0x140017258  test    eax, eax
0x14001725a  js      short loc_1400172A0
0x14001725c  inc     esi
0x14001725e  cmp     esi, 3
0x140017261  jb      short loc_140017229
0x140017263  xor     r9d, r9d; DaclDefaulted
0x140017266  mov     r8, rbp; Dacl
0x140017269  mov     dl, 1; DaclPresent
0x14001726b  mov     rcx, rdi; SecurityDescriptor
0x14001726e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140017275  nop     dword ptr [rax+rax+00h]
0x14001727a  mov     ebx, eax
0x14001727c  test    eax, eax
0x14001727e  js      short loc_1400172A0
0x140017280  xor     r8d, r8d; OwnerDefaulted
0x140017283  mov     rdx, r12; Owner
0x140017286  mov     rcx, rdi; SecurityDescriptor
0x140017289  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140017290  nop     dword ptr [rax+rax+00h]
0x140017295  mov     ebx, eax
0x140017297  test    eax, eax
0x140017299  js      short loc_1400172A0
0x14001729b  mov     [r15], rdi
0x14001729e  jmp     short loc_1400172AF
0x1400172a0  mov     rcx, rdi
0x1400172a3  call    LuafvFreePool
0x1400172a8  jmp     short loc_1400172AF
0x1400172aa  mov     ebx, 0C000009Ah
0x1400172af  mov     eax, ebx
0x1400172b1  add     rsp, 30h
0x1400172b5  pop     r15
0x1400172b7  pop     r14
0x1400172b9  pop     r12
0x1400172bb  pop     rdi
0x1400172bc  pop     rsi
0x1400172bd  pop     rbp
0x1400172be  pop     rbx
0x1400172bf  retn
```
