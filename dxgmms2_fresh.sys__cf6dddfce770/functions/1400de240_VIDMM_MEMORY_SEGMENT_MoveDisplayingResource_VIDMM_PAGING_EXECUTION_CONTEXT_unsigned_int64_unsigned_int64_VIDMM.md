# VIDMM_MEMORY_SEGMENT::MoveDisplayingResource(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DISPLAYING_BLOCK const *)

- ea: `0x1400de240`
- end: `0x1400de5e0`
- name: `?MoveDisplayingResource@VIDMM_MEMORY_SEGMENT@@QEAA_KPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1PEBUVIDMM_DISPLAYING_BLOCK@@@Z`
- size: `928`
- prototype: `unsigned __int64 __usercall@<rax>(VIDMM_MEMORY_SEGMENT *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, const struct VIDMM_DISPLAYING_BLOCK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1400dda80`

## callees

- `0x140004268`
- `0x14002d810`
- `0x14002da90`
- `0x14003a734`
- `0x14003b264`
- `0x1400a0a18`
- `0x1400bcd40`
- `0x1400d782c`
- `0x1400de240`
- `0x1400df0f4`
- `0x1400df204`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400de5a9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400de5a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400de5b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400de5b5`
- `watchdog!WdLogSingleEntry3` at `0x1400de4a9`
- `watchdog!WdLogSingleEntry3` at `0x1400de4a9`
- `watchdog!WdLogSingleEntry2` at `0x1400de2f0`
- `watchdog!WdLogSingleEntry2` at `0x1400de2f0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400de3a5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400de3a5`
- `watchdog!WdLogSingleEntry0` at `0x1400de3f4`
- `watchdog!WdLogSingleEntry0` at `0x1400de3f4`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400de399`

## string_xrefs

- `0x1400de403`: `Unable to find a contiguous region in memory as a temporary location for displaying resource.`

## pseudocode

```c
char *__fastcall VIDMM_MEMORY_SEGMENT::MoveDisplayingResource(
        VIDMM_LINEAR_POOL **this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        __int64 a3,
        __int64 a4,
        const struct VIDMM_DISPLAYING_BLOCK *a5)
{
  const struct VIDMM_DISPLAYING_BLOCK *v5; // r12
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v8; // rdi
  __int64 v9; // r14
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *); // rax
  VIDMM_GLOBAL *v12; // rcx
  VIDMM_GLOBAL **v13; // r15
  __int64 *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char *v18; // rbx
  int v19; // ecx
  int v20; // r8d
  unsigned __int64 v21; // r14
  VIDMM_LINEAR_POOL *v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v25; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 v26; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall *v27)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *); // [rsp+68h] [rbp-51h] BYREF
  int v28; // [rsp+70h] [rbp-49h]
  int v29; // [rsp+74h] [rbp-45h]
  __int64 v30; // [rsp+78h] [rbp-41h] BYREF
  char v31; // [rsp+80h] [rbp-39h]
  int v32; // [rsp+84h] [rbp-35h]
  __int64 v33; // [rsp+88h] [rbp-31h]
  _BYTE v34[16]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v35[5]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+Fh]
  __int64 v37; // [rsp+D0h] [rbp+17h]
  char v38; // [rsp+118h] [rbp+5Fh] BYREF
  __int64 v39; // [rsp+128h] [rbp+6Fh]
  __int64 v40; // [rsp+130h] [rbp+77h]

  v40 = a4;
  v39 = a3;
  v5 = a5;
  v38 = 0;
  v8 = *(struct VIDMM_PHYSICAL_ALLOC_LEGACY **)a5;
  v9 = *((_QWORD *)a5 + 1);
  v10 = **(_QWORD **)a5;
  v11 = *(__int64 (__fastcall **)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *))(*(_QWORD *)a5 + 16LL);
  v33 = v10;
  v27 = v11;
  DXGAUTOPUSHLOCKFASTSHARED::DXGAUTOPUSHLOCKFASTSHARED(
    (DXGAUTOPUSHLOCKFASTSHARED *)&v30,
    (struct DXGPUSHLOCKFAST *)(v10 + 320),
    1);
  DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)v34, (struct DXGFASTMUTEX *const)(v10 + 136), 0);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v34);
  VIDMM_GLOBAL::SuspendSchedulerDeviceForMove(v12, (struct VIDMM_GLOBAL_ALLOC *)v10);
  v13 = this + 1;
  if ( *((_BYTE *)v5 + 24) || (*((_DWORD *)*v13 + 786) & 0x40000) != 0 )
  {
    v15 = *((_QWORD *)v8 + 2);
    v14 = (__int64 *)((char *)v5 + 16);
    v35[0] = v39;
    v35[1] = v40;
    v35[3] = *((unsigned int *)v8 + 8);
    v35[4] = VidMmiIsSaveableResource;
    v36 = *((_QWORD *)v5 + 2);
    v37 = v15 + v36;
    LOBYTE(a5) = 0;
    v25 = 0;
    v26 = 0;
    v35[2] = v15;
    if ( (int)VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(
                this[32],
                (const struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *)v35,
                1,
                &v25,
                &v26) >= 0 )
    {
      v21 = v25;
    }
    else
    {
      if ( g_IsInternalReleaseOrDbg )
      {
        WdLogNewEntry5_WdTrace(v17, v16);
        WdLogGlobalForLineNumber = 3182;
      }
      if ( (int)VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(
                  this[32],
                  (const struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *)v35,
                  0,
                  &v25,
                  &v26) < 0 )
      {
        v18 = (char *)v27 + v9;
        _InterlockedIncrement(&dword_1400877FC);
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 3206;
        DxgkLogInternalTriageEvent(
          v19,
          262145,
          v20,
          (unsigned int)L"Unable to find a contiguous region in memory as a temporary location for displaying resource.",
          3206,
          0,
          0,
          0);
        goto LABEL_14;
      }
      v21 = v25;
      v27 = VIDMM_SEGMENT::SaveResourceCB;
      v29 = v32;
      v28 = 0;
      VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
        (unsigned int)this[32],
        (_DWORD)a2,
        v25,
        v26,
        0,
        (__int64)&v27,
        (__int64)this,
        0,
        (__int64)&a5,
        (__int64)&v38);
      LOBYTE(a5) = 1;
    }
    WdLogSingleEntry3(4, *((_QWORD *)v5 + 1), v21, *v14);
    WdLogGlobalForLineNumber = 3232;
    MoveAndFlipDisplayingAllocation(a2, *v13, v21);
    MoveAndFlipDisplayingAllocation(a2, *v13, *v14);
    if ( (_BYTE)a5 )
    {
      v22 = this[32];
      v27 = VIDMM_SEGMENT::RestoreResourceCB;
      v29 = v32;
      v28 = 0;
      VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
        (_DWORD)v22,
        (_DWORD)a2,
        v21,
        v26,
        0,
        (__int64)&v27,
        (__int64)this,
        0,
        (__int64)&a5,
        (__int64)&v38);
    }
  }
  else
  {
    v14 = (__int64 *)((char *)v5 + 16);
    WdLogSingleEntry2(4, *((_QWORD *)v5 + 1), *((_QWORD *)v5 + 2));
    WdLogGlobalForLineNumber = 3141;
    MoveAndFlipDisplayingAllocation(a2, *v13, *((_QWORD *)v5 + 2));
  }
  **((_QWORD **)v8 + 16) = *v14;
  *((_QWORD *)v8 + 18) = *v14;
  *(_QWORD *)(*(_QWORD *)(v33 + 392) + 40LL) = (char *)this[3] + *v14;
  v18 = (char *)(*((_QWORD *)v8 + 2) + *v14);
  VIDMM_SEGMENT::UpdateVirtualAddressForNewResourceLocation((VIDMM_SEGMENT *)this, a2, v8);
LABEL_14:
  DXGAUTOMUTEX::~DXGAUTOMUTEX((DXGAUTOMUTEX *)v34);
  if ( v31 )
  {
    v23 = v30;
    _InterlockedDecrement((volatile signed __int32 *)(v30 + 16));
    ExReleasePushLockSharedEx(v23, 0);
    KeLeaveCriticalRegion();
  }
  return v18;
}

```

## disassembly

```asm
0x1400de240  mov     rax, rsp
0x1400de243  mov     [rax+10h], rbx
0x1400de247  mov     [rax+20h], r9
0x1400de24b  mov     [rax+18h], r8
0x1400de24f  push    rbp
0x1400de250  push    rsi
0x1400de251  push    rdi
0x1400de252  push    r12
0x1400de254  push    r13
0x1400de256  push    r14
0x1400de258  push    r15
0x1400de25a  lea     rbp, [rax-57h]
0x1400de25e  sub     rsp, 0D0h
0x1400de265  mov     r12, [rbp+4Fh+arg_20]
0x1400de269  mov     r13, rdx
0x1400de26c  mov     [rbp+4Fh+arg_0], 0
0x1400de270  mov     rsi, rcx
0x1400de273  mov     r8b, 1; bool
0x1400de276  lea     rcx, [rbp+4Fh+var_90]; this
0x1400de27a  mov     rdi, [r12]
0x1400de27e  mov     r14, [r12+8]
0x1400de283  mov     rbx, [rdi]
0x1400de286  mov     rax, [rdi+10h]
0x1400de28a  mov     [rbp+4Fh+var_80], rbx
0x1400de28e  mov     [rbp+4Fh+var_A0], rax
0x1400de292  lea     rdx, [rbx+140h]; struct DXGPUSHLOCKFAST *
0x1400de299  call    ??0DXGAUTOPUSHLOCKFASTSHARED@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTSHARED::DXGAUTOPUSHLOCKFASTSHARED(DXGPUSHLOCKFAST &,bool)
0x1400de29e  lea     rdx, [rbx+88h]; struct DXGFASTMUTEX *
0x1400de2a5  xor     r8d, r8d; unsigned __int8
0x1400de2a8  lea     rcx, [rbp+4Fh+var_78]; this
0x1400de2ac  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1400de2b1  lea     rcx, [rbp+4Fh+var_78]; this
0x1400de2b5  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400de2ba  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400de2bd  call    ?SuspendSchedulerDeviceForMove@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::SuspendSchedulerDeviceForMove(VIDMM_GLOBAL_ALLOC *)
0x1400de2c2  xor     edx, edx
0x1400de2c4  lea     r15, [rsi+8]
0x1400de2c8  cmp     [r12+18h], dl
0x1400de2cd  jnz     short loc_1400DE329
0x1400de2cf  mov     rax, [r15]
0x1400de2d2  test    dword ptr [rax+0C48h], 40000h
0x1400de2dc  jnz     short loc_1400DE329
0x1400de2de  mov     rdx, [r12+8]
0x1400de2e3  lea     rbx, [r12+10h]
0x1400de2e8  mov     r8, [rbx]
0x1400de2eb  mov     ecx, 4
0x1400de2f0  call    cs:__imp_WdLogSingleEntry2
0x1400de2f7  nop     dword ptr [rax+rax+00h]
0x1400de2fc  mov     cs:WdLogGlobalForLineNumber, 0C45h
0x1400de306  mov     r8, rdi
0x1400de309  mov     rax, [rbx]
0x1400de30c  mov     rcx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400de30f  mov     r9, [r12+8]
0x1400de314  mov     rdx, [r15]; this
0x1400de317  mov     [rsp+100h+var_E0], rax; __int64
0x1400de31c  call    MoveAndFlipDisplayingAllocation
0x1400de321  xor     r15d, r15d
0x1400de324  jmp     loc_1400DE54E
0x1400de329  mov     rcx, [rdi+10h]
0x1400de32d  lea     rbx, [r12+10h]
0x1400de332  mov     rax, [rbp+4Fh+arg_10]
0x1400de336  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64 *
0x1400de33a  mov     [rbp+4Fh+var_68], rax
0x1400de33e  mov     r8b, 1; bool
0x1400de341  mov     rax, [rbp+4Fh+arg_18]
0x1400de345  mov     [rbp+4Fh+var_60], rax
0x1400de349  mov     eax, [rdi+20h]
0x1400de34c  mov     [rbp+4Fh+var_50], rax
0x1400de350  lea     rax, ?VidMmiIsSaveableResource@@YA_NPEBUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VidMmiIsSaveableResource(VIDMM_PHYSICAL_ALLOC_LEGACY const *)
0x1400de357  mov     [rbp+4Fh+var_48], rax
0x1400de35b  mov     rax, [rbx]
0x1400de35e  mov     [rbp+4Fh+var_40], rax
0x1400de362  add     rax, rcx
0x1400de365  mov     [rbp+4Fh+var_38], rax
0x1400de369  lea     rax, [rbp+4Fh+var_A8]
0x1400de36d  mov     byte ptr [rbp+4Fh+arg_20], dl
0x1400de370  mov     [rbp+4Fh+var_B0], rdx
0x1400de374  mov     [rbp+4Fh+var_A8], rdx
0x1400de378  lea     rdx, [rbp+4Fh+var_68]; struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *
0x1400de37c  mov     [rbp+4Fh+var_58], rcx
0x1400de380  mov     rcx, [rsi+100h]; this
0x1400de387  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1400de38c  call    ?FindTemporarySegmentLocationForResource@VIDMM_LINEAR_POOL@@QEAAJPEBUVIDMM_FIND_TEMPORARY_LOCATION_ARGS@@_NPEA_K2@Z; VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(VIDMM_FIND_TEMPORARY_LOCATION_ARGS const *,bool,unsigned __int64 *,unsigned __int64 *)
0x1400de391  test    eax, eax
0x1400de393  jns     loc_1400DE495
0x1400de399  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400de3a0  cmp     byte ptr [rax], 0
0x1400de3a3  jz      short loc_1400DE3BB
0x1400de3a5  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400de3ac  nop     dword ptr [rax+rax+00h]
0x1400de3b1  mov     cs:WdLogGlobalForLineNumber, 0C6Eh
0x1400de3bb  mov     rcx, [rsi+100h]; this
0x1400de3c2  lea     rax, [rbp+4Fh+var_A8]
0x1400de3c6  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64 *
0x1400de3ca  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1400de3cf  xor     r8d, r8d; bool
0x1400de3d2  lea     rdx, [rbp+4Fh+var_68]; struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *
0x1400de3d6  call    ?FindTemporarySegmentLocationForResource@VIDMM_LINEAR_POOL@@QEAAJPEBUVIDMM_FIND_TEMPORARY_LOCATION_ARGS@@_NPEA_K2@Z; VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(VIDMM_FIND_TEMPORARY_LOCATION_ARGS const *,bool,unsigned __int64 *,unsigned __int64 *)
0x1400de3db  xor     ecx, ecx
0x1400de3dd  test    eax, eax
0x1400de3df  jns     short loc_1400DE438
0x1400de3e1  mov     rbx, [rbp+4Fh+var_A0]
0x1400de3e5  add     rbx, r14
0x1400de3e8  lock inc cs:dword_1400877FC
0x1400de3ef  mov     ecx, 6
0x1400de3f4  call    cs:__imp_WdLogSingleEntry0
0x1400de3fb  nop     dword ptr [rax+rax+00h]
0x1400de400  xor     r15d, r15d
0x1400de403  lea     r9, aUnableToFindAC; "Unable to find a contiguous region in m"...
0x1400de40a  mov     [rsp+100h+var_C8], r15
0x1400de40f  mov     eax, 0C86h
0x1400de414  mov     [rsp+100h+var_D0], r15
0x1400de419  mov     edx, 40001h
0x1400de41e  mov     [rsp+100h+var_D8], r15
0x1400de423  mov     [rsp+100h+var_E0], rax
0x1400de428  mov     cs:WdLogGlobalForLineNumber, eax
0x1400de42e  call    DxgkLogInternalTriageEvent
0x1400de433  jmp     loc_1400DE590
0x1400de438  mov     r14, [rbp+4Fh+var_B0]
0x1400de43c  lea     rax, ?SaveResourceCB@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::SaveResourceCB(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400de443  mov     r9, [rbp+4Fh+var_A8]
0x1400de447  mov     r8, r14
0x1400de44a  mov     [rbp+4Fh+var_A0], rax
0x1400de44e  mov     rdx, r13
0x1400de451  mov     eax, [rbp+4Fh+var_84]
0x1400de454  mov     [rbp+4Fh+var_94], eax
0x1400de457  lea     rax, [rbp+4Fh+arg_0]
0x1400de45b  mov     [rsp+48h], rax
0x1400de460  lea     rax, [rbp+4Fh+arg_20]
0x1400de464  mov     [rsp+100h+var_C0], rax
0x1400de469  lea     rax, [rbp+4Fh+var_A0]
0x1400de46d  mov     [rsp+100h+var_C8], rcx
0x1400de472  mov     [rsp+100h+var_D0], rsi
0x1400de477  mov     [rsp+100h+var_D8], rax
0x1400de47c  mov     dword ptr [rsp+100h+var_E0], ecx
0x1400de480  mov     [rbp+4Fh+var_98], ecx
0x1400de483  mov     rcx, [rsi+100h]
0x1400de48a  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400de48f  mov     byte ptr [rbp+4Fh+arg_20], 1
0x1400de493  jmp     short loc_1400DE499
0x1400de495  mov     r14, [rbp+4Fh+var_B0]
0x1400de499  mov     r9, [rbx]
0x1400de49c  mov     r8, r14
0x1400de49f  mov     rdx, [r12+8]
0x1400de4a4  mov     ecx, 4
0x1400de4a9  call    cs:__imp_WdLogSingleEntry3
0x1400de4b0  nop     dword ptr [rax+rax+00h]
0x1400de4b5  mov     cs:WdLogGlobalForLineNumber, 0CA0h
0x1400de4bf  mov     r8, rdi
0x1400de4c2  mov     r9, [r12+8]
0x1400de4c7  mov     rcx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400de4ca  mov     rdx, [r15]; this
0x1400de4cd  mov     [rsp+100h+var_E0], r14; __int64
0x1400de4d2  call    MoveAndFlipDisplayingAllocation
0x1400de4d7  mov     rax, [rbx]
0x1400de4da  mov     r9, r14
0x1400de4dd  mov     rdx, [r15]; this
0x1400de4e0  mov     r8, rdi
0x1400de4e3  mov     rcx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400de4e6  mov     [rsp+100h+var_E0], rax; __int64
0x1400de4eb  call    MoveAndFlipDisplayingAllocation
0x1400de4f0  xor     r15d, r15d
0x1400de4f3  cmp     byte ptr [rbp+4Fh+arg_20], r15b
0x1400de4f7  jz      short loc_1400DE54E
0x1400de4f9  mov     r9, [rbp+4Fh+var_A8]
0x1400de4fd  lea     rax, ?RestoreResourceCB@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::RestoreResourceCB(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400de504  mov     rcx, [rsi+100h]
0x1400de50b  mov     r8, r14
0x1400de50e  mov     [rbp+4Fh+var_A0], rax
0x1400de512  mov     rdx, r13
0x1400de515  mov     eax, [rbp+4Fh+var_84]
0x1400de518  mov     [rbp+4Fh+var_94], eax
0x1400de51b  lea     rax, [rbp+4Fh+arg_0]
0x1400de51f  mov     [rsp+48h], rax
0x1400de524  lea     rax, [rbp+4Fh+arg_20]
0x1400de528  mov     [rsp+100h+var_C0], rax
0x1400de52d  lea     rax, [rbp+4Fh+var_A0]
0x1400de531  mov     [rsp+100h+var_C8], r15
0x1400de536  mov     [rsp+100h+var_D0], rsi
0x1400de53b  mov     [rsp+100h+var_D8], rax
0x1400de540  mov     dword ptr [rsp+100h+var_E0], r15d
0x1400de545  mov     [rbp+4Fh+var_98], r15d
0x1400de549  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400de54e  mov     rax, [rbx]
0x1400de551  mov     r8, rdi; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400de554  mov     rcx, [rdi+80h]
0x1400de55b  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400de55e  mov     [rcx], rax
0x1400de561  mov     rax, [rbx]
0x1400de564  mov     [rdi+90h], rax
0x1400de56b  mov     rcx, [rsi+18h]
0x1400de56f  add     rcx, [rbx]
0x1400de572  mov     rax, [rbp+4Fh+var_80]
0x1400de576  mov     rax, [rax+188h]
0x1400de57d  mov     [rax+28h], rcx
0x1400de581  mov     rcx, rsi; this
0x1400de584  mov     rbx, [rbx]
0x1400de587  add     rbx, [rdi+10h]
0x1400de58b  call    ?UpdateVirtualAddressForNewResourceLocation@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VIDMM_SEGMENT::UpdateVirtualAddressForNewResourceLocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *)
0x1400de590  lea     rcx, [rbp+4Fh+var_78]; this
0x1400de594  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400de599  cmp     [rbp+4Fh+var_88], r15b
0x1400de59d  jz      short loc_1400DE5C1
0x1400de59f  mov     rcx, [rbp+4Fh+var_90]
0x1400de5a3  xor     edx, edx
0x1400de5a5  lock dec dword ptr [rcx+10h]
0x1400de5a9  call    cs:__imp_ExReleasePushLockSharedEx
0x1400de5b0  nop     dword ptr [rax+rax+00h]
0x1400de5b5  call    cs:__imp_KeLeaveCriticalRegion
0x1400de5bc  nop     dword ptr [rax+rax+00h]
0x1400de5c1  mov     rax, rbx
0x1400de5c4  mov     rbx, [rsp+100h+arg_8]
0x1400de5cc  add     rsp, 0D0h
0x1400de5d3  pop     r15
0x1400de5d5  pop     r14
0x1400de5d7  pop     r13
0x1400de5d9  pop     r12
0x1400de5db  pop     rdi
0x1400de5dc  pop     rsi
0x1400de5dd  pop     rbp
0x1400de5de  retn
```
