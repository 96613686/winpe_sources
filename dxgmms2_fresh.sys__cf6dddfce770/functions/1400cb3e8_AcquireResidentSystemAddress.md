# AcquireResidentSystemAddress

- ea: `0x1400cb3e8`
- end: `0x1400cb708`
- name: `AcquireResidentSystemAddress`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cb710`

## callees

- `0x140004268`
- `0x14004c13c`
- `0x1400c115c`
- `0x1400cb3e8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cb5fe`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cb5fe`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400cb55c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400cb55c`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400cb67e`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400cb67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb65e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb65e`
- `watchdog!WdLogSingleEntry5` at `0x1400cb6b7`
- `watchdog!WdLogSingleEntry5` at `0x1400cb6f2`
- `watchdog!WdLogSingleEntry5` at `0x1400cb6b7`
- `watchdog!WdLogSingleEntry5` at `0x1400cb6f2`
- `watchdog!WdLogSingleEntry0` at `0x1400cb59a`
- `watchdog!WdLogSingleEntry0` at `0x1400cb61d`
- `watchdog!WdLogSingleEntry0` at `0x1400cb59a`
- `watchdog!WdLogSingleEntry0` at `0x1400cb61d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400cb68f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400cb6cd`

## string_xrefs

- `0x1400cb62e`: `Failed to create system space mapping for MDL`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
PVOID __fastcall AcquireResidentSystemAddress(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  __int64 v5; // r9
  __int64 v6; // r11
  PVOID result; // rax
  const struct PBMM_PHYSICAL_ALLOC *v8; // rcx
  unsigned __int64 AllocationSegmentOffset; // r8
  __int64 *v10; // r9
  __int64 v11; // r11
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r10
  int v16; // eax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdi
  _QWORD *v19; // rbx
  _QWORD *v20; // r10
  unsigned int v21; // r8d
  __int64 v22; // r10
  unsigned int v23; // r8d
  __int64 v24; // rcx
  struct _MDL *v25; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // ecx
  int v29; // r8d
  __int64 v30; // rcx
  unsigned int v31; // [rsp+88h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a2 + 64);
  v5 = a2;
  v6 = a1;
  if ( (v3 & 8) != 0 )
    return *(PVOID *)(*(_QWORD *)a2 + 224LL);
  if ( (v3 & 0x20) == 0 )
  {
LABEL_23:
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 88, v6, v5, a3);
    WdLogGlobalForLineNumber = 227;
    JUMPOUT(0x1400CB708LL);
  }
  v8 = *(const struct PBMM_PHYSICAL_ALLOC **)(a2 + 72);
  v31 = 0;
  AllocationSegmentOffset = PbmmGetAllocationSegmentOffset(v8, &v31);
  v12 = *(_QWORD *)(*(_QWORD *)(v11 + 2664) + 8LL * v31);
  v13 = *(_DWORD *)(v12 + 64);
  if ( (v13 & 0x2000) != 0 )
    return 0;
  if ( (v13 & 4) == 0 )
  {
    v30 = *v10;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 73, v11, v30, v12);
    WdLogGlobalForLineNumber = 227;
    goto LABEL_23;
  }
  v14 = *(_QWORD *)(v12 + 32);
  v15 = v14 + AllocationSegmentOffset;
  v16 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 56) + 24LL) + 444LL);
  if ( !*(_BYTE *)(a3 + 16) )
  {
    if ( (v16 & 8) == 0 )
      return (PVOID)MmMapIoSpaceEx(v15, v10[2], 1028);
    v25 = VidMmiBuildMdlFromMdl(v10[2], *(const struct _MDL **)(v12 + 32), AllocationSegmentOffset >> 12);
    *(_QWORD *)a3 = v25;
    if ( v25 )
    {
      v25->MdlFlags |= 0x802u;
      result = MmMapLockedPagesSpecifyCache(*(PMDL *)a3, 0, MmCached, 0, 0, 0x40000010u);
      if ( result )
        return result;
      _InterlockedIncrement(&dword_1400878A8);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3200;
      DxgkLogInternalTriageEvent(
        v28,
        262145,
        v29,
        (unsigned int)L"Failed to create system space mapping for MDL",
        3200,
        0,
        0,
        0);
      ExFreePoolWithTag(*(PVOID *)a3, 0);
      *(_QWORD *)a3 = 0;
    }
    else
    {
      _InterlockedIncrement(&dword_140087774);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3177;
      DxgkLogInternalTriageEvent(
        v26,
        262145,
        v27,
        (unsigned int)L"Failed to build SoftGPU MDL system address",
        3177,
        0,
        0,
        0);
    }
    return 0;
  }
  v17 = v10[2];
  v18 = v17 >> 12;
  v19 = (_QWORD *)(*(_QWORD *)(v11 + 2504) + 48LL);
  if ( (v16 & 8) != 0 )
  {
    v20 = (_QWORD *)(v14 + 48 + 8 * (AllocationSegmentOffset >> 12));
    v21 = 0;
    if ( v18 )
    {
      do
      {
        ++v21;
        *v19 = *v20++;
        v17 = v10[2];
        ++v19;
      }
      while ( v21 < v17 >> 12 );
    }
  }
  else
  {
    v22 = v15 >> 12;
    v23 = 0;
    if ( v18 )
    {
      do
      {
        ++v23;
        *v19 = v22++;
        v17 = v10[2];
        ++v19;
      }
      while ( v23 < v17 >> 12 );
    }
  }
  v24 = *(_QWORD *)(v11 + 2504);
  *(_DWORD *)(v24 + 40) = v17;
  *(_WORD *)(v24 + 8) = 8 * (((v17 + 4095) >> 12) + 6);
  *(_QWORD *)v24 = 0;
  *(_WORD *)(v24 + 10) = 0;
  *(_QWORD *)(v24 + 32) = 0;
  *(_DWORD *)(v24 + 44) = 0;
  *(_WORD *)(*(_QWORD *)(v11 + 2504) + 10LL) |= 0x802u;
  return MmMapLockedPagesWithReservedMapping(
           *(PVOID *)(v11 + 2496),
           0x6D4D6956u,
           *(PMDL *)(v11 + 2504),
           MmWriteCombined);
}

```

## disassembly

```asm
0x1400cb3e8  push    rbx
0x1400cb3ea  push    rbp
0x1400cb3eb  push    rsi
0x1400cb3ec  push    rdi
0x1400cb3ed  sub     rsp, 58h
0x1400cb3f1  mov     eax, [rdx+40h]
0x1400cb3f4  mov     rbx, r8
0x1400cb3f7  mov     r9, rdx
0x1400cb3fa  mov     r11, rcx
0x1400cb3fd  test    al, 8
0x1400cb3ff  jz      short loc_1400CB415
0x1400cb401  mov     rax, [rdx]
0x1400cb404  mov     rax, [rax+0E0h]
0x1400cb40b  add     rsp, 58h
0x1400cb40f  pop     rdi
0x1400cb410  pop     rsi
0x1400cb411  pop     rbp
0x1400cb412  pop     rbx
0x1400cb413  retn
0x1400cb415  test    al, 20h
0x1400cb417  jz      loc_1400CB6CD
0x1400cb41d  mov     rcx, [r9+48h]; struct PBMM_PHYSICAL_ALLOC *
0x1400cb421  lea     rdx, [rsp+78h+arg_8]; unsigned int *
0x1400cb429  xor     ebp, ebp
0x1400cb42b  mov     [rsp+78h+arg_8], ebp
0x1400cb432  call    ?PbmmGetAllocationSegmentOffset@@YA_KPEBUPBMM_PHYSICAL_ALLOC@@PEAI@Z; PbmmGetAllocationSegmentOffset(PBMM_PHYSICAL_ALLOC const *,uint *)
0x1400cb437  mov     ecx, [rsp+78h+arg_8]
0x1400cb43e  mov     r8, rax
0x1400cb441  mov     rax, [r11+0A68h]
0x1400cb448  mov     rdx, [rax+rcx*8]
0x1400cb44c  mov     eax, [rdx+40h]
0x1400cb44f  bt      eax, 0Dh
0x1400cb453  jb      loc_1400CB5D6
0x1400cb459  test    al, 4
0x1400cb45b  jz      loc_1400CB68F
0x1400cb461  mov     rax, [r11+38h]
0x1400cb465  mov     rcx, [rdx+20h]
0x1400cb469  mov     rsi, [rax+18h]
0x1400cb46d  lea     r10, [rcx+r8]
0x1400cb471  mov     eax, [rsi+1BCh]
0x1400cb477  cmp     [rbx+10h], bpl
0x1400cb47b  jz      loc_1400CB56D
0x1400cb481  mov     rdx, [r9+10h]
0x1400cb485  mov     rbx, [r11+9C8h]
0x1400cb48c  mov     rdi, rdx
0x1400cb48f  shr     rdi, 0Ch
0x1400cb493  add     rbx, 30h ; '0'
0x1400cb497  test    al, 8
0x1400cb499  jz      short loc_1400CB4D5
0x1400cb49b  shr     r8, 0Ch
0x1400cb49f  lea     r10, [rcx+30h]
0x1400cb4a3  lea     r10, [r10+r8*8]
0x1400cb4a7  mov     r8d, ebp
0x1400cb4aa  test    rdi, rdi
0x1400cb4ad  jz      short loc_1400CB504
0x1400cb4af  mov     rax, [r10]
0x1400cb4b2  inc     r8d
0x1400cb4b5  mov     [rbx], rax
0x1400cb4b8  lea     r10, [r10+8]
0x1400cb4bc  mov     rdx, [r9+10h]
0x1400cb4c0  lea     rbx, [rbx+8]
0x1400cb4c4  mov     rcx, rdx
0x1400cb4c7  mov     eax, r8d
0x1400cb4ca  shr     rcx, 0Ch
0x1400cb4ce  cmp     rax, rcx
0x1400cb4d1  jb      short loc_1400CB4AF
0x1400cb4d3  jmp     short loc_1400CB504
0x1400cb4d5  sar     r10, 0Ch
0x1400cb4d9  mov     r8d, ebp
0x1400cb4dc  test    rdi, rdi
0x1400cb4df  jz      short loc_1400CB504
0x1400cb4e1  mov     rax, r10
0x1400cb4e4  inc     r8d
0x1400cb4e7  mov     [rbx], rax
0x1400cb4ea  inc     r10
0x1400cb4ed  mov     rdx, [r9+10h]
0x1400cb4f1  lea     rbx, [rbx+8]
0x1400cb4f5  mov     rcx, rdx
0x1400cb4f8  mov     eax, r8d
0x1400cb4fb  shr     rcx, 0Ch
0x1400cb4ff  cmp     rax, rcx
0x1400cb502  jb      short loc_1400CB4E1
0x1400cb504  mov     rcx, [r11+9C8h]
0x1400cb50b  lea     rax, [rdx+0FFFh]
0x1400cb512  shr     rax, 0Ch
0x1400cb516  mov     r9d, 2; CacheType
0x1400cb51c  add     ax, 6
0x1400cb520  shl     ax, 3
0x1400cb524  mov     [rcx+28h], edx
0x1400cb527  mov     edx, 6D4D6956h; PoolTag
0x1400cb52c  mov     [rcx+8], ax
0x1400cb530  mov     [rcx], rbp
0x1400cb533  mov     [rcx+0Ah], bp
0x1400cb537  mov     [rcx+20h], rbp
0x1400cb53b  mov     [rcx+2Ch], ebp
0x1400cb53e  mov     ecx, 802h
0x1400cb543  mov     rax, [r11+9C8h]
0x1400cb54a  or      [rax+0Ah], cx
0x1400cb54e  mov     r8, [r11+9C8h]; MemoryDescriptorList
0x1400cb555  mov     rcx, [r11+9C0h]; MappingAddress
0x1400cb55c  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400cb563  nop     dword ptr [rax+rax+00h]
0x1400cb568  jmp     loc_1400CB40B
0x1400cb56d  mov     r11, [r9+10h]
0x1400cb571  test    al, 8
0x1400cb573  jz      loc_1400CB672
0x1400cb579  mov     rdx, rcx; struct _MDL *
0x1400cb57c  shr     r8, 0Ch; unsigned __int64
0x1400cb580  mov     rcx, r11; Length
0x1400cb583  call    ?VidMmiBuildMdlFromMdl@@YAPEAU_MDL@@_KPEBU1@0@Z; VidMmiBuildMdlFromMdl(unsigned __int64,_MDL const *,unsigned __int64)
0x1400cb588  mov     [rbx], rax
0x1400cb58b  test    rax, rax
0x1400cb58e  jnz     short loc_1400CB5DD
0x1400cb590  lock inc cs:dword_140087774
0x1400cb597  lea     ecx, [rax+6]
0x1400cb59a  call    cs:__imp_WdLogSingleEntry0
0x1400cb5a1  nop     dword ptr [rax+rax+00h]
0x1400cb5a6  mov     [rsp+78h+var_40], rbp
0x1400cb5ab  lea     r9, aFailedToBuildS; "Failed to build SoftGPU MDL system addr"...
0x1400cb5b2  mov     eax, 0C69h
0x1400cb5b7  mov     [rsp+78h+var_48], rbp
0x1400cb5bc  mov     qword ptr [rsp+78h+Priority], rbp
0x1400cb5c1  mov     edx, 40001h
0x1400cb5c6  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cb5cc  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1400cb5d1  call    DxgkLogInternalTriageEvent
0x1400cb5d6  xor     eax, eax
0x1400cb5d8  jmp     loc_1400CB40B
0x1400cb5dd  xor     r9d, r9d; RequestedAddress
0x1400cb5e0  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400cb5e8  mov     ecx, 802h
0x1400cb5ed  mov     [rsp+78h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400cb5f1  or      [rax+0Ah], cx
0x1400cb5f5  xor     edx, edx; AccessMode
0x1400cb5f7  mov     rcx, [rbx]; MemoryDescriptorList
0x1400cb5fa  lea     r8d, [r9+1]; CacheType
0x1400cb5fe  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400cb605  nop     dword ptr [rax+rax+00h]
0x1400cb60a  test    rax, rax
0x1400cb60d  jnz     loc_1400CB40B
0x1400cb613  lock inc cs:dword_1400878A8
0x1400cb61a  lea     ecx, [rax+6]
0x1400cb61d  call    cs:__imp_WdLogSingleEntry0
0x1400cb624  nop     dword ptr [rax+rax+00h]
0x1400cb629  mov     [rsp+78h+var_40], rbp
0x1400cb62e  lea     r9, aFailedToCreate_0; "Failed to create system space mapping f"...
0x1400cb635  mov     eax, 0C80h
0x1400cb63a  mov     [rsp+78h+var_48], rbp
0x1400cb63f  mov     qword ptr [rsp+78h+Priority], rbp
0x1400cb644  mov     edx, 40001h
0x1400cb649  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cb64f  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1400cb654  call    DxgkLogInternalTriageEvent
0x1400cb659  mov     rcx, [rbx]; P
0x1400cb65c  xor     edx, edx; Tag
0x1400cb65e  call    cs:__imp_ExFreePoolWithTag
0x1400cb665  nop     dword ptr [rax+rax+00h]
0x1400cb66a  mov     [rbx], rbp
0x1400cb66d  jmp     loc_1400CB5D6
0x1400cb672  mov     r8d, 404h
0x1400cb678  mov     rdx, r11
0x1400cb67b  mov     rcx, r10
0x1400cb67e  call    cs:__imp_MmMapIoSpaceEx
0x1400cb685  nop     dword ptr [rax+rax+00h]
0x1400cb68a  jmp     loc_1400CB40B
0x1400cb68f  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400cb696  mov     rcx, [r9]
0x1400cb699  mov     dword ptr [rax], 1
0x1400cb69f  mov     qword ptr [rsp+78h+Priority], rdx
0x1400cb6a4  mov     r9, r11
0x1400cb6a7  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx
0x1400cb6ac  mov     edx, 10Eh
0x1400cb6b1  xor     ecx, ecx
0x1400cb6b3  lea     r8d, [rcx+49h]
0x1400cb6b7  call    cs:__imp_WdLogSingleEntry5
0x1400cb6be  nop     dword ptr [rax+rax+00h]
0x1400cb6c3  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400cb6cd  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400cb6d4  mov     dword ptr [rax], 1
0x1400cb6da  xor     ecx, ecx
0x1400cb6dc  mov     qword ptr [rsp+78h+Priority], rbx
0x1400cb6e1  mov     qword ptr [rsp+78h+BugCheckOnFailure], r9
0x1400cb6e6  mov     edx, 10Eh
0x1400cb6eb  mov     r9, r11
0x1400cb6ee  lea     r8d, [rcx+58h]
0x1400cb6f2  call    cs:__imp_WdLogSingleEntry5
0x1400cb6f9  nop     dword ptr [rax+rax+00h]
0x1400cb6fe  mov     cs:WdLogGlobalForLineNumber, 0E3h
```
