# VIDMM_PROCESS_HEAP::AllocateSmallAllocation(unsigned __int64,uint,bool,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400aed94`
- end: `0x1400af262`
- name: `?AllocateSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAJ_KI_NW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `1230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400ae640`

## callees

- `0x1400045ec`
- `0x140013434`
- `0x14002fbac`
- `0x14002fd94`
- `0x140031934`
- `0x140058760`
- `0x140058ac0`
- `0x1400aed94`
- `0x1400b0d0c`
- `0x1400b13b8`
- `0x1400d28fc`
- `0x1400f70b4`
- `0x1400fbad4`
- `0x1400fd688`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400aee29`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400aee29`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400af229`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400af229`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400aede7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400aefee`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400af099`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400af0c3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400aede7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400aefee`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400af099`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400af0c3`
- `watchdog!WdLogSingleEntry0` at `0x1400aee50`
- `watchdog!WdLogSingleEntry0` at `0x1400aef9f`
- `watchdog!WdLogSingleEntry0` at `0x1400aee50`
- `watchdog!WdLogSingleEntry0` at `0x1400aef9f`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400aedb8`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400aefe2`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400af08d`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400af0b7`

## string_xrefs

- `0x1400aefad`: `Failed to commit reserved virtual address range from block.\n`

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
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD **BlockListHead; // r13
  _QWORD *v23; // r14
  VIDMM_LINEAR_POOL *v24; // rcx
  unsigned __int64 v25; // r12
  unsigned int v26; // r8d
  int v27; // edx
  unsigned int v28; // eax
  int v29; // r8d
  int v30; // eax
  __int64 v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // rcx
  int v34; // r8d
  __int64 v35; // rax
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
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
    v12 = (_QWORD *)WdLogNewEntry5_WdTrace(a1, a2);
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
    v23 = *BlockListHead;
    while ( v23 != BlockListHead )
    {
      v8 = v23 - 1;
      v24 = (VIDMM_LINEAR_POOL *)v23[8];
      v23 = (_QWORD *)*v23;
      v39 = v8;
      if ( (int)VIDMM_LINEAR_POOL::Allocate(v24, v42, v9, 1u, 0, 0, 0, 0, 0, &v41, (void **)&v40) >= 0 )
      {
        v11 = 0;
        goto LABEL_9;
      }
    }
    if ( g_IsInternalReleaseOrDbg )
    {
      WdLogNewEntry5_WdTrace(v21, v20);
      WdLogGlobalForLineNumber = 729;
    }
    v30 = VIDMM_PROCESS_HEAP::AllocateBlock(a1, v42, v9, v19, &v39, v43);
    v8 = v39;
    v17 = v30;
    if ( v30 < 0 )
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
          WdLogNewEntry5_WdTrace(v21, v20);
          WdLogGlobalForLineNumber = 762;
        }
        v16 = 1;
        goto LABEL_41;
      }
LABEL_9:
      v25 = v41;
      if ( v8[7] || v8[11] )
        goto LABEL_24;
      v26 = 8392704;
      v27 = 4096;
      v28 = *(_DWORD *)(a1 + 288);
      if ( *((_DWORD *)v8 + 20) != 2 )
        v27 = 8392704;
      v38 = (void *)(v41 + v8[4]);
      if ( !v43 )
        v26 = v27;
      v17 = VidMmAllocateVirtualMemory(&v38, &v42, v26, *((_DWORD *)v8 + 12), v28);
      if ( v17 >= 0 )
      {
LABEL_24:
        if ( g_IsInternalReleaseOrDbg )
        {
          v31 = WdLogNewEntry5_WdTrace(v21, v20);
          *(_QWORD *)(v31 + 24) = v8;
          *(_QWORD *)(v31 + 32) = v25;
          WdLogGlobalForLineNumber = 808;
        }
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 176LL) += v42;
        v32 = *(_QWORD **)(a1 + 8);
        if ( v19 == 1 )
        {
          v32[25] += v42;
        }
        else if ( v19 == 2 )
        {
          v32[27] += v42;
        }
        else
        {
          v32[29] += v42;
        }
        *(_DWORD *)v15 &= ~1u;
        v15[7] = v42;
        v15[3] = v40;
        *((_BYTE *)v15 + 64) = 0;
        v15[1] = v8;
        v15[2] = v25;
        v15[4] = 0;
        ++*((_DWORD *)v8 + 6);
        DXGFASTMUTEX::Release((DXGFASTMUTEX *)(a1 + 16));
        *a6 = v15;
        if ( v19 - 5 <= 1 )
        {
          v33 = v15[2] + *(_QWORD *)(v15[1] + 32LL);
          *a7 = v33;
        }
        if ( (byte_140086201 & 0x10) != 0 )
        {
          if ( v19 - 3 <= 3 )
            v35 = v8[11];
          else
            v35 = v8[4];
          McTemplateK0qxxx_EtwWriteTransfer(
            v33,
            (unsigned int)EventCreateProcessAllocationDetails,
            v34,
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
            (char)v15,
            v42,
            v35);
        }
        *a8 = 1;
        return 0;
      }
      v38 = 0;
      _InterlockedIncrement(&dword_1400867A8);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 797;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        v29,
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
  _InterlockedIncrement(&dword_140086704);
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
0x1400aed94  mov     [rsp-38h+arg_10], rbx
0x1400aed99  mov     [rsp-38h+arg_18], r9b
0x1400aed9e  mov     [rsp-38h+arg_8], rdx
0x1400aeda3  push    rbp
0x1400aeda4  push    rsi
0x1400aeda5  push    rdi
0x1400aeda6  push    r12
0x1400aeda8  push    r13
0x1400aedaa  push    r14
0x1400aedac  push    r15
0x1400aedae  mov     rbp, rsp
0x1400aedb1  sub     rsp, 80h
0x1400aedb8  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400aedbf  xor     r14d, r14d
0x1400aedc2  mov     ebx, r14d
0x1400aedc5  mov     [rbp+var_20], r14
0x1400aedc9  mov     r12d, r8d
0x1400aedcc  mov     rsi, rcx
0x1400aedcf  mov     [rbp+var_18], rbx
0x1400aedd3  mov     r13b, r14b
0x1400aedd6  mov     [rbp+var_10], r14
0x1400aedda  mov     [rbp+var_8], r14
0x1400aedde  mov     [rbp+arg_0], r14b
0x1400aede2  cmp     [rax], r14b
0x1400aede5  jz      short loc_1400AEE0D
0x1400aede7  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400aedee  nop     dword ptr [rax+rax+00h]
0x1400aedf3  mov     rcx, [rbp+arg_8]
0x1400aedf7  mov     [rax+18h], rcx
0x1400aedfb  mov     [rax+20h], r12
0x1400aedff  mov     [rax+28h], rsi
0x1400aee03  mov     cs:WdLogGlobalForLineNumber, 28Ah
0x1400aee0d  mov     rax, [rbp+arg_28]
0x1400aee11  lea     r15, [rsi+40h]
0x1400aee15  mov     rcx, r15; Lookaside
0x1400aee18  mov     [rax], r14
0x1400aee1b  mov     rax, [rbp+arg_30]
0x1400aee1f  mov     [rax], r14
0x1400aee22  mov     rax, [rbp+arg_38]
0x1400aee26  mov     [rax], r14b
0x1400aee29  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400aee30  nop     dword ptr [rax+rax+00h]
0x1400aee35  mov     rdi, rax
0x1400aee38  test    rax, rax
0x1400aee3b  jnz     short loc_1400AEE93
0x1400aee3d  mov     r12b, r14b
0x1400aee40  mov     r14d, 0C0000017h
0x1400aee46  lock inc cs:dword_140086704
0x1400aee4d  lea     ecx, [rax+6]
0x1400aee50  call    cs:__imp_WdLogSingleEntry0
0x1400aee57  nop     dword ptr [rax+rax+00h]
0x1400aee5c  xor     ecx, ecx
0x1400aee5e  lea     r9, aCouldnTAllocat_37; "Couldn't allocate memory for VIDMM_PROC"...
0x1400aee65  mov     qword ptr [rsp+80h+var_48], rcx
0x1400aee6a  mov     eax, 2A4h
0x1400aee6f  mov     qword ptr [rsp+80h+var_50], rcx
0x1400aee74  mov     edx, 40001h
0x1400aee79  mov     [rsp+80h+var_58], rcx
0x1400aee7e  mov     qword ptr [rsp+80h+var_60], rax
0x1400aee83  mov     cs:WdLogGlobalForLineNumber, eax
0x1400aee89  call    DxgkLogInternalTriageEvent
0x1400aee8e  jmp     loc_1400AF1CF
0x1400aee93  xor     edx, edx; Val
0x1400aee95  mov     rcx, rdi; void *
0x1400aee98  lea     r8d, [rdx+60h]; Size
0x1400aee9c  call    memset
0x1400aeea1  lea     rcx, [rsi+10h]; this
0x1400aeea5  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400aeeaa  mov     r15d, [rbp+arg_20]
0x1400aeeae  mov     rcx, rsi
0x1400aeeb1  mov     edx, r15d
0x1400aeeb4  call    ?GetBlockListHead@VIDMM_PROCESS_HEAP@@AEAAPEAU_LIST_ENTRY@@W4VIDMM_PROCESS_HEAP_MAPPING@@@Z; VIDMM_PROCESS_HEAP::GetBlockListHead(VIDMM_PROCESS_HEAP_MAPPING)
0x1400aeeb9  mov     r13, rax
0x1400aeebc  mov     r14, [rax]
0x1400aeebf  cmp     r14, r13
0x1400aeec2  jz      loc_1400AEFE2
0x1400aeec8  mov     rdx, [rbp+arg_8]; unsigned __int64
0x1400aeecc  lea     rbx, [r14-8]
0x1400aeed0  mov     rcx, [rbx+48h]; this
0x1400aeed4  lea     rax, [rbp+var_10]
0x1400aeed8  mov     r14, [r14]
0x1400aeedb  mov     r9b, 1; unsigned __int8
0x1400aeede  mov     [rsp+80h+var_30], rax; void **
0x1400aeee3  mov     r8d, r12d; unsigned int
0x1400aeee6  lea     rax, [rbp+var_8]
0x1400aeeea  mov     [rbp+var_18], rbx
0x1400aeeee  mov     [rsp+80h+var_38], rax; unsigned __int64 *
0x1400aeef3  mov     [rsp+80h+var_40], 0; struct VIDMM_PHYSICAL_ALLOC *
0x1400aeefc  mov     [rsp+80h+var_48], 0; char
0x1400aef01  mov     [rsp+80h+var_50], 0; char
0x1400aef06  mov     [rsp+80h+var_58], 0; unsigned __int64
0x1400aef0f  mov     qword ptr [rsp+80h+var_60], 0; unsigned __int64
0x1400aef18  call    ?Allocate@VIDMM_LINEAR_POOL@@QEAAJ_KKE00EEPEAUVIDMM_PHYSICAL_ALLOC@@PEA_KPEAPEAX@Z; VIDMM_LINEAR_POOL::Allocate(unsigned __int64,ulong,uchar,unsigned __int64,unsigned __int64,uchar,uchar,VIDMM_PHYSICAL_ALLOC *,unsigned __int64 *,void * *)
0x1400aef1d  test    eax, eax
0x1400aef1f  js      short loc_1400AEEBF
0x1400aef21  mov     r13b, [rbp+arg_0]
0x1400aef25  cmp     qword ptr [rbx+38h], 0
0x1400aef2a  mov     r12, [rbp+var_8]
0x1400aef2e  jnz     loc_1400AF0B7
0x1400aef34  cmp     qword ptr [rbx+58h], 0
0x1400aef39  jnz     loc_1400AF0B7
0x1400aef3f  cmp     dword ptr [rbx+50h], 2
0x1400aef43  mov     r8d, 801000h
0x1400aef49  mov     rcx, [rbx+20h]
0x1400aef4d  mov     edx, 1000h
0x1400aef52  mov     eax, [rsi+120h]
0x1400aef58  cmovnz  edx, r8d
0x1400aef5c  add     rcx, r12
0x1400aef5f  mov     [rsp+80h+var_60], eax; unsigned int
0x1400aef63  cmp     [rbp+arg_18], 0
0x1400aef67  mov     [rbp+var_20], rcx
0x1400aef6b  lea     rcx, [rbp+var_20]; void **
0x1400aef6f  mov     r9d, [rbx+30h]; unsigned int
0x1400aef73  cmovz   r8d, edx; unsigned int
0x1400aef77  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1400aef7b  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400aef80  mov     r14d, eax
0x1400aef83  test    eax, eax
0x1400aef85  jns     loc_1400AF0B7
0x1400aef8b  mov     [rbp+var_20], 0
0x1400aef93  lock inc cs:dword_1400867A8
0x1400aef9a  mov     ecx, 6
0x1400aef9f  call    cs:__imp_WdLogSingleEntry0
0x1400aefa6  nop     dword ptr [rax+rax+00h]
0x1400aefab  xor     ecx, ecx
0x1400aefad  lea     r9, aFailedToCommit_1; "Failed to commit reserved virtual addre"...
0x1400aefb4  mov     qword ptr [rsp+80h+var_48], rcx
0x1400aefb9  mov     eax, 31Dh
0x1400aefbe  mov     qword ptr [rsp+80h+var_50], rcx
0x1400aefc3  mov     edx, 40001h
0x1400aefc8  mov     [rsp+80h+var_58], rcx
0x1400aefcd  mov     qword ptr [rsp+80h+var_60], rax
0x1400aefd2  mov     cs:WdLogGlobalForLineNumber, eax
0x1400aefd8  call    DxgkLogInternalTriageEvent
0x1400aefdd  jmp     loc_1400AF1C8
0x1400aefe2  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400aefe9  cmp     byte ptr [rax], 0
0x1400aefec  jz      short loc_1400AF004
0x1400aefee  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400aeff5  nop     dword ptr [rax+rax+00h]
0x1400aeffa  mov     cs:WdLogGlobalForLineNumber, 2D9h
0x1400af004  mov     al, [rbp+arg_18]
0x1400af007  mov     r9d, r15d
0x1400af00a  mov     rdx, [rbp+arg_8]
0x1400af00e  mov     r8d, r12d
0x1400af011  mov     byte ptr [rsp+80h+var_58], al
0x1400af015  mov     rcx, rsi
0x1400af018  lea     rax, [rbp+var_18]
0x1400af01c  mov     qword ptr [rsp+80h+var_60], rax
0x1400af021  call    ?AllocateBlock@VIDMM_PROCESS_HEAP@@AEAAJ_KKW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAU_VIDMM_PROCESS_HEAP_BLOCK@@_N@Z; VIDMM_PROCESS_HEAP::AllocateBlock(unsigned __int64,ulong,VIDMM_PROCESS_HEAP_MAPPING,_VIDMM_PROCESS_HEAP_BLOCK * *,bool)
0x1400af026  mov     rbx, [rbp+var_18]
0x1400af02a  mov     r14d, eax
0x1400af02d  test    eax, eax
0x1400af02f  js      loc_1400AF1C4
0x1400af035  mov     rdx, [rbp+arg_8]; unsigned __int64
0x1400af039  lea     rax, [rbp+var_10]
0x1400af03d  mov     rcx, [rbx+48h]; this
0x1400af041  mov     r13b, 1
0x1400af044  mov     [rsp+80h+var_30], rax; void **
0x1400af049  mov     r9b, r13b; unsigned __int8
0x1400af04c  lea     rax, [rbp+var_8]
0x1400af050  mov     r8d, r12d; unsigned int
0x1400af053  mov     [rsp+80h+var_38], rax; unsigned __int64 *
0x1400af058  mov     [rsp+80h+var_40], 0; struct VIDMM_PHYSICAL_ALLOC *
0x1400af061  mov     [rsp+80h+var_48], 0; char
0x1400af066  mov     [rsp+80h+var_50], 0; char
0x1400af06b  mov     [rsp+80h+var_58], 0; unsigned __int64
0x1400af074  mov     qword ptr [rsp+80h+var_60], 0; unsigned __int64
0x1400af07d  call    ?Allocate@VIDMM_LINEAR_POOL@@QEAAJ_KKE00EEPEAUVIDMM_PHYSICAL_ALLOC@@PEA_KPEAPEAX@Z; VIDMM_LINEAR_POOL::Allocate(unsigned __int64,ulong,uchar,unsigned __int64,unsigned __int64,uchar,uchar,VIDMM_PHYSICAL_ALLOC *,unsigned __int64 *,void * *)
0x1400af082  mov     r14d, eax
0x1400af085  test    eax, eax
0x1400af087  jns     loc_1400AEF25
0x1400af08d  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400af094  cmp     byte ptr [rax], 0
0x1400af097  jz      short loc_1400AF0AF
0x1400af099  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400af0a0  nop     dword ptr [rax+rax+00h]
0x1400af0a5  mov     cs:WdLogGlobalForLineNumber, 2FAh
0x1400af0af  mov     r12b, r13b
0x1400af0b2  jmp     loc_1400AF1CB
0x1400af0b7  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400af0be  cmp     byte ptr [rax], 0
0x1400af0c1  jz      short loc_1400AF0E1
0x1400af0c3  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400af0ca  nop     dword ptr [rax+rax+00h]
0x1400af0cf  mov     [rax+18h], rbx
0x1400af0d3  mov     [rax+20h], r12
0x1400af0d7  mov     cs:WdLogGlobalForLineNumber, 328h
0x1400af0e1  mov     rcx, [rsi+8]
0x1400af0e5  mov     rax, [rbp+arg_8]
0x1400af0e9  add     [rcx+0B0h], rax
0x1400af0f0  mov     rcx, [rsi+8]
0x1400af0f4  mov     rax, [rbp+arg_8]
0x1400af0f8  cmp     r15d, 1
0x1400af0fc  jnz     short loc_1400AF107
0x1400af0fe  add     [rcx+0C8h], rax
0x1400af105  jmp     short loc_1400AF11D
0x1400af107  cmp     r15d, 2
0x1400af10b  jnz     short loc_1400AF116
0x1400af10d  add     [rcx+0D8h], rax
0x1400af114  jmp     short loc_1400AF11D
0x1400af116  add     [rcx+0E8h], rax
0x1400af11d  and     dword ptr [rdi], 0FFFFFFFEh
0x1400af120  lea     rcx, [rsi+10h]; this
0x1400af124  mov     rax, [rbp+arg_8]
0x1400af128  mov     [rdi+38h], rax
0x1400af12c  mov     rax, [rbp+var_10]
0x1400af130  mov     [rdi+18h], rax
0x1400af134  mov     byte ptr [rdi+40h], 0
0x1400af138  mov     [rdi+8], rbx
0x1400af13c  mov     [rdi+10h], r12
0x1400af140  mov     qword ptr [rdi+20h], 0
0x1400af148  inc     dword ptr [rbx+18h]
0x1400af14b  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400af150  mov     rax, [rbp+arg_28]
0x1400af154  mov     [rax], rdi
0x1400af157  lea     eax, [r15-5]
0x1400af15b  cmp     eax, 1
0x1400af15e  ja      short loc_1400AF173
0x1400af160  mov     rax, [rdi+8]
0x1400af164  mov     rcx, [rax+20h]
0x1400af168  mov     rax, [rbp+arg_30]
0x1400af16c  add     rcx, [rdi+10h]
0x1400af170  mov     [rax], rcx
0x1400af173  test    cs:byte_140086201, 10h
0x1400af17a  jz      short loc_1400AF1B6
0x1400af17c  lea     eax, [r15-3]
0x1400af180  cmp     eax, 3
0x1400af183  jbe     short loc_1400AF18B
0x1400af185  mov     rax, [rbx+20h]
0x1400af189  jmp     short loc_1400AF18F
0x1400af18b  mov     rax, [rbx+58h]
0x1400af18f  mov     r9, [rsi+8]
0x1400af193  lea     rdx, EventCreateProcessAllocationDetails
0x1400af19a  mov     qword ptr [rsp+80h+var_50], rax
0x1400af19f  mov     rax, [rbp+arg_8]
0x1400af1a3  mov     [rsp+80h+var_58], rax
0x1400af1a8  mov     r9d, [r9+18h]
0x1400af1ac  mov     qword ptr [rsp+80h+var_60], rdi
0x1400af1b1  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400af1b6  mov     rax, [rbp+arg_38]
0x1400af1ba  mov     byte ptr [rax], 1
0x1400af1bd  xor     eax, eax
0x1400af1bf  jmp     loc_1400AF246
0x1400af1c4  mov     r13b, [rbp+arg_0]
0x1400af1c8  mov     r12b, 1
0x1400af1cb  lea     r15, [rsi+40h]
0x1400af1cf  cmp     [rbp+var_20], 0
0x1400af1d4  jz      short loc_1400AF1F6
0x1400af1d6  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400af1db  mov     r9d, 4000h
0x1400af1e1  lea     r8, [rbp+arg_8]
0x1400af1e5  lea     rdx, [rbp+var_20]
0x1400af1e9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400af1ed  mov     rax, [rax+10h]
0x1400af1f1  call    _guard_dispatch_icall
0x1400af1f6  mov     rdx, [rbp+var_10]; struct _VIDMM_POOL_BLOCK *
0x1400af1fa  test    rdx, rdx
0x1400af1fd  jz      short loc_1400AF20D
0x1400af1ff  test    rbx, rbx
0x1400af202  jz      short loc_1400AF20D
0x1400af204  mov     rcx, [rbx+48h]; this
0x1400af208  call    ?Free@VIDMM_LINEAR_POOL@@QEAAXPEAX@Z; VIDMM_LINEAR_POOL::Free(void *)
0x1400af20d  cmp     r13b, 1
0x1400af211  jnz     short loc_1400AF21E
0x1400af213  mov     rdx, rbx; struct _VIDMM_PROCESS_HEAP_BLOCK *
0x1400af216  mov     rcx, rsi; this
0x1400af219  call    ?FreeBlock@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_BLOCK@@@Z; VIDMM_PROCESS_HEAP::FreeBlock(_VIDMM_PROCESS_HEAP_BLOCK *)
0x1400af21e  test    rdi, rdi
0x1400af221  jz      short loc_1400AF235
0x1400af223  mov     rdx, rdi; Entry
0x1400af226  mov     rcx, r15; Lookaside
0x1400af229  call    cs:__imp_ExFreeToPagedLookasideList
0x1400af230  nop     dword ptr [rax+rax+00h]
0x1400af235  test    r12b, r12b
0x1400af238  jz      short loc_1400AF243
0x1400af23a  lea     rcx, [rsi+10h]; this
0x1400af23e  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400af243  mov     eax, r14d
0x1400af246  mov     rbx, [rsp+80h+arg_10]
0x1400af24e  add     rsp, 80h
0x1400af255  pop     r15
0x1400af257  pop     r14
0x1400af259  pop     r13
0x1400af25b  pop     r12
0x1400af25d  pop     rdi
0x1400af25e  pop     rsi
0x1400af25f  pop     rbp
0x1400af260  retn
```
