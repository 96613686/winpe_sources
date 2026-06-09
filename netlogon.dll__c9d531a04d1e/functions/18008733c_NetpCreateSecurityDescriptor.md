# NetpCreateSecurityDescriptor

- ea: `0x18008733c`
- end: `0x180087625`
- name: `NetpCreateSecurityDescriptor`
- size: `745`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, void *, struct _ACL **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034fa8`
- `0x18008762c`

## callees

- `0x180003200`
- `0x180003670`
- `0x18008733c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180087541`
- `ntdll!RtlCopySid` at `0x180087541`
- `ntdll!RtlCreateAcl` at `0x18008740b`
- `ntdll!RtlCreateAcl` at `0x18008743e`
- `ntdll!RtlCreateAcl` at `0x18008740b`
- `ntdll!RtlCreateAcl` at `0x18008743e`
- `ntdll!RtlAddAce` at `0x18008756c`
- `ntdll!RtlAddAce` at `0x18008756c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180087591`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180087591`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800875af`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800875af`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800875cd`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800875cd`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800875e8`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800875e8`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180087603`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180087603`
- `ntdll!RtlLengthSid` at `0x180087382`
- `ntdll!RtlLengthSid` at `0x1800874c1`
- `ntdll!RtlLengthSid` at `0x180087532`
- `ntdll!RtlLengthSid` at `0x180087382`
- `ntdll!RtlLengthSid` at `0x1800874c1`
- `ntdll!RtlLengthSid` at `0x180087532`

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
  ULONG v24; // eax
  ULONG AceListLength; // r8d
  void *v26; // rdi
  ULONG v27; // eax
  NTSTATUS v28; // eax
  ULONG v29; // [rsp+30h] [rbp-58h]
  struct _ACL *Acl; // [rsp+38h] [rbp-50h]
  struct _ACL *v31; // [rsp+40h] [rbp-48h]

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
  v31 = 0;
  if ( v7 == 8 )
  {
    v21 = 0;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(v21, v7, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v31 = v21;
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
    v24 = RtlLengthSid(**(PSID **)(v23 + a1 + 8));
    AceListLength = v24;
    switch ( *(_BYTE *)(v23 + a1) )
    {
      case 0:
        v26 = **(void ***)(v23 + a1 + 8);
        *v19 = 0;
        goto LABEL_39;
      case 1:
        v26 = **(void ***)(v23 + a1 + 8);
        *v19 = 1;
LABEL_39:
        Acl = v20;
        goto LABEL_40;
      case 2:
        Acl = v21;
        v26 = **(void ***)(v23 + a1 + 8);
        *v19 = 2;
LABEL_40:
        v19[1] = *(_BYTE *)(v23 + a1 + 1) | *(_BYTE *)(v23 + a1 + 2);
        *((_DWORD *)v19 + 1) = *(_DWORD *)(v23 + a1 + 4);
        v29 = v24 + 8;
        *((_WORD *)v19 + 1) = v24 + 8;
        v27 = RtlLengthSid(v26);
        v28 = RtlCopySid(v27, v19 + 8, v26);
        AceListLength = v29;
        SecurityDescriptor = v28;
        break;
    }
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    SecurityDescriptor = RtlAddAce(Acl, 2u, 0xFFFFFFFF, v19, AceListLength);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v21 = v31;
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
0x18008733c  mov     rax, rsp
0x18008733f  mov     [rax+8], rbx
0x180087343  mov     [rax+20h], r9
0x180087347  mov     [rax+18h], r8
0x18008734b  mov     [rax+10h], edx
0x18008734e  push    rbp
0x18008734f  push    rsi
0x180087350  push    rdi
0x180087351  push    r12
0x180087353  push    r13
0x180087355  push    r14
0x180087357  push    r15
0x180087359  sub     rsp, 50h
0x18008735d  mov     ebp, 8
0x180087362  xor     r12d, r12d
0x180087365  mov     edi, ebp
0x180087367  mov     r14d, ebp
0x18008736a  xor     esi, esi
0x18008736c  mov     eax, edx
0x18008736e  mov     r13, rcx
0x180087371  cmp     esi, eax
0x180087373  jnb     short loc_1800873C9
0x180087375  mov     ebx, esi
0x180087377  add     rbx, rbx
0x18008737a  mov     rcx, [r13+rbx*8+8]
0x18008737f  mov     rcx, [rcx]; Sid
0x180087382  call    cs:__imp_RtlLengthSid
0x180087388  movzx   edx, byte ptr [r13+rbx*8+0]
0x18008738e  test    edx, edx
0x180087390  jz      short loc_1800873A6
0x180087392  sub     edx, 1
0x180087395  jz      short loc_1800873A6
0x180087397  cmp     edx, 1
0x18008739a  jnz     short loc_1800873BF
0x18008739c  lea     ecx, [rax+8]
0x18008739f  mov     eax, ecx
0x1800873a1  add     r14d, ecx
0x1800873a4  jmp     short loc_1800873AA
0x1800873a6  add     eax, ebp
0x1800873a8  add     edi, eax
0x1800873aa  inc     esi
0x1800873ac  cmp     r12d, eax
0x1800873af  cmova   eax, r12d
0x1800873b3  mov     r12d, eax
0x1800873b6  mov     eax, [rsp+88h+arg_8]
0x1800873bd  jmp     short loc_180087371
0x1800873bf  mov     eax, 0C000000Dh
0x1800873c4  jmp     loc_180087480
0x1800873c9  mov     ecx, 28h ; '('
0x1800873ce  lea     eax, [rdi+28h]
0x1800873d1  cmp     edi, ebp
0x1800873d3  cmovz   eax, ecx
0x1800873d6  cmp     r14d, ebp
0x1800873d9  lea     ecx, [rax+r14]
0x1800873dd  cmovz   ecx, eax
0x1800873e0  call    NetpMemoryAllocate
0x1800873e5  mov     rbp, rax
0x1800873e8  test    rax, rax
0x1800873eb  jnz     short loc_1800873F7
0x1800873ed  mov     ebx, 0C0000017h
0x1800873f2  jmp     loc_18008747E
0x1800873f7  xor     esi, esi
0x1800873f9  lea     r15, [rax+28h]
0x1800873fd  cmp     edi, 8
0x180087400  jz      short loc_18008741C
0x180087402  lea     r8d, [rsi+2]; AclRevision
0x180087406  mov     edx, edi; AclSize
0x180087408  mov     rcx, r15; Acl
0x18008740b  call    cs:__imp_RtlCreateAcl
0x180087411  mov     ebx, eax
0x180087413  test    eax, eax
0x180087415  js      short loc_180087469
0x180087417  add     rdi, r15
0x18008741a  jmp     short loc_180087427
0x18008741c  mov     rdi, r15
0x18008741f  mov     ebx, 0C000000Dh
0x180087424  xor     r15d, r15d
0x180087427  mov     [rsp+88h+var_48], rsi
0x18008742c  cmp     r14d, 8
0x180087430  jz      short loc_180087451
0x180087432  mov     r8d, 2; AclRevision
0x180087438  mov     edx, r14d; AclSize
0x18008743b  mov     rcx, rdi; Acl
0x18008743e  call    cs:__imp_RtlCreateAcl
0x180087444  mov     ebx, eax
0x180087446  test    eax, eax
0x180087448  js      short loc_180087469
0x18008744a  mov     [rsp+88h+var_48], rdi
0x18008744f  jmp     short loc_180087454
0x180087451  mov     rdi, rsi
0x180087454  mov     ecx, r12d
0x180087457  call    NetpMemoryAllocate
0x18008745c  mov     rsi, rax
0x18008745f  test    rax, rax
0x180087462  jnz     short loc_180087498
0x180087464  mov     ebx, 0C0000017h
0x180087469  mov     rcx, rbp
0x18008746c  call    NetpMemoryFree
0x180087471  test    rsi, rsi
0x180087474  jz      short loc_18008747E
0x180087476  mov     rcx, rsi
0x180087479  call    NetpMemoryFree
0x18008747e  mov     eax, ebx
0x180087480  mov     rbx, [rsp+88h+arg_0]
0x180087488  add     rsp, 50h
0x18008748c  pop     r15
0x18008748e  pop     r14
0x180087490  pop     r13
0x180087492  pop     r12
0x180087494  pop     rdi
0x180087495  pop     rsi
0x180087496  pop     rbp
0x180087497  retn
0x180087498  xor     r12d, r12d
0x18008749b  cmp     r12d, [rsp+88h+arg_8]
0x1800874a3  jnb     loc_180087589
0x1800874a9  mov     r14d, r12d
0x1800874ac  shl     r14, 4
0x1800874b0  mov     [rsp+88h+Acl], 0
0x1800874b9  mov     rcx, [r14+r13+8]
0x1800874be  mov     rcx, [rcx]; Sid
0x1800874c1  call    cs:__imp_RtlLengthSid
0x1800874c7  movzx   edx, byte ptr [r14+r13]
0x1800874cc  mov     r8d, eax
0x1800874cf  test    edx, edx
0x1800874d1  jz      short loc_1800874FC
0x1800874d3  sub     edx, 1
0x1800874d6  jz      short loc_1800874EF
0x1800874d8  cmp     edx, 1
0x1800874db  jnz     short loc_18008754E
0x1800874dd  mov     rax, [r14+r13+8]
0x1800874e2  mov     [rsp+88h+Acl], rdi
0x1800874e7  mov     rdi, [rax]
0x1800874ea  mov     byte ptr [rsi], 2
0x1800874ed  jmp     short loc_18008750C
0x1800874ef  mov     rax, [r14+r13+8]
0x1800874f4  mov     rdi, [rax]
0x1800874f7  mov     byte ptr [rsi], 1
0x1800874fa  jmp     short loc_180087507
0x1800874fc  mov     rax, [r14+r13+8]
0x180087501  mov     rdi, [rax]
0x180087504  mov     byte ptr [rsi], 0
0x180087507  mov     [rsp+88h+Acl], r15
0x18008750c  mov     al, [r14+r13+2]
0x180087511  add     r8d, 8
0x180087515  or      al, [r14+r13+1]
0x18008751a  mov     rcx, rdi; Sid
0x18008751d  mov     [rsi+1], al
0x180087520  mov     eax, [r14+r13+4]
0x180087525  mov     [rsi+4], eax
0x180087528  mov     [rsp+88h+var_58], r8d
0x18008752d  mov     [rsi+2], r8w
0x180087532  call    cs:__imp_RtlLengthSid
0x180087538  mov     r8, rdi; SourceSid
0x18008753b  lea     rdx, [rsi+8]; DestinationSid
0x18008753f  mov     ecx, eax; DestinationSidLength
0x180087541  call    cs:__imp_RtlCopySid
0x180087547  mov     r8d, [rsp+88h+var_58]
0x18008754c  mov     ebx, eax
0x18008754e  test    ebx, ebx
0x180087550  js      loc_180087469
0x180087556  mov     rcx, [rsp+88h+Acl]; Acl
0x18008755b  mov     r9, rsi; AceList
0x18008755e  mov     [rsp+88h+AceListLength], r8d; AceListLength
0x180087563  mov     edx, 2; AceRevision
0x180087568  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18008756c  call    cs:__imp_RtlAddAce
0x180087572  mov     ebx, eax
0x180087574  test    eax, eax
0x180087576  js      loc_180087469
0x18008757c  mov     rdi, [rsp+88h+var_48]
0x180087581  inc     r12d
0x180087584  jmp     loc_18008749B
0x180087589  mov     edx, 1; Revision
0x18008758e  mov     rcx, rbp; SecurityDescriptor
0x180087591  call    cs:__imp_RtlCreateSecurityDescriptor
0x180087597  mov     ebx, eax
0x180087599  test    eax, eax
0x18008759b  js      loc_180087469
0x1800875a1  mov     rdx, [rsp+88h+Owner]; Owner
0x1800875a9  xor     r8d, r8d; OwnerDefaulted
0x1800875ac  mov     rcx, rbp; SecurityDescriptor
0x1800875af  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800875b5  mov     ebx, eax
0x1800875b7  test    eax, eax
0x1800875b9  js      loc_180087469
0x1800875bf  mov     rdx, [rsp+88h+Group]; Group
0x1800875c7  xor     r8d, r8d; GroupDefaulted
0x1800875ca  mov     rcx, rbp; SecurityDescriptor
0x1800875cd  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800875d3  mov     ebx, eax
0x1800875d5  test    eax, eax
0x1800875d7  js      loc_180087469
0x1800875dd  xor     r9d, r9d; DaclDefaulted
0x1800875e0  mov     r8, r15; Dacl
0x1800875e3  mov     dl, 1; DaclPresent
0x1800875e5  mov     rcx, rbp; SecurityDescriptor
0x1800875e8  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800875ee  mov     ebx, eax
0x1800875f0  test    eax, eax
0x1800875f2  js      loc_180087469
0x1800875f8  xor     r9d, r9d; SaclDefaulted
0x1800875fb  mov     r8, rdi; Sacl
0x1800875fe  xor     edx, edx; SaclPresent
0x180087600  mov     rcx, rbp; SecurityDescriptor
0x180087603  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180087609  mov     ebx, eax
0x18008760b  test    eax, eax
0x18008760d  js      loc_180087469
0x180087613  xor     ebx, ebx
0x180087615  mov     rax, [rsp+88h+arg_20]
0x18008761d  mov     [rax], rbp
0x180087620  jmp     loc_180087476
```
