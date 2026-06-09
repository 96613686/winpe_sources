# VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)

- ea: `0x140102390`
- end: `0x140102a46`
- name: `?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z`
- size: `1718`
- prototype: `void __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_DEVICE *, struct VIDMM_GLOBAL_ALLOC *, bool)`
- caller_count: `9`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400997d4`
- `0x14009c1ac`
- `0x1400bc240`
- `0x1400bd81c`
- `0x1400bdbf8`
- `0x140101e68`
- `0x1401020cc`
- `0x140102378`
- `0x140103bfc`

## callees

- `0x14002ec00`
- `0x14002ed1c`
- `0x14003056c`
- `0x140030ae0`
- `0x140030d18`
- `0x1400327b8`
- `0x140037d38`
- `0x140038bcc`
- `0x140039acc`
- `0x14003ad30`
- `0x14003dfcc`
- `0x140044eb0`
- `0x140057e40`
- `0x140058680`
- `0x140058760`
- `0x140058ac0`
- `0x14009d444`
- `0x1400e0950`
- `0x1400e3458`
- `0x1400e5be4`
- `0x1400e84b4`
- `0x1400f16f0`
- `0x1400f1710`
- `0x140102390`
- `0x140102a4c`
- `0x140102e90`
- `0x140102eb4`
- `0x140108cd8`
- `0x14010db5c`
- `0x140113110`
- `0x1401186d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1401028c3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401028c3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401023dc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401023dc`
- `watchdog!WdLogSingleEntry5` at `0x1401027c1`
- `watchdog!WdLogSingleEntry5` at `0x1401027c1`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010279c`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14010274d`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14010274d`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1401023ba`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_GLOBAL::DestroyOneAllocation(
        VIDMM_GLOBAL *this,
        struct VIDMM_DEVICE *a2,
        struct VIDMM_GLOBAL_ALLOC *a3,
        char a4)
{
  __int64 v4; // r14
  __int64 v9; // rax
  bool v10; // si
  __int64 v11; // rax
  VIDMM_GLOBAL *v12; // rcx
  int v13; // r8d
  struct VIDMM_CROSSADAPTER_ALLOC *v14; // rdx
  __int64 v15; // rdx
  int *v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  char *v19; // rax
  struct VIDMM_GLOBAL_ALLOC_NONPAGED *v20; // rdx
  void *v21; // rdx
  __int64 v22; // rcx
  VIDMM_FLIP_QUEUE_REFERENCES *v23; // rcx
  unsigned int v24; // edx
  int v25; // eax
  bool v26; // r8
  __int64 v27; // r15
  VIDMM_PROCESS *v28; // rcx
  __int64 v29; // rsi
  unsigned int CurrentProcessId; // eax
  int v31; // r8d
  __int64 i; // rsi
  void *v33; // rcx
  int v34; // [rsp+28h] [rbp-168h]
  int v35; // [rsp+48h] [rbp-148h]
  int v36; // [rsp+60h] [rbp-130h]
  int v37; // [rsp+138h] [rbp-58h]
  int v38; // [rsp+13Ch] [rbp-54h]
  int v39; // [rsp+140h] [rbp-50h]
  int v40; // [rsp+144h] [rbp-4Ch]
  int v41; // [rsp+148h] [rbp-48h]
  int v42; // [rsp+14Ch] [rbp-44h]
  __int64 v44; // [rsp+160h] [rbp-30h]
  __int64 v45; // [rsp+168h] [rbp-28h]
  __int64 v46; // [rsp+170h] [rbp-20h]
  _BYTE v47[24]; // [rsp+178h] [rbp-18h] BYREF
  _QWORD v48[12]; // [rsp+190h] [rbp+0h] BYREF

  v4 = *(_QWORD *)a3;
  if ( g_IsInternalReleaseOrDbg )
  {
    v9 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v9 + 24) = a3;
    *(_QWORD *)(v9 + 32) = a2;
    WdLogGlobalForLineNumber = 4586;
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
      v25 = (*(_DWORD *)(v4 + 60) >> 2) & 0x3F;
      LODWORD(v48[0]) = 112;
      HIDWORD(v48[0]) = v25;
      v48[5] = a3;
      LODWORD(v48[6]) = 0;
      VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(this, (struct VIDMM_SYSTEM_COMMAND *)v48, v26);
      v10 = 0;
    }
    else
    {
      v10 = 1;
    }
    v27 = *(_QWORD *)(*((_QWORD *)a3 + 6) + 32LL);
    if ( (*((_DWORD *)a3 + 8) & 2) != 0 )
    {
      VIDMM_SEGMENT::UnlockAllocationBackingStore(this, a3, 0);
      VIDMM_GLOBAL::ReturnPinnedBackingStore(this, *(_QWORD *)(v4 + 16));
      *((_DWORD *)a3 + 8) &= ~2u;
    }
    v48[7] = *(_QWORD *)(*((_QWORD *)a3 + 6) + 8LL);
    LOBYTE(v48[0]) = 0;
    VIDMM_PROCESS::SafeAttach((VIDMM_PROCESS *)v48[7], (struct _KAPC_STATE *)&v48[1]);
    LOBYTE(v48[0]) = 1;
    VIDMM_GLOBAL::CloseOneAllocation(this, (struct VIDMM_ALLOC *)(v27 - 40), 0, 0, 0, 0);
    if ( LOBYTE(v48[0]) )
    {
      VIDMM_PROCESS::SafeDetach(v28, (struct _KAPC_STATE *)&v48[1]);
      LOBYTE(v48[0]) = 0;
    }
    *((_QWORD *)a3 + 6) = 0;
  }
  if ( v10 )
    VidMmSynchronizeWithWorkerThreadRun(*(const struct VIDMM_WORKER_THREAD **)this);
  if ( a4 )
    VIDMM_GLOBAL::WaitForAllPagingOperations(this, 0, a3);
  if ( (unsigned int)Feature_SystemCommitMdlLeakInstrumentation__private_IsEnabledDeviceUsageNoInline() )
  {
    v11 = *((_QWORD *)a3 + 7);
    if ( v11 )
    {
      LOBYTE(v34) = 5;
      DxgCreateLiveDumpWithWdLogs(403, 2083, this, a3, v11, v34);
    }
  }
  if ( (*((_DWORD *)a3 + 8) & 0x20) != 0 )
    VIDMM_GLOBAL::UncommitGlobalBackingStore(this, a3, 1);
  VidMmiClosePartition(**((struct VIDMM_PARTITION ***)a3 + 43));
  v14 = (struct VIDMM_CROSSADAPTER_ALLOC *)*((_QWORD *)a3 + 44);
  if ( !v14 )
  {
LABEL_15:
    v15 = *((_QWORD *)a3 + 48);
    if ( !*(_WORD *)(v15 + 8) )
      goto LABEL_16;
    goto LABEL_50;
  }
  VIDMM_GLOBAL::FreeCrossAdapterDataDpc(v12, v14, a3);
  v12 = (VIDMM_GLOBAL *)(unsigned int)_InterlockedDecrement(*((volatile signed __int32 **)a3 + 44));
  if ( !(_DWORD)v12 )
  {
    VIDMM_GLOBAL::DestroyCrossAdapterAllocation(v12, *((struct VIDMM_CROSSADAPTER_ALLOC **)a3 + 44));
LABEL_47:
    *((_QWORD *)a3 + 44) = 0;
    goto LABEL_15;
  }
  if ( (int)v12 >= 0 )
    goto LABEL_47;
  g_DxgMmsBugcheckExportIndex = 1;
  WdLogSingleEntry5(0, 270, 66);
  WdLogGlobalForLineNumber = 222;
LABEL_50:
  if ( (byte_140086201 & 1) != 0 )
    McTemplateK0puu_EtwWriteTransfer(
      (_DWORD)v12,
      (unsigned int)EventReportOfferAllocation,
      v13,
      (_DWORD)a3,
      *(_BYTE *)(v15 + 8),
      *((_BYTE *)a3 + 304));
LABEL_16:
  VidMmGetAllocationHint(a3);
  if ( (byte_140086201 & 0x10) != 0 )
  {
    LOBYTE(v29) = (_BYTE)a2;
    v44 = *((_QWORD *)a3 + 1);
    v37 = *(_DWORD *)(v4 + 56);
    v38 = *(_DWORD *)(v4 + 36);
    v39 = *(_DWORD *)(v4 + 48);
    v40 = *(_DWORD *)(v4 + 40);
    v41 = *(_DWORD *)(v4 + 32);
    v45 = *(_QWORD *)(v4 + 16);
    v42 = *v16;
    v46 = *((_QWORD *)this + 3);
    if ( a2 )
      v29 = *((_QWORD *)a2 + 3);
    CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
    McTemplateK0pppqxqqqqqqqpppqqqqqqqqqqtphtp_EtwWriteTransfer(
      v46,
      (unsigned int)EventDestroyAdapterAllocation,
      v31,
      CurrentProcessId,
      v29,
      v46,
      v42,
      v45,
      v41,
      v35,
      v40,
      v39,
      v36,
      v38,
      v37,
      (char)a3,
      v44);
  }
  v17 = *(_QWORD *)(v4 + 16);
  _InterlockedIncrement((volatile signed __int32 *)this + 944);
  _InterlockedAdd64((volatile signed __int64 *)this + 473, v17);
  v18 = *(_QWORD *)(v4 + 16);
  v19 = (char *)this + 3904;
  if ( (**((_DWORD **)a3 + 48) & 0x20000000) == 0 )
    v19 = (char *)this + 3920;
  _InterlockedIncrement((volatile signed __int32 *)v19);
  _InterlockedAdd64((volatile signed __int64 *)v19 + 1, v18);
  _InterlockedAdd64((volatile signed __int64 *)this + 4556, -*(_QWORD *)(v4 + 16));
  v20 = (struct VIDMM_GLOBAL_ALLOC_NONPAGED *)*((_QWORD *)a3 + 48);
  if ( v20 )
  {
    if ( *((_QWORD *)v20 + 4) )
    {
      VidSchiValidateAllocationNotDisplayed(*(struct _VIDSCH_GLOBAL **)(*((_QWORD *)this + 2) + 744LL), v20);
      for ( i = 0; i != 2; ++i )
      {
        v33 = *(void **)(*(_QWORD *)(*((_QWORD *)a3 + 48) + 32LL) + 8 * i);
        if ( v33 )
        {
          VidSchDestroySyncObject(v33);
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a3 + 48) + 32LL) + 8 * i) = 0;
        }
      }
      operator delete(*(void **)(*((_QWORD *)a3 + 48) + 32LL));
      *(_QWORD *)(*((_QWORD *)a3 + 48) + 32LL) = 0;
    }
    v23 = *(VIDMM_FLIP_QUEUE_REFERENCES **)(*((_QWORD *)a3 + 48) + 24LL);
    if ( v23 )
    {
      VIDMM_FLIP_QUEUE_REFERENCES::ReleaseReference(v23, (unsigned int)v20);
      *(_QWORD *)(*((_QWORD *)a3 + 48) + 24LL) = 0;
    }
  }
  v21 = (void *)*((_QWORD *)a3 + 45);
  if ( v21 )
    SysMmFreeLogicalMemory(*(struct SYSMM_ADAPTER **)(*((_QWORD *)this + 3) + 224LL), v21);
  if ( *(_QWORD *)a3 )
  {
    v22 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * ((*(_DWORD *)(v4 + 60) >> 2) & 0x3F));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
    *(_QWORD *)a3 = 0;
  }
  if ( *((_DWORD *)a3 + 62) )
  {
    *((_DWORD *)a3 + 6) |= 0x40000u;
  }
  else
  {
    operator delete(*((void **)a3 + 48));
    *((_DWORD *)a3 + 6) |= 0x20000u;
    VIDMM_GLOBAL_ALLOC::`scalar deleting destructor'(a3, v24);
  }
}

```

## disassembly

```asm
0x140102390  mov     [rsp-8+arg_18], rbx
0x140102395  push    rbp
0x140102396  push    rsi
0x140102397  push    rdi
0x140102398  push    r12
0x14010239a  push    r13
0x14010239c  push    r14
0x14010239e  push    r15
0x1401023a0  lea     rbp, [rsp-70h]
0x1401023a5  sub     rsp, 200h
0x1401023ac  mov     rax, cs:__security_cookie
0x1401023b3  xor     rax, rsp
0x1401023b6  mov     [rbp+0A0h+var_40], rax
0x1401023ba  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1401023c1  xor     r13d, r13d
0x1401023c4  mov     r14, [r8]
0x1401023c7  mov     r12b, r9b
0x1401023ca  mov     rbx, r8
0x1401023cd  mov     [rbp+0A0h+var_E0], rdx
0x1401023d1  mov     rsi, rdx
0x1401023d4  mov     rdi, rcx
0x1401023d7  cmp     [rax], r13b
0x1401023da  jz      short loc_1401023FA
0x1401023dc  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1401023e3  nop     dword ptr [rax+rax+00h]
0x1401023e8  mov     [rax+18h], rbx
0x1401023ec  mov     [rax+20h], rsi
0x1401023f0  mov     cs:WdLogGlobalForLineNumber, 11EAh
0x1401023fa  mov     eax, [rbx+18h]
0x1401023fd  mov     sil, r13b
0x140102400  test    al, 4
0x140102402  jz      loc_14010255E
0x140102408  mov     eax, [rbx+20h]
0x14010240b  test    al, 4
0x14010240d  jnz     loc_1401025F2
0x140102413  test    sil, sil
0x140102416  jnz     loc_140102714
0x14010241c  test    r12b, r12b
0x14010241f  jnz     loc_140102721
0x140102425  call    Feature_SystemCommitMdlLeakInstrumentation__private_IsEnabledDeviceUsageNoInline
0x14010242a  test    eax, eax
0x14010242c  jz      short loc_14010243B
0x14010242e  mov     rax, [rbx+38h]
0x140102432  test    rax, rax
0x140102435  jnz     loc_140102733
0x14010243b  mov     eax, [rbx+20h]
0x14010243e  test    al, 20h
0x140102440  jnz     loc_1401026AC
0x140102446  mov     rcx, [rbx+158h]
0x14010244d  mov     rcx, [rcx]; this
0x140102450  call    ?VidMmiClosePartition@@YAXPEAUVIDMM_PARTITION@@@Z; VidMmiClosePartition(VIDMM_PARTITION *)
0x140102455  mov     rdx, [rbx+160h]; struct VIDMM_CROSSADAPTER_ALLOC *
0x14010245c  test    rdx, rdx
0x14010245f  jnz     loc_14010275E
0x140102465  mov     rdx, [rbx+180h]
0x14010246c  cmp     [rdx+8], r13w
0x140102471  jnz     loc_1401027D7
0x140102477  mov     rcx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x14010247a  call    ?VidMmGetAllocationHint@@YAPEBU_DXGK_ALLOCATIONUSAGEHINT@@PEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetAllocationHint(VIDMM_GLOBAL_ALLOC const *)
0x14010247f  test    cs:byte_140086201, 10h
0x140102486  jnz     loc_140102810
0x14010248c  mov     rax, [r14+10h]
0x140102490  lock inc dword ptr [rdi+0EC0h]
0x140102497  lock add [rdi+0EC8h], rax
0x14010249f  mov     rax, [rbx+180h]
0x1401024a6  mov     rdx, [r14+10h]
0x1401024aa  test    dword ptr [rax], 20000000h
0x1401024b0  lea     rax, [rdi+0F40h]
0x1401024b7  jnz     short loc_1401024C0
0x1401024b9  lea     rax, [rdi+0F50h]
0x1401024c0  lock inc dword ptr [rax]
0x1401024c3  lock add [rax+8], rdx
0x1401024c8  mov     rax, [r14+10h]
0x1401024cc  neg     rax
0x1401024cf  lock add [rdi+8E60h], rax
0x1401024d7  mov     rdx, [rbx+180h]; struct VIDMM_GLOBAL_ALLOC_NONPAGED *
0x1401024de  test    rdx, rdx
0x1401024e1  jnz     loc_1401025A1
0x1401024e7  mov     rdx, [rbx+168h]; void *
0x1401024ee  test    rdx, rdx
0x1401024f1  jnz     loc_140102A31
0x1401024f7  mov     rdx, [rbx]
0x1401024fa  test    rdx, rdx
0x1401024fd  jz      short loc_140102524
0x1401024ff  mov     rax, [rdi+8E80h]
0x140102506  mov     ecx, [r14+3Ch]
0x14010250a  shr     rcx, 2
0x14010250e  and     ecx, 3Fh
0x140102511  mov     rcx, [rax+rcx*8]
0x140102515  mov     rax, [rcx]
0x140102518  mov     rax, [rax+28h]
0x14010251c  call    _guard_dispatch_icall
0x140102521  mov     [rbx], r13
0x140102524  cmp     [rbx+0F8h], r13d
0x14010252b  jz      loc_1401025D4
0x140102531  bts     dword ptr [rbx+18h], 12h
0x140102536  mov     rcx, [rbp+0A0h+var_40]
0x14010253a  xor     rcx, rsp; StackCookie
0x14010253d  call    __security_check_cookie
0x140102542  mov     rbx, [rsp+230h+arg_18]
0x14010254a  add     rsp, 200h
0x140102551  pop     r15
0x140102553  pop     r14
0x140102555  pop     r13
0x140102557  pop     r12
0x140102559  pop     rdi
0x14010255a  pop     rsi
0x14010255b  pop     rbp
0x14010255c  retn
0x14010255e  lea     rdx, [rdi+8E38h]; struct DXGPUSHLOCK *
0x140102565  lea     rcx, [rbp+0A0h+var_B8]; this
0x140102569  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x14010256e  cmp     [rbx+110h], r13
0x140102575  jnz     loc_1401026BF
0x14010257b  cmp     [rbx+120h], r13
0x140102582  jnz     loc_1401026CF
0x140102588  cmp     [rdi+0A1A8h], rbx
0x14010258f  lea     rcx, [rbp+0A0h+var_B8]; this
0x140102593  setz    sil
0x140102597  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14010259c  jmp     loc_140102408
0x1401025a1  cmp     [rdx+20h], r13
0x1401025a5  jnz     loc_1401029CD
0x1401025ab  mov     rax, [rbx+180h]
0x1401025b2  mov     rcx, [rax+18h]; this
0x1401025b6  test    rcx, rcx
0x1401025b9  jz      loc_1401024E7
0x1401025bf  call    ?ReleaseReference@VIDMM_FLIP_QUEUE_REFERENCES@@QEAAXI@Z; VIDMM_FLIP_QUEUE_REFERENCES::ReleaseReference(uint)
0x1401025c4  mov     rax, [rbx+180h]
0x1401025cb  mov     [rax+18h], r13
0x1401025cf  jmp     loc_1401024E7
0x1401025d4  mov     rcx, [rbx+180h]; void *
0x1401025db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1401025e0  bts     dword ptr [rbx+18h], 11h
0x1401025e5  mov     rcx, rbx; P
0x1401025e8  call    ??_GVIDMM_GLOBAL_ALLOC@@QEAAPEAXI@Z; VIDMM_GLOBAL_ALLOC::`scalar deleting destructor'(uint)
0x1401025ed  jmp     loc_140102536
0x1401025f2  mov     eax, [r14+40h]
0x1401025f6  test    al, 40h
0x1401025f8  jnz     loc_1401026DF
0x1401025fe  mov     eax, [r14+40h]
0x140102602  test    al, 41h
0x140102604  jz      loc_1401026E9
0x14010260a  xor     edx, edx; Val
0x14010260c  lea     rcx, [rbp+0A0h+var_A0]; void *
0x140102610  lea     r8d, [rdx+58h]; Size
0x140102614  call    memset
0x140102619  mov     eax, [r14+3Ch]
0x14010261d  lea     rdx, [rbp+0A0h+var_A0]; struct VIDMM_SYSTEM_COMMAND *
0x140102621  shr     eax, 2
0x140102624  mov     rcx, rdi; this
0x140102627  and     eax, 3Fh
0x14010262a  mov     [rbp+0A0h+var_A0], 70h ; 'p'
0x140102631  mov     [rbp+0A0h+var_9C], eax
0x140102634  mov     [rbp+0A0h+var_98.Process], rbx
0x140102638  mov     dword ptr [rbp+0A0h+var_98.28h], r13d
0x14010263c  call    ?QueueSystemCleanupCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x140102641  mov     sil, r13b
0x140102644  mov     rax, [rbx+30h]
0x140102648  mov     r15, [rax+20h]
0x14010264c  mov     eax, [rbx+20h]
0x14010264f  test    al, 2
0x140102651  jnz     loc_1401026F1
0x140102657  mov     rax, [rbx+30h]
0x14010265b  lea     rdx, [rbp+0A0h+var_98]; struct _KAPC_STATE *
0x14010265f  mov     rcx, [rax+8]; this
0x140102663  mov     [rbp+0A0h+var_68], rcx
0x140102667  mov     byte ptr [rbp+0A0h+var_A0], r13b
0x14010266b  call    ?SafeAttach@VIDMM_PROCESS@@QEAAXPEAU_KAPC_STATE@@@Z; VIDMM_PROCESS::SafeAttach(_KAPC_STATE *)
0x140102670  xor     r9d, r9d; bool
0x140102673  mov     [rsp+230h+var_208], r13; struct _KEVENT **
0x140102678  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x14010267b  mov     byte ptr [rbp+0A0h+var_A0], 1
0x14010267f  lea     rdx, [r15-28h]; struct VIDMM_ALLOC *
0x140102683  mov     dword ptr [rsp+230h+var_210], r13d; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x140102688  mov     rcx, rdi; this
0x14010268b  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x140102690  cmp     byte ptr [rbp+0A0h+var_A0], r13b
0x140102694  jz      short loc_1401026A3
0x140102696  lea     rdx, [rbp+0A0h+var_98]; struct _KAPC_STATE *
0x14010269a  call    ?SafeDetach@VIDMM_PROCESS@@QEAAXPEAU_KAPC_STATE@@@Z; VIDMM_PROCESS::SafeDetach(_KAPC_STATE *)
0x14010269f  mov     byte ptr [rbp+0A0h+var_A0], r13b
0x1401026a3  mov     [rbx+30h], r13
0x1401026a7  jmp     loc_140102413
0x1401026ac  mov     r8b, 1; bool
0x1401026af  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1401026b2  mov     rcx, rdi; this
0x1401026b5  call    ?UncommitGlobalBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::UncommitGlobalBackingStore(VIDMM_GLOBAL_ALLOC *,bool)
0x1401026ba  jmp     loc_140102446
0x1401026bf  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1401026c2  mov     rcx, rdi; this
0x1401026c5  call    ?RemoveAllocationFromOfferList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromOfferList(VIDMM_GLOBAL_ALLOC *)
0x1401026ca  jmp     loc_14010257B
0x1401026cf  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1401026d2  mov     rcx, rdi; this
0x1401026d5  call    ?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *)
0x1401026da  jmp     loc_140102588
0x1401026df  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1401026e4  jmp     loc_1401025FE
0x1401026e9  mov     sil, 1
0x1401026ec  jmp     loc_140102644
0x1401026f1  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1401026f4  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1401026f7  mov     rcx, rdi; this
0x1401026fa  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1401026ff  mov     rdx, [r14+10h]; unsigned __int64
0x140102703  mov     rcx, rdi; this
0x140102706  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x14010270b  and     dword ptr [rbx+20h], 0FFFFFFFDh
0x14010270f  jmp     loc_140102657
0x140102714  mov     rcx, [rdi]; struct VIDMM_WORKER_THREAD *
0x140102717  call    ?VidMmSynchronizeWithWorkerThreadRun@@YAXPEBUVIDMM_WORKER_THREAD@@@Z; VidMmSynchronizeWithWorkerThreadRun(VIDMM_WORKER_THREAD const *)
0x14010271c  jmp     loc_14010241C
0x140102721  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x140102724  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x140102726  mov     rcx, rdi; this
0x140102729  call    ?WaitForAllPagingOperations@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingOperations(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x14010272e  jmp     loc_140102425
0x140102733  mov     byte ptr [rsp+230h+var_208], 5
0x140102738  mov     r9, rbx
0x14010273b  mov     r8, rdi
0x14010273e  mov     qword ptr [rsp+230h+var_210], rax
0x140102743  mov     edx, 823h
0x140102748  mov     ecx, 193h
0x14010274d  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x140102754  nop     dword ptr [rax+rax+00h]
0x140102759  jmp     loc_14010243B
0x14010275e  mov     r8, rbx; struct VIDMM_GLOBAL_ALLOC *
0x140102761  call    ?FreeCrossAdapterDataDpc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::FreeCrossAdapterDataDpc(VIDMM_CROSSADAPTER_ALLOC *,VIDMM_GLOBAL_ALLOC *)
0x140102766  mov     rax, [rbx+160h]
0x14010276d  or      ecx, 0FFFFFFFFh
0x140102770  lock xadd [rax], ecx
0x140102774  sub     ecx, 1; this
0x140102777  jnz     short loc_140102791
0x140102779  mov     rdx, [rbx+160h]; struct VIDMM_CROSSADAPTER_ALLOC *
0x140102780  call    ?DestroyCrossAdapterAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_CROSSADAPTER_ALLOC@@@Z; VIDMM_GLOBAL::DestroyCrossAdapterAllocation(VIDMM_CROSSADAPTER_ALLOC *)
0x140102785  mov     [rbx+160h], r13
0x14010278c  jmp     loc_140102465
0x140102791  test    ecx, ecx
0x140102793  jns     short loc_140102785
0x140102795  mov     r9, [rbx+160h]
0x14010279c  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1401027a3  movsxd  rcx, dword ptr [r9]
0x1401027a6  mov     dword ptr [rax], 1
0x1401027ac  mov     [rsp+230h+var_208], r13
0x1401027b1  mov     edx, 10Eh
0x1401027b6  mov     qword ptr [rsp+230h+var_210], rcx
0x1401027bb  xor     ecx, ecx
0x1401027bd  lea     r8d, [rcx+42h]
0x1401027c1  call    cs:__imp_WdLogSingleEntry5
0x1401027c8  nop     dword ptr [rax+rax+00h]
0x1401027cd  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1401027d7  test    cs:byte_140086201, 1
0x1401027de  jz      loc_140102477
0x1401027e4  mov     al, [rbx+130h]
0x1401027ea  mov     r9, rbx
0x1401027ed  mov     byte ptr [rsp+230h+var_208], al
0x1401027f1  mov     al, [rdx+8]
0x1401027f4  lea     rdx, EventReportOfferAllocation
0x1401027fb  mov     byte ptr [rsp+230h+var_210], al
0x1401027ff  call    McTemplateK0puu_EtwWriteTransfer
0x140102804  mov     rdx, [rbx+180h]
0x14010280b  jmp     loc_140102477
0x140102810  mov     rcx, [rbx]
0x140102813  mov     r15d, [rbx+18h]
0x140102817  mov     r12d, [r14+3Ch]
0x14010281b  mov     r13d, [rbx+20h]
0x14010281f  mov     rsi, [rbp+0A0h+var_E0]
0x140102823  mov     [rbp+0A0h+var_D8], rcx
0x140102827  mov     ecx, [rax+24h]
0x14010282a  mov     [rbp+0A0h+var_120], ecx
0x14010282d  mov     ecx, [rax+20h]
0x140102830  mov     [rbp+0A0h+var_11C], ecx
0x140102833  mov     ecx, [rax+1Ch]
0x140102836  mov     [rbp+0A0h+var_118], ecx
0x140102839  mov     ecx, [rax+18h]
0x14010283c  mov     [rbp+0A0h+var_114], ecx
0x14010283f  mov     ecx, [rax+14h]
0x140102842  mov     [rbp+0A0h+var_110], ecx
0x140102845  mov     ecx, [rax+10h]
0x140102848  mov     [rbp+0A0h+var_10C], ecx
0x14010284b  mov     ecx, [rax+0Ch]
0x14010284e  mov     [rbp+0A0h+var_108], ecx
0x140102851  mov     ecx, [rax+8]
0x140102854  shr     r15d, 2
0x140102858  shr     r12d, 2
0x14010285c  and     r15d, 1
0x140102860  shr     r13d, 1
0x140102863  and     r12w, 3Fh
0x140102868  mov     [rbp+0A0h+var_104], ecx
0x14010286b  and     r13d, 1
0x14010286f  mov     ecx, [rax+4]
0x140102872  mov     eax, [rax]
0x140102874  mov     [rbp+0A0h+var_FC], eax
0x140102877  mov     rax, [rbx+8]
0x14010287b  mov     [rbp+0A0h+var_D0], rax
0x14010287f  mov     eax, [r14+38h]
0x140102883  mov     [rbp+0A0h+var_F8], eax
0x140102886  mov     eax, [r14+24h]
0x14010288a  mov     [rbp+0A0h+var_F4], eax
  ... truncated ...
```
