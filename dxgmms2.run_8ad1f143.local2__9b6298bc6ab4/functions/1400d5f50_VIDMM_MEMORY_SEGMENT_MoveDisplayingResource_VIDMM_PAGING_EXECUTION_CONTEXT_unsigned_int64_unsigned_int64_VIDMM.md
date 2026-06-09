# VIDMM_MEMORY_SEGMENT::MoveDisplayingResource(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DISPLAYING_BLOCK const *)

- ea: `0x1400d5f50`
- end: `0x1400d62f0`
- name: `?MoveDisplayingResource@VIDMM_MEMORY_SEGMENT@@QEAA_KPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1PEBUVIDMM_DISPLAYING_BLOCK@@@Z`
- size: `928`
- prototype: `unsigned __int64 __usercall@<rax>(VIDMM_MEMORY_SEGMENT *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, const struct VIDMM_DISPLAYING_BLOCK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1400d5790`

## callees

- `0x1400045ec`
- `0x14002faf0`
- `0x14002fd70`
- `0x14003ba24`
- `0x14003c554`
- `0x14009f87c`
- `0x1400b9358`
- `0x1400d080c`
- `0x1400d5f50`
- `0x1400d6c94`
- `0x1400d6da4`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d62b9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d62b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d62c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d62c5`
- `watchdog!WdLogSingleEntry3` at `0x1400d61b9`
- `watchdog!WdLogSingleEntry3` at `0x1400d61b9`
- `watchdog!WdLogSingleEntry2` at `0x1400d6000`
- `watchdog!WdLogSingleEntry2` at `0x1400d6000`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d60b5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d60b5`
- `watchdog!WdLogSingleEntry0` at `0x1400d6104`
- `watchdog!WdLogSingleEntry0` at `0x1400d6104`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400d60a9`

## string_xrefs

- `0x1400d6113`: `Unable to find a contiguous region in memory as a temporary location for displaying resource.`

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
        WdLogGlobalForLineNumber = 3147;
      }
      if ( (int)VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(
                  this[32],
                  (const struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *)v35,
                  0,
                  &v25,
                  &v26) < 0 )
      {
        v18 = (char *)v27 + v9;
        _InterlockedIncrement(&dword_14008681C);
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 3171;
        DxgkLogInternalTriageEvent(
          v19,
          262145,
          v20,
          (unsigned int)L"Unable to find a contiguous region in memory as a temporary location for displaying resource.",
          3171,
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
    WdLogGlobalForLineNumber = 3197;
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
    WdLogGlobalForLineNumber = 3106;
    MoveAndFlipDisplayingAllocation(a2, *v13, *((_QWORD *)v5 + 2));
  }
  **((_QWORD **)v8 + 16) = *v14;
  *((_QWORD *)v8 + 18) = *v14;
  *(_QWORD *)(*(_QWORD *)(v33 + 384) + 40LL) = (char *)this[3] + *v14;
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
0x1400d5f50  mov     rax, rsp
0x1400d5f53  mov     [rax+10h], rbx
0x1400d5f57  mov     [rax+20h], r9
0x1400d5f5b  mov     [rax+18h], r8
0x1400d5f5f  push    rbp
0x1400d5f60  push    rsi
0x1400d5f61  push    rdi
0x1400d5f62  push    r12
0x1400d5f64  push    r13
0x1400d5f66  push    r14
0x1400d5f68  push    r15
0x1400d5f6a  lea     rbp, [rax-57h]
0x1400d5f6e  sub     rsp, 0D0h
0x1400d5f75  mov     r12, [rbp+4Fh+arg_20]
0x1400d5f79  mov     r13, rdx
0x1400d5f7c  mov     [rbp+4Fh+arg_0], 0
0x1400d5f80  mov     rsi, rcx
0x1400d5f83  mov     r8b, 1; bool
0x1400d5f86  lea     rcx, [rbp+4Fh+var_90]; this
0x1400d5f8a  mov     rdi, [r12]
0x1400d5f8e  mov     r14, [r12+8]
0x1400d5f93  mov     rbx, [rdi]
0x1400d5f96  mov     rax, [rdi+10h]
0x1400d5f9a  mov     [rbp+4Fh+var_80], rbx
0x1400d5f9e  mov     [rbp+4Fh+var_A0], rax
0x1400d5fa2  lea     rdx, [rbx+140h]; struct DXGPUSHLOCKFAST *
0x1400d5fa9  call    ??0DXGAUTOPUSHLOCKFASTSHARED@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTSHARED::DXGAUTOPUSHLOCKFASTSHARED(DXGPUSHLOCKFAST &,bool)
0x1400d5fae  lea     rdx, [rbx+88h]; struct DXGFASTMUTEX *
0x1400d5fb5  xor     r8d, r8d; unsigned __int8
0x1400d5fb8  lea     rcx, [rbp+4Fh+var_78]; this
0x1400d5fbc  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1400d5fc1  lea     rcx, [rbp+4Fh+var_78]; this
0x1400d5fc5  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1400d5fca  mov     rdx, rbx; struct VIDMM_GLOBAL_ALLOC *
0x1400d5fcd  call    ?SuspendSchedulerDeviceForMove@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::SuspendSchedulerDeviceForMove(VIDMM_GLOBAL_ALLOC *)
0x1400d5fd2  xor     edx, edx
0x1400d5fd4  lea     r15, [rsi+8]
0x1400d5fd8  cmp     [r12+18h], dl
0x1400d5fdd  jnz     short loc_1400D6039
0x1400d5fdf  mov     rax, [r15]
0x1400d5fe2  test    dword ptr [rax+0C48h], 40000h
0x1400d5fec  jnz     short loc_1400D6039
0x1400d5fee  mov     rdx, [r12+8]
0x1400d5ff3  lea     rbx, [r12+10h]
0x1400d5ff8  mov     r8, [rbx]
0x1400d5ffb  mov     ecx, 4
0x1400d6000  call    cs:__imp_WdLogSingleEntry2
0x1400d6007  nop     dword ptr [rax+rax+00h]
0x1400d600c  mov     cs:WdLogGlobalForLineNumber, 0C22h
0x1400d6016  mov     r8, rdi
0x1400d6019  mov     rax, [rbx]
0x1400d601c  mov     rcx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400d601f  mov     r9, [r12+8]
0x1400d6024  mov     rdx, [r15]; this
0x1400d6027  mov     [rsp+100h+var_E0], rax; __int64
0x1400d602c  call    MoveAndFlipDisplayingAllocation
0x1400d6031  xor     r15d, r15d
0x1400d6034  jmp     loc_1400D625E
0x1400d6039  mov     rcx, [rdi+10h]
0x1400d603d  lea     rbx, [r12+10h]
0x1400d6042  mov     rax, [rbp+4Fh+arg_10]
0x1400d6046  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64 *
0x1400d604a  mov     [rbp+4Fh+var_68], rax
0x1400d604e  mov     r8b, 1; bool
0x1400d6051  mov     rax, [rbp+4Fh+arg_18]
0x1400d6055  mov     [rbp+4Fh+var_60], rax
0x1400d6059  mov     eax, [rdi+20h]
0x1400d605c  mov     [rbp+4Fh+var_50], rax
0x1400d6060  lea     rax, ?VidMmiIsSaveableResource@@YA_NPEBUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VidMmiIsSaveableResource(VIDMM_PHYSICAL_ALLOC_LEGACY const *)
0x1400d6067  mov     [rbp+4Fh+var_48], rax
0x1400d606b  mov     rax, [rbx]
0x1400d606e  mov     [rbp+4Fh+var_40], rax
0x1400d6072  add     rax, rcx
0x1400d6075  mov     [rbp+4Fh+var_38], rax
0x1400d6079  lea     rax, [rbp+4Fh+var_A8]
0x1400d607d  mov     byte ptr [rbp+4Fh+arg_20], dl
0x1400d6080  mov     [rbp+4Fh+var_B0], rdx
0x1400d6084  mov     [rbp+4Fh+var_A8], rdx
0x1400d6088  lea     rdx, [rbp+4Fh+var_68]; struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *
0x1400d608c  mov     [rbp+4Fh+var_58], rcx
0x1400d6090  mov     rcx, [rsi+100h]; this
0x1400d6097  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1400d609c  call    ?FindTemporarySegmentLocationForResource@VIDMM_LINEAR_POOL@@QEAAJPEBUVIDMM_FIND_TEMPORARY_LOCATION_ARGS@@_NPEA_K2@Z; VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(VIDMM_FIND_TEMPORARY_LOCATION_ARGS const *,bool,unsigned __int64 *,unsigned __int64 *)
0x1400d60a1  test    eax, eax
0x1400d60a3  jns     loc_1400D61A5
0x1400d60a9  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400d60b0  cmp     byte ptr [rax], 0
0x1400d60b3  jz      short loc_1400D60CB
0x1400d60b5  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400d60bc  nop     dword ptr [rax+rax+00h]
0x1400d60c1  mov     cs:WdLogGlobalForLineNumber, 0C4Bh
0x1400d60cb  mov     rcx, [rsi+100h]; this
0x1400d60d2  lea     rax, [rbp+4Fh+var_A8]
0x1400d60d6  lea     r9, [rbp+4Fh+var_B0]; unsigned __int64 *
0x1400d60da  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1400d60df  xor     r8d, r8d; bool
0x1400d60e2  lea     rdx, [rbp+4Fh+var_68]; struct VIDMM_FIND_TEMPORARY_LOCATION_ARGS *
0x1400d60e6  call    ?FindTemporarySegmentLocationForResource@VIDMM_LINEAR_POOL@@QEAAJPEBUVIDMM_FIND_TEMPORARY_LOCATION_ARGS@@_NPEA_K2@Z; VIDMM_LINEAR_POOL::FindTemporarySegmentLocationForResource(VIDMM_FIND_TEMPORARY_LOCATION_ARGS const *,bool,unsigned __int64 *,unsigned __int64 *)
0x1400d60eb  xor     ecx, ecx
0x1400d60ed  test    eax, eax
0x1400d60ef  jns     short loc_1400D6148
0x1400d60f1  mov     rbx, [rbp+4Fh+var_A0]
0x1400d60f5  add     rbx, r14
0x1400d60f8  lock inc cs:dword_14008681C
0x1400d60ff  mov     ecx, 6
0x1400d6104  call    cs:__imp_WdLogSingleEntry0
0x1400d610b  nop     dword ptr [rax+rax+00h]
0x1400d6110  xor     r15d, r15d
0x1400d6113  lea     r9, aUnableToFindAC; "Unable to find a contiguous region in m"...
0x1400d611a  mov     [rsp+100h+var_C8], r15
0x1400d611f  mov     eax, 0C63h
0x1400d6124  mov     [rsp+100h+var_D0], r15
0x1400d6129  mov     edx, 40001h
0x1400d612e  mov     [rsp+100h+var_D8], r15
0x1400d6133  mov     [rsp+100h+var_E0], rax
0x1400d6138  mov     cs:WdLogGlobalForLineNumber, eax
0x1400d613e  call    DxgkLogInternalTriageEvent
0x1400d6143  jmp     loc_1400D62A0
0x1400d6148  mov     r14, [rbp+4Fh+var_B0]
0x1400d614c  lea     rax, ?SaveResourceCB@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::SaveResourceCB(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400d6153  mov     r9, [rbp+4Fh+var_A8]
0x1400d6157  mov     r8, r14
0x1400d615a  mov     [rbp+4Fh+var_A0], rax
0x1400d615e  mov     rdx, r13
0x1400d6161  mov     eax, [rbp+4Fh+var_84]
0x1400d6164  mov     [rbp+4Fh+var_94], eax
0x1400d6167  lea     rax, [rbp+4Fh+arg_0]
0x1400d616b  mov     [rsp+48h], rax
0x1400d6170  lea     rax, [rbp+4Fh+arg_20]
0x1400d6174  mov     [rsp+100h+var_C0], rax
0x1400d6179  lea     rax, [rbp+4Fh+var_A0]
0x1400d617d  mov     [rsp+100h+var_C8], rcx
0x1400d6182  mov     [rsp+100h+var_D0], rsi
0x1400d6187  mov     [rsp+100h+var_D8], rax
0x1400d618c  mov     dword ptr [rsp+100h+var_E0], ecx
0x1400d6190  mov     [rbp+4Fh+var_98], ecx
0x1400d6193  mov     rcx, [rsi+100h]
0x1400d619a  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400d619f  mov     byte ptr [rbp+4Fh+arg_20], 1
0x1400d61a3  jmp     short loc_1400D61A9
0x1400d61a5  mov     r14, [rbp+4Fh+var_B0]
0x1400d61a9  mov     r9, [rbx]
0x1400d61ac  mov     r8, r14
0x1400d61af  mov     rdx, [r12+8]
0x1400d61b4  mov     ecx, 4
0x1400d61b9  call    cs:__imp_WdLogSingleEntry3
0x1400d61c0  nop     dword ptr [rax+rax+00h]
0x1400d61c5  mov     cs:WdLogGlobalForLineNumber, 0C7Dh
0x1400d61cf  mov     r8, rdi
0x1400d61d2  mov     r9, [r12+8]
0x1400d61d7  mov     rcx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400d61da  mov     rdx, [r15]; this
0x1400d61dd  mov     [rsp+100h+var_E0], r14; __int64
0x1400d61e2  call    MoveAndFlipDisplayingAllocation
0x1400d61e7  mov     rax, [rbx]
0x1400d61ea  mov     r9, r14
0x1400d61ed  mov     rdx, [r15]; this
0x1400d61f0  mov     r8, rdi
0x1400d61f3  mov     rcx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400d61f6  mov     [rsp+100h+var_E0], rax; __int64
0x1400d61fb  call    MoveAndFlipDisplayingAllocation
0x1400d6200  xor     r15d, r15d
0x1400d6203  cmp     byte ptr [rbp+4Fh+arg_20], r15b
0x1400d6207  jz      short loc_1400D625E
0x1400d6209  mov     r9, [rbp+4Fh+var_A8]
0x1400d620d  lea     rax, ?RestoreResourceCB@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::RestoreResourceCB(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400d6214  mov     rcx, [rsi+100h]
0x1400d621b  mov     r8, r14
0x1400d621e  mov     [rbp+4Fh+var_A0], rax
0x1400d6222  mov     rdx, r13
0x1400d6225  mov     eax, [rbp+4Fh+var_84]
0x1400d6228  mov     [rbp+4Fh+var_94], eax
0x1400d622b  lea     rax, [rbp+4Fh+arg_0]
0x1400d622f  mov     [rsp+48h], rax
0x1400d6234  lea     rax, [rbp+4Fh+arg_20]
0x1400d6238  mov     [rsp+100h+var_C0], rax
0x1400d623d  lea     rax, [rbp+4Fh+var_A0]
0x1400d6241  mov     [rsp+100h+var_C8], r15
0x1400d6246  mov     [rsp+100h+var_D0], rsi
0x1400d624b  mov     [rsp+100h+var_D8], rax
0x1400d6250  mov     dword ptr [rsp+100h+var_E0], r15d
0x1400d6255  mov     [rbp+4Fh+var_98], r15d
0x1400d6259  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400d625e  mov     rax, [rbx]
0x1400d6261  mov     r8, rdi; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400d6264  mov     rcx, [rdi+80h]
0x1400d626b  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400d626e  mov     [rcx], rax
0x1400d6271  mov     rax, [rbx]
0x1400d6274  mov     [rdi+90h], rax
0x1400d627b  mov     rcx, [rsi+18h]
0x1400d627f  add     rcx, [rbx]
0x1400d6282  mov     rax, [rbp+4Fh+var_80]
0x1400d6286  mov     rax, [rax+180h]
0x1400d628d  mov     [rax+28h], rcx
0x1400d6291  mov     rcx, rsi; this
0x1400d6294  mov     rbx, [rbx]
0x1400d6297  add     rbx, [rdi+10h]
0x1400d629b  call    ?UpdateVirtualAddressForNewResourceLocation@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@@Z; VIDMM_SEGMENT::UpdateVirtualAddressForNewResourceLocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *)
0x1400d62a0  lea     rcx, [rbp+4Fh+var_78]; this
0x1400d62a4  call    ??1DXGAUTOMUTEX@@QEAA@XZ; DXGAUTOMUTEX::~DXGAUTOMUTEX(void)
0x1400d62a9  cmp     [rbp+4Fh+var_88], r15b
0x1400d62ad  jz      short loc_1400D62D1
0x1400d62af  mov     rcx, [rbp+4Fh+var_90]
0x1400d62b3  xor     edx, edx
0x1400d62b5  lock dec dword ptr [rcx+10h]
0x1400d62b9  call    cs:__imp_ExReleasePushLockSharedEx
0x1400d62c0  nop     dword ptr [rax+rax+00h]
0x1400d62c5  call    cs:__imp_KeLeaveCriticalRegion
0x1400d62cc  nop     dword ptr [rax+rax+00h]
0x1400d62d1  mov     rax, rbx
0x1400d62d4  mov     rbx, [rsp+100h+arg_8]
0x1400d62dc  add     rsp, 0D0h
0x1400d62e3  pop     r15
0x1400d62e5  pop     r14
0x1400d62e7  pop     r13
0x1400d62e9  pop     r12
0x1400d62eb  pop     rdi
0x1400d62ec  pop     rsi
0x1400d62ed  pop     rbp
0x1400d62ee  retn
```
