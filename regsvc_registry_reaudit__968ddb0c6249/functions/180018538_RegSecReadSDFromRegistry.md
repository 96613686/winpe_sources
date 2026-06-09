# RegSecReadSDFromRegistry

- ea: `0x180018538`
- end: `0x180018958`
- name: `RegSecReadSDFromRegistry`
- size: `1056`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017b54`
- `0x1800181ec`

## callees

- `0x180007740`
- `0x180018538`
- `0x18001e431`

## import_xrefs

- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180018786`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180018786`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800187e4`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800187e4`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180018626`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180018626`
- `ntdll!RtlLengthSid` at `0x18001872d`
- `ntdll!RtlLengthSid` at `0x180018757`
- `ntdll!RtlLengthSid` at `0x18001879c`
- `ntdll!RtlLengthSid` at `0x1800187c6`
- `ntdll!RtlLengthSid` at `0x18001872d`
- `ntdll!RtlLengthSid` at `0x180018757`
- `ntdll!RtlLengthSid` at `0x18001879c`
- `ntdll!RtlLengthSid` at `0x1800187c6`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800188ec`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800188ec`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18001871a`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18001871a`
- `ntdll!RtlQueryInformationAcl` at `0x180018657`
- `ntdll!RtlQueryInformationAcl` at `0x180018657`
- `ntdll!RtlGetAce` at `0x180018677`
- `ntdll!RtlGetAce` at `0x180018677`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180018775`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180018775`
- `ntdll!NtQuerySecurityObject` at `0x1800185b9`
- `ntdll!NtQuerySecurityObject` at `0x180018609`
- `ntdll!NtQuerySecurityObject` at `0x1800185b9`
- `ntdll!NtQuerySecurityObject` at `0x180018609`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180018892`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180018892`
- `ntdll!RtlLengthRequiredSid` at `0x18001889d`
- `ntdll!RtlLengthRequiredSid` at `0x18001889d`
- `ntdll!RtlFreeHeap` at `0x1800187fc`
- `ntdll!RtlFreeHeap` at `0x18001881f`
- `ntdll!RtlFreeHeap` at `0x1800187fc`
- `ntdll!RtlFreeHeap` at `0x18001881f`
- `ntdll!RtlCreateAcl` at `0x1800188d9`
- `ntdll!RtlCreateAcl` at `0x1800188d9`
- `ntdll!RtlFreeSid` at `0x18001890f`
- `ntdll!RtlFreeSid` at `0x180018925`
- `ntdll!RtlFreeSid` at `0x18001890f`
- `ntdll!RtlFreeSid` at `0x180018925`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180018901`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180018901`
- `ntdll!RtlAllocateHeap` at `0x1800185e2`
- `ntdll!RtlAllocateHeap` at `0x1800186ca`
- `ntdll!RtlAllocateHeap` at `0x180018745`
- `ntdll!RtlAllocateHeap` at `0x1800187b4`
- `ntdll!RtlAllocateHeap` at `0x180018838`
- `ntdll!RtlAllocateHeap` at `0x1800188b9`
- `ntdll!RtlAllocateHeap` at `0x1800185e2`
- `ntdll!RtlAllocateHeap` at `0x1800186ca`
- `ntdll!RtlAllocateHeap` at `0x180018745`
- `ntdll!RtlAllocateHeap` at `0x1800187b4`
- `ntdll!RtlAllocateHeap` at `0x180018838`
- `ntdll!RtlAllocateHeap` at `0x1800188b9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800186e4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180018852`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800186e4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180018852`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018709`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018709`

## pseudocode

```c
__int64 __fastcall RegSecReadSDFromRegistry(HANDLE Handle, struct _ACL **a2)
{
  PVOID v4; // rsi
  ULONG i; // ebx
  int v6; // ecx
  int v7; // eax
  int v8; // ecx
  struct _ACL *v9; // rax
  struct _ACL *v10; // rdi
  ULONG v11; // eax
  PVOID v12; // rbx
  ULONG v13; // eax
  NTSTATUS GroupSecurityDescriptor; // r14d
  ULONG v15; // eax
  PVOID v16; // rbx
  ULONG v17; // eax
  __int64 result; // rax
  struct _ACL *Heap; // rax
  struct _ACL *v20; // rdi
  NTSTATUS v21; // ebx
  ULONG v22; // r14d
  struct _ACL *v23; // rax
  struct _ACL *v24; // rsi
  unsigned __int8 DaclPresent; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+61h] [rbp-18h] BYREF
  unsigned __int8 DaclDefaulted[2]; // [rsp+62h] [rbp-17h] BYREF
  ULONG Length; // [rsp+64h] [rbp-15h] BYREF
  PSID Owner; // [rsp+68h] [rbp-11h] BYREF
  PACL Dacl; // [rsp+70h] [rbp-9h] BYREF
  PSID Sid; // [rsp+78h] [rbp-1h] BYREF
  PVOID Ace; // [rsp+80h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp+Fh] BYREF
  __int64 Information; // [rsp+90h] [rbp+17h] BYREF
  int v35; // [rsp+98h] [rbp+1Fh]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *a2 = 0;
  Information = 0;
  v35 = 0;
  Ace = 0;
  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  Owner = 0;
  OwnerDefaulted = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Length = 0;
  if ( NtQuerySecurityObject(Handle, 7u, 0, 0, &Length) != -1073741789 )
  {
LABEL_30:
    Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
    v20 = Heap;
    if ( Heap )
    {
      InitializeSecurityDescriptor(Heap, 1u);
      v21 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid);
      v22 = RtlLengthRequiredSid(2u) + 20;
      v23 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      v24 = v23;
      if ( v21 >= 0 )
      {
        if ( v23 )
        {
          RtlCreateAcl(v23, v22, 2u);
          if ( RtlAddAccessAllowedAce(v24, 2u, 3u, Sid) >= 0 && RtlSetDaclSecurityDescriptor(v20, 1u, v24, 0) >= 0 )
          {
            RtlFreeSid(Sid);
            result = 0;
            *a2 = v20;
            return result;
          }
        }
      }
      if ( Sid )
        RtlFreeSid(Sid);
    }
    return 3221225495LL;
  }
  v4 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length);
  if ( !v4 || NtQuerySecurityObject(Handle, 7u, v4, Length, &Length) < 0 )
    return 3221225495LL;
  if ( RtlGetDaclSecurityDescriptor(v4, &DaclPresent, &Dacl, DaclDefaulted) < 0
    || !DaclPresent
    || !Dacl
    || RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation) < 0 )
  {
    goto LABEL_29;
  }
  for ( i = 0; i < (unsigned int)Information; ++i )
  {
    if ( RtlGetAce(Dacl, i, &Ace) < 0 )
      goto LABEL_29;
    if ( *(_BYTE *)Ace <= 1u )
    {
      v6 = *((_DWORD *)Ace + 1);
      v7 = (v6 & 0x20019) != 0;
      v8 = v6 & 0x20006;
      if ( v8 )
      {
        if ( v8 != 0x20000 )
          v7 |= 2u;
      }
      *((_DWORD *)Ace + 1) = v7;
    }
  }
  v9 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length);
  v10 = v9;
  if ( !v9 )
  {
LABEL_29:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    goto LABEL_30;
  }
  InitializeSecurityDescriptor(v9, 1u);
  memcpy_0(&v10[5], Dacl, HIDWORD(Information));
  SetSecurityDescriptorDacl(v10, 1, v10 + 5, 0);
  if ( RtlGetOwnerSecurityDescriptor(v4, &Owner, &OwnerDefaulted) >= 0 && Owner )
  {
    v11 = RtlLengthSid(Owner);
    v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    if ( v12 )
    {
      v13 = RtlLengthSid(Owner);
      memcpy_0(v12, Owner, v13);
    }
    RtlSetOwnerSecurityDescriptor(v10, v12, 0);
  }
  GroupSecurityDescriptor = RtlGetGroupSecurityDescriptor(v4, &Owner, &OwnerDefaulted);
  if ( GroupSecurityDescriptor >= 0 && Owner )
  {
    v15 = RtlLengthSid(Owner);
    v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    if ( v16 )
    {
      v17 = RtlLengthSid(Owner);
      memcpy_0(v16, Owner, v17);
    }
    RtlSetGroupSecurityDescriptor(v10, v16, 0);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  result = (unsigned int)GroupSecurityDescriptor;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x180018538  mov     [rsp-8+arg_10], rbx
0x18001853d  mov     [rsp-8+arg_18], rsi
0x180018542  push    rbp
0x180018543  push    rdi
0x180018544  push    r12
0x180018546  push    r14
0x180018548  push    r15
0x18001854a  lea     rbp, [rsp-37h]
0x18001854f  sub     rsp, 0B0h
0x180018556  mov     rax, cs:__security_cookie
0x18001855d  xor     rax, rsp
0x180018560  mov     [rbp+57h+var_30], rax
0x180018564  xor     r12d, r12d
0x180018567  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18001856d  xor     eax, eax
0x18001856f  mov     [rdx], r12
0x180018572  mov     [rbp+57h+Information], rax
0x180018576  mov     r15, rdx
0x180018579  mov     [rbp+57h+var_38], eax
0x18001857c  xor     r9d, r9d; Length
0x18001857f  lea     rax, [rbp+57h+Length]
0x180018583  mov     [rbp+57h+Ace], r12
0x180018587  lea     edi, [r12+7]
0x18001858c  mov     [rbp+57h+Dacl], r12
0x180018590  mov     edx, edi; SecurityInformation
0x180018592  mov     [rbp+57h+DaclPresent], r12b
0x180018596  xor     r8d, r8d; SecurityDescriptor
0x180018599  mov     [rbp+57h+DaclDefaulted], r12b
0x18001859d  mov     rbx, rcx
0x1800185a0  mov     [rbp+57h+Owner], r12
0x1800185a4  mov     [rbp+57h+OwnerDefaulted], r12b
0x1800185a8  mov     [rbp+57h+var_58], r12
0x1800185ac  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x1800185b0  mov     [rbp+57h+Length], r12d
0x1800185b4  mov     [rsp+0D0h+LengthNeeded], rax; LengthNeeded
0x1800185b9  call    cs:__imp_NtQuerySecurityObject
0x1800185bf  lea     r14d, [r12+2]
0x1800185c4  cmp     eax, 0C0000023h
0x1800185c9  jnz     loc_180018825
0x1800185cf  mov     rcx, gs:60h
0x1800185d8  xor     edx, edx; Flags
0x1800185da  mov     r8d, [rbp+57h+Length]; Size
0x1800185de  mov     rcx, [rcx+30h]; HeapHandle
0x1800185e2  call    cs:__imp_RtlAllocateHeap
0x1800185e8  mov     rsi, rax
0x1800185eb  test    rax, rax
0x1800185ee  jz      loc_18001892B
0x1800185f4  mov     r9d, [rbp+57h+Length]; Length
0x1800185f8  lea     rax, [rbp+57h+Length]
0x1800185fc  mov     r8, rsi; SecurityDescriptor
0x1800185ff  mov     [rsp+0D0h+LengthNeeded], rax; LengthNeeded
0x180018604  mov     edx, edi; SecurityInformation
0x180018606  mov     rcx, rbx; Handle
0x180018609  call    cs:__imp_NtQuerySecurityObject
0x18001860f  test    eax, eax
0x180018611  js      loc_18001892B
0x180018617  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18001861b  mov     rcx, rsi; SecurityDescriptor
0x18001861e  lea     r8, [rbp+57h+Dacl]; Dacl
0x180018622  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x180018626  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18001862c  test    eax, eax
0x18001862e  js      loc_18001880D
0x180018634  cmp     [rbp+57h+DaclPresent], r12b
0x180018638  jz      loc_18001880D
0x18001863e  mov     rcx, [rbp+57h+Dacl]; Acl
0x180018642  test    rcx, rcx
0x180018645  jz      loc_18001880D
0x18001864b  mov     r9d, r14d; InformationClass
0x18001864e  lea     r8d, [r12+0Ch]; InformationLength
0x180018653  lea     rdx, [rbp+57h+Information]; Information
0x180018657  call    cs:__imp_RtlQueryInformationAcl
0x18001865d  test    eax, eax
0x18001865f  js      loc_18001880D
0x180018665  mov     ebx, r12d
0x180018668  cmp     ebx, dword ptr [rbp+57h+Information]
0x18001866b  jnb     short loc_1800186B7
0x18001866d  mov     rcx, [rbp+57h+Dacl]; Acl
0x180018671  lea     r8, [rbp+57h+Ace]; Ace
0x180018675  mov     edx, ebx; AceIndex
0x180018677  call    cs:__imp_RtlGetAce
0x18001867d  test    eax, eax
0x18001867f  js      loc_18001880D
0x180018685  mov     rdx, [rbp+57h+Ace]
0x180018689  cmp     byte ptr [rdx], 1
0x18001868c  ja      short loc_1800186B3
0x18001868e  mov     ecx, [rdx+4]
0x180018691  mov     eax, r12d
0x180018694  test    ecx, 20019h
0x18001869a  setnz   al
0x18001869d  and     ecx, 20006h
0x1800186a3  jz      short loc_1800186B0
0x1800186a5  cmp     ecx, 20000h
0x1800186ab  jz      short loc_1800186B0
0x1800186ad  or      eax, r14d
0x1800186b0  mov     [rdx+4], eax
0x1800186b3  inc     ebx
0x1800186b5  jmp     short loc_180018668
0x1800186b7  mov     rcx, gs:60h
0x1800186c0  xor     edx, edx; Flags
0x1800186c2  mov     r8d, [rbp+57h+Length]; Size
0x1800186c6  mov     rcx, [rcx+30h]; HeapHandle
0x1800186ca  call    cs:__imp_RtlAllocateHeap
0x1800186d0  mov     rdi, rax
0x1800186d3  test    rax, rax
0x1800186d6  jz      loc_18001880D
0x1800186dc  mov     edx, 1; dwRevision
0x1800186e1  mov     rcx, rax; pSecurityDescriptor
0x1800186e4  call    cs:__imp_InitializeSecurityDescriptor
0x1800186ea  mov     r8d, dword ptr [rbp+57h+Information+4]; Size
0x1800186ee  lea     rcx, [rdi+28h]; void *
0x1800186f2  mov     rdx, [rbp+57h+Dacl]; Src
0x1800186f6  call    memcpy_0
0x1800186fb  xor     r9d, r9d; bDaclDefaulted
0x1800186fe  lea     r8, [rdi+28h]; pDacl
0x180018702  mov     rcx, rdi; pSecurityDescriptor
0x180018705  lea     edx, [r9+1]; bDaclPresent
0x180018709  call    cs:__imp_SetSecurityDescriptorDacl
0x18001870f  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x180018713  mov     rcx, rsi; SecurityDescriptor
0x180018716  lea     rdx, [rbp+57h+Owner]; Owner
0x18001871a  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x180018720  test    eax, eax
0x180018722  js      short loc_18001877B
0x180018724  mov     rcx, [rbp+57h+Owner]; Sid
0x180018728  test    rcx, rcx
0x18001872b  jz      short loc_18001877B
0x18001872d  call    cs:__imp_RtlLengthSid
0x180018733  mov     rcx, gs:60h
0x18001873c  xor     edx, edx; Flags
0x18001873e  mov     r8d, eax; Size
0x180018741  mov     rcx, [rcx+30h]; HeapHandle
0x180018745  call    cs:__imp_RtlAllocateHeap
0x18001874b  mov     rbx, rax
0x18001874e  test    rax, rax
0x180018751  jz      short loc_18001876C
0x180018753  mov     rcx, [rbp+57h+Owner]; Sid
0x180018757  call    cs:__imp_RtlLengthSid
0x18001875d  mov     rdx, [rbp+57h+Owner]; Src
0x180018761  mov     rcx, rbx; void *
0x180018764  mov     r8d, eax; Size
0x180018767  call    memcpy_0
0x18001876c  xor     r8d, r8d; OwnerDefaulted
0x18001876f  mov     rdx, rbx; Owner
0x180018772  mov     rcx, rdi; SecurityDescriptor
0x180018775  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18001877b  lea     r8, [rbp+57h+OwnerDefaulted]; GroupDefaulted
0x18001877f  mov     rcx, rsi; SecurityDescriptor
0x180018782  lea     rdx, [rbp+57h+Owner]; Group
0x180018786  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18001878c  mov     r14d, eax
0x18001878f  test    eax, eax
0x180018791  js      short loc_1800187EA
0x180018793  mov     rcx, [rbp+57h+Owner]; Sid
0x180018797  test    rcx, rcx
0x18001879a  jz      short loc_1800187EA
0x18001879c  call    cs:__imp_RtlLengthSid
0x1800187a2  mov     rcx, gs:60h
0x1800187ab  xor     edx, edx; Flags
0x1800187ad  mov     r8d, eax; Size
0x1800187b0  mov     rcx, [rcx+30h]; HeapHandle
0x1800187b4  call    cs:__imp_RtlAllocateHeap
0x1800187ba  mov     rbx, rax
0x1800187bd  test    rax, rax
0x1800187c0  jz      short loc_1800187DB
0x1800187c2  mov     rcx, [rbp+57h+Owner]; Sid
0x1800187c6  call    cs:__imp_RtlLengthSid
0x1800187cc  mov     rdx, [rbp+57h+Owner]; Src
0x1800187d0  mov     rcx, rbx; void *
0x1800187d3  mov     r8d, eax; Size
0x1800187d6  call    memcpy_0
0x1800187db  xor     r8d, r8d; GroupDefaulted
0x1800187de  mov     rdx, rbx; Group
0x1800187e1  mov     rcx, rdi; SecurityDescriptor
0x1800187e4  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800187ea  mov     rcx, gs:60h
0x1800187f3  mov     r8, rsi; P
0x1800187f6  xor     edx, edx; Flags
0x1800187f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800187fc  call    cs:__imp_RtlFreeHeap
0x180018802  mov     eax, r14d
0x180018805  mov     [r15], rdi
0x180018808  jmp     loc_180018930
0x18001880d  mov     rcx, gs:60h
0x180018816  mov     r8, rsi; P
0x180018819  xor     edx, edx; Flags
0x18001881b  mov     rcx, [rcx+30h]; HeapHandle
0x18001881f  call    cs:__imp_RtlFreeHeap
0x180018825  mov     rcx, gs:60h
0x18001882e  xor     edx, edx; Flags
0x180018830  mov     rcx, [rcx+30h]; HeapHandle
0x180018834  lea     r8d, [rdx+28h]; Size
0x180018838  call    cs:__imp_RtlAllocateHeap
0x18001883e  mov     rdi, rax
0x180018841  test    rax, rax
0x180018844  jz      loc_18001892B
0x18001884a  mov     edx, 1; dwRevision
0x18001884f  mov     rcx, rax; pSecurityDescriptor
0x180018852  call    cs:__imp_InitializeSecurityDescriptor
0x180018858  lea     rax, [rbp+57h+var_58]
0x18001885c  mov     r9d, 220h; SubAuthority1
0x180018862  mov     [rsp+0D0h+Sid], rax; Sid
0x180018867  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18001886b  mov     [rsp+0D0h+SubAuthority7], r12d; SubAuthority7
0x180018870  mov     r8d, 20h ; ' '; SubAuthority0
0x180018876  mov     [rsp+0D0h+SubAuthority6], r12d; SubAuthority6
0x18001887b  mov     dl, r14b; SubAuthorityCount
0x18001887e  mov     [rsp+0D0h+SubAuthority5], r12d; SubAuthority5
0x180018883  mov     [rsp+0D0h+SubAuthority4], r12d; SubAuthority4
0x180018888  mov     [rsp+0D0h+SubAuthority3], r12d; SubAuthority3
0x18001888d  mov     dword ptr [rsp+0D0h+LengthNeeded], r12d; SubAuthority2
0x180018892  call    cs:__imp_RtlAllocateAndInitializeSid
0x180018898  mov     ecx, r14d; SubAuthorityCount
0x18001889b  mov     ebx, eax
0x18001889d  call    cs:__imp_RtlLengthRequiredSid
0x1800188a3  mov     rcx, gs:60h
0x1800188ac  xor     edx, edx; Flags
0x1800188ae  lea     r14d, [rax+14h]
0x1800188b2  mov     rcx, [rcx+30h]; HeapHandle
0x1800188b6  mov     r8d, r14d; Size
0x1800188b9  call    cs:__imp_RtlAllocateHeap
0x1800188bf  mov     rsi, rax
0x1800188c2  test    ebx, ebx
0x1800188c4  js      short loc_18001891C
0x1800188c6  test    rax, rax
0x1800188c9  jz      short loc_18001891C
0x1800188cb  mov     ebx, 2
0x1800188d0  mov     edx, r14d; AclSize
0x1800188d3  mov     r8d, ebx; AclRevision
0x1800188d6  mov     rcx, rax; Acl
0x1800188d9  call    cs:__imp_RtlCreateAcl
0x1800188df  mov     r9, [rbp+57h+var_58]; Sid
0x1800188e3  lea     r8d, [rbx+1]; AccessMask
0x1800188e7  mov     edx, ebx; Revision
0x1800188e9  mov     rcx, rsi; Acl
0x1800188ec  call    cs:__imp_RtlAddAccessAllowedAce
0x1800188f2  test    eax, eax
0x1800188f4  js      short loc_18001891C
0x1800188f6  xor     r9d, r9d; DaclDefaulted
0x1800188f9  mov     r8, rsi; Dacl
0x1800188fc  mov     dl, 1; DaclPresent
0x1800188fe  mov     rcx, rdi; SecurityDescriptor
0x180018901  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180018907  test    eax, eax
0x180018909  js      short loc_18001891C
0x18001890b  mov     rcx, [rbp+57h+var_58]; Sid
0x18001890f  call    cs:__imp_RtlFreeSid
0x180018915  xor     eax, eax
0x180018917  mov     [r15], rdi
0x18001891a  jmp     short loc_180018930
0x18001891c  mov     rcx, [rbp+57h+var_58]; Sid
0x180018920  test    rcx, rcx
0x180018923  jz      short loc_18001892B
0x180018925  call    cs:__imp_RtlFreeSid
0x18001892b  mov     eax, 0C0000017h
0x180018930  mov     rcx, [rbp+57h+var_30]
0x180018934  xor     rcx, rsp; StackCookie
0x180018937  call    __security_check_cookie
0x18001893c  lea     r11, [rsp+0D0h+var_20]
0x180018944  mov     rbx, [r11+40h]
0x180018948  mov     rsi, [r11+48h]
0x18001894c  mov     rsp, r11
0x18001894f  pop     r15
0x180018951  pop     r14
0x180018953  pop     r12
0x180018955  pop     rdi
0x180018956  pop     rbp
0x180018957  retn
```
