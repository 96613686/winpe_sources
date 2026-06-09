# AcquireResidentSystemAddress

- ea: `0x1400c5880`
- end: `0x1400c5ba0`
- name: `AcquireResidentSystemAddress`
- size: `800`
- prototype: `PVOID __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c5bb0`

## callees

- `0x1400045ec`
- `0x14004ba2c`
- `0x1400bd6ac`
- `0x1400c5880`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c5a96`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c5a96`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400c59f4`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400c59f4`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400c5b16`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400c5b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5af6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5af6`
- `watchdog!WdLogSingleEntry5` at `0x1400c5b4f`
- `watchdog!WdLogSingleEntry5` at `0x1400c5b8a`
- `watchdog!WdLogSingleEntry5` at `0x1400c5b4f`
- `watchdog!WdLogSingleEntry5` at `0x1400c5b8a`
- `watchdog!WdLogSingleEntry0` at `0x1400c5a32`
- `watchdog!WdLogSingleEntry0` at `0x1400c5ab5`
- `watchdog!WdLogSingleEntry0` at `0x1400c5a32`
- `watchdog!WdLogSingleEntry0` at `0x1400c5ab5`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400c5b27`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400c5b65`

## string_xrefs

- `0x1400c5ac6`: `Failed to create system space mapping for MDL`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
PVOID __fastcall AcquireResidentSystemAddress(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  PVOID result; // rax
  const struct PBMM_PHYSICAL_ALLOC *v6; // rcx
  unsigned __int64 AllocationSegmentOffset; // r8
  __int64 v8; // r9
  __int64 v9; // r11
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r10
  int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  _QWORD *v17; // rbx
  _QWORD *v18; // r10
  unsigned int v19; // r8d
  __int64 v20; // r10
  unsigned int v21; // r8d
  __int64 v22; // rcx
  struct _MDL *v23; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // ecx
  int v27; // r8d
  unsigned int v28; // [rsp+88h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a2 + 64);
  if ( (v3 & 8) != 0 )
    return *(PVOID *)(*(_QWORD *)a2 + 224LL);
  if ( (v3 & 0x20) == 0 )
  {
LABEL_23:
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 88);
    WdLogGlobalForLineNumber = 222;
    JUMPOUT(0x1400C5BA0LL);
  }
  v6 = *(const struct PBMM_PHYSICAL_ALLOC **)(a2 + 72);
  v28 = 0;
  AllocationSegmentOffset = PbmmGetAllocationSegmentOffset(v6, &v28);
  v10 = *(_QWORD *)(*(_QWORD *)(v9 + 2400) + 8LL * v28);
  v11 = *(_DWORD *)(v10 + 64);
  if ( (v11 & 0x2000) != 0 )
    return 0;
  if ( (v11 & 4) == 0 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 73);
    WdLogGlobalForLineNumber = 222;
    goto LABEL_23;
  }
  v12 = *(_QWORD *)(v10 + 32);
  v13 = v12 + AllocationSegmentOffset;
  v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 56) + 24LL) + 444LL);
  if ( !*(_BYTE *)(a3 + 16) )
  {
    if ( (v14 & 8) == 0 )
      return (PVOID)MmMapIoSpaceEx(v13, *(_QWORD *)(v8 + 16), 1028);
    v23 = VidMmiBuildMdlFromMdl(*(_QWORD *)(v8 + 16), *(const struct _MDL **)(v10 + 32), AllocationSegmentOffset >> 12);
    *(_QWORD *)a3 = v23;
    if ( v23 )
    {
      v23->MdlFlags |= 0x802u;
      result = MmMapLockedPagesSpecifyCache(*(PMDL *)a3, 0, MmCached, 0, 0, 0x40000010u);
      if ( result )
        return result;
      _InterlockedIncrement(&dword_1400868C8);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3200;
      DxgkLogInternalTriageEvent(
        v26,
        262145,
        v27,
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
      _InterlockedIncrement(&dword_140086794);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3177;
      DxgkLogInternalTriageEvent(
        v24,
        262145,
        v25,
        (unsigned int)L"Failed to build SoftGPU MDL system address",
        3177,
        0,
        0,
        0);
    }
    return 0;
  }
  v15 = *(_QWORD *)(v8 + 16);
  v16 = v15 >> 12;
  v17 = (_QWORD *)(*(_QWORD *)(v9 + 2240) + 48LL);
  if ( (v14 & 8) != 0 )
  {
    v18 = (_QWORD *)(v12 + 48 + 8 * (AllocationSegmentOffset >> 12));
    v19 = 0;
    if ( v16 )
    {
      do
      {
        ++v19;
        *v17 = *v18++;
        v15 = *(_QWORD *)(v8 + 16);
        ++v17;
      }
      while ( v19 < v15 >> 12 );
    }
  }
  else
  {
    v20 = v13 >> 12;
    v21 = 0;
    if ( v16 )
    {
      do
      {
        ++v21;
        *v17 = v20++;
        v15 = *(_QWORD *)(v8 + 16);
        ++v17;
      }
      while ( v21 < v15 >> 12 );
    }
  }
  v22 = *(_QWORD *)(v9 + 2240);
  *(_DWORD *)(v22 + 40) = v15;
  *(_WORD *)(v22 + 8) = 8 * (((v15 + 4095) >> 12) + 6);
  *(_QWORD *)v22 = 0;
  *(_WORD *)(v22 + 10) = 0;
  *(_QWORD *)(v22 + 32) = 0;
  *(_DWORD *)(v22 + 44) = 0;
  *(_WORD *)(*(_QWORD *)(v9 + 2240) + 10LL) |= 0x802u;
  return MmMapLockedPagesWithReservedMapping(*(PVOID *)(v9 + 2232), 0x6D4D6956u, *(PMDL *)(v9 + 2240), MmWriteCombined);
}

```

## disassembly

```asm
0x1400c5880  push    rbx
0x1400c5882  push    rbp
0x1400c5883  push    rsi
0x1400c5884  push    rdi
0x1400c5885  sub     rsp, 58h
0x1400c5889  mov     eax, [rdx+40h]
0x1400c588c  mov     rbx, r8
0x1400c588f  mov     r9, rdx
0x1400c5892  mov     r11, rcx
0x1400c5895  test    al, 8
0x1400c5897  jz      short loc_1400C58AD
0x1400c5899  mov     rax, [rdx]
0x1400c589c  mov     rax, [rax+0E0h]
0x1400c58a3  add     rsp, 58h
0x1400c58a7  pop     rdi
0x1400c58a8  pop     rsi
0x1400c58a9  pop     rbp
0x1400c58aa  pop     rbx
0x1400c58ab  retn
0x1400c58ad  test    al, 20h
0x1400c58af  jz      loc_1400C5B65
0x1400c58b5  mov     rcx, [r9+48h]; struct PBMM_PHYSICAL_ALLOC *
0x1400c58b9  lea     rdx, [rsp+78h+arg_8]; unsigned int *
0x1400c58c1  xor     ebp, ebp
0x1400c58c3  mov     [rsp+78h+arg_8], ebp
0x1400c58ca  call    ?PbmmGetAllocationSegmentOffset@@YA_KPEBUPBMM_PHYSICAL_ALLOC@@PEAI@Z; PbmmGetAllocationSegmentOffset(PBMM_PHYSICAL_ALLOC const *,uint *)
0x1400c58cf  mov     ecx, [rsp+78h+arg_8]
0x1400c58d6  mov     r8, rax
0x1400c58d9  mov     rax, [r11+960h]
0x1400c58e0  mov     rdx, [rax+rcx*8]
0x1400c58e4  mov     eax, [rdx+40h]
0x1400c58e7  bt      eax, 0Dh
0x1400c58eb  jb      loc_1400C5A6E
0x1400c58f1  test    al, 4
0x1400c58f3  jz      loc_1400C5B27
0x1400c58f9  mov     rax, [r11+38h]
0x1400c58fd  mov     rcx, [rdx+20h]
0x1400c5901  mov     rsi, [rax+18h]
0x1400c5905  lea     r10, [rcx+r8]
0x1400c5909  mov     eax, [rsi+1BCh]
0x1400c590f  cmp     [rbx+10h], bpl
0x1400c5913  jz      loc_1400C5A05
0x1400c5919  mov     rdx, [r9+10h]
0x1400c591d  mov     rbx, [r11+8C0h]
0x1400c5924  mov     rdi, rdx
0x1400c5927  shr     rdi, 0Ch
0x1400c592b  add     rbx, 30h ; '0'
0x1400c592f  test    al, 8
0x1400c5931  jz      short loc_1400C596D
0x1400c5933  shr     r8, 0Ch
0x1400c5937  lea     r10, [rcx+30h]
0x1400c593b  lea     r10, [r10+r8*8]
0x1400c593f  mov     r8d, ebp
0x1400c5942  test    rdi, rdi
0x1400c5945  jz      short loc_1400C599C
0x1400c5947  mov     rax, [r10]
0x1400c594a  inc     r8d
0x1400c594d  mov     [rbx], rax
0x1400c5950  lea     r10, [r10+8]
0x1400c5954  mov     rdx, [r9+10h]
0x1400c5958  lea     rbx, [rbx+8]
0x1400c595c  mov     rcx, rdx
0x1400c595f  mov     eax, r8d
0x1400c5962  shr     rcx, 0Ch
0x1400c5966  cmp     rax, rcx
0x1400c5969  jb      short loc_1400C5947
0x1400c596b  jmp     short loc_1400C599C
0x1400c596d  sar     r10, 0Ch
0x1400c5971  mov     r8d, ebp
0x1400c5974  test    rdi, rdi
0x1400c5977  jz      short loc_1400C599C
0x1400c5979  mov     rax, r10
0x1400c597c  inc     r8d
0x1400c597f  mov     [rbx], rax
0x1400c5982  inc     r10
0x1400c5985  mov     rdx, [r9+10h]
0x1400c5989  lea     rbx, [rbx+8]
0x1400c598d  mov     rcx, rdx
0x1400c5990  mov     eax, r8d
0x1400c5993  shr     rcx, 0Ch
0x1400c5997  cmp     rax, rcx
0x1400c599a  jb      short loc_1400C5979
0x1400c599c  mov     rcx, [r11+8C0h]
0x1400c59a3  lea     rax, [rdx+0FFFh]
0x1400c59aa  shr     rax, 0Ch
0x1400c59ae  mov     r9d, 2; CacheType
0x1400c59b4  add     ax, 6
0x1400c59b8  shl     ax, 3
0x1400c59bc  mov     [rcx+28h], edx
0x1400c59bf  mov     edx, 6D4D6956h; PoolTag
0x1400c59c4  mov     [rcx+8], ax
0x1400c59c8  mov     [rcx], rbp
0x1400c59cb  mov     [rcx+0Ah], bp
0x1400c59cf  mov     [rcx+20h], rbp
0x1400c59d3  mov     [rcx+2Ch], ebp
0x1400c59d6  mov     ecx, 802h
0x1400c59db  mov     rax, [r11+8C0h]
0x1400c59e2  or      [rax+0Ah], cx
0x1400c59e6  mov     r8, [r11+8C0h]; MemoryDescriptorList
0x1400c59ed  mov     rcx, [r11+8B8h]; MappingAddress
0x1400c59f4  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400c59fb  nop     dword ptr [rax+rax+00h]
0x1400c5a00  jmp     loc_1400C58A3
0x1400c5a05  mov     r11, [r9+10h]
0x1400c5a09  test    al, 8
0x1400c5a0b  jz      loc_1400C5B0A
0x1400c5a11  mov     rdx, rcx; struct _MDL *
0x1400c5a14  shr     r8, 0Ch; unsigned __int64
0x1400c5a18  mov     rcx, r11; Length
0x1400c5a1b  call    ?VidMmiBuildMdlFromMdl@@YAPEAU_MDL@@_KPEBU1@0@Z; VidMmiBuildMdlFromMdl(unsigned __int64,_MDL const *,unsigned __int64)
0x1400c5a20  mov     [rbx], rax
0x1400c5a23  test    rax, rax
0x1400c5a26  jnz     short loc_1400C5A75
0x1400c5a28  lock inc cs:dword_140086794
0x1400c5a2f  lea     ecx, [rax+6]
0x1400c5a32  call    cs:__imp_WdLogSingleEntry0
0x1400c5a39  nop     dword ptr [rax+rax+00h]
0x1400c5a3e  mov     [rsp+78h+var_40], rbp
0x1400c5a43  lea     r9, aFailedToBuildS; "Failed to build SoftGPU MDL system addr"...
0x1400c5a4a  mov     eax, 0C69h
0x1400c5a4f  mov     [rsp+78h+var_48], rbp
0x1400c5a54  mov     qword ptr [rsp+78h+Priority], rbp
0x1400c5a59  mov     edx, 40001h
0x1400c5a5e  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c5a64  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1400c5a69  call    DxgkLogInternalTriageEvent
0x1400c5a6e  xor     eax, eax
0x1400c5a70  jmp     loc_1400C58A3
0x1400c5a75  xor     r9d, r9d; RequestedAddress
0x1400c5a78  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400c5a80  mov     ecx, 802h
0x1400c5a85  mov     [rsp+78h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400c5a89  or      [rax+0Ah], cx
0x1400c5a8d  xor     edx, edx; AccessMode
0x1400c5a8f  mov     rcx, [rbx]; MemoryDescriptorList
0x1400c5a92  lea     r8d, [r9+1]; CacheType
0x1400c5a96  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400c5a9d  nop     dword ptr [rax+rax+00h]
0x1400c5aa2  test    rax, rax
0x1400c5aa5  jnz     loc_1400C58A3
0x1400c5aab  lock inc cs:dword_1400868C8
0x1400c5ab2  lea     ecx, [rax+6]
0x1400c5ab5  call    cs:__imp_WdLogSingleEntry0
0x1400c5abc  nop     dword ptr [rax+rax+00h]
0x1400c5ac1  mov     [rsp+78h+var_40], rbp
0x1400c5ac6  lea     r9, aFailedToCreate_0; "Failed to create system space mapping f"...
0x1400c5acd  mov     eax, 0C80h
0x1400c5ad2  mov     [rsp+78h+var_48], rbp
0x1400c5ad7  mov     qword ptr [rsp+78h+Priority], rbp
0x1400c5adc  mov     edx, 40001h
0x1400c5ae1  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c5ae7  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x1400c5aec  call    DxgkLogInternalTriageEvent
0x1400c5af1  mov     rcx, [rbx]; P
0x1400c5af4  xor     edx, edx; Tag
0x1400c5af6  call    cs:__imp_ExFreePoolWithTag
0x1400c5afd  nop     dword ptr [rax+rax+00h]
0x1400c5b02  mov     [rbx], rbp
0x1400c5b05  jmp     loc_1400C5A6E
0x1400c5b0a  mov     r8d, 404h
0x1400c5b10  mov     rdx, r11
0x1400c5b13  mov     rcx, r10
0x1400c5b16  call    cs:__imp_MmMapIoSpaceEx
0x1400c5b1d  nop     dword ptr [rax+rax+00h]
0x1400c5b22  jmp     loc_1400C58A3
0x1400c5b27  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400c5b2e  mov     rcx, [r9]
0x1400c5b31  mov     dword ptr [rax], 1
0x1400c5b37  mov     qword ptr [rsp+78h+Priority], rdx
0x1400c5b3c  mov     r9, r11
0x1400c5b3f  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx
0x1400c5b44  mov     edx, 10Eh
0x1400c5b49  xor     ecx, ecx
0x1400c5b4b  lea     r8d, [rcx+49h]
0x1400c5b4f  call    cs:__imp_WdLogSingleEntry5
0x1400c5b56  nop     dword ptr [rax+rax+00h]
0x1400c5b5b  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400c5b65  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400c5b6c  mov     dword ptr [rax], 1
0x1400c5b72  xor     ecx, ecx
0x1400c5b74  mov     qword ptr [rsp+78h+Priority], rbx
0x1400c5b79  mov     qword ptr [rsp+78h+BugCheckOnFailure], r9
0x1400c5b7e  mov     edx, 10Eh
0x1400c5b83  mov     r9, r11
0x1400c5b86  lea     r8d, [rcx+58h]
0x1400c5b8a  call    cs:__imp_WdLogSingleEntry5
0x1400c5b91  nop     dword ptr [rax+rax+00h]
0x1400c5b96  mov     cs:WdLogGlobalForLineNumber, 0DEh
```
