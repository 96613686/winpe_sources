# VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)

- ea: `0x1400fdc1c`
- end: `0x1400fe305`
- name: `?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z`
- size: `1769`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_DEVICE *, struct VIDMM_GLOBAL_ALLOC *, bool)`
- caller_count: `9`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14009d31c`
- `0x14009fcf4`
- `0x1400bfce0`
- `0x1400c12cc`
- `0x1400c1cdc`
- `0x1400f18cc`
- `0x1400fd7a8`
- `0x1400fdb44`
- `0x1400fdc04`

## callees

- `0x14002bcc0`
- `0x14002bddc`
- `0x14002e2ac`
- `0x14002e6c0`
- `0x14002e8f8`
- `0x140030578`
- `0x140031434`
- `0x14003196c`
- `0x140036d98`
- `0x140037c2c`
- `0x140038b2c`
- `0x140039a40`
- `0x14003ccdc`
- `0x1400450b4`
- `0x140058710`
- `0x140058f50`
- `0x140059030`
- `0x140059380`
- `0x140097af4`
- `0x1400c9c8c`
- `0x1400e8db0`
- `0x1400eaf08`
- `0x1400ee6e4`
- `0x1400fdc1c`
- `0x1400feb90`
- `0x14010bea0`
- `0x14010cd20`
- `0x14010d018`
- `0x1401114dc`
- `0x140115f00`
- `0x140119e10`
- `0x14011c214`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400fe033`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400fe033`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fdc63`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fdc63`
- `watchdog!WdLogSingleEntry5` at `0x1400fe019`
- `watchdog!WdLogSingleEntry5` at `0x1400fe019`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fdff4`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x1400fde10`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x1400fde10`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400fdc45`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_GLOBAL::DestroyOneAllocation(
        VIDMM_GLOBAL *this,
        struct VIDMM_DEVICE *a2,
        struct VIDMM_GLOBAL_ALLOC *a3,
        char a4)
{
  __int64 v4; // rbp
  __int64 v9; // rax
  bool v10; // si
  int v11; // eax
  bool v12; // r8
  __int64 v13; // r14
  __int64 v14; // rax
  VIDMM_GLOBAL *v15; // rcx
  int v16; // r8d
  struct VIDMM_CROSSADAPTER_ALLOC *v17; // rdx
  __int64 v18; // rdx
  int *v19; // rdx
  __int64 v20; // rsi
  int *v21; // r9
  __int64 v22; // rcx
  unsigned int CurrentProcessId; // eax
  int v24; // r8d
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rdx
  char *v27; // rax
  struct VIDMM_GLOBAL_ALLOC_NONPAGED *v28; // rdx
  __int64 i; // rsi
  void *v30; // rcx
  VIDMM_FLIP_QUEUE_REFERENCES *v31; // rcx
  void *v32; // rdx
  __int64 v33; // rcx
  unsigned int v34; // edx
  int v35; // [rsp+28h] [rbp-210h]
  int v36; // [rsp+48h] [rbp-1F0h]
  int v37; // [rsp+60h] [rbp-1D8h]
  int v38; // [rsp+138h] [rbp-100h]
  int v39; // [rsp+13Ch] [rbp-FCh]
  int v40; // [rsp+140h] [rbp-F8h]
  int v41; // [rsp+144h] [rbp-F4h]
  int v42; // [rsp+148h] [rbp-F0h]
  int v43; // [rsp+14Ch] [rbp-ECh]
  __int64 v44; // [rsp+158h] [rbp-E0h]
  __int64 v45; // [rsp+160h] [rbp-D8h]
  __int64 v46; // [rsp+168h] [rbp-D0h]
  _BYTE v47[32]; // [rsp+170h] [rbp-C8h] BYREF
  _QWORD v48[12]; // [rsp+190h] [rbp-A8h] BYREF

  v4 = *(_QWORD *)a3;
  if ( g_IsInternalReleaseOrDbg )
  {
    v9 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v9 + 24) = a3;
    *(_QWORD *)(v9 + 32) = a2;
    WdLogGlobalForLineNumber = 4719;
  }
  v10 = 0;
  if ( (*((_DWORD *)a3 + 6) & 4) == 0 )
  {
    DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
      (DXGAUTOPUSHLOCKEXCLUSIVE *)v47,
      (VIDMM_GLOBAL *)((char *)this + 36408));
    if ( *((_QWORD *)a3 + 34) )
      VIDMM_GLOBAL::RemoveAllocationFromOfferList(this, a3);
    if ( *((_QWORD *)a3 + 36) )
      VIDMM_GLOBAL::RemoveAllocationFromDecommitList(this, a3);
    v10 = *((_QWORD *)this + 5173) == (_QWORD)a3;
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v47);
  }
  if ( (*((_DWORD *)a3 + 8) & 4) != 0 )
  {
    if ( (*(_DWORD *)(v4 + 64) & 0x40) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( (*(_DWORD *)(v4 + 64) & 0x41) != 0 )
    {
      memset(v48, 0, 0x58u);
      v11 = (*(_DWORD *)(v4 + 60) >> 2) & 0x3F;
      LODWORD(v48[0]) = 112;
      HIDWORD(v48[0]) = v11;
      v48[5] = a3;
      LODWORD(v48[6]) = 0;
      VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(this, (struct VIDMM_SYSTEM_COMMAND *)v48, v12);
      v10 = 0;
    }
    else
    {
      v10 = 1;
    }
    v13 = *(_QWORD *)(*((_QWORD *)a3 + 6) + 32LL);
    if ( (*((_DWORD *)a3 + 8) & 2) != 0 )
    {
      VIDMM_SEGMENT::UnlockAllocationBackingStore(this, a3, 0);
      VIDMM_GLOBAL::ReturnPinnedBackingStore(this, *(_QWORD *)(v4 + 16));
      *((_DWORD *)a3 + 8) &= ~2u;
    }
    VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
      (VIDMM_PROCESS_AUTOATTACH *)v48,
      *(struct VIDMM_PROCESS **)(*((_QWORD *)a3 + 6) + 8LL),
      1);
    VIDMM_GLOBAL::CloseOneAllocation(this, (struct VIDMM_ALLOC *)(v13 - 40), 0, 0, 0, 0);
    VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v48);
    *((_QWORD *)a3 + 6) = 0;
  }
  if ( v10 )
    VidMmSynchronizeWithWorkerThreadRun(*(const struct VIDMM_WORKER_THREAD **)this);
  if ( a4 )
    VIDMM_GLOBAL::WaitForAllPagingOperations(this, 0, a3);
  if ( (unsigned int)Feature_SystemCommitMdlLeakInstrumentation__private_IsEnabledDeviceUsageNoInline() )
  {
    v14 = *((_QWORD *)a3 + 7);
    if ( v14 )
    {
      LOBYTE(v35) = 5;
      DxgCreateLiveDumpWithWdLogs(403, 2083, this, a3, v14, v35);
    }
  }
  if ( (*((_DWORD *)a3 + 8) & 0x20) != 0 )
    VIDMM_GLOBAL::UncommitGlobalBackingStore(this, a3, 1);
  if ( g_Feature_ResourcePoolManagement )
    VidMmDereferenceResourcePool(**((const struct VIDMM_RESOURCE_POOL ***)a3 + 44));
  else
    VidMmiClosePartition(**((struct VIDMM_PARTITION ***)a3 + 43));
  v17 = (struct VIDMM_CROSSADAPTER_ALLOC *)*((_QWORD *)a3 + 45);
  if ( v17 )
  {
    VIDMM_GLOBAL::FreeCrossAdapterDataDpc(v15, v17, a3);
    v15 = (VIDMM_GLOBAL *)(unsigned int)_InterlockedDecrement(*((volatile signed __int32 **)a3 + 45));
    if ( (_DWORD)v15 )
    {
      if ( (int)v15 < 0 )
      {
        v21 = (int *)*((_QWORD *)a3 + 45);
        v22 = *v21;
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 270, 66, v21, v22, 0);
        WdLogGlobalForLineNumber = 227;
        goto LABEL_42;
      }
    }
    else
    {
      VIDMM_GLOBAL::DestroyCrossAdapterAllocation(v15, *((struct VIDMM_CROSSADAPTER_ALLOC **)a3 + 45));
    }
    *((_QWORD *)a3 + 45) = 0;
  }
  v18 = *((_QWORD *)a3 + 49);
  if ( *(_WORD *)(v18 + 8) && (byte_140087201 & 1) != 0 )
    McTemplateK0puu_EtwWriteTransfer(
      (_DWORD)v15,
      (unsigned int)&EventReportOfferAllocation,
      v16,
      (_DWORD)a3,
      *(_BYTE *)(v18 + 8),
      *((_BYTE *)a3 + 304));
  VidMmGetAllocationHint(a3);
  if ( (byte_140087201 & 0x10) != 0 )
  {
    v44 = *((_QWORD *)a3 + 1);
    v38 = *(_DWORD *)(v4 + 56);
    v39 = *(_DWORD *)(v4 + 36);
    v40 = *(_DWORD *)(v4 + 48);
    v41 = *(_DWORD *)(v4 + 40);
    v42 = *(_DWORD *)(v4 + 32);
    v45 = *(_QWORD *)(v4 + 16);
    v43 = *v19;
    v46 = *((_QWORD *)this + 3);
    if ( !a2 )
    {
      LOBYTE(v20) = 0;
LABEL_43:
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
        v46,
        (unsigned int)&EventDestroyAdapterAllocation,
        v24,
        CurrentProcessId,
        v20,
        v46,
        v43,
        v45,
        v42,
        v36,
        v41,
        v40,
        v37,
        v39,
        v38,
        (char)a3,
        v44);
      goto LABEL_44;
    }
LABEL_42:
    v20 = *((_QWORD *)a2 + 3);
    goto LABEL_43;
  }
LABEL_44:
  v25 = *(_QWORD *)(v4 + 16);
  _InterlockedIncrement((volatile signed __int32 *)this + 944);
  _InterlockedAdd64((volatile signed __int64 *)this + 473, v25);
  v26 = *(_QWORD *)(v4 + 16);
  v27 = (char *)this + 3904;
  if ( (**((_DWORD **)a3 + 49) & 0x20000000) == 0 )
    v27 = (char *)this + 3920;
  _InterlockedIncrement((volatile signed __int32 *)v27);
  _InterlockedAdd64((volatile signed __int64 *)v27 + 1, v26);
  _InterlockedAdd64((volatile signed __int64 *)this + 4556, -*(_QWORD *)(v4 + 16));
  v28 = (struct VIDMM_GLOBAL_ALLOC_NONPAGED *)*((_QWORD *)a3 + 49);
  if ( v28 )
  {
    if ( *((_QWORD *)v28 + 4) )
    {
      VidSchiValidateAllocationNotDisplayed(*(struct _VIDSCH_GLOBAL **)(*((_QWORD *)this + 2) + 744LL), v28);
      for ( i = 0; i != 2; ++i )
      {
        v30 = *(void **)(*(_QWORD *)(*((_QWORD *)a3 + 49) + 32LL) + 8 * i);
        if ( v30 )
        {
          VidSchDestroySyncObject(v30);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a3 + 49) + 32LL) + 8 * i) = 0;
        }
      }
      operator delete(*(void **)(*((_QWORD *)a3 + 49) + 32LL));
      *(_QWORD *)(*((_QWORD *)a3 + 49) + 32LL) = 0;
    }
    v31 = *(VIDMM_FLIP_QUEUE_REFERENCES **)(*((_QWORD *)a3 + 49) + 24LL);
    if ( v31 )
    {
      VIDMM_FLIP_QUEUE_REFERENCES::ReleaseReference(v31, (unsigned int)v28);
      *(_QWORD *)(*((_QWORD *)a3 + 49) + 24LL) = 0;
    }
  }
  v32 = (void *)*((_QWORD *)a3 + 46);
  if ( v32 )
    SysMmFreeLogicalMemory(*(struct SYSMM_ADAPTER **)(*((_QWORD *)this + 3) + 224LL), v32);
  if ( *(_QWORD *)a3 )
  {
    v33 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 40LL))(v33);
    *(_QWORD *)a3 = 0;
  }
  if ( *((_DWORD *)a3 + 62) )
  {
    *((_DWORD *)a3 + 6) |= 0x40000u;
  }
  else
  {
    operator delete(*((void **)a3 + 49));
    *((_DWORD *)a3 + 6) |= 0x20000u;
    VIDMM_GLOBAL_ALLOC::`scalar deleting destructor'(a3, v34);
  }
}

```

## disassembly

```asm
0x1400fdc1c  mov     [rsp+arg_18], rbx
0x1400fdc21  push    rbp
0x1400fdc22  push    rsi
0x1400fdc23  push    rdi
0x1400fdc24  push    r12
0x1400fdc26  push    r13
0x1400fdc28  push    r14
0x1400fdc2a  push    r15
0x1400fdc2c  sub     rsp, 200h
0x1400fdc33  mov     rax, cs:__security_cookie
0x1400fdc3a  xor     rax, rsp
0x1400fdc3d  mov     [rsp+238h+var_48], rax
0x1400fdc45  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400fdc4c  xor     r12d, r12d
0x1400fdc4f  mov     rbp, [r8]
0x1400fdc52  mov     r15b, r9b
0x1400fdc55  mov     rbx, r8
0x1400fdc58  mov     r13, rdx
0x1400fdc5b  mov     rdi, rcx
0x1400fdc5e  cmp     [rax], r12b
0x1400fdc61  jz      short loc_1400FDC81
0x1400fdc63  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400fdc6a  nop     dword ptr [rax+rax+00h]
0x1400fdc6f  mov     [rax+18h], rbx
0x1400fdc73  mov     [rax+20h], r13
0x1400fdc77  mov     cs:WdLogGlobalForLineNumber, 126Fh
0x1400fdc81  mov     eax, [rbx+18h]
0x1400fdc84  mov     sil, r12b
0x1400fdc87  test    al, 4
0x1400fdc89  jnz     short loc_1400FDCDF
0x1400fdc8b  lea     rdx, [rdi+8E38h]; struct DXGPUSHLOCK *
0x1400fdc92  lea     rcx, [rsp+238h+var_C8]; this
0x1400fdc9a  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400fdc9f  cmp     [rbx+110h], r12
0x1400fdca6  jz      short loc_1400FDCB3
0x1400fdca8  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fdcab  mov     rcx, rdi; this
0x1400fdcae  call    ?RemoveAllocationFromOfferList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromOfferList(VIDMM_GLOBAL_ALLOC *)
0x1400fdcb3  cmp     [rbx+120h], r12
0x1400fdcba  jz      short loc_1400FDCC7
0x1400fdcbc  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fdcbf  mov     rcx, rdi; this
0x1400fdcc2  call    ?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *)
0x1400fdcc7  cmp     [rdi+0A1A8h], rbx
0x1400fdcce  lea     rcx, [rsp+238h+var_C8]; this
0x1400fdcd6  setz    sil
0x1400fdcda  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400fdcdf  mov     eax, [rbx+20h]
0x1400fdce2  test    al, 4
0x1400fdce4  jz      loc_1400FDDC5
0x1400fdcea  mov     eax, [rbp+40h]
0x1400fdced  test    al, 40h
0x1400fdcef  jz      short loc_1400FDCF6
0x1400fdcf1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400fdcf6  mov     eax, [rbp+40h]
0x1400fdcf9  test    al, 41h
0x1400fdcfb  jnz     short loc_1400FDD02
0x1400fdcfd  mov     sil, 1
0x1400fdd00  jmp     short loc_1400FDD53
0x1400fdd02  xor     edx, edx; Val
0x1400fdd04  lea     rcx, [rsp+238h+var_A8]; void *
0x1400fdd0c  lea     r8d, [rdx+58h]; Size
0x1400fdd10  call    memset
0x1400fdd15  mov     eax, [rbp+3Ch]
0x1400fdd18  lea     rdx, [rsp+238h+var_A8]; struct VIDMM_SYSTEM_COMMAND *
0x1400fdd20  shr     eax, 2
0x1400fdd23  mov     rcx, rdi; this
0x1400fdd26  and     eax, 3Fh
0x1400fdd29  mov     [rsp+238h+var_A8], 70h ; 'p'
0x1400fdd34  mov     [rsp+238h+var_A4], eax
0x1400fdd3b  mov     [rsp+238h+var_80], rbx
0x1400fdd43  mov     [rsp+238h+var_78], r12d
0x1400fdd4b  call    ?QueueSystemCleanupCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x1400fdd50  mov     sil, r12b
0x1400fdd53  mov     rax, [rbx+30h]
0x1400fdd57  mov     r14, [rax+20h]
0x1400fdd5b  mov     eax, [rbx+20h]
0x1400fdd5e  test    al, 2
0x1400fdd60  jz      short loc_1400FDD80
0x1400fdd62  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1400fdd65  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fdd68  mov     rcx, rdi; this
0x1400fdd6b  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400fdd70  mov     rdx, [rbp+10h]; unsigned __int64
0x1400fdd74  mov     rcx, rdi; this
0x1400fdd77  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400fdd7c  and     dword ptr [rbx+20h], 0FFFFFFFDh
0x1400fdd80  mov     rdx, [rbx+30h]
0x1400fdd84  lea     rcx, [rsp+238h+var_A8]; this
0x1400fdd8c  mov     r8b, 1; bool
0x1400fdd8f  mov     rdx, [rdx+8]; struct VIDMM_PROCESS *
0x1400fdd93  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400fdd98  xor     r9d, r9d; bool
0x1400fdd9b  mov     [rsp+238h+var_210], r12; struct _KEVENT **
0x1400fdda0  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1400fdda3  mov     dword ptr [rsp+238h+var_218], r12d; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400fdda8  lea     rdx, [r14-28h]; struct VIDMM_ALLOC *
0x1400fddac  mov     rcx, rdi; this
0x1400fddaf  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x1400fddb4  lea     rcx, [rsp+238h+var_A8]; this
0x1400fddbc  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400fddc1  mov     [rbx+30h], r12
0x1400fddc5  test    sil, sil
0x1400fddc8  jz      short loc_1400FDDD2
0x1400fddca  mov     rcx, [rdi]; struct VIDMM_WORKER_THREAD *
0x1400fddcd  call    ?VidMmSynchronizeWithWorkerThreadRun@@YAXPEBUVIDMM_WORKER_THREAD@@@Z; VidMmSynchronizeWithWorkerThreadRun(VIDMM_WORKER_THREAD const *)
0x1400fddd2  test    r15b, r15b
0x1400fddd5  jz      short loc_1400FDDE4
0x1400fddd7  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fddda  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400fdddc  mov     rcx, rdi; this
0x1400fdddf  call    ?WaitForAllPagingOperations@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingOperations(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400fdde4  call    Feature_SystemCommitMdlLeakInstrumentation__private_IsEnabledDeviceUsageNoInline
0x1400fdde9  test    eax, eax
0x1400fddeb  jz      short loc_1400FDE1C
0x1400fdded  mov     rax, [rbx+38h]
0x1400fddf1  test    rax, rax
0x1400fddf4  jz      short loc_1400FDE1C
0x1400fddf6  mov     byte ptr [rsp+238h+var_210], 5
0x1400fddfb  mov     r9, rbx
0x1400fddfe  mov     r8, rdi
0x1400fde01  mov     qword ptr [rsp+238h+var_218], rax
0x1400fde06  mov     edx, 823h
0x1400fde0b  mov     ecx, 193h
0x1400fde10  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x1400fde17  nop     dword ptr [rax+rax+00h]
0x1400fde1c  mov     eax, [rbx+20h]
0x1400fde1f  test    al, 20h
0x1400fde21  jz      short loc_1400FDE31
0x1400fde23  mov     r8b, 1; bool
0x1400fde26  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fde29  mov     rcx, rdi; this
0x1400fde2c  call    ?UncommitGlobalBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::UncommitGlobalBackingStore(VIDMM_GLOBAL_ALLOC *,bool)
0x1400fde31  cmp     cs:?g_Feature_ResourcePoolManagement@@3_NA, r12b; bool g_Feature_ResourcePoolManagement
0x1400fde38  jz      short loc_1400FDE4B
0x1400fde3a  mov     rcx, [rbx+160h]
0x1400fde41  mov     rcx, [rcx]; this
0x1400fde44  call    ?VidMmDereferenceResourcePool@@YAXPEBUVIDMM_RESOURCE_POOL@@@Z; VidMmDereferenceResourcePool(VIDMM_RESOURCE_POOL const *)
0x1400fde49  jmp     short loc_1400FDE5A
0x1400fde4b  mov     rcx, [rbx+158h]
0x1400fde52  mov     rcx, [rcx]; this
0x1400fde55  call    ?VidMmiClosePartition@@YAXPEAUVIDMM_PARTITION@@@Z; VidMmiClosePartition(VIDMM_PARTITION *)
0x1400fde5a  mov     rdx, [rbx+168h]; struct VIDMM_CROSSADAPTER_ALLOC *
0x1400fde61  test    rdx, rdx
0x1400fde64  jz      short loc_1400FDE98
0x1400fde66  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fde69  call    ?FreeCrossAdapterDataDpc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::FreeCrossAdapterDataDpc(VIDMM_CROSSADAPTER_ALLOC *,VIDMM_GLOBAL_ALLOC *)
0x1400fde6e  mov     rax, [rbx+168h]
0x1400fde75  or      ecx, 0FFFFFFFFh
0x1400fde78  lock xadd [rax], ecx
0x1400fde7c  sub     ecx, 1; this
0x1400fde7f  jnz     loc_1400FDFE5
0x1400fde85  mov     rdx, [rbx+168h]; struct VIDMM_CROSSADAPTER_ALLOC *
0x1400fde8c  call    ?DestroyCrossAdapterAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_CROSSADAPTER_ALLOC@@@Z; VIDMM_GLOBAL::DestroyCrossAdapterAllocation(VIDMM_CROSSADAPTER_ALLOC *)
0x1400fde91  mov     [rbx+168h], r12
0x1400fde98  mov     rdx, [rbx+188h]
0x1400fde9f  cmp     [rdx+8], r12w
0x1400fdea4  jz      short loc_1400FDED6
0x1400fdea6  test    cs:byte_140087201, 1
0x1400fdead  jz      short loc_1400FDED6
0x1400fdeaf  mov     al, [rbx+130h]
0x1400fdeb5  mov     r9, rbx
0x1400fdeb8  mov     byte ptr [rsp+238h+var_210], al
0x1400fdebc  mov     al, [rdx+8]
0x1400fdebf  lea     rdx, EventReportOfferAllocation
0x1400fdec6  mov     byte ptr [rsp+238h+var_218], al
0x1400fdeca  call    McTemplateK0puu_EtwWriteTransfer
0x1400fdecf  mov     rdx, [rbx+188h]
0x1400fded6  mov     rcx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400fded9  call    ?VidMmGetAllocationHint@@YAPEBU_DXGK_ALLOCATIONUSAGEHINT@@PEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetAllocationHint(VIDMM_GLOBAL_ALLOC const *)
0x1400fdede  test    cs:byte_140087201, 10h
0x1400fdee5  jz      loc_1400FE188
0x1400fdeeb  mov     rcx, [rbx]
0x1400fdeee  mov     r14d, [rbx+18h]
0x1400fdef2  mov     r15d, [rbp+3Ch]
0x1400fdef6  mov     r12d, [rbx+20h]
0x1400fdefa  mov     [rsp+238h+var_E8], rcx
0x1400fdf02  mov     ecx, [rax+24h]
0x1400fdf05  mov     [rsp+238h+var_128], ecx
0x1400fdf0c  mov     ecx, [rax+20h]
0x1400fdf0f  mov     [rsp+238h+var_124], ecx
0x1400fdf16  mov     ecx, [rax+1Ch]
0x1400fdf19  mov     [rsp+238h+var_120], ecx
0x1400fdf20  mov     ecx, [rax+18h]
0x1400fdf23  mov     [rsp+238h+var_11C], ecx
0x1400fdf2a  mov     ecx, [rax+14h]
0x1400fdf2d  mov     [rsp+238h+var_118], ecx
0x1400fdf34  mov     ecx, [rax+10h]
0x1400fdf37  mov     [rsp+238h+var_114], ecx
0x1400fdf3e  mov     ecx, [rax+0Ch]
0x1400fdf41  mov     [rsp+238h+var_110], ecx
0x1400fdf48  mov     ecx, [rax+8]
0x1400fdf4b  shr     r14d, 2
0x1400fdf4f  shr     r15d, 2
0x1400fdf53  and     r14d, 1
0x1400fdf57  shr     r12d, 1
0x1400fdf5a  and     r15w, 3Fh
0x1400fdf5f  mov     [rsp+238h+var_10C], ecx
0x1400fdf66  and     r12d, 1
0x1400fdf6a  mov     ecx, [rax+4]
0x1400fdf6d  mov     eax, [rax]
0x1400fdf6f  mov     [rsp+238h+var_104], eax
0x1400fdf76  mov     rax, [rbx+8]
0x1400fdf7a  mov     [rsp+238h+var_E0], rax
0x1400fdf82  mov     eax, [rbp+38h]
0x1400fdf85  mov     [rsp+238h+var_100], eax
0x1400fdf8c  mov     eax, [rbp+24h]
0x1400fdf8f  mov     [rsp+238h+var_FC], eax
0x1400fdf96  mov     eax, [rbp+30h]
0x1400fdf99  mov     [rsp+238h+var_F8], eax
0x1400fdfa0  mov     eax, [rbp+28h]
0x1400fdfa3  mov     [rsp+238h+var_F4], eax
0x1400fdfaa  mov     eax, [rbp+20h]
0x1400fdfad  mov     [rsp+238h+var_F0], eax
0x1400fdfb4  mov     rax, [rbp+10h]
0x1400fdfb8  mov     [rsp+238h+var_D8], rax
0x1400fdfc0  mov     eax, [rdx]
0x1400fdfc2  mov     [rsp+238h+var_EC], eax
0x1400fdfc9  mov     rax, [rdi+18h]
0x1400fdfcd  mov     [rsp+238h+var_D0], rax
0x1400fdfd5  mov     [rsp+238h+var_108], ecx
0x1400fdfdc  test    r13, r13
0x1400fdfdf  jnz     short loc_1400FE02F
0x1400fdfe1  xor     esi, esi
0x1400fdfe3  jmp     short loc_1400FE033
0x1400fdfe5  test    ecx, ecx
0x1400fdfe7  jns     loc_1400FDE91
0x1400fdfed  mov     r9, [rbx+168h]
0x1400fdff4  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400fdffb  movsxd  rcx, dword ptr [r9]
0x1400fdffe  mov     dword ptr [rax], 1
0x1400fe004  mov     [rsp+238h+var_210], r12
0x1400fe009  mov     edx, 10Eh
0x1400fe00e  mov     qword ptr [rsp+238h+var_218], rcx
0x1400fe013  xor     ecx, ecx
0x1400fe015  lea     r8d, [rcx+42h]
0x1400fe019  call    cs:__imp_WdLogSingleEntry5
0x1400fe020  nop     dword ptr [rax+rax+00h]
0x1400fe025  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400fe02f  mov     rsi, [r13+18h]
0x1400fe033  call    cs:__imp_PsGetCurrentProcessId
0x1400fe03a  nop     dword ptr [rax+rax+00h]
0x1400fe03f  mov     rcx, [rsp+238h+var_E8]
0x1400fe047  lea     rdx, EventDestroyAdapterAllocation
0x1400fe04e  mov     [rsp+238h+var_138], rcx
0x1400fe056  mov     r9, rax
0x1400fe059  mov     ecx, [rsp+238h+var_128]
0x1400fe060  mov     [rsp+238h+var_140], r14d
0x1400fe068  mov     [rsp+238h+var_148], r15w
0x1400fe071  mov     [rsp+238h+var_150], 0
0x1400fe07d  mov     [rsp+238h+var_158], r12d
0x1400fe085  mov     [rsp+238h+var_160], ecx
0x1400fe08c  mov     ecx, [rsp+238h+var_124]
0x1400fe093  mov     [rsp+238h+var_168], ecx
0x1400fe09a  mov     ecx, [rsp+238h+var_120]
0x1400fe0a1  mov     [rsp+238h+var_170], ecx
0x1400fe0a8  mov     ecx, [rsp+238h+var_11C]
0x1400fe0af  mov     [rsp+238h+var_178], ecx
0x1400fe0b6  mov     ecx, [rsp+238h+var_118]
0x1400fe0bd  mov     [rsp+238h+var_180], ecx
0x1400fe0c4  mov     ecx, [rsp+238h+var_114]
0x1400fe0cb  mov     [rsp+238h+var_188], ecx
0x1400fe0d2  mov     ecx, [rsp+238h+var_110]
0x1400fe0d9  mov     [rsp+238h+var_190], ecx
0x1400fe0e0  mov     ecx, [rsp+238h+var_10C]
0x1400fe0e7  mov     [rsp+238h+var_198], ecx
0x1400fe0ee  mov     ecx, [rsp+238h+var_108]
0x1400fe0f5  mov     [rsp+238h+var_1A0], ecx
0x1400fe0fc  mov     ecx, [rsp+238h+var_104]
0x1400fe103  mov     [rsp+238h+var_1A8], ecx
0x1400fe10a  mov     rcx, [rsp+238h+var_E0]
0x1400fe112  mov     [rsp+238h+var_1B8], rcx
0x1400fe11a  mov     ecx, [rsp+238h+var_100]
0x1400fe121  mov     [rsp+238h+var_1C0], rbx
0x1400fe126  mov     [rsp+238h+var_1C8], ecx
0x1400fe12a  mov     ecx, [rsp+238h+var_FC]
0x1400fe131  mov     [rsp+238h+var_1D0], ecx
0x1400fe135  mov     ecx, [rsp+238h+var_F8]
0x1400fe13c  mov     [rsp+238h+var_1E0], ecx
0x1400fe140  mov     ecx, [rsp+238h+var_F4]
0x1400fe147  mov     [rsp+238h+var_1E8], ecx
0x1400fe14b  mov     ecx, [rsp+238h+var_F0]
0x1400fe152  mov     [rsp+238h+var_1F8], ecx
0x1400fe156  mov     rcx, [rsp+238h+var_D8]
0x1400fe15e  mov     [rsp+238h+var_200], rcx
0x1400fe163  mov     ecx, [rsp+238h+var_EC]
0x1400fe16a  mov     [rsp+238h+var_208], ecx
0x1400fe16e  mov     rcx, [rsp+238h+var_D0]
0x1400fe176  mov     [rsp+238h+var_210], rcx
0x1400fe17b  mov     qword ptr [rsp+238h+var_218], rsi
0x1400fe180  call    McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer
0x1400fe185  xor     r12d, r12d
0x1400fe188  mov     rax, [rbp+10h]
0x1400fe18c  lock inc dword ptr [rdi+0EC0h]
0x1400fe193  lock add [rdi+0EC8h], rax
0x1400fe19b  mov     rax, [rbx+188h]
0x1400fe1a2  mov     rdx, [rbp+10h]
0x1400fe1a6  test    dword ptr [rax], 20000000h
0x1400fe1ac  lea     rax, [rdi+0F40h]
0x1400fe1b3  jnz     short loc_1400FE1BC
  ... truncated ...
```
