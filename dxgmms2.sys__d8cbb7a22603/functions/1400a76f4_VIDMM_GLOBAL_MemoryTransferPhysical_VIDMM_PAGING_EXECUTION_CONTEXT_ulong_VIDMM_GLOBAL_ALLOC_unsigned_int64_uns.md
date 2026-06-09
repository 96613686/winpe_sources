# VIDMM_GLOBAL::MemoryTransferPhysical(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,VIDMM_TRANSFER_PARAMETER *,VIDMM_TRANSFER_PARAMETER *,_DXGK_TRANSFERFLAGS)

- ea: `0x1400a76f4`
- end: `0x1400a7c57`
- name: `?MemoryTransferPhysical@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@KPEAUVIDMM_GLOBAL_ALLOC@@_K2PEAUVIDMM_TRANSFER_PARAMETER@@3U_DXGK_TRANSFERFLAGS@@@Z`
- size: `1379`
- prototype: `void __usercall(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, unsigned int@<r8d>, struct VIDMM_GLOBAL_ALLOC *@<r9>, unsigned __int64, unsigned __int64, struct VIDMM_TRANSFER_PARAMETER *, struct VIDMM_TRANSFER_PARAMETER *, struct _DXGK_TRANSFERFLAGS)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a7528`

## callees

- `0x14002eb5c`
- `0x140038740`
- `0x1400393e8`
- `0x140059380`
- `0x140097b0c`
- `0x14009c1f4`
- `0x14009c364`
- `0x1400a76f4`
- `0x1400e7e20`
- `0x1400e94e0`
- `0x14010e82c`
- `0x1401113d8`
- `0x140114ee4`
- `0x140116694`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a7b82`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a7b82`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a7755`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a777f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a77bb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a7800`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a7755`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a777f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a77bb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a7800`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a7737`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a7765`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a77a1`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a77ea`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::MemoryTransferPhysical(
        VIDMM_GLOBAL *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        unsigned int a3,
        struct VIDMM_GLOBAL_ALLOC *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        LARGE_INTEGER *a7,
        LARGE_INTEGER *a8,
        DXGK_TRANSFERFLAGS a9)
{
  __int64 v12; // rcx
  LARGE_INTEGER *v13; // rsi
  LARGE_INTEGER *v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r13
  __int64 v19; // rcx
  _QWORD *v20; // rax
  LARGE_INTEGER v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r10
  __int64 v25; // r11
  bool v26; // zf
  UINT Value; // eax
  void *DriverAllocation; // rax
  unsigned int v29; // r10d
  unsigned int v30; // ebx
  LARGE_INTEGER v31; // rcx
  unsigned __int64 v32; // r8
  unsigned int v33; // r10d
  unsigned __int64 QuadPart; // r9
  const unsigned __int64 *v35; // rdx
  LARGE_INTEGER v36; // rcx
  unsigned __int64 v37; // r9
  const unsigned __int64 *v38; // rdx
  BOOL v39; // ecx
  LARGE_INTEGER v40; // rcx
  unsigned __int8 IsAllocationInUse; // al
  int v42; // r10d
  int v43; // ecx
  struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E v44; // eax
  ADAPTER_RENDER *v45; // rcx
  __int64 v46; // rcx
  LARGE_INTEGER v47; // rax
  LARGE_INTEGER v48; // rax
  unsigned int v49; // r13d
  __int64 v50; // rdi
  unsigned int CurrentProcessId; // eax
  int v52; // edx
  int v53; // r8d
  struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E v54; // edi
  bool v55; // sf
  D3DGPU_VIRTUAL_ADDRESS v56; // [rsp+58h] [rbp-B0h]
  __int64 v57; // [rsp+60h] [rbp-A8h]
  struct _DXGKARG_BUILDPAGINGBUFFER v58; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v59; // [rsp+1E8h] [rbp+E0h] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v60; // [rsp+1F0h] [rbp+E8h]
  unsigned int v61; // [rsp+1F8h] [rbp+F0h]

  v61 = a3;
  v60 = a2;
  memset(&v58, 0, sizeof(v58));
  v13 = a8;
  v14 = a7;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v12) + 24) = a4;
    WdLogGlobalForLineNumber = 15538;
    v16 = WdLogNewEntry5_WdTrace(v15);
    v17 = a5;
    v18 = a6;
    *(_QWORD *)(v16 + 24) = a5;
    *(_QWORD *)(v16 + 32) = v18;
    WdLogGlobalForLineNumber = 15541;
    v20 = (_QWORD *)WdLogNewEntry5_WdTrace(v19);
    v20[3] = v14[2].QuadPart;
    v20[4] = v14->QuadPart;
    v20[5] = v14[4].QuadPart;
    v21 = v14[3];
    v20[6] = v21.QuadPart;
    WdLogGlobalForLineNumber = 15543;
    v22 = (_QWORD *)((__int64 (__fastcall *)(_QWORD))WdLogNewEntry5_WdTrace)((LARGE_INTEGER)v21.QuadPart);
    v22[3] = v13[2].QuadPart;
    v22[4] = v13->QuadPart;
    v22[5] = v13[4].QuadPart;
    v22[6] = v13[3].QuadPart;
    WdLogGlobalForLineNumber = 15545;
  }
  else
  {
    v18 = a6;
    v17 = a5;
  }
  memset(&v58, 0, sizeof(v58));
  LOBYTE(v23) = *((_BYTE *)this + 37231) != 0;
  v58.hSystemContext = (HANDLE)VidSchGetDriverPagingContext(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v61, v23);
  v58.MultipassOffset = v25;
  if ( a2 )
    v57 = *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v24);
  else
    v57 = v25;
  v26 = (*((_BYTE *)this + 37225) & 0x20) == 0;
  Value = a9.Value;
  v58.Transfer.Flags = a9;
  if ( v26 && a4 )
  {
    if ( !v18 )
    {
      Value = a9.Value | 8;
      v58.Transfer.Flags.Value = a9.Value | 8;
    }
    if ( v17 + v18 == *(_QWORD *)(*(_QWORD *)a4 + 16LL) )
      v58.Transfer.Flags.Value = Value | 0x10;
  }
  DriverAllocation = VidMmGetDriverAllocation(a4);
  v30 = HIDWORD(a5);
  v56 = (D3DGPU_VIRTUAL_ADDRESS)DriverAllocation;
  do
  {
    VIDMM_GLOBAL::SetupForBuildPagingBufferIteration(this, v60, v29, a4, &v58);
    v26 = (*((_BYTE *)this + 37225) & 0x20) == 0;
    v31 = v14[2];
    v58.UpdateContextAllocation.ContextAllocation = v56;
    if ( v26 )
    {
      v58.Transfer.TransferSize = __PAIR64__(v30, v17);
      v58.Operation = DXGK_OPERATION_TRANSFER;
      v58.Transfer.TransferOffset = v18;
      v58.Transfer.MdlOffset = 0;
      if ( v31.QuadPart )
      {
        v58.Transfer.Source.SegmentId = *(unsigned __int16 *)(v31.QuadPart + 64);
        v58.Transfer.Source.SegmentAddress.QuadPart = v14->QuadPart + *(_QWORD *)(v31.QuadPart + 16);
        v58.Transfer.TransferOffset = v14[3].LowPart;
      }
      else
      {
        v58.Transfer.Source.SegmentAddress = v14[4];
        v58.Transfer.Source.SegmentId = 0;
      }
      v40 = v13[2];
      if ( v40.QuadPart )
      {
        v58.Transfer.Destination.SegmentId = *(unsigned __int16 *)(v40.QuadPart + 64);
        v58.Transfer.Destination.SegmentAddress.QuadPart = v13->QuadPart + *(_QWORD *)(v40.QuadPart + 16);
        v58.Transfer.TransferOffset = v13[3].LowPart;
      }
      else
      {
        v58.Transfer.Destination.SegmentAddress = v13[4];
        v58.Transfer.Destination.SegmentId = 0;
      }
      if ( a4 )
      {
        IsAllocationInUse = VIDMM_GLOBAL::IsAllocationInUse(this, a4);
        v43 = v42;
        LOBYTE(v43) = IsAllocationInUse == 0;
      }
      else
      {
        v43 = 1;
      }
      v58.Transfer.Flags.Value = v58.Transfer.Flags.Value & 0xFFFFFFFB | (4 * v43);
    }
    else
    {
      v58.Operation = DXGK_OPERATION_SIGNAL_MONITORED_FENCE|DXGK_OPERATION_SPECIAL_LOCK_TRANSFER;
      v32 = v17 >> 12;
      v33 = (unsigned int)v17 >> 12;
      v58.DiscardContent.SegmentId = v17 >> 12;
      v58.Fill.FillPattern = v18 >> 12;
      if ( v31.QuadPart )
      {
        v58.Transfer.TransferOffset = (unsigned __int64)v14[3].QuadPart >> 12;
        v58.Transfer.Source.SegmentId = *(unsigned __int16 *)(v31.QuadPart + 64);
        v58.UnmapApertureSegment.DummyPage.QuadPart = (unsigned __int64)(v14->QuadPart + *(_QWORD *)(v31.QuadPart + 16)) >> 12;
        v58.Transfer.Source.SegmentAddress.HighPart = 1;
        v58.Transfer.Source.SegmentAddress.LowPart = (unsigned int)v17 >> 12;
      }
      else
      {
        QuadPart = v14[1].QuadPart;
        v35 = (const unsigned __int64 *)v14[5].QuadPart;
        v58.Transfer.Source.SegmentId = 0;
        VidMmiInitializeAdlForPfnArray((struct _DXGK_ADL *)&v58.Reserved.Reserved[8], v35, v32, QuadPart);
        LODWORD(v32) = v58.DiscardContent.SegmentId;
      }
      v36 = v13[2];
      if ( v36.QuadPart )
      {
        v58.Transfer.TransferOffset = (unsigned __int64)v13[3].QuadPart >> 12;
        v58.Transfer.Destination.SegmentAddress.LowPart = *(unsigned __int16 *)(v36.QuadPart + 64);
        v58.UpdatePageTable.AllocationOffsetInBytes = (unsigned __int64)(v13->QuadPart + *(_QWORD *)(v36.QuadPart + 16)) >> 12;
        v58.TransferVirtual.DestinationPageTable = v33 | 0x100000000LL;
      }
      else
      {
        v37 = v13[1].QuadPart;
        v38 = (const unsigned __int64 *)v13[5].QuadPart;
        v58.Transfer.Destination.SegmentAddress.LowPart = 0;
        VidMmiInitializeAdlForPfnArray((struct _DXGK_ADL *)&v58.Reserved.Reserved[14], v38, v32, v37);
      }
      if ( a4 )
        v39 = VIDMM_GLOBAL::IsAllocationInUse(this, a4) == 0;
      else
        v39 = 1;
      v58.Reserved.Reserved[18] = v58.Reserved.Reserved[18] & 0xFFFFFFFB | (4 * v39);
    }
    v44 = (struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E)ADAPTER_RENDER::DdiBuildPagingBuffer(*((ADAPTER_RENDER **)this + 2), &v58);
    a9.0 = v44;
    if ( a4 && v44 == -1071775486 )
    {
      VIDMM_GLOBAL::WaitForAllPagingEngines(this, v60, a4);
      VIDMM_GLOBAL::VerifyAllocationIsIdle(this, a4);
      v45 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
      v58.Transfer.Flags.Value |= 4u;
      a9.0 = (struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E)ADAPTER_RENDER::DdiBuildPagingBuffer(v45, &v58);
    }
    v46 = *((_QWORD *)this + 390);
    if ( v46 )
    {
      v47 = v13[2];
      if ( !v47.QuadPart || *(_DWORD *)(v47.QuadPart + 100) != 1 )
        VIDMM_PROCESS::ChargeEvictionTransfer(
          *(VIDMM_PROCESS **)(v46 + 8),
          *(_DWORD *)(*((_QWORD *)this + 3) + 240LL),
          v17);
    }
    _InterlockedAdd64((volatile signed __int64 *)this + 501, v17);
    LOBYTE(v59) = byte_140087201 & 0x10;
    if ( (byte_140087201 & 0x10) != 0 )
    {
      v48 = v14[2];
      if ( !v48.QuadPart || (v49 = 2, *(_DWORD *)(v48.QuadPart + 100) != 1) )
        v49 = 1;
      v50 = *(_QWORD *)(v57 + 16);
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      McTemplateK0pppxxq_EtwWriteTransfer(a6, v52, v53, CurrentProcessId, (char)a4, v50, a6, a5, v49);
      VidMmRecordTransfer((VIDMM_GLOBAL *)((char *)this + 3296), a5, v49);
      v18 = a6;
    }
    v54 = a9.0;
    v59 = 0;
    VIDMM_GLOBAL::CompleteBuildPagingBufferIteration(this, v60, v61, a4, &v58, a9.Value, 0, &v59, 0);
    v29 = v61;
    v55 = *(int *)&v54 < 0;
    v17 = a5;
  }
  while ( v55 );
}

```

## disassembly

```asm
0x1400a76f4  mov     rax, rsp
0x1400a76f7  mov     [rax+20h], rbx
0x1400a76fb  mov     [rax+18h], r8d
0x1400a76ff  mov     [rax+10h], rdx
0x1400a7703  push    rbp
0x1400a7704  push    rsi
0x1400a7705  push    rdi
0x1400a7706  push    r12
0x1400a7708  push    r13
0x1400a770a  push    r14
0x1400a770c  push    r15
0x1400a770e  lea     rbp, [rax-0D8h]
0x1400a7715  sub     rsp, 1A0h
0x1400a771c  mov     rbx, rdx
0x1400a771f  mov     r14, rcx
0x1400a7722  xor     edx, edx; Val
0x1400a7724  lea     rcx, [rsp+1D0h+var_170]; void *
0x1400a7729  mov     r8d, 140h; Size
0x1400a772f  mov     r15, r9
0x1400a7732  call    memset
0x1400a7737  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a773e  mov     rsi, [rbp+0D0h+arg_38]
0x1400a7745  mov     r12, [rbp+0D0h+arg_30]
0x1400a774c  cmp     byte ptr [rax], 0
0x1400a774f  jz      loc_1400A7837
0x1400a7755  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a775c  nop     dword ptr [rax+rax+00h]
0x1400a7761  mov     [rax+18h], r15
0x1400a7765  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a776c  mov     cs:WdLogGlobalForLineNumber, 3CB2h
0x1400a7776  cmp     byte ptr [rax], 0
0x1400a7779  jz      loc_1400A7837
0x1400a777f  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a7786  nop     dword ptr [rax+rax+00h]
0x1400a778b  mov     rdi, [rbp+0D0h+arg_20]
0x1400a7792  mov     r13, [rbp+0D0h+arg_28]
0x1400a7799  mov     [rax+18h], rdi
0x1400a779d  mov     [rax+20h], r13
0x1400a77a1  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a77a8  mov     cs:WdLogGlobalForLineNumber, 3CB5h
0x1400a77b2  cmp     byte ptr [rax], 0
0x1400a77b5  jz      loc_1400A7845
0x1400a77bb  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a77c2  nop     dword ptr [rax+rax+00h]
0x1400a77c7  mov     rcx, [r12+10h]
0x1400a77cc  mov     [rax+18h], rcx
0x1400a77d0  mov     rcx, [r12]
0x1400a77d4  mov     [rax+20h], rcx
0x1400a77d8  mov     rcx, [r12+20h]
0x1400a77dd  mov     [rax+28h], rcx
0x1400a77e1  mov     rcx, [r12+18h]
0x1400a77e6  mov     [rax+30h], rcx
0x1400a77ea  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a77f1  mov     cs:WdLogGlobalForLineNumber, 3CB7h
0x1400a77fb  cmp     byte ptr [rax], 0
0x1400a77fe  jz      short loc_1400A7845
0x1400a7800  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a7807  nop     dword ptr [rax+rax+00h]
0x1400a780c  mov     rcx, [rsi+10h]
0x1400a7810  mov     [rax+18h], rcx
0x1400a7814  mov     rcx, [rsi]
0x1400a7817  mov     [rax+20h], rcx
0x1400a781b  mov     rcx, [rsi+20h]
0x1400a781f  mov     [rax+28h], rcx
0x1400a7823  mov     rcx, [rsi+18h]
0x1400a7827  mov     [rax+30h], rcx
0x1400a782b  mov     cs:WdLogGlobalForLineNumber, 3CB9h
0x1400a7835  jmp     short loc_1400A7845
0x1400a7837  mov     r13, [rbp+0D0h+arg_28]
0x1400a783e  mov     rdi, [rbp+0D0h+arg_20]
0x1400a7845  xor     edx, edx; Val
0x1400a7847  lea     rcx, [rsp+1D0h+var_170]; void *
0x1400a784c  mov     r8d, 140h; Size
0x1400a7852  call    memset
0x1400a7857  mov     rcx, [r14+10h]
0x1400a785b  xor     r11d, r11d
0x1400a785e  cmp     [r14+916Fh], r11b
0x1400a7865  mov     r10d, [rbp+0D0h+arg_10]
0x1400a786c  setnz   r8b
0x1400a7870  mov     edx, r10d
0x1400a7873  mov     rcx, [rcx+2E8h]
0x1400a787a  call    VidSchGetDriverPagingContext
0x1400a787f  mov     [rbp+0D0h+var_170.hSystemContext], rax
0x1400a7886  mov     [rbp+0D0h+var_170.MultipassOffset], r11d
0x1400a788a  test    rbx, rbx
0x1400a788d  jz      short loc_1400A789E
0x1400a788f  mov     rax, [rbx+18h]
0x1400a7893  mov     rdx, [rax+r10*8]
0x1400a7897  mov     [rsp+1D0h+var_178], rdx
0x1400a789c  jmp     short loc_1400A78A3
0x1400a789e  mov     [rsp+1D0h+var_178], r11
0x1400a78a3  test    byte ptr [r14+9169h], 20h
0x1400a78ab  mov     eax, dword ptr [rbp+0D0h+arg_40]
0x1400a78b1  mov     dword ptr [rbp+0D0h+var_170.28h+38h], eax
0x1400a78b4  jnz     short loc_1400A78D9
0x1400a78b6  test    r15, r15
0x1400a78b9  jz      short loc_1400A78D9
0x1400a78bb  test    r13, r13
0x1400a78be  jnz     short loc_1400A78C6
0x1400a78c0  or      eax, 8
0x1400a78c3  mov     dword ptr [rbp+0D0h+var_170.28h+38h], eax
0x1400a78c6  mov     rcx, [r15]
0x1400a78c9  lea     rdx, [rdi+r13]
0x1400a78cd  cmp     rdx, [rcx+10h]
0x1400a78d1  jnz     short loc_1400A78D9
0x1400a78d3  or      eax, 10h
0x1400a78d6  mov     dword ptr [rbp+0D0h+var_170.28h+38h], eax
0x1400a78d9  mov     rcx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a78dc  call    ?VidMmGetDriverAllocation@@YAPEAXPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetDriverAllocation(VIDMM_GLOBAL_ALLOC const *)
0x1400a78e1  mov     ebx, dword ptr [rbp+0D0h+arg_20+4]
0x1400a78e7  mov     [rsp+1D0h+var_180], rax
0x1400a78ec  mov     rdx, [rbp+0D0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a78f3  lea     rax, [rsp+1D0h+var_170]
0x1400a78f8  mov     r9, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a78fb  mov     [rsp+1D0h+var_1B0], rax; struct _DXGKARG_BUILDPAGINGBUFFER *
0x1400a7900  mov     r8d, r10d; unsigned int
0x1400a7903  mov     rcx, r14; this
0x1400a7906  call    ?SetupForBuildPagingBufferIteration@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@KPEBUVIDMM_GLOBAL_ALLOC@@PEAU_DXGKARG_BUILDPAGINGBUFFER@@@Z; VIDMM_GLOBAL::SetupForBuildPagingBufferIteration(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,VIDMM_GLOBAL_ALLOC const *,_DXGKARG_BUILDPAGINGBUFFER *)
0x1400a790b  test    byte ptr [r14+9169h], 20h
0x1400a7913  mov     rax, [rsp+1D0h+var_180]
0x1400a7918  mov     rcx, [r12+10h]
0x1400a791d  mov     qword ptr [rbp+0D0h+var_170.28h], rax
0x1400a7921  jz      loc_1400A7A1E
0x1400a7927  mov     r8, rdi
0x1400a792a  mov     [rsp+1D0h+var_170.Operation], 17h
0x1400a7932  shr     r8, 0Ch; unsigned int
0x1400a7936  mov     rax, r13
0x1400a7939  shr     rax, 0Ch
0x1400a793d  mov     r10d, edi
0x1400a7940  shr     r10d, 0Ch
0x1400a7944  mov     dword ptr [rbp+0D0h+var_170.28h+0Ch], r8d
0x1400a7948  mov     dword ptr [rbp+0D0h+var_170.28h+10h], eax
0x1400a794b  test    rcx, rcx
0x1400a794e  jz      short loc_1400A7980
0x1400a7950  mov     rax, [r12+18h]
0x1400a7955  shr     rax, 0Ch
0x1400a7959  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a795c  movzx   eax, word ptr [rcx+40h]
0x1400a7960  mov     dword ptr [rbp+0D0h+var_170.28h+18h], eax
0x1400a7963  mov     rdx, [rcx+10h]
0x1400a7967  add     rdx, [r12]
0x1400a796b  shr     rdx, 0Ch
0x1400a796f  mov     qword ptr [rbp+0D0h+var_170.28h+28h], rdx
0x1400a7973  mov     dword ptr [rbp+0D0h+var_170.28h+24h], 1
0x1400a797a  mov     dword ptr [rbp+0D0h+var_170.28h+20h], r10d
0x1400a797e  jmp     short loc_1400A799E
0x1400a7980  mov     r9, [r12+8]; unsigned __int64
0x1400a7985  lea     rcx, [rbp+0D0h+var_170.28h+20h]; struct _DXGK_ADL *
0x1400a7989  mov     rdx, [r12+28h]; unsigned __int64 *
0x1400a798e  mov     dword ptr [rbp+0D0h+var_170.28h+18h], 0
0x1400a7995  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x1400a799a  mov     r8d, dword ptr [rbp+0D0h+var_170.28h+0Ch]; unsigned int
0x1400a799e  mov     rcx, [rsi+10h]
0x1400a79a2  test    rcx, rcx
0x1400a79a5  jz      short loc_1400A79D5
0x1400a79a7  mov     rax, [rsi+18h]
0x1400a79ab  shr     rax, 0Ch
0x1400a79af  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a79b2  movzx   eax, word ptr [rcx+40h]
0x1400a79b6  mov     dword ptr [rbp+0D0h+var_170.28h+30h], eax
0x1400a79b9  mov     rdx, [rcx+10h]
0x1400a79bd  add     rdx, [rsi]
0x1400a79c0  shr     rdx, 0Ch
0x1400a79c4  mov     qword ptr [rbp+0D0h+var_170.28h+40h], rdx
0x1400a79c8  mov     dword ptr [rbp+0D0h+var_170.28h+3Ch], 1
0x1400a79cf  mov     dword ptr [rbp+0D0h+var_170.28h+38h], r10d
0x1400a79d3  jmp     short loc_1400A79ED
0x1400a79d5  mov     r9, [rsi+8]; unsigned __int64
0x1400a79d9  lea     rcx, [rbp+0D0h+var_170.28h+38h]; struct _DXGK_ADL *
0x1400a79dd  mov     rdx, [rsi+28h]; unsigned __int64 *
0x1400a79e1  mov     dword ptr [rbp+0D0h+var_170.28h+30h], 0
0x1400a79e8  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x1400a79ed  test    r15, r15
0x1400a79f0  jz      short loc_1400A7A06
0x1400a79f2  mov     rdx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a79f5  mov     rcx, r14; this
0x1400a79f8  call    ?IsAllocationInUse@VIDMM_GLOBAL@@QEBAEPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::IsAllocationInUse(VIDMM_GLOBAL_ALLOC *)
0x1400a79fd  xor     ecx, ecx
0x1400a79ff  test    al, al
0x1400a7a01  setz    cl
0x1400a7a04  jmp     short loc_1400A7A0B
0x1400a7a06  mov     ecx, 1
0x1400a7a0b  mov     eax, dword ptr [rbp+0D0h+var_170.28h+48h]
0x1400a7a0e  and     eax, 0FFFFFFFBh
0x1400a7a11  shl     ecx, 2
0x1400a7a14  or      ecx, eax
0x1400a7a16  mov     dword ptr [rbp+0D0h+var_170.28h+48h], ecx
0x1400a7a19  jmp     loc_1400A7ABF
0x1400a7a1e  xor     r10d, r10d
0x1400a7a21  mov     dword ptr [rbp+0D0h+var_170.28h+10h], edi
0x1400a7a24  mov     [rsp+1D0h+var_170.Operation], r10d
0x1400a7a29  mov     dword ptr [rbp+0D0h+var_170.28h+14h], ebx
0x1400a7a2c  mov     dword ptr [rbp+0D0h+var_170.28h+8], r13d
0x1400a7a30  mov     dword ptr [rbp+0D0h+var_170.28h+3Ch], r10d
0x1400a7a34  test    rcx, rcx
0x1400a7a37  jz      short loc_1400A7A56
0x1400a7a39  movzx   eax, word ptr [rcx+40h]
0x1400a7a3d  mov     dword ptr [rbp+0D0h+var_170.28h+18h], eax
0x1400a7a40  mov     rax, [rcx+10h]
0x1400a7a44  add     rax, [r12]
0x1400a7a48  mov     qword ptr [rbp+0D0h+var_170.28h+20h], rax
0x1400a7a4c  mov     eax, [r12+18h]
0x1400a7a51  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a7a54  jmp     short loc_1400A7A63
0x1400a7a56  mov     rax, [r12+20h]
0x1400a7a5b  mov     qword ptr [rbp+0D0h+var_170.28h+20h], rax
0x1400a7a5f  mov     dword ptr [rbp+0D0h+var_170.28h+18h], r10d
0x1400a7a63  mov     rcx, [rsi+10h]
0x1400a7a67  test    rcx, rcx
0x1400a7a6a  jz      short loc_1400A7A86
0x1400a7a6c  movzx   eax, word ptr [rcx+40h]
0x1400a7a70  mov     dword ptr [rbp+0D0h+var_170.28h+28h], eax
0x1400a7a73  mov     rax, [rcx+10h]
0x1400a7a77  add     rax, [rsi]
0x1400a7a7a  mov     qword ptr [rbp+0D0h+var_170.28h+30h], rax
0x1400a7a7e  mov     eax, [rsi+18h]
0x1400a7a81  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a7a84  jmp     short loc_1400A7A92
0x1400a7a86  mov     rax, [rsi+20h]
0x1400a7a8a  mov     qword ptr [rbp+0D0h+var_170.28h+30h], rax
0x1400a7a8e  mov     dword ptr [rbp+0D0h+var_170.28h+28h], r10d
0x1400a7a92  test    r15, r15
0x1400a7a95  jz      short loc_1400A7AAC
0x1400a7a97  mov     rdx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7a9a  mov     rcx, r14; this
0x1400a7a9d  call    ?IsAllocationInUse@VIDMM_GLOBAL@@QEBAEPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::IsAllocationInUse(VIDMM_GLOBAL_ALLOC *)
0x1400a7aa2  test    al, al
0x1400a7aa4  mov     ecx, r10d
0x1400a7aa7  setz    cl
0x1400a7aaa  jmp     short loc_1400A7AB1
0x1400a7aac  mov     ecx, 1
0x1400a7ab1  mov     eax, dword ptr [rbp+0D0h+var_170.28h+38h]
0x1400a7ab4  and     eax, 0FFFFFFFBh
0x1400a7ab7  shl     ecx, 2
0x1400a7aba  or      ecx, eax
0x1400a7abc  mov     dword ptr [rbp+0D0h+var_170.28h+38h], ecx
0x1400a7abf  mov     rcx, [r14+10h]; this
0x1400a7ac3  lea     rdx, [rsp+1D0h+var_170]; struct _DXGKARG_BUILDPAGINGBUFFER *
0x1400a7ac8  call    ?DdiBuildPagingBuffer@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_BUILDPAGINGBUFFER@@@Z; ADAPTER_RENDER::DdiBuildPagingBuffer(_DXGKARG_BUILDPAGINGBUFFER *)
0x1400a7acd  mov     dword ptr [rbp+0D0h+arg_40], eax
0x1400a7ad3  test    r15, r15
0x1400a7ad6  jz      short loc_1400A7B14
0x1400a7ad8  cmp     eax, 0C01E0102h
0x1400a7add  jnz     short loc_1400A7B14
0x1400a7adf  mov     rdx, [rbp+0D0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a7ae6  mov     r8, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7ae9  mov     rcx, r14; this
0x1400a7aec  call    ?WaitForAllPagingEngines@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingEngines(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400a7af1  mov     rdx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7af4  mov     rcx, r14; this
0x1400a7af7  call    ?VerifyAllocationIsIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::VerifyAllocationIsIdle(VIDMM_GLOBAL_ALLOC *)
0x1400a7afc  mov     rcx, [r14+10h]; this
0x1400a7b00  lea     rdx, [rsp+1D0h+var_170]; struct _DXGKARG_BUILDPAGINGBUFFER *
0x1400a7b05  or      dword ptr [rbp+0D0h+var_170.28h+38h], 4
0x1400a7b09  call    ?DdiBuildPagingBuffer@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_BUILDPAGINGBUFFER@@@Z; ADAPTER_RENDER::DdiBuildPagingBuffer(_DXGKARG_BUILDPAGINGBUFFER *)
0x1400a7b0e  mov     dword ptr [rbp+0D0h+arg_40], eax
0x1400a7b14  mov     rcx, [r14+0C30h]
0x1400a7b1b  test    rcx, rcx
0x1400a7b1e  jz      short loc_1400A7B45
0x1400a7b20  mov     rax, [rsi+10h]
0x1400a7b24  test    rax, rax
0x1400a7b27  jz      short loc_1400A7B2F
0x1400a7b29  cmp     dword ptr [rax+64h], 1
0x1400a7b2d  jz      short loc_1400A7B45
0x1400a7b2f  mov     rdx, [r14+18h]
0x1400a7b33  mov     r8, rdi; unsigned __int64
0x1400a7b36  mov     rcx, [rcx+8]; this
0x1400a7b3a  mov     edx, [rdx+0F0h]; unsigned int
0x1400a7b40  call    ?ChargeEvictionTransfer@VIDMM_PROCESS@@QEAAXK_K@Z; VIDMM_PROCESS::ChargeEvictionTransfer(ulong,unsigned __int64)
0x1400a7b45  lock add [r14+0FA8h], rdi
0x1400a7b4d  mov     al, cs:byte_140087201
0x1400a7b53  and     al, 10h
0x1400a7b55  mov     byte ptr [rbp+0D0h+arg_0], al
0x1400a7b5b  jz      short loc_1400A7BDA
0x1400a7b5d  mov     rax, [r12+10h]
0x1400a7b62  test    rax, rax
0x1400a7b65  jz      short loc_1400A7B73
0x1400a7b67  cmp     dword ptr [rax+64h], 1
0x1400a7b6b  mov     r13d, 2
0x1400a7b71  jz      short loc_1400A7B79
0x1400a7b73  mov     r13d, 1
0x1400a7b79  mov     rax, [rsp+1D0h+var_178]
0x1400a7b7e  mov     rdi, [rax+10h]
0x1400a7b82  call    cs:__imp_PsGetCurrentProcessId
0x1400a7b89  nop     dword ptr [rax+rax+00h]
0x1400a7b8e  mov     rcx, [rbp+0D0h+arg_20]
0x1400a7b95  mov     r9, rax
0x1400a7b98  mov     [rsp+40h], r13d
0x1400a7b9d  mov     [rsp+1D0h+var_198], rcx
0x1400a7ba2  mov     rcx, [rbp+0D0h+arg_28]
0x1400a7ba9  mov     qword ptr [rsp+1D0h+var_1A0], rcx
0x1400a7bae  mov     qword ptr [rsp+1D0h+var_1A8], rdi
0x1400a7bb3  mov     [rsp+1D0h+var_1B0], r15
0x1400a7bb8  call    McTemplateK0pppxxq_EtwWriteTransfer
0x1400a7bbd  mov     rdx, [rbp+0D0h+arg_20]; unsigned __int64
0x1400a7bc4  lea     rcx, [r14+0CE0h]; struct VIDMM_GLOBAL_STATISTICS *
0x1400a7bcb  mov     r8d, r13d; unsigned int
0x1400a7bce  call    ?VidMmRecordTransfer@@YAXPEAUVIDMM_GLOBAL_STATISTICS@@_KI@Z; VidMmRecordTransfer(VIDMM_GLOBAL_STATISTICS *,unsigned __int64,uint)
0x1400a7bd3  mov     r13, [rbp+0D0h+arg_28]
0x1400a7bda  mov     edi, dword ptr [rbp+0D0h+arg_40]
  ... truncated ...
```
