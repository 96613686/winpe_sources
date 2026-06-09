# SetDefaultOwner

- ea: `0x180122de4`
- end: `0x1801236cc`
- name: `SetDefaultOwner`
- size: `2280`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180121330`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18001e090`
- `0x180035f7c`
- `0x18011cc00`
- `0x18011cddc`
- `0x18011fcd4`
- `0x180122de4`
- `0x180172b30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180123315`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180123315`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180122f5e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1801230ab`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180122f5e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1801230ab`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1801234f8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1801234f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123221`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123275`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801232ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801232fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123221`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123275`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801232ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801232fd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180123524`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180123524`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180123544`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180123589`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180123544`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180123589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801230b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012327f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801230b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012327f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123593`
- `ntdll!RtlAllocateHeap` at `0x180123564`
- `ntdll!RtlAllocateHeap` at `0x180123564`
- `ntdll!RtlFreeHeap` at `0x18012369a`
- `ntdll!RtlFreeHeap` at `0x18045e67a`
- `ntdll!RtlFreeHeap` at `0x18012369a`
- `ntdll!RtlFreeHeap` at `0x18045e67a`

## pseudocode

```c
__int64 __fastcall SetDefaultOwner(
        __int64 a1,
        void *a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        unsigned int a6,
        PSECURITY_DESCRIPTOR *a7,
        DWORD *a8)
{
  __int64 v9; // rbx
  void **v10; // r12
  PSID *v11; // r13
  PSID v12; // rdi
  int v13; // esi
  void *v14; // r14
  __int64 v16; // r9
  DWORD LastError; // ebx
  int v18; // r8d
  int v19; // r9d
  _DWORD *v20; // r13
  int v21; // r13d
  __int64 v22; // rdx
  __int64 v23; // rax
  PSID *v24; // rbx
  int v25; // r13d
  int v26; // r13d
  int v27; // r13d
  void *v28; // rsi
  bool v29; // zf
  void **v30; // rax
  void **v31; // rax
  void *v32; // rdx
  PSECURITY_DESCRIPTOR v33; // rdi
  PVOID *v34; // r14
  PVOID Heap; // rax
  void *v36; // [rsp+68h] [rbp-130h]
  PSID *v37; // [rsp+70h] [rbp-128h]
  DWORD ReturnLength; // [rsp+78h] [rbp-120h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+80h] [rbp-118h]
  PSECURITY_DESCRIPTOR *v40; // [rsp+88h] [rbp-110h]
  int v41; // [rsp+90h] [rbp-108h]
  DWORD dwPrimaryGroupSize; // [rsp+94h] [rbp-104h] BYREF
  DWORD dwOwnerSize; // [rsp+98h] [rbp-100h] BYREF
  DWORD dwSaclSize; // [rsp+9Ch] [rbp-FCh] BYREF
  DWORD dwDaclSize; // [rsp+A0h] [rbp-F8h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+A4h] [rbp-F4h] BYREF
  PACL pDacl; // [rsp+A8h] [rbp-F0h]
  PACL pSacl; // [rsp+B0h] [rbp-E8h]
  HANDLE TokenHandle; // [rsp+B8h] [rbp-E0h]
  PSID pPrimaryGroup; // [rsp+C0h] [rbp-D8h]
  void **v51; // [rsp+C8h] [rbp-D0h] BYREF
  void *Src; // [rsp+D0h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-C0h] BYREF
  _BYTE *v54; // [rsp+E0h] [rbp-B8h]
  LPDWORD lpdwBufferLength; // [rsp+E8h] [rbp-B0h]
  __int64 v56; // [rsp+F0h] [rbp-A8h]
  PSECURITY_DESCRIPTOR *v57; // [rsp+F8h] [rbp-A0h]
  __int128 v58; // [rsp+100h] [rbp-98h] BYREF
  __int128 v59; // [rsp+110h] [rbp-88h]
  _BYTE v60[32]; // [rsp+120h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+140h] [rbp-58h] BYREF
  int v62; // [rsp+148h] [rbp-50h]
  int v63; // [rsp+14Ch] [rbp-4Ch]

  TokenHandle = a4;
  pSelfRelativeSecurityDescriptor = a2;
  v9 = a5;
  v56 = a1;
  v40 = a7;
  v57 = a7;
  lpdwBufferLength = a8;
  ReturnLength = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  Src = 0;
  memset(v60, 0, 28);
  v10 = 0;
  v51 = 0;
  v58 = 0;
  v59 = 0;
  v53 = 0;
  *a7 = 0;
  *a8 = 0;
  if ( !a1 || !*(_QWORD *)(a1 + 5576) )
    return 8430;
  v11 = 0;
  v37 = 0;
  v36 = 0;
  pAbsoluteSecurityDescriptor = 0;
  pDacl = 0;
  pSacl = 0;
  pPrimaryGroup = 0;
  v12 = 0;
  v54 = 0;
  v13 = 0;
  v14 = 0;
  MakeAbsoluteSD(
    a2,
    0,
    &dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    &dwSaclSize,
    0,
    &dwOwnerSize,
    0,
    &dwPrimaryGroupSize);
  if ( dwOwnerSize )
    return 0;
  pAbsoluteSecurityDescriptor = (PSECURITY_DESCRIPTOR)THAlloc_(a1, 1, dwAbsoluteSecurityDescriptorSize, 1, 0, 52562800);
  pDacl = (PACL)THAlloc_(a1, 1, dwDaclSize, 1, 0, 52562801);
  pSacl = (PACL)THAlloc_(a1, 1, dwSaclSize, 1, 0, 52562802);
  pPrimaryGroup = (PSID)THAlloc_(a1, 1, dwPrimaryGroupSize, 1, 0, 52562803);
  if ( !MakeAbsoluteSD(
          pSelfRelativeSecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          &dwAbsoluteSecurityDescriptorSize,
          pDacl,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          0,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    LastError = GetLastError();
LABEL_83:
    v28 = v36;
    goto LABEL_84;
  }
  if ( a5 && (v20 = *(_DWORD **)(a5 + 40)) != 0 )
  {
    v21 = *v20 & 0xF;
    v22 = a6;
  }
  else
  {
    v22 = a6;
    if ( a6 == dword_18052B2C8 )
    {
      v21 = 1;
    }
    else if ( a6 == dword_18052B2F8 )
    {
      v21 = 4;
    }
    else
    {
      v21 = 8;
      if ( a6 == dword_18052B288 )
        v21 = 2;
    }
  }
  if ( v21 == 8 )
  {
    if ( a5 && (v23 = *(_QWORD *)(a5 + 40)) != 0 )
    {
      if ( !*(_DWORD *)gfADAM )
        v9 = *(_QWORD *)(v23 + 16);
      Src = (void *)(*(_QWORD *)v9 + 24LL);
    }
    else
    {
      LastError = GetSidForNC(a1, v22, &Src, v16);
      if ( LastError )
        goto LABEL_82;
    }
    v54 = v60;
    MakeSid(Src);
  }
  LastError = GetAuthzContextHandle(a1, &v53);
  if ( LastError )
    goto LABEL_82;
  if ( (*(_DWORD *)(a1 + 5612) & 0x200000) != 0 )
  {
    LastError = AuthzGetInfoHelper(a1, v53, 1, &v51);
    v10 = v51;
    if ( !LastError )
      goto LABEL_34;
LABEL_82:
    v11 = v37;
    goto LABEL_83;
  }
  GetTokenInformation(TokenHandle, TokenOwner, 0, 0, &ReturnLength);
  v24 = (PSID *)THAlloc_(a1, 1, ReturnLength, 1, 0, 52562883);
  v37 = v24;
  if ( !GetTokenInformation(TokenHandle, TokenOwner, v24, ReturnLength, &ReturnLength)
    || (GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength),
        v36 = (void *)THAlloc_(a1, 1, ReturnLength, 1, 0, 52562899),
        !GetTokenInformation(TokenHandle, TokenUser, v36, ReturnLength, &ReturnLength)) )
  {
    LastError = GetLastError();
    goto LABEL_82;
  }
  if ( EqualSid(*v24, gpBuiltinAdminSid) )
    v13 = 16;
  v41 = v13;
LABEL_34:
  *(_QWORD *)&v58 = gpDomainAdminSid;
  *((_QWORD *)&v58 + 1) = gpEnterpriseAdminSid;
  *(_QWORD *)&v59 = gpSchemaAdminSid;
  *((_QWORD *)&v59 + 1) = v54;
  LastError = CheckGroupMembershipAnyClient(a1, v53, &v58, 4, &pSelfRelativeSecurityDescriptor);
  if ( LastError )
    goto LABEL_82;
  if ( (_DWORD)pSelfRelativeSecurityDescriptor )
  {
    v13 |= 4u;
    v41 = v13;
  }
  if ( HIDWORD(pSelfRelativeSecurityDescriptor) )
  {
    v13 |= 1u;
    v41 = v13;
  }
  if ( v62 )
  {
    v13 |= 2u;
    v41 = v13;
  }
  if ( v63 )
  {
    v13 |= 8u;
    v41 = v13;
  }
  v25 = v21 - 1;
  if ( !v25 )
  {
    if ( (v13 & 4) == 0 )
      goto LABEL_68;
LABEL_65:
    v12 = gpDomainAdminSid;
    goto LABEL_54;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    if ( (v13 & 2) != 0 )
    {
      v12 = gpSchemaAdminSid;
      goto LABEL_54;
    }
    goto LABEL_63;
  }
  v27 = v26 - 2;
  if ( !v27 )
  {
LABEL_63:
    if ( (v13 & 1) != 0 )
    {
LABEL_53:
      v12 = gpEnterpriseAdminSid;
LABEL_54:
      v14 = v12;
      goto LABEL_49;
    }
    if ( (v13 & 4) == 0 )
      goto LABEL_55;
    goto LABEL_65;
  }
  if ( v27 != 4 )
  {
LABEL_49:
    v28 = v36;
LABEL_50:
    v11 = v37;
    goto LABEL_51;
  }
  if ( (v13 & 8) != 0 )
  {
    v12 = v54;
    v14 = v54;
    goto LABEL_49;
  }
LABEL_68:
  if ( (v13 & 1) != 0 )
    goto LABEL_53;
LABEL_55:
  v29 = (v13 & 0x10) == 0;
  v28 = v36;
  if ( !v29 )
  {
    v30 = (void **)v36;
    if ( __CFSHR__(*(_DWORD *)(a1 + 5612), 22) )
      v30 = v10;
    v12 = *v30;
    if ( __CFSHR__(*(_DWORD *)(a1 + 5612), 22) )
      v14 = *v10;
    else
      v14 = 0;
    goto LABEL_50;
  }
  v11 = v37;
  v31 = v37;
  if ( __CFSHR__(*(_DWORD *)(a1 + 5612), 22) )
    v31 = v10;
  v12 = *v31;
  if ( __CFSHR__(*(_DWORD *)(a1 + 5612), 22) )
    v14 = *v10;
  else
    v14 = 0;
LABEL_51:
  if ( !v12 )
  {
    LastError = 1337;
LABEL_84:
    v33 = pAbsoluteSecurityDescriptor;
    goto LABEL_85;
  }
  v32 = v12;
  v33 = pAbsoluteSecurityDescriptor;
  if ( SetSecurityDescriptorOwner(pAbsoluteSecurityDescriptor, v32, 1)
    && (!v14 || SetSecurityDescriptorGroup(v33, v14, 1)) )
  {
    v34 = v40;
    MakeSelfRelativeSD(v33, *v40, lpdwBufferLength);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *lpdwBufferLength);
    *v34 = Heap;
    if ( Heap )
    {
      if ( !MakeSelfRelativeSD(v33, Heap, lpdwBufferLength) )
        LastError = GetLastError();
    }
    else
    {
      LastError = 8;
    }
    goto LABEL_86;
  }
  LastError = GetLastError();
LABEL_85:
  v34 = v40;
LABEL_86:
  if ( v33 )
    THFreeAux(a1, (_DWORD)v33, v18, v19, 52563068);
  if ( pDacl )
    THFreeAux(a1, (_DWORD)pDacl, v18, v19, 52563071);
  if ( pSacl )
    THFreeAux(a1, (_DWORD)pSacl, v18, v19, 52563074);
  if ( pPrimaryGroup )
    THFreeAux(a1, (_DWORD)pPrimaryGroup, v18, v19, 52563077);
  if ( (*(_DWORD *)(a1 + 5612) & 0x200000) != 0 )
  {
    if ( v10 )
      THFreeAux(a1, (_DWORD)v10, v18, v19, 52563081);
  }
  else
  {
    if ( v28 )
      THFreeAux(a1, (_DWORD)v28, v18, v19, 52563086);
    if ( v11 )
      THFreeAux(a1, (_DWORD)v11, v18, v19, 52563089);
  }
  if ( LastError )
  {
    if ( *v34 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v34);
  }
  return LastError;
}

```

## disassembly

```asm
0x180122de4  mov     r11, rsp
0x180122de7  push    rbx
0x180122de8  push    rsi
0x180122de9  push    rdi
0x180122dea  push    r12
0x180122dec  push    r13
0x180122dee  push    r14
0x180122df0  push    r15
0x180122df2  sub     rsp, 160h
0x180122df9  mov     rax, cs:__security_cookie
0x180122e00  xor     rax, rsp
0x180122e03  mov     [rsp+198h+var_48], rax
0x180122e0b  mov     [rsp+198h+TokenHandle], r9
0x180122e13  mov     rax, rdx
0x180122e16  mov     [rsp+198h+pSelfRelativeSecurityDescriptor], rdx
0x180122e1e  mov     r15, rcx
0x180122e21  mov     rbx, [rsp+198h+arg_20]
0x180122e29  mov     [rsp+198h+var_A8], rcx
0x180122e31  mov     rcx, [rsp+198h+arg_30]
0x180122e39  mov     [rsp+198h+var_110], rcx
0x180122e41  mov     [rsp+198h+var_A0], rcx
0x180122e49  mov     rdx, [rsp+198h+arg_38]
0x180122e51  mov     [rsp+198h+lpdwBufferLength], rdx
0x180122e59  xor     r9d, r9d; pDacl
0x180122e5c  mov     [rsp+198h+ReturnLength], r9d
0x180122e61  mov     [r11-0F4h], r9d
0x180122e68  mov     [r11-0F8h], r9d
0x180122e6f  mov     [r11-0FCh], r9d
0x180122e76  mov     [r11-100h], r9d
0x180122e7d  mov     [r11-104h], r9d
0x180122e84  mov     [r11-0C8h], r9
0x180122e8b  xorps   xmm0, xmm0
0x180122e8e  movups  xmmword ptr [r11-78h], xmm0
0x180122e93  movups  xmmword ptr [r11-6Ch], xmm0
0x180122e98  mov     r12d, r9d
0x180122e9b  mov     [r11-0D0h], r9
0x180122ea2  movups  [rsp+198h+var_98], xmm0
0x180122eaa  movups  [rsp+198h+var_88], xmm0
0x180122eb2  mov     [r11-0C0h], r9
0x180122eb9  mov     [rcx], r9
0x180122ebc  mov     [rdx], r9d
0x180122ebf  test    r15, r15
0x180122ec2  jz      loc_1801236A4
0x180122ec8  cmp     [r15+15C8h], r9
0x180122ecf  jz      loc_1801236A4
0x180122ed5  mov     r13d, r9d
0x180122ed8  mov     [rsp+198h+var_128], r9
0x180122edd  mov     [rsp+198h+var_130], r9
0x180122ee2  mov     [rsp+198h+var_138], r9d
0x180122ee7  mov     [r11-118h], r9
0x180122eee  mov     [r11-0F0h], r9
0x180122ef5  mov     [r11-0E8h], r9
0x180122efc  mov     [r11-0D8h], r9
0x180122f03  mov     edi, r9d
0x180122f06  mov     [r11-0B8h], r9
0x180122f0d  mov     esi, r9d
0x180122f10  mov     r14d, r9d
0x180122f13  lea     rcx, [r11-104h]
0x180122f1a  mov     [rsp+198h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x180122f1f  mov     [rsp+198h+pPrimaryGroup], r9; pPrimaryGroup
0x180122f24  lea     rcx, [r11-100h]
0x180122f2b  mov     [rsp+198h+lpdwOwnerSize], rcx; lpdwOwnerSize
0x180122f30  mov     [rsp+198h+pOwner], r9; pOwner
0x180122f35  lea     rcx, [r11-0FCh]
0x180122f3c  mov     [rsp+198h+lpdwSaclSize], rcx; lpdwSaclSize
0x180122f41  mov     [rsp+198h+pSacl], r9; pSacl
0x180122f46  lea     rcx, [r11-0F8h]
0x180122f4d  mov     [rsp+198h+lpdwDaclSize], rcx; lpdwDaclSize
0x180122f52  lea     r8, [r11-0F4h]; lpdwAbsoluteSecurityDescriptorSize
0x180122f59  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180122f5b  mov     rcx, rax; pSelfRelativeSecurityDescriptor
0x180122f5e  call    cs:__imp_MakeAbsoluteSD
0x180122f64  cmp     [rsp+198h+dwOwnerSize], esi
0x180122f6b  jz      short loc_180122F74
0x180122f6d  xor     eax, eax
0x180122f6f  jmp     loc_1801236A9
0x180122f74  mov     r8d, [rsp+198h+dwAbsoluteSecurityDescriptorSize]
0x180122f7c  mov     dword ptr [rsp+198h+pSacl], 3220B70h
0x180122f84  mov     dword ptr [rsp+198h+lpdwDaclSize], 0
0x180122f8c  mov     eax, 1
0x180122f91  mov     r9d, eax
0x180122f94  mov     edx, eax
0x180122f96  mov     rcx, r15
0x180122f99  call    THAlloc_
0x180122f9e  mov     [rsp+198h+pAbsoluteSecurityDescriptor], rax
0x180122fa6  mov     r8d, [rsp+198h+dwDaclSize]
0x180122fae  mov     dword ptr [rsp+198h+pSacl], 3220B71h
0x180122fb6  mov     dword ptr [rsp+198h+lpdwDaclSize], 0
0x180122fbe  mov     eax, 1
0x180122fc3  mov     r9d, eax
0x180122fc6  mov     edx, eax
0x180122fc8  mov     rcx, r15
0x180122fcb  call    THAlloc_
0x180122fd0  mov     [rsp+198h+pDacl], rax
0x180122fd8  mov     r8d, [rsp+198h+dwSaclSize]
0x180122fe0  mov     dword ptr [rsp+198h+pSacl], 3220B72h
0x180122fe8  mov     dword ptr [rsp+198h+lpdwDaclSize], 0
0x180122ff0  mov     eax, 1
0x180122ff5  mov     r9d, eax
0x180122ff8  mov     edx, eax
0x180122ffa  mov     rcx, r15
0x180122ffd  call    THAlloc_
0x180123002  mov     [rsp+198h+var_E8], rax
0x18012300a  mov     r8d, [rsp+198h+dwPrimaryGroupSize]
0x180123012  mov     dword ptr [rsp+198h+pSacl], 3220B73h
0x18012301a  mov     dword ptr [rsp+198h+lpdwDaclSize], 0
0x180123022  mov     eax, 1
0x180123027  mov     r9d, eax
0x18012302a  mov     edx, eax
0x18012302c  mov     rcx, r15
0x18012302f  call    THAlloc_
0x180123034  mov     [rsp+198h+var_D8], rax
0x18012303c  lea     rcx, [rsp+198h+dwPrimaryGroupSize]
0x180123044  mov     [rsp+198h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x180123049  mov     [rsp+198h+pPrimaryGroup], rax; pPrimaryGroup
0x18012304e  lea     rax, [rsp+198h+dwOwnerSize]
0x180123056  mov     [rsp+198h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18012305b  mov     [rsp+198h+pOwner], 0; pOwner
0x180123064  lea     rax, [rsp+198h+dwSaclSize]
0x18012306c  mov     [rsp+198h+lpdwSaclSize], rax; lpdwSaclSize
0x180123071  mov     rax, [rsp+198h+var_E8]
0x180123079  mov     [rsp+198h+pSacl], rax; pSacl
0x18012307e  lea     rax, [rsp+198h+dwDaclSize]
0x180123086  mov     [rsp+198h+lpdwDaclSize], rax; lpdwDaclSize
0x18012308b  mov     r9, [rsp+198h+pDacl]; pDacl
0x180123093  lea     r8, [rsp+198h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18012309b  mov     rdx, [rsp+198h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1801230a3  mov     rcx, [rsp+198h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1801230ab  call    cs:__imp_MakeAbsoluteSD
0x1801230b1  test    eax, eax
0x1801230b3  jnz     short loc_1801230C6
0x1801230b5  call    cs:__imp_GetLastError
0x1801230bb  mov     ebx, eax
0x1801230bd  mov     [rsp+198h+var_138], eax
0x1801230c1  jmp     loc_1801235A6
0x1801230c6  test    rbx, rbx
0x1801230c9  jz      short loc_1801230E5
0x1801230cb  mov     r13, [rbx+28h]
0x1801230cf  test    r13, r13
0x1801230d2  jz      short loc_1801230E5
0x1801230d4  mov     r13d, [r13+0]
0x1801230d8  and     r13d, 0Fh
0x1801230dc  mov     edx, [rsp+198h+arg_28]
0x1801230e3  jmp     short loc_18012311F
0x1801230e5  mov     edx, [rsp+198h+arg_28]
0x1801230ec  cmp     edx, cs:dword_18052B2C8
0x1801230f2  jnz     short loc_1801230FC
0x1801230f4  mov     r13d, 1
0x1801230fa  jmp     short loc_18012311F
0x1801230fc  cmp     edx, cs:dword_18052B2F8
0x180123102  jnz     short loc_18012310C
0x180123104  mov     r13d, 4
0x18012310a  jmp     short loc_18012311F
0x18012310c  mov     eax, 2
0x180123111  lea     r13d, [rax+6]
0x180123115  cmp     edx, cs:dword_18052B288
0x18012311b  cmovz   r13d, eax
0x18012311f  cmp     r13d, 8
0x180123123  jnz     short loc_18012319E
0x180123125  test    rbx, rbx
0x180123128  jz      short loc_180123151
0x18012312a  mov     rax, [rbx+28h]
0x18012312e  test    rax, rax
0x180123131  jz      short loc_180123151
0x180123133  cmp     cs:gfADAM, 0
0x18012313a  jnz     short loc_180123140
0x18012313c  mov     rbx, [rax+10h]
0x180123140  mov     rax, [rbx]
0x180123143  add     rax, 18h
0x180123147  mov     [rsp+198h+Src], rax
0x18012314f  jmp     short loc_18012316F
0x180123151  lea     r8, [rsp+198h+Src]
0x180123159  mov     rcx, r15
0x18012315c  call    GetSidForNC
0x180123161  mov     ebx, eax
0x180123163  mov     [rsp+198h+var_138], eax
0x180123167  test    eax, eax
0x180123169  jnz     loc_1801235A1
0x18012316f  lea     rax, [rsp+198h+var_78]
0x180123177  mov     [rsp+198h+var_B8], rax
0x18012317f  lea     r9, [rsp+198h+ReturnLength]
0x180123184  lea     r8, [rsp+198h+var_78]
0x18012318c  mov     edx, 200h
0x180123191  mov     rcx, [rsp+198h+Src]; Src
0x180123199  call    MakeSid
0x18012319e  lea     rdx, [rsp+198h+var_C0]
0x1801231a6  mov     rcx, r15
0x1801231a9  call    GetAuthzContextHandle
0x1801231ae  mov     ebx, eax
0x1801231b0  mov     [rsp+198h+var_138], eax
0x1801231b4  test    eax, eax
0x1801231b6  jnz     loc_1801235A1
0x1801231bc  test    dword ptr [r15+15ECh], 200000h
0x1801231c7  jz      short loc_180123205
0x1801231c9  lea     r9, [rsp+198h+var_D0]
0x1801231d1  lea     r8d, [rax+1]
0x1801231d5  mov     rdx, [rsp+198h+var_C0]
0x1801231dd  mov     rcx, r15
0x1801231e0  call    AuthzGetInfoHelper
0x1801231e5  mov     ebx, eax
0x1801231e7  mov     [rsp+198h+var_138], eax
0x1801231eb  mov     r12, [rsp+198h+var_D0]
0x1801231f3  test    eax, eax
0x1801231f5  jnz     loc_1801235A1
0x1801231fb  mov     rbx, [rsp+198h+var_128]
0x180123200  jmp     loc_18012332C
0x180123205  lea     rax, [rsp+198h+ReturnLength]
0x18012320a  mov     [rsp+198h+lpdwDaclSize], rax; ReturnLength
0x18012320f  xor     r9d, r9d; TokenInformationLength
0x180123212  xor     r8d, r8d; TokenInformation
0x180123215  lea     edx, [r9+4]; TokenInformationClass
0x180123219  mov     rcx, [rsp+198h+TokenHandle]; TokenHandle
0x180123221  call    cs:__imp_GetTokenInformation
0x180123227  mov     r8d, [rsp+198h+ReturnLength]
0x18012322c  mov     dword ptr [rsp+198h+pSacl], 3220BC3h
0x180123234  mov     dword ptr [rsp+198h+lpdwDaclSize], 0
0x18012323c  mov     eax, 1
0x180123241  mov     r9d, eax
0x180123244  mov     edx, eax
0x180123246  mov     rcx, r15
0x180123249  call    THAlloc_
0x18012324e  mov     rbx, rax
0x180123251  mov     [rsp+198h+var_128], rax
0x180123256  lea     rax, [rsp+198h+ReturnLength]
0x18012325b  mov     [rsp+198h+lpdwDaclSize], rax; ReturnLength
0x180123260  mov     r9d, [rsp+198h+ReturnLength]; TokenInformationLength
0x180123265  mov     r8, rbx; TokenInformation
0x180123268  mov     edx, 4; TokenInformationClass
0x18012326d  mov     rcx, [rsp+198h+TokenHandle]; TokenHandle
0x180123275  call    cs:__imp_GetTokenInformation
0x18012327b  test    eax, eax
0x18012327d  jnz     short loc_180123290
0x18012327f  call    cs:__imp_GetLastError
0x180123285  mov     ebx, eax
0x180123287  mov     [rsp+198h+var_138], eax
0x18012328b  jmp     loc_1801235A1
0x180123290  lea     rax, [rsp+198h+ReturnLength]
0x180123295  mov     [rsp+198h+lpdwDaclSize], rax; ReturnLength
0x18012329a  xor     r9d, r9d; TokenInformationLength
0x18012329d  xor     r8d, r8d; TokenInformation
0x1801232a0  lea     edx, [r9+1]; TokenInformationClass
0x1801232a4  mov     rcx, [rsp+198h+TokenHandle]; TokenHandle
0x1801232ac  call    cs:__imp_GetTokenInformation
0x1801232b2  mov     r8d, [rsp+198h+ReturnLength]
0x1801232b7  mov     dword ptr [rsp+198h+pSacl], 3220BD3h
0x1801232bf  mov     dword ptr [rsp+198h+lpdwDaclSize], 0
0x1801232c7  mov     eax, 1
0x1801232cc  mov     r9d, eax
0x1801232cf  mov     edx, eax
0x1801232d1  mov     rcx, r15
0x1801232d4  call    THAlloc_
0x1801232d9  mov     [rsp+198h+var_130], rax
0x1801232de  lea     rcx, [rsp+198h+ReturnLength]
0x1801232e3  mov     [rsp+198h+lpdwDaclSize], rcx; ReturnLength
0x1801232e8  mov     r9d, [rsp+198h+ReturnLength]; TokenInformationLength
0x1801232ed  mov     r8, rax; TokenInformation
0x1801232f0  mov     edx, 1; TokenInformationClass
0x1801232f5  mov     rcx, [rsp+198h+TokenHandle]; TokenHandle
0x1801232fd  call    cs:__imp_GetTokenInformation
0x180123303  test    eax, eax
0x180123305  jz      loc_18012327F
0x18012330b  mov     rdx, cs:gpBuiltinAdminSid; pSid2
0x180123312  mov     rcx, [rbx]; pSid1
0x180123315  call    cs:__imp_EqualSid
0x18012331b  mov     ecx, 10h
0x180123320  test    eax, eax
0x180123322  cmovnz  esi, ecx
0x180123325  mov     [rsp+198h+var_108], esi
0x18012332c  mov     rax, [rsp+198h+var_130]
0x180123331  mov     rax, cs:gpDomainAdminSid
0x180123338  mov     qword ptr [rsp+198h+var_98], rax
0x180123340  mov     rax, cs:gpEnterpriseAdminSid
0x180123347  mov     qword ptr [rsp+198h+var_98+8], rax
0x18012334f  mov     rax, cs:gpSchemaAdminSid
0x180123356  mov     qword ptr [rsp+198h+var_88], rax
0x18012335e  mov     rax, [rsp+198h+var_B8]
0x180123366  mov     qword ptr [rsp+198h+var_88+8], rax
0x18012336e  lea     rax, [rsp+198h+pSelfRelativeSecurityDescriptor]
0x180123376  mov     [rsp+198h+lpdwDaclSize], rax
0x18012337b  mov     r9d, 4
0x180123381  lea     r8, [rsp+198h+var_98]
0x180123389  mov     rdx, [rsp+198h+var_C0]
0x180123391  mov     rcx, r15
0x180123394  call    CheckGroupMembershipAnyClient
0x180123399  mov     ebx, eax
0x18012339b  mov     [rsp+198h+var_138], eax
0x18012339f  test    eax, eax
0x1801233a1  jnz     loc_1801235A1
0x1801233a7  cmp     dword ptr [rsp+198h+pSelfRelativeSecurityDescriptor], eax
0x1801233ae  jz      short loc_1801233BA
0x1801233b0  or      esi, 4
0x1801233b3  mov     [rsp+198h+var_108], esi
0x1801233ba  cmp     dword ptr [rsp+198h+pSelfRelativeSecurityDescriptor+4], 0
0x1801233c2  jz      short loc_1801233CE
0x1801233c4  or      esi, 1
0x1801233c7  mov     [rsp+198h+var_108], esi
0x1801233ce  mov     eax, 2
0x1801233d3  cmp     [rsp+198h+var_50], 0
0x1801233db  jz      short loc_1801233E6
0x1801233dd  or      esi, eax
  ... truncated ...
```
