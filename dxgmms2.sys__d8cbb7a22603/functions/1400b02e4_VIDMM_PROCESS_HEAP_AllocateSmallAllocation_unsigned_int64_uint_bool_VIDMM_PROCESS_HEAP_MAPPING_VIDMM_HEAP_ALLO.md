# VIDMM_PROCESS_HEAP::AllocateSmallAllocation(unsigned __int64,uint,bool,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400b02e4`
- end: `0x1400b07b2`
- name: `?AllocateSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAJ_KI_NW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `1230`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400afb90`

## callees

- `0x140004268`
- `0x140012ed4`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002f7d0`
- `0x140059030`
- `0x140059380`
- `0x1400b02e4`
- `0x1400b225c`
- `0x1400b2908`
- `0x1400dabec`
- `0x1400fc094`
- `0x140106954`
- `0x140107cfc`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400b0379`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400b0379`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b0779`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b0779`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b0337`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b053e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b05e9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b0613`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b0337`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b053e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b05e9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b0613`
- `watchdog!WdLogSingleEntry0` at `0x1400b03a0`
- `watchdog!WdLogSingleEntry0` at `0x1400b04ef`
- `watchdog!WdLogSingleEntry0` at `0x1400b03a0`
- `watchdog!WdLogSingleEntry0` at `0x1400b04ef`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b0308`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b0532`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b05dd`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b0607`

## string_xrefs

- `0x1400b04fd`: `Failed to commit reserved virtual address range from block.\n`

## pseudocode

```c
__int64 __fastcall VIDMM_PROCESS_HEAP::AllocateSmallAllocation(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        char a4,
        unsigned int a5,
        _QWORD *a6,
        _QWORD *a7,
        _BYTE *a8)
{
  _QWORD *v8; // rbx
  __int64 v9; // r12
  char v11; // r13
  _QWORD *v12; // rax
  struct _PAGED_LOOKASIDE_LIST *v13; // r15
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  char v16; // r12
  int v17; // r14d
  int v18; // r8d
  unsigned int v19; // r15d
  __int64 v20; // rcx
  _QWORD **BlockListHead; // r13
  _QWORD *v22; // r14
  VIDMM_LINEAR_POOL *v23; // rcx
  unsigned __int64 v24; // r12
  unsigned int v25; // r8d
  int v26; // edx
  unsigned int v27; // eax
  int v28; // r8d
  int v29; // eax
  __int64 v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  int v33; // r8d
  __int64 v34; // rax
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  int v37; // [rsp+28h] [rbp-58h]
  void *v38; // [rsp+60h] [rbp-20h] BYREF
  _QWORD *v39; // [rsp+68h] [rbp-18h] BYREF
  struct _VIDMM_POOL_BLOCK *v40; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int64 v41; // [rsp+78h] [rbp-8h] BYREF
  unsigned __int64 v42; // [rsp+C8h] [rbp+48h] BYREF
  char v43; // [rsp+D8h] [rbp+58h]

  v43 = a4;
  v42 = a2;
  v8 = 0;
  v38 = 0;
  v9 = a3;
  v39 = 0;
  v11 = 0;
  v40 = 0;
  v41 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    v12 = (_QWORD *)WdLogNewEntry5_WdTrace(a1);
    v12[3] = v42;
    v12[4] = v9;
    v12[5] = a1;
    WdLogGlobalForLineNumber = 650;
  }
  v13 = (struct _PAGED_LOOKASIDE_LIST *)(a1 + 64);
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  v14 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 64));
  v15 = v14;
  if ( v14 )
  {
    memset(v14, 0, 0x60u);
    DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)(a1 + 16));
    v19 = a5;
    BlockListHead = (_QWORD **)VIDMM_PROCESS_HEAP::GetBlockListHead(a1, a5);
    v22 = *BlockListHead;
    while ( v22 != BlockListHead )
    {
      v8 = v22 - 1;
      v23 = (VIDMM_LINEAR_POOL *)v22[8];
      v22 = (_QWORD *)*v22;
      v39 = v8;
      if ( (int)VIDMM_LINEAR_POOL::Allocate(v23, v42, v9, 1u, 0, 0, 0, 0, 0, &v41, (void **)&v40) >= 0 )
      {
        v11 = 0;
        goto LABEL_9;
      }
    }
    if ( g_IsInternalReleaseOrDbg )
    {
      WdLogNewEntry5_WdTrace(v20);
      WdLogGlobalForLineNumber = 729;
    }
    LOBYTE(v37) = v43;
    v29 = VIDMM_PROCESS_HEAP::AllocateBlock(a1, v42, (unsigned int)v9, v19, &v39, v37);
    v8 = v39;
    v17 = v29;
    if ( v29 < 0 )
    {
      v11 = 0;
    }
    else
    {
      v11 = 1;
      v17 = VIDMM_LINEAR_POOL::Allocate((VIDMM_LINEAR_POOL *)v39[9], v42, v9, 1u, 0, 0, 0, 0, 0, &v41, (void **)&v40);
      if ( v17 < 0 )
      {
        if ( g_IsInternalReleaseOrDbg )
        {
          WdLogNewEntry5_WdTrace(v20);
          WdLogGlobalForLineNumber = 762;
        }
        v16 = 1;
        goto LABEL_41;
      }
LABEL_9:
      v24 = v41;
      if ( v8[7] || v8[11] )
        goto LABEL_24;
      v25 = 8392704;
      v26 = 4096;
      v27 = *(_DWORD *)(a1 + 288);
      if ( *((_DWORD *)v8 + 20) != 2 )
        v26 = 8392704;
      v38 = (void *)(v41 + v8[4]);
      if ( !v43 )
        v25 = v26;
      v17 = VidMmAllocateVirtualMemory(&v38, &v42, v25, *((_DWORD *)v8 + 12), v27);
      if ( v17 >= 0 )
      {
LABEL_24:
        if ( g_IsInternalReleaseOrDbg )
        {
          v30 = WdLogNewEntry5_WdTrace(v20);
          *(_QWORD *)(v30 + 24) = v8;
          *(_QWORD *)(v30 + 32) = v24;
          WdLogGlobalForLineNumber = 808;
        }
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL) += v42;
        v31 = *(_QWORD **)(a1 + 8);
        if ( v19 == 1 )
        {
          v31[26] += v42;
        }
        else if ( v19 == 2 )
        {
          v31[28] += v42;
        }
        else
        {
          v31[30] += v42;
        }
        *(_DWORD *)v15 &= ~1u;
        v15[7] = v42;
        v15[3] = v40;
        *((_BYTE *)v15 + 64) = 0;
        v15[1] = v8;
        v15[2] = v24;
        v15[4] = 0;
        ++*((_DWORD *)v8 + 6);
        DXGFASTMUTEX::Release((DXGFASTMUTEX *)(a1 + 16));
        *a6 = v15;
        if ( v19 - 5 <= 1 )
        {
          v32 = v15[2] + *(_QWORD *)(v15[1] + 32LL);
          *a7 = v32;
        }
        if ( (byte_140087201 & 0x10) != 0 )
        {
          if ( v19 - 3 <= 3 )
            v34 = v8[11];
          else
            v34 = v8[4];
          McTemplateK0qxxx_EtwWriteTransfer(
            v32,
            (unsigned int)EventCreateProcessAllocationDetails,
            v33,
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
            (char)v15,
            v42,
            v34);
        }
        *a8 = 1;
        return 0;
      }
      v38 = 0;
      _InterlockedIncrement(&dword_140087788);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 797;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        v28,
        (unsigned int)L"Failed to commit reserved virtual address range from block.\n",
        797,
        0,
        0,
        0);
    }
    v16 = 1;
LABEL_41:
    v13 = (struct _PAGED_LOOKASIDE_LIST *)(a1 + 64);
    goto LABEL_42;
  }
  v16 = 0;
  v17 = -1073741801;
  _InterlockedIncrement(&dword_1400876E4);
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 676;
  DxgkLogInternalTriageEvent(
    0,
    262145,
    v18,
    (unsigned int)L"Couldn't allocate memory for VIDMM_PROCESS_HEAP_ALLOC structure.\n",
    676,
    0,
    0,
    0);
LABEL_42:
  if ( v38 )
  {
    VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
    (*((void (__fastcall **)(__int64, void **, unsigned __int64 *, __int64))VirtualMemoryInterface + 2))(
      -1,
      &v38,
      &v42,
      0x4000);
  }
  if ( v40 && v8 )
    VIDMM_LINEAR_POOL::Free((VIDMM_LINEAR_POOL *)v8[9], v40);
  if ( v11 == 1 )
    VIDMM_PROCESS_HEAP::FreeBlock((VIDMM_PROCESS_HEAP *)a1, (struct _VIDMM_PROCESS_HEAP_BLOCK *)v8);
  if ( v15 )
    ExFreeToPagedLookasideList(v13, v15);
  if ( v16 )
    DXGFASTMUTEX::Release((DXGFASTMUTEX *)(a1 + 16));
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400b02e4  mov     [rsp-38h+arg_10], rbx
0x1400b02e9  mov     [rsp-38h+arg_18], r9b
0x1400b02ee  mov     [rsp-38h+arg_8], rdx
0x1400b02f3  push    rbp
0x1400b02f4  push    rsi
0x1400b02f5  push    rdi
0x1400b02f6  push    r12
0x1400b02f8  push    r13
0x1400b02fa  push    r14
0x1400b02fc  push    r15
0x1400b02fe  mov     rbp, rsp
0x1400b0301  sub     rsp, 80h
0x1400b0308  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b030f  xor     r14d, r14d
0x1400b0312  mov     ebx, r14d
0x1400b0315  mov     [rbp+var_20], r14
0x1400b0319  mov     r12d, r8d
0x1400b031c  mov     rsi, rcx
0x1400b031f  mov     [rbp+var_18], rbx
0x1400b0323  mov     r13b, r14b
0x1400b0326  mov     [rbp+var_10], r14
0x1400b032a  mov     [rbp+var_8], r14
0x1400b032e  mov     [rbp+arg_0], r14b
0x1400b0332  cmp     [rax], r14b
0x1400b0335  jz      short loc_1400B035D
0x1400b0337  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b033e  nop     dword ptr [rax+rax+00h]
0x1400b0343  mov     rcx, [rbp+arg_8]
0x1400b0347  mov     [rax+18h], rcx
0x1400b034b  mov     [rax+20h], r12
0x1400b034f  mov     [rax+28h], rsi
0x1400b0353  mov     cs:WdLogGlobalForLineNumber, 28Ah
0x1400b035d  mov     rax, [rbp+arg_28]
0x1400b0361  lea     r15, [rsi+40h]
0x1400b0365  mov     rcx, r15; Lookaside
0x1400b0368  mov     [rax], r14
0x1400b036b  mov     rax, [rbp+arg_30]
0x1400b036f  mov     [rax], r14
0x1400b0372  mov     rax, [rbp+arg_38]
0x1400b0376  mov     [rax], r14b
0x1400b0379  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400b0380  nop     dword ptr [rax+rax+00h]
0x1400b0385  mov     rdi, rax
0x1400b0388  test    rax, rax
0x1400b038b  jnz     short loc_1400B03E3
0x1400b038d  mov     r12b, r14b
0x1400b0390  mov     r14d, 0C0000017h
0x1400b0396  lock inc cs:dword_1400876E4
0x1400b039d  lea     ecx, [rax+6]
0x1400b03a0  call    cs:__imp_WdLogSingleEntry0
0x1400b03a7  nop     dword ptr [rax+rax+00h]
0x1400b03ac  xor     ecx, ecx
0x1400b03ae  lea     r9, aCouldnTAllocat_39; "Couldn't allocate memory for VIDMM_PROC"...
0x1400b03b5  mov     qword ptr [rsp+80h+var_48], rcx
0x1400b03ba  mov     eax, 2A4h
0x1400b03bf  mov     qword ptr [rsp+80h+var_50], rcx
0x1400b03c4  mov     edx, 40001h
0x1400b03c9  mov     [rsp+80h+var_58], rcx
0x1400b03ce  mov     qword ptr [rsp+80h+var_60], rax
0x1400b03d3  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b03d9  call    DxgkLogInternalTriageEvent
0x1400b03de  jmp     loc_1400B071F
0x1400b03e3  xor     edx, edx; Val
0x1400b03e5  mov     rcx, rdi; void *
0x1400b03e8  lea     r8d, [rdx+60h]; Size
0x1400b03ec  call    memset
0x1400b03f1  lea     rcx, [rsi+10h]; this
0x1400b03f5  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400b03fa  mov     r15d, [rbp+arg_20]
0x1400b03fe  mov     rcx, rsi
0x1400b0401  mov     edx, r15d
0x1400b0404  call    ?GetBlockListHead@VIDMM_PROCESS_HEAP@@AEAAPEAU_LIST_ENTRY@@W4VIDMM_PROCESS_HEAP_MAPPING@@@Z; VIDMM_PROCESS_HEAP::GetBlockListHead(VIDMM_PROCESS_HEAP_MAPPING)
0x1400b0409  mov     r13, rax
0x1400b040c  mov     r14, [rax]
0x1400b040f  cmp     r14, r13
0x1400b0412  jz      loc_1400B0532
0x1400b0418  mov     rdx, [rbp+arg_8]; unsigned __int64
0x1400b041c  lea     rbx, [r14-8]
0x1400b0420  mov     rcx, [rbx+48h]; this
0x1400b0424  lea     rax, [rbp+var_10]
0x1400b0428  mov     r14, [r14]
0x1400b042b  mov     r9b, 1; unsigned __int8
0x1400b042e  mov     [rsp+80h+var_30], rax; void **
0x1400b0433  mov     r8d, r12d; unsigned int
0x1400b0436  lea     rax, [rbp+var_8]
0x1400b043a  mov     [rbp+var_18], rbx
0x1400b043e  mov     [rsp+80h+var_38], rax; unsigned __int64 *
0x1400b0443  mov     [rsp+80h+var_40], 0; struct VIDMM_PHYSICAL_ALLOC *
0x1400b044c  mov     [rsp+80h+var_48], 0; char
0x1400b0451  mov     [rsp+80h+var_50], 0; char
0x1400b0456  mov     [rsp+80h+var_58], 0; unsigned __int64
0x1400b045f  mov     qword ptr [rsp+80h+var_60], 0; unsigned __int64
0x1400b0468  call    ?Allocate@VIDMM_LINEAR_POOL@@QEAAJ_KKE00EEPEAUVIDMM_PHYSICAL_ALLOC@@PEA_KPEAPEAX@Z; VIDMM_LINEAR_POOL::Allocate(unsigned __int64,ulong,uchar,unsigned __int64,unsigned __int64,uchar,uchar,VIDMM_PHYSICAL_ALLOC *,unsigned __int64 *,void * *)
0x1400b046d  test    eax, eax
0x1400b046f  js      short loc_1400B040F
0x1400b0471  mov     r13b, [rbp+arg_0]
0x1400b0475  cmp     qword ptr [rbx+38h], 0
0x1400b047a  mov     r12, [rbp+var_8]
0x1400b047e  jnz     loc_1400B0607
0x1400b0484  cmp     qword ptr [rbx+58h], 0
0x1400b0489  jnz     loc_1400B0607
0x1400b048f  cmp     dword ptr [rbx+50h], 2
0x1400b0493  mov     r8d, 801000h
0x1400b0499  mov     rcx, [rbx+20h]
0x1400b049d  mov     edx, 1000h
0x1400b04a2  mov     eax, [rsi+120h]
0x1400b04a8  cmovnz  edx, r8d
0x1400b04ac  add     rcx, r12
0x1400b04af  mov     [rsp+80h+var_60], eax; unsigned int
0x1400b04b3  cmp     [rbp+arg_18], 0
0x1400b04b7  mov     [rbp+var_20], rcx
0x1400b04bb  lea     rcx, [rbp+var_20]; void **
0x1400b04bf  mov     r9d, [rbx+30h]; unsigned int
0x1400b04c3  cmovz   r8d, edx; unsigned int
0x1400b04c7  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1400b04cb  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400b04d0  mov     r14d, eax
0x1400b04d3  test    eax, eax
0x1400b04d5  jns     loc_1400B0607
0x1400b04db  mov     [rbp+var_20], 0
0x1400b04e3  lock inc cs:dword_140087788
0x1400b04ea  mov     ecx, 6
0x1400b04ef  call    cs:__imp_WdLogSingleEntry0
0x1400b04f6  nop     dword ptr [rax+rax+00h]
0x1400b04fb  xor     ecx, ecx
0x1400b04fd  lea     r9, aFailedToCommit_1; "Failed to commit reserved virtual addre"...
0x1400b0504  mov     qword ptr [rsp+80h+var_48], rcx
0x1400b0509  mov     eax, 31Dh
0x1400b050e  mov     qword ptr [rsp+80h+var_50], rcx
0x1400b0513  mov     edx, 40001h
0x1400b0518  mov     [rsp+80h+var_58], rcx
0x1400b051d  mov     qword ptr [rsp+80h+var_60], rax
0x1400b0522  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b0528  call    DxgkLogInternalTriageEvent
0x1400b052d  jmp     loc_1400B0718
0x1400b0532  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b0539  cmp     byte ptr [rax], 0
0x1400b053c  jz      short loc_1400B0554
0x1400b053e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b0545  nop     dword ptr [rax+rax+00h]
0x1400b054a  mov     cs:WdLogGlobalForLineNumber, 2D9h
0x1400b0554  mov     al, [rbp+arg_18]
0x1400b0557  mov     r9d, r15d
0x1400b055a  mov     rdx, [rbp+arg_8]
0x1400b055e  mov     r8d, r12d
0x1400b0561  mov     byte ptr [rsp+80h+var_58], al
0x1400b0565  mov     rcx, rsi
0x1400b0568  lea     rax, [rbp+var_18]
0x1400b056c  mov     qword ptr [rsp+80h+var_60], rax
0x1400b0571  call    ?AllocateBlock@VIDMM_PROCESS_HEAP@@AEAAJ_KKW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAU_VIDMM_PROCESS_HEAP_BLOCK@@_N@Z; VIDMM_PROCESS_HEAP::AllocateBlock(unsigned __int64,ulong,VIDMM_PROCESS_HEAP_MAPPING,_VIDMM_PROCESS_HEAP_BLOCK * *,bool)
0x1400b0576  mov     rbx, [rbp+var_18]
0x1400b057a  mov     r14d, eax
0x1400b057d  test    eax, eax
0x1400b057f  js      loc_1400B0714
0x1400b0585  mov     rdx, [rbp+arg_8]; unsigned __int64
0x1400b0589  lea     rax, [rbp+var_10]
0x1400b058d  mov     rcx, [rbx+48h]; this
0x1400b0591  mov     r13b, 1
0x1400b0594  mov     [rsp+80h+var_30], rax; void **
0x1400b0599  mov     r9b, r13b; unsigned __int8
0x1400b059c  lea     rax, [rbp+var_8]
0x1400b05a0  mov     r8d, r12d; unsigned int
0x1400b05a3  mov     [rsp+80h+var_38], rax; unsigned __int64 *
0x1400b05a8  mov     [rsp+80h+var_40], 0; struct VIDMM_PHYSICAL_ALLOC *
0x1400b05b1  mov     [rsp+80h+var_48], 0; char
0x1400b05b6  mov     [rsp+80h+var_50], 0; char
0x1400b05bb  mov     [rsp+80h+var_58], 0; unsigned __int64
0x1400b05c4  mov     qword ptr [rsp+80h+var_60], 0; unsigned __int64
0x1400b05cd  call    ?Allocate@VIDMM_LINEAR_POOL@@QEAAJ_KKE00EEPEAUVIDMM_PHYSICAL_ALLOC@@PEA_KPEAPEAX@Z; VIDMM_LINEAR_POOL::Allocate(unsigned __int64,ulong,uchar,unsigned __int64,unsigned __int64,uchar,uchar,VIDMM_PHYSICAL_ALLOC *,unsigned __int64 *,void * *)
0x1400b05d2  mov     r14d, eax
0x1400b05d5  test    eax, eax
0x1400b05d7  jns     loc_1400B0475
0x1400b05dd  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b05e4  cmp     byte ptr [rax], 0
0x1400b05e7  jz      short loc_1400B05FF
0x1400b05e9  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b05f0  nop     dword ptr [rax+rax+00h]
0x1400b05f5  mov     cs:WdLogGlobalForLineNumber, 2FAh
0x1400b05ff  mov     r12b, r13b
0x1400b0602  jmp     loc_1400B071B
0x1400b0607  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b060e  cmp     byte ptr [rax], 0
0x1400b0611  jz      short loc_1400B0631
0x1400b0613  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b061a  nop     dword ptr [rax+rax+00h]
0x1400b061f  mov     [rax+18h], rbx
0x1400b0623  mov     [rax+20h], r12
0x1400b0627  mov     cs:WdLogGlobalForLineNumber, 328h
0x1400b0631  mov     rcx, [rsi+8]
0x1400b0635  mov     rax, [rbp+arg_8]
0x1400b0639  add     [rcx+0B8h], rax
0x1400b0640  mov     rcx, [rsi+8]
0x1400b0644  mov     rax, [rbp+arg_8]
0x1400b0648  cmp     r15d, 1
0x1400b064c  jnz     short loc_1400B0657
0x1400b064e  add     [rcx+0D0h], rax
0x1400b0655  jmp     short loc_1400B066D
0x1400b0657  cmp     r15d, 2
0x1400b065b  jnz     short loc_1400B0666
0x1400b065d  add     [rcx+0E0h], rax
0x1400b0664  jmp     short loc_1400B066D
0x1400b0666  add     [rcx+0F0h], rax
0x1400b066d  and     dword ptr [rdi], 0FFFFFFFEh
0x1400b0670  lea     rcx, [rsi+10h]; this
0x1400b0674  mov     rax, [rbp+arg_8]
0x1400b0678  mov     [rdi+38h], rax
0x1400b067c  mov     rax, [rbp+var_10]
0x1400b0680  mov     [rdi+18h], rax
0x1400b0684  mov     byte ptr [rdi+40h], 0
0x1400b0688  mov     [rdi+8], rbx
0x1400b068c  mov     [rdi+10h], r12
0x1400b0690  mov     qword ptr [rdi+20h], 0
0x1400b0698  inc     dword ptr [rbx+18h]
0x1400b069b  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400b06a0  mov     rax, [rbp+arg_28]
0x1400b06a4  mov     [rax], rdi
0x1400b06a7  lea     eax, [r15-5]
0x1400b06ab  cmp     eax, 1
0x1400b06ae  ja      short loc_1400B06C3
0x1400b06b0  mov     rax, [rdi+8]
0x1400b06b4  mov     rcx, [rax+20h]
0x1400b06b8  mov     rax, [rbp+arg_30]
0x1400b06bc  add     rcx, [rdi+10h]
0x1400b06c0  mov     [rax], rcx
0x1400b06c3  test    cs:byte_140087201, 10h
0x1400b06ca  jz      short loc_1400B0706
0x1400b06cc  lea     eax, [r15-3]
0x1400b06d0  cmp     eax, 3
0x1400b06d3  jbe     short loc_1400B06DB
0x1400b06d5  mov     rax, [rbx+20h]
0x1400b06d9  jmp     short loc_1400B06DF
0x1400b06db  mov     rax, [rbx+58h]
0x1400b06df  mov     r9, [rsi+8]
0x1400b06e3  lea     rdx, EventCreateProcessAllocationDetails
0x1400b06ea  mov     qword ptr [rsp+80h+var_50], rax
0x1400b06ef  mov     rax, [rbp+arg_8]
0x1400b06f3  mov     [rsp+80h+var_58], rax
0x1400b06f8  mov     r9d, [r9+18h]
0x1400b06fc  mov     qword ptr [rsp+80h+var_60], rdi
0x1400b0701  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400b0706  mov     rax, [rbp+arg_38]
0x1400b070a  mov     byte ptr [rax], 1
0x1400b070d  xor     eax, eax
0x1400b070f  jmp     loc_1400B0796
0x1400b0714  mov     r13b, [rbp+arg_0]
0x1400b0718  mov     r12b, 1
0x1400b071b  lea     r15, [rsi+40h]
0x1400b071f  cmp     [rbp+var_20], 0
0x1400b0724  jz      short loc_1400B0746
0x1400b0726  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400b072b  mov     r9d, 4000h
0x1400b0731  lea     r8, [rbp+arg_8]
0x1400b0735  lea     rdx, [rbp+var_20]
0x1400b0739  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b073d  mov     rax, [rax+10h]
0x1400b0741  call    _guard_dispatch_icall
0x1400b0746  mov     rdx, [rbp+var_10]; struct _VIDMM_POOL_BLOCK *
0x1400b074a  test    rdx, rdx
0x1400b074d  jz      short loc_1400B075D
0x1400b074f  test    rbx, rbx
0x1400b0752  jz      short loc_1400B075D
0x1400b0754  mov     rcx, [rbx+48h]; this
0x1400b0758  call    ?Free@VIDMM_LINEAR_POOL@@QEAAXPEAX@Z; VIDMM_LINEAR_POOL::Free(void *)
0x1400b075d  cmp     r13b, 1
0x1400b0761  jnz     short loc_1400B076E
0x1400b0763  mov     rdx, rbx; struct _VIDMM_PROCESS_HEAP_BLOCK *
0x1400b0766  mov     rcx, rsi; this
0x1400b0769  call    ?FreeBlock@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_BLOCK@@@Z; VIDMM_PROCESS_HEAP::FreeBlock(_VIDMM_PROCESS_HEAP_BLOCK *)
0x1400b076e  test    rdi, rdi
0x1400b0771  jz      short loc_1400B0785
0x1400b0773  mov     rdx, rdi; Entry
0x1400b0776  mov     rcx, r15; Lookaside
0x1400b0779  call    cs:__imp_ExFreeToPagedLookasideList
0x1400b0780  nop     dword ptr [rax+rax+00h]
0x1400b0785  test    r12b, r12b
0x1400b0788  jz      short loc_1400B0793
0x1400b078a  lea     rcx, [rsi+10h]; this
0x1400b078e  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400b0793  mov     eax, r14d
0x1400b0796  mov     rbx, [rsp+80h+arg_10]
0x1400b079e  add     rsp, 80h
0x1400b07a5  pop     r15
0x1400b07a7  pop     r14
0x1400b07a9  pop     r13
0x1400b07ab  pop     r12
0x1400b07ad  pop     rdi
0x1400b07ae  pop     rsi
0x1400b07af  pop     rbp
0x1400b07b0  retn
```
