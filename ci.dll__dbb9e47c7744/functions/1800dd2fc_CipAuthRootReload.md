# CipAuthRootReload

- ea: `0x1800dd2fc`
- end: `0x1800dd76e`
- name: `CipAuthRootReload`
- size: `1138`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800dd088`
- `0x1800dd2c4`

## callees

- `0x18006027c`
- `0x18007277c`
- `0x180093a64`
- `0x18009860c`
- `0x1800dd2fc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800dd652`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800dd652`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800dd667`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800dd667`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800dd747`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800dd747`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd42a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd444`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd45e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd478`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd491`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd702`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd71a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd42a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd444`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd45e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd478`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd491`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd702`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800dd71a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800dd753`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800dd753`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800dd35f`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800dd35f`
- `ntoskrnl!qsort_s` at `0x1800dd618`
- `ntoskrnl!qsort_s` at `0x1800dd646`
- `ntoskrnl!qsort_s` at `0x1800dd618`
- `ntoskrnl!qsort_s` at `0x1800dd646`

## string_xrefs

- `0x1800dd3f3`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x1800dd4f7`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`
- `0x1800dd529`: `\Registry\Machine\Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

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
  v2 = qword_180049560;
  v3 = qword_180049550;
  v4 = byte_180049568;
  v5 = byte_180049569;
  v6 = byte_18004956A;
  v16 = qword_180049550;
  if ( byte_180049568 )
  {
    if ( byte_180049569 )
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
    qword_180049550 = v24;
    qword_180049560 = v25;
    if ( v4 )
    {
      byte_180049568 = v4;
      byte_18004956A = 1;
    }
    if ( v12 )
      byte_180049569 = v12;
    if ( v6 )
      byte_18004956A = v6;
    if ( qword_180049548 )
    {
      ExFreePoolWithTag(*((PVOID *)qword_180049548 + 1), 0x63734943u);
      ExFreePoolWithTag(qword_180049548, 0x63734943u);
    }
    if ( qword_180049558 )
    {
      ExFreePoolWithTag(*((PVOID *)qword_180049558 + 1), 0x63734943u);
      ExFreePoolWithTag(qword_180049558, 0x63734943u);
    }
    qword_180049548 = v13;
    qword_180049558 = v14;
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
0x1800dd2fc  push    rbp
0x1800dd2fe  push    rbx
0x1800dd2ff  push    rsi
0x1800dd300  push    rdi
0x1800dd301  push    r12
0x1800dd303  push    r13
0x1800dd305  push    r14
0x1800dd307  push    r15
0x1800dd309  lea     rbp, [rsp-1Fh]
0x1800dd30e  sub     rsp, 0A8h
0x1800dd315  xor     edi, edi
0x1800dd317  xorps   xmm1, xmm1
0x1800dd31a  xor     ebx, ebx
0x1800dd31c  mov     [rbp+57h+arg_8], rdi
0x1800dd320  test    cs:g_CiPolicyState, 2000h
0x1800dd32a  xorps   xmm0, xmm0
0x1800dd32d  mov     [rbp+57h+arg_10], rdi
0x1800dd331  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800dd335  mov     [rbp+57h+arg_18], rdi
0x1800dd339  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x1800dd33d  mov     [rbp+57h+arg_0], rbx
0x1800dd341  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1800dd345  movups  [rbp+57h+var_70], xmm1
0x1800dd349  movups  [rbp+57h+var_60], xmm1
0x1800dd34d  movups  [rbp+57h+var_50], xmm1
0x1800dd351  jz      loc_1800DD419
0x1800dd357  lea     rcx, [rbp+57h+var_B0]
0x1800dd35b  mov     [rbp+57h+var_B0], rbx
0x1800dd35f  call    cs:__imp_KeQuerySystemTimePrecise
0x1800dd366  nop     dword ptr [rax+rax+00h]
0x1800dd36b  mov     rax, cs:g_CiAuthRootStore
0x1800dd372  mov     r13, cs:qword_180049560
0x1800dd379  mov     rcx, cs:qword_180049550
0x1800dd380  mov     r15b, cs:byte_180049568
0x1800dd387  movzx   esi, cs:byte_180049569
0x1800dd38e  mov     r14b, cs:byte_18004956A
0x1800dd395  mov     [rbp+57h+var_A8], rcx
0x1800dd399  test    r15b, r15b
0x1800dd39c  jz      short loc_1800DD3D6
0x1800dd39e  test    sil, sil
0x1800dd3a1  jz      short loc_1800DD3D6
0x1800dd3a3  test    rax, rax
0x1800dd3a6  jz      short loc_1800DD3D6
0x1800dd3a8  mov     rcx, [rbp+57h+var_B0]
0x1800dd3ac  sub     rcx, rax
0x1800dd3af  mov     rax, 0D6BF94D5E57A42BDh
0x1800dd3b9  imul    rcx
0x1800dd3bc  add     rdx, rcx
0x1800dd3bf  sar     rdx, 17h
0x1800dd3c3  mov     rax, rdx
0x1800dd3c6  shr     rax, 3Fh
0x1800dd3ca  add     rdx, rax
0x1800dd3cd  cmp     rdx, 15180h
0x1800dd3d4  jb      short loc_1800DD419
0x1800dd3d6  lea     rax, [rbp+57h+P]
0x1800dd3da  mov     r12d, 1
0x1800dd3e0  mov     [rsp+0E0h+var_B8], rax
0x1800dd3e5  lea     r8, aEncodedctl; "EncodedCtl"
0x1800dd3ec  lea     rax, [rbp+57h+P+8]
0x1800dd3f0  mov     r9d, r12d
0x1800dd3f3  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dd3fa  mov     [rsp+0E0h+Context], rax
0x1800dd3ff  call    CipGetRegistryValue2
0x1800dd404  mov     edi, eax
0x1800dd406  test    eax, eax
0x1800dd408  jns     loc_1800DD4DD
0x1800dd40e  test    r14b, r14b
0x1800dd411  jz      loc_1800DD4C3
0x1800dd417  xor     edi, edi
0x1800dd419  mov     rsi, [rbp+57h+P+8]
0x1800dd41d  test    rsi, rsi
0x1800dd420  jz      short loc_1800DD436
0x1800dd422  mov     edx, 63734943h; Tag
0x1800dd427  mov     rcx, rsi; P
0x1800dd42a  call    cs:__imp_ExFreePoolWithTag
0x1800dd431  nop     dword ptr [rax+rax+00h]
0x1800dd436  mov     rcx, [rbp+57h+var_90+8]; P
0x1800dd43a  test    rcx, rcx
0x1800dd43d  jz      short loc_1800DD450
0x1800dd43f  mov     edx, 63734943h; Tag
0x1800dd444  call    cs:__imp_ExFreePoolWithTag
0x1800dd44b  nop     dword ptr [rax+rax+00h]
0x1800dd450  mov     rcx, [rbp+57h+var_80+8]; P
0x1800dd454  test    rcx, rcx
0x1800dd457  jz      short loc_1800DD46A
0x1800dd459  mov     edx, 63734943h; Tag
0x1800dd45e  call    cs:__imp_ExFreePoolWithTag
0x1800dd465  nop     dword ptr [rax+rax+00h]
0x1800dd46a  mov     rcx, [rbp+57h+arg_18]; P
0x1800dd46e  test    rcx, rcx
0x1800dd471  jz      short loc_1800DD484
0x1800dd473  mov     edx, 63734943h; Tag
0x1800dd478  call    cs:__imp_ExFreePoolWithTag
0x1800dd47f  nop     dword ptr [rax+rax+00h]
0x1800dd484  test    rbx, rbx
0x1800dd487  jz      short loc_1800DD49D
0x1800dd489  mov     edx, 63734943h; Tag
0x1800dd48e  mov     rcx, rbx; P
0x1800dd491  call    cs:__imp_ExFreePoolWithTag
0x1800dd498  nop     dword ptr [rax+rax+00h]
0x1800dd49d  cmp     dword ptr [rbp+57h+var_70], 0
0x1800dd4a1  jz      short loc_1800DD4AC
0x1800dd4a3  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800dd4a7  call    I_MincryptFreeChainInfo
0x1800dd4ac  mov     eax, edi
0x1800dd4ae  add     rsp, 0A8h
0x1800dd4b5  pop     r15
0x1800dd4b7  pop     r14
0x1800dd4b9  pop     r13
0x1800dd4bb  pop     r12
0x1800dd4bd  pop     rdi
0x1800dd4be  pop     rsi
0x1800dd4bf  pop     rbx
0x1800dd4c0  pop     rbp
0x1800dd4c1  retn
0x1800dd4c3  lea     rdx, [rbp+57h+P]
0x1800dd4c7  lea     rcx, [rbp+57h+P+8]
0x1800dd4cb  call    CipAuthRootLoadCTLsFromCrypt32Dll
0x1800dd4d0  test    eax, eax
0x1800dd4d2  js      loc_1800DD419
0x1800dd4d8  mov     r14b, r12b
0x1800dd4db  jmp     short loc_1800DD4E0
0x1800dd4dd  mov     r15b, r12b
0x1800dd4e0  lea     rax, [rbp+57h+var_90]
0x1800dd4e4  mov     r9d, r12d
0x1800dd4e7  mov     [rsp+0E0h+var_B8], rax
0x1800dd4ec  lea     r8, aDisallowedcert; "DisallowedCertEncodedCtl"
0x1800dd4f3  lea     rax, [rbp+57h+var_90+8]
0x1800dd4f7  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dd4fe  mov     [rsp+0E0h+Context], rax
0x1800dd503  call    CipGetRegistryValue2
0x1800dd508  mov     edi, eax
0x1800dd50a  test    eax, eax
0x1800dd50c  js      loc_1800DD419
0x1800dd512  lea     rax, [rbp+57h+var_80]
0x1800dd516  mov     r9d, r12d
0x1800dd519  mov     [rsp+0E0h+var_B8], rax
0x1800dd51e  lea     r8, aDisallowedcert_0; "DisallowedCertLastSyncTime"
0x1800dd525  lea     rax, [rbp+57h+var_80+8]
0x1800dd529  lea     rdx, aRegistryMachin_25; "\\Registry\\Machine\\Software\\Microsof"...
0x1800dd530  mov     [rsp+0E0h+Context], rax
0x1800dd535  call    CipGetRegistryValue2
0x1800dd53a  mov     r8d, dword ptr [rbp+57h+P]
0x1800dd53e  lea     r9, [rbp+57h+arg_18]
0x1800dd542  test    eax, eax
0x1800dd544  mov     r12d, esi
0x1800dd547  mov     rsi, [rbp+57h+P+8]
0x1800dd54b  lea     rax, [rbp+57h+arg_8]
0x1800dd54f  mov     [rsp+0E0h+var_B8], rax
0x1800dd554  mov     ecx, 1
0x1800dd559  lea     rax, [rbp+57h+var_70]
0x1800dd55d  mov     rdx, rsi
0x1800dd560  mov     [rsp+0E0h+Context], rax
0x1800dd565  cmovns  r12d, ecx
0x1800dd569  call    CiAuthRootParseCTL
0x1800dd56e  mov     edi, eax
0x1800dd570  test    eax, eax
0x1800dd572  js      loc_1800DD41D
0x1800dd578  cmp     dword ptr [rbp+57h+var_70], ebx
0x1800dd57b  jz      short loc_1800DD595
0x1800dd57d  mov     rcx, qword ptr [rbp+57h+var_60]
0x1800dd581  call    I_MincryptFreeChainInfo
0x1800dd586  xorps   xmm0, xmm0
0x1800dd589  movups  [rbp+57h+var_70], xmm0
0x1800dd58d  movups  [rbp+57h+var_60], xmm0
0x1800dd591  movups  [rbp+57h+var_50], xmm0
0x1800dd595  mov     r8d, dword ptr [rbp+57h+var_90]
0x1800dd599  lea     rax, [rbp+57h+arg_10]
0x1800dd59d  mov     rdx, [rbp+57h+var_90+8]
0x1800dd5a1  lea     r9, [rbp+57h+arg_0]
0x1800dd5a5  mov     [rsp+0E0h+var_B8], rax
0x1800dd5aa  xor     ecx, ecx
0x1800dd5ac  lea     rax, [rbp+57h+var_70]
0x1800dd5b0  mov     [rsp+0E0h+Context], rax
0x1800dd5b5  call    CiAuthRootParseCTL
0x1800dd5ba  mov     edi, eax
0x1800dd5bc  test    eax, eax
0x1800dd5be  js      short loc_1800DD5EF
0x1800dd5c0  cmp     [rbp+57h+arg_10], r13
0x1800dd5c4  jl      loc_1800DD764
0x1800dd5ca  mov     rax, [rbp+57h+var_A8]
0x1800dd5ce  cmp     [rbp+57h+arg_8], rax
0x1800dd5d2  jl      loc_1800DD764
0x1800dd5d8  cmp     [rbp+57h+arg_10], r13
0x1800dd5dc  jnz     short loc_1800DD5F8
0x1800dd5de  cmp     [rbp+57h+arg_8], rax
0x1800dd5e2  jnz     short loc_1800DD5F8
0x1800dd5e4  mov     rax, [rbp+57h+var_B0]
0x1800dd5e8  mov     cs:g_CiAuthRootStore, rax
0x1800dd5ef  mov     rbx, [rbp+57h+arg_0]
0x1800dd5f3  jmp     loc_1800DD41D
0x1800dd5f8  mov     rbx, [rbp+57h+arg_18]
0x1800dd5fc  lea     r9, CipAuthRootHashSearchCompare; PtFuncCompare
0x1800dd603  mov     r8d, 44h ; 'D'; SizeOfElements
0x1800dd609  mov     [rsp+0E0h+Context], 0; Context
0x1800dd612  mov     edx, [rbx]; NumOfElements
0x1800dd614  mov     rcx, [rbx+8]; Base
0x1800dd618  call    cs:__imp_qsort_s
0x1800dd61f  nop     dword ptr [rax+rax+00h]
0x1800dd624  mov     r13, [rbp+57h+arg_0]
0x1800dd628  lea     r9, CipAuthRootHashSearchCompare; PtFuncCompare
0x1800dd62f  mov     r8d, 44h ; 'D'; SizeOfElements
0x1800dd635  mov     [rsp+0E0h+Context], 0; Context
0x1800dd63e  mov     edx, [r13+0]; NumOfElements
0x1800dd642  mov     rcx, [r13+8]; Base
0x1800dd646  call    cs:__imp_qsort_s
0x1800dd64d  nop     dword ptr [rax+rax+00h]
0x1800dd652  call    cs:__imp_KeEnterCriticalRegion
0x1800dd659  nop     dword ptr [rax+rax+00h]
0x1800dd65e  xor     edx, edx
0x1800dd660  lea     rcx, g_CiAuthRootStoreLock
0x1800dd667  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800dd66e  nop     dword ptr [rax+rax+00h]
0x1800dd673  mov     rax, [rbp+57h+arg_8]
0x1800dd677  mov     cs:qword_180049550, rax
0x1800dd67e  mov     rax, [rbp+57h+arg_10]
0x1800dd682  mov     cs:qword_180049560, rax
0x1800dd689  test    r15b, r15b
0x1800dd68c  jz      short loc_1800DD69C
0x1800dd68e  mov     cs:byte_180049568, r15b
0x1800dd695  mov     cs:byte_18004956A, 1
0x1800dd69c  test    r12b, r12b
0x1800dd69f  jz      short loc_1800DD6A8
0x1800dd6a1  mov     cs:byte_180049569, r12b
0x1800dd6a8  test    r14b, r14b
0x1800dd6ab  jz      short loc_1800DD6B4
0x1800dd6ad  mov     cs:byte_18004956A, r14b
0x1800dd6b4  mov     rcx, cs:qword_180049548
0x1800dd6bb  test    rcx, rcx
0x1800dd6be  jz      short loc_1800DD6ED
0x1800dd6c0  mov     rcx, [rcx+8]; P
0x1800dd6c4  mov     edx, 63734943h; Tag
0x1800dd6c9  call    cs:__imp_ExFreePoolWithTag
0x1800dd6d0  nop     dword ptr [rax+rax+00h]
0x1800dd6d5  mov     rcx, cs:qword_180049548; P
0x1800dd6dc  mov     edx, 63734943h; Tag
0x1800dd6e1  call    cs:__imp_ExFreePoolWithTag
0x1800dd6e8  nop     dword ptr [rax+rax+00h]
0x1800dd6ed  mov     rcx, cs:qword_180049558
0x1800dd6f4  test    rcx, rcx
0x1800dd6f7  jz      short loc_1800DD726
0x1800dd6f9  mov     rcx, [rcx+8]; P
0x1800dd6fd  mov     edx, 63734943h; Tag
0x1800dd702  call    cs:__imp_ExFreePoolWithTag
0x1800dd709  nop     dword ptr [rax+rax+00h]
0x1800dd70e  mov     rcx, cs:qword_180049558; P
0x1800dd715  mov     edx, 63734943h; Tag
0x1800dd71a  call    cs:__imp_ExFreePoolWithTag
0x1800dd721  nop     dword ptr [rax+rax+00h]
0x1800dd726  mov     cs:qword_180049548, rbx
0x1800dd72d  lea     rcx, g_CiAuthRootStoreLock
0x1800dd734  xor     edx, edx
0x1800dd736  mov     cs:qword_180049558, r13
0x1800dd73d  xor     ebx, ebx
0x1800dd73f  mov     [rbp+57h+arg_18], 0
0x1800dd747  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800dd74e  nop     dword ptr [rax+rax+00h]
0x1800dd753  call    cs:__imp_KeLeaveCriticalRegion
0x1800dd75a  nop     dword ptr [rax+rax+00h]
0x1800dd75f  jmp     loc_1800DD41D
0x1800dd764  mov     edi, 0C0000428h
0x1800dd769  jmp     loc_1800DD5EF
```
