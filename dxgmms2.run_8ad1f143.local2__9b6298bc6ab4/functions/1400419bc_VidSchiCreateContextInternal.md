# VidSchiCreateContextInternal

- ea: `0x1400419bc`
- end: `0x140042220`
- name: `VidSchiCreateContextInternal`
- size: `2148`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400d931c`
- `0x14011efb0`

## callees

- `0x140002138`
- `0x1400045ec`
- `0x14000a240`
- `0x140013040`
- `0x14001c44c`
- `0x14002f510`
- `0x14003b25c`
- `0x14003fba4`
- `0x1400416d8`
- `0x1400419bc`
- `0x140044e68`
- `0x140058680`
- `0x140058ac0`
- `0x140114630`
- `0x14011c9a0`

## import_xrefs

- `ntoskrnl!KeInitializeTimer` at `0x140041d0b`
- `ntoskrnl!KeInitializeTimer` at `0x140041d0b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041c51`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140041c51`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041cd5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140041cd5`
- `ntoskrnl!KeInitializeDpc` at `0x140041d28`
- `ntoskrnl!KeInitializeDpc` at `0x140041d28`
- `ntoskrnl!KeInitializeEvent` at `0x140041bab`
- `ntoskrnl!KeInitializeEvent` at `0x140041bab`
- `ntoskrnl!ExAllocatePool2` at `0x140041ad4`
- `ntoskrnl!ExAllocatePool2` at `0x140042129`
- `ntoskrnl!ExAllocatePool2` at `0x1400421a3`
- `ntoskrnl!ExAllocatePool2` at `0x140041ad4`
- `ntoskrnl!ExAllocatePool2` at `0x140042129`
- `ntoskrnl!ExAllocatePool2` at `0x1400421a3`
- `watchdog!WdLogSingleEntry2` at `0x140041a2c`
- `watchdog!WdLogSingleEntry2` at `0x140041a2c`
- `watchdog!WdLogSingleEntry0` at `0x140041aa9`
- `watchdog!WdLogSingleEntry0` at `0x140041aeb`
- `watchdog!WdLogSingleEntry0` at `0x1400421f6`
- `watchdog!WdLogSingleEntry0` at `0x140041aa9`
- `watchdog!WdLogSingleEntry0` at `0x140041aeb`
- `watchdog!WdLogSingleEntry0` at `0x1400421f6`

## string_xrefs

- `0x140041a48`: `Process 0x%p cannot create a context against engine type %d because another process acquired exclusive access to it`

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
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rdx
  __int128 v41; // xmm0
  __int64 v42; // rax
  __int64 v43; // rdx
  __int128 v44; // xmm1
  HANDLE hContext; // rax
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int64 v48; // r9
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // ebx
  __int64 v52; // r11
  __int64 v53; // r9
  int v54; // r13d
  unsigned int v55; // edx
  __int64 v56; // rax
  __int64 v57; // rax
  unsigned int v58; // r12d
  int v59; // r14d
  __int64 v60; // r13
  __int64 v61; // rax
  __int64 v62; // rcx
  char v63[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v64; // [rsp+88h] [rbp-78h] BYREF
  __int16 v65[2]; // [rsp+90h] [rbp-70h] BYREF
  int v66; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  _DXGKARG_CREATECONTEXT v72; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE LockHandle[32]; // [rsp+110h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a1 + 40);
  v5 = *((unsigned int *)a2 + 1);
  v64 = a3;
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
    v67 = v22;
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
        memset(&v72, 0, sizeof(v72));
        v31 = *(unsigned int *)(v16 + 88);
        v32 = *(_QWORD *)(v3 + 776);
        v33 = v32 + 8 * v31;
        v34 = (unsigned int)v31 < *(_DWORD *)(v3 + 848);
        if ( (unsigned int)v31 >= *(_DWORD *)(v3 + 848) )
          v33 = *(_QWORD *)(v3 + 776);
        v72.NodeOrdinal = *(unsigned __int16 *)(*(_QWORD *)v33 + 8LL);
        if ( v34 )
          v32 += 8 * v31;
        v35 = *(ADAPTER_RENDER **)(v3 + 8);
        v72.EngineAffinity = 1 << *(_BYTE *)(*(_QWORD *)v32 + 6LL);
        v36 = 352LL * *(unsigned __int16 *)(v67 + 6);
        v72.Flags.Value = (v30 & 4 | ((v30 & 0x200 | (v30 >> 1) & 0x400) >> 4)) >> 2;
        v37 = *(void **)(a1 + 24);
        v72.Flags.Value |= 4 * (*(_BYTE *)(v36 + *(_QWORD *)(*((_QWORD *)v35 + 2) + 3104LL) + 48) & 1);
        if ( (int)ADAPTER_RENDER::DdiCreateContext(v35, v37, &v72) < 0 )
        {
          v64 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 16LL) + 412LL);
          if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000000LL) )
          {
            v40 = *(_QWORD *)(v16 + 56);
            v65[0] = 0;
            v41 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v40 + 16) + 40LL) + 64LL) + 144LL);
            v69 = LockHandle;
            v42 = *(_QWORD *)(v16 + 104);
            *(_OWORD *)LockHandle = v41;
            v70 = *(_QWORD *)(*(_QWORD *)(v42 + 48) + 2648LL);
            LOBYTE(v42) = *(_BYTE *)(v40 + 144);
            v43 = *(_QWORD *)(v3 + 8);
            v63[0] = v42;
            v71 = v64;
            v66 = *(_DWORD *)(*(_QWORD *)(v43 + 16) + 424LL);
            LODWORD(v67) = *(_DWORD *)(*(_QWORD *)(v43 + 16) + 420LL);
            LODWORD(v64) = v38;
            v68 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
              v67,
              (unsigned int)&byte_14007BE8F,
              v38,
              v39,
              (__int64)&v68,
              (__int64)&v64,
              (__int64)&v67,
              (__int64)&v66,
              (__int64)&v71,
              (__int64)v63,
              (__int64)&v70,
              (__int64)&v69,
              (__int64)v65);
          }
LABEL_59:
          VidSchTerminateContext((struct _VIDSCH_CONTEXT *)v16);
          return 0;
        }
        v24 = bTracingEnabled == 0;
        v44 = *(_OWORD *)&v72.Flags.0;
        hContext = v72.hContext;
        *(_OWORD *)(v16 + 920) = *(_OWORD *)&v72.hContext;
        *(_QWORD *)(v16 + 64) = hContext;
        v46 = *(_OWORD *)&v72.PrivateDriverDataSize;
        *(_OWORD *)(v16 + 936) = v44;
        v47 = *(_OWORD *)&v72.ContextInfo.AllocationListSize;
        *(_OWORD *)(v16 + 952) = v46;
        *(_QWORD *)&v46 = *(_QWORD *)&v72.ContextInfo.PagingCompanionNodeId;
        *(_OWORD *)(v16 + 968) = v47;
        *(_QWORD *)(v16 + 984) = v46;
        if ( !v24 )
        {
          v48 = *(_QWORD *)(a1 + 8);
          if ( !v48 )
            LODWORD(v48) = a1;
          if ( (byte_140086201 & 8) != 0 )
            McTemplateK0pqqqqqqqqppp_EtwWriteTransfer(
              (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) >> 4) & 1)) | 1,
              (unsigned int)EventCreateContext,
              v72.ContextInfo.AllocationListSize,
              v48,
              v72.NodeOrdinal,
              v72.EngineAffinity,
              v72.ContextInfo.DmaBufferSize,
              v72.ContextInfo.DmaBufferSegmentSet,
              v72.ContextInfo.DmaBufferPrivateDataSize,
              v72.ContextInfo.AllocationListSize,
              v72.ContextInfo.PatchLocationListSize,
              (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) & 0x10) != 0)) | 1,
              v16);
        }
      }
      else if ( bTracingEnabled )
      {
        v49 = *(unsigned int *)(v16 + 88);
        if ( (unsigned int)v49 < *(_DWORD *)(v3 + 88) )
        {
          v50 = *(_QWORD *)(v3 + 776);
          v51 = *(_DWORD *)a2 & 0x40;
          memset(LockHandle, 0, sizeof(LockHandle));
          if ( (unsigned int)v49 >= *(_DWORD *)(v3 + 848) )
          {
            v52 = v50;
          }
          else
          {
            v52 = v50 + 8 * v49;
            v50 = v52;
          }
          v53 = *(_QWORD *)(a1 + 8);
          if ( !v53 )
            LODWORD(v53) = a1;
          if ( (byte_140086201 & 8) != 0 )
            McTemplateK0pqqqqqqqqppp_EtwWriteTransfer(
              *(unsigned __int16 *)(*(_QWORD *)v52 + 8LL),
              (unsigned int)EventCreateContext,
              (v51 != 0 ? 5 : 1) | (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) >> 4) & 1)),
              v53,
              *(_WORD *)(*(_QWORD *)v52 + 8LL),
              1 << *(_BYTE *)(*(_QWORD *)v50 + 6LL),
              0,
              0,
              0,
              0,
              0,
              (v51 != 0 ? 5 : 1) | (2 * ((*(_DWORD *)(*(_QWORD *)(v16 + 104) + 56LL) & 0x10) != 0)),
              v16);
        }
      }
    }
    else
    {
      *(_QWORD *)(v16 + 64) = *(_QWORD *)(v64 + 184);
    }
    if ( (int)VidSchSetPriorityContext((struct _VIDSCH_CONTEXT *)v16, *((_DWORD *)a2 + 6), 0) >= 0 )
    {
      v54 = 0;
      v55 = *(_DWORD *)(v3 + 160) * (72 * *(_DWORD *)(v3 + 84) + 224) + 8 * (*(_DWORD *)(v3 + 84) + 113);
      v56 = 1136;
      if ( v55 > 0x470 )
        v56 = v55;
      v64 = v56;
      do
      {
        v57 = ExAllocatePool2(64, v56, 895576406);
        if ( !v57 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 5491;
          goto LABEL_59;
        }
        v68 = v3 + 2104;
        VidSchiInterlockedInsertTailList(v3 + 2104, v16 + 768, v57 + 8, v16 + 784);
        VidSchiFreeQueuePacket(v16);
        v56 = v64;
        ++v54;
      }
      while ( v54 < 5 );
      if ( (*(_DWORD *)a2 & 0x100) == 0 )
        return v16;
      v58 = *((_DWORD *)a2 + 7);
      if ( v58 )
      {
        v59 = 0;
        v60 = v64;
        while ( 1 )
        {
          v61 = ExAllocatePool2(64, v60, 895576406);
          if ( !v61 )
            break;
          v62 = v68;
          *(_DWORD *)(v61 + 64) |= 0x40u;
          VidSchiInterlockedInsertTailList(v62, v16 + 768, v61 + 8, v16 + 784);
          VidSchiFreeQueuePacket(v16);
          if ( ++v59 >= v58 )
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
0x1400419bc  mov     [rsp-8+arg_18], rbx
0x1400419c1  push    rbp
0x1400419c2  push    rsi
0x1400419c3  push    rdi
0x1400419c4  push    r12
0x1400419c6  push    r13
0x1400419c8  push    r14
0x1400419ca  push    r15
0x1400419cc  lea     rbp, [rsp-40h]
0x1400419d1  sub     rsp, 140h
0x1400419d8  mov     rax, cs:__security_cookie
0x1400419df  xor     rax, rsp
0x1400419e2  mov     [rbp+70h+var_40], rax
0x1400419e6  mov     r14, [rcx+28h]
0x1400419ea  mov     rbx, r8
0x1400419ed  mov     eax, [rdx+4]
0x1400419f0  mov     r13, rcx
0x1400419f3  mov     [rbp+70h+var_E8], rbx
0x1400419f7  mov     r12, rdx
0x1400419fa  mov     rcx, [r14+308h]
0x140041a01  cmp     eax, [r14+350h]
0x140041a08  jnb     short loc_140041A0E
0x140041a0a  lea     rcx, [rcx+rax*8]
0x140041a0e  mov     rax, [rcx]
0x140041a11  mov     rcx, r14
0x140041a14  mov     rdx, [r13+30h]
0x140041a18  movsxd  r8, dword ptr [rax+14h]
0x140041a1c  call    VidSchiCheckEngineAccess
0x140041a21  cmp     eax, 2
0x140041a24  jnz     short loc_140041A97
0x140041a26  lea     ecx, [rax-1]
0x140041a29  mov     rbx, r8
0x140041a2c  call    cs:__imp_WdLogSingleEntry2
0x140041a33  nop     dword ptr [rax+rax+00h]
0x140041a38  xor     esi, esi
0x140041a3a  mov     cs:WdLogGlobalForLineNumber, 142Fh
0x140041a44  mov     rax, [r13+30h]
0x140041a48  lea     r9, aProcess0xPCann; "Process 0x%p cannot create a context ag"...
0x140041a4f  mov     [rsp+170h+var_138], rsi
0x140041a54  mov     edx, 40000h
0x140041a59  mov     [rsp+170h+var_140], rsi
0x140041a5e  mov     qword ptr [rsp+170h+var_148], rbx
0x140041a63  mov     qword ptr [rsp+170h+var_150], rax
0x140041a68  call    DxgkLogInternalTriageEvent
0x140041a6d  xor     eax, eax
0x140041a6f  mov     rcx, [rbp+70h+var_40]
0x140041a73  xor     rcx, rsp; StackCookie
0x140041a76  call    __security_check_cookie
0x140041a7b  mov     rbx, [rsp+170h+arg_18]
0x140041a83  add     rsp, 140h
0x140041a8a  pop     r15
0x140041a8c  pop     r14
0x140041a8e  pop     r13
0x140041a90  pop     r12
0x140041a92  pop     rdi
0x140041a93  pop     rsi
0x140041a94  pop     rbp
0x140041a95  retn
0x140041a97  mov     eax, [r12]
0x140041a9b  xor     esi, esi
0x140041a9d  test    al, 4
0x140041a9f  jnz     short loc_140041AC1
0x140041aa1  test    rbx, rbx
0x140041aa4  jnz     short loc_140041AC1
0x140041aa6  lea     ecx, [rsi+3]
0x140041aa9  call    cs:__imp_WdLogSingleEntry0
0x140041ab0  nop     dword ptr [rax+rax+00h]
0x140041ab5  mov     cs:WdLogGlobalForLineNumber, 1438h
0x140041abf  jmp     short loc_140041A6D
0x140041ac1  mov     r15d, 34616956h
0x140041ac7  mov     edx, 3F0h
0x140041acc  mov     r8d, r15d
0x140041acf  mov     ecx, 40h ; '@'
0x140041ad4  call    cs:__imp_ExAllocatePool2
0x140041adb  nop     dword ptr [rax+rax+00h]
0x140041ae0  mov     rdi, rax
0x140041ae3  test    rax, rax
0x140041ae6  jnz     short loc_140041B06
0x140041ae8  lea     ecx, [rax+3]
0x140041aeb  call    cs:__imp_WdLogSingleEntry0
0x140041af2  nop     dword ptr [rax+rax+00h]
0x140041af7  mov     cs:WdLogGlobalForLineNumber, 1446h
0x140041b01  jmp     loc_140041A6D
0x140041b06  mov     [rax], r15d
0x140041b09  mov     [rax+38h], rbx
0x140041b0d  mov     [rax+68h], r13
0x140041b11  mov     rax, gs:188h
0x140041b1a  movups  xmm0, xmmword ptr [r12]
0x140041b1f  mov     rcx, [r14+308h]
0x140041b26  movups  xmm1, xmmword ptr [r12+10h]
0x140041b2c  mov     [rdi+50h], rax
0x140041b30  mov     eax, [r12+20h]
0x140041b35  movups  xmmword ptr [rdi+70h], xmm0
0x140041b39  movups  xmmword ptr [rdi+80h], xmm1
0x140041b40  mov     [rdi+90h], eax
0x140041b46  mov     eax, [r12+4]
0x140041b4b  mov     [rdi+58h], eax
0x140041b4e  cmp     eax, [r14+350h]
0x140041b55  jnb     short loc_140041B5B
0x140041b57  lea     rcx, [rcx+rax*8]
0x140041b5b  mov     rbx, [rcx]
0x140041b5e  mov     [rbp+70h+var_D8], rbx
0x140041b62  mov     [rdi+60h], rbx
0x140041b66  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140041b6b  xorps   xmm0, xmm0
0x140041b6e  mov     r15d, 1
0x140041b74  mov     [rdi+98h], r15
0x140041b7b  xor     r8d, r8d; State
0x140041b7e  mov     edx, r15d; Type
0x140041b81  mov     ecx, [rax+198h]
0x140041b87  xor     eax, eax
0x140041b89  shr     ecx, 8
0x140041b8c  and     cl, r15b
0x140041b8f  mov     [rdi+395h], cl
0x140041b95  lea     rcx, [rdi+148h]; Event
0x140041b9c  movups  xmmword ptr [rcx], xmm0
0x140041b9f  movups  xmmword ptr [rcx+10h], xmm0
0x140041ba3  movups  xmmword ptr [rcx+20h], xmm0
0x140041ba7  mov     [rcx+30h], rax
0x140041bab  call    cs:__imp_KeInitializeEvent
0x140041bb2  nop     dword ptr [rax+rax+00h]
0x140041bb7  test    dword ptr [r12], 100h
0x140041bbf  lea     rax, [rdi+180h]
0x140041bc6  mov     [rax+8], rax
0x140041bca  mov     [rax], rax
0x140041bcd  lea     rax, [rdi+2A0h]
0x140041bd4  mov     [rax+8], rax
0x140041bd8  mov     [rax], rax
0x140041bdb  lea     rax, [rdi+2B0h]
0x140041be2  mov     [rax+8], rax
0x140041be6  mov     [rax], rax
0x140041be9  lea     rax, [rdi+2C0h]
0x140041bf0  mov     [rax+8], rax
0x140041bf4  mov     [rax], rax
0x140041bf7  lea     rax, [rdi+2D0h]
0x140041bfe  mov     [rax+8], rax
0x140041c02  mov     [rax], rax
0x140041c05  jz      short loc_140041C15
0x140041c07  lea     rax, [rdi+2E8h]
0x140041c0e  mov     [rax+8], rax
0x140041c12  mov     [rax], rax
0x140041c15  lea     rax, [rdi+300h]
0x140041c1c  mov     rcx, rdi
0x140041c1f  mov     [rax+8], rax
0x140041c23  mov     [rax], rax
0x140041c26  mov     [rdi+394h], r15b
0x140041c2d  call    VidSchiIncrementContextReference
0x140041c32  xorps   xmm0, xmm0
0x140041c35  mov     [rdi+394h], sil
0x140041c3c  xor     eax, eax
0x140041c3e  lea     rcx, [r14+830h]; SpinLock
0x140041c45  lea     rdx, [rbp+70h+LockHandle]; LockHandle
0x140041c49  mov     qword ptr [rbp+70h+LockHandle+10h], rax
0x140041c4d  movups  xmmword ptr [rbp+70h+LockHandle], xmm0
0x140041c51  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140041c58  nop     dword ptr [rax+rax+00h]
0x140041c5d  cmp     [r13+678h], sil
0x140041c64  jnz     short loc_140041C78
0x140041c66  cmp     [r13+679h], sil
0x140041c6d  jnz     short loc_140041C78
0x140041c6f  lea     rcx, [rbx+0AA0h]
0x140041c76  jmp     short loc_140041C8F
0x140041c78  mov     eax, [rdi+0C0h]
0x140041c7e  lea     rcx, [rbx+0AC0h]
0x140041c85  bts     eax, 8
0x140041c89  mov     [rdi+0C0h], eax
0x140041c8f  mov     rdx, [rcx+8]
0x140041c93  cmp     [rdx], rcx
0x140041c96  jnz     loc_140042219
0x140041c9c  lea     rax, [rdi+8]
0x140041ca0  mov     [rax], rcx
0x140041ca3  mov     [rax+8], rdx
0x140041ca7  mov     [rdx], rax
0x140041caa  mov     [rcx+8], rax
0x140041cae  lea     rcx, [r13+50h]
0x140041cb2  mov     rdx, [rcx+8]
0x140041cb6  cmp     [rdx], rcx
0x140041cb9  jnz     loc_140042219
0x140041cbf  lea     rax, [rdi+18h]
0x140041cc3  mov     [rax], rcx
0x140041cc6  mov     [rax+8], rdx
0x140041cca  mov     [rdx], rax
0x140041ccd  mov     [rcx+8], rax
0x140041cd1  lea     rcx, [rbp+70h+LockHandle]; LockHandle
0x140041cd5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140041cdc  nop     dword ptr [rax+rax+00h]
0x140041ce1  mov     rcx, [r14+0BB0h]
0x140041ce8  mov     rax, [r14+0BE0h]
0x140041cef  mov     [rdi+1E0h], rcx
0x140041cf6  mov     [rdi+1C0h], rcx
0x140041cfd  lea     rcx, [rdi+208h]; Timer
0x140041d04  mov     [rdi+1E8h], rax
0x140041d0b  call    cs:__imp_KeInitializeTimer
0x140041d12  nop     dword ptr [rax+rax+00h]
0x140041d17  lea     rcx, [rdi+248h]; Dpc
0x140041d1e  mov     r8, rdi; DeferredContext
0x140041d21  lea     rdx, VidSchiDelayReadyRoutine; DeferredRoutine
0x140041d28  call    cs:__imp_KeInitializeDpc
0x140041d2f  nop     dword ptr [rax+rax+00h]
0x140041d34  mov     ebx, [r12]
0x140041d38  test    ebx, 604h
0x140041d3e  jnz     short loc_140041D54
0x140041d40  mov     rax, [rbp+70h+var_E8]
0x140041d44  mov     rax, [rax+0B8h]
0x140041d4b  mov     [rdi+40h], rax
0x140041d4f  jmp     loc_1400420C3
0x140041d54  test    r15b, bl
0x140041d57  jz      loc_140041FF7
0x140041d5d  xor     edx, edx; Val
0x140041d5f  lea     rcx, [rbp+70h+var_B0]; void *
0x140041d63  lea     r8d, [rdx+48h]; Size
0x140041d67  call    memset
0x140041d6c  mov     r8d, [rdi+58h]
0x140041d70  mov     rdx, [r14+308h]
0x140041d77  lea     rax, [rdx+r8*8]
0x140041d7b  cmp     r8d, [r14+350h]
0x140041d82  jb      short loc_140041D87
0x140041d84  mov     rax, rdx
0x140041d87  mov     rax, [rax]
0x140041d8a  movzx   ecx, word ptr [rax+8]
0x140041d8e  mov     [rbp+70h+var_B0.NodeOrdinal], ecx
0x140041d91  jnb     short loc_140041D97
0x140041d93  lea     rdx, [rdx+r8*8]
0x140041d97  mov     rcx, [rdx]
0x140041d9a  mov     r9d, ebx
0x140041d9d  shr     r9d, 1
0x140041da0  mov     eax, r15d
0x140041da3  and     r9d, 400h
0x140041daa  mov     cl, [rcx+6]
0x140041dad  shl     eax, cl
0x140041daf  mov     rcx, [r14+8]; this
0x140041db3  mov     [rbp+70h+var_B0.EngineAffinity], eax
0x140041db6  mov     eax, ebx
0x140041db8  and     eax, 200h
0x140041dbd  and     ebx, 4
0x140041dc0  or      r9d, eax
0x140041dc3  mov     rax, [rbp+70h+var_D8]
0x140041dc7  shr     r9d, 4
0x140041dcb  or      r9d, ebx
0x140041dce  shr     r9d, 2
0x140041dd2  movzx   eax, word ptr [rax+6]
0x140041dd6  imul    r8, rax, 160h
0x140041ddd  mov     dword ptr [rbp+70h+var_B0.Flags], r9d
0x140041de1  mov     rax, [rcx+10h]
0x140041de5  mov     rdx, [rax+0C20h]
0x140041dec  movzx   eax, byte ptr [r8+rdx+30h]
0x140041df2  lea     r8, [rbp+70h+var_B0]; struct _DXGKARG_CREATECONTEXT *
0x140041df6  mov     rdx, [r13+18h]; void *
0x140041dfa  and     eax, r15d
0x140041dfd  shl     eax, 2
0x140041e00  or      eax, r9d
0x140041e03  mov     dword ptr [rbp+70h+var_B0.Flags], eax
0x140041e06  call    ?DdiCreateContext@ADAPTER_RENDER@@QEAAJPEAXPEAU_DXGKARG_CREATECONTEXT@@@Z; ADAPTER_RENDER::DdiCreateContext(void *,_DXGKARG_CREATECONTEXT *)
0x140041e0b  mov     r8d, eax
0x140041e0e  test    eax, eax
0x140041e10  jns     loc_140041F35
0x140041e16  mov     rcx, [r14+8]
0x140041e1a  mov     rdx, [rcx+10h]
0x140041e1e  mov     ecx, [rdx+19Ch]
0x140041e24  mov     dword ptr [rbp+70h+var_E8], ecx
0x140041e27  mov     ecx, [rdx+1A0h]
0x140041e2d  mov     dword ptr [rbp+70h+var_E8+4], ecx
0x140041e30  mov     ecx, cs:dword_140086048
0x140041e36  cmp     ecx, 5
0x140041e39  jbe     loc_14004220C
0x140041e3f  mov     rdx, 400000000000h
0x140041e49  lea     rcx, dword_140086048
0x140041e50  call    _tlgKeywordOn
0x140041e55  test    al, al
0x140041e57  jz      loc_14004220C
0x140041e5d  mov     rdx, [rdi+38h]
0x140041e61  mov     [rbp+70h+var_E0], si
0x140041e65  mov     rax, [rdx+10h]
0x140041e69  mov     rcx, [rax+28h]
0x140041e6d  mov     rax, [rcx+40h]
0x140041e71  movups  xmm0, xmmword ptr [rax+90h]
0x140041e78  lea     rax, [rbp+70h+LockHandle]
0x140041e7c  mov     [rbp+70h+var_C8], rax
0x140041e80  mov     rax, [rdi+68h]
0x140041e84  movdqu  xmmword ptr [rbp+70h+LockHandle], xmm0
0x140041e89  mov     rcx, [rax+30h]
0x140041e8d  mov     rax, [rcx+0A58h]
0x140041e94  mov     [rbp+70h+var_C0], rax
0x140041e98  mov     al, [rdx+90h]
0x140041e9e  mov     rdx, [r14+8]
0x140041ea2  mov     [rbp+70h+var_F0], al
0x140041ea5  mov     rax, [rbp+70h+var_E8]
0x140041ea9  mov     [rbp+70h+var_B8], rax
0x140041ead  mov     rax, [rdx+10h]
0x140041eb1  mov     ecx, [rax+1A8h]
0x140041eb7  mov     [rbp+70h+var_DC], ecx
0x140041eba  mov     rax, [rdx+10h]
0x140041ebe  lea     rdx, byte_14007BE8F
0x140041ec5  mov     ecx, [rax+1A4h]
0x140041ecb  lea     rax, [rbp+70h+var_E0]
0x140041ecf  mov     [rsp+170h+var_110], rax
0x140041ed4  lea     rax, [rbp+70h+var_C8]
0x140041ed8  mov     [rsp+170h+var_118], rax
0x140041edd  lea     rax, [rbp+70h+var_C0]
0x140041ee1  mov     [rsp+170h+var_120], rax
  ... truncated ...
```
