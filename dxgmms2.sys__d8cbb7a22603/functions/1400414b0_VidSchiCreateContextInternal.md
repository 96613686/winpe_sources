# VidSchiCreateContextInternal

- ea: `0x1400414b0`
- end: `0x140041d14`
- name: `VidSchiCreateContextInternal`
- size: `2148`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400e177c`
- `0x140122790`

## callees

- `0x140002138`
- `0x140004268`
- `0x140009ed0`
- `0x140012ae0`
- `0x14001bd6c`
- `0x14002c5d0`
- `0x140039f6c`
- `0x14003e524`
- `0x1400403fc`
- `0x1400414b0`
- `0x14004506c`
- `0x140058f50`
- `0x140059380`
- `0x1401181b0`
- `0x1401202b0`

## import_xrefs

- `ntoskrnl!KeInitializeTimer` at `0x1400417ff`
- `ntoskrnl!KeInitializeTimer` at `0x1400417ff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041745`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041745`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400417c9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400417c9`
- `ntoskrnl!KeInitializeDpc` at `0x14004181c`
- `ntoskrnl!KeInitializeDpc` at `0x14004181c`
- `ntoskrnl!KeInitializeEvent` at `0x14004169f`
- `ntoskrnl!KeInitializeEvent` at `0x14004169f`
- `ntoskrnl!ExAllocatePool2` at `0x1400415c8`
- `ntoskrnl!ExAllocatePool2` at `0x140041c1d`
- `ntoskrnl!ExAllocatePool2` at `0x140041c97`
- `ntoskrnl!ExAllocatePool2` at `0x1400415c8`
- `ntoskrnl!ExAllocatePool2` at `0x140041c1d`
- `ntoskrnl!ExAllocatePool2` at `0x140041c97`
- `watchdog!WdLogSingleEntry2` at `0x140041520`
- `watchdog!WdLogSingleEntry2` at `0x140041520`
- `watchdog!WdLogSingleEntry0` at `0x14004159d`
- `watchdog!WdLogSingleEntry0` at `0x1400415df`
- `watchdog!WdLogSingleEntry0` at `0x140041cea`
- `watchdog!WdLogSingleEntry0` at `0x14004159d`
- `watchdog!WdLogSingleEntry0` at `0x1400415df`
- `watchdog!WdLogSingleEntry0` at `0x140041cea`

## string_xrefs

- `0x14004153c`: `Process 0x%p cannot create a context against engine type %d because another process acquired exclusive access to it`

## pseudocode

```c
__int64 __fastcall VidSchiCreateContextInternal(__int64 a1, __int128 *a2, __int64 a3)
{
  __int64 v3; // r14
  __int64 v5; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbx
  int v12; // ecx
  int v13; // r8d
  __int64 Pool2; // rax
  __int64 v16; // rdi
  __int128 v17; // xmm0
  __int64 *v18; // rcx
  __int128 v19; // xmm1
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rbx
  struct DXGPROCESS *Current; // rax
  bool v24; // zf
  __int64 v25; // rcx
  _QWORD *v26; // rdx
  _QWORD *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // ebx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rax
  bool v34; // cf
  ADAPTER_RENDER *v35; // rcx
  __int64 v36; // r8
  void *v37; // rdx
  int v38; // eax
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rdx
  __int128 v42; // xmm0
  __int64 v43; // rax
  __int64 v44; // rdx
  __int128 v45; // xmm1
  HANDLE hContext; // rax
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // rcx
  int v52; // ebx
  __int64 v53; // r11
  __int64 v54; // r9
  int v55; // r13d
  unsigned int v56; // edx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rbx
  unsigned int v60; // r12d
  int v61; // r14d
  __int64 v62; // r13
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rcx
  char v66[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  __int16 v68[2]; // [rsp+90h] [rbp-70h] BYREF
  int v69; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v70; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v72; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-48h] BYREF
  _DXGKARG_CREATECONTEXT v75; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE LockHandle[32]; // [rsp+110h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a1 + 40);
  v5 = *((unsigned int *)a2 + 1);
  v67 = a3;
  v8 = *(_QWORD *)(v3 + 776);
  if ( (unsigned int)v5 < *(_DWORD *)(v3 + 848) )
    v8 += 8 * v5;
  if ( (unsigned int)VidSchiCheckEngineAccess(v3, *(_QWORD *)(a1 + 48), *(int *)(*(_QWORD *)v8 + 20LL)) != 2 )
  {
    if ( (*(_DWORD *)a2 & 4) == 0 && !a3 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 5176;
      return 0;
    }
    Pool2 = ExAllocatePool2(64, 1008, 878799190);
    v16 = Pool2;
    if ( !Pool2 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 5190;
      return 0;
    }
    *(_DWORD *)Pool2 = 878799190;
    *(_QWORD *)(Pool2 + 56) = a3;
    *(_QWORD *)(Pool2 + 104) = a1;
    v17 = *a2;
    v18 = *(__int64 **)(v3 + 776);
    v19 = a2[1];
    *(_QWORD *)(Pool2 + 80) = KeGetCurrentThread();
    v20 = *((_DWORD *)a2 + 8);
    *(_OWORD *)(v16 + 112) = v17;
    *(_OWORD *)(v16 + 128) = v19;
    *(_DWORD *)(v16 + 144) = v20;
    v21 = *((unsigned int *)a2 + 1);
    *(_DWORD *)(v16 + 88) = v21;
    if ( (unsigned int)v21 < *(_DWORD *)(v3 + 848) )
      v18 += v21;
    v22 = *v18;
    v70 = v22;
    *(_QWORD *)(v16 + 96) = v22;
    Current = DXGPROCESS::GetCurrent();
    *(_QWORD *)(v16 + 152) = 1;
    *(_BYTE *)(v16 + 917) = BYTE1(*((_DWORD *)Current + 102)) & 1;
    *(_OWORD *)(v16 + 328) = 0;
    *(_OWORD *)(v16 + 344) = 0;
    *(_OWORD *)(v16 + 360) = 0;
    *(_QWORD *)(v16 + 376) = 0;
    KeInitializeEvent((PRKEVENT)(v16 + 328), SynchronizationEvent, 0);
    v24 = (*(_DWORD *)a2 & 0x100) == 0;
    *(_QWORD *)(v16 + 392) = v16 + 384;
    *(_QWORD *)(v16 + 384) = v16 + 384;
    *(_QWORD *)(v16 + 680) = v16 + 672;
    *(_QWORD *)(v16 + 672) = v16 + 672;
    *(_QWORD *)(v16 + 696) = v16 + 688;
    *(_QWORD *)(v16 + 688) = v16 + 688;
    *(_QWORD *)(v16 + 712) = v16 + 704;
    *(_QWORD *)(v16 + 704) = v16 + 704;
    *(_QWORD *)(v16 + 728) = v16 + 720;
    *(_QWORD *)(v16 + 720) = v16 + 720;
    if ( !v24 )
    {
      *(_QWORD *)(v16 + 752) = v16 + 744;
      *(_QWORD *)(v16 + 744) = v16 + 744;
    }
    *(_QWORD *)(v16 + 776) = v16 + 768;
    *(_QWORD *)(v16 + 768) = v16 + 768;
    *(_BYTE *)(v16 + 916) = 1;
    VidSchiIncrementContextReference(v16);
    *(_BYTE *)(v16 + 916) = 0;
    memset(LockHandle, 0, 24);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 2096), (PKLOCK_QUEUE_HANDLE)LockHandle);
    if ( *(_BYTE *)(a1 + 1656) || *(_BYTE *)(a1 + 1657) )
    {
      v25 = v22 + 2752;
      *(_DWORD *)(v16 + 192) |= 0x100u;
    }
    else
    {
      v25 = v22 + 2720;
    }
    v26 = *(_QWORD **)(v25 + 8);
    if ( *v26 != v25
      || (*(_QWORD *)(v16 + 8) = v25,
          *(_QWORD *)(v16 + 16) = v26,
          *v26 = v16 + 8,
          *(_QWORD *)(v25 + 8) = v16 + 8,
          v27 = *(_QWORD **)(a1 + 88),
          *v27 != a1 + 80) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)(v16 + 24) = a1 + 80;
    *(_QWORD *)(v16 + 32) = v27;
    *v27 = v16 + 24;
    *(_QWORD *)(a1 + 88) = v16 + 24;
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
    v28 = *(_QWORD *)(v3 + 2992);
    v29 = *(_QWORD *)(v3 + 3040);
    *(_QWORD *)(v16 + 480) = v28;
    *(_QWORD *)(v16 + 448) = v28;
    *(_QWORD *)(v16 + 488) = v29;
    KeInitializeTimer((PKTIMER)(v16 + 520));
    KeInitializeDpc((PRKDPC)(v16 + 584), VidSchiDelayReadyRoutine, (PVOID)v16);
    v30 = *(_DWORD *)a2;
    if ( (*(_DWORD *)a2 & 0x604) != 0 )
    {
      if ( (v30 & 1) != 0 )
      {
        memset(&v75, 0, sizeof(v75));
        v31 = *(unsigned int *)(v16 + 88);
        v32 = *(_QWORD *)(v3 + 776);
        v33 = v32 + 8 * v31;
        v34 = (unsigned int)v31 < *(_DWORD *)(v3 + 848);
        if ( (unsigned int)v31 >= *(_DWORD *)(v3 + 848) )
          v33 = *(_QWORD *)(v3 + 776);
        v75.NodeOrdinal = *(unsigned __int16 *)(*(_QWORD *)v33 + 8LL);
        if ( v34 )
          v32 += 8 * v31;
        v35 = *(ADAPTER_RENDER **)(v3 + 8);
        v75.EngineAffinity = 1 << *(_BYTE *)(*(_QWORD *)v32 + 6LL);
        v36 = 352LL * *(unsigned __int16 *)(v70 + 6);
        v75.Flags.Value = (v30 & 4 | ((v30 & 0x200 | (v30 >> 1) & 0x400) >> 4)) >> 2;
        v37 = *(void **)(a1 + 24);
        v75.Flags.Value |= 4 * (*(_BYTE *)(v36 + *(_QWORD *)(*((_QWORD *)v35 + 2) + 3120LL) + 48) & 1);
        v38 = ADAPTER_RENDER::DdiCreateContext(v35, v37, &v75);
        if ( v38 < 0 )
        {
          v67 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 16LL) + 412LL);
          if ( (unsigned int)dword_140087048 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000000LL, (unsigned int)v38) )
          {
            v41 = *(_QWORD *)(v16 + 56);
            v68[0] = 0;
            v42 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v41 + 16) + 40LL) + 64LL) + 144LL);
            v72 = LockHandle;
            v43 = *(_QWORD *)(v16 + 104);
            *(_OWORD *)LockHandle = v42;
            v73 = *(_QWORD *)(*(_QWORD *)(v43 + 48) + 2648LL);
            LOBYTE(v43) = *(_BYTE *)(v41 + 144);
            v44 = *(_QWORD *)(v3 + 8);
            v66[0] = v43;
            v74 = v67;
            v69 = *(_DWORD *)(*(_QWORD *)(v44 + 16) + 424LL);
            LODWORD(v70) = *(_DWORD *)(*(_QWORD *)(v44 + 16) + 420LL);
            LODWORD(v67) = v39;
            v71 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
              v70,
              (unsigned int)&byte_14007D70F,
              v39,
              v40,
              (__int64)&v71,
              (__int64)&v67,
              (__int64)&v70,
              (__int64)&v69,
              (__int64)&v74,
              (__int64)v66,
              (__int64)&v73,
              (__int64)&v72,
              (__int64)v68);
          }
LABEL_59:
          VidSchTerminateContext((struct _VIDSCH_CONTEXT *)v16);
          return 0;
        }
        v24 = bTracingEnabled == 0;
        v45 = *(_OWORD *)&v75.Flags.0;
        hContext = v75.hContext;
        *(_OWORD *)(v16 + 920) = *(_OWORD *)&v75.hContext;
        *(_QWORD *)(v16 + 64) = hContext;
        v47 = *(_OWORD *)&v75.PrivateDriverDataSize;
        *(_OWORD *)(v16 + 936) = v45;
        v48 = *(_OWORD *)&v75.ContextInfo.AllocationListSize;
        *(_OWORD *)(v16 + 952) = v47;
        *(_QWORD *)&v47 = *(_QWORD *)&v75.ContextInfo.PagingCompanionNodeId;
        *(_OWORD *)(v16 + 968) = v48;
        *(_QWORD *)(v16 + 984) = v47;
        if ( !v24 )
        {
          v49 = *(_QWORD *)(a1 + 8);
          if ( !v49 )
            LODWORD(v49) = a1;
          if ( (byte_140087201 & 8) != 0 )
            McTemplateK0pqqqqqqqqppp_EtwWriteTransfer(
              (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) >> 4) & 1)) | 1,
              (unsigned int)EventCreateContext,
              v75.ContextInfo.AllocationListSize,
              v49,
              v75.NodeOrdinal,
              v75.EngineAffinity,
              v75.ContextInfo.DmaBufferSize,
              v75.ContextInfo.DmaBufferSegmentSet,
              v75.ContextInfo.DmaBufferPrivateDataSize,
              v75.ContextInfo.AllocationListSize,
              v75.ContextInfo.PatchLocationListSize,
              (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) & 0x10) != 0)) | 1,
              v16);
        }
      }
      else if ( bTracingEnabled )
      {
        v50 = *(unsigned int *)(v16 + 88);
        if ( (unsigned int)v50 < *(_DWORD *)(v3 + 88) )
        {
          v51 = *(_QWORD *)(v3 + 776);
          v52 = *(_DWORD *)a2 & 0x40;
          memset(LockHandle, 0, sizeof(LockHandle));
          if ( (unsigned int)v50 >= *(_DWORD *)(v3 + 848) )
          {
            v53 = v51;
          }
          else
          {
            v53 = v51 + 8 * v50;
            v51 = v53;
          }
          v54 = *(_QWORD *)(a1 + 8);
          if ( !v54 )
            LODWORD(v54) = a1;
          if ( (byte_140087201 & 8) != 0 )
            McTemplateK0pqqqqqqqqppp_EtwWriteTransfer(
              *(unsigned __int16 *)(*(_QWORD *)v53 + 8LL),
              (unsigned int)EventCreateContext,
              (v52 != 0 ? 5 : 1) | (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) >> 4) & 1)),
              v54,
              *(_WORD *)(*(_QWORD *)v53 + 8LL),
              1 << *(_BYTE *)(*(_QWORD *)v51 + 6LL),
              0,
              0,
              0,
              0,
              0,
              (v52 != 0 ? 5 : 1) | (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) & 0x10) != 0)),
              v16);
        }
      }
    }
    else
    {
      *(_QWORD *)(v16 + 64) = *(_QWORD *)(v67 + 184);
    }
    if ( (int)VidSchSetPriorityContext((struct _VIDSCH_CONTEXT *)v16, *((_DWORD *)a2 + 6), 0) >= 0 )
    {
      v55 = 0;
      v56 = *(_DWORD *)(v3 + 160) * (72 * *(_DWORD *)(v3 + 84) + 224) + 8 * (*(_DWORD *)(v3 + 84) + 113);
      v57 = 1136;
      if ( v56 > 0x470 )
        v57 = v56;
      v67 = v57;
      do
      {
        v58 = ExAllocatePool2(64, v57, 895576406);
        v59 = v58;
        if ( !v58 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 5491;
          goto LABEL_59;
        }
        v71 = v3 + 2104;
        VidSchiInterlockedInsertTailList(v3 + 2104, v16 + 768, v58 + 8, v16 + 784);
        VidSchiFreeQueuePacket(v16, v59);
        v57 = v67;
        ++v55;
      }
      while ( v55 < 5 );
      if ( (*(_DWORD *)a2 & 0x100) == 0 )
        return v16;
      v60 = *((_DWORD *)a2 + 7);
      if ( v60 )
      {
        v61 = 0;
        v62 = v67;
        while ( 1 )
        {
          v63 = ExAllocatePool2(64, v62, 895576406);
          v64 = v63;
          if ( !v63 )
            break;
          v65 = v71;
          *(_DWORD *)(v63 + 64) |= 0x40u;
          VidSchiInterlockedInsertTailList(v65, v16 + 768, v63 + 8, v16 + 784);
          VidSchiFreeQueuePacket(v16, v64);
          if ( ++v61 >= v60 )
            return v16;
        }
      }
    }
    goto LABEL_59;
  }
  v11 = v10;
  WdLogSingleEntry2(1, v9, v10);
  WdLogGlobalForLineNumber = 5167;
  DxgkLogInternalTriageEvent(
    v12,
    0x40000,
    v13,
    (unsigned int)L"Process 0x%p cannot create a context against engine type %d because another process acquired exclusive access to it",
    *(_QWORD *)(a1 + 48),
    v11,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x1400414b0  mov     [rsp-8+arg_18], rbx
0x1400414b5  push    rbp
0x1400414b6  push    rsi
0x1400414b7  push    rdi
0x1400414b8  push    r12
0x1400414ba  push    r13
0x1400414bc  push    r14
0x1400414be  push    r15
0x1400414c0  lea     rbp, [rsp-40h]
0x1400414c5  sub     rsp, 140h
0x1400414cc  mov     rax, cs:__security_cookie
0x1400414d3  xor     rax, rsp
0x1400414d6  mov     [rbp+70h+var_40], rax
0x1400414da  mov     r14, [rcx+28h]
0x1400414de  mov     rbx, r8
0x1400414e1  mov     eax, [rdx+4]
0x1400414e4  mov     r13, rcx
0x1400414e7  mov     [rbp+70h+var_E8], rbx
0x1400414eb  mov     r12, rdx
0x1400414ee  mov     rcx, [r14+308h]
0x1400414f5  cmp     eax, [r14+350h]
0x1400414fc  jnb     short loc_140041502
0x1400414fe  lea     rcx, [rcx+rax*8]
0x140041502  mov     rax, [rcx]
0x140041505  mov     rcx, r14
0x140041508  mov     rdx, [r13+30h]
0x14004150c  movsxd  r8, dword ptr [rax+14h]
0x140041510  call    VidSchiCheckEngineAccess
0x140041515  cmp     eax, 2
0x140041518  jnz     short loc_14004158B
0x14004151a  lea     ecx, [rax-1]
0x14004151d  mov     rbx, r8
0x140041520  call    cs:__imp_WdLogSingleEntry2
0x140041527  nop     dword ptr [rax+rax+00h]
0x14004152c  xor     esi, esi
0x14004152e  mov     cs:WdLogGlobalForLineNumber, 142Fh
0x140041538  mov     rax, [r13+30h]
0x14004153c  lea     r9, aProcess0xPCann; "Process 0x%p cannot create a context ag"...
0x140041543  mov     [rsp+170h+var_138], rsi
0x140041548  mov     edx, 40000h
0x14004154d  mov     [rsp+170h+var_140], rsi
0x140041552  mov     qword ptr [rsp+170h+var_148], rbx
0x140041557  mov     qword ptr [rsp+170h+var_150], rax
0x14004155c  call    DxgkLogInternalTriageEvent
0x140041561  xor     eax, eax
0x140041563  mov     rcx, [rbp+70h+var_40]
0x140041567  xor     rcx, rsp; StackCookie
0x14004156a  call    __security_check_cookie
0x14004156f  mov     rbx, [rsp+170h+arg_18]
0x140041577  add     rsp, 140h
0x14004157e  pop     r15
0x140041580  pop     r14
0x140041582  pop     r13
0x140041584  pop     r12
0x140041586  pop     rdi
0x140041587  pop     rsi
0x140041588  pop     rbp
0x140041589  retn
0x14004158b  mov     eax, [r12]
0x14004158f  xor     esi, esi
0x140041591  test    al, 4
0x140041593  jnz     short loc_1400415B5
0x140041595  test    rbx, rbx
0x140041598  jnz     short loc_1400415B5
0x14004159a  lea     ecx, [rsi+3]
0x14004159d  call    cs:__imp_WdLogSingleEntry0
0x1400415a4  nop     dword ptr [rax+rax+00h]
0x1400415a9  mov     cs:WdLogGlobalForLineNumber, 1438h
0x1400415b3  jmp     short loc_140041561
0x1400415b5  mov     r15d, 34616956h
0x1400415bb  mov     edx, 3F0h
0x1400415c0  mov     r8d, r15d
0x1400415c3  mov     ecx, 40h ; '@'
0x1400415c8  call    cs:__imp_ExAllocatePool2
0x1400415cf  nop     dword ptr [rax+rax+00h]
0x1400415d4  mov     rdi, rax
0x1400415d7  test    rax, rax
0x1400415da  jnz     short loc_1400415FA
0x1400415dc  lea     ecx, [rax+3]
0x1400415df  call    cs:__imp_WdLogSingleEntry0
0x1400415e6  nop     dword ptr [rax+rax+00h]
0x1400415eb  mov     cs:WdLogGlobalForLineNumber, 1446h
0x1400415f5  jmp     loc_140041561
0x1400415fa  mov     [rax], r15d
0x1400415fd  mov     [rax+38h], rbx
0x140041601  mov     [rax+68h], r13
0x140041605  mov     rax, gs:188h
0x14004160e  movups  xmm0, xmmword ptr [r12]
0x140041613  mov     rcx, [r14+308h]
0x14004161a  movups  xmm1, xmmword ptr [r12+10h]
0x140041620  mov     [rdi+50h], rax
0x140041624  mov     eax, [r12+20h]
0x140041629  movups  xmmword ptr [rdi+70h], xmm0
0x14004162d  movups  xmmword ptr [rdi+80h], xmm1
0x140041634  mov     [rdi+90h], eax
0x14004163a  mov     eax, [r12+4]
0x14004163f  mov     [rdi+58h], eax
0x140041642  cmp     eax, [r14+350h]
0x140041649  jnb     short loc_14004164F
0x14004164b  lea     rcx, [rcx+rax*8]
0x14004164f  mov     rbx, [rcx]
0x140041652  mov     [rbp+70h+var_D8], rbx
0x140041656  mov     [rdi+60h], rbx
0x14004165a  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14004165f  xorps   xmm0, xmm0
0x140041662  mov     r15d, 1
0x140041668  mov     [rdi+98h], r15
0x14004166f  xor     r8d, r8d; State
0x140041672  mov     edx, r15d; Type
0x140041675  mov     ecx, [rax+198h]
0x14004167b  xor     eax, eax
0x14004167d  shr     ecx, 8
0x140041680  and     cl, r15b
0x140041683  mov     [rdi+395h], cl
0x140041689  lea     rcx, [rdi+148h]; Event
0x140041690  movups  xmmword ptr [rcx], xmm0
0x140041693  movups  xmmword ptr [rcx+10h], xmm0
0x140041697  movups  xmmword ptr [rcx+20h], xmm0
0x14004169b  mov     [rcx+30h], rax
0x14004169f  call    cs:__imp_KeInitializeEvent
0x1400416a6  nop     dword ptr [rax+rax+00h]
0x1400416ab  test    dword ptr [r12], 100h
0x1400416b3  lea     rax, [rdi+180h]
0x1400416ba  mov     [rax+8], rax
0x1400416be  mov     [rax], rax
0x1400416c1  lea     rax, [rdi+2A0h]
0x1400416c8  mov     [rax+8], rax
0x1400416cc  mov     [rax], rax
0x1400416cf  lea     rax, [rdi+2B0h]
0x1400416d6  mov     [rax+8], rax
0x1400416da  mov     [rax], rax
0x1400416dd  lea     rax, [rdi+2C0h]
0x1400416e4  mov     [rax+8], rax
0x1400416e8  mov     [rax], rax
0x1400416eb  lea     rax, [rdi+2D0h]
0x1400416f2  mov     [rax+8], rax
0x1400416f6  mov     [rax], rax
0x1400416f9  jz      short loc_140041709
0x1400416fb  lea     rax, [rdi+2E8h]
0x140041702  mov     [rax+8], rax
0x140041706  mov     [rax], rax
0x140041709  lea     rax, [rdi+300h]
0x140041710  mov     rcx, rdi
0x140041713  mov     [rax+8], rax
0x140041717  mov     [rax], rax
0x14004171a  mov     [rdi+394h], r15b
0x140041721  call    VidSchiIncrementContextReference
0x140041726  xorps   xmm0, xmm0
0x140041729  mov     [rdi+394h], sil
0x140041730  xor     eax, eax
0x140041732  lea     rcx, [r14+830h]; SpinLock
0x140041739  lea     rdx, [rbp+70h+LockHandle]; LockHandle
0x14004173d  mov     qword ptr [rbp+70h+LockHandle+10h], rax
0x140041741  movups  xmmword ptr [rbp+70h+LockHandle], xmm0
0x140041745  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004174c  nop     dword ptr [rax+rax+00h]
0x140041751  cmp     [r13+678h], sil
0x140041758  jnz     short loc_14004176C
0x14004175a  cmp     [r13+679h], sil
0x140041761  jnz     short loc_14004176C
0x140041763  lea     rcx, [rbx+0AA0h]
0x14004176a  jmp     short loc_140041783
0x14004176c  mov     eax, [rdi+0C0h]
0x140041772  lea     rcx, [rbx+0AC0h]
0x140041779  bts     eax, 8
0x14004177d  mov     [rdi+0C0h], eax
0x140041783  mov     rdx, [rcx+8]
0x140041787  cmp     [rdx], rcx
0x14004178a  jnz     loc_140041D0D
0x140041790  lea     rax, [rdi+8]
0x140041794  mov     [rax], rcx
0x140041797  mov     [rax+8], rdx
0x14004179b  mov     [rdx], rax
0x14004179e  mov     [rcx+8], rax
0x1400417a2  lea     rcx, [r13+50h]
0x1400417a6  mov     rdx, [rcx+8]
0x1400417aa  cmp     [rdx], rcx
0x1400417ad  jnz     loc_140041D0D
0x1400417b3  lea     rax, [rdi+18h]
0x1400417b7  mov     [rax], rcx
0x1400417ba  mov     [rax+8], rdx
0x1400417be  mov     [rdx], rax
0x1400417c1  mov     [rcx+8], rax
0x1400417c5  lea     rcx, [rbp+70h+LockHandle]; LockHandle
0x1400417c9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400417d0  nop     dword ptr [rax+rax+00h]
0x1400417d5  mov     rcx, [r14+0BB0h]
0x1400417dc  mov     rax, [r14+0BE0h]
0x1400417e3  mov     [rdi+1E0h], rcx
0x1400417ea  mov     [rdi+1C0h], rcx
0x1400417f1  lea     rcx, [rdi+208h]; Timer
0x1400417f8  mov     [rdi+1E8h], rax
0x1400417ff  call    cs:__imp_KeInitializeTimer
0x140041806  nop     dword ptr [rax+rax+00h]
0x14004180b  lea     rcx, [rdi+248h]; Dpc
0x140041812  mov     r8, rdi; DeferredContext
0x140041815  lea     rdx, VidSchiDelayReadyRoutine; DeferredRoutine
0x14004181c  call    cs:__imp_KeInitializeDpc
0x140041823  nop     dword ptr [rax+rax+00h]
0x140041828  mov     ebx, [r12]
0x14004182c  test    ebx, 604h
0x140041832  jnz     short loc_140041848
0x140041834  mov     rax, [rbp+70h+var_E8]
0x140041838  mov     rax, [rax+0B8h]
0x14004183f  mov     [rdi+40h], rax
0x140041843  jmp     loc_140041BB7
0x140041848  test    r15b, bl
0x14004184b  jz      loc_140041AEB
0x140041851  xor     edx, edx; Val
0x140041853  lea     rcx, [rbp+70h+var_B0]; void *
0x140041857  lea     r8d, [rdx+48h]; Size
0x14004185b  call    memset
0x140041860  mov     r8d, [rdi+58h]
0x140041864  mov     rdx, [r14+308h]
0x14004186b  lea     rax, [rdx+r8*8]
0x14004186f  cmp     r8d, [r14+350h]
0x140041876  jb      short loc_14004187B
0x140041878  mov     rax, rdx
0x14004187b  mov     rax, [rax]
0x14004187e  movzx   ecx, word ptr [rax+8]
0x140041882  mov     [rbp+70h+var_B0.NodeOrdinal], ecx
0x140041885  jnb     short loc_14004188B
0x140041887  lea     rdx, [rdx+r8*8]
0x14004188b  mov     rcx, [rdx]
0x14004188e  mov     r9d, ebx
0x140041891  shr     r9d, 1
0x140041894  mov     eax, r15d
0x140041897  and     r9d, 400h
0x14004189e  mov     cl, [rcx+6]
0x1400418a1  shl     eax, cl
0x1400418a3  mov     rcx, [r14+8]; this
0x1400418a7  mov     [rbp+70h+var_B0.EngineAffinity], eax
0x1400418aa  mov     eax, ebx
0x1400418ac  and     eax, 200h
0x1400418b1  and     ebx, 4
0x1400418b4  or      r9d, eax
0x1400418b7  mov     rax, [rbp+70h+var_D8]
0x1400418bb  shr     r9d, 4
0x1400418bf  or      r9d, ebx
0x1400418c2  shr     r9d, 2
0x1400418c6  movzx   eax, word ptr [rax+6]
0x1400418ca  imul    r8, rax, 160h
0x1400418d1  mov     dword ptr [rbp+70h+var_B0.Flags], r9d
0x1400418d5  mov     rax, [rcx+10h]
0x1400418d9  mov     rdx, [rax+0C30h]
0x1400418e0  movzx   eax, byte ptr [r8+rdx+30h]
0x1400418e6  lea     r8, [rbp+70h+var_B0]; struct _DXGKARG_CREATECONTEXT *
0x1400418ea  mov     rdx, [r13+18h]; void *
0x1400418ee  and     eax, r15d
0x1400418f1  shl     eax, 2
0x1400418f4  or      eax, r9d
0x1400418f7  mov     dword ptr [rbp+70h+var_B0.Flags], eax
0x1400418fa  call    ?DdiCreateContext@ADAPTER_RENDER@@QEAAJPEAXPEAU_DXGKARG_CREATECONTEXT@@@Z; ADAPTER_RENDER::DdiCreateContext(void *,_DXGKARG_CREATECONTEXT *)
0x1400418ff  mov     r8d, eax
0x140041902  test    eax, eax
0x140041904  jns     loc_140041A29
0x14004190a  mov     rcx, [r14+8]
0x14004190e  mov     rdx, [rcx+10h]
0x140041912  mov     ecx, [rdx+19Ch]
0x140041918  mov     dword ptr [rbp+70h+var_E8], ecx
0x14004191b  mov     ecx, [rdx+1A0h]
0x140041921  mov     dword ptr [rbp+70h+var_E8+4], ecx
0x140041924  mov     ecx, cs:dword_140087048
0x14004192a  cmp     ecx, 5
0x14004192d  jbe     loc_140041D00
0x140041933  mov     rdx, 400000000000h
0x14004193d  lea     rcx, dword_140087048
0x140041944  call    _tlgKeywordOn
0x140041949  test    al, al
0x14004194b  jz      loc_140041D00
0x140041951  mov     rdx, [rdi+38h]
0x140041955  mov     [rbp+70h+var_E0], si
0x140041959  mov     rax, [rdx+10h]
0x14004195d  mov     rcx, [rax+28h]
0x140041961  mov     rax, [rcx+40h]
0x140041965  movups  xmm0, xmmword ptr [rax+90h]
0x14004196c  lea     rax, [rbp+70h+LockHandle]
0x140041970  mov     [rbp+70h+var_C8], rax
0x140041974  mov     rax, [rdi+68h]
0x140041978  movdqu  xmmword ptr [rbp+70h+LockHandle], xmm0
0x14004197d  mov     rcx, [rax+30h]
0x140041981  mov     rax, [rcx+0A58h]
0x140041988  mov     [rbp+70h+var_C0], rax
0x14004198c  mov     al, [rdx+90h]
0x140041992  mov     rdx, [r14+8]
0x140041996  mov     [rbp+70h+var_F0], al
0x140041999  mov     rax, [rbp+70h+var_E8]
0x14004199d  mov     [rbp+70h+var_B8], rax
0x1400419a1  mov     rax, [rdx+10h]
0x1400419a5  mov     ecx, [rax+1A8h]
0x1400419ab  mov     [rbp+70h+var_DC], ecx
0x1400419ae  mov     rax, [rdx+10h]
0x1400419b2  lea     rdx, byte_14007D70F
0x1400419b9  mov     ecx, [rax+1A4h]
0x1400419bf  lea     rax, [rbp+70h+var_E0]
0x1400419c3  mov     [rsp+170h+var_110], rax
0x1400419c8  lea     rax, [rbp+70h+var_C8]
0x1400419cc  mov     [rsp+170h+var_118], rax
0x1400419d1  lea     rax, [rbp+70h+var_C0]
0x1400419d5  mov     [rsp+170h+var_120], rax
  ... truncated ...
```
