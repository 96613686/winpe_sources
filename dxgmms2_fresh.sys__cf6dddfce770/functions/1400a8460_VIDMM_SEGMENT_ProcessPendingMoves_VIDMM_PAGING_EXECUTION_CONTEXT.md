# VIDMM_SEGMENT::ProcessPendingMoves(VIDMM_PAGING_EXECUTION_CONTEXT *)

- ea: `0x1400a8460`
- end: `0x1400a88e3`
- name: `?ProcessPendingMoves@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z`
- size: `1155`
- prototype: `void __fastcall(VIDMM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a7e84`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x14002eae8`
- `0x14002ed18`
- `0x14003e344`
- `0x1400499f0`
- `0x140058f50`
- `0x140059030`
- `0x140097be8`
- `0x14009ecf4`
- `0x1400a8460`
- `0x1400d3fcc`
- `0x1400df0f4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a876a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a876a`
- `watchdog!WdLogSingleEntry3` at `0x1400a852d`
- `watchdog!WdLogSingleEntry3` at `0x1400a88a5`
- `watchdog!WdLogSingleEntry3` at `0x1400a852d`
- `watchdog!WdLogSingleEntry3` at `0x1400a88a5`
- `watchdog!WdLogSingleEntry5` at `0x1400a87f8`
- `watchdog!WdLogSingleEntry5` at `0x1400a87f8`
- `watchdog!WdLogSingleEntry0` at `0x1400a8854`
- `watchdog!WdLogSingleEntry0` at `0x1400a8854`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400a87d3`
- `dxgkrnl!g_IsInternalRelease` at `0x1400a87c7`

## string_xrefs

- `0x1400a8865`: `No allocations detected in VPR during pending move`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_SEGMENT::ProcessPendingMoves(VIDMM_SEGMENT *this, struct VIDMM_PAGING_EXECUTION_CONTEXT *a2)
{
  bool v4; // zf
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r15
  int v8; // eax
  __int64 v9; // rdx
  VIDMM_GLOBAL *v10; // r10
  bool v11; // r14
  __int64 v12; // r12
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // rcx
  unsigned __int64 v16; // r8
  UINT v17; // ecx
  __int64 v18; // rax
  DXG_DEFERRED_WORK_QUEUE *v19; // rcx
  SIZE_T v20; // rdx
  SIZE_T v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  int v26; // ecx
  int v27; // r8d
  _BYTE v28[8]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v29; // [rsp+58h] [rbp-41h] BYREF
  __int64 (__fastcall *v30)(VIDMM_SEGMENT *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *); // [rsp+60h] [rbp-39h] BYREF
  int v31; // [rsp+68h] [rbp-31h]
  int v32; // [rsp+6Ch] [rbp-2Dh]
  unsigned __int64 v33; // [rsp+70h] [rbp-29h] BYREF
  int v34; // [rsp+78h] [rbp-21h]
  int v35; // [rsp+7Ch] [rbp-1Dh]
  struct _DXGKARG_SETVIDEOPROTECTEDREGION v36; // [rsp+80h] [rbp-19h] BYREF

  if ( *((_BYTE *)this + 480) )
  {
    v4 = *((_QWORD *)this + 55) == 0;
    v5 = 40;
    *((_BYTE *)this + 480) = 0;
    v28[0] = 0;
    if ( !v4 )
      v5 = 424;
    v29 = 0;
    v6 = *((_QWORD *)this + 32);
    v7 = *(_QWORD *)((char *)this + v5);
    v33 = (unsigned __int64)VIDMM_SEGMENT::MoveOneResource;
    v35 = v32;
    v34 = 0;
    v8 = VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
           v6,
           (_DWORD)a2,
           0,
           v7,
           1,
           (__int64)&v33,
           (__int64)this,
           0,
           (__int64)&v29,
           (__int64)v28);
    if ( v8 >= 0 )
    {
      if ( *((_QWORD *)this + 55) )
      {
        v9 = *((unsigned __int16 *)this + 34);
        v10 = (VIDMM_GLOBAL *)*((_QWORD *)this + 1);
        v11 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 3) + 3120LL) + 352 * v9 + 16) & 8) != 0;
        if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 3) + 3120LL) + 352 * v9 + 16) & 8) != 0 )
        {
          VIDMM_GLOBAL::FlushPagingBufferInternal(v10, a2, v9, 0, 0, 0);
          VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*((VIDMM_GLOBAL **)this + 1), a2, *((unsigned __int16 *)this + 34));
          *(_BYTE *)(*((_QWORD *)this + 1) + 37231LL) = 1;
        }
        v12 = *((_QWORD *)this + 54);
        v13 = *((_QWORD *)this + 32);
        v30 = VIDMM_SEGMENT::MoveOneResource;
        v31 = 0;
        v14 = VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
                v13,
                (_DWORD)a2,
                v7,
                v12,
                1,
                (__int64)&v30,
                (__int64)this,
                0,
                (__int64)&v29,
                (__int64)v28);
        if ( v11 )
        {
          VIDMM_GLOBAL::FlushPagingBufferInternal(
            *((VIDMM_GLOBAL **)this + 1),
            a2,
            *((unsigned __int16 *)this + 34),
            0,
            0,
            1);
          VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*((VIDMM_GLOBAL **)this + 1), a2, *((unsigned __int16 *)this + 34));
          *(_BYTE *)(*((_QWORD *)this + 1) + 37231LL) = 0;
        }
        v15 = *((_QWORD *)this + 32);
        v30 = (__int64 (__fastcall *)(VIDMM_SEGMENT *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *))VIDMM_SEGMENT::CheckLowestAddress;
        v33 = 0;
        v31 = 0;
        if ( (unsigned int)VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
                             v15,
                             (_DWORD)a2,
                             v7,
                             v12,
                             0,
                             (__int64)&v30,
                             (__int64)this,
                             (__int64)&v33,
                             (__int64)&v29,
                             (__int64)v28) == -1073741823 )
        {
          v16 = *((_QWORD *)this + 53);
          v33 &= ~*((_QWORD *)this + 51);
          if ( v33 > v16 )
          {
            v36.PhysicalAdapterIndex = *((unsigned __int16 *)this + 34);
            *(_QWORD *)&v36.VprIndex = 0;
            v17 = VIDMM_SEGMENT::DriverId(this);
            v36.CurrentSize = *((_QWORD *)this + 55);
            v18 = *((_QWORD *)this + 54);
            v36.SegmentIndex = v17;
            v19 = (DXG_DEFERRED_WORK_QUEUE *)(*((_QWORD *)this + 1) + 37440LL);
            v36.NewSize = v18 - v20;
            *((_QWORD *)this + 55) = v18 - v20;
            v36.CurrentStartOffset = v21;
            v36.NewStartOffset = v20;
            *((_QWORD *)this + 53) = v20;
            if ( (unsigned int)DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems(v19) )
            {
              if ( (byte_140087201 & 1) != 0 )
                McTemplateK0q_EtwWriteTransfer(v22, &EventPerformanceWarning, v23, 24);
              KeWaitForSingleObject((PVOID)(*((_QWORD *)this + 1) + 37488LL), Executive, 0, 0, 0);
            }
            (*(void (__fastcall **)(_QWORD, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(**((_QWORD **)this + 2) + 200LL))(
              *((_QWORD *)this + 2),
              a2);
            VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(
              *((VIDMM_GLOBAL **)this + 1),
              a2,
              *((unsigned __int16 *)this + 34));
            VIDMM_SEGMENT::CheckFreeVPRReserve(this, &v36);
            v14 = ADAPTER_RENDER::DdiSetVideoProtectedRegion(
                    *(ADAPTER_RENDER **)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 3256LL),
                    &v36);
            if ( v14 < 0 && g_IsInternalRelease )
            {
              g_DxgMmsBugcheckExportIndex = 1;
              WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
              WdLogGlobalForLineNumber = 227;
            }
            if ( (byte_140087201 & 1) != 0 )
              McTemplateK0qqqxxp_EtwWriteTransfer(
                *(_QWORD *)(*((_QWORD *)this + 1) + 24LL),
                v24,
                v25,
                v36.PhysicalAdapterIndex,
                v36.SegmentIndex,
                v36.VprIndex,
                v36.NewStartOffset,
                v36.NewSize,
                *(_QWORD *)(*((_QWORD *)this + 1) + 24LL));
          }
        }
        else
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 6681;
          DxgkLogInternalTriageEvent(
            v26,
            0x40000,
            v27,
            (unsigned int)L"No allocations detected in VPR during pending move",
            6681,
            0,
            0,
            0);
        }
        if ( v14 < 0 )
        {
          WdLogSingleEntry3(3, v29, v14, v28[0]);
          WdLogGlobalForLineNumber = 6698;
        }
      }
    }
    else
    {
      WdLogSingleEntry3(3, v29, v8, v28[0]);
      WdLogGlobalForLineNumber = 6498;
    }
  }
}

```

## disassembly

```asm
0x1400a8460  mov     [rsp-8+arg_10], rbx
0x1400a8465  push    rbp
0x1400a8466  push    rsi
0x1400a8467  push    rdi
0x1400a8468  push    r12
0x1400a846a  push    r13
0x1400a846c  push    r14
0x1400a846e  push    r15
0x1400a8470  lea     rbp, [rsp-27h]
0x1400a8475  sub     rsp, 0C0h
0x1400a847c  mov     rax, cs:__security_cookie
0x1400a8483  xor     rax, rsp
0x1400a8486  mov     [rbp+57h+var_40], rax
0x1400a848a  xor     r13d, r13d
0x1400a848d  mov     rdi, rdx
0x1400a8490  mov     rbx, rcx
0x1400a8493  cmp     [rcx+1E0h], r13b
0x1400a849a  jz      loc_1400A88BB
0x1400a84a0  cmp     [rbx+1B8h], r13
0x1400a84a7  lea     eax, [r13+28h]
0x1400a84ab  mov     [rcx+1E0h], r13b
0x1400a84b2  lea     esi, [r13+1]
0x1400a84b6  mov     ecx, 1A8h
0x1400a84bb  mov     [rbp+57h+var_A0], r13b
0x1400a84bf  cmovnz  eax, ecx
0x1400a84c2  mov     [rbp+57h+var_98], r13
0x1400a84c6  mov     rcx, [rbx+100h]
0x1400a84cd  xor     r8d, r8d
0x1400a84d0  mov     r15, [rax+rbx]
0x1400a84d4  lea     rax, ?MoveOneResource@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::MoveOneResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400a84db  mov     [rbp+57h+var_80], rax
0x1400a84df  mov     r9, r15
0x1400a84e2  mov     eax, [rbp+57h+var_84]
0x1400a84e5  mov     [rbp+57h+var_74], eax
0x1400a84e8  lea     rax, [rbp+57h+var_A0]
0x1400a84ec  mov     [rsp+0F0h+var_A8], rax
0x1400a84f1  lea     rax, [rbp+57h+var_98]
0x1400a84f5  mov     [rsp+0F0h+var_B0], rax
0x1400a84fa  lea     rax, [rbp+57h+var_80]
0x1400a84fe  mov     [rsp+0F0h+var_B8], r13
0x1400a8503  mov     [rsp+0F0h+var_C0], rbx
0x1400a8508  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400a850d  mov     dword ptr [rsp+0F0h+Timeout], esi
0x1400a8511  mov     [rbp+57h+var_78], r13d
0x1400a8515  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400a851a  test    eax, eax
0x1400a851c  jns     short loc_1400A8548
0x1400a851e  movzx   r9d, [rbp+57h+var_A0]
0x1400a8523  lea     ecx, [rsi+2]
0x1400a8526  mov     rdx, [rbp+57h+var_98]
0x1400a852a  movsxd  r8, eax
0x1400a852d  call    cs:__imp_WdLogSingleEntry3
0x1400a8534  nop     dword ptr [rax+rax+00h]
0x1400a8539  mov     cs:WdLogGlobalForLineNumber, 1962h
0x1400a8543  jmp     loc_1400A88BB
0x1400a8548  cmp     [rbx+1B8h], r13
0x1400a854f  jz      loc_1400A88BB
0x1400a8555  movzx   edx, word ptr [rbx+44h]
0x1400a8559  mov     r10, [rbx+8]
0x1400a855d  imul    rcx, rdx, 160h
0x1400a8564  mov     rax, [r10+18h]
0x1400a8568  mov     rax, [rax+0C30h]
0x1400a856f  mov     r14d, [rax+rcx+10h]
0x1400a8574  shr     r14d, 3
0x1400a8578  and     r14b, sil
0x1400a857b  jz      short loc_1400A85B4
0x1400a857d  mov     r8d, edx; unsigned int
0x1400a8580  mov     [rsp+0F0h+var_C8], r13b; bool
0x1400a8585  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a8588  mov     byte ptr [rsp+0F0h+Timeout], r13b; bool
0x1400a858d  xor     r9d, r9d; bool
0x1400a8590  mov     rcx, r10; this
0x1400a8593  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a8598  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a859d  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a85a0  mov     rcx, [rbx+8]; this
0x1400a85a4  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a85a9  mov     rax, [rbx+8]
0x1400a85ad  mov     [rax+916Fh], sil
0x1400a85b4  mov     r12, [rbx+1B0h]
0x1400a85bb  lea     rax, ?MoveOneResource@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::MoveOneResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400a85c2  mov     rcx, [rbx+100h]
0x1400a85c9  mov     r9, r12
0x1400a85cc  mov     [rbp+57h+var_90], rax
0x1400a85d0  mov     r8, r15
0x1400a85d3  mov     eax, [rbp+57h+var_84]
0x1400a85d6  mov     rdx, rdi
0x1400a85d9  mov     [rbp+57h+var_84], eax
0x1400a85dc  lea     rax, [rbp+57h+var_A0]
0x1400a85e0  mov     [rsp+0F0h+var_A8], rax
0x1400a85e5  lea     rax, [rbp+57h+var_98]
0x1400a85e9  mov     [rsp+0F0h+var_B0], rax
0x1400a85ee  lea     rax, [rbp+57h+var_90]
0x1400a85f2  mov     [rsp+0F0h+var_B8], r13
0x1400a85f7  mov     [rsp+0F0h+var_C0], rbx
0x1400a85fc  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400a8601  mov     dword ptr [rsp+0F0h+Timeout], esi
0x1400a8605  mov     [rbp+57h+var_88], r13d
0x1400a8609  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400a860e  mov     esi, eax
0x1400a8610  test    r14b, r14b
0x1400a8613  jz      short loc_1400A864F
0x1400a8615  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a861a  xor     r9d, r9d; bool
0x1400a861d  mov     rcx, [rbx+8]; this
0x1400a8621  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a8624  mov     [rsp+0F0h+var_C8], 1; bool
0x1400a8629  mov     byte ptr [rsp+0F0h+Timeout], r13b; bool
0x1400a862e  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a8633  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a8638  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a863b  mov     rcx, [rbx+8]; this
0x1400a863f  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a8644  mov     rax, [rbx+8]
0x1400a8648  mov     [rax+916Fh], r13b
0x1400a864f  mov     rcx, [rbx+100h]
0x1400a8656  lea     rax, ?CheckLowestAddress@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::CheckLowestAddress(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400a865d  mov     [rbp+57h+var_90], rax
0x1400a8661  mov     r9, r12
0x1400a8664  mov     eax, [rbp+57h+var_84]
0x1400a8667  mov     r8, r15
0x1400a866a  mov     [rbp+57h+var_84], eax
0x1400a866d  mov     rdx, rdi
0x1400a8670  lea     rax, [rbp+57h+var_A0]
0x1400a8674  mov     [rbp+57h+var_80], r13
0x1400a8678  mov     [rsp+0F0h+var_A8], rax
0x1400a867d  lea     rax, [rbp+57h+var_98]
0x1400a8681  mov     [rsp+0F0h+var_B0], rax
0x1400a8686  lea     rax, [rbp+57h+var_80]
0x1400a868a  mov     [rsp+0F0h+var_B8], rax
0x1400a868f  lea     rax, [rbp+57h+var_90]
0x1400a8693  mov     [rsp+0F0h+var_C0], rbx
0x1400a8698  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400a869d  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x1400a86a2  mov     [rbp+57h+var_88], r13d
0x1400a86a6  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400a86ab  cmp     eax, 0C0000001h
0x1400a86b0  jnz     loc_1400A884F
0x1400a86b6  mov     rdx, [rbp+57h+var_80]
0x1400a86ba  mov     rax, [rbx+198h]
0x1400a86c1  mov     r8, [rbx+1A8h]
0x1400a86c8  not     rax
0x1400a86cb  and     rdx, rax
0x1400a86ce  mov     [rbp+57h+var_80], rdx
0x1400a86d2  cmp     rdx, r8
0x1400a86d5  jbe     loc_1400A8890
0x1400a86db  movzx   eax, word ptr [rbx+44h]
0x1400a86df  mov     rcx, rbx; this
0x1400a86e2  mov     [rbp+57h+var_70.PhysicalAdapterIndex], eax
0x1400a86e5  mov     qword ptr [rbp+57h+var_70.VprIndex], r13
0x1400a86e9  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a86ee  movzx   ecx, ax
0x1400a86f1  mov     rax, [rbx+1B8h]
0x1400a86f8  mov     [rbp+57h+var_70.CurrentSize], rax
0x1400a86fc  mov     rax, [rbx+1B0h]
0x1400a8703  mov     [rbp+57h+var_70.SegmentIndex], ecx
0x1400a8706  sub     rax, rdx
0x1400a8709  mov     rcx, [rbx+8]
0x1400a870d  add     rcx, 9240h; this
0x1400a8714  mov     [rbp+57h+var_70.NewSize], rax
0x1400a8718  mov     [rbx+1B8h], rax
0x1400a871f  mov     [rbp+57h+var_70.CurrentStartOffset], r8
0x1400a8723  mov     [rbp+57h+var_70.NewStartOffset], rdx
0x1400a8727  mov     [rbx+1A8h], rdx
0x1400a872e  call    ?GetNumWorkItems@DXG_DEFERRED_WORK_QUEUE@@QEBAJXZ; DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems(void)
0x1400a8733  test    eax, eax
0x1400a8735  jz      short loc_1400A8776
0x1400a8737  test    cs:byte_140087201, 1
0x1400a873e  jz      short loc_1400A8752
0x1400a8740  mov     r9d, 18h
0x1400a8746  lea     rdx, EventPerformanceWarning
0x1400a874d  call    McTemplateK0q_EtwWriteTransfer
0x1400a8752  mov     rcx, [rbx+8]
0x1400a8756  xor     r9d, r9d; Alertable
0x1400a8759  add     rcx, 9270h; Object
0x1400a8760  mov     [rsp+0F0h+Timeout], r13; Timeout
0x1400a8765  xor     r8d, r8d; WaitMode
0x1400a8768  xor     edx, edx; WaitReason
0x1400a876a  call    cs:__imp_KeWaitForSingleObject
0x1400a8771  nop     dword ptr [rax+rax+00h]
0x1400a8776  mov     rcx, [rbx+10h]
0x1400a877a  mov     rdx, rdi
0x1400a877d  mov     rax, [rcx]
0x1400a8780  mov     rax, [rax+0C8h]
0x1400a8787  call    _guard_dispatch_icall
0x1400a878c  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a8791  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a8794  mov     rcx, [rbx+8]; this
0x1400a8798  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a879d  lea     rdx, [rbp+57h+var_70]; struct _DXGKARG_SETVIDEOPROTECTEDREGION *
0x1400a87a1  mov     rcx, rbx; this
0x1400a87a4  call    ?CheckFreeVPRReserve@VIDMM_SEGMENT@@QEAA_NPEAU_DXGKARG_SETVIDEOPROTECTEDREGION@@@Z; VIDMM_SEGMENT::CheckFreeVPRReserve(_DXGKARG_SETVIDEOPROTECTEDREGION *)
0x1400a87a9  mov     rax, [rbx+8]
0x1400a87ad  lea     rdx, [rbp+57h+var_70]; struct _DXGKARG_SETVIDEOPROTECTEDREGION *
0x1400a87b1  mov     rcx, [rax+18h]
0x1400a87b5  mov     rcx, [rcx+0CB8h]; this
0x1400a87bc  call    ?DdiSetVideoProtectedRegion@ADAPTER_RENDER@@QEAAJPEBU_DXGKARG_SETVIDEOPROTECTEDREGION@@@Z; ADAPTER_RENDER::DdiSetVideoProtectedRegion(_DXGKARG_SETVIDEOPROTECTEDREGION const *)
0x1400a87c1  mov     esi, eax
0x1400a87c3  test    eax, eax
0x1400a87c5  jns     short loc_1400A880E
0x1400a87c7  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400a87ce  cmp     [rax], r13b
0x1400a87d1  jz      short loc_1400A880E
0x1400a87d3  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400a87da  mov     dword ptr [rax], 1
0x1400a87e0  xor     r9d, r9d
0x1400a87e3  mov     qword ptr [rsp+0F0h+var_C8], r13
0x1400a87e8  mov     edx, 10Eh
0x1400a87ed  mov     [rsp+0F0h+Timeout], r13
0x1400a87f2  xor     ecx, ecx
0x1400a87f4  lea     r8d, [r9+9]
0x1400a87f8  call    cs:__imp_WdLogSingleEntry5
0x1400a87ff  nop     dword ptr [rax+rax+00h]
0x1400a8804  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400a880e  test    cs:byte_140087201, 1
0x1400a8815  jz      short loc_1400A8890
0x1400a8817  mov     rax, [rbx+8]
0x1400a881b  mov     r9d, [rbp+57h+var_70.PhysicalAdapterIndex]
0x1400a881f  mov     rcx, [rax+18h]
0x1400a8823  mov     rax, [rbp+57h+var_70.NewSize]
0x1400a8827  mov     [rsp+0F0h+var_B0], rcx
0x1400a882c  mov     [rsp+0F0h+var_B8], rax
0x1400a8831  mov     rax, [rbp+57h+var_70.NewStartOffset]
0x1400a8835  mov     [rsp+0F0h+var_C0], rax
0x1400a883a  mov     eax, [rbp+57h+var_70.VprIndex]
0x1400a883d  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400a8841  mov     eax, [rbp+57h+var_70.SegmentIndex]
0x1400a8844  mov     dword ptr [rsp+0F0h+Timeout], eax
0x1400a8848  call    McTemplateK0qqqxxp_EtwWriteTransfer
0x1400a884d  jmp     short loc_1400A8890
0x1400a884f  mov     ecx, 1
0x1400a8854  call    cs:__imp_WdLogSingleEntry0
0x1400a885b  nop     dword ptr [rax+rax+00h]
0x1400a8860  mov     [rsp+0F0h+var_B8], r13
0x1400a8865  lea     r9, aNoAllocationsD; "No allocations detected in VPR during p"...
0x1400a886c  mov     eax, 1A19h
0x1400a8871  mov     [rsp+0F0h+var_C0], r13
0x1400a8876  mov     qword ptr [rsp+0F0h+var_C8], r13
0x1400a887b  mov     edx, 40000h
0x1400a8880  mov     cs:WdLogGlobalForLineNumber, eax
0x1400a8886  mov     [rsp+0F0h+Timeout], rax
0x1400a888b  call    DxgkLogInternalTriageEvent
0x1400a8890  test    esi, esi
0x1400a8892  jns     short loc_1400A88BB
0x1400a8894  movzx   r9d, [rbp+57h+var_A0]
0x1400a8899  mov     ecx, 3
0x1400a889e  mov     rdx, [rbp+57h+var_98]
0x1400a88a2  movsxd  r8, esi
0x1400a88a5  call    cs:__imp_WdLogSingleEntry3
0x1400a88ac  nop     dword ptr [rax+rax+00h]
0x1400a88b1  mov     cs:WdLogGlobalForLineNumber, 1A2Ah
0x1400a88bb  mov     rcx, [rbp+57h+var_40]
0x1400a88bf  xor     rcx, rsp; StackCookie
0x1400a88c2  call    __security_check_cookie
0x1400a88c7  mov     rbx, [rsp+0F0h+arg_10]
0x1400a88cf  add     rsp, 0C0h
0x1400a88d6  pop     r15
0x1400a88d8  pop     r14
0x1400a88da  pop     r13
0x1400a88dc  pop     r12
0x1400a88de  pop     rdi
0x1400a88df  pop     rsi
0x1400a88e0  pop     rbp
0x1400a88e1  retn
```
