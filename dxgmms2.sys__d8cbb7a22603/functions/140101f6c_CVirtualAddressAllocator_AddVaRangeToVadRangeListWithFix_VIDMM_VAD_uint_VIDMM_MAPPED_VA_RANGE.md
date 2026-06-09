# CVirtualAddressAllocator::AddVaRangeToVadRangeListWithFix(VIDMM_VAD *,uint,VIDMM_MAPPED_VA_RANGE *)

- ea: `0x140101f6c`
- end: `0x1401026ea`
- name: `?AddVaRangeToVadRangeListWithFix@CVirtualAddressAllocator@@QEAAJPEAUVIDMM_VAD@@IPEAUVIDMM_MAPPED_VA_RANGE@@@Z`
- size: `1918`
- prototype: `__int64 __fastcall(CVirtualAddressAllocator *__hidden this, struct VIDMM_VAD *, unsigned int, struct VIDMM_MAPPED_VA_RANGE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140101e04`

## callees

- `0x140004268`
- `0x14002bc54`
- `0x14002eebc`
- `0x14002f580`
- `0x14002f6a8`
- `0x140033e20`
- `0x140101b98`
- `0x140101e1c`
- `0x140101f6c`
- `0x1401026f0`
- `0x140102710`
- `0x140102880`
- `0x1401028b0`
- `0x140102950`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140102073`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140102089`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140102073`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140102089`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140102110`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010225a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140102110`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14010225a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140102177`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140102177`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010218c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010218c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140102233`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401026cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140102233`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401026cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010223f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401026d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010223f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401026d9`
- `watchdog!WdLogSingleEntry2` at `0x1401020b3`
- `watchdog!WdLogSingleEntry2` at `0x1401020b3`

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
    _InterlockedIncrement(&dword_1400877D0);
    WdLogSingleEntry2(6, v16, v17);
    WdLogGlobalForLineNumber = 12196;
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
  if ( byte_140087202 < 0 )
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
0x140101f6c  mov     [rsp+arg_10], r8d
0x140101f71  mov     [rsp+arg_8], rdx
0x140101f76  push    rbx
0x140101f77  push    rbp
0x140101f78  push    rsi
0x140101f79  push    rdi
0x140101f7a  push    r12
0x140101f7c  push    r13
0x140101f7e  push    r14
0x140101f80  push    r15
0x140101f82  sub     rsp, 0A8h
0x140101f89  mov     r13, rcx
0x140101f8c  mov     edi, r8d
0x140101f8f  mov     ecx, [r9+48h]
0x140101f93  mov     r12, rdx
0x140101f96  mov     rdx, [r9+40h]
0x140101f9a  and     ecx, 0Fh
0x140101f9d  mov     rsi, r9
0x140101fa0  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x140101fa5  mov     rbx, rax
0x140101fa8  mov     [rsp+0E8h+var_60], rax
0x140101fb0  lea     rax, [r13+40h]
0x140101fb4  mov     [rsp+0E8h+arg_18], 0
0x140101fbc  mov     rdx, [rax+8]
0x140101fc0  mov     rcx, gs:188h
0x140101fc9  mov     [rsp+0E8h+var_58], rax
0x140101fd1  cmp     rdx, rcx
0x140101fd4  jz      short loc_140101FE6
0x140101fd6  mov     rcx, rax; this
0x140101fd9  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x140101fde  mov     [rsp+0E8h+arg_18], 1
0x140101fe6  mov     [rsp+0E8h+arg_0], 0
0x140101fee  test    rbx, rbx
0x140101ff1  jnz     loc_14010215E
0x140101ff7  lea     rax, [rdi+4]
0x140101ffb  lea     rax, [rax+rax*2]
0x140101fff  lea     rax, [r12+rax*8]
0x140102003  xor     r12d, r12d
0x140102006  mov     rdi, [rax]
0x140102009  mov     ebx, r12d
0x14010200c  mov     [rsp+0E8h+var_70], rax
0x140102011  test    rdi, rdi
0x140102014  jz      short loc_14010206C
0x140102016  mov     rdx, rdi
0x140102019  lea     rcx, [rsi+68h]
0x14010201d  call    CompareVaRangeAddressWithin
0x140102022  test    eax, eax
0x140102024  jz      short loc_140102034
0x140102026  jns     loc_140102155
0x14010202c  mov     rbx, rdi
0x14010202f  mov     rdi, [rdi]
0x140102032  jmp     short loc_140102011
0x140102034  mov     rbx, rdi
0x140102037  mov     rbp, r12
0x14010203a  mov     rdi, [rdi]
0x14010203d  test    rdi, rdi
0x140102040  jz      short loc_14010206C
0x140102042  mov     rdx, rdi
0x140102045  lea     rcx, [rsi+68h]
0x140102049  call    CompareVaRangeAddressWithin
0x14010204e  test    eax, eax
0x140102050  js      loc_14010214D
0x140102056  jle     loc_14010214A
0x14010205c  mov     rdi, [rdi+8]
0x140102060  test    rdi, rdi
0x140102063  jnz     short loc_140102042
0x140102065  test    rbp, rbp
0x140102068  cmovnz  rbx, rbp
0x14010206c  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140102073  call    cs:__imp_ExAllocateFromLookasideListEx
0x14010207a  nop     dword ptr [rax+rax+00h]
0x14010207f  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140102086  mov     rbp, rax
0x140102089  call    cs:__imp_ExAllocateFromLookasideListEx
0x140102090  nop     dword ptr [rax+rax+00h]
0x140102095  mov     r15, rax
0x140102098  test    rbp, rbp
0x14010209b  jnz     loc_1401021B5
0x1401020a1  lock inc cs:dword_1400877D0
0x1401020a8  mov     r8, r15
0x1401020ab  mov     rdx, rbp
0x1401020ae  mov     ecx, 6
0x1401020b3  call    cs:__imp_WdLogSingleEntry2
0x1401020ba  nop     dword ptr [rax+rax+00h]
0x1401020bf  mov     [rsp+0E8h+var_B0], r12
0x1401020c4  lea     r9, aFailedToAlloca_34; "Failed to allocate memory needed for VA"...
0x1401020cb  mov     [rsp+0E8h+var_B8], r12
0x1401020d0  mov     edx, 40001h
0x1401020d5  mov     [rsp+0E8h+var_C0], r15
0x1401020da  mov     qword ptr [rsp+0E8h+var_C8], rbp
0x1401020df  mov     cs:WdLogGlobalForLineNumber, 2FA4h
0x1401020e9  call    DxgkLogInternalTriageEvent
0x1401020ee  mov     edi, 0C0000017h
0x1401020f3  cmp     [rsp+0E8h+arg_0], r12b
0x1401020fb  jnz     loc_14010221B
0x140102101  test    rbp, rbp
0x140102104  jz      short loc_14010211C
0x140102106  mov     rdx, rbp; Entry
0x140102109  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140102110  call    cs:__imp_ExFreeToLookasideListEx
0x140102117  nop     dword ptr [rax+rax+00h]
0x14010211c  test    r15, r15
0x14010211f  jnz     loc_140102250
0x140102125  cmp     [rsp+0E8h+arg_18], r12b
0x14010212d  jnz     loc_1401026BF
0x140102133  mov     eax, edi
0x140102135  add     rsp, 0A8h
0x14010213c  pop     r15
0x14010213e  pop     r14
0x140102140  pop     r13
0x140102142  pop     r12
0x140102144  pop     rdi
0x140102145  pop     rsi
0x140102146  pop     rbp
0x140102147  pop     rbx
0x140102148  retn
0x14010214a  mov     rbp, rdi
0x14010214d  mov     rdi, [rdi]
0x140102150  jmp     loc_140102060
0x140102155  mov     rdi, [rdi+8]
0x140102159  jmp     loc_140102011
0x14010215e  mov     rcx, [rbx+0C8h]
0x140102165  mov     rax, gs:188h
0x14010216e  cmp     rcx, rax
0x140102171  jz      loc_140101FF7
0x140102177  call    cs:__imp_KeEnterCriticalRegion
0x14010217e  nop     dword ptr [rax+rax+00h]
0x140102183  xor     edx, edx
0x140102185  lea     rcx, [rbx+0C0h]
0x14010218c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140102193  nop     dword ptr [rax+rax+00h]
0x140102198  mov     rax, gs:188h
0x1401021a1  mov     [rbx+0C8h], rax
0x1401021a8  mov     [rsp+0E8h+arg_0], 1
0x1401021b0  jmp     loc_140101FF7
0x1401021b5  test    r15, r15
0x1401021b8  jz      loc_1401020A1
0x1401021be  mov     rcx, rsi
0x1401021c1  call    ValidateUniqueGpuVaMapping
0x1401021c6  test    al, al
0x1401021c8  jz      loc_14010253A
0x1401021ce  test    dword ptr [rsi+48h], 8000h
0x1401021d5  jnz     loc_1401024B9
0x1401021db  lea     r14, [rsi+70h]
0x1401021df  test    rbx, rbx
0x1401021e2  jnz     loc_14010226B
0x1401021e8  mov     r12, [rsp+0E8h+arg_8]
0x1401021f0  mov     r8, [rsp+0E8h+var_70]; struct _RTL_AVL_TREE *
0x1401021f5  mov     r9, rsi; struct VIDMM_MAPPED_VA_RANGE *
0x1401021f8  mov     rdx, r12; struct VIDMM_VAD *
0x1401021fb  mov     rcx, r13; this
0x1401021fe  call    ?AddVaRangeToVadWithFix@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_VAD@@PEAU_RTL_AVL_TREE@@PEAUVIDMM_MAPPED_VA_RANGE@@@Z; CVirtualAddressAllocator::AddVaRangeToVadWithFix(VIDMM_VAD *,_RTL_AVL_TREE *,VIDMM_MAPPED_VA_RANGE *)
0x140102203  xor     r12d, r12d
0x140102206  cmp     cs:byte_140087202, r12b
0x14010220d  jl      loc_14010264D
0x140102213  mov     edi, r12d
0x140102216  jmp     loc_1401020F3
0x14010221b  mov     rcx, [rsp+0E8h+var_60]
0x140102223  xor     edx, edx
0x140102225  mov     [rcx+0C8h], r12
0x14010222c  add     rcx, 0C0h
0x140102233  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14010223a  nop     dword ptr [rax+rax+00h]
0x14010223f  call    cs:__imp_KeLeaveCriticalRegion
0x140102246  nop     dword ptr [rax+rax+00h]
0x14010224b  jmp     loc_140102101
0x140102250  mov     rdx, r15; Entry
0x140102253  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14010225a  call    cs:__imp_ExFreeToLookasideListEx
0x140102261  nop     dword ptr [rax+rax+00h]
0x140102266  jmp     loc_140102125
0x14010226b  mov     rax, [rbx+8]
0x14010226f  lea     rdi, [rbx-8]
0x140102273  test    rax, rax
0x140102276  jnz     loc_140102510
0x14010227c  mov     rax, rbx
0x14010227f  mov     rbx, [rbx+10h]
0x140102283  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140102287  jz      short loc_14010228E
0x140102289  cmp     [rbx], rax
0x14010228c  jnz     short loc_14010227C
0x14010228e  mov     rax, [rdi+68h]
0x140102292  lea     r14, [rsi+70h]
0x140102296  cmp     [r14], rax
0x140102299  jbe     loc_1401021E8
0x14010229f  lock inc dword ptr [rdi+88h]
0x1401022a6  xor     r9d, r9d; bool
0x1401022a9  mov     [rsp+0E8h+var_C8], 1; bool
0x1401022ae  xor     r8d, r8d; bool
0x1401022b1  mov     rdx, rdi; Entry
0x1401022b4  mov     rcx, r13; this
0x1401022b7  call    ?RemoveVaRangeFromVad@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_MAPPED_VA_RANGE@@_N11@Z; CVirtualAddressAllocator::RemoveVaRangeFromVad(VIDMM_MAPPED_VA_RANGE *,bool,bool,bool)
0x1401022bc  mov     rdx, [rsi+68h]
0x1401022c0  mov     r12, [rdi+68h]
0x1401022c4  cmp     rdx, r12
0x1401022c7  ja      short loc_1401022FD
0x1401022c9  mov     r9, [rdi+70h]
0x1401022cd  mov     r11, [r14]
0x1401022d0  cmp     r11, r9
0x1401022d3  jb      loc_14010240D
0x1401022d9  mov     r8, [rdi+50h]; unsigned __int64
0x1401022dd  mov     rdx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1401022e0  mov     qword ptr [rsp+0E8h+var_C8], r9; unsigned __int64
0x1401022e5  mov     rcx, r13; struct CVirtualAddressAllocator *
0x1401022e8  mov     r9, r12; unsigned __int64
0x1401022eb  call    ?VidMmiLogEndVaRangeMapping@@YAXPEAVCVirtualAddressAllocator@@PEAUVIDMM_MAPPED_VA_RANGE@@_K22@Z; VidMmiLogEndVaRangeMapping(CVirtualAddressAllocator *,VIDMM_MAPPED_VA_RANGE *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1401022f0  mov     rcx, rdi; Entry
0x1401022f3  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x1401022f8  jmp     loc_1401021DF
0x1401022fd  mov     rax, [rdi+70h]
0x140102301  mov     [rsp+0E8h+var_68], rax
0x140102309  cmp     [r14], rax
0x14010230c  jnb     loc_140102544
0x140102312  test    rbp, rbp
0x140102315  jnz     loc_1401025DC
0x14010231b  mov     r8, [rsp+0E8h+var_70]; struct _RTL_AVL_TREE *
0x140102320  mov     r9, rbp; struct VIDMM_MAPPED_VA_RANGE *
0x140102323  mov     rdx, [rsp+0E8h+arg_8]; struct VIDMM_VAD *
0x14010232b  mov     rcx, r13; this
0x14010232e  call    ?AddVaRangeToVadWithFix@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_VAD@@PEAU_RTL_AVL_TREE@@PEAUVIDMM_MAPPED_VA_RANGE@@@Z; CVirtualAddressAllocator::AddVaRangeToVadWithFix(VIDMM_VAD *,_RTL_AVL_TREE *,VIDMM_MAPPED_VA_RANGE *)
0x140102333  mov     rdx, [rsi+68h]
0x140102337  mov     rcx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x14010233a  sub     rdx, r12; __int64
0x14010233d  call    ?VidMmiCalculateNewOwnerOffset@@YA_KPEAUVIDMM_MAPPED_VA_RANGE@@_J@Z; VidMmiCalculateNewOwnerOffset(VIDMM_MAPPED_VA_RANGE *,__int64)
0x140102342  mov     r11, [r14]
0x140102345  mov     rcx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x140102348  mov     r9d, [rdi+48h]
0x14010234c  mov     rdx, r11
0x14010234f  mov     r10d, r9d
0x140102352  sub     rdx, r12; __int64
0x140102355  mov     rbx, rax
0x140102358  and     r10d, 0Fh
0x14010235c  call    ?VidMmiCalculateNewOwnerOffset@@YA_KPEAUVIDMM_MAPPED_VA_RANGE@@_J@Z; VidMmiCalculateNewOwnerOffset(VIDMM_MAPPED_VA_RANGE *,__int64)
0x140102361  mov     rcx, [rdi+78h]
0x140102365  mov     r12, [rsp+0E8h+arg_8]
0x14010236d  mov     [rsp+0E8h+var_80], r9d
0x140102372  mov     r8, r12
0x140102375  mov     [rsp+0E8h+var_88], rcx
0x14010237a  mov     r9, r11
0x14010237d  mov     rcx, [rdi+80h]
0x140102384  mov     [rsp+0E8h+var_90], rcx
0x140102389  mov     rcx, [rdi+58h]
0x14010238d  mov     [rsp+0E8h+var_98], rcx
0x140102392  mov     rcx, [rdi+60h]
0x140102396  mov     [rsp+0E8h+var_A0], rcx
0x14010239b  mov     rcx, r15
0x14010239e  mov     dword ptr [rsp+0E8h+var_A8], r10d
0x1401023a3  mov     [rsp+0E8h+var_B0], rax
0x1401023a8  mov     rax, [rdi+40h]
0x1401023ac  mov     [rsp+0E8h+var_B8], rax
0x1401023b1  mov     eax, [rsp+0E8h+arg_10]
0x1401023b8  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1401023bc  mov     rax, [rsp+0E8h+var_68]
0x1401023c4  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1401023c9  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
0x1401023ce  mov     r8, [rsp+0E8h+var_70]; struct _RTL_AVL_TREE *
0x1401023d3  mov     rdx, r12; struct VIDMM_VAD *
0x1401023d6  mov     rcx, r13; this
0x1401023d9  mov     r9, r15; struct VIDMM_MAPPED_VA_RANGE *
0x1401023dc  call    ?AddVaRangeToVadWithFix@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_VAD@@PEAU_RTL_AVL_TREE@@PEAUVIDMM_MAPPED_VA_RANGE@@@Z; CVirtualAddressAllocator::AddVaRangeToVadWithFix(VIDMM_VAD *,_RTL_AVL_TREE *,VIDMM_MAPPED_VA_RANGE *)
0x1401023e1  mov     rax, [r14]
0x1401023e4  mov     r8, rbx; unsigned __int64
0x1401023e7  mov     r9, [rsi+68h]; unsigned __int64
0x1401023eb  mov     rdx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x1401023ee  mov     rcx, r13; struct CVirtualAddressAllocator *
0x1401023f1  mov     qword ptr [rsp+0E8h+var_C8], rax; unsigned __int64
0x1401023f6  call    ?VidMmiLogEndVaRangeMapping@@YAXPEAVCVirtualAddressAllocator@@PEAUVIDMM_MAPPED_VA_RANGE@@_K22@Z; VidMmiLogEndVaRangeMapping(CVirtualAddressAllocator *,VIDMM_MAPPED_VA_RANGE *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1401023fb  xor     ebp, ebp
0x1401023fd  xor     r15d, r15d
0x140102400  mov     rcx, rdi; Entry
0x140102403  call    ?ReleaseVaRangeReference@VIDMM_MAPPED_VA_RANGE@@QEAAJXZ; VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(void)
0x140102408  jmp     loc_1401021F0
0x14010240d  mov     r10, [rdi+60h]
0x140102411  mov     rdx, r11
0x140102414  sub     rdx, r12; __int64
0x140102417  mov     rcx, rdi; struct VIDMM_MAPPED_VA_RANGE *
0x14010241a  call    ?VidMmiCalculateNewOwnerOffset@@YA_KPEAUVIDMM_MAPPED_VA_RANGE@@_J@Z; VidMmiCalculateNewOwnerOffset(VIDMM_MAPPED_VA_RANGE *,__int64)
0x14010241f  mov     ecx, [rdi+48h]
0x140102422  mov     edx, ecx
0x140102424  mov     r12, [rsp+0E8h+arg_8]
0x14010242c  and     edx, 0Fh
0x14010242f  mov     [rsp+0E8h+var_80], ecx
0x140102433  mov     r8, r12
0x140102436  mov     rcx, [rdi+78h]
0x14010243a  mov     [rsp+0E8h+var_88], rcx
0x14010243f  mov     rcx, [rdi+80h]
0x140102446  mov     [rsp+0E8h+var_90], rcx
0x14010244b  mov     rcx, [rdi+58h]
0x14010244f  mov     [rsp+0E8h+var_98], rcx
0x140102454  mov     rcx, r15
0x140102457  mov     [rsp+0E8h+var_A0], r10
0x14010245c  mov     dword ptr [rsp+0E8h+var_A8], edx
0x140102460  mov     [rsp+0E8h+var_B0], rax
0x140102465  mov     rax, [rdi+40h]
0x140102469  mov     [rsp+0E8h+var_B8], rax
0x14010246e  mov     eax, [rsp+0E8h+arg_10]
0x140102475  mov     dword ptr [rsp+0E8h+var_C0], eax
0x140102479  mov     qword ptr [rsp+0E8h+var_C8], r9
0x14010247e  mov     r9, r11
0x140102481  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
  ... truncated ...
```
