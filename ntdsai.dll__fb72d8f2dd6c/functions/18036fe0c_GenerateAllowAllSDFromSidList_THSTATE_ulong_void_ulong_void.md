# GenerateAllowAllSDFromSidList(_THSTATE *,ulong,void * *,ulong *,void * *)

- ea: `0x18036fe0c`
- end: `0x1803700db`
- name: `?GenerateAllowAllSDFromSidList@@YAKPEAU_THSTATE@@KPEAPEAXPEAK1@Z`
- size: `719`
- prototype: `unsigned int __fastcall(struct _THSTATE *, unsigned int, void **, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18036d594`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000ef30`
- `0x180036e3c`
- `0x18036fe0c`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x18036ffc4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18036ffc4`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180370017`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180370053`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180370017`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180370053`
- `ntdll!RtlAddAccessAllowedAce` at `0x18036ff4d`
- `ntdll!RtlAddAccessAllowedAce` at `0x18036ff7e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18036ff4d`
- `ntdll!RtlAddAccessAllowedAce` at `0x18036ff7e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18036ffde`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18036ffde`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18036fff7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18036fff7`
- `ntdll!RtlNtStatusToDosError` at `0x18036ff2b`
- `ntdll!RtlNtStatusToDosError` at `0x18036ff2b`
- `ntdll!RtlLengthSid` at `0x18036fe86`
- `ntdll!RtlLengthSid` at `0x18036feba`
- `ntdll!RtlLengthSid` at `0x18036fe86`
- `ntdll!RtlLengthSid` at `0x18036feba`
- `ntdll!RtlCreateAcl` at `0x18036ff1f`
- `ntdll!RtlCreateAcl` at `0x18036ff1f`

## pseudocode

```c
__int64 __fastcall GenerateAllowAllSDFromSidList(
        struct _THSTATE *a1,
        unsigned int a2,
        void **a3,
        unsigned int *a4,
        void **a5)
{
  int v7; // r14d
  struct _ACL *v8; // r15
  void *v9; // rsi
  void *v10; // rdi
  ULONG UserSIDFromCurrentToken; // ebx
  int v12; // r8d
  int v13; // r9d
  ULONG v14; // eax
  unsigned int v15; // eax
  ULONG v16; // eax
  __int64 i; // r15
  ULONG v18; // eax
  unsigned int v19; // eax
  int Acl; // eax
  __int64 j; // r12
  ULONG AclSize; // [rsp+30h] [rbp-68h] BYREF
  ULONG v24; // [rsp+34h] [rbp-64h]
  int v25; // [rsp+38h] [rbp-60h]
  PSID Sid; // [rsp+40h] [rbp-58h] BYREF
  void *v27; // [rsp+48h] [rbp-50h]
  void *v28; // [rsp+50h] [rbp-48h]
  struct _ACL *v29; // [rsp+58h] [rbp-40h]

  v7 = (int)a1;
  Sid = 0;
  AclSize = 0;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  v28 = 0;
  v10 = 0;
  v27 = 0;
  *a4 = 0;
  *a5 = 0;
  UserSIDFromCurrentToken = GetUserSIDFromCurrentToken(a1, &Sid);
  v24 = UserSIDFromCurrentToken;
  if ( !UserSIDFromCurrentToken )
  {
    v14 = RtlLengthSid(Sid);
    v15 = DsaSafeAdd(8, v14);
    v16 = DsaSafeAdd(v15, 8);
    AclSize = v16;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v25 = i;
      if ( (unsigned int)i >= a2 )
        break;
      v18 = RtlLengthSid(a3[i]);
      v19 = DsaSafeAdd(AclSize, v18);
      v16 = DsaSafeAdd(v19, 8);
      AclSize = v16;
    }
    v8 = (struct _ACL *)THAlloc_(v7, 1, v16, 1, 0, 201855508);
    v29 = v8;
    Acl = RtlCreateAcl(v8, AclSize, 2u);
    if ( Acl < 0 )
      goto LABEL_6;
    Acl = RtlAddAccessAllowedAce(v8, 2u, 0xF07FFu, Sid);
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v25 = j;
      if ( (unsigned int)j >= a2 )
        break;
      if ( Acl < 0 )
        goto LABEL_6;
      Acl = RtlAddAccessAllowedAce(v8, 2u, 0xF07FFu, a3[j]);
    }
    if ( Acl < 0 )
      goto LABEL_6;
    v9 = (void *)THAlloc_(v7, 1, 40, 1, 0, 201855542);
    v28 = v9;
    Acl = RtlCreateSecurityDescriptor(v9, 1u);
    if ( Acl < 0
      || (Acl = RtlSetDaclSecurityDescriptor(v9, 1u, v8, 0), Acl < 0)
      || (Acl = RtlSetOwnerSecurityDescriptor(v9, Sid, 0), Acl < 0)
      || (AclSize = 0,
          RtlAbsoluteToSelfRelativeSD(v9, 0, &AclSize),
          v10 = (void *)THAlloc_(v7, 1, AclSize, 1, 0, 201855580),
          v27 = v10,
          Acl = RtlAbsoluteToSelfRelativeSD(v9, v10, &AclSize),
          Acl < 0) )
    {
LABEL_6:
      UserSIDFromCurrentToken = RtlNtStatusToDosError(Acl);
      v24 = UserSIDFromCurrentToken;
    }
    else
    {
      *a5 = v10;
      *a4 = AclSize;
      v10 = 0;
      v27 = 0;
    }
  }
  if ( v9 )
    THFreeAux(v7, (_DWORD)v9, v12, v13, 201855594);
  if ( v8 )
    THFreeAux(v7, (_DWORD)v8, v12, v13, 201855598);
  if ( v10 )
    THFreeAux(v7, (_DWORD)v10, v12, v13, 201855602);
  return UserSIDFromCurrentToken;
}

```

## disassembly

```asm
0x18036fe0c  mov     rax, rsp
0x18036fe0f  mov     [rax+20h], r9
0x18036fe13  mov     [rax+18h], r8
0x18036fe17  mov     [rax+8], rcx
0x18036fe1b  push    rbx
0x18036fe1c  push    rsi
0x18036fe1d  push    rdi
0x18036fe1e  push    r12
0x18036fe20  push    r13
0x18036fe22  push    r14
0x18036fe24  push    r15
0x18036fe26  sub     rsp, 60h
0x18036fe2a  mov     r12, r8
0x18036fe2d  mov     r13d, edx
0x18036fe30  mov     r14, rcx
0x18036fe33  xor     ecx, ecx
0x18036fe35  mov     [rax-58h], rcx
0x18036fe39  mov     [rax-68h], ecx
0x18036fe3c  mov     r15d, ecx
0x18036fe3f  mov     [rax-40h], rcx
0x18036fe43  mov     esi, ecx
0x18036fe45  mov     [rax-48h], rcx
0x18036fe49  mov     edi, ecx
0x18036fe4b  mov     [rax-50h], rcx
0x18036fe4f  mov     [r9], ecx
0x18036fe52  mov     rax, [rsp+98h+arg_20]
0x18036fe5a  mov     [rax], rcx
0x18036fe5d  lea     rdx, [rsp+98h+Sid]
0x18036fe62  mov     rcx, r14
0x18036fe65  call    GetUserSIDFromCurrentToken
0x18036fe6a  mov     ebx, eax
0x18036fe6c  mov     [rsp+98h+var_64], eax
0x18036fe70  test    eax, eax
0x18036fe72  jnz     loc_180370081
0x18036fe78  lea     r15d, [rdi+8]
0x18036fe7c  mov     [rsp+98h+AclSize], r15d
0x18036fe81  mov     rcx, [rsp+98h+Sid]; Sid
0x18036fe86  call    cs:__imp_RtlLengthSid
0x18036fe8c  mov     edx, eax
0x18036fe8e  mov     ecx, [rsp+98h+AclSize]
0x18036fe92  call    DsaSafeAdd
0x18036fe97  mov     ecx, eax
0x18036fe99  mov     [rsp+98h+AclSize], ecx
0x18036fe9d  mov     edx, r15d
0x18036fea0  call    DsaSafeAdd
0x18036fea5  mov     [rsp+98h+AclSize], eax
0x18036fea9  xor     r15d, r15d
0x18036feac  mov     [rsp+98h+var_60], r15d
0x18036feb1  cmp     r15d, r13d
0x18036feb4  jnb     short loc_18036FEE4
0x18036feb6  mov     rcx, [r12+r15*8]; Sid
0x18036feba  call    cs:__imp_RtlLengthSid
0x18036fec0  mov     edx, eax
0x18036fec2  mov     ecx, [rsp+98h+AclSize]
0x18036fec6  call    DsaSafeAdd
0x18036fecb  mov     ecx, eax
0x18036fecd  mov     [rsp+98h+AclSize], ecx
0x18036fed1  mov     edx, 8
0x18036fed6  call    DsaSafeAdd
0x18036fedb  mov     [rsp+98h+AclSize], eax
0x18036fedf  inc     r15d
0x18036fee2  jmp     short loc_18036FEAC
0x18036fee4  mov     r8d, eax
0x18036fee7  mov     [rsp+98h+var_70], 0C081214h
0x18036feef  mov     [rsp+98h+var_78], 0
0x18036fef7  mov     edx, 1
0x18036fefc  mov     r9d, edx
0x18036feff  mov     rcx, r14
0x18036ff02  call    THAlloc_
0x18036ff07  mov     r15, rax
0x18036ff0a  mov     [rsp+98h+var_40], rax
0x18036ff0f  mov     r12d, 2
0x18036ff15  mov     r8d, r12d; AclRevision
0x18036ff18  mov     edx, [rsp+98h+AclSize]; AclSize
0x18036ff1c  mov     rcx, rax; Acl
0x18036ff1f  call    cs:__imp_RtlCreateAcl
0x18036ff25  test    eax, eax
0x18036ff27  jns     short loc_18036FF3C
0x18036ff29  mov     ecx, eax; Status
0x18036ff2b  call    cs:__imp_RtlNtStatusToDosError
0x18036ff31  mov     ebx, eax
0x18036ff33  mov     [rsp+98h+var_64], eax
0x18036ff37  jmp     loc_180370081
0x18036ff3c  mov     r9, [rsp+98h+Sid]; Sid
0x18036ff41  mov     r8d, 0F07FFh; AccessMask
0x18036ff47  mov     edx, r12d; Revision
0x18036ff4a  mov     rcx, r15; Acl
0x18036ff4d  call    cs:__imp_RtlAddAccessAllowedAce
0x18036ff53  xor     r12d, r12d
0x18036ff56  mov     [rsp+98h+var_60], r12d
0x18036ff5b  cmp     r12d, r13d
0x18036ff5e  jnb     short loc_18036FF89
0x18036ff60  test    eax, eax
0x18036ff62  js      short loc_18036FF29
0x18036ff64  mov     rax, [rsp+98h+arg_10]
0x18036ff6c  mov     r9, [rax+r12*8]; Sid
0x18036ff70  mov     edx, 2; Revision
0x18036ff75  mov     r8d, 0F07FFh; AccessMask
0x18036ff7b  mov     rcx, r15; Acl
0x18036ff7e  call    cs:__imp_RtlAddAccessAllowedAce
0x18036ff84  inc     r12d
0x18036ff87  jmp     short loc_18036FF56
0x18036ff89  test    eax, eax
0x18036ff8b  js      short loc_18036FF29
0x18036ff8d  mov     [rsp+98h+var_70], 0C081236h
0x18036ff95  mov     [rsp+98h+var_78], 0
0x18036ff9d  mov     r12d, 1
0x18036ffa3  mov     r9d, r12d
0x18036ffa6  lea     r8d, [r12+27h]
0x18036ffab  mov     edx, r12d
0x18036ffae  mov     rcx, r14
0x18036ffb1  call    THAlloc_
0x18036ffb6  mov     rsi, rax
0x18036ffb9  mov     [rsp+98h+var_48], rax
0x18036ffbe  mov     edx, r12d; Revision
0x18036ffc1  mov     rcx, rax; SecurityDescriptor
0x18036ffc4  call    cs:__imp_RtlCreateSecurityDescriptor
0x18036ffca  test    eax, eax
0x18036ffcc  js      loc_18036FF29
0x18036ffd2  xor     r9d, r9d; DaclDefaulted
0x18036ffd5  mov     r8, r15; Dacl
0x18036ffd8  mov     dl, r12b; DaclPresent
0x18036ffdb  mov     rcx, rsi; SecurityDescriptor
0x18036ffde  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18036ffe4  test    eax, eax
0x18036ffe6  js      loc_18036FF29
0x18036ffec  xor     r8d, r8d; OwnerDefaulted
0x18036ffef  mov     rdx, [rsp+98h+Sid]; Owner
0x18036fff4  mov     rcx, rsi; SecurityDescriptor
0x18036fff7  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18036fffd  test    eax, eax
0x18036ffff  js      loc_18036FF29
0x180370005  mov     [rsp+98h+AclSize], 0
0x18037000d  lea     r8, [rsp+98h+AclSize]; BufferLength
0x180370012  xor     edx, edx; SelfRelativeSecurityDescriptor
0x180370014  mov     rcx, rsi; AbsoluteSecurityDescriptor
0x180370017  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18037001d  mov     r8d, [rsp+98h+AclSize]
0x180370022  mov     [rsp+98h+var_70], 0C08125Ch
0x18037002a  mov     [rsp+98h+var_78], 0
0x180370032  mov     r9d, r12d
0x180370035  mov     edx, r12d
0x180370038  mov     rcx, r14
0x18037003b  call    THAlloc_
0x180370040  mov     rdi, rax
0x180370043  mov     [rsp+98h+var_50], rax
0x180370048  lea     r8, [rsp+98h+AclSize]; BufferLength
0x18037004d  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x180370050  mov     rcx, rsi; AbsoluteSecurityDescriptor
0x180370053  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180370059  test    eax, eax
0x18037005b  js      loc_18036FF29
0x180370061  mov     rax, [rsp+98h+arg_20]
0x180370069  mov     [rax], rdi
0x18037006c  mov     eax, [rsp+98h+AclSize]
0x180370070  mov     rcx, [rsp+98h+arg_18]
0x180370078  mov     [rcx], eax
0x18037007a  xor     edi, edi
0x18037007c  mov     [rsp+98h+var_50], rdi
0x180370081  test    rsi, rsi
0x180370084  jz      short loc_180370099
0x180370086  mov     [rsp+98h+var_78], 0C08126Ah
0x18037008e  mov     rdx, rsi
0x180370091  mov     rcx, r14
0x180370094  call    THFreeAux
0x180370099  test    r15, r15
0x18037009c  jz      short loc_1803700B1
0x18037009e  mov     [rsp+98h+var_78], 0C08126Eh
0x1803700a6  mov     rdx, r15
0x1803700a9  mov     rcx, r14
0x1803700ac  call    THFreeAux
0x1803700b1  test    rdi, rdi
0x1803700b4  jz      short loc_1803700C9
0x1803700b6  mov     [rsp+98h+var_78], 0C081272h
0x1803700be  mov     rdx, rdi
0x1803700c1  mov     rcx, r14
0x1803700c4  call    THFreeAux
0x1803700c9  mov     eax, ebx
0x1803700cb  add     rsp, 60h
0x1803700cf  pop     r15
0x1803700d1  pop     r14
0x1803700d3  pop     r13
0x1803700d5  pop     r12
0x1803700d7  pop     rdi
0x1803700d8  pop     rsi
0x1803700d9  pop     rbx
0x1803700da  retn
0x180473cd3  push    rbp
0x180473cd5  sub     rsp, 30h
0x180473cd9  mov     rbp, rdx
0x180473cdc  mov     rdx, [rbp+50h]
0x180473ce0  test    rdx, rdx
0x180473ce3  jz      short loc_180473D01
0x180473ce5  mov     [rsp+38h+var_18], 0C08126Ah
0x180473ced  mov     rcx, [rbp+0A0h]
0x180473cf4  call    THFreeAux
0x180473cf9  mov     qword ptr [rbp+50h], 0
0x180473d01  mov     rdx, [rbp+58h]
0x180473d05  test    rdx, rdx
0x180473d08  jz      short loc_180473D26
0x180473d0a  mov     [rsp+38h+var_18], 0C08126Eh
0x180473d12  mov     rcx, [rbp+0A0h]
0x180473d19  call    THFreeAux
0x180473d1e  mov     qword ptr [rbp+58h], 0
0x180473d26  mov     rdx, [rbp+48h]
0x180473d2a  test    rdx, rdx
0x180473d2d  jz      short loc_180473D4B
0x180473d2f  mov     [rsp+38h+var_18], 0C081272h
0x180473d37  mov     rcx, [rbp+0A0h]
0x180473d3e  call    THFreeAux
0x180473d43  mov     qword ptr [rbp+48h], 0
0x180473d4b  add     rsp, 30h
0x180473d4f  pop     rbp
0x180473d50  retn
```
