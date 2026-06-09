# NetpCreateSecurityDescriptor

- ea: `0x18008d770`
- end: `0x18008daa2`
- name: `NetpCreateSecurityDescriptor`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180036f50`
- `0x18008daa8`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x18008d770`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18008d994`
- `ntdll!RtlCopySid` at `0x18008d994`
- `ntdll!RtlCreateAcl` at `0x18008d845`
- `ntdll!RtlCreateAcl` at `0x18008d87e`
- `ntdll!RtlCreateAcl` at `0x18008d845`
- `ntdll!RtlCreateAcl` at `0x18008d87e`
- `ntdll!RtlAddAce` at `0x18008d9c5`
- `ntdll!RtlAddAce` at `0x18008d9c5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008d9f0`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008d9f0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18008da14`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18008da14`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18008da38`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18008da38`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18008da59`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18008da59`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18008da7a`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18008da7a`
- `ntdll!RtlLengthSid` at `0x18008d7b6`
- `ntdll!RtlLengthSid` at `0x18008d908`
- `ntdll!RtlLengthSid` at `0x18008d97f`
- `ntdll!RtlLengthSid` at `0x18008d7b6`
- `ntdll!RtlLengthSid` at `0x18008d908`
- `ntdll!RtlLengthSid` at `0x18008d97f`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityDescriptor(__int64 a1, unsigned int a2, void *a3, void *a4, struct _ACL **a5)
{
  ULONG v5; // r12d
  __int64 v6; // rdi
  ULONG v7; // r14d
  unsigned int v8; // esi
  unsigned int i; // eax
  ULONG v11; // eax
  ULONG v12; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  struct _ACL *v16; // rax
  struct _ACL *v17; // rbp
  NTSTATUS SecurityDescriptor; // ebx
  char *v19; // rsi
  struct _ACL *v20; // r15
  struct _ACL *v21; // rdi
  unsigned int j; // r12d
  __int64 v23; // r14
  ULONG AceListLength; // r8d
  void *v25; // rdi
  ULONG v26; // eax
  NTSTATUS v27; // eax
  ULONG v28; // [rsp+30h] [rbp-58h]
  struct _ACL *Acl; // [rsp+38h] [rbp-50h]
  struct _ACL *v30; // [rsp+40h] [rbp-48h]

  v5 = 0;
  v6 = 8;
  v7 = 8;
  v8 = 0;
  for ( i = a2; v8 < i; i = a2 )
  {
    v11 = RtlLengthSid(**(PSID **)(a1 + 16LL * v8 + 8));
    if ( !*(_BYTE *)(a1 + 16LL * v8) || *(_BYTE *)(a1 + 16LL * v8) == 1 )
    {
      v12 = v11 + 8;
      v6 = v12 + (unsigned int)v6;
    }
    else
    {
      if ( *(_BYTE *)(a1 + 16LL * v8) != 2 )
        return 3221225485LL;
      v12 = v11 + 8;
      v7 += v12;
    }
    ++v8;
    if ( v5 > v12 )
      v12 = v5;
    v5 = v12;
  }
  v14 = v6 + 40;
  if ( (_DWORD)v6 == 8 )
    v14 = 40;
  v15 = v14 + v7;
  if ( v7 == 8 )
    v15 = v14;
  v16 = (struct _ACL *)NetpMemoryAllocate(v15);
  v17 = v16;
  if ( !v16 )
    return (unsigned int)-1073741801;
  v19 = 0;
  v20 = v16 + 5;
  if ( (_DWORD)v6 == 8 )
  {
    v21 = v16 + 5;
    SecurityDescriptor = -1073741811;
    v20 = 0;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(v16 + 5, v6, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v21 = (struct _ACL *)((char *)v20 + v6);
  }
  v30 = 0;
  if ( v7 == 8 )
  {
    v21 = 0;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(v21, v7, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v30 = v21;
  }
  v19 = (char *)NetpMemoryAllocate(v5);
  if ( !v19 )
  {
    SecurityDescriptor = -1073741801;
    goto LABEL_28;
  }
  for ( j = 0; j < a2; ++j )
  {
    v23 = 16LL * j;
    Acl = 0;
    AceListLength = RtlLengthSid(**(PSID **)(v23 + a1 + 8));
    switch ( *(_BYTE *)(v23 + a1) )
    {
      case 0:
        v25 = **(void ***)(v23 + a1 + 8);
        *v19 = 0;
        goto LABEL_39;
      case 1:
        v25 = **(void ***)(v23 + a1 + 8);
        *v19 = 1;
LABEL_39:
        Acl = v20;
        goto LABEL_40;
      case 2:
        Acl = v21;
        v25 = **(void ***)(v23 + a1 + 8);
        *v19 = 2;
LABEL_40:
        v19[1] = *(_BYTE *)(v23 + a1 + 1) | *(_BYTE *)(v23 + a1 + 2);
        *((_DWORD *)v19 + 1) = *(_DWORD *)(v23 + a1 + 4);
        v28 = AceListLength + 8;
        *((_WORD *)v19 + 1) = AceListLength + 8;
        v26 = RtlLengthSid(v25);
        v27 = RtlCopySid(v26, v19 + 8, v25);
        AceListLength = v28;
        SecurityDescriptor = v27;
        break;
    }
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    SecurityDescriptor = RtlAddAce(Acl, 2u, 0xFFFFFFFF, v19, AceListLength);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v21 = v30;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(v17, 1u);
  if ( SecurityDescriptor < 0
    || (SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v17, a3, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetGroupSecurityDescriptor(v17, a4, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(v17, 1u, v20, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetSaclSecurityDescriptor(v17, 0, v21, 0), SecurityDescriptor < 0) )
  {
LABEL_28:
    NetpMemoryFree(v17);
    if ( v19 )
      goto LABEL_29;
    return (unsigned int)SecurityDescriptor;
  }
  SecurityDescriptor = 0;
  *a5 = v17;
LABEL_29:
  NetpMemoryFree(v19);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x18008d770  mov     rax, rsp
0x18008d773  mov     [rax+8], rbx
0x18008d777  mov     [rax+20h], r9
0x18008d77b  mov     [rax+18h], r8
0x18008d77f  mov     [rax+10h], edx
0x18008d782  push    rbp
0x18008d783  push    rsi
0x18008d784  push    rdi
0x18008d785  push    r12
0x18008d787  push    r13
0x18008d789  push    r14
0x18008d78b  push    r15
0x18008d78d  sub     rsp, 50h
0x18008d791  mov     ebp, 8
0x18008d796  xor     r12d, r12d
0x18008d799  mov     edi, ebp
0x18008d79b  mov     r14d, ebp
0x18008d79e  xor     esi, esi
0x18008d7a0  mov     eax, edx
0x18008d7a2  mov     r13, rcx
0x18008d7a5  cmp     esi, eax
0x18008d7a7  jnb     short loc_18008D803
0x18008d7a9  mov     ebx, esi
0x18008d7ab  add     rbx, rbx
0x18008d7ae  mov     rcx, [r13+rbx*8+8]
0x18008d7b3  mov     rcx, [rcx]; Sid
0x18008d7b6  call    cs:__imp_RtlLengthSid
0x18008d7bd  nop     dword ptr [rax+rax+00h]
0x18008d7c2  movzx   edx, byte ptr [r13+rbx*8+0]
0x18008d7c8  test    edx, edx
0x18008d7ca  jz      short loc_18008D7E0
0x18008d7cc  sub     edx, 1
0x18008d7cf  jz      short loc_18008D7E0
0x18008d7d1  cmp     edx, 1
0x18008d7d4  jnz     short loc_18008D7F9
0x18008d7d6  lea     ecx, [rax+8]
0x18008d7d9  mov     eax, ecx
0x18008d7db  add     r14d, ecx
0x18008d7de  jmp     short loc_18008D7E4
0x18008d7e0  add     eax, ebp
0x18008d7e2  add     edi, eax
0x18008d7e4  inc     esi
0x18008d7e6  cmp     r12d, eax
0x18008d7e9  cmova   eax, r12d
0x18008d7ed  mov     r12d, eax
0x18008d7f0  mov     eax, [rsp+88h+arg_8]
0x18008d7f7  jmp     short loc_18008D7A5
0x18008d7f9  mov     eax, 0C000000Dh
0x18008d7fe  jmp     loc_18008D8C6
0x18008d803  mov     ecx, 28h ; '('
0x18008d808  lea     eax, [rdi+28h]
0x18008d80b  cmp     edi, ebp
0x18008d80d  cmovz   eax, ecx
0x18008d810  cmp     r14d, ebp
0x18008d813  lea     ecx, [rax+r14]
0x18008d817  cmovz   ecx, eax
0x18008d81a  call    NetpMemoryAllocate
0x18008d81f  mov     rbp, rax
0x18008d822  test    rax, rax
0x18008d825  jnz     short loc_18008D831
0x18008d827  mov     ebx, 0C0000017h
0x18008d82c  jmp     loc_18008D8C4
0x18008d831  xor     esi, esi
0x18008d833  lea     r15, [rax+28h]
0x18008d837  cmp     edi, 8
0x18008d83a  jz      short loc_18008D85C
0x18008d83c  lea     r8d, [rsi+2]; AclRevision
0x18008d840  mov     edx, edi; AclSize
0x18008d842  mov     rcx, r15; Acl
0x18008d845  call    cs:__imp_RtlCreateAcl
0x18008d84c  nop     dword ptr [rax+rax+00h]
0x18008d851  mov     ebx, eax
0x18008d853  test    eax, eax
0x18008d855  js      short loc_18008D8AF
0x18008d857  add     rdi, r15
0x18008d85a  jmp     short loc_18008D867
0x18008d85c  mov     rdi, r15
0x18008d85f  mov     ebx, 0C000000Dh
0x18008d864  xor     r15d, r15d
0x18008d867  mov     [rsp+88h+var_48], rsi
0x18008d86c  cmp     r14d, 8
0x18008d870  jz      short loc_18008D897
0x18008d872  mov     r8d, 2; AclRevision
0x18008d878  mov     edx, r14d; AclSize
0x18008d87b  mov     rcx, rdi; Acl
0x18008d87e  call    cs:__imp_RtlCreateAcl
0x18008d885  nop     dword ptr [rax+rax+00h]
0x18008d88a  mov     ebx, eax
0x18008d88c  test    eax, eax
0x18008d88e  js      short loc_18008D8AF
0x18008d890  mov     [rsp+88h+var_48], rdi
0x18008d895  jmp     short loc_18008D89A
0x18008d897  mov     rdi, rsi
0x18008d89a  mov     ecx, r12d
0x18008d89d  call    NetpMemoryAllocate
0x18008d8a2  mov     rsi, rax
0x18008d8a5  test    rax, rax
0x18008d8a8  jnz     short loc_18008D8DF
0x18008d8aa  mov     ebx, 0C0000017h
0x18008d8af  mov     rcx, rbp
0x18008d8b2  call    NetpMemoryFree
0x18008d8b7  test    rsi, rsi
0x18008d8ba  jz      short loc_18008D8C4
0x18008d8bc  mov     rcx, rsi
0x18008d8bf  call    NetpMemoryFree
0x18008d8c4  mov     eax, ebx
0x18008d8c6  mov     rbx, [rsp+88h+arg_0]
0x18008d8ce  add     rsp, 50h
0x18008d8d2  pop     r15
0x18008d8d4  pop     r14
0x18008d8d6  pop     r13
0x18008d8d8  pop     r12
0x18008d8da  pop     rdi
0x18008d8db  pop     rsi
0x18008d8dc  pop     rbp
0x18008d8dd  retn
0x18008d8df  xor     r12d, r12d
0x18008d8e2  cmp     r12d, [rsp+88h+arg_8]
0x18008d8ea  jnb     loc_18008D9E8
0x18008d8f0  mov     r14d, r12d
0x18008d8f3  shl     r14, 4
0x18008d8f7  mov     [rsp+88h+Acl], 0
0x18008d900  mov     rcx, [r14+r13+8]
0x18008d905  mov     rcx, [rcx]; Sid
0x18008d908  call    cs:__imp_RtlLengthSid
0x18008d90f  nop     dword ptr [rax+rax+00h]
0x18008d914  movzx   edx, byte ptr [r14+r13]
0x18008d919  mov     r8d, eax
0x18008d91c  test    edx, edx
0x18008d91e  jz      short loc_18008D949
0x18008d920  sub     edx, 1
0x18008d923  jz      short loc_18008D93C
0x18008d925  cmp     edx, 1
0x18008d928  jnz     short loc_18008D9A7
0x18008d92a  mov     rax, [r14+r13+8]
0x18008d92f  mov     [rsp+88h+Acl], rdi
0x18008d934  mov     rdi, [rax]
0x18008d937  mov     byte ptr [rsi], 2
0x18008d93a  jmp     short loc_18008D959
0x18008d93c  mov     rax, [r14+r13+8]
0x18008d941  mov     rdi, [rax]
0x18008d944  mov     byte ptr [rsi], 1
0x18008d947  jmp     short loc_18008D954
0x18008d949  mov     rax, [r14+r13+8]
0x18008d94e  mov     rdi, [rax]
0x18008d951  mov     byte ptr [rsi], 0
0x18008d954  mov     [rsp+88h+Acl], r15
0x18008d959  mov     al, [r14+r13+2]
0x18008d95e  add     r8d, 8
0x18008d962  or      al, [r14+r13+1]
0x18008d967  mov     rcx, rdi; Sid
0x18008d96a  mov     [rsi+1], al
0x18008d96d  mov     eax, [r14+r13+4]
0x18008d972  mov     [rsi+4], eax
0x18008d975  mov     [rsp+88h+var_58], r8d
0x18008d97a  mov     [rsi+2], r8w
0x18008d97f  call    cs:__imp_RtlLengthSid
0x18008d986  nop     dword ptr [rax+rax+00h]
0x18008d98b  mov     r8, rdi; SourceSid
0x18008d98e  lea     rdx, [rsi+8]; DestinationSid
0x18008d992  mov     ecx, eax; DestinationSidLength
0x18008d994  call    cs:__imp_RtlCopySid
0x18008d99b  nop     dword ptr [rax+rax+00h]
0x18008d9a0  mov     r8d, [rsp+88h+var_58]
0x18008d9a5  mov     ebx, eax
0x18008d9a7  test    ebx, ebx
0x18008d9a9  js      loc_18008D8AF
0x18008d9af  mov     rcx, [rsp+88h+Acl]; Acl
0x18008d9b4  mov     r9, rsi; AceList
0x18008d9b7  mov     [rsp+88h+AceListLength], r8d; AceListLength
0x18008d9bc  mov     edx, 2; AceRevision
0x18008d9c1  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18008d9c5  call    cs:__imp_RtlAddAce
0x18008d9cc  nop     dword ptr [rax+rax+00h]
0x18008d9d1  mov     ebx, eax
0x18008d9d3  test    eax, eax
0x18008d9d5  js      loc_18008D8AF
0x18008d9db  mov     rdi, [rsp+88h+var_48]
0x18008d9e0  inc     r12d
0x18008d9e3  jmp     loc_18008D8E2
0x18008d9e8  mov     edx, 1; Revision
0x18008d9ed  mov     rcx, rbp; SecurityDescriptor
0x18008d9f0  call    cs:__imp_RtlCreateSecurityDescriptor
0x18008d9f7  nop     dword ptr [rax+rax+00h]
0x18008d9fc  mov     ebx, eax
0x18008d9fe  test    eax, eax
0x18008da00  js      loc_18008D8AF
0x18008da06  mov     rdx, [rsp+88h+Owner]; Owner
0x18008da0e  xor     r8d, r8d; OwnerDefaulted
0x18008da11  mov     rcx, rbp; SecurityDescriptor
0x18008da14  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18008da1b  nop     dword ptr [rax+rax+00h]
0x18008da20  mov     ebx, eax
0x18008da22  test    eax, eax
0x18008da24  js      loc_18008D8AF
0x18008da2a  mov     rdx, [rsp+88h+Group]; Group
0x18008da32  xor     r8d, r8d; GroupDefaulted
0x18008da35  mov     rcx, rbp; SecurityDescriptor
0x18008da38  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18008da3f  nop     dword ptr [rax+rax+00h]
0x18008da44  mov     ebx, eax
0x18008da46  test    eax, eax
0x18008da48  js      loc_18008D8AF
0x18008da4e  xor     r9d, r9d; DaclDefaulted
0x18008da51  mov     r8, r15; Dacl
0x18008da54  mov     dl, 1; DaclPresent
0x18008da56  mov     rcx, rbp; SecurityDescriptor
0x18008da59  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18008da60  nop     dword ptr [rax+rax+00h]
0x18008da65  mov     ebx, eax
0x18008da67  test    eax, eax
0x18008da69  js      loc_18008D8AF
0x18008da6f  xor     r9d, r9d; SaclDefaulted
0x18008da72  mov     r8, rdi; Sacl
0x18008da75  xor     edx, edx; SaclPresent
0x18008da77  mov     rcx, rbp; SecurityDescriptor
0x18008da7a  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18008da81  nop     dword ptr [rax+rax+00h]
0x18008da86  mov     ebx, eax
0x18008da88  test    eax, eax
0x18008da8a  js      loc_18008D8AF
0x18008da90  xor     ebx, ebx
0x18008da92  mov     rax, [rsp+88h+arg_20]
0x18008da9a  mov     [rax], rbp
0x18008da9d  jmp     loc_18008D8BC
```
