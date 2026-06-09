# CipAuthRootReload

- ea: `0x1800dd30c`
- end: `0x1800dd77e`
- name: `CipAuthRootReload`
- size: `1138`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800dd098`
- `0x1800dd2d4`

## callees

- `0x18006021c`
- `0x180072a5c`
- `0x18008eddc`
- `0x1800993c4`
- `0x1800dd30c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800dd662`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800dd662`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800dd677`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800dd677`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800dd757`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800dd757`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd43a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd454`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd46e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd4a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd712`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd72a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd43a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd454`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd46e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd4a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd712`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd72a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800dd763`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800dd763`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800dd36f`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800dd36f`
- `ntoskrnl!qsort_s` at `0x1800dd628`
- `ntoskrnl!qsort_s` at `0x1800dd656`
- `ntoskrnl!qsort_s` at `0x1800dd628`
- `ntoskrnl!qsort_s` at `0x1800dd656`

## string_xrefs

- `0x1800dd403`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x1800dd507`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x1800dd539`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

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
  v2 = qword_180049568;
  v3 = qword_180049558;
  v4 = byte_180049570;
  v5 = byte_180049571;
  v6 = byte_180049572;
  v16 = qword_180049558;
  if ( byte_180049570 )
  {
    if ( byte_180049571 )
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
    qword_180049558 = v24;
    qword_180049568 = v25;
    if ( v4 )
    {
      byte_180049570 = v4;
      byte_180049572 = 1;
    }
    if ( v12 )
      byte_180049571 = v12;
    if ( v6 )
      byte_180049572 = v6;
    if ( qword_180049550 )
    {
      ExFreePoolWithTag(*((PVOID *)qword_180049550 + 1), 0x63734943u);
      ExFreePoolWithTag(qword_180049550, 0x63734943u);
    }
    if ( qword_180049560 )
    {
      ExFreePoolWithTag(*((PVOID *)qword_180049560 + 1), 0x63734943u);
      ExFreePoolWithTag(qword_180049560, 0x63734943u);
    }
    qword_180049550 = v13;
    qword_180049560 = v14;
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
0x1800dd30c  push    rbp
0x1800dd30e  push    rbx
0x1800dd30f  push    rsi
0x1800dd310  push    rdi
0x1800dd311  push    r12
0x1800dd313  push    r13
0x1800dd315  push    r14
0x1800dd317  push    r15
0x1800dd319  lea     rbp, [rsp-1Fh]
0x1800dd31e  sub     rsp, 0A8h
0x1800dd325  xor     edi, edi
0x1800dd327  xorps   xmm1, xmm1
0x1800dd32a  xor     ebx, ebx
0x1800dd32c  mov     [rbp+57h+arg_8], rdi
0x1800dd330  test    cs:g_CiPolicyState, 2000h
0x1800dd33a  xorps   xmm0, xmm0
0x1800dd33d  mov     [rbp+57h+arg_10], rdi
0x1800dd341  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800dd345  mov     [rbp+57h+arg_18], rdi
0x1800dd349  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x1800dd34d  mov     [rbp+57h+arg_0], rbx
0x1800dd351  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1800dd355  movups  [rbp+57h+var_70], xmm1
0x1800dd359  movups  [rbp+57h+var_60], xmm1
0x1800dd35d  movups  [rbp+57h+var_50], xmm1
0x1800dd361  jz      loc_1800DD429
0x1800dd367  lea     rcx, [rbp+57h+var_B0]
0x1800dd36b  mov     [rbp+57h+var_B0], rbx
0x1800dd36f  call    cs:__imp_KeQuerySystemTimePrecise
0x1800dd376  nop     dword ptr [rax+rax+00h]
0x1800dd37b  mov     rax, cs:g_CiAuthRootStore
0x1800dd382  mov     r13, cs:qword_180049568
0x1800dd389  mov     rcx, cs:qword_180049558
0x1800dd390  mov     r15b, cs:byte_180049570
0x1800dd397  movzx   esi, cs:byte_180049571
0x1800dd39e  mov     r14b, cs:byte_180049572
0x1800dd3a5  mov     [rbp+57h+var_A8], rcx
0x1800dd3a9  test    r15b, r15b
0x1800dd3ac  jz      short loc_1800DD3E6
0x1800dd3ae  test    sil, sil
0x1800dd3b1  jz      short loc_1800DD3E6
0x1800dd3b3  test    rax, rax
0x1800dd3b6  jz      short loc_1800DD3E6
0x1800dd3b8  mov     rcx, [rbp+57h+var_B0]
0x1800dd3bc  sub     rcx, rax
0x1800dd3bf  mov     rax, 0D6BF94D5E57A42BDh
0x1800dd3c9  imul    rcx
0x1800dd3cc  add     rdx, rcx
0x1800dd3cf  sar     rdx, 17h
0x1800dd3d3  mov     rax, rdx
0x1800dd3d6  shr     rax, 3Fh
0x1800dd3da  add     rdx, rax
0x1800dd3dd  cmp     rdx, 15180h
0x1800dd3e4  jb      short loc_1800DD429
0x1800dd3e6  lea     rax, [rbp+57h+P]
0x1800dd3ea  mov     r12d, 1
0x1800dd3f0  mov     [rsp+0E0h+var_B8], rax
0x1800dd3f5  lea     r8, aEncodedctl; "EncodedCtl"
0x1800dd3fc  lea     rax, [rbp+57h+P+8]
0x1800dd400  mov     r9d, r12d
0x1800dd403  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dd40a  mov     [rsp+0E0h+Context], rax
0x1800dd40f  call    CipGetRegistryValue2
0x1800dd414  mov     edi, eax
0x1800dd416  test    eax, eax
0x1800dd418  jns     loc_1800DD4ED
0x1800dd41e  test    r14b, r14b
0x1800dd421  jz      loc_1800DD4D3
0x1800dd427  xor     edi, edi
0x1800dd429  mov     rsi, [rbp+57h+P+8]
0x1800dd42d  test    rsi, rsi
0x1800dd430  jz      short loc_1800DD446
0x1800dd432  mov     edx, 63734943h; Tag
0x1800dd437  mov     rcx, rsi; P
0x1800dd43a  call    cs:__imp_ExFreePoolWithTag
0x1800dd441  nop     dword ptr [rax+rax+00h]
0x1800dd446  mov     rcx, [rbp+57h+var_90+8]; P
0x1800dd44a  test    rcx, rcx
0x1800dd44d  jz      short loc_1800DD460
0x1800dd44f  mov     edx, 63734943h; Tag
0x1800dd454  call    cs:__imp_ExFreePoolWithTag
0x1800dd45b  nop     dword ptr [rax+rax+00h]
0x1800dd460  mov     rcx, [rbp+57h+var_80+8]; P
0x1800dd464  test    rcx, rcx
0x1800dd467  jz      short loc_1800DD47A
0x1800dd469  mov     edx, 63734943h; Tag
0x1800dd46e  call    cs:__imp_ExFreePoolWithTag
0x1800dd475  nop     dword ptr [rax+rax+00h]
0x1800dd47a  mov     rcx, [rbp+57h+arg_18]; P
0x1800dd47e  test    rcx, rcx
0x1800dd481  jz      short loc_1800DD494
0x1800dd483  mov     edx, 63734943h; Tag
0x1800dd488  call    cs:__imp_ExFreePoolWithTag
0x1800dd48f  nop     dword ptr [rax+rax+00h]
0x1800dd494  test    rbx, rbx
0x1800dd497  jz      short loc_1800DD4AD
0x1800dd499  mov     edx, 63734943h; Tag
0x1800dd49e  mov     rcx, rbx; P
0x1800dd4a1  call    cs:__imp_ExFreePoolWithTag
0x1800dd4a8  nop     dword ptr [rax+rax+00h]
0x1800dd4ad  cmp     dword ptr [rbp+57h+var_70], 0
0x1800dd4b1  jz      short loc_1800DD4BC
0x1800dd4b3  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800dd4b7  call    I_MincryptFreeChainInfo
0x1800dd4bc  mov     eax, edi
0x1800dd4be  add     rsp, 0A8h
0x1800dd4c5  pop     r15
0x1800dd4c7  pop     r14
0x1800dd4c9  pop     r13
0x1800dd4cb  pop     r12
0x1800dd4cd  pop     rdi
0x1800dd4ce  pop     rsi
0x1800dd4cf  pop     rbx
0x1800dd4d0  pop     rbp
0x1800dd4d1  retn
0x1800dd4d3  lea     rdx, [rbp+57h+P]
0x1800dd4d7  lea     rcx, [rbp+57h+P+8]
0x1800dd4db  call    CipAuthRootLoadCTLsFromCrypt32Dll
0x1800dd4e0  test    eax, eax
0x1800dd4e2  js      loc_1800DD429
0x1800dd4e8  mov     r14b, r12b
0x1800dd4eb  jmp     short loc_1800DD4F0
0x1800dd4ed  mov     r15b, r12b
0x1800dd4f0  lea     rax, [rbp+57h+var_90]
0x1800dd4f4  mov     r9d, r12d
0x1800dd4f7  mov     [rsp+0E0h+var_B8], rax
0x1800dd4fc  lea     r8, aDisallowedcert; "DisallowedCertEncodedCtl"
0x1800dd503  lea     rax, [rbp+57h+var_90+8]
0x1800dd507  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dd50e  mov     [rsp+0E0h+Context], rax
0x1800dd513  call    CipGetRegistryValue2
0x1800dd518  mov     edi, eax
0x1800dd51a  test    eax, eax
0x1800dd51c  js      loc_1800DD429
0x1800dd522  lea     rax, [rbp+57h+var_80]
0x1800dd526  mov     r9d, r12d
0x1800dd529  mov     [rsp+0E0h+var_B8], rax
0x1800dd52e  lea     r8, aDisallowedcert_0; "DisallowedCertLastSyncTime"
0x1800dd535  lea     rax, [rbp+57h+var_80+8]
0x1800dd539  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dd540  mov     [rsp+0E0h+Context], rax
0x1800dd545  call    CipGetRegistryValue2
0x1800dd54a  mov     r8d, dword ptr [rbp+57h+P]
0x1800dd54e  lea     r9, [rbp+57h+arg_18]
0x1800dd552  test    eax, eax
0x1800dd554  mov     r12d, esi
0x1800dd557  mov     rsi, [rbp+57h+P+8]
0x1800dd55b  lea     rax, [rbp+57h+arg_8]
0x1800dd55f  mov     [rsp+0E0h+var_B8], rax
0x1800dd564  mov     ecx, 1
0x1800dd569  lea     rax, [rbp+57h+var_70]
0x1800dd56d  mov     rdx, rsi
0x1800dd570  mov     [rsp+0E0h+Context], rax
0x1800dd575  cmovns  r12d, ecx
0x1800dd579  call    CiAuthRootParseCTL
0x1800dd57e  mov     edi, eax
0x1800dd580  test    eax, eax
0x1800dd582  js      loc_1800DD42D
0x1800dd588  cmp     dword ptr [rbp+57h+var_70], ebx
0x1800dd58b  jz      short loc_1800DD5A5
0x1800dd58d  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800dd591  call    I_MincryptFreeChainInfo
0x1800dd596  xorps   xmm0, xmm0
0x1800dd599  movups  [rbp+57h+var_70], xmm0
0x1800dd59d  movups  [rbp+57h+var_60], xmm0
0x1800dd5a1  movups  [rbp+57h+var_50], xmm0
0x1800dd5a5  mov     r8d, dword ptr [rbp+57h+var_90]
0x1800dd5a9  lea     rax, [rbp+57h+arg_10]
0x1800dd5ad  mov     rdx, [rbp+57h+var_90+8]
0x1800dd5b1  lea     r9, [rbp+57h+arg_0]
0x1800dd5b5  mov     [rsp+0E0h+var_B8], rax
0x1800dd5ba  xor     ecx, ecx
0x1800dd5bc  lea     rax, [rbp+57h+var_70]
0x1800dd5c0  mov     [rsp+0E0h+Context], rax
0x1800dd5c5  call    CiAuthRootParseCTL
0x1800dd5ca  mov     edi, eax
0x1800dd5cc  test    eax, eax
0x1800dd5ce  js      short loc_1800DD5FF
0x1800dd5d0  cmp     [rbp+57h+arg_10], r13
0x1800dd5d4  jl      loc_1800DD774
0x1800dd5da  mov     rax, [rbp+57h+var_A8]
0x1800dd5de  cmp     [rbp+57h+arg_8], rax
0x1800dd5e2  jl      loc_1800DD774
0x1800dd5e8  cmp     [rbp+57h+arg_10], r13
0x1800dd5ec  jnz     short loc_1800DD608
0x1800dd5ee  cmp     [rbp+57h+arg_8], rax
0x1800dd5f2  jnz     short loc_1800DD608
0x1800dd5f4  mov     rax, [rbp+57h+var_B0]
0x1800dd5f8  mov     cs:g_CiAuthRootStore, rax
0x1800dd5ff  mov     rbx, [rbp+57h+arg_0]
0x1800dd603  jmp     loc_1800DD42D
0x1800dd608  mov     rbx, [rbp+57h+arg_18]
0x1800dd60c  lea     r9, CipAuthRootHashSearchCompare; PtFuncCompare
0x1800dd613  mov     r8d, 44h ; 'D'; SizeOfElements
0x1800dd619  mov     [rsp+0E0h+Context], 0; Context
0x1800dd622  mov     edx, [rbx]; NumOfElements
0x1800dd624  mov     rcx, [rbx+8]; Base
0x1800dd628  call    cs:__imp_qsort_s
0x1800dd62f  nop     dword ptr [rax+rax+00h]
0x1800dd634  mov     r13, [rbp+57h+arg_0]
0x1800dd638  lea     r9, CipAuthRootHashSearchCompare; PtFuncCompare
0x1800dd63f  mov     r8d, 44h ; 'D'; SizeOfElements
0x1800dd645  mov     [rsp+0E0h+Context], 0; Context
0x1800dd64e  mov     edx, [r13+0]; NumOfElements
0x1800dd652  mov     rcx, [r13+8]; Base
0x1800dd656  call    cs:__imp_qsort_s
0x1800dd65d  nop     dword ptr [rax+rax+00h]
0x1800dd662  call    cs:__imp_KeEnterCriticalRegion
0x1800dd669  nop     dword ptr [rax+rax+00h]
0x1800dd66e  xor     edx, edx
0x1800dd670  lea     rcx, g_CiAuthRootStoreLock
0x1800dd677  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800dd67e  nop     dword ptr [rax+rax+00h]
0x1800dd683  mov     rax, [rbp+57h+arg_8]
0x1800dd687  mov     cs:qword_180049558, rax
0x1800dd68e  mov     rax, [rbp+57h+arg_10]
0x1800dd692  mov     cs:qword_180049568, rax
0x1800dd699  test    r15b, r15b
0x1800dd69c  jz      short loc_1800DD6AC
0x1800dd69e  mov     cs:byte_180049570, r15b
0x1800dd6a5  mov     cs:byte_180049572, 1
0x1800dd6ac  test    r12b, r12b
0x1800dd6af  jz      short loc_1800DD6B8
0x1800dd6b1  mov     cs:byte_180049571, r12b
0x1800dd6b8  test    r14b, r14b
0x1800dd6bb  jz      short loc_1800DD6C4
0x1800dd6bd  mov     cs:byte_180049572, r14b
0x1800dd6c4  mov     rcx, cs:qword_180049550
0x1800dd6cb  test    rcx, rcx
0x1800dd6ce  jz      short loc_1800DD6FD
0x1800dd6d0  mov     rcx, [rcx+8]; P
0x1800dd6d4  mov     edx, 63734943h; Tag
0x1800dd6d9  call    cs:__imp_ExFreePoolWithTag
0x1800dd6e0  nop     dword ptr [rax+rax+00h]
0x1800dd6e5  mov     rcx, cs:qword_180049550; P
0x1800dd6ec  mov     edx, 63734943h; Tag
0x1800dd6f1  call    cs:__imp_ExFreePoolWithTag
0x1800dd6f8  nop     dword ptr [rax+rax+00h]
0x1800dd6fd  mov     rcx, cs:qword_180049560
0x1800dd704  test    rcx, rcx
0x1800dd707  jz      short loc_1800DD736
0x1800dd709  mov     rcx, [rcx+8]; P
0x1800dd70d  mov     edx, 63734943h; Tag
0x1800dd712  call    cs:__imp_ExFreePoolWithTag
0x1800dd719  nop     dword ptr [rax+rax+00h]
0x1800dd71e  mov     rcx, cs:qword_180049560; P
0x1800dd725  mov     edx, 63734943h; Tag
0x1800dd72a  call    cs:__imp_ExFreePoolWithTag
0x1800dd731  nop     dword ptr [rax+rax+00h]
0x1800dd736  mov     cs:qword_180049550, rbx
0x1800dd73d  lea     rcx, g_CiAuthRootStoreLock
0x1800dd744  xor     edx, edx
0x1800dd746  mov     cs:qword_180049560, r13
0x1800dd74d  xor     ebx, ebx
0x1800dd74f  mov     [rbp+57h+arg_18], 0
0x1800dd757  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800dd75e  nop     dword ptr [rax+rax+00h]
0x1800dd763  call    cs:__imp_KeLeaveCriticalRegion
0x1800dd76a  nop     dword ptr [rax+rax+00h]
0x1800dd76f  jmp     loc_1800DD42D
0x1800dd774  mov     edi, 0C0000428h
0x1800dd779  jmp     loc_1800DD5FF
```
