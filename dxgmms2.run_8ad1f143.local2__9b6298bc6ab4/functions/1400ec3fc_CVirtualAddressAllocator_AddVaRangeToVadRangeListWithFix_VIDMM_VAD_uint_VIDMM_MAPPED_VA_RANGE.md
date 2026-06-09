# CVirtualAddressAllocator::AddVaRangeToVadRangeListWithFix(VIDMM_VAD *,uint,VIDMM_MAPPED_VA_RANGE *)

- ea: `0x1400ec3fc`
- end: `0x1400ecb7a`
- name: `?AddVaRangeToVadRangeListWithFix@CVirtualAddressAllocator@@QEAAJPEAUVIDMM_VAD@@IPEAUVIDMM_MAPPED_VA_RANGE@@@Z`
- size: `1918`
- prototype: `__int64 __fastcall(CVirtualAddressAllocator *__hidden this, struct VIDMM_VAD *, unsigned int, struct VIDMM_MAPPED_VA_RANGE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400ec294`

## callees

- `0x1400045ec`
- `0x14002eb94`
- `0x1400311ac`
- `0x140031704`
- `0x14003180c`
- `0x140035530`
- `0x1400ec028`
- `0x1400ec2ac`
- `0x1400ec3fc`
- `0x1400ecb80`
- `0x1400ecba0`
- `0x1400ecd10`
- `0x1400ecd40`
- `0x1400ecde0`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400ec503`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400ec519`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400ec503`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400ec519`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ec5a0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ec6ea`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ec5a0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ec6ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ec607`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ec607`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ec61c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ec61c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ec6c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ecb5d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ec6c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ecb5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ec6cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ecb69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ec6cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ecb69`
- `watchdog!WdLogSingleEntry2` at `0x1400ec543`
- `watchdog!WdLogSingleEntry2` at `0x1400ec543`

## pseudocode

```c
__int64 __fastcall CVirtualAddressAllocator::AddVaRangeToVadRangeListWithFix(
        struct _KTHREAD **this,
        struct VIDMM_VAD *a2,
        unsigned int a3,
        struct VIDMM_MAPPED_VA_RANGE *a4)
{
  __int64 v5; // rdi
  __int64 VidMmGlobalAllocFromOwner; // rbx
  struct _RTL_AVL_TREE *v9; // rax
  _QWORD *v10; // rdi
  _QWORD *v11; // rbx
  int v12; // eax
  _QWORD *v13; // rbp
  _QWORD *v14; // rdi
  int v15; // eax
  struct VIDMM_MAPPED_VA_RANGE *v16; // rbp
  struct VIDMM_MAPPED_VA_RANGE *v17; // rax
  struct VIDMM_MAPPED_VA_RANGE *v18; // r15
  int v19; // ecx
  int v20; // r8d
  unsigned int v21; // edi
  unsigned __int64 *v23; // r14
  struct VIDMM_VAD *v24; // r12
  _QWORD **v25; // rax
  volatile signed __int32 *v26; // rdi
  _QWORD *v27; // rax
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // rbx
  unsigned __int64 v32; // rax
  __int64 v33; // rdx
  int v34; // r9d
  int v35; // r10d
  __int64 v36; // r11
  unsigned __int64 v37; // rax
  __int64 v38; // r9
  __int64 v39; // r10
  __int64 v40; // r11
  _QWORD *v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rdx
  _QWORD *v44; // rax
  __int64 v45; // rcx
  _QWORD *v46; // rdx
  _QWORD *v47; // rcx
  char VidMmAllocFromOwner; // al
  int v49; // r8d
  struct _RTL_AVL_TREE *v50; // [rsp+78h] [rbp-70h]
  unsigned __int64 v51; // [rsp+80h] [rbp-68h]
  __int64 v52; // [rsp+88h] [rbp-60h]
  char v53; // [rsp+F0h] [rbp+8h]
  char v56; // [rsp+108h] [rbp+20h]

  v5 = a3;
  VidMmGlobalAllocFromOwner = GetVidMmGlobalAllocFromOwner(*((_DWORD *)a4 + 18) & 0xF, *((_QWORD *)a4 + 8));
  v52 = VidMmGlobalAllocFromOwner;
  v56 = 0;
  if ( this[9] != KeGetCurrentThread() )
  {
    DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(this + 8));
    v56 = 1;
  }
  v53 = 0;
  if ( VidMmGlobalAllocFromOwner && *(struct _KTHREAD **)(VidMmGlobalAllocFromOwner + 200) != KeGetCurrentThread() )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(VidMmGlobalAllocFromOwner + 192, 0);
    *(_QWORD *)(VidMmGlobalAllocFromOwner + 200) = KeGetCurrentThread();
    v53 = 1;
  }
  v9 = (struct VIDMM_VAD *)((char *)a2 + 24 * v5 + 96);
  v10 = *(_QWORD **)v9;
  v11 = 0;
  v50 = v9;
  while ( 1 )
  {
    if ( !v10 )
      goto LABEL_16;
    v12 = CompareVaRangeAddressWithin((char *)a4 + 104, v10);
    if ( !v12 )
      break;
    if ( v12 >= 0 )
    {
      v10 = (_QWORD *)v10[1];
    }
    else
    {
      v11 = v10;
      v10 = (_QWORD *)*v10;
    }
  }
  v11 = v10;
  v13 = 0;
  v14 = (_QWORD *)*v10;
  if ( !v14 )
    goto LABEL_16;
  do
  {
    v15 = CompareVaRangeAddressWithin((char *)a4 + 104, v14);
    if ( v15 >= 0 )
    {
      if ( v15 > 0 )
      {
        v14 = (_QWORD *)v14[1];
        continue;
      }
      v13 = v14;
    }
    v14 = (_QWORD *)*v14;
  }
  while ( v14 );
  if ( v13 )
    v11 = v13;
LABEL_16:
  v16 = (struct VIDMM_MAPPED_VA_RANGE *)ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
  v17 = (struct VIDMM_MAPPED_VA_RANGE *)ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
  v18 = v17;
  if ( !v16 || !v17 )
  {
    _InterlockedIncrement(&dword_1400867F0);
    WdLogSingleEntry2(6, v16, v17);
    WdLogGlobalForLineNumber = 12195;
    DxgkLogInternalTriageEvent(
      v19,
      262145,
      v20,
      (unsigned int)L"Failed to allocate memory needed for VA range management",
      (__int64)v16,
      (__int64)v18,
      0,
      0);
    v21 = -1073741801;
    goto LABEL_18;
  }
  if ( !(unsigned __int8)ValidateUniqueGpuVaMapping(a4) )
  {
    v21 = -1073741811;
    goto LABEL_18;
  }
  if ( (*((_DWORD *)a4 + 18) & 0x8000) != 0 )
  {
    v41 = (_QWORD *)((char *)a4 + 32);
    v42 = *((_QWORD *)a4 + 4);
    if ( v42 )
    {
      if ( *(_QWORD **)(v42 + 8) != v41 )
        goto LABEL_65;
      v43 = (_QWORD *)*((_QWORD *)a4 + 5);
      if ( (_QWORD *)*v43 != v41 )
        goto LABEL_65;
      *v43 = v42;
      *(_QWORD *)(v42 + 8) = v43;
      *v41 = 0;
      *((_QWORD *)a4 + 5) = 0;
    }
    v44 = (_QWORD *)((char *)a4 + 8);
    v45 = *((_QWORD *)a4 + 1);
    if ( *(struct VIDMM_MAPPED_VA_RANGE **)(v45 + 8) == (struct VIDMM_MAPPED_VA_RANGE *)((char *)a4 + 8) )
    {
      v46 = (_QWORD *)*((_QWORD *)a4 + 2);
      if ( (_QWORD *)*v46 == v44 )
      {
        *v46 = v45;
        *(_QWORD *)(v45 + 8) = v46;
        *v44 = 0;
        *((_QWORD *)a4 + 2) = 0;
        *((_DWORD *)a4 + 18) &= ~0x8000u;
        goto LABEL_35;
      }
    }
LABEL_65:
    __fastfail(3u);
  }
LABEL_35:
  v23 = (unsigned __int64 *)((char *)a4 + 112);
  while ( 2 )
  {
    if ( !v11 )
      goto LABEL_37;
    v25 = (_QWORD **)v11[1];
    v26 = (volatile signed __int32 *)(v11 - 1);
    if ( v25 )
    {
      v47 = *v25;
      if ( *v25 )
      {
        do
        {
          v11 = v47;
          v47 = (_QWORD *)*v47;
        }
        while ( v47 );
      }
      else
      {
        v11 = (_QWORD *)v11[1];
      }
    }
    else
    {
      do
      {
        v27 = v11;
        v11 = (_QWORD *)(v11[2] & 0xFFFFFFFFFFFFFFFCuLL);
      }
      while ( v11 && (_QWORD *)*v11 != v27 );
    }
    v23 = (unsigned __int64 *)((char *)a4 + 112);
    if ( *((_QWORD *)a4 + 14) <= *((_QWORD *)v26 + 13) )
    {
LABEL_37:
      v24 = a2;
      goto LABEL_38;
    }
    _InterlockedIncrement(v26 + 34);
    CVirtualAddressAllocator::RemoveVaRangeFromVad((CVirtualAddressAllocator *)this, (PVOID)v26, 0, 0, 1);
    v28 = *((_QWORD *)a4 + 13);
    v29 = *((_QWORD *)v26 + 13);
    if ( v28 <= v29 )
    {
      v30 = *((_QWORD *)v26 + 14);
      if ( *v23 < v30 )
      {
        v37 = VidMmiCalculateNewOwnerOffset((struct VIDMM_MAPPED_VA_RANGE *)v26, *v23 - v29);
        v24 = a2;
        VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
          v18,
          v26[18] & 0xF,
          a2,
          v40,
          v38,
          a3,
          *((_QWORD *)v26 + 8),
          v37,
          v26[18] & 0xF,
          v39,
          *((_QWORD *)v26 + 11),
          *((_QWORD *)v26 + 16),
          *((_QWORD *)v26 + 15),
          *((_DWORD *)v26 + 18));
        CVirtualAddressAllocator::AddVaRangeToVadWithFix((CVirtualAddressAllocator *)this, a2, v50, v18);
        VidMmiLogEndVaRangeMapping(
          (struct CVirtualAddressAllocator *)this,
          (struct VIDMM_MAPPED_VA_RANGE *)v26,
          *((_QWORD *)v26 + 10),
          *((_QWORD *)v26 + 13),
          *v23);
        goto LABEL_52;
      }
      goto LABEL_47;
    }
    v51 = *((_QWORD *)v26 + 14);
    if ( *v23 >= v51 )
    {
      if ( v16 )
        VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
          v16,
          v28,
          a2,
          v29,
          v28,
          a3,
          *((_QWORD *)v26 + 8),
          *((_QWORD *)v26 + 10),
          v26[18] & 0xF,
          *((_QWORD *)v26 + 12),
          *((_QWORD *)v26 + 11),
          *((_QWORD *)v26 + 16),
          *((_QWORD *)v26 + 15),
          *((_DWORD *)v26 + 18));
      CVirtualAddressAllocator::AddVaRangeToVadWithFix((CVirtualAddressAllocator *)this, a2, v50, v16);
      v30 = *((_QWORD *)v26 + 14);
      v16 = 0;
      v29 = *((_QWORD *)a4 + 13);
LABEL_47:
      VidMmiLogEndVaRangeMapping(
        (struct CVirtualAddressAllocator *)this,
        (struct VIDMM_MAPPED_VA_RANGE *)v26,
        *((_QWORD *)v26 + 10),
        v29,
        v30);
      VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference((PVOID)v26);
      continue;
    }
    break;
  }
  if ( v16 )
    VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
      v16,
      v28,
      a2,
      v29,
      v28,
      a3,
      *((_QWORD *)v26 + 8),
      *((_QWORD *)v26 + 10),
      v26[18] & 0xF,
      *((_QWORD *)v26 + 12),
      *((_QWORD *)v26 + 11),
      *((_QWORD *)v26 + 16),
      *((_QWORD *)v26 + 15),
      *((_DWORD *)v26 + 18));
  CVirtualAddressAllocator::AddVaRangeToVadWithFix((CVirtualAddressAllocator *)this, a2, v50, v16);
  v31 = VidMmiCalculateNewOwnerOffset((struct VIDMM_MAPPED_VA_RANGE *)v26, *((_QWORD *)a4 + 13) - v29);
  v32 = VidMmiCalculateNewOwnerOffset((struct VIDMM_MAPPED_VA_RANGE *)v26, *v23 - v29);
  v24 = a2;
  VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
    v18,
    v33,
    a2,
    v36,
    v51,
    a3,
    *((_QWORD *)v26 + 8),
    v32,
    v35,
    *((_QWORD *)v26 + 12),
    *((_QWORD *)v26 + 11),
    *((_QWORD *)v26 + 16),
    *((_QWORD *)v26 + 15),
    v34);
  CVirtualAddressAllocator::AddVaRangeToVadWithFix((CVirtualAddressAllocator *)this, a2, v50, v18);
  VidMmiLogEndVaRangeMapping(
    (struct CVirtualAddressAllocator *)this,
    (struct VIDMM_MAPPED_VA_RANGE *)v26,
    v31,
    *((_QWORD *)a4 + 13),
    *v23);
  v16 = 0;
LABEL_52:
  v18 = 0;
  VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference((PVOID)v26);
LABEL_38:
  CVirtualAddressAllocator::AddVaRangeToVadWithFix((CVirtualAddressAllocator *)this, v24, v50, a4);
  if ( byte_140086202 < 0 )
  {
    VidMmAllocFromOwner = GetVidMmAllocFromOwner(*((_DWORD *)a4 + 18) & 0xF, *((_QWORD *)a4 + 8));
    McTemplateK0ppxxxxxqxx_EtwWriteTransfer(
      *((_QWORD *)a4 + 10),
      (unsigned int)UpdateGpuVirtualAddressRangeMapping,
      v49,
      (_DWORD)this,
      VidMmAllocFromOwner,
      *((_QWORD *)a4 + 10),
      *((_QWORD *)a4 + 13),
      *v23,
      *((_QWORD *)a4 + 12),
      *((_QWORD *)a4 + 11),
      v49,
      *((_QWORD *)a4 + 15),
      *((_QWORD *)a4 + 16));
  }
  v21 = 0;
LABEL_18:
  if ( v53 )
  {
    *(_QWORD *)(v52 + 200) = 0;
    ExReleasePushLockExclusiveEx(v52 + 192, 0);
    KeLeaveCriticalRegion();
  }
  if ( v16 )
    ExFreeToLookasideListEx(&g_VaRangeLookasideList, v16);
  if ( v18 )
    ExFreeToLookasideListEx(&g_VaRangeLookasideList, v18);
  if ( v56 )
  {
    this[9] = 0;
    ExReleasePushLockExclusiveEx(this + 8, 0);
    KeLeaveCriticalRegion();
  }
  return v21;
}

```

## disassembly

```asm
0x1400ec3fc  mov     [rsp+arg_10], r8d
0x1400ec401  mov     [rsp+arg_8], rdx
0x1400ec406  push    rbx
0x1400ec407  push    rbp
0x1400ec408  push    rsi
0x1400ec409  push    rdi
0x1400ec40a  push    r12
0x1400ec40c  push    r13
0x1400ec40e  push    r14
0x1400ec410  push    r15
0x1400ec412  sub     rsp, 0A8h
0x1400ec419  mov     r13, rcx
0x1400ec41c  mov     edi, r8d
0x1400ec41f  mov     ecx, [r9+48h]
0x1400ec423  mov     r12, rdx
0x1400ec426  mov     rdx, [r9+40h]
0x1400ec42a  and     ecx, 0Fh
0x1400ec42d  mov     rsi, r9
0x1400ec430  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x1400ec435  mov     rbx, rax
0x1400ec438  mov     [rsp+0E8h+var_60], rax
0x1400ec440  lea     rax, [r13+40h]
0x1400ec444  mov     [rsp+0E8h+arg_18], 0
0x1400ec44c  mov     rdx, [rax+8]
0x1400ec450  mov     rcx, gs:188h
0x1400ec459  mov     [rsp+0E8h+var_58], rax
0x1400ec461  cmp     rdx, rcx
0x1400ec464  jz      short loc_1400EC476
0x1400ec466  mov     rcx, rax; this
0x1400ec469  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1400ec46e  mov     [rsp+0E8h+arg_18], 1
0x1400ec476  mov     [rsp+0E8h+arg_0], 0
0x1400ec47e  test    rbx, rbx
0x1400ec481  jnz     loc_1400EC5EE
0x1400ec487  lea     rax, [rdi+4]
0x1400ec48b  lea     rax, [rax+rax*2]
0x1400ec48f  lea     rax, [r12+rax*8]
0x1400ec493  xor     r12d, r12d
0x1400ec496  mov     rdi, [rax]
0x1400ec499  mov     ebx, r12d
0x1400ec49c  mov     [rsp+0E8h+var_70], rax
0x1400ec4a1  test    rdi, rdi
0x1400ec4a4  jz      short loc_1400EC4FC
0x1400ec4a6  mov     rdx, rdi
0x1400ec4a9  lea     rcx, [rsi+68h]
0x1400ec4ad  call    CompareVaRangeAddressWithin
0x1400ec4b2  test    eax, eax
0x1400ec4b4  jz      short loc_1400EC4C4
0x1400ec4b6  jns     loc_1400EC5E5
0x1400ec4bc  mov     rbx, rdi
0x1400ec4bf  mov     rdi, [rdi]
0x1400ec4c2  jmp     short loc_1400EC4A1
0x1400ec4c4  mov     rbx, rdi
0x1400ec4c7  mov     rbp, r12
0x1400ec4ca  mov     rdi, [rdi]
0x1400ec4cd  test    rdi, rdi
0x1400ec4d0  jz      short loc_1400EC4FC
0x1400ec4d2  mov     rdx, rdi
0x1400ec4d5  lea     rcx, [rsi+68h]
0x1400ec4d9  call    CompareVaRangeAddressWithin
0x1400ec4de  test    eax, eax
0x1400ec4e0  js      loc_1400EC5DD
0x1400ec4e6  jle     loc_1400EC5DA
0x1400ec4ec  mov     rdi, [rdi+8]
0x1400ec4f0  test    rdi, rdi
0x1400ec4f3  jnz     short loc_1400EC4D2
0x1400ec4f5  test    rbp, rbp
0x1400ec4f8  cmovnz  rbx, rbp
0x1400ec4fc  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1400ec503  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400ec50a  nop     dword ptr [rax+rax+00h]
0x1400ec50f  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1400ec516  mov     rbp, rax
0x1400ec519  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400ec520  nop     dword ptr [rax+rax+00h]
0x1400ec525  mov     r15, rax
0x1400ec528  test    rbp, rbp
0x1400ec52b  jnz     loc_1400EC645
0x1400ec531  lock inc cs:dword_1400867F0
0x1400ec538  mov     r8, r15
0x1400ec53b  mov     rdx, rbp
0x1400ec53e  mov     ecx, 6
0x1400ec543  call    cs:__imp_WdLogSingleEntry2
0x1400ec54a  nop     dword ptr [rax+rax+00h]
0x1400ec54f  mov     [rsp+0E8h+var_B0], r12
0x1400ec554  lea     r9, aFailedToAlloca_30; "Failed to allocate memory needed for VA"...
0x1400ec55b  mov     [rsp+0E8h+var_B8], r12
0x1400ec560  mov     edx, 40001h
0x1400ec565  mov     [rsp+0E8h+var_C0], r15
0x1400ec56a  mov     qword ptr [rsp+0E8h+var_C8], rbp
0x1400ec56f  mov     cs:WdLogGlobalForLineNumber, 2FA3h
0x1400ec579  call    DxgkLogInternalTriageEvent
0x1400ec57e  mov     edi, 0C0000017h
0x1400ec583  cmp     [rsp+0E8h+arg_0], r12b
0x1400ec58b  jnz     loc_1400EC6AB
0x1400ec591  test    rbp, rbp
0x1400ec594  jz      short loc_1400EC5AC
0x1400ec596  mov     rdx, rbp; Entry
0x1400ec599  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1400ec5a0  call    cs:__imp_ExFreeToLookasideListEx
0x1400ec5a7  nop     dword ptr [rax+rax+00h]
0x1400ec5ac  test    r15, r15
0x1400ec5af  jnz     loc_1400EC6E0
0x1400ec5b5  cmp     [rsp+0E8h+arg_18], r12b
0x1400ec5bd  jnz     loc_1400ECB4F
0x1400ec5c3  mov     eax, edi
0x1400ec5c5  add     rsp, 0A8h
0x1400ec5cc  pop     r15
0x1400ec5ce  pop     r14
0x1400ec5d0  pop     r13
0x1400ec5d2  pop     r12
0x1400ec5d4  pop     rdi
0x1400ec5d5  pop     rsi
0x1400ec5d6  pop     rbp
0x1400ec5d7  pop     rbx
0x1400ec5d8  retn
0x1400ec5da  mov     rbp, rdi
0x1400ec5dd  mov     rdi, [rdi]
0x1400ec5e0  jmp     loc_1400EC4F0
0x1400ec5e5  mov     rdi, [rdi+8]
0x1400ec5e9  jmp     loc_1400EC4A1
0x1400ec5ee  mov     rcx, [rbx+0C8h]
0x1400ec5f5  mov     rax, gs:188h
0x1400ec5fe  cmp     rcx, rax
0x1400ec601  jz      loc_1400EC487
0x1400ec607  call    cs:__imp_KeEnterCriticalRegion
0x1400ec60e  nop     dword ptr [rax+rax+00h]
0x1400ec613  xor     edx, edx
0x1400ec615  lea     rcx, [rbx+0C0h]
0x1400ec61c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400ec623  nop     dword ptr [rax+rax+00h]
0x1400ec628  mov     rax, gs:188h
0x1400ec631  mov     [rbx+0C8h], rax
0x1400ec638  mov     [rsp+0E8h+arg_0], 1
0x1400ec640  jmp     loc_1400EC487
0x1400ec645  test    r15, r15
0x1400ec648  jz      loc_1400EC531
0x1400ec64e  mov     rcx, rsi
0x1400ec651  call    ValidateUniqueGpuVaMapping
0x1400ec656  test    al, al
0x1400ec658  jz      loc_1400EC9CA
0x1400ec65e  test    dword ptr [rsi+48h], 8000h
0x1400ec665  jnz     loc_1400EC949
0x1400ec66b  lea     r14, [rsi+70h]
0x1400ec66f  test    rbx, rbx
0x1400ec672  jnz     loc_1400EC6FB
0x1400ec678  mov     r12, [rsp+0E8h+arg_8]
0x1400ec680  mov     r8, [rsp+0E8h+var_70]; struct _RTL_AVL_TREE *
0x1400ec685  mov     r9, rsi; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec688  mov     rdx, r12; struct VIDMM_VAD *
0x1400ec68b  mov     rcx, r13; this
0x1400ec68e  call    ?AddVaRangeToVadWithFix@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_VAD@@PEAU_RTL_AVL_TREE@@PEAUVIDMM_MAPPED_VA_RANGE@@@Z; CVirtualAddressAllocator::AddVaRangeToVadWithFix(VIDMM_VAD *,_RTL_AVL_TREE *,VIDMM_MAPPED_VA_RANGE *)
0x1400ec693  xor     r12d, r12d
0x1400ec696  cmp     cs:byte_140086202, r12b
0x1400ec69d  jl      loc_1400ECADD
0x1400ec6a3  mov     edi, r12d
0x1400ec6a6  jmp     loc_1400EC583
0x1400ec6ab  mov     rcx, [rsp+0E8h+var_60]
0x1400ec6b3  xor     edx, edx
0x1400ec6b5  mov     [rcx+0C8h], r12
0x1400ec6bc  add     rcx, 0C0h
0x1400ec6c3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400ec6ca  nop     dword ptr [rax+rax+00h]
0x1400ec6cf  call    cs:__imp_KeLeaveCriticalRegion
0x1400ec6d6  nop     dword ptr [rax+rax+00h]
0x1400ec6db  jmp     loc_1400EC591
0x1400ec6e0  mov     rdx, r15; Entry
0x1400ec6e3  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1400ec6ea  call    cs:__imp_ExFreeToLookasideListEx
0x1400ec6f1  nop     dword ptr [rax+rax+00h]
0x1400ec6f6  jmp     loc_1400EC5B5
0x1400ec6fb  mov     rax, [rbx+8]
0x1400ec6ff  lea     rdi, [rbx-8]
0x1400ec703  test    rax, rax
0x1400ec706  jnz     loc_1400EC9A0
0x1400ec70c  mov     rax, rbx
0x1400ec70f  mov     rbx, [rbx+10h]
0x1400ec713  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400ec717  jz      short loc_1400EC71E
0x1400ec719  cmp     [rbx], rax
0x1400ec71c  jnz     short loc_1400EC70C
0x1400ec71e  mov     rax, [rdi+68h]
0x1400ec722  lea     r14, [rsi+70h]
0x1400ec726  cmp     [r14], rax
0x1400ec729  jbe     loc_1400EC678
0x1400ec72f  lock inc dword ptr [rdi+88h]
0x1400ec736  xor     r9d, r9d; bool
0x1400ec739  mov     [rsp+0E8h+var_C8], 1; bool
0x1400ec73e  xor     r8d, r8d; bool
0x1400ec741  mov     rdx, rdi; Entry
0x1400ec744  mov     rcx, r13; this
0x1400ec747  call    ?RemoveVaRangeFromVad@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_MAPPED_VA_RANGE@@_N11@Z; CVirtualAddressAllocator::RemoveVaRangeFromVad(VIDMM_MAPPED_VA_RANGE *,bool,bool,bool)
0x1400ec74c  mov     rdx, [rsi+68h]
0x1400ec750  mov     r12, [rdi+68h]
0x1400ec754  cmp     rdx, r12
0x1400ec757  ja      short loc_1400EC78D
0x1400ec759  mov     r9, [rdi+70h]
0x1400ec75d  mov     r11, [r14]
0x1400ec760  cmp     r11, r9
0x1400ec763  jb      loc_1400EC89D
0x1400ec769  mov     r8, [rdi+50h]; unsigned __int64
0x1400ec76d  mov     rdx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec770  mov     qword ptr [rsp+0E8h+var_C8], r9; unsigned __int64
0x1400ec775  mov     rcx, r13; struct CVirtualAddressAllocator *
0x1400ec778  mov     r9, r12; unsigned __int64
0x1400ec77b  call    ?VidMmiLogEndVaRangeMapping@@YAXPEAVCVirtualAddressAllocator@@PEAUVIDMM_MAPPED_VA_RANGE@@_K22@Z; VidMmiLogEndVaRangeMapping(CVirtualAddressAllocator *,VIDMM_MAPPED_VA_RANGE *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1400ec780  mov     rcx, rdi; Entry
0x1400ec783  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1400ec788  jmp     loc_1400EC66F
0x1400ec78d  mov     rax, [rdi+70h]
0x1400ec791  mov     [rsp+0E8h+var_68], rax
0x1400ec799  cmp     [r14], rax
0x1400ec79c  jnb     loc_1400EC9D4
0x1400ec7a2  test    rbp, rbp
0x1400ec7a5  jnz     loc_1400ECA6C
0x1400ec7ab  mov     r8, [rsp+0E8h+var_70]; struct _RTL_AVL_TREE *
0x1400ec7b0  mov     r9, rbp; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec7b3  mov     rdx, [rsp+0E8h+arg_8]; struct VIDMM_VAD *
0x1400ec7bb  mov     rcx, r13; this
0x1400ec7be  call    ?AddVaRangeToVadWithFix@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_VAD@@PEAU_RTL_AVL_TREE@@PEAUVIDMM_MAPPED_VA_RANGE@@@Z; CVirtualAddressAllocator::AddVaRangeToVadWithFix(VIDMM_VAD *,_RTL_AVL_TREE *,VIDMM_MAPPED_VA_RANGE *)
0x1400ec7c3  mov     rdx, [rsi+68h]
0x1400ec7c7  mov     rcx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec7ca  sub     rdx, r12; __int64
0x1400ec7cd  call    ?VidMmiCalculateNewOwnerOffset@@YA_KPEAUVIDMM_MAPPED_VA_RANGE@@_J@Z; VidMmiCalculateNewOwnerOffset(VIDMM_MAPPED_VA_RANGE *,__int64)
0x1400ec7d2  mov     r11, [r14]
0x1400ec7d5  mov     rcx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec7d8  mov     r9d, [rdi+48h]
0x1400ec7dc  mov     rdx, r11
0x1400ec7df  mov     r10d, r9d
0x1400ec7e2  sub     rdx, r12; __int64
0x1400ec7e5  mov     rbx, rax
0x1400ec7e8  and     r10d, 0Fh
0x1400ec7ec  call    ?VidMmiCalculateNewOwnerOffset@@YA_KPEAUVIDMM_MAPPED_VA_RANGE@@_J@Z; VidMmiCalculateNewOwnerOffset(VIDMM_MAPPED_VA_RANGE *,__int64)
0x1400ec7f1  mov     rcx, [rdi+78h]
0x1400ec7f5  mov     r12, [rsp+0E8h+arg_8]
0x1400ec7fd  mov     [rsp+0E8h+var_80], r9d
0x1400ec802  mov     r8, r12
0x1400ec805  mov     [rsp+0E8h+var_88], rcx
0x1400ec80a  mov     r9, r11
0x1400ec80d  mov     rcx, [rdi+80h]
0x1400ec814  mov     [rsp+0E8h+var_90], rcx
0x1400ec819  mov     rcx, [rdi+58h]
0x1400ec81d  mov     [rsp+0E8h+var_98], rcx
0x1400ec822  mov     rcx, [rdi+60h]
0x1400ec826  mov     [rsp+0E8h+var_A0], rcx
0x1400ec82b  mov     rcx, r15
0x1400ec82e  mov     dword ptr [rsp+0E8h+var_A8], r10d
0x1400ec833  mov     [rsp+0E8h+var_B0], rax
0x1400ec838  mov     rax, [rdi+40h]
0x1400ec83c  mov     [rsp+0E8h+var_B8], rax
0x1400ec841  mov     eax, [rsp+0E8h+arg_10]
0x1400ec848  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1400ec84c  mov     rax, [rsp+0E8h+var_68]
0x1400ec854  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1400ec859  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
0x1400ec85e  mov     r8, [rsp+0E8h+var_70]; struct _RTL_AVL_TREE *
0x1400ec863  mov     rdx, r12; struct VIDMM_VAD *
0x1400ec866  mov     rcx, r13; this
0x1400ec869  mov     r9, r15; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec86c  call    ?AddVaRangeToVadWithFix@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_VAD@@PEAU_RTL_AVL_TREE@@PEAUVIDMM_MAPPED_VA_RANGE@@@Z; CVirtualAddressAllocator::AddVaRangeToVadWithFix(VIDMM_VAD *,_RTL_AVL_TREE *,VIDMM_MAPPED_VA_RANGE *)
0x1400ec871  mov     rax, [r14]
0x1400ec874  mov     r8, rbx; unsigned __int64
0x1400ec877  mov     r9, [rsi+68h]; unsigned __int64
0x1400ec87b  mov     rdx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec87e  mov     rcx, r13; struct CVirtualAddressAllocator *
0x1400ec881  mov     qword ptr [rsp+0E8h+var_C8], rax; unsigned __int64
0x1400ec886  call    ?VidMmiLogEndVaRangeMapping@@YAXPEAVCVirtualAddressAllocator@@PEAUVIDMM_MAPPED_VA_RANGE@@_K22@Z; VidMmiLogEndVaRangeMapping(CVirtualAddressAllocator *,VIDMM_MAPPED_VA_RANGE *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1400ec88b  xor     ebp, ebp
0x1400ec88d  xor     r15d, r15d
0x1400ec890  mov     rcx, rdi; Entry
0x1400ec893  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1400ec898  jmp     loc_1400EC680
0x1400ec89d  mov     r10, [rdi+60h]
0x1400ec8a1  mov     rdx, r11
0x1400ec8a4  sub     rdx, r12; __int64
0x1400ec8a7  mov     rcx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1400ec8aa  call    ?VidMmiCalculateNewOwnerOffset@@YA_KPEAUVIDMM_MAPPED_VA_RANGE@@_J@Z; VidMmiCalculateNewOwnerOffset(VIDMM_MAPPED_VA_RANGE *,__int64)
0x1400ec8af  mov     ecx, [rdi+48h]
0x1400ec8b2  mov     edx, ecx
0x1400ec8b4  mov     r12, [rsp+0E8h+arg_8]
0x1400ec8bc  and     edx, 0Fh
0x1400ec8bf  mov     [rsp+0E8h+var_80], ecx
0x1400ec8c3  mov     r8, r12
0x1400ec8c6  mov     rcx, [rdi+78h]
0x1400ec8ca  mov     [rsp+0E8h+var_88], rcx
0x1400ec8cf  mov     rcx, [rdi+80h]
0x1400ec8d6  mov     [rsp+0E8h+var_90], rcx
0x1400ec8db  mov     rcx, [rdi+58h]
0x1400ec8df  mov     [rsp+0E8h+var_98], rcx
0x1400ec8e4  mov     rcx, r15
0x1400ec8e7  mov     [rsp+0E8h+var_A0], r10
0x1400ec8ec  mov     dword ptr [rsp+0E8h+var_A8], edx
0x1400ec8f0  mov     [rsp+0E8h+var_B0], rax
0x1400ec8f5  mov     rax, [rdi+40h]
0x1400ec8f9  mov     [rsp+0E8h+var_B8], rax
0x1400ec8fe  mov     eax, [rsp+0E8h+arg_10]
0x1400ec905  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1400ec909  mov     qword ptr [rsp+0E8h+var_C8], r9
0x1400ec90e  mov     r9, r11
0x1400ec911  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
  ... truncated ...
```
