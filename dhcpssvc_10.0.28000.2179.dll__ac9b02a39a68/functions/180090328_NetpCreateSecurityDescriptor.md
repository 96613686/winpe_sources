# NetpCreateSecurityDescriptor

- ea: `0x180090328`
- end: `0x180090695`
- name: `NetpCreateSecurityDescriptor`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009069c`

## callees

- `0x180090328`

## import_xrefs

- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180090631`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180090631`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18009060e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18009060e`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800905ea`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800905ea`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800905c6`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800905c6`
- `ntdll!RtlAddAce` at `0x180090593`
- `ntdll!RtlAddAce` at `0x180090593`
- `ntdll!RtlCreateAcl` at `0x180090440`
- `ntdll!RtlCreateAcl` at `0x180090469`
- `ntdll!RtlCreateAcl` at `0x180090440`
- `ntdll!RtlCreateAcl` at `0x180090469`
- `ntdll!RtlLengthSid` at `0x180090388`
- `ntdll!RtlLengthSid` at `0x1800904eb`
- `ntdll!RtlLengthSid` at `0x180090554`
- `ntdll!RtlLengthSid` at `0x180090388`
- `ntdll!RtlLengthSid` at `0x1800904eb`
- `ntdll!RtlLengthSid` at `0x180090554`
- `ntdll!RtlCopySid` at `0x180090569`
- `ntdll!RtlCopySid` at `0x180090569`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180090654`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180090654`
- `KERNEL32!LocalAlloc` at `0x180090404`
- `KERNEL32!LocalAlloc` at `0x180090485`
- `KERNEL32!LocalAlloc` at `0x180090404`
- `KERNEL32!LocalAlloc` at `0x180090485`
- `KERNEL32!LocalFree` at `0x1800904a1`
- `KERNEL32!LocalFree` at `0x1800904b9`
- `KERNEL32!LocalFree` at `0x1800904a1`
- `KERNEL32!LocalFree` at `0x1800904b9`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityDescriptor(__int64 a1, unsigned int a2, void *a3, void *a4, struct _ACL **a5)
{
  ULONG v5; // r15d
  char *v6; // rsi
  unsigned int v7; // ebp
  ULONG v8; // r14d
  __int64 v10; // rax
  NTSTATUS SecurityDescriptor; // edi
  ULONG v12; // r12d
  ULONG v13; // eax
  ULONG v14; // eax
  int v15; // eax
  unsigned int v16; // ecx
  struct _ACL *v17; // rax
  struct _ACL *v18; // rbp
  struct _ACL *v19; // rbx
  unsigned int v20; // r12d
  PSID **v21; // r14
  struct _ACL *v22; // r13
  ULONG v23; // eax
  ULONG AceListLength; // r15d
  PSID v25; // rdi
  ULONG v26; // eax
  struct _ACL *Dacl; // [rsp+30h] [rbp-58h]
  struct _ACL *Sacl; // [rsp+38h] [rbp-50h]

  v5 = 0;
  Dacl = 0;
  v6 = 0;
  Sacl = 0;
  v7 = 0;
  v8 = 8;
  v10 = a1;
  SecurityDescriptor = -1073741811;
  v12 = 8;
  if ( a2 )
  {
    while ( 1 )
    {
      v13 = RtlLengthSid(**(PSID **)(v10 + 16LL * v7 + 8));
      if ( !*(_BYTE *)(a1 + 16LL * v7) || *(_BYTE *)(a1 + 16LL * v7) == 1 )
      {
        v14 = v13 + 8;
        v8 += v14;
      }
      else
      {
        if ( *(_BYTE *)(a1 + 16LL * v7) != 2 )
          return (unsigned int)SecurityDescriptor;
        v14 = v13 + 8;
        v12 += v14;
      }
      if ( v5 > v14 )
        v14 = v5;
      ++v7;
      v5 = v14;
      if ( v7 >= a2 )
        break;
      v10 = a1;
    }
  }
  v15 = v8 + 40;
  if ( v8 == 8 )
    v15 = 40;
  v16 = v15 + v12;
  if ( v12 == 8 )
    v16 = v15;
  if ( !v16 )
    return (unsigned int)-1073741801;
  v17 = (struct _ACL *)LocalAlloc(0, v16);
  if ( (v18 = v17) == 0 )
    return (unsigned int)-1073741801;
  v19 = v17 + 5;
  if ( v8 == 8
    || (Dacl = v17 + 5,
        v19 = (struct _ACL *)((char *)v19 + v8),
        SecurityDescriptor = RtlCreateAcl(v17 + 5, v8, 2u),
        SecurityDescriptor >= 0) )
  {
    if ( v12 == 8 || (Sacl = v19, SecurityDescriptor = RtlCreateAcl(v19, v12, 2u), SecurityDescriptor >= 0) )
    {
      if ( !v5 || (v6 = (char *)LocalAlloc(0, v5)) == 0 )
      {
        SecurityDescriptor = -1073741801;
        goto LABEL_24;
      }
      v20 = 0;
      if ( a2 )
      {
        v21 = (PSID **)(a1 + 8);
        while ( 1 )
        {
          v22 = 0;
          v23 = RtlLengthSid(**v21);
          AceListLength = v23;
          if ( !*((_BYTE *)v21 - 8) )
            break;
          if ( *((_BYTE *)v21 - 8) == 1 )
          {
            v25 = **v21;
            *v6 = 1;
LABEL_34:
            v22 = Dacl;
            goto LABEL_35;
          }
          if ( *((_BYTE *)v21 - 8) == 2 )
          {
            v22 = Sacl;
            v25 = **v21;
            *v6 = 2;
LABEL_35:
            AceListLength = v23 + 8;
            v6[1] = *((_BYTE *)v21 - 6) | *((_BYTE *)v21 - 7);
            *((_DWORD *)v6 + 1) = *((_DWORD *)v21 - 1);
            *((_WORD *)v6 + 1) = v23 + 8;
            v26 = RtlLengthSid(v25);
            SecurityDescriptor = RtlCopySid(v26, v6 + 8, v25);
          }
          if ( SecurityDescriptor < 0 )
            goto LABEL_24;
          SecurityDescriptor = RtlAddAce(v22, 2u, 0xFFFFFFFF, v6, AceListLength);
          if ( SecurityDescriptor < 0 )
            goto LABEL_24;
          ++v20;
          v21 += 2;
          if ( v20 >= a2 )
            goto LABEL_39;
        }
        v25 = **v21;
        *v6 = 0;
        goto LABEL_34;
      }
LABEL_39:
      SecurityDescriptor = RtlCreateSecurityDescriptor(v18, 1u);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v18, a3, 0);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlSetGroupSecurityDescriptor(v18, a4, 0);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = RtlSetDaclSecurityDescriptor(v18, 1u, Dacl, 0);
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = RtlSetSaclSecurityDescriptor(v18, 0, Sacl, 0);
              if ( SecurityDescriptor >= 0 )
              {
                SecurityDescriptor = 0;
                *a5 = v18;
                goto LABEL_25;
              }
            }
          }
        }
      }
    }
  }
LABEL_24:
  LocalFree(v18);
  if ( v6 )
LABEL_25:
    LocalFree(v6);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x180090328  mov     rax, rsp
0x18009032b  mov     [rax+20h], r9
0x18009032f  mov     [rax+18h], r8
0x180090333  mov     [rax+10h], edx
0x180090336  mov     [rax+8], rcx
0x18009033a  push    rbx
0x18009033b  push    rbp
0x18009033c  push    rsi
0x18009033d  push    rdi
0x18009033e  push    r12
0x180090340  push    r13
0x180090342  push    r14
0x180090344  push    r15
0x180090346  sub     rsp, 48h
0x18009034a  xor     r15d, r15d
0x18009034d  mov     [rsp+88h+Dacl], 0
0x180090356  xor     esi, esi
0x180090358  mov     [rsp+88h+Sacl], 0
0x180090361  xor     ebp, ebp
0x180090363  mov     r14d, 8
0x180090369  mov     r13d, edx
0x18009036c  mov     rax, rcx
0x18009036f  mov     edi, 0C000000Dh
0x180090374  mov     r12d, r14d
0x180090377  test    edx, edx
0x180090379  jz      short loc_1800903DD
0x18009037b  mov     ebx, ebp
0x18009037d  add     rbx, rbx
0x180090380  mov     rcx, [rax+rbx*8+8]
0x180090385  mov     rcx, [rcx]; Sid
0x180090388  call    cs:__imp_RtlLengthSid
0x18009038f  nop     dword ptr [rax+rax+00h]
0x180090394  mov     rcx, [rsp+88h+arg_0]
0x18009039c  movzx   edx, byte ptr [rcx+rbx*8]
0x1800903a0  test    edx, edx
0x1800903a2  jz      short loc_1800903BC
0x1800903a4  sub     edx, 1
0x1800903a7  jz      short loc_1800903BC
0x1800903a9  cmp     edx, 1
0x1800903ac  jnz     loc_180090681
0x1800903b2  lea     ecx, [rax+8]
0x1800903b5  mov     eax, ecx
0x1800903b7  add     r12d, ecx
0x1800903ba  jmp     short loc_1800903C2
0x1800903bc  add     eax, 8
0x1800903bf  add     r14d, eax
0x1800903c2  cmp     r15d, eax
0x1800903c5  cmova   eax, r15d
0x1800903c9  inc     ebp
0x1800903cb  mov     r15d, eax
0x1800903ce  cmp     ebp, r13d
0x1800903d1  jnb     short loc_1800903DD
0x1800903d3  mov     rax, [rsp+88h+arg_0]
0x1800903db  jmp     short loc_18009037B
0x1800903dd  cmp     r14d, 8
0x1800903e1  lea     eax, [r14+28h]
0x1800903e5  mov     ecx, 28h ; '('
0x1800903ea  cmovz   eax, ecx
0x1800903ed  cmp     r12d, 8
0x1800903f1  lea     ecx, [rax+r12]
0x1800903f5  cmovz   ecx, eax
0x1800903f8  test    ecx, ecx
0x1800903fa  jz      loc_18009067C
0x180090400  mov     edx, ecx; uBytes
0x180090402  xor     ecx, ecx; uFlags
0x180090404  call    cs:__imp_LocalAlloc
0x18009040b  nop     dword ptr [rax+rax+00h]
0x180090410  mov     rbp, rax
0x180090413  test    rax, rax
0x180090416  jz      loc_18009067C
0x18009041c  lea     rbx, [rax+28h]
0x180090420  cmp     r14d, 8
0x180090424  jz      short loc_180090452
0x180090426  mov     rax, rbx
0x180090429  mov     ecx, r14d
0x18009042c  mov     [rsp+88h+Dacl], rbx
0x180090431  mov     r8d, 2; AclRevision
0x180090437  add     rbx, rcx
0x18009043a  mov     edx, r14d; AclSize
0x18009043d  mov     rcx, rax; Acl
0x180090440  call    cs:__imp_RtlCreateAcl
0x180090447  nop     dword ptr [rax+rax+00h]
0x18009044c  mov     edi, eax
0x18009044e  test    eax, eax
0x180090450  js      short loc_18009049E
0x180090452  cmp     r12d, 8
0x180090456  jz      short loc_18009047B
0x180090458  mov     r8d, 2; AclRevision
0x18009045e  mov     [rsp+88h+Sacl], rbx
0x180090463  mov     edx, r12d; AclSize
0x180090466  mov     rcx, rbx; Acl
0x180090469  call    cs:__imp_RtlCreateAcl
0x180090470  nop     dword ptr [rax+rax+00h]
0x180090475  mov     edi, eax
0x180090477  test    eax, eax
0x180090479  js      short loc_18009049E
0x18009047b  test    r15d, r15d
0x18009047e  jz      short loc_180090499
0x180090480  mov     edx, r15d; uBytes
0x180090483  xor     ecx, ecx; uFlags
0x180090485  call    cs:__imp_LocalAlloc
0x18009048c  nop     dword ptr [rax+rax+00h]
0x180090491  mov     rsi, rax
0x180090494  test    rax, rax
0x180090497  jnz     short loc_1800904CA
0x180090499  mov     edi, 0C0000017h
0x18009049e  mov     rcx, rbp; hMem
0x1800904a1  call    cs:__imp_LocalFree
0x1800904a8  nop     dword ptr [rax+rax+00h]
0x1800904ad  test    rsi, rsi
0x1800904b0  jz      loc_180090681
0x1800904b6  mov     rcx, rsi; hMem
0x1800904b9  call    cs:__imp_LocalFree
0x1800904c0  nop     dword ptr [rax+rax+00h]
0x1800904c5  jmp     loc_180090681
0x1800904ca  xor     r12d, r12d
0x1800904cd  test    r13d, r13d
0x1800904d0  jz      loc_1800905BE
0x1800904d6  mov     r14, [rsp+88h+arg_0]
0x1800904de  add     r14, 8
0x1800904e2  mov     rcx, [r14]
0x1800904e5  xor     r13d, r13d
0x1800904e8  mov     rcx, [rcx]; Sid
0x1800904eb  call    cs:__imp_RtlLengthSid
0x1800904f2  nop     dword ptr [rax+rax+00h]
0x1800904f7  movzx   edx, byte ptr [r14-8]
0x1800904fc  mov     r15d, eax
0x1800904ff  test    edx, edx
0x180090501  jz      short loc_180090528
0x180090503  sub     edx, 1
0x180090506  jz      short loc_18009051D
0x180090508  cmp     edx, 1
0x18009050b  jnz     short loc_180090577
0x18009050d  mov     rax, [r14]
0x180090510  mov     r13, [rsp+88h+Sacl]
0x180090515  mov     rdi, [rax]
0x180090518  mov     byte ptr [rsi], 2
0x18009051b  jmp     short loc_180090536
0x18009051d  mov     rax, [r14]
0x180090520  mov     rdi, [rax]
0x180090523  mov     byte ptr [rsi], 1
0x180090526  jmp     short loc_180090531
0x180090528  mov     rax, [r14]
0x18009052b  mov     rdi, [rax]
0x18009052e  mov     byte ptr [rsi], 0
0x180090531  mov     r13, [rsp+88h+Dacl]
0x180090536  mov     al, [r14-7]
0x18009053a  add     r15d, 8
0x18009053e  or      al, [r14-6]
0x180090542  mov     rcx, rdi; Sid
0x180090545  mov     [rsi+1], al
0x180090548  mov     eax, [r14-4]
0x18009054c  mov     [rsi+4], eax
0x18009054f  mov     [rsi+2], r15w
0x180090554  call    cs:__imp_RtlLengthSid
0x18009055b  nop     dword ptr [rax+rax+00h]
0x180090560  mov     r8, rdi; SourceSid
0x180090563  lea     rdx, [rsi+8]; DestinationSid
0x180090567  mov     ecx, eax; DestinationSidLength
0x180090569  call    cs:__imp_RtlCopySid
0x180090570  nop     dword ptr [rax+rax+00h]
0x180090575  mov     edi, eax
0x180090577  test    edi, edi
0x180090579  js      loc_18009049E
0x18009057f  mov     r9, rsi; AceList
0x180090582  mov     [rsp+88h+AceListLength], r15d; AceListLength
0x180090587  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18009058b  mov     edx, 2; AceRevision
0x180090590  mov     rcx, r13; Acl
0x180090593  call    cs:__imp_RtlAddAce
0x18009059a  nop     dword ptr [rax+rax+00h]
0x18009059f  mov     edi, eax
0x1800905a1  test    eax, eax
0x1800905a3  js      loc_18009049E
0x1800905a9  inc     r12d
0x1800905ac  add     r14, 10h
0x1800905b0  cmp     r12d, [rsp+88h+arg_8]
0x1800905b8  jb      loc_1800904E2
0x1800905be  mov     edx, 1; Revision
0x1800905c3  mov     rcx, rbp; SecurityDescriptor
0x1800905c6  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800905cd  nop     dword ptr [rax+rax+00h]
0x1800905d2  mov     edi, eax
0x1800905d4  test    eax, eax
0x1800905d6  js      loc_18009049E
0x1800905dc  mov     rdx, [rsp+88h+Owner]; Owner
0x1800905e4  xor     r8d, r8d; OwnerDefaulted
0x1800905e7  mov     rcx, rbp; SecurityDescriptor
0x1800905ea  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800905f1  nop     dword ptr [rax+rax+00h]
0x1800905f6  mov     edi, eax
0x1800905f8  test    eax, eax
0x1800905fa  js      loc_18009049E
0x180090600  mov     rdx, [rsp+88h+Group]; Group
0x180090608  xor     r8d, r8d; GroupDefaulted
0x18009060b  mov     rcx, rbp; SecurityDescriptor
0x18009060e  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180090615  nop     dword ptr [rax+rax+00h]
0x18009061a  mov     edi, eax
0x18009061c  test    eax, eax
0x18009061e  js      loc_18009049E
0x180090624  mov     r8, [rsp+88h+Dacl]; Dacl
0x180090629  xor     r9d, r9d; DaclDefaulted
0x18009062c  mov     dl, 1; DaclPresent
0x18009062e  mov     rcx, rbp; SecurityDescriptor
0x180090631  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180090638  nop     dword ptr [rax+rax+00h]
0x18009063d  mov     edi, eax
0x18009063f  test    eax, eax
0x180090641  js      loc_18009049E
0x180090647  mov     r8, [rsp+88h+Sacl]; Sacl
0x18009064c  xor     r9d, r9d; SaclDefaulted
0x18009064f  xor     edx, edx; SaclPresent
0x180090651  mov     rcx, rbp; SecurityDescriptor
0x180090654  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18009065b  nop     dword ptr [rax+rax+00h]
0x180090660  mov     edi, eax
0x180090662  test    eax, eax
0x180090664  js      loc_18009049E
0x18009066a  xor     edi, edi
0x18009066c  mov     rax, [rsp+88h+arg_20]
0x180090674  mov     [rax], rbp
0x180090677  jmp     loc_1800904B6
0x18009067c  mov     edi, 0C0000017h
0x180090681  mov     eax, edi
0x180090683  add     rsp, 48h
0x180090687  pop     r15
0x180090689  pop     r14
0x18009068b  pop     r13
0x18009068d  pop     r12
0x18009068f  pop     rdi
0x180090690  pop     rsi
0x180090691  pop     rbp
0x180090692  pop     rbx
0x180090693  retn
```
