# BasepCreateLowBox

- ea: `0x18000ec14`
- end: `0x18000f340`
- name: `BasepCreateLowBox`
- size: `1836`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f500`
- `0x18008e220`

## callees

- `0x18000e0f8`
- `0x18000ec14`
- `0x18000f348`
- `0x18000f4c0`
- `0x18000f60c`
- `0x180018b00`
- `0x180073a2c`
- `0x1801369c9`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000ed44`
- `ntdll!NtQueryInformationToken` at `0x18000f0ba`
- `ntdll!NtQueryInformationToken` at `0x18000ed44`
- `ntdll!NtQueryInformationToken` at `0x18000f0ba`
- `ntdll!NtClose` at `0x18000eec4`
- `ntdll!NtClose` at `0x18000eed9`
- `ntdll!NtClose` at `0x18000eeee`
- `ntdll!NtClose` at `0x18000ef03`
- `ntdll!NtClose` at `0x18000ef18`
- `ntdll!NtClose` at `0x18000ef2d`
- `ntdll!NtClose` at `0x18000ef4f`
- `ntdll!NtClose` at `0x18000f070`
- `ntdll!NtClose` at `0x18000eec4`
- `ntdll!NtClose` at `0x18000eed9`
- `ntdll!NtClose` at `0x18000eeee`
- `ntdll!NtClose` at `0x18000ef03`
- `ntdll!NtClose` at `0x18000ef18`
- `ntdll!NtClose` at `0x18000ef2d`
- `ntdll!NtClose` at `0x18000ef4f`
- `ntdll!NtClose` at `0x18000f070`
- `ntdll!RtlFreeSid` at `0x18000ef67`
- `ntdll!RtlFreeSid` at `0x18000ef7c`
- `ntdll!RtlFreeSid` at `0x18000ef67`
- `ntdll!RtlFreeSid` at `0x18000ef7c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f1e8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000f1e8`
- `ntdll!RtlGetAppContainerSidType` at `0x18000ee23`
- `ntdll!RtlGetAppContainerSidType` at `0x18000ee23`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18000f0db`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18000f0db`
- `ntdll!RtlFreeHeap` at `0x18000ef9f`
- `ntdll!RtlFreeHeap` at `0x18000ef9f`
- `ntdll!NtOpenProcessToken` at `0x18000f319`
- `ntdll!NtOpenProcessToken` at `0x18000f319`
- `ntdll!NtOpenThreadToken` at `0x18000f2d2`
- `ntdll!NtOpenThreadToken` at `0x18000f2d2`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000f27d`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000f27d`
- `ntdll!NtCreateLowBoxToken` at `0x18000ee93`
- `ntdll!NtCreateLowBoxToken` at `0x18000ee93`
- `ntdll!RtlAllocateHeap` at `0x18000f111`
- `ntdll!RtlAllocateHeap` at `0x18000f111`

## pseudocode

```c
NTSTATUS __fastcall BasepCreateLowBox(HANDLE TokenHandle, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  HANDLE v5; // rdi
  __int64 v6; // rsi
  int v7; // r14d
  int TokenFromLowboxToken; // ebx
  char v9; // si
  int v10; // r14d
  PSID v11; // rcx
  void *v12; // rdi
  NTSTATUS result; // eax
  void **v14; // r8
  void **v15; // r8
  _QWORD *Heap; // rax
  PSID v17; // rbx
  ULONG SubAuthority7; // r12d
  ULONG SubAuthority6; // r15d
  ULONG SubAuthority5; // r14d
  ULONG v21; // esi
  ULONG v22; // edi
  ULONG *SidSubAuthority; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  int SubAuthority3; // [rsp+28h] [rbp-D8h]
  ULONG SubAuthority4[2]; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+60h] [rbp-A0h]
  _QWORD *P; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  ULONG v30; // [rsp+78h] [rbp-88h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+7Ch] [rbp-84h] BYREF
  int TokenInformation; // [rsp+80h] [rbp-80h] BYREF
  PSID Sid; // [rsp+88h] [rbp-78h] BYREF
  int v34; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+94h] [rbp-6Ch] BYREF
  HANDLE TokenHandlea; // [rsp+98h] [rbp-68h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-60h] BYREF
  __int128 Handle; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v40; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v41; // [rsp+D8h] [rbp-28h] BYREF
  PSID v42; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v43; // [rsp+E8h] [rbp-18h]
  __int64 v44; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD *v46; // [rsp+100h] [rbp+0h]
  _BYTE v47[48]; // [rsp+108h] [rbp+8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+138h] [rbp+38h] BYREF
  __int128 v49; // [rsp+140h] [rbp+40h] BYREF
  __int128 v50; // [rsp+150h] [rbp+50h]
  __int128 v51; // [rsp+160h] [rbp+60h]
  HANDLE v52; // [rsp+170h] [rbp+70h]
  WCHAR packageFamilyName[72]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v54[10]; // [rsp+210h] [rbp+110h] BYREF

  v46 = a3;
  v43 = TokenHandle;
  v3 = a3;
  TokenHandlea = 0;
  v39 = 0u;
  v5 = TokenHandle;
  TokenInformation = 0;
  Handle = 0u;
  v30 = 0;
  memset(v47, 0, 44);
  v40 = 0u;
  v41 = 0;
  v37 = 0;
  v49 = 0;
  v52 = 0;
  v50 = 0;
  v51 = 0;
  memset_0(v54, 0, 0x4Cu);
  Sid = 0;
  packageFamilyNameLength = 65;
  v34 = 1179650;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  v42 = 0;
  v35 = 0;
  if ( !*(_QWORD *)a2 )
    return -1073741811;
  v6 = *(_QWORD *)(a2 + 8);
  v7 = *(_DWORD *)(a2 + 16);
  v29 = v6;
  v27 = v7;
  if ( !ValuesQueried )
  {
    RtlQueryRegistryValuesEx(2, L"Session Manager\\NamespaceSeparation", &BnoRegistryConfigurationTable);
    if ( InteractiveUserNameSpaceSeparation )
    {
      AppcontainerUserNameSpaceSeparation = 1;
      InteractiveUserNameSpaceSeparation = 1;
    }
    ValuesQueried = 1;
  }
  if ( !v5 )
  {
    if ( NtCurrentTeb()->IsImpersonating )
      result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xF01FFu, 0, &TokenHandlea);
    else
      result = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xF01FFu, &TokenHandlea);
    if ( result < 0 )
      return result;
    v5 = TokenHandlea;
    v43 = TokenHandlea;
  }
  P = 0;
  if ( *(_DWORD *)(a2 + 16) && !*(_QWORD *)(a2 + 8) )
  {
    TokenFromLowboxToken = -1073741811;
    goto LABEL_49;
  }
  TokenFromLowboxToken = NtQueryInformationToken(v5, TokenIsAppContainer, &TokenInformation, 4u, &v30);
  if ( TokenFromLowboxToken < 0 )
  {
LABEL_49:
    v12 = 0;
    goto LABEL_16;
  }
  v44 = 0;
  v45 = 0;
  v9 = 0;
  AppModelPolicy_GetPolicy_Internal((_DWORD)v5, 33, (unsigned int)&v34, (unsigned int)&v45, (__int64)&v44);
  v10 = 6;
  if ( TokenInformation )
  {
    v30 = 76;
    result = NtQueryInformationToken(v5, TokenAppContainerSid, v54, 0x4Cu, &v30);
    TokenFromLowboxToken = result;
    if ( result < 0 )
      return result;
    if ( (unsigned __int8)RtlIsParentOfChildAppContainer(v54[0], *(_QWORD *)a2) )
    {
      v9 = 1;
    }
    else
    {
      TokenFromLowboxToken = BasepCreateTokenFromLowboxToken(v5);
      if ( TokenFromLowboxToken < 0 )
        goto LABEL_48;
    }
LABEL_58:
    if ( TokenInformation && !v9 )
    {
LABEL_13:
      *v3 = v37;
      goto LABEL_14;
    }
LABEL_8:
    TokenFromLowboxToken = BasepCreateLowBoxObjectDirectories(
                             *(PSID *)a2,
                             v5,
                             (HANDLE *)&Handle,
                             (HANDLE *)&Handle + 1,
                             (HANDLE *)&v39,
                             (__int64)&v39 + 8,
                             &v40,
                             (HANDLE *)&v40 + 1,
                             &v41);
    if ( TokenFromLowboxToken < 0 )
      goto LABEL_14;
    v11 = *(PSID *)a2;
    v49 = Handle;
    v50 = v39;
    v51 = v40;
    TokenFromLowboxToken = RtlGetAppContainerSidType(v11, &v35);
    if ( TokenFromLowboxToken < 0 )
      goto LABEL_14;
    if ( v35 == 1 )
    {
      v10 = 7;
      v52 = v41;
    }
    *(_DWORD *)v47 = 48;
    *(_QWORD *)SubAuthority4 = *(_QWORD *)(a2 + 8);
    SubAuthority3 = *(_DWORD *)(a2 + 16);
    ReturnLength = *(PULONG *)a2;
    memset(&v47[8], 0, 20);
    *(_OWORD *)&v47[32] = 0;
    TokenFromLowboxToken = NtCreateLowBoxToken(
                             &v37,
                             v5,
                             983551,
                             v47,
                             ReturnLength,
                             SubAuthority3,
                             *(_QWORD *)SubAuthority4,
                             v10,
                             &v49);
    if ( TokenFromLowboxToken < 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( v34 != 2162689 )
    goto LABEL_8;
  if ( GetPackageFamilyNameFromToken(v5, &packageFamilyNameLength, packageFamilyName) > 0 )
    TokenFromLowboxToken = (unsigned __int16)GetPackageFamilyNameFromToken(
                                               v5,
                                               &packageFamilyNameLength,
                                               packageFamilyName)
                         | 0xC0070000;
  else
    TokenFromLowboxToken = GetPackageFamilyNameFromToken(v5, &packageFamilyNameLength, packageFamilyName);
  if ( TokenFromLowboxToken < 0
    || ((int)ARI::Internal::PackageSidFromFamilyName(packageFamilyName, (const unsigned __int16 *)&Sid, v14) > 0
      ? (TokenFromLowboxToken = (unsigned __int16)ARI::Internal::PackageSidFromFamilyName(
                                                    packageFamilyName,
                                                    (const unsigned __int16 *)&Sid,
                                                    v15)
                              | 0xC0070000)
      : (TokenFromLowboxToken = ARI::Internal::PackageSidFromFamilyName(
                                  packageFamilyName,
                                  (const unsigned __int16 *)&Sid,
                                  v15)),
        TokenFromLowboxToken < 0) )
  {
LABEL_48:
    v7 = v27;
    v6 = v29;
    goto LABEL_49;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * (unsigned int)(*(_DWORD *)(a2 + 16) + 1));
  P = Heap;
  v12 = Heap;
  if ( !Heap )
  {
    TokenFromLowboxToken = -1073741801;
    goto LABEL_15;
  }
  if ( *(_DWORD *)(a2 + 16) )
    memcpy_0(Heap, *(const void **)(a2 + 8), 16LL * *(unsigned int *)(a2 + 16));
  v17 = Sid;
  SubAuthority7 = *GetSidSubAuthority(Sid, 7u);
  SubAuthority6 = *GetSidSubAuthority(v17, 6u);
  SubAuthority5 = *GetSidSubAuthority(v17, 5u);
  v21 = *GetSidSubAuthority(v17, 4u);
  v22 = *GetSidSubAuthority(v17, 3u);
  LODWORD(v17) = *GetSidSubAuthority(v17, 2u);
  SidSubAuthority = GetSidSubAuthority(Sid, 1u);
  TokenFromLowboxToken = RtlAllocateAndInitializeSid(
                           &IdentifierAuthority,
                           8u,
                           3u,
                           *SidSubAuthority,
                           (ULONG)v17,
                           v22,
                           v21,
                           SubAuthority5,
                           SubAuthority6,
                           SubAuthority7,
                           &v42);
  if ( TokenFromLowboxToken >= 0 )
  {
    v10 = 6;
    v9 = 0;
    v5 = v43;
    v3 = v46;
    P[2 * *(unsigned int *)(a2 + 16)] = v42;
    LODWORD(P[2 * (unsigned int)(*(_DWORD *)(a2 + 16))++ + 1]) = 4;
    *(_QWORD *)(a2 + 8) = P;
    goto LABEL_58;
  }
LABEL_14:
  v12 = P;
LABEL_15:
  v6 = v29;
  v7 = v27;
LABEL_16:
  if ( (_QWORD)Handle )
    NtClose((HANDLE)Handle);
  if ( *((_QWORD *)&Handle + 1) )
    NtClose(*((HANDLE *)&Handle + 1));
  if ( (_QWORD)v39 )
    NtClose((HANDLE)v39);
  if ( *((_QWORD *)&v39 + 1) )
    NtClose(*((HANDLE *)&v39 + 1));
  if ( (_QWORD)v40 )
    NtClose((HANDLE)v40);
  if ( *((_QWORD *)&v40 + 1) )
    NtClose(*((HANDLE *)&v40 + 1));
  if ( v41 )
    NtClose(v41);
  if ( TokenHandlea )
    NtClose(TokenHandlea);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v42 )
    RtlFreeSid(v42);
  if ( v12 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  *(_QWORD *)(a2 + 8) = v6;
  result = TokenFromLowboxToken;
  *(_DWORD *)(a2 + 16) = v7;
  return result;
}

```

## disassembly

```asm
0x18000ec14  mov     [rsp-8+arg_18], rbx
0x18000ec19  push    rbp
0x18000ec1a  push    rsi
0x18000ec1b  push    rdi
0x18000ec1c  push    r12
0x18000ec1e  push    r13
0x18000ec20  push    r14
0x18000ec22  push    r15
0x18000ec24  lea     rbp, [rsp-170h]
0x18000ec2c  sub     rsp, 270h
0x18000ec33  mov     rax, cs:__security_cookie
0x18000ec3a  xor     rax, rsp
0x18000ec3d  mov     [rbp+1A0h+var_40], rax
0x18000ec44  xor     r12d, r12d
0x18000ec47  mov     [rbp+1A0h+var_1A0], r8
0x18000ec4b  xorps   xmm0, xmm0
0x18000ec4e  mov     [rbp+1A0h+var_1B8], rcx
0x18000ec52  mov     r15, r8
0x18000ec55  mov     [rbp+1A0h+TokenHandle], r12
0x18000ec59  mov     r13, rdx
0x18000ec5c  mov     qword ptr [rbp+1A0h+var_1E8], r12
0x18000ec60  mov     rdi, rcx
0x18000ec63  mov     [rbp+1A0h+TokenInformation], r12d
0x18000ec67  xor     eax, eax
0x18000ec69  mov     qword ptr [rbp+1A0h+var_1E8+8], r12
0x18000ec6d  movups  [rbp+1A0h+var_188], xmm0
0x18000ec71  lea     r8d, [r12+4Ch]; Size
0x18000ec76  mov     qword ptr [rbp+1A0h+Handle], r12
0x18000ec7a  xor     edx, edx; Val
0x18000ec7c  mov     [rsp+2A0h+var_228], r12d
0x18000ec81  lea     rcx, [rbp+1A0h+var_90]; void *
0x18000ec88  mov     qword ptr [rbp+1A0h+Handle+8], r12
0x18000ec8c  movups  [rbp+1A0h+var_198], xmm0
0x18000ec90  mov     qword ptr [rbp+1A0h+var_1D8], r12
0x18000ec94  movups  [rbp+1A0h+var_188+0Ch], xmm0
0x18000ec98  mov     qword ptr [rbp+1A0h+var_1D8+8], r12
0x18000ec9c  mov     [rbp+1A0h+var_1C8], r12
0x18000eca0  mov     [rbp+1A0h+var_200], r12
0x18000eca4  movups  [rbp+1A0h+var_160], xmm0
0x18000eca8  mov     [rbp+1A0h+var_130], rax
0x18000ecac  movups  [rbp+1A0h+var_150], xmm0
0x18000ecb0  movups  [rbp+1A0h+var_140], xmm0
0x18000ecb4  call    memset_0
0x18000ecb9  mov     [rbp+1A0h+Sid], r12
0x18000ecbd  mov     [rsp+2A0h+packageFamilyNameLength], 41h ; 'A'
0x18000ecc5  mov     [rbp+1A0h+var_210], 120002h
0x18000eccc  mov     dword ptr [rbp+1A0h+IdentifierAuthority.Value], r12d
0x18000ecd0  mov     word ptr [rbp+1A0h+IdentifierAuthority.Value+4], 0F00h
0x18000ecd6  mov     [rbp+1A0h+var_1C0], r12
0x18000ecda  mov     [rbp+1A0h+var_20C], r12d
0x18000ecde  cmp     [r13+0], r12
0x18000ece2  jz      loc_18000F2A9
0x18000ece8  cmp     cs:ValuesQueried, r12d
0x18000ecef  lea     ebx, [r12+1]
0x18000ecf4  mov     rsi, [r13+8]
0x18000ecf8  mov     r14d, [r13+10h]
0x18000ecfc  mov     [rsp+2A0h+var_230], rsi
0x18000ed01  mov     [rsp+2A0h+var_240], r14d
0x18000ed06  jz      loc_18000F263
0x18000ed0c  mov     ecx, 0F01FFh
0x18000ed11  test    rdi, rdi
0x18000ed14  jz      loc_18000F2B3
0x18000ed1a  mov     [rsp+2A0h+P], r12
0x18000ed1f  cmp     [r13+10h], r12d
0x18000ed23  ja      loc_18000EFE0
0x18000ed29  mov     r9d, 4; TokenInformationLength
0x18000ed2f  lea     rax, [rsp+2A0h+var_228]
0x18000ed34  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x18000ed38  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18000ed3d  mov     rcx, rdi; TokenHandle
0x18000ed40  lea     edx, [r9+19h]; TokenInformationClass
0x18000ed44  call    cs:__imp_NtQueryInformationToken
0x18000ed4b  nop     dword ptr [rax+rax+00h]
0x18000ed50  mov     ebx, eax
0x18000ed52  test    eax, eax
0x18000ed54  js      loc_18000F068
0x18000ed5a  lea     rax, [rbp+1A0h+var_1B0]
0x18000ed5e  mov     [rbp+1A0h+var_1B0], r12
0x18000ed62  lea     r9, [rbp+1A0h+var_1A8]
0x18000ed66  mov     [rsp+2A0h+ReturnLength], rax
0x18000ed6b  lea     r8, [rbp+1A0h+var_210]
0x18000ed6f  mov     [rbp+1A0h+var_1A8], r12
0x18000ed73  mov     edx, 21h ; '!'
0x18000ed78  mov     rcx, rdi
0x18000ed7b  mov     sil, r12b
0x18000ed7e  call    AppModelPolicy_GetPolicy_Internal
0x18000ed83  mov     r14d, 6
0x18000ed89  cmp     [rbp+1A0h+TokenInformation], r12d
0x18000ed8d  jnz     loc_18000F094
0x18000ed93  cmp     [rbp+1A0h+var_210], 210001h
0x18000ed9a  jz      loc_18000EFF1
0x18000eda0  mov     rcx, [r13+0]; Sid
0x18000eda4  lea     rax, [rbp+1A0h+var_1C8]
0x18000eda8  mov     qword ptr [rsp+2A0h+SubAuthority6], rax; __int64
0x18000edad  lea     r9, [rbp+1A0h+Handle+8]
0x18000edb1  lea     rax, [rbp+1A0h+var_1D8+8]
0x18000edb5  mov     rdx, rdi; TokenHandle
0x18000edb8  mov     qword ptr [rsp+2A0h+SubAuthority5], rax; __int64
0x18000edbd  lea     r8, [rbp+1A0h+Handle]
0x18000edc1  lea     rax, [rbp+1A0h+var_1D8]
0x18000edc5  mov     qword ptr [rsp+2A0h+SubAuthority4], rax; __int64
0x18000edca  lea     rax, [rbp+1A0h+var_1E8+8]
0x18000edce  mov     qword ptr [rsp+2A0h+SubAuthority3], rax; __int64
0x18000edd3  lea     rax, [rbp+1A0h+var_1E8]
0x18000edd7  mov     [rsp+2A0h+ReturnLength], rax; __int64
0x18000eddc  call    BasepCreateLowBoxObjectDirectories
0x18000ede1  mov     ebx, eax
0x18000ede3  test    eax, eax
0x18000ede5  js      loc_18000EEAC
0x18000edeb  mov     rax, qword ptr [rbp+1A0h+Handle]
0x18000edef  lea     rdx, [rbp+1A0h+var_20C]
0x18000edf3  mov     rcx, [r13+0]
0x18000edf7  mov     qword ptr [rbp+1A0h+var_160], rax
0x18000edfb  mov     rax, qword ptr [rbp+1A0h+Handle+8]
0x18000edff  mov     qword ptr [rbp+1A0h+var_160+8], rax
0x18000ee03  mov     rax, qword ptr [rbp+1A0h+var_1E8]
0x18000ee07  mov     qword ptr [rbp+1A0h+var_150], rax
0x18000ee0b  mov     rax, qword ptr [rbp+1A0h+var_1E8+8]
0x18000ee0f  mov     qword ptr [rbp+1A0h+var_150+8], rax
0x18000ee13  mov     rax, qword ptr [rbp+1A0h+var_1D8]
0x18000ee17  mov     qword ptr [rbp+1A0h+var_140], rax
0x18000ee1b  mov     rax, qword ptr [rbp+1A0h+var_1D8+8]
0x18000ee1f  mov     qword ptr [rbp+1A0h+var_140+8], rax
0x18000ee23  call    cs:__imp_RtlGetAppContainerSidType
0x18000ee2a  nop     dword ptr [rax+rax+00h]
0x18000ee2f  mov     ebx, eax
0x18000ee31  test    eax, eax
0x18000ee33  js      short loc_18000EEAC
0x18000ee35  cmp     [rbp+1A0h+var_20C], 1
0x18000ee39  jz      loc_18000F081
0x18000ee3f  lea     rax, [rbp+1A0h+var_160]
0x18000ee43  mov     dword ptr [rbp+1A0h+var_198], 30h ; '0'
0x18000ee4a  mov     qword ptr [rsp+2A0h+SubAuthority6], rax
0x18000ee4f  lea     r9, [rbp+1A0h+var_198]
0x18000ee53  mov     rax, [r13+8]
0x18000ee57  lea     rcx, [rbp+1A0h+var_200]
0x18000ee5b  mov     [rsp+2A0h+SubAuthority5], r14d
0x18000ee60  xorps   xmm0, xmm0
0x18000ee63  mov     qword ptr [rsp+2A0h+SubAuthority4], rax
0x18000ee68  mov     r8d, 0F01FFh
0x18000ee6e  mov     eax, [r13+10h]
0x18000ee72  mov     rdx, rdi
0x18000ee75  mov     [rsp+2A0h+SubAuthority3], eax
0x18000ee79  mov     rax, [r13+0]
0x18000ee7d  mov     [rsp+2A0h+ReturnLength], rax
0x18000ee82  mov     qword ptr [rbp+1A0h+var_198+8], r12
0x18000ee86  mov     dword ptr [rbp+1A0h+var_188+8], r12d
0x18000ee8a  mov     qword ptr [rbp+1A0h+var_188], r12
0x18000ee8e  movdqu  [rbp+1A0h+var_178], xmm0
0x18000ee93  call    cs:__imp_NtCreateLowBoxToken
0x18000ee9a  nop     dword ptr [rax+rax+00h]
0x18000ee9f  mov     ebx, eax
0x18000eea1  test    eax, eax
0x18000eea3  js      short loc_18000EEAC
0x18000eea5  mov     rax, [rbp+1A0h+var_200]
0x18000eea9  mov     [r15], rax
0x18000eeac  mov     rdi, [rsp+2A0h+P]
0x18000eeb1  mov     rsi, [rsp+2A0h+var_230]
0x18000eeb6  mov     r14d, [rsp+2A0h+var_240]
0x18000eebb  mov     rcx, qword ptr [rbp+1A0h+Handle]; Handle
0x18000eebf  test    rcx, rcx
0x18000eec2  jz      short loc_18000EED0
0x18000eec4  call    cs:__imp_NtClose
0x18000eecb  nop     dword ptr [rax+rax+00h]
0x18000eed0  mov     rcx, qword ptr [rbp+1A0h+Handle+8]; Handle
0x18000eed4  test    rcx, rcx
0x18000eed7  jz      short loc_18000EEE5
0x18000eed9  call    cs:__imp_NtClose
0x18000eee0  nop     dword ptr [rax+rax+00h]
0x18000eee5  mov     rcx, qword ptr [rbp+1A0h+var_1E8]; Handle
0x18000eee9  test    rcx, rcx
0x18000eeec  jz      short loc_18000EEFA
0x18000eeee  call    cs:__imp_NtClose
0x18000eef5  nop     dword ptr [rax+rax+00h]
0x18000eefa  mov     rcx, qword ptr [rbp+1A0h+var_1E8+8]; Handle
0x18000eefe  test    rcx, rcx
0x18000ef01  jz      short loc_18000EF0F
0x18000ef03  call    cs:__imp_NtClose
0x18000ef0a  nop     dword ptr [rax+rax+00h]
0x18000ef0f  mov     rcx, qword ptr [rbp+1A0h+var_1D8]; Handle
0x18000ef13  test    rcx, rcx
0x18000ef16  jz      short loc_18000EF24
0x18000ef18  call    cs:__imp_NtClose
0x18000ef1f  nop     dword ptr [rax+rax+00h]
0x18000ef24  mov     rcx, qword ptr [rbp+1A0h+var_1D8+8]; Handle
0x18000ef28  test    rcx, rcx
0x18000ef2b  jz      short loc_18000EF39
0x18000ef2d  call    cs:__imp_NtClose
0x18000ef34  nop     dword ptr [rax+rax+00h]
0x18000ef39  mov     rcx, [rbp+1A0h+var_1C8]; Handle
0x18000ef3d  test    rcx, rcx
0x18000ef40  jnz     loc_18000F070
0x18000ef46  mov     rcx, [rbp+1A0h+TokenHandle]; Handle
0x18000ef4a  test    rcx, rcx
0x18000ef4d  jz      short loc_18000EF5B
0x18000ef4f  call    cs:__imp_NtClose
0x18000ef56  nop     dword ptr [rax+rax+00h]
0x18000ef5b  mov     rax, [rbp+1A0h+Sid]
0x18000ef5f  test    rax, rax
0x18000ef62  jz      short loc_18000EF73
0x18000ef64  mov     rcx, rax; Sid
0x18000ef67  call    cs:__imp_RtlFreeSid
0x18000ef6e  nop     dword ptr [rax+rax+00h]
0x18000ef73  mov     rcx, [rbp+1A0h+var_1C0]; Sid
0x18000ef77  test    rcx, rcx
0x18000ef7a  jz      short loc_18000EF88
0x18000ef7c  call    cs:__imp_RtlFreeSid
0x18000ef83  nop     dword ptr [rax+rax+00h]
0x18000ef88  test    rdi, rdi
0x18000ef8b  jz      short loc_18000EFAB
0x18000ef8d  mov     rcx, gs:60h
0x18000ef96  mov     r8, rdi; P
0x18000ef99  xor     edx, edx; Flags
0x18000ef9b  mov     rcx, [rcx+30h]; HeapHandle
0x18000ef9f  call    cs:__imp_RtlFreeHeap
0x18000efa6  nop     dword ptr [rax+rax+00h]
0x18000efab  mov     [r13+8], rsi
0x18000efaf  mov     eax, ebx
0x18000efb1  mov     [r13+10h], r14d
0x18000efb5  mov     rcx, [rbp+1A0h+var_40]
0x18000efbc  xor     rcx, rsp; StackCookie
0x18000efbf  call    __security_check_cookie
0x18000efc4  mov     rbx, [rsp+2A0h+arg_18]
0x18000efcc  add     rsp, 270h
0x18000efd3  pop     r15
0x18000efd5  pop     r14
0x18000efd7  pop     r13
0x18000efd9  pop     r12
0x18000efdb  pop     rdi
0x18000efdc  pop     rsi
0x18000efdd  pop     rbp
0x18000efde  retn
0x18000efe0  cmp     [r13+8], r12
0x18000efe4  jnz     loc_18000ED29
0x18000efea  mov     ebx, 0C000000Dh
0x18000efef  jmp     short loc_18000F068
0x18000eff1  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x18000eff8  mov     rcx, rdi; token
0x18000effb  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x18000f000  call    GetPackageFamilyNameFromToken
0x18000f005  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x18000f00c  mov     esi, 0C0070000h
0x18000f011  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x18000f016  mov     rcx, rdi; token
0x18000f019  test    eax, eax
0x18000f01b  jg      loc_18000F254
0x18000f021  call    GetPackageFamilyNameFromToken
0x18000f026  mov     ebx, eax
0x18000f028  test    ebx, ebx
0x18000f02a  js      short loc_18000F05E
0x18000f02c  lea     rdx, [rbp+1A0h+Sid]; unsigned __int16 *
0x18000f030  lea     rcx, [rbp+1A0h+packageFamilyName]; SourceString
0x18000f037  call    ?PackageSidFromFamilyName@Internal@ARI@@YAJPEBGPEAPEAX@Z; ARI::Internal::PackageSidFromFamilyName(ushort const *,void * *)
0x18000f03c  lea     rdx, [rbp+1A0h+Sid]; unsigned __int16 *
0x18000f040  lea     rcx, [rbp+1A0h+packageFamilyName]; SourceString
0x18000f047  test    eax, eax
0x18000f049  jg      loc_18000F327
0x18000f04f  call    ?PackageSidFromFamilyName@Internal@ARI@@YAJPEBGPEAPEAX@Z; ARI::Internal::PackageSidFromFamilyName(ushort const *,void * *)
0x18000f054  mov     ebx, eax
0x18000f056  test    ebx, ebx
0x18000f058  jns     loc_18000F0F7
0x18000f05e  mov     r14d, [rsp+2A0h+var_240]
0x18000f063  mov     rsi, [rsp+2A0h+var_230]
0x18000f068  mov     rdi, r12
0x18000f06b  jmp     loc_18000EEBB
0x18000f070  call    cs:__imp_NtClose
0x18000f077  nop     dword ptr [rax+rax+00h]
0x18000f07c  jmp     loc_18000EF46
0x18000f081  mov     rax, [rbp+1A0h+var_1C8]
0x18000f085  mov     r14d, 7
0x18000f08b  mov     [rbp+1A0h+var_130], rax
0x18000f08f  jmp     loc_18000EE3F
0x18000f094  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18000f09a  mov     [rsp+2A0h+var_228], 4Ch ; 'L'
0x18000f0a2  lea     rax, [rsp+2A0h+var_228]
0x18000f0a7  mov     rcx, rdi; TokenHandle
0x18000f0aa  lea     r8, [rbp+1A0h+var_90]; TokenInformation
0x18000f0b1  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x18000f0b6  lea     edx, [r9-2Dh]; TokenInformationClass
0x18000f0ba  call    cs:__imp_NtQueryInformationToken
0x18000f0c1  nop     dword ptr [rax+rax+00h]
0x18000f0c6  mov     ebx, eax
0x18000f0c8  test    eax, eax
0x18000f0ca  js      loc_18000EFB5
0x18000f0d0  mov     rdx, [r13+0]
0x18000f0d4  mov     rcx, [rbp+1A0h+var_90]
0x18000f0db  call    cs:__imp_RtlIsParentOfChildAppContainer
0x18000f0e2  nop     dword ptr [rax+rax+00h]
0x18000f0e7  test    al, al
0x18000f0e9  jz      loc_18000F2F3
0x18000f0ef  mov     sil, 1
0x18000f0f2  jmp     loc_18000F23C
0x18000f0f7  mov     r8d, [r13+10h]
0x18000f0fb  xor     edx, edx; Flags
0x18000f0fd  mov     rcx, gs:60h
0x18000f106  inc     r8d
0x18000f109  shl     r8, 4; Size
0x18000f10d  mov     rcx, [rcx+30h]; HeapHandle
0x18000f111  call    cs:__imp_RtlAllocateHeap
0x18000f118  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
