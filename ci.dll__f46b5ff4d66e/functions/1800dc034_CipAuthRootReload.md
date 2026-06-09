# CipAuthRootReload

- ea: `0x1800dc034`
- end: `0x1800dc4a6`
- name: `CipAuthRootReload`
- size: `1138`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800db9bc`
- `0x1800dbbf8`

## callees

- `0x18005fac8`
- `0x1800714cc`
- `0x180092434`
- `0x180096fdc`
- `0x1800dc034`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800dc38a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800dc38a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800dc39f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800dc39f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800dc47f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800dc47f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc162`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc17c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc1b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc1c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc401`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc419`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc43a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc452`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc162`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc17c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc1b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc1c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc401`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc419`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc43a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dc452`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800dc48b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800dc48b`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800dc097`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800dc097`
- `ntoskrnl!qsort_s` at `0x1800dc350`
- `ntoskrnl!qsort_s` at `0x1800dc37e`
- `ntoskrnl!qsort_s` at `0x1800dc350`
- `ntoskrnl!qsort_s` at `0x1800dc37e`

## string_xrefs

- `0x1800dc12b`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x1800dc22f`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x1800dc261`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
__int64 CipAuthRootReload()
{
  int RegistryValue2; // edi
  unsigned int *v1; // rbx
  __int64 v2; // r13
  __int64 v3; // rcx
  char v4; // r15
  char v5; // si
  char v6; // r14
  __int64 v7; // rcx
  PVOID v8; // rsi
  __int64 v10; // rcx
  int v11; // eax
  char v12; // r12
  PVOID v13; // rbx
  unsigned int *v14; // r13
  __int64 v15; // [rsp+30h] [rbp-59h] BYREF
  __int64 v16; // [rsp+38h] [rbp-51h]
  PVOID P[2]; // [rsp+40h] [rbp-49h] BYREF
  PVOID v18[2]; // [rsp+50h] [rbp-39h] BYREF
  PVOID v19[2]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v20; // [rsp+70h] [rbp-19h] BYREF
  __int128 v21; // [rsp+80h] [rbp-9h]
  __int128 v22; // [rsp+90h] [rbp+7h]
  void **v23; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+100h] [rbp+77h] BYREF
  PVOID v26; // [rsp+108h] [rbp+7Fh] BYREF

  RegistryValue2 = 0;
  v1 = 0;
  v24 = 0;
  v25 = 0;
  *(_OWORD *)P = 0;
  v26 = 0;
  *(_OWORD *)v18 = 0;
  v23 = 0;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( (g_CiPolicyState & 0x2000) == 0 )
    goto LABEL_9;
  v15 = 0;
  KeQuerySystemTimePrecise(&v15);
  v2 = qword_180048558;
  v3 = qword_180048548;
  v4 = byte_180048560;
  v5 = byte_180048561;
  v6 = byte_180048562;
  v16 = qword_180048548;
  if ( byte_180048560 )
  {
    if ( byte_180048561 )
    {
      if ( g_CiAuthRootStore )
      {
        v3 = v15 - g_CiAuthRootStore;
        if ( (unsigned __int64)((v15 - g_CiAuthRootStore) / 10000000) < 0x15180 )
          goto LABEL_9;
      }
    }
  }
  RegistryValue2 = CipGetRegistryValue2(
                     v3,
                     L"\\Registry\\Machine\\Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
                     (__int64)L"EncodedCtl",
                     1,
                     &P[1],
                     P);
  if ( RegistryValue2 >= 0 )
  {
    v4 = 1;
  }
  else
  {
    if ( v6 )
    {
      RegistryValue2 = 0;
LABEL_9:
      v8 = P[1];
      goto LABEL_10;
    }
    if ( (int)CipAuthRootLoadCTLsFromCrypt32Dll(&P[1], P) < 0 )
      goto LABEL_9;
    v6 = 1;
  }
  RegistryValue2 = CipGetRegistryValue2(
                     v7,
                     L"\\Registry\\Machine\\Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
                     (__int64)L"DisallowedCertEncodedCtl",
                     1,
                     &v18[1],
                     v18);
  if ( RegistryValue2 < 0 )
    goto LABEL_9;
  v11 = CipGetRegistryValue2(
          v10,
          L"\\Registry\\Machine\\Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
          (__int64)L"DisallowedCertLastSyncTime",
          1,
          &v19[1],
          v19);
  v12 = v5;
  v8 = P[1];
  if ( v11 >= 0 )
    v12 = 1;
  RegistryValue2 = CiAuthRootParseCTL(1, (int)P[1], (int)P[0], (unsigned int **)&v26, (__int64)&v20, (__int64)&v24);
  if ( RegistryValue2 >= 0 )
  {
    if ( (_DWORD)v20 )
    {
      I_MincryptFreeChainInfo(v21);
      v20 = 0;
      v21 = 0;
      v22 = 0;
    }
    RegistryValue2 = CiAuthRootParseCTL(
                       0,
                       (int)v18[1],
                       (int)v18[0],
                       (unsigned int **)&v23,
                       (__int64)&v20,
                       (__int64)&v25);
    if ( RegistryValue2 < 0 )
      goto LABEL_38;
    if ( v25 < v2 || v24 < v16 )
    {
      RegistryValue2 = -1073740760;
      goto LABEL_38;
    }
    if ( v25 == v2 && v24 == v16 )
    {
      g_CiAuthRootStore = v15;
LABEL_38:
      v1 = (unsigned int *)v23;
      goto LABEL_10;
    }
    v13 = v26;
    qsort_s(*((void **)v26 + 1), *(unsigned int *)v26, 0x44u, CipAuthRootHashSearchCompare, 0);
    v14 = (unsigned int *)v23;
    qsort_s(v23[1], *(unsigned int *)v23, 0x44u, CipAuthRootHashSearchCompare, 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&g_CiAuthRootStoreLock, 0);
    qword_180048548 = v24;
    qword_180048558 = v25;
    if ( v4 )
    {
      byte_180048560 = v4;
      byte_180048562 = 1;
    }
    if ( v12 )
      byte_180048561 = v12;
    if ( v6 )
      byte_180048562 = v6;
    if ( qword_180048540 )
    {
      ExFreePoolWithTag(*((PVOID *)qword_180048540 + 1), 0x63734943u);
      ExFreePoolWithTag(qword_180048540, 0x63734943u);
    }
    if ( qword_180048550 )
    {
      ExFreePoolWithTag(*((PVOID *)qword_180048550 + 1), 0x63734943u);
      ExFreePoolWithTag(qword_180048550, 0x63734943u);
    }
    qword_180048540 = v13;
    qword_180048550 = v14;
    v1 = 0;
    v26 = 0;
    ExReleasePushLockExclusiveEx(&g_CiAuthRootStoreLock, 0);
    KeLeaveCriticalRegion();
  }
LABEL_10:
  if ( v8 )
    ExFreePoolWithTag(v8, 0x63734943u);
  if ( v18[1] )
    ExFreePoolWithTag(v18[1], 0x63734943u);
  if ( v19[1] )
    ExFreePoolWithTag(v19[1], 0x63734943u);
  if ( v26 )
    ExFreePoolWithTag(v26, 0x63734943u);
  if ( v1 )
    ExFreePoolWithTag(v1, 0x63734943u);
  if ( (_DWORD)v20 )
    I_MincryptFreeChainInfo(v21);
  return (unsigned int)RegistryValue2;
}

```

## disassembly

```asm
0x1800dc034  push    rbp
0x1800dc036  push    rbx
0x1800dc037  push    rsi
0x1800dc038  push    rdi
0x1800dc039  push    r12
0x1800dc03b  push    r13
0x1800dc03d  push    r14
0x1800dc03f  push    r15
0x1800dc041  lea     rbp, [rsp-1Fh]
0x1800dc046  sub     rsp, 0A8h
0x1800dc04d  xor     edi, edi
0x1800dc04f  xorps   xmm1, xmm1
0x1800dc052  xor     ebx, ebx
0x1800dc054  mov     [rbp+57h+arg_8], rdi
0x1800dc058  test    cs:g_CiPolicyState, 2000h
0x1800dc062  xorps   xmm0, xmm0
0x1800dc065  mov     [rbp+57h+arg_10], rdi
0x1800dc069  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800dc06d  mov     [rbp+57h+arg_18], rdi
0x1800dc071  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x1800dc075  mov     [rbp+57h+arg_0], rbx
0x1800dc079  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1800dc07d  movups  [rbp+57h+var_70], xmm1
0x1800dc081  movups  [rbp+57h+var_60], xmm1
0x1800dc085  movups  [rbp+57h+var_50], xmm1
0x1800dc089  jz      loc_1800DC151
0x1800dc08f  lea     rcx, [rbp+57h+var_B0]
0x1800dc093  mov     [rbp+57h+var_B0], rbx
0x1800dc097  call    cs:__imp_KeQuerySystemTimePrecise
0x1800dc09e  nop     dword ptr [rax+rax+00h]
0x1800dc0a3  mov     rax, cs:g_CiAuthRootStore
0x1800dc0aa  mov     r13, cs:qword_180048558
0x1800dc0b1  mov     rcx, cs:qword_180048548
0x1800dc0b8  mov     r15b, cs:byte_180048560
0x1800dc0bf  movzx   esi, cs:byte_180048561
0x1800dc0c6  mov     r14b, cs:byte_180048562
0x1800dc0cd  mov     [rbp+57h+var_A8], rcx
0x1800dc0d1  test    r15b, r15b
0x1800dc0d4  jz      short loc_1800DC10E
0x1800dc0d6  test    sil, sil
0x1800dc0d9  jz      short loc_1800DC10E
0x1800dc0db  test    rax, rax
0x1800dc0de  jz      short loc_1800DC10E
0x1800dc0e0  mov     rcx, [rbp+57h+var_B0]
0x1800dc0e4  sub     rcx, rax
0x1800dc0e7  mov     rax, 0D6BF94D5E57A42BDh
0x1800dc0f1  imul    rcx
0x1800dc0f4  add     rdx, rcx
0x1800dc0f7  sar     rdx, 17h
0x1800dc0fb  mov     rax, rdx
0x1800dc0fe  shr     rax, 3Fh
0x1800dc102  add     rdx, rax
0x1800dc105  cmp     rdx, 15180h
0x1800dc10c  jb      short loc_1800DC151
0x1800dc10e  lea     rax, [rbp+57h+P]
0x1800dc112  mov     r12d, 1
0x1800dc118  mov     [rsp+0E0h+var_B8], rax
0x1800dc11d  lea     r8, aEncodedctl; "EncodedCtl"
0x1800dc124  lea     rax, [rbp+57h+P+8]
0x1800dc128  mov     r9d, r12d
0x1800dc12b  lea     rdx, aRegistryMachin_26; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dc132  mov     [rsp+0E0h+Context], rax
0x1800dc137  call    CipGetRegistryValue2
0x1800dc13c  mov     edi, eax
0x1800dc13e  test    eax, eax
0x1800dc140  jns     loc_1800DC215
0x1800dc146  test    r14b, r14b
0x1800dc149  jz      loc_1800DC1FB
0x1800dc14f  xor     edi, edi
0x1800dc151  mov     rsi, [rbp+57h+P+8]
0x1800dc155  test    rsi, rsi
0x1800dc158  jz      short loc_1800DC16E
0x1800dc15a  mov     edx, 63734943h; Tag
0x1800dc15f  mov     rcx, rsi; P
0x1800dc162  call    cs:__imp_ExFreePoolWithTag
0x1800dc169  nop     dword ptr [rax+rax+00h]
0x1800dc16e  mov     rcx, [rbp+57h+var_90+8]; P
0x1800dc172  test    rcx, rcx
0x1800dc175  jz      short loc_1800DC188
0x1800dc177  mov     edx, 63734943h; Tag
0x1800dc17c  call    cs:__imp_ExFreePoolWithTag
0x1800dc183  nop     dword ptr [rax+rax+00h]
0x1800dc188  mov     rcx, [rbp+57h+var_80+8]; P
0x1800dc18c  test    rcx, rcx
0x1800dc18f  jz      short loc_1800DC1A2
0x1800dc191  mov     edx, 63734943h; Tag
0x1800dc196  call    cs:__imp_ExFreePoolWithTag
0x1800dc19d  nop     dword ptr [rax+rax+00h]
0x1800dc1a2  mov     rcx, [rbp+57h+arg_18]; P
0x1800dc1a6  test    rcx, rcx
0x1800dc1a9  jz      short loc_1800DC1BC
0x1800dc1ab  mov     edx, 63734943h; Tag
0x1800dc1b0  call    cs:__imp_ExFreePoolWithTag
0x1800dc1b7  nop     dword ptr [rax+rax+00h]
0x1800dc1bc  test    rbx, rbx
0x1800dc1bf  jz      short loc_1800DC1D5
0x1800dc1c1  mov     edx, 63734943h; Tag
0x1800dc1c6  mov     rcx, rbx; P
0x1800dc1c9  call    cs:__imp_ExFreePoolWithTag
0x1800dc1d0  nop     dword ptr [rax+rax+00h]
0x1800dc1d5  cmp     dword ptr [rbp+57h+var_70], 0
0x1800dc1d9  jz      short loc_1800DC1E4
0x1800dc1db  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800dc1df  call    I_MincryptFreeChainInfo
0x1800dc1e4  mov     eax, edi
0x1800dc1e6  add     rsp, 0A8h
0x1800dc1ed  pop     r15
0x1800dc1ef  pop     r14
0x1800dc1f1  pop     r13
0x1800dc1f3  pop     r12
0x1800dc1f5  pop     rdi
0x1800dc1f6  pop     rsi
0x1800dc1f7  pop     rbx
0x1800dc1f8  pop     rbp
0x1800dc1f9  retn
0x1800dc1fb  lea     rdx, [rbp+57h+P]
0x1800dc1ff  lea     rcx, [rbp+57h+P+8]
0x1800dc203  call    CipAuthRootLoadCTLsFromCrypt32Dll
0x1800dc208  test    eax, eax
0x1800dc20a  js      loc_1800DC151
0x1800dc210  mov     r14b, r12b
0x1800dc213  jmp     short loc_1800DC218
0x1800dc215  mov     r15b, r12b
0x1800dc218  lea     rax, [rbp+57h+var_90]
0x1800dc21c  mov     r9d, r12d
0x1800dc21f  mov     [rsp+0E0h+var_B8], rax
0x1800dc224  lea     r8, aDisallowedcert; "DisallowedCertEncodedCtl"
0x1800dc22b  lea     rax, [rbp+57h+var_90+8]
0x1800dc22f  lea     rdx, aRegistryMachin_26; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dc236  mov     [rsp+0E0h+Context], rax
0x1800dc23b  call    CipGetRegistryValue2
0x1800dc240  mov     edi, eax
0x1800dc242  test    eax, eax
0x1800dc244  js      loc_1800DC151
0x1800dc24a  lea     rax, [rbp+57h+var_80]
0x1800dc24e  mov     r9d, r12d
0x1800dc251  mov     [rsp+0E0h+var_B8], rax
0x1800dc256  lea     r8, aDisallowedcert_0; "DisallowedCertLastSyncTime"
0x1800dc25d  lea     rax, [rbp+57h+var_80+8]
0x1800dc261  lea     rdx, aRegistryMachin_26; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dc268  mov     [rsp+0E0h+Context], rax
0x1800dc26d  call    CipGetRegistryValue2
0x1800dc272  mov     r8d, dword ptr [rbp+57h+P]
0x1800dc276  lea     r9, [rbp+57h+arg_18]
0x1800dc27a  test    eax, eax
0x1800dc27c  mov     r12d, esi
0x1800dc27f  mov     rsi, [rbp+57h+P+8]
0x1800dc283  lea     rax, [rbp+57h+arg_8]
0x1800dc287  mov     [rsp+0E0h+var_B8], rax
0x1800dc28c  mov     ecx, 1
0x1800dc291  lea     rax, [rbp+57h+var_70]
0x1800dc295  mov     rdx, rsi
0x1800dc298  mov     [rsp+0E0h+Context], rax
0x1800dc29d  cmovns  r12d, ecx
0x1800dc2a1  call    CiAuthRootParseCTL
0x1800dc2a6  mov     edi, eax
0x1800dc2a8  test    eax, eax
0x1800dc2aa  js      loc_1800DC155
0x1800dc2b0  cmp     dword ptr [rbp+57h+var_70], ebx
0x1800dc2b3  jz      short loc_1800DC2CD
0x1800dc2b5  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800dc2b9  call    I_MincryptFreeChainInfo
0x1800dc2be  xorps   xmm0, xmm0
0x1800dc2c1  movups  [rbp+57h+var_70], xmm0
0x1800dc2c5  movups  [rbp+57h+var_60], xmm0
0x1800dc2c9  movups  [rbp+57h+var_50], xmm0
0x1800dc2cd  mov     r8d, dword ptr [rbp+57h+var_90]
0x1800dc2d1  lea     rax, [rbp+57h+arg_10]
0x1800dc2d5  mov     rdx, [rbp+57h+var_90+8]
0x1800dc2d9  lea     r9, [rbp+57h+arg_0]
0x1800dc2dd  mov     [rsp+0E0h+var_B8], rax
0x1800dc2e2  xor     ecx, ecx
0x1800dc2e4  lea     rax, [rbp+57h+var_70]
0x1800dc2e8  mov     [rsp+0E0h+Context], rax
0x1800dc2ed  call    CiAuthRootParseCTL
0x1800dc2f2  mov     edi, eax
0x1800dc2f4  test    eax, eax
0x1800dc2f6  js      short loc_1800DC327
0x1800dc2f8  cmp     [rbp+57h+arg_10], r13
0x1800dc2fc  jl      loc_1800DC49C
0x1800dc302  mov     rax, [rbp+57h+var_A8]
0x1800dc306  cmp     [rbp+57h+arg_8], rax
0x1800dc30a  jl      loc_1800DC49C
0x1800dc310  cmp     [rbp+57h+arg_10], r13
0x1800dc314  jnz     short loc_1800DC330
0x1800dc316  cmp     [rbp+57h+arg_8], rax
0x1800dc31a  jnz     short loc_1800DC330
0x1800dc31c  mov     rax, [rbp+57h+var_B0]
0x1800dc320  mov     cs:g_CiAuthRootStore, rax
0x1800dc327  mov     rbx, [rbp+57h+arg_0]
0x1800dc32b  jmp     loc_1800DC155
0x1800dc330  mov     rbx, [rbp+57h+arg_18]
0x1800dc334  lea     r9, CipAuthRootHashSearchCompare; PtFuncCompare
0x1800dc33b  mov     r8d, 44h ; 'D'; SizeOfElements
0x1800dc341  mov     [rsp+0E0h+Context], 0; Context
0x1800dc34a  mov     edx, [rbx]; NumOfElements
0x1800dc34c  mov     rcx, [rbx+8]; Base
0x1800dc350  call    cs:__imp_qsort_s
0x1800dc357  nop     dword ptr [rax+rax+00h]
0x1800dc35c  mov     r13, [rbp+57h+arg_0]
0x1800dc360  lea     r9, CipAuthRootHashSearchCompare; PtFuncCompare
0x1800dc367  mov     r8d, 44h ; 'D'; SizeOfElements
0x1800dc36d  mov     [rsp+0E0h+Context], 0; Context
0x1800dc376  mov     edx, [r13+0]; NumOfElements
0x1800dc37a  mov     rcx, [r13+8]; Base
0x1800dc37e  call    cs:__imp_qsort_s
0x1800dc385  nop     dword ptr [rax+rax+00h]
0x1800dc38a  call    cs:__imp_KeEnterCriticalRegion
0x1800dc391  nop     dword ptr [rax+rax+00h]
0x1800dc396  xor     edx, edx
0x1800dc398  lea     rcx, g_CiAuthRootStoreLock
0x1800dc39f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800dc3a6  nop     dword ptr [rax+rax+00h]
0x1800dc3ab  mov     rax, [rbp+57h+arg_8]
0x1800dc3af  mov     cs:qword_180048548, rax
0x1800dc3b6  mov     rax, [rbp+57h+arg_10]
0x1800dc3ba  mov     cs:qword_180048558, rax
0x1800dc3c1  test    r15b, r15b
0x1800dc3c4  jz      short loc_1800DC3D4
0x1800dc3c6  mov     cs:byte_180048560, r15b
0x1800dc3cd  mov     cs:byte_180048562, 1
0x1800dc3d4  test    r12b, r12b
0x1800dc3d7  jz      short loc_1800DC3E0
0x1800dc3d9  mov     cs:byte_180048561, r12b
0x1800dc3e0  test    r14b, r14b
0x1800dc3e3  jz      short loc_1800DC3EC
0x1800dc3e5  mov     cs:byte_180048562, r14b
0x1800dc3ec  mov     rcx, cs:qword_180048540
0x1800dc3f3  test    rcx, rcx
0x1800dc3f6  jz      short loc_1800DC425
0x1800dc3f8  mov     rcx, [rcx+8]; P
0x1800dc3fc  mov     edx, 63734943h; Tag
0x1800dc401  call    cs:__imp_ExFreePoolWithTag
0x1800dc408  nop     dword ptr [rax+rax+00h]
0x1800dc40d  mov     rcx, cs:qword_180048540; P
0x1800dc414  mov     edx, 63734943h; Tag
0x1800dc419  call    cs:__imp_ExFreePoolWithTag
0x1800dc420  nop     dword ptr [rax+rax+00h]
0x1800dc425  mov     rcx, cs:qword_180048550
0x1800dc42c  test    rcx, rcx
0x1800dc42f  jz      short loc_1800DC45E
0x1800dc431  mov     rcx, [rcx+8]; P
0x1800dc435  mov     edx, 63734943h; Tag
0x1800dc43a  call    cs:__imp_ExFreePoolWithTag
0x1800dc441  nop     dword ptr [rax+rax+00h]
0x1800dc446  mov     rcx, cs:qword_180048550; P
0x1800dc44d  mov     edx, 63734943h; Tag
0x1800dc452  call    cs:__imp_ExFreePoolWithTag
0x1800dc459  nop     dword ptr [rax+rax+00h]
0x1800dc45e  mov     cs:qword_180048540, rbx
0x1800dc465  lea     rcx, g_CiAuthRootStoreLock
0x1800dc46c  xor     edx, edx
0x1800dc46e  mov     cs:qword_180048550, r13
0x1800dc475  xor     ebx, ebx
0x1800dc477  mov     [rbp+57h+arg_18], 0
0x1800dc47f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800dc486  nop     dword ptr [rax+rax+00h]
0x1800dc48b  call    cs:__imp_KeLeaveCriticalRegion
0x1800dc492  nop     dword ptr [rax+rax+00h]
0x1800dc497  jmp     loc_1800DC155
0x1800dc49c  mov     edi, 0C0000428h
0x1800dc4a1  jmp     loc_1800DC327
```
