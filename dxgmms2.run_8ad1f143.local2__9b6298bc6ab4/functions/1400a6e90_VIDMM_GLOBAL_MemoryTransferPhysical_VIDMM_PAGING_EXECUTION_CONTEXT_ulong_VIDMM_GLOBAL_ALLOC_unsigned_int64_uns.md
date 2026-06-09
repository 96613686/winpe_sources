# VIDMM_GLOBAL::MemoryTransferPhysical(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,VIDMM_TRANSFER_PARAMETER *,VIDMM_TRANSFER_PARAMETER *,_DXGK_TRANSFERFLAGS)

- ea: `0x1400a6e90`
- end: `0x1400a73f3`
- name: `?MemoryTransferPhysical@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@KPEAUVIDMM_GLOBAL_ALLOC@@_K2PEAUVIDMM_TRANSFER_PARAMETER@@3U_DXGK_TRANSFERFLAGS@@@Z`
- size: `1379`
- prototype: `void __usercall(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, unsigned int@<r8d>, struct VIDMM_GLOBAL_ALLOC *@<r9>, unsigned __int64, unsigned __int64, struct VIDMM_TRANSFER_PARAMETER *, struct VIDMM_TRANSFER_PARAMETER *, struct _DXGK_TRANSFERFLAGS)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a6cc4`

## callees

- `0x140030f7c`
- `0x1400396e0`
- `0x14003a468`
- `0x140058ac0`
- `0x1400986ac`
- `0x14009881c`
- `0x14009d45c`
- `0x1400a6e90`
- `0x1400df9c0`
- `0x1400e1270`
- `0x14010aa7c`
- `0x14010da58`
- `0x1401122a4`
- `0x1401138a4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a731e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a731e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6ef1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6f1b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6f57`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6f9c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6ef1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6f1b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6f57`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a6f9c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a6ed3`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a6f01`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a6f3d`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a6f86`

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
  __int64 v12; // rdx
  __int64 v13; // rcx
  LARGE_INTEGER *v14; // rsi
  LARGE_INTEGER *v15; // r12
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // r13
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  LARGE_INTEGER v24; // rcx
  __int64 v25; // rdx
  _QWORD *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r10
  __int64 v29; // r11
  bool v30; // zf
  UINT Value; // eax
  void *DriverAllocation; // rax
  unsigned int v33; // r10d
  unsigned int v34; // ebx
  LARGE_INTEGER v35; // rcx
  unsigned __int64 v36; // r8
  unsigned int v37; // r10d
  unsigned __int64 QuadPart; // r9
  const unsigned __int64 *v39; // rdx
  LARGE_INTEGER v40; // rcx
  unsigned __int64 v41; // r9
  const unsigned __int64 *v42; // rdx
  BOOL v43; // ecx
  LARGE_INTEGER v44; // rcx
  unsigned __int8 IsAllocationInUse; // al
  int v46; // r10d
  int v47; // ecx
  struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E v48; // eax
  ADAPTER_RENDER *v49; // rcx
  __int64 v50; // rcx
  LARGE_INTEGER v51; // rax
  LARGE_INTEGER v52; // rax
  unsigned int v53; // r13d
  __int64 v54; // rdi
  unsigned int CurrentProcessId; // eax
  int v56; // edx
  int v57; // r8d
  struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E v58; // edi
  bool v59; // sf
  D3DGPU_VIRTUAL_ADDRESS v60; // [rsp+58h] [rbp-B0h]
  __int64 v61; // [rsp+60h] [rbp-A8h]
  struct _DXGKARG_BUILDPAGINGBUFFER v62; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v63; // [rsp+1E8h] [rbp+E0h] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v64; // [rsp+1F0h] [rbp+E8h]
  unsigned int v65; // [rsp+1F8h] [rbp+F0h]

  v65 = a3;
  v64 = a2;
  memset(&v62, 0, sizeof(v62));
  v14 = a8;
  v15 = a7;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v13, v12) + 24) = a4;
    WdLogGlobalForLineNumber = 15366;
    v18 = WdLogNewEntry5_WdTrace(v17, v16);
    v19 = a5;
    v20 = a6;
    *(_QWORD *)(v18 + 24) = a5;
    *(_QWORD *)(v18 + 32) = v20;
    WdLogGlobalForLineNumber = 15369;
    v23 = (_QWORD *)WdLogNewEntry5_WdTrace(v22, v21);
    v23[3] = v15[2].QuadPart;
    v23[4] = v15->QuadPart;
    v23[5] = v15[4].QuadPart;
    v24 = v15[3];
    v23[6] = v24.QuadPart;
    WdLogGlobalForLineNumber = 15371;
    v26 = (_QWORD *)((__int64 (__fastcall *)(_QWORD, _QWORD))WdLogNewEntry5_WdTrace)((LARGE_INTEGER)v24.QuadPart, v25);
    v26[3] = v14[2].QuadPart;
    v26[4] = v14->QuadPart;
    v26[5] = v14[4].QuadPart;
    v26[6] = v14[3].QuadPart;
    WdLogGlobalForLineNumber = 15373;
  }
  else
  {
    v20 = a6;
    v19 = a5;
  }
  memset(&v62, 0, sizeof(v62));
  LOBYTE(v27) = *((_BYTE *)this + 37231) != 0;
  v62.hSystemContext = (HANDLE)VidSchGetDriverPagingContext(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v65, v27);
  v62.MultipassOffset = v29;
  if ( a2 )
    v61 = *(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v28);
  else
    v61 = v29;
  v30 = (*((_BYTE *)this + 37225) & 0x20) == 0;
  Value = a9.Value;
  v62.Transfer.Flags = a9;
  if ( v30 && a4 )
  {
    if ( !v20 )
    {
      Value = a9.Value | 8;
      v62.Transfer.Flags.Value = a9.Value | 8;
    }
    if ( v19 + v20 == *(_QWORD *)(*(_QWORD *)a4 + 16LL) )
      v62.Transfer.Flags.Value = Value | 0x10;
  }
  DriverAllocation = VidMmGetDriverAllocation(a4);
  v34 = HIDWORD(a5);
  v60 = (D3DGPU_VIRTUAL_ADDRESS)DriverAllocation;
  do
  {
    VIDMM_GLOBAL::SetupForBuildPagingBufferIteration(this, v64, v33, a4, &v62);
    v30 = (*((_BYTE *)this + 37225) & 0x20) == 0;
    v35 = v15[2];
    v62.UpdateContextAllocation.ContextAllocation = v60;
    if ( v30 )
    {
      v62.Transfer.TransferSize = __PAIR64__(v34, v19);
      v62.Operation = DXGK_OPERATION_TRANSFER;
      v62.Transfer.TransferOffset = v20;
      v62.Transfer.MdlOffset = 0;
      if ( v35.QuadPart )
      {
        v62.Transfer.Source.SegmentId = *(unsigned __int16 *)(v35.QuadPart + 64);
        v62.Transfer.Source.SegmentAddress.QuadPart = v15->QuadPart + *(_QWORD *)(v35.QuadPart + 16);
        v62.Transfer.TransferOffset = v15[3].LowPart;
      }
      else
      {
        v62.Transfer.Source.SegmentAddress = v15[4];
        v62.Transfer.Source.SegmentId = 0;
      }
      v44 = v14[2];
      if ( v44.QuadPart )
      {
        v62.Transfer.Destination.SegmentId = *(unsigned __int16 *)(v44.QuadPart + 64);
        v62.Transfer.Destination.SegmentAddress.QuadPart = v14->QuadPart + *(_QWORD *)(v44.QuadPart + 16);
        v62.Transfer.TransferOffset = v14[3].LowPart;
      }
      else
      {
        v62.Transfer.Destination.SegmentAddress = v14[4];
        v62.Transfer.Destination.SegmentId = 0;
      }
      if ( a4 )
      {
        IsAllocationInUse = VIDMM_GLOBAL::IsAllocationInUse(this, a4);
        v47 = v46;
        LOBYTE(v47) = IsAllocationInUse == 0;
      }
      else
      {
        v47 = 1;
      }
      v62.Transfer.Flags.Value = v62.Transfer.Flags.Value & 0xFFFFFFFB | (4 * v47);
    }
    else
    {
      v62.Operation = DXGK_OPERATION_SIGNAL_MONITORED_FENCE|DXGK_OPERATION_SPECIAL_LOCK_TRANSFER;
      v36 = v19 >> 12;
      v37 = (unsigned int)v19 >> 12;
      v62.DiscardContent.SegmentId = v19 >> 12;
      v62.Fill.FillPattern = v20 >> 12;
      if ( v35.QuadPart )
      {
        v62.Transfer.TransferOffset = (unsigned __int64)v15[3].QuadPart >> 12;
        v62.Transfer.Source.SegmentId = *(unsigned __int16 *)(v35.QuadPart + 64);
        v62.UnmapApertureSegment.DummyPage.QuadPart = (unsigned __int64)(v15->QuadPart + *(_QWORD *)(v35.QuadPart + 16)) >> 12;
        v62.Transfer.Source.SegmentAddress.HighPart = 1;
        v62.Transfer.Source.SegmentAddress.LowPart = (unsigned int)v19 >> 12;
      }
      else
      {
        QuadPart = v15[1].QuadPart;
        v39 = (const unsigned __int64 *)v15[5].QuadPart;
        v62.Transfer.Source.SegmentId = 0;
        VidMmiInitializeAdlForPfnArray((struct _DXGK_ADL *)&v62.Reserved.Reserved[8], v39, v36, QuadPart);
        LODWORD(v36) = v62.DiscardContent.SegmentId;
      }
      v40 = v14[2];
      if ( v40.QuadPart )
      {
        v62.Transfer.TransferOffset = (unsigned __int64)v14[3].QuadPart >> 12;
        v62.Transfer.Destination.SegmentAddress.LowPart = *(unsigned __int16 *)(v40.QuadPart + 64);
        v62.UpdatePageTable.AllocationOffsetInBytes = (unsigned __int64)(v14->QuadPart + *(_QWORD *)(v40.QuadPart + 16)) >> 12;
        v62.TransferVirtual.DestinationPageTable = v37 | 0x100000000LL;
      }
      else
      {
        v41 = v14[1].QuadPart;
        v42 = (const unsigned __int64 *)v14[5].QuadPart;
        v62.Transfer.Destination.SegmentAddress.LowPart = 0;
        VidMmiInitializeAdlForPfnArray((struct _DXGK_ADL *)&v62.Reserved.Reserved[14], v42, v36, v41);
      }
      if ( a4 )
        v43 = VIDMM_GLOBAL::IsAllocationInUse(this, a4) == 0;
      else
        v43 = 1;
      v62.Reserved.Reserved[18] = v62.Reserved.Reserved[18] & 0xFFFFFFFB | (4 * v43);
    }
    v48 = (struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E)ADAPTER_RENDER::DdiBuildPagingBuffer(*((ADAPTER_RENDER **)this + 2), &v62);
    a9.0 = v48;
    if ( a4 && v48 == -1071775486 )
    {
      VIDMM_GLOBAL::WaitForAllPagingEngines(this, v64, a4);
      VIDMM_GLOBAL::VerifyAllocationIsIdle(this, a4);
      v49 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
      v62.Transfer.Flags.Value |= 4u;
      a9.0 = (struct _DXGK_TRANSFERFLAGS::$4D1486DD1E7506599394F0F2A8A65E0A::$302D1026E10F578CC86103988839248E)ADAPTER_RENDER::DdiBuildPagingBuffer(v49, &v62);
    }
    v50 = *((_QWORD *)this + 390);
    if ( v50 )
    {
      v51 = v14[2];
      if ( !v51.QuadPart || *(_DWORD *)(v51.QuadPart + 100) != 1 )
        VIDMM_PROCESS::ChargeEvictionTransfer(
          *(VIDMM_PROCESS **)(v50 + 8),
          *(_DWORD *)(*((_QWORD *)this + 3) + 240LL),
          v19);
    }
    _InterlockedAdd64((volatile signed __int64 *)this + 501, v19);
    LOBYTE(v63) = byte_140086201 & 0x10;
    if ( (byte_140086201 & 0x10) != 0 )
    {
      v52 = v15[2];
      if ( !v52.QuadPart || (v53 = 2, *(_DWORD *)(v52.QuadPart + 100) != 1) )
        v53 = 1;
      v54 = *(_QWORD *)(v61 + 16);
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      McTemplateK0pppxxq_EtwWriteTransfer(a6, v56, v57, CurrentProcessId, (char)a4, v54, a6, a5, v53);
      VidMmRecordTransfer((VIDMM_GLOBAL *)((char *)this + 3296), a5, v53);
      v20 = a6;
    }
    v58 = a9.0;
    v63 = 0;
    VIDMM_GLOBAL::CompleteBuildPagingBufferIteration(this, v64, v65, a4, &v62, a9.Value, 0, &v63, 0);
    v33 = v65;
    v59 = *(int *)&v58 < 0;
    v19 = a5;
  }
  while ( v59 );
}

```

## disassembly

```asm
0x1400a6e90  mov     rax, rsp
0x1400a6e93  mov     [rax+20h], rbx
0x1400a6e97  mov     [rax+18h], r8d
0x1400a6e9b  mov     [rax+10h], rdx
0x1400a6e9f  push    rbp
0x1400a6ea0  push    rsi
0x1400a6ea1  push    rdi
0x1400a6ea2  push    r12
0x1400a6ea4  push    r13
0x1400a6ea6  push    r14
0x1400a6ea8  push    r15
0x1400a6eaa  lea     rbp, [rax-0D8h]
0x1400a6eb1  sub     rsp, 1A0h
0x1400a6eb8  mov     rbx, rdx
0x1400a6ebb  mov     r14, rcx
0x1400a6ebe  xor     edx, edx; Val
0x1400a6ec0  lea     rcx, [rsp+1D0h+var_170]; void *
0x1400a6ec5  mov     r8d, 140h; Size
0x1400a6ecb  mov     r15, r9
0x1400a6ece  call    memset
0x1400a6ed3  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a6eda  mov     rsi, [rbp+0D0h+arg_38]
0x1400a6ee1  mov     r12, [rbp+0D0h+arg_30]
0x1400a6ee8  cmp     byte ptr [rax], 0
0x1400a6eeb  jz      loc_1400A6FD3
0x1400a6ef1  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a6ef8  nop     dword ptr [rax+rax+00h]
0x1400a6efd  mov     [rax+18h], r15
0x1400a6f01  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a6f08  mov     cs:WdLogGlobalForLineNumber, 3C06h
0x1400a6f12  cmp     byte ptr [rax], 0
0x1400a6f15  jz      loc_1400A6FD3
0x1400a6f1b  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a6f22  nop     dword ptr [rax+rax+00h]
0x1400a6f27  mov     rdi, [rbp+0D0h+arg_20]
0x1400a6f2e  mov     r13, [rbp+0D0h+arg_28]
0x1400a6f35  mov     [rax+18h], rdi
0x1400a6f39  mov     [rax+20h], r13
0x1400a6f3d  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a6f44  mov     cs:WdLogGlobalForLineNumber, 3C09h
0x1400a6f4e  cmp     byte ptr [rax], 0
0x1400a6f51  jz      loc_1400A6FE1
0x1400a6f57  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a6f5e  nop     dword ptr [rax+rax+00h]
0x1400a6f63  mov     rcx, [r12+10h]
0x1400a6f68  mov     [rax+18h], rcx
0x1400a6f6c  mov     rcx, [r12]
0x1400a6f70  mov     [rax+20h], rcx
0x1400a6f74  mov     rcx, [r12+20h]
0x1400a6f79  mov     [rax+28h], rcx
0x1400a6f7d  mov     rcx, [r12+18h]
0x1400a6f82  mov     [rax+30h], rcx
0x1400a6f86  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a6f8d  mov     cs:WdLogGlobalForLineNumber, 3C0Bh
0x1400a6f97  cmp     byte ptr [rax], 0
0x1400a6f9a  jz      short loc_1400A6FE1
0x1400a6f9c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a6fa3  nop     dword ptr [rax+rax+00h]
0x1400a6fa8  mov     rcx, [rsi+10h]
0x1400a6fac  mov     [rax+18h], rcx
0x1400a6fb0  mov     rcx, [rsi]
0x1400a6fb3  mov     [rax+20h], rcx
0x1400a6fb7  mov     rcx, [rsi+20h]
0x1400a6fbb  mov     [rax+28h], rcx
0x1400a6fbf  mov     rcx, [rsi+18h]
0x1400a6fc3  mov     [rax+30h], rcx
0x1400a6fc7  mov     cs:WdLogGlobalForLineNumber, 3C0Dh
0x1400a6fd1  jmp     short loc_1400A6FE1
0x1400a6fd3  mov     r13, [rbp+0D0h+arg_28]
0x1400a6fda  mov     rdi, [rbp+0D0h+arg_20]
0x1400a6fe1  xor     edx, edx; Val
0x1400a6fe3  lea     rcx, [rsp+1D0h+var_170]; void *
0x1400a6fe8  mov     r8d, 140h; Size
0x1400a6fee  call    memset
0x1400a6ff3  mov     rcx, [r14+10h]
0x1400a6ff7  xor     r11d, r11d
0x1400a6ffa  cmp     [r14+916Fh], r11b
0x1400a7001  mov     r10d, [rbp+0D0h+arg_10]
0x1400a7008  setnz   r8b
0x1400a700c  mov     edx, r10d
0x1400a700f  mov     rcx, [rcx+2E8h]
0x1400a7016  call    VidSchGetDriverPagingContext
0x1400a701b  mov     [rbp+0D0h+var_170.hSystemContext], rax
0x1400a7022  mov     [rbp+0D0h+var_170.MultipassOffset], r11d
0x1400a7026  test    rbx, rbx
0x1400a7029  jz      short loc_1400A703A
0x1400a702b  mov     rax, [rbx+18h]
0x1400a702f  mov     rdx, [rax+r10*8]
0x1400a7033  mov     [rsp+1D0h+var_178], rdx
0x1400a7038  jmp     short loc_1400A703F
0x1400a703a  mov     [rsp+1D0h+var_178], r11
0x1400a703f  test    byte ptr [r14+9169h], 20h
0x1400a7047  mov     eax, dword ptr [rbp+0D0h+arg_40]
0x1400a704d  mov     dword ptr [rbp+0D0h+var_170.28h+38h], eax
0x1400a7050  jnz     short loc_1400A7075
0x1400a7052  test    r15, r15
0x1400a7055  jz      short loc_1400A7075
0x1400a7057  test    r13, r13
0x1400a705a  jnz     short loc_1400A7062
0x1400a705c  or      eax, 8
0x1400a705f  mov     dword ptr [rbp+0D0h+var_170.28h+38h], eax
0x1400a7062  mov     rcx, [r15]
0x1400a7065  lea     rdx, [rdi+r13]
0x1400a7069  cmp     rdx, [rcx+10h]
0x1400a706d  jnz     short loc_1400A7075
0x1400a706f  or      eax, 10h
0x1400a7072  mov     dword ptr [rbp+0D0h+var_170.28h+38h], eax
0x1400a7075  mov     rcx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7078  call    ?VidMmGetDriverAllocation@@YAPEAXPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetDriverAllocation(VIDMM_GLOBAL_ALLOC const *)
0x1400a707d  mov     ebx, dword ptr [rbp+0D0h+arg_20+4]
0x1400a7083  mov     [rsp+1D0h+var_180], rax
0x1400a7088  mov     rdx, [rbp+0D0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a708f  lea     rax, [rsp+1D0h+var_170]
0x1400a7094  mov     r9, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7097  mov     [rsp+1D0h+var_1B0], rax; struct _DXGKARG_BUILDPAGINGBUFFER *
0x1400a709c  mov     r8d, r10d; unsigned int
0x1400a709f  mov     rcx, r14; this
0x1400a70a2  call    ?SetupForBuildPagingBufferIteration@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@KPEBUVIDMM_GLOBAL_ALLOC@@PEAU_DXGKARG_BUILDPAGINGBUFFER@@@Z; VIDMM_GLOBAL::SetupForBuildPagingBufferIteration(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,VIDMM_GLOBAL_ALLOC const *,_DXGKARG_BUILDPAGINGBUFFER *)
0x1400a70a7  test    byte ptr [r14+9169h], 20h
0x1400a70af  mov     rax, [rsp+1D0h+var_180]
0x1400a70b4  mov     rcx, [r12+10h]
0x1400a70b9  mov     qword ptr [rbp+0D0h+var_170.28h], rax
0x1400a70bd  jz      loc_1400A71BA
0x1400a70c3  mov     r8, rdi
0x1400a70c6  mov     [rsp+1D0h+var_170.Operation], 17h
0x1400a70ce  shr     r8, 0Ch; unsigned int
0x1400a70d2  mov     rax, r13
0x1400a70d5  shr     rax, 0Ch
0x1400a70d9  mov     r10d, edi
0x1400a70dc  shr     r10d, 0Ch
0x1400a70e0  mov     dword ptr [rbp+0D0h+var_170.28h+0Ch], r8d
0x1400a70e4  mov     dword ptr [rbp+0D0h+var_170.28h+10h], eax
0x1400a70e7  test    rcx, rcx
0x1400a70ea  jz      short loc_1400A711C
0x1400a70ec  mov     rax, [r12+18h]
0x1400a70f1  shr     rax, 0Ch
0x1400a70f5  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a70f8  movzx   eax, word ptr [rcx+40h]
0x1400a70fc  mov     dword ptr [rbp+0D0h+var_170.28h+18h], eax
0x1400a70ff  mov     rdx, [rcx+10h]
0x1400a7103  add     rdx, [r12]
0x1400a7107  shr     rdx, 0Ch
0x1400a710b  mov     qword ptr [rbp+0D0h+var_170.28h+28h], rdx
0x1400a710f  mov     dword ptr [rbp+0D0h+var_170.28h+24h], 1
0x1400a7116  mov     dword ptr [rbp+0D0h+var_170.28h+20h], r10d
0x1400a711a  jmp     short loc_1400A713A
0x1400a711c  mov     r9, [r12+8]; unsigned __int64
0x1400a7121  lea     rcx, [rbp+0D0h+var_170.28h+20h]; struct _DXGK_ADL *
0x1400a7125  mov     rdx, [r12+28h]; unsigned __int64 *
0x1400a712a  mov     dword ptr [rbp+0D0h+var_170.28h+18h], 0
0x1400a7131  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x1400a7136  mov     r8d, dword ptr [rbp+0D0h+var_170.28h+0Ch]; unsigned int
0x1400a713a  mov     rcx, [rsi+10h]
0x1400a713e  test    rcx, rcx
0x1400a7141  jz      short loc_1400A7171
0x1400a7143  mov     rax, [rsi+18h]
0x1400a7147  shr     rax, 0Ch
0x1400a714b  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a714e  movzx   eax, word ptr [rcx+40h]
0x1400a7152  mov     dword ptr [rbp+0D0h+var_170.28h+30h], eax
0x1400a7155  mov     rdx, [rcx+10h]
0x1400a7159  add     rdx, [rsi]
0x1400a715c  shr     rdx, 0Ch
0x1400a7160  mov     qword ptr [rbp+0D0h+var_170.28h+40h], rdx
0x1400a7164  mov     dword ptr [rbp+0D0h+var_170.28h+3Ch], 1
0x1400a716b  mov     dword ptr [rbp+0D0h+var_170.28h+38h], r10d
0x1400a716f  jmp     short loc_1400A7189
0x1400a7171  mov     r9, [rsi+8]; unsigned __int64
0x1400a7175  lea     rcx, [rbp+0D0h+var_170.28h+38h]; struct _DXGK_ADL *
0x1400a7179  mov     rdx, [rsi+28h]; unsigned __int64 *
0x1400a717d  mov     dword ptr [rbp+0D0h+var_170.28h+30h], 0
0x1400a7184  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x1400a7189  test    r15, r15
0x1400a718c  jz      short loc_1400A71A2
0x1400a718e  mov     rdx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7191  mov     rcx, r14; this
0x1400a7194  call    ?IsAllocationInUse@VIDMM_GLOBAL@@QEBAEPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::IsAllocationInUse(VIDMM_GLOBAL_ALLOC *)
0x1400a7199  xor     ecx, ecx
0x1400a719b  test    al, al
0x1400a719d  setz    cl
0x1400a71a0  jmp     short loc_1400A71A7
0x1400a71a2  mov     ecx, 1
0x1400a71a7  mov     eax, dword ptr [rbp+0D0h+var_170.28h+48h]
0x1400a71aa  and     eax, 0FFFFFFFBh
0x1400a71ad  shl     ecx, 2
0x1400a71b0  or      ecx, eax
0x1400a71b2  mov     dword ptr [rbp+0D0h+var_170.28h+48h], ecx
0x1400a71b5  jmp     loc_1400A725B
0x1400a71ba  xor     r10d, r10d
0x1400a71bd  mov     dword ptr [rbp+0D0h+var_170.28h+10h], edi
0x1400a71c0  mov     [rsp+1D0h+var_170.Operation], r10d
0x1400a71c5  mov     dword ptr [rbp+0D0h+var_170.28h+14h], ebx
0x1400a71c8  mov     dword ptr [rbp+0D0h+var_170.28h+8], r13d
0x1400a71cc  mov     dword ptr [rbp+0D0h+var_170.28h+3Ch], r10d
0x1400a71d0  test    rcx, rcx
0x1400a71d3  jz      short loc_1400A71F2
0x1400a71d5  movzx   eax, word ptr [rcx+40h]
0x1400a71d9  mov     dword ptr [rbp+0D0h+var_170.28h+18h], eax
0x1400a71dc  mov     rax, [rcx+10h]
0x1400a71e0  add     rax, [r12]
0x1400a71e4  mov     qword ptr [rbp+0D0h+var_170.28h+20h], rax
0x1400a71e8  mov     eax, [r12+18h]
0x1400a71ed  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a71f0  jmp     short loc_1400A71FF
0x1400a71f2  mov     rax, [r12+20h]
0x1400a71f7  mov     qword ptr [rbp+0D0h+var_170.28h+20h], rax
0x1400a71fb  mov     dword ptr [rbp+0D0h+var_170.28h+18h], r10d
0x1400a71ff  mov     rcx, [rsi+10h]
0x1400a7203  test    rcx, rcx
0x1400a7206  jz      short loc_1400A7222
0x1400a7208  movzx   eax, word ptr [rcx+40h]
0x1400a720c  mov     dword ptr [rbp+0D0h+var_170.28h+28h], eax
0x1400a720f  mov     rax, [rcx+10h]
0x1400a7213  add     rax, [rsi]
0x1400a7216  mov     qword ptr [rbp+0D0h+var_170.28h+30h], rax
0x1400a721a  mov     eax, [rsi+18h]
0x1400a721d  mov     dword ptr [rbp+0D0h+var_170.28h+8], eax
0x1400a7220  jmp     short loc_1400A722E
0x1400a7222  mov     rax, [rsi+20h]
0x1400a7226  mov     qword ptr [rbp+0D0h+var_170.28h+30h], rax
0x1400a722a  mov     dword ptr [rbp+0D0h+var_170.28h+28h], r10d
0x1400a722e  test    r15, r15
0x1400a7231  jz      short loc_1400A7248
0x1400a7233  mov     rdx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7236  mov     rcx, r14; this
0x1400a7239  call    ?IsAllocationInUse@VIDMM_GLOBAL@@QEBAEPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::IsAllocationInUse(VIDMM_GLOBAL_ALLOC *)
0x1400a723e  test    al, al
0x1400a7240  mov     ecx, r10d
0x1400a7243  setz    cl
0x1400a7246  jmp     short loc_1400A724D
0x1400a7248  mov     ecx, 1
0x1400a724d  mov     eax, dword ptr [rbp+0D0h+var_170.28h+38h]
0x1400a7250  and     eax, 0FFFFFFFBh
0x1400a7253  shl     ecx, 2
0x1400a7256  or      ecx, eax
0x1400a7258  mov     dword ptr [rbp+0D0h+var_170.28h+38h], ecx
0x1400a725b  mov     rcx, [r14+10h]; this
0x1400a725f  lea     rdx, [rsp+1D0h+var_170]; struct _DXGKARG_BUILDPAGINGBUFFER *
0x1400a7264  call    ?DdiBuildPagingBuffer@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_BUILDPAGINGBUFFER@@@Z; ADAPTER_RENDER::DdiBuildPagingBuffer(_DXGKARG_BUILDPAGINGBUFFER *)
0x1400a7269  mov     dword ptr [rbp+0D0h+arg_40], eax
0x1400a726f  test    r15, r15
0x1400a7272  jz      short loc_1400A72B0
0x1400a7274  cmp     eax, 0C01E0102h
0x1400a7279  jnz     short loc_1400A72B0
0x1400a727b  mov     rdx, [rbp+0D0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a7282  mov     r8, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7285  mov     rcx, r14; this
0x1400a7288  call    ?WaitForAllPagingEngines@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingEngines(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400a728d  mov     rdx, r15; struct VIDMM_GLOBAL_ALLOC *
0x1400a7290  mov     rcx, r14; this
0x1400a7293  call    ?VerifyAllocationIsIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::VerifyAllocationIsIdle(VIDMM_GLOBAL_ALLOC *)
0x1400a7298  mov     rcx, [r14+10h]; this
0x1400a729c  lea     rdx, [rsp+1D0h+var_170]; struct _DXGKARG_BUILDPAGINGBUFFER *
0x1400a72a1  or      dword ptr [rbp+0D0h+var_170.28h+38h], 4
0x1400a72a5  call    ?DdiBuildPagingBuffer@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_BUILDPAGINGBUFFER@@@Z; ADAPTER_RENDER::DdiBuildPagingBuffer(_DXGKARG_BUILDPAGINGBUFFER *)
0x1400a72aa  mov     dword ptr [rbp+0D0h+arg_40], eax
0x1400a72b0  mov     rcx, [r14+0C30h]
0x1400a72b7  test    rcx, rcx
0x1400a72ba  jz      short loc_1400A72E1
0x1400a72bc  mov     rax, [rsi+10h]
0x1400a72c0  test    rax, rax
0x1400a72c3  jz      short loc_1400A72CB
0x1400a72c5  cmp     dword ptr [rax+64h], 1
0x1400a72c9  jz      short loc_1400A72E1
0x1400a72cb  mov     rdx, [r14+18h]
0x1400a72cf  mov     r8, rdi; unsigned __int64
0x1400a72d2  mov     rcx, [rcx+8]; this
0x1400a72d6  mov     edx, [rdx+0F0h]; unsigned int
0x1400a72dc  call    ?ChargeEvictionTransfer@VIDMM_PROCESS@@QEAAXK_K@Z; VIDMM_PROCESS::ChargeEvictionTransfer(ulong,unsigned __int64)
0x1400a72e1  lock add [r14+0FA8h], rdi
0x1400a72e9  mov     al, cs:byte_140086201
0x1400a72ef  and     al, 10h
0x1400a72f1  mov     byte ptr [rbp+0D0h+arg_0], al
0x1400a72f7  jz      short loc_1400A7376
0x1400a72f9  mov     rax, [r12+10h]
0x1400a72fe  test    rax, rax
0x1400a7301  jz      short loc_1400A730F
0x1400a7303  cmp     dword ptr [rax+64h], 1
0x1400a7307  mov     r13d, 2
0x1400a730d  jz      short loc_1400A7315
0x1400a730f  mov     r13d, 1
0x1400a7315  mov     rax, [rsp+1D0h+var_178]
0x1400a731a  mov     rdi, [rax+10h]
0x1400a731e  call    cs:__imp_PsGetCurrentProcessId
0x1400a7325  nop     dword ptr [rax+rax+00h]
0x1400a732a  mov     rcx, [rbp+0D0h+arg_20]
0x1400a7331  mov     r9, rax
0x1400a7334  mov     [rsp+40h], r13d
0x1400a7339  mov     [rsp+1D0h+var_198], rcx
0x1400a733e  mov     rcx, [rbp+0D0h+arg_28]
0x1400a7345  mov     qword ptr [rsp+1D0h+var_1A0], rcx
0x1400a734a  mov     qword ptr [rsp+1D0h+var_1A8], rdi
0x1400a734f  mov     [rsp+1D0h+var_1B0], r15
0x1400a7354  call    McTemplateK0pppxxq_EtwWriteTransfer
0x1400a7359  mov     rdx, [rbp+0D0h+arg_20]; unsigned __int64
0x1400a7360  lea     rcx, [r14+0CE0h]; struct VIDMM_GLOBAL_STATISTICS *
0x1400a7367  mov     r8d, r13d; unsigned int
0x1400a736a  call    ?VidMmRecordTransfer@@YAXPEAUVIDMM_GLOBAL_STATISTICS@@_KI@Z; VidMmRecordTransfer(VIDMM_GLOBAL_STATISTICS *,unsigned __int64,uint)
0x1400a736f  mov     r13, [rbp+0D0h+arg_28]
0x1400a7376  mov     edi, dword ptr [rbp+0D0h+arg_40]
  ... truncated ...
```
