# VIDMM_SEGMENT::ProcessPendingMoves(VIDMM_PAGING_EXECUTION_CONTEXT *)

- ea: `0x1400a75cc`
- end: `0x1400a7a4f`
- name: `?ProcessPendingMoves@VIDMM_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z`
- size: `1155`
- prototype: `void __fastcall(VIDMM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009d594`

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x140030f08`
- `0x140031138`
- `0x14003f9c4`
- `0x140049320`
- `0x140058680`
- `0x140058760`
- `0x14009b1ac`
- `0x14009df00`
- `0x1400a75cc`
- `0x1400ce13c`
- `0x1400d6c94`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a78d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a78d6`
- `watchdog!WdLogSingleEntry3` at `0x1400a7699`
- `watchdog!WdLogSingleEntry3` at `0x1400a7a11`
- `watchdog!WdLogSingleEntry3` at `0x1400a7699`
- `watchdog!WdLogSingleEntry3` at `0x1400a7a11`
- `watchdog!WdLogSingleEntry5` at `0x1400a7964`
- `watchdog!WdLogSingleEntry5` at `0x1400a7964`
- `watchdog!WdLogSingleEntry0` at `0x1400a79c0`
- `watchdog!WdLogSingleEntry0` at `0x1400a79c0`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400a793f`
- `dxgkrnl!g_IsInternalRelease` at `0x1400a7933`

## string_xrefs

- `0x1400a79d1`: `No allocations detected in VPR during pending move`

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
  int v24; // edx
  int v25; // r8d
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
        v11 = (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 3) + 3104LL) + 352 * v9 + 16) & 8) != 0;
        if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 3) + 3104LL) + 352 * v9 + 16) & 8) != 0 )
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
              if ( (byte_140086201 & 1) != 0 )
                McTemplateK0q_EtwWriteTransfer(v22, EventPerformanceWarning, v23, 24);
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
                    *(ADAPTER_RENDER **)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 3240LL),
                    &v36);
            if ( v14 < 0 && g_IsInternalRelease )
            {
              g_DxgMmsBugcheckExportIndex = 1;
              WdLogSingleEntry5(0, 270, 9);
              WdLogGlobalForLineNumber = 222;
            }
            if ( (byte_140086201 & 1) != 0 )
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
          WdLogGlobalForLineNumber = 6089;
          DxgkLogInternalTriageEvent(
            v26,
            0x40000,
            v27,
            (unsigned int)L"No allocations detected in VPR during pending move",
            6089,
            0,
            0,
            0);
        }
        if ( v14 < 0 )
        {
          WdLogSingleEntry3(3, v29, v14, v28[0]);
          WdLogGlobalForLineNumber = 6106;
        }
      }
    }
    else
    {
      WdLogSingleEntry3(3, v29, v8, v28[0]);
      WdLogGlobalForLineNumber = 5906;
    }
  }
}

```

## disassembly

```asm
0x1400a75cc  mov     [rsp-8+arg_10], rbx
0x1400a75d1  push    rbp
0x1400a75d2  push    rsi
0x1400a75d3  push    rdi
0x1400a75d4  push    r12
0x1400a75d6  push    r13
0x1400a75d8  push    r14
0x1400a75da  push    r15
0x1400a75dc  lea     rbp, [rsp-27h]
0x1400a75e1  sub     rsp, 0C0h
0x1400a75e8  mov     rax, cs:__security_cookie
0x1400a75ef  xor     rax, rsp
0x1400a75f2  mov     [rbp+57h+var_40], rax
0x1400a75f6  xor     r13d, r13d
0x1400a75f9  mov     rdi, rdx
0x1400a75fc  mov     rbx, rcx
0x1400a75ff  cmp     [rcx+1E0h], r13b
0x1400a7606  jz      loc_1400A7A27
0x1400a760c  cmp     [rbx+1B8h], r13
0x1400a7613  lea     eax, [r13+28h]
0x1400a7617  mov     [rcx+1E0h], r13b
0x1400a761e  lea     esi, [r13+1]
0x1400a7622  mov     ecx, 1A8h
0x1400a7627  mov     [rbp+57h+var_A0], r13b
0x1400a762b  cmovnz  eax, ecx
0x1400a762e  mov     [rbp+57h+var_98], r13
0x1400a7632  mov     rcx, [rbx+100h]
0x1400a7639  xor     r8d, r8d
0x1400a763c  mov     r15, [rax+rbx]
0x1400a7640  lea     rax, ?MoveOneResource@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::MoveOneResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400a7647  mov     [rbp+57h+var_80], rax
0x1400a764b  mov     r9, r15
0x1400a764e  mov     eax, [rbp+57h+var_84]
0x1400a7651  mov     [rbp+57h+var_74], eax
0x1400a7654  lea     rax, [rbp+57h+var_A0]
0x1400a7658  mov     [rsp+0F0h+var_A8], rax
0x1400a765d  lea     rax, [rbp+57h+var_98]
0x1400a7661  mov     [rsp+0F0h+var_B0], rax
0x1400a7666  lea     rax, [rbp+57h+var_80]
0x1400a766a  mov     [rsp+0F0h+var_B8], r13
0x1400a766f  mov     [rsp+0F0h+var_C0], rbx
0x1400a7674  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400a7679  mov     dword ptr [rsp+0F0h+Timeout], esi
0x1400a767d  mov     [rbp+57h+var_78], r13d
0x1400a7681  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400a7686  test    eax, eax
0x1400a7688  jns     short loc_1400A76B4
0x1400a768a  movzx   r9d, [rbp+57h+var_A0]
0x1400a768f  lea     ecx, [rsi+2]
0x1400a7692  mov     rdx, [rbp+57h+var_98]
0x1400a7696  movsxd  r8, eax
0x1400a7699  call    cs:__imp_WdLogSingleEntry3
0x1400a76a0  nop     dword ptr [rax+rax+00h]
0x1400a76a5  mov     cs:WdLogGlobalForLineNumber, 1712h
0x1400a76af  jmp     loc_1400A7A27
0x1400a76b4  cmp     [rbx+1B8h], r13
0x1400a76bb  jz      loc_1400A7A27
0x1400a76c1  movzx   edx, word ptr [rbx+44h]
0x1400a76c5  mov     r10, [rbx+8]
0x1400a76c9  imul    rcx, rdx, 160h
0x1400a76d0  mov     rax, [r10+18h]
0x1400a76d4  mov     rax, [rax+0C20h]
0x1400a76db  mov     r14d, [rax+rcx+10h]
0x1400a76e0  shr     r14d, 3
0x1400a76e4  and     r14b, sil
0x1400a76e7  jz      short loc_1400A7720
0x1400a76e9  mov     r8d, edx; unsigned int
0x1400a76ec  mov     [rsp+0F0h+var_C8], r13b; bool
0x1400a76f1  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a76f4  mov     byte ptr [rsp+0F0h+Timeout], r13b; bool
0x1400a76f9  xor     r9d, r9d; bool
0x1400a76fc  mov     rcx, r10; this
0x1400a76ff  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a7704  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a7709  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a770c  mov     rcx, [rbx+8]; this
0x1400a7710  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a7715  mov     rax, [rbx+8]
0x1400a7719  mov     [rax+916Fh], sil
0x1400a7720  mov     r12, [rbx+1B0h]
0x1400a7727  lea     rax, ?MoveOneResource@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::MoveOneResource(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400a772e  mov     rcx, [rbx+100h]
0x1400a7735  mov     r9, r12
0x1400a7738  mov     [rbp+57h+var_90], rax
0x1400a773c  mov     r8, r15
0x1400a773f  mov     eax, [rbp+57h+var_84]
0x1400a7742  mov     rdx, rdi
0x1400a7745  mov     [rbp+57h+var_84], eax
0x1400a7748  lea     rax, [rbp+57h+var_A0]
0x1400a774c  mov     [rsp+0F0h+var_A8], rax
0x1400a7751  lea     rax, [rbp+57h+var_98]
0x1400a7755  mov     [rsp+0F0h+var_B0], rax
0x1400a775a  lea     rax, [rbp+57h+var_90]
0x1400a775e  mov     [rsp+0F0h+var_B8], r13
0x1400a7763  mov     [rsp+0F0h+var_C0], rbx
0x1400a7768  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400a776d  mov     dword ptr [rsp+0F0h+Timeout], esi
0x1400a7771  mov     [rbp+57h+var_88], r13d
0x1400a7775  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400a777a  mov     esi, eax
0x1400a777c  test    r14b, r14b
0x1400a777f  jz      short loc_1400A77BB
0x1400a7781  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a7786  xor     r9d, r9d; bool
0x1400a7789  mov     rcx, [rbx+8]; this
0x1400a778d  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a7790  mov     [rsp+0F0h+var_C8], 1; bool
0x1400a7795  mov     byte ptr [rsp+0F0h+Timeout], r13b; bool
0x1400a779a  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a779f  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a77a4  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a77a7  mov     rcx, [rbx+8]; this
0x1400a77ab  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a77b0  mov     rax, [rbx+8]
0x1400a77b4  mov     [rax+916Fh], r13b
0x1400a77bb  mov     rcx, [rbx+100h]
0x1400a77c2  lea     rax, ?CheckLowestAddress@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@Z; VIDMM_SEGMENT::CheckLowestAddress(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *)
0x1400a77c9  mov     [rbp+57h+var_90], rax
0x1400a77cd  mov     r9, r12
0x1400a77d0  mov     eax, [rbp+57h+var_84]
0x1400a77d3  mov     r8, r15
0x1400a77d6  mov     [rbp+57h+var_84], eax
0x1400a77d9  mov     rdx, rdi
0x1400a77dc  lea     rax, [rbp+57h+var_A0]
0x1400a77e0  mov     [rbp+57h+var_80], r13
0x1400a77e4  mov     [rsp+0F0h+var_A8], rax
0x1400a77e9  lea     rax, [rbp+57h+var_98]
0x1400a77ed  mov     [rsp+0F0h+var_B0], rax
0x1400a77f2  lea     rax, [rbp+57h+var_80]
0x1400a77f6  mov     [rsp+0F0h+var_B8], rax
0x1400a77fb  lea     rax, [rbp+57h+var_90]
0x1400a77ff  mov     [rsp+0F0h+var_C0], rbx
0x1400a7804  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1400a7809  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x1400a780e  mov     [rbp+57h+var_88], r13d
0x1400a7812  call    ?DirectedIterateAllocatedBlocksInRange@VIDMM_LINEAR_POOL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@_K1W4VIDMM_DEFRAGMENT_DIRECTION@@P8VIDMM_SEGMENT@@EAAJ0PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@PEA_NPEAX@ZPEAV4@5PEAPEAU5@4@Z; VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(VIDMM_PAGING_EXECUTION_CONTEXT *,unsigned __int64,unsigned __int64,VIDMM_DEFRAGMENT_DIRECTION,long (VIDMM_SEGMENT::*)(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool *,void *),VIDMM_SEGMENT *,void *,VIDMM_PHYSICAL_ALLOC_LEGACY * *,bool *)
0x1400a7817  cmp     eax, 0C0000001h
0x1400a781c  jnz     loc_1400A79BB
0x1400a7822  mov     rdx, [rbp+57h+var_80]
0x1400a7826  mov     rax, [rbx+198h]
0x1400a782d  mov     r8, [rbx+1A8h]
0x1400a7834  not     rax
0x1400a7837  and     rdx, rax
0x1400a783a  mov     [rbp+57h+var_80], rdx
0x1400a783e  cmp     rdx, r8
0x1400a7841  jbe     loc_1400A79FC
0x1400a7847  movzx   eax, word ptr [rbx+44h]
0x1400a784b  mov     rcx, rbx; this
0x1400a784e  mov     [rbp+57h+var_70.PhysicalAdapterIndex], eax
0x1400a7851  mov     qword ptr [rbp+57h+var_70.VprIndex], r13
0x1400a7855  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a785a  movzx   ecx, ax
0x1400a785d  mov     rax, [rbx+1B8h]
0x1400a7864  mov     [rbp+57h+var_70.CurrentSize], rax
0x1400a7868  mov     rax, [rbx+1B0h]
0x1400a786f  mov     [rbp+57h+var_70.SegmentIndex], ecx
0x1400a7872  sub     rax, rdx
0x1400a7875  mov     rcx, [rbx+8]
0x1400a7879  add     rcx, 9240h; this
0x1400a7880  mov     [rbp+57h+var_70.NewSize], rax
0x1400a7884  mov     [rbx+1B8h], rax
0x1400a788b  mov     [rbp+57h+var_70.CurrentStartOffset], r8
0x1400a788f  mov     [rbp+57h+var_70.NewStartOffset], rdx
0x1400a7893  mov     [rbx+1A8h], rdx
0x1400a789a  call    ?GetNumWorkItems@DXG_DEFERRED_WORK_QUEUE@@QEBAJXZ; DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems(void)
0x1400a789f  test    eax, eax
0x1400a78a1  jz      short loc_1400A78E2
0x1400a78a3  test    cs:byte_140086201, 1
0x1400a78aa  jz      short loc_1400A78BE
0x1400a78ac  mov     r9d, 18h
0x1400a78b2  lea     rdx, EventPerformanceWarning
0x1400a78b9  call    McTemplateK0q_EtwWriteTransfer
0x1400a78be  mov     rcx, [rbx+8]
0x1400a78c2  xor     r9d, r9d; Alertable
0x1400a78c5  add     rcx, 9270h; Object
0x1400a78cc  mov     [rsp+0F0h+Timeout], r13; Timeout
0x1400a78d1  xor     r8d, r8d; WaitMode
0x1400a78d4  xor     edx, edx; WaitReason
0x1400a78d6  call    cs:__imp_KeWaitForSingleObject
0x1400a78dd  nop     dword ptr [rax+rax+00h]
0x1400a78e2  mov     rcx, [rbx+10h]
0x1400a78e6  mov     rdx, rdi
0x1400a78e9  mov     rax, [rcx]
0x1400a78ec  mov     rax, [rax+0C8h]
0x1400a78f3  call    _guard_dispatch_icall
0x1400a78f8  movzx   r8d, word ptr [rbx+44h]; unsigned int
0x1400a78fd  mov     rdx, rdi; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a7900  mov     rcx, [rbx+8]; this
0x1400a7904  call    ?WaitForAllPagingEnginesIdle@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a7909  lea     rdx, [rbp+57h+var_70]; struct _DXGKARG_SETVIDEOPROTECTEDREGION *
0x1400a790d  mov     rcx, rbx; this
0x1400a7910  call    ?CheckFreeVPRReserve@VIDMM_SEGMENT@@QEAA_NPEAU_DXGKARG_SETVIDEOPROTECTEDREGION@@@Z; VIDMM_SEGMENT::CheckFreeVPRReserve(_DXGKARG_SETVIDEOPROTECTEDREGION *)
0x1400a7915  mov     rax, [rbx+8]
0x1400a7919  lea     rdx, [rbp+57h+var_70]; struct _DXGKARG_SETVIDEOPROTECTEDREGION *
0x1400a791d  mov     rcx, [rax+18h]
0x1400a7921  mov     rcx, [rcx+0CA8h]; this
0x1400a7928  call    ?DdiSetVideoProtectedRegion@ADAPTER_RENDER@@QEAAJPEBU_DXGKARG_SETVIDEOPROTECTEDREGION@@@Z; ADAPTER_RENDER::DdiSetVideoProtectedRegion(_DXGKARG_SETVIDEOPROTECTEDREGION const *)
0x1400a792d  mov     esi, eax
0x1400a792f  test    eax, eax
0x1400a7931  jns     short loc_1400A797A
0x1400a7933  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400a793a  cmp     [rax], r13b
0x1400a793d  jz      short loc_1400A797A
0x1400a793f  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400a7946  mov     dword ptr [rax], 1
0x1400a794c  xor     r9d, r9d
0x1400a794f  mov     qword ptr [rsp+0F0h+var_C8], r13
0x1400a7954  mov     edx, 10Eh
0x1400a7959  mov     [rsp+0F0h+Timeout], r13
0x1400a795e  xor     ecx, ecx
0x1400a7960  lea     r8d, [r9+9]
0x1400a7964  call    cs:__imp_WdLogSingleEntry5
0x1400a796b  nop     dword ptr [rax+rax+00h]
0x1400a7970  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400a797a  test    cs:byte_140086201, 1
0x1400a7981  jz      short loc_1400A79FC
0x1400a7983  mov     rax, [rbx+8]
0x1400a7987  mov     r9d, [rbp+57h+var_70.PhysicalAdapterIndex]
0x1400a798b  mov     rcx, [rax+18h]
0x1400a798f  mov     rax, [rbp+57h+var_70.NewSize]
0x1400a7993  mov     [rsp+0F0h+var_B0], rcx
0x1400a7998  mov     [rsp+0F0h+var_B8], rax
0x1400a799d  mov     rax, [rbp+57h+var_70.NewStartOffset]
0x1400a79a1  mov     [rsp+0F0h+var_C0], rax
0x1400a79a6  mov     eax, [rbp+57h+var_70.VprIndex]
0x1400a79a9  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400a79ad  mov     eax, [rbp+57h+var_70.SegmentIndex]
0x1400a79b0  mov     dword ptr [rsp+0F0h+Timeout], eax
0x1400a79b4  call    McTemplateK0qqqxxp_EtwWriteTransfer
0x1400a79b9  jmp     short loc_1400A79FC
0x1400a79bb  mov     ecx, 1
0x1400a79c0  call    cs:__imp_WdLogSingleEntry0
0x1400a79c7  nop     dword ptr [rax+rax+00h]
0x1400a79cc  mov     [rsp+0F0h+var_B8], r13
0x1400a79d1  lea     r9, aNoAllocationsD; "No allocations detected in VPR during p"...
0x1400a79d8  mov     eax, 17C9h
0x1400a79dd  mov     [rsp+0F0h+var_C0], r13
0x1400a79e2  mov     qword ptr [rsp+0F0h+var_C8], r13
0x1400a79e7  mov     edx, 40000h
0x1400a79ec  mov     cs:WdLogGlobalForLineNumber, eax
0x1400a79f2  mov     [rsp+0F0h+Timeout], rax
0x1400a79f7  call    DxgkLogInternalTriageEvent
0x1400a79fc  test    esi, esi
0x1400a79fe  jns     short loc_1400A7A27
0x1400a7a00  movzx   r9d, [rbp+57h+var_A0]
0x1400a7a05  mov     ecx, 3
0x1400a7a0a  mov     rdx, [rbp+57h+var_98]
0x1400a7a0e  movsxd  r8, esi
0x1400a7a11  call    cs:__imp_WdLogSingleEntry3
0x1400a7a18  nop     dword ptr [rax+rax+00h]
0x1400a7a1d  mov     cs:WdLogGlobalForLineNumber, 17DAh
0x1400a7a27  mov     rcx, [rbp+57h+var_40]
0x1400a7a2b  xor     rcx, rsp; StackCookie
0x1400a7a2e  call    __security_check_cookie
0x1400a7a33  mov     rbx, [rsp+0F0h+arg_10]
0x1400a7a3b  add     rsp, 0C0h
0x1400a7a42  pop     r15
0x1400a7a44  pop     r14
0x1400a7a46  pop     r13
0x1400a7a48  pop     r12
0x1400a7a4a  pop     rdi
0x1400a7a4b  pop     rsi
0x1400a7a4c  pop     rbp
0x1400a7a4d  retn
```
