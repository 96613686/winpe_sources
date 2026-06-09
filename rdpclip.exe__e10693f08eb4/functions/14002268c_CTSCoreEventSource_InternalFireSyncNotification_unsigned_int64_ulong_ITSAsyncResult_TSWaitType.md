# CTSCoreEventSource::InternalFireSyncNotification(unsigned __int64,ulong *,ITSAsyncResult *,TSWaitType)

- ea: `0x14002268c`
- end: `0x140022d5a`
- name: `?InternalFireSyncNotification@CTSCoreEventSource@@AEAAJ_KPEAKPEAVITSAsyncResult@@W4TSWaitType@@@Z`
- size: `1742`
- prototype: `int __high(unsigned __int64, unsigned int *, struct ITSAsyncResult *, enum TSWaitType)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140022070`
- `0x140022140`
- `0x140022160`

## callees

- `0x14000142c`
- `0x1400014d4`
- `0x1400015ec`
- `0x140001c24`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14000cae0`
- `0x140010500`
- `0x140010528`
- `0x140019e80`
- `0x14001a1a8`
- `0x14001c620`
- `0x14001c660`
- `0x14001da74`
- `0x140021534`
- `0x1400222d8`
- `0x14002268c`
- `0x140024e24`
- `0x140025450`
- `0x1400256b4`
- `0x14006a120`
- `0x14006b010`

## string_xrefs

- `0x140022bc5`: `WaitForCompletion timeout: 0x%x`
- `0x140022994`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventsvc.cpp`
- `0x140022bb2`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventsvc.cpp`
- `0x140022c59`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventsvc.cpp`
- `0x1400229a7`: `Failed to make a copy of the sink list!`
- `0x140022ae6`: `Sync wait completed ok for SyncNotify: 0x%x`

## pseudocode

```c
__int64 __fastcall CTSCoreEventSource::InternalFireSyncNotification(
        __int64 a1,
        const char *a2,
        __int64 a3,
        struct ITSAsyncResult *a4,
        unsigned int a5)
{
  CTSSyncWaitResult *v6; // r13
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v10; // rbx
  __int64 v11; // rbx
  int PooledObject; // r14d
  int ActivityIdPrefix; // eax
  int v14; // eax
  int v15; // eax
  CVPtrList *v16; // r8
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  CVPtrList *v20; // rcx
  CTSCoreEventSink *v21; // r14
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // r14d
  CVPtrList *v26; // rcx
  CTSCoreEventSink *v27; // r12
  const char *v28; // rbx
  struct ITSThread *TargetThread; // rax
  CTSSyncWaitResult *v30; // r14
  const char *v31; // r14
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ebx
  unsigned int v39; // eax
  int v41; // [rsp+60h] [rbp-A0h] BYREF
  CTSSyncWaitResult *v42; // [rsp+68h] [rbp-98h] BYREF
  void *v43; // [rsp+70h] [rbp-90h] BYREF
  CTSSyncWaitResult *v44; // [rsp+78h] [rbp-88h] BYREF
  CTSCoreEventSink *v45; // [rsp+80h] [rbp-80h] BYREF
  const char *v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  const char *v48; // [rsp+98h] [rbp-68h] BYREF
  const char *v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  const char *v51; // [rsp+B0h] [rbp-50h] BYREF
  const char *v52; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-40h] BYREF
  CVPtrList *v54; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v55; // [rsp+D8h] [rbp-28h]
  int v56; // [rsp+E0h] [rbp-20h]
  _QWORD v57[50]; // [rsp+E8h] [rbp-18h] BYREF
  CVPtrList *v58; // [rsp+278h] [rbp+178h]

  v48 = a2;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  v42 = 0;
  v8 = 0;
  v47 = 0;
  v50 = 0;
  CVPtrList::CVPtrList((CVPtrList *)&v54);
  v10 = *(_QWORD *)(*(_QWORD *)(a1 + 544) + 2120LL);
  v53 = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 64LL))(v10);
  if ( v11 )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v50);
    v50 = v11;
    v8 = v11;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v50);
  }
  CTSReaderWriterLock::ReadLock((CTSReaderWriterLock *)(a1 + 72));
  if ( !*(_DWORD *)(a1 + 528) )
  {
    PooledObject = 0;
LABEL_7:
    CTSReaderWriterLock::ReadUnlock((CTSReaderWriterLock *)(a1 + 72));
    goto LABEL_62;
  }
  if ( (*(_BYTE *)(a1 + 536) & 1) != 0 )
  {
    if ( !a4 )
      goto LABEL_25;
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v47);
    v7 = (__int64)a4;
    v47 = (__int64)a4;
    goto LABEL_24;
  }
  PooledObject = CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(*(_QWORD *)(a1 + 552), &v42);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids,
        ActivityIdPrefix,
        (__int64)"Unable to get a SyncWaitResult from pool!",
        PooledObject);
    }
    CTSReaderWriterLock::ReadUnlock((CTSReaderWriterLock *)(a1 + 72));
    v6 = v42;
    goto LABEL_62;
  }
  v6 = v42;
  PooledObject = CTSSyncWaitResult::InitializeForReuse(v42, a4);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids,
        v14,
        (__int64)"InitializeForReuse failed!",
        PooledObject);
    }
    goto LABEL_7;
  }
  if ( (((unsigned __int64)v6 + 80) & -(__int64)(v6 != 0)) != 0 )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v47);
    v7 = ((unsigned __int64)v6 + 80) & -(__int64)(v6 != 0);
    v47 = v7;
LABEL_24:
    TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v47);
  }
LABEL_25:
  v15 = *(_DWORD *)(a1 + 528);
  v57[49] = 0;
  if ( v15 )
    v56 = v15;
  v16 = v54;
  v17 = v57;
  v55 = v57;
  v18 = 0;
  v57[0] = 0;
  while ( 1 )
  {
    v19 = 3 * v18++;
    v20 = (CVPtrList *)&v17[v19 + 1];
    *((_QWORD *)v20 + 1) = v16;
    v16 = v20;
    v54 = v20;
    if ( v18 == 16 )
      break;
    v17 = v55;
  }
  v43 = *(void **)(a1 + 512);
  while ( (unsigned int)CVPtrList::GetNext(v20, &v43, (void **)&v45) )
  {
    v21 = v45;
    if ( !CVPtrList::AddTail((CVPtrList *)&v54, v45) )
    {
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        v41 = 1827;
        v42 = (CTSSyncWaitResult *)"InternalFireSyncNotification";
        LODWORD(v44) = -2147467259;
        v46 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventsvc.cpp";
        v43 = "Failed to make a copy of the sink list!";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)&dword_14007EFF4,
          v23,
          v24,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v46,
          (__int64)&v41,
          (__int64)&v42);
      }
      PooledObject = -2092629993;
      CTSReaderWriterLock::ReadUnlock((CTSReaderWriterLock *)(a1 + 72));
      goto LABEL_61;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 + 4) + 8LL))(*((_QWORD *)v21 + 4));
  }
  v25 = 0;
  v41 = 0;
  CTSReaderWriterLock::ReadUnlock((CTSReaderWriterLock *)(a1 + 72));
  v26 = v58;
  v43 = v58;
  while ( (unsigned int)CVPtrList::GetNext(v26, &v43, (void **)&v45) )
  {
    v27 = v45;
    v28 = 0;
    v42 = 0;
    v46 = 0;
    TargetThread = CTSCoreEventSink::GetTargetThread(v45);
    v44 = 0;
    v30 = TargetThread;
    if ( TargetThread )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v42);
      v42 = v30;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v42);
      v44 = v30;
    }
    v31 = (const char *)*((_QWORD *)v27 + 7);
    if ( v31 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v46);
      v28 = v31;
      v46 = v31;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v46);
    }
    PooledObject = (*(__int64 (__fastcall **)(CTSSyncWaitResult *, const char *, __int64, _QWORD, const char *, int, _QWORD, _DWORD))(*(_QWORD *)v44 + 112LL))(
                     v44,
                     v28,
                     v7,
                     0,
                     v48,
                     1,
                     0,
                     *(_DWORD *)(a1 + 56));
    if ( PooledObject < 0 )
    {
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        LODWORD(v43) = *(_DWORD *)(a1 + 56);
        v49 = "InternalFireSyncNotification";
        v48 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventsvc.cpp";
        v52 = "Callback 0x%p failed for event:0x%x";
        v51 = v28;
        LODWORD(v44) = 1892;
        v41 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v32,
          (unsigned int)&unk_14007EF18,
          v33,
          v34,
          (__int64)&v52,
          (__int64)&v41,
          (__int64)&v48,
          (__int64)&v44,
          (__int64)&v49,
          (__int64)&v51,
          (__int64)&v43);
      }
      goto LABEL_57;
    }
    if ( v6 )
    {
      v35 = CTSSyncWaitResult::WaitForCompletion((__int64)v6, a5, v8);
      if ( v35 < 0 )
      {
        if ( (unsigned int)dword_1400880C8 > 2 )
        {
          LODWORD(v44) = v35;
          v49 = "InternalFireSyncNotification";
          v41 = 1884;
          v48 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventsvc.cpp";
          v51 = "WaitForCompletion timeout: 0x%x";
          LODWORD(v43) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)qword_14007EF80,
            v36,
            v37,
            (__int64)&v51,
            (__int64)&v43,
            (__int64)&v48,
            (__int64)&v41,
            (__int64)&v49,
            (__int64)&v44);
        }
        PooledObject = -2092630013;
LABEL_57:
        TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v46);
        TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v42);
        goto LABEL_61;
      }
      if ( (unsigned int)dword_1400880C8 > 5 )
      {
        LODWORD(v44) = *(_DWORD *)(a1 + 56);
        v49 = "Sync wait completed ok for SyncNotify: 0x%x";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v35,
          (unsigned int)byte_14007EFC9,
          v36,
          v37,
          (__int64)&v49,
          (__int64)&v44);
      }
    }
    v25 = ++v41;
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v46);
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v42);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v38 = *(_DWORD *)(a1 + 56);
    v39 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids, v39, v25, v38);
  }
  PooledObject = 0;
LABEL_61:
  while ( (unsigned int)CVPtrList::RemoveHead((CVPtrList *)&v54, (void **)&v45) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v45 + 4) + 16LL))(*((_QWORD *)v45 + 4));
LABEL_62:
  CVPtrList::~CVPtrList((CVPtrList *)&v54);
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v50);
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v53);
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v47);
  if ( v6 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 4) + 16LL))(*((_QWORD *)v6 + 4));
  return (unsigned int)PooledObject;
}

```

## disassembly

```asm
0x14002268c  mov     [rsp-8+arg_10], rbx
0x140022691  push    rbp
0x140022692  push    rsi
0x140022693  push    rdi
0x140022694  push    r12
0x140022696  push    r13
0x140022698  push    r14
0x14002269a  push    r15
0x14002269c  lea     rbp, [rsp-1A0h]
0x1400226a4  sub     rsp, 2A0h
0x1400226ab  mov     rax, cs:__security_cookie
0x1400226b2  xor     rax, rsp
0x1400226b5  mov     [rbp+1D0h+var_40], rax
0x1400226bc  mov     r15, rcx
0x1400226bf  mov     [rbp+1D0h+var_238], rdx
0x1400226c3  xor     r13d, r13d
0x1400226c6  mov     [rbp+1D0h+var_250], 0
0x1400226ce  xor     edi, edi
0x1400226d0  mov     [rsp+2D0h+var_268], r13
0x1400226d5  xor     esi, esi
0x1400226d7  mov     [rbp+1D0h+var_240], rdi
0x1400226db  lea     rcx, [rbp+1D0h+var_200]; this
0x1400226df  mov     [rbp+1D0h+var_228], rsi
0x1400226e3  mov     r12, r9
0x1400226e6  call    ??0CVPtrList@@QEAA@XZ; CVPtrList::CVPtrList(void)
0x1400226eb  mov     rax, [r15+220h]
0x1400226f2  mov     rbx, [rax+848h]
0x1400226f9  mov     [rbp+1D0h+var_210], rbx
0x1400226fd  test    rbx, rbx
0x140022700  jz      short loc_140022711
0x140022702  mov     rax, [rbx]
0x140022705  mov     rcx, rbx
0x140022708  mov     rax, [rax+8]
0x14002270c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022711  mov     rax, [rbx]
0x140022714  mov     rcx, rbx
0x140022717  mov     rax, [rax+40h]
0x14002271b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022720  mov     rbx, rax
0x140022723  test    rax, rax
0x140022726  jz      short loc_140022741
0x140022728  lea     rcx, [rbp+1D0h+var_228]
0x14002272c  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140022731  lea     rcx, [rbp+1D0h+var_228]
0x140022735  mov     [rbp+1D0h+var_228], rbx
0x140022739  mov     rsi, rbx
0x14002273c  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140022741  lea     rbx, [r15+48h]
0x140022745  mov     rcx, rbx; this
0x140022748  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x14002274d  cmp     [r15+210h], edi
0x140022754  jnz     short loc_140022766
0x140022756  xor     r14d, r14d
0x140022759  mov     rcx, rbx; this
0x14002275c  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x140022761  jmp     loc_140022CF4
0x140022766  test    byte ptr [r15+218h], 1
0x14002276e  jz      short loc_14002278E
0x140022770  test    r12, r12
0x140022773  jz      loc_1400228B3
0x140022779  lea     rcx, [rbp+1D0h+var_240]
0x14002277d  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140022782  mov     rdi, r12
0x140022785  mov     [rbp+1D0h+var_240], r12
0x140022789  jmp     loc_1400228AA
0x14002278e  mov     rcx, [r15+228h]
0x140022795  lea     rdx, [rsp+2D0h+var_268]
0x14002279a  call    ?GetPooledObject@?$CTSObjectPool@VCTSSyncWaitResult@@@@QEAAJPEAPEAVCTSSyncWaitResult@@H@Z; CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(CTSSyncWaitResult * *,int)
0x14002279f  mov     r14d, eax
0x1400227a2  test    eax, eax
0x1400227a4  jns     short loc_14002280C
0x1400227a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400227ad  lea     rax, WPP_GLOBAL_Control
0x1400227b4  cmp     rcx, rax
0x1400227b7  jz      short loc_1400227FA
0x1400227b9  test    byte ptr [rcx+1Ch], 8
0x1400227bd  jz      short loc_1400227FA
0x1400227bf  cmp     byte ptr [rcx+19h], 2
0x1400227c3  jb      short loc_1400227FA
0x1400227c5  call    RdpX_GetActivityIdPrefix
0x1400227ca  lea     rcx, aUnableToGetASy; "Unable to get a SyncWaitResult from poo"...
0x1400227d1  mov     dword ptr [rsp+2D0h+var_2A8], r14d
0x1400227d6  mov     [rsp+2D0h+var_2B0], rcx
0x1400227db  lea     r8, WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids
0x1400227e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400227e9  mov     edx, 55h ; 'U'
0x1400227ee  mov     r9d, eax
0x1400227f1  mov     rcx, [rcx+10h]
0x1400227f5  call    WPP_SF_DsD
0x1400227fa  mov     rcx, rbx; this
0x1400227fd  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x140022802  mov     r13, [rsp+2D0h+var_268]
0x140022807  jmp     loc_140022CF4
0x14002280c  mov     r13, [rsp+2D0h+var_268]
0x140022811  mov     rdx, r12; struct ITSAsyncResult *
0x140022814  mov     rcx, r13; this
0x140022817  call    ?InitializeForReuse@CTSSyncWaitResult@@QEAAJPEAVITSAsyncResult@@@Z; CTSSyncWaitResult::InitializeForReuse(ITSAsyncResult *)
0x14002281c  mov     r14d, eax
0x14002281f  test    eax, eax
0x140022821  jns     short loc_140022888
0x140022823  mov     rcx, cs:WPP_GLOBAL_Control
0x14002282a  lea     rax, WPP_GLOBAL_Control
0x140022831  cmp     rcx, rax
0x140022834  jz      loc_140022759
0x14002283a  test    byte ptr [rcx+1Ch], 8
0x14002283e  jz      loc_140022759
0x140022844  cmp     byte ptr [rcx+19h], 2
0x140022848  jb      loc_140022759
0x14002284e  call    RdpX_GetActivityIdPrefix
0x140022853  lea     rcx, aInitializeforr; "InitializeForReuse failed!"
0x14002285a  mov     dword ptr [rsp+2D0h+var_2A8], r14d
0x14002285f  mov     [rsp+2D0h+var_2B0], rcx
0x140022864  lea     r8, WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids
0x14002286b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022872  mov     edx, 56h ; 'V'
0x140022877  mov     r9d, eax
0x14002287a  mov     rcx, [rcx+10h]
0x14002287e  call    WPP_SF_DsD
0x140022883  jmp     loc_140022759
0x140022888  mov     rax, r13
0x14002288b  lea     rcx, [r13+50h]
0x14002288f  neg     rax
0x140022892  sbb     r14, r14
0x140022895  and     r14, rcx
0x140022898  jz      short loc_1400228B3
0x14002289a  lea     rcx, [rbp+1D0h+var_240]
0x14002289e  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400228a3  mov     rdi, r14
0x1400228a6  mov     [rbp+1D0h+var_240], r14
0x1400228aa  lea     rcx, [rbp+1D0h+var_240]
0x1400228ae  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x1400228b3  mov     eax, [r15+210h]
0x1400228ba  mov     [rbp+1D0h+var_60], 0
0x1400228c5  test    eax, eax
0x1400228c7  jz      short loc_1400228CC
0x1400228c9  mov     [rbp+1D0h+var_1F0], eax
0x1400228cc  mov     r8, [rbp+1D0h+var_200]
0x1400228d0  lea     rcx, [rbp+1D0h+var_1E8]
0x1400228d4  mov     [rbp+1D0h+var_1F8], rcx
0x1400228d8  xor     edx, edx
0x1400228da  mov     [rbp+1D0h+var_1E8], 0
0x1400228e2  lea     rax, [rdx+rdx*2]
0x1400228e6  inc     rdx
0x1400228e9  lea     rcx, [rcx+rax*8]
0x1400228ed  add     rcx, 8
0x1400228f1  mov     [rcx+8], r8
0x1400228f5  mov     r8, rcx
0x1400228f8  mov     [rbp+1D0h+var_200], rcx
0x1400228fc  cmp     rdx, 10h
0x140022900  jz      short loc_140022908
0x140022902  mov     rcx, [rbp+1D0h+var_1F8]
0x140022906  jmp     short loc_1400228E2
0x140022908  mov     rax, [r15+200h]
0x14002290f  mov     [rsp+2D0h+var_260], rax
0x140022914  jmp     short loc_14002293B
0x140022916  mov     r14, [rbp+1D0h+var_250]
0x14002291a  lea     rcx, [rbp+1D0h+var_200]; this
0x14002291e  mov     rdx, r14; void *
0x140022921  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x140022926  test    rax, rax
0x140022929  jz      short loc_14002296E
0x14002292b  mov     rcx, [r14+20h]
0x14002292f  mov     rax, [rcx]
0x140022932  mov     rax, [rax+8]
0x140022936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002293b  lea     r8, [rbp+1D0h+var_250]; void **
0x14002293f  lea     rdx, [rsp+2D0h+var_260]; void **
0x140022944  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x140022949  test    eax, eax
0x14002294b  jnz     short loc_140022916
0x14002294d  xor     r14d, r14d
0x140022950  mov     rcx, rbx; this
0x140022953  mov     [rsp+2D0h+var_270], r14d
0x140022958  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x14002295d  mov     rcx, [rbp+1D0h+var_58]
0x140022964  mov     [rsp+2D0h+var_260], rcx
0x140022969  jmp     loc_140022B29
0x14002296e  mov     eax, cs:dword_1400880C8
0x140022974  cmp     eax, 2
0x140022977  jbe     short loc_1400229E9
0x140022979  lea     rax, aInternalfiresy; "InternalFireSyncNotification"
0x140022980  mov     [rsp+2D0h+var_270], 723h
0x140022988  mov     [rsp+2D0h+var_268], rax
0x14002298d  lea     rdx, dword_14007EFF4
0x140022994  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14002299b  mov     dword ptr [rsp+2D0h+var_258], 80004005h
0x1400229a3  mov     [rbp+1D0h+var_248], rax
0x1400229a7  lea     rax, aFailedToMakeAC; "Failed to make a copy of the sink list!"
0x1400229ae  mov     [rsp+2D0h+var_260], rax
0x1400229b3  lea     rax, [rsp+2D0h+var_268]
0x1400229b8  mov     [rsp+2D0h+var_290], rax
0x1400229bd  lea     rax, [rsp+2D0h+var_270]
0x1400229c2  mov     [rsp+2D0h+var_298], rax
0x1400229c7  lea     rax, [rbp+1D0h+var_248]
0x1400229cb  mov     [rsp+2D0h+var_2A0], rax
0x1400229d0  lea     rax, [rsp+2D0h+var_258]
0x1400229d5  mov     [rsp+2D0h+var_2A8], rax
0x1400229da  lea     rax, [rsp+2D0h+var_260]
0x1400229df  mov     [rsp+2D0h+var_2B0], rax
0x1400229e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400229e9  mov     rcx, rbx; this
0x1400229ec  mov     r14d, 83450017h
0x1400229f2  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x1400229f7  jmp     loc_140022CE3
0x1400229fc  mov     r12, [rbp+1D0h+var_250]
0x140022a00  xor     ebx, ebx
0x140022a02  mov     rcx, r12; this
0x140022a05  mov     [rsp+2D0h+var_268], 0
0x140022a0e  mov     [rbp+1D0h+var_248], rbx
0x140022a12  call    ?GetTargetThread@CTSCoreEventSink@@QEAAPEAVITSThread@@XZ; CTSCoreEventSink::GetTargetThread(void)
0x140022a17  mov     [rsp+2D0h+var_258], rbx
0x140022a1c  mov     r14, rax
0x140022a1f  test    rax, rax
0x140022a22  jz      short loc_140022A42
0x140022a24  lea     rcx, [rsp+2D0h+var_268]
0x140022a29  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140022a2e  lea     rcx, [rsp+2D0h+var_268]
0x140022a33  mov     [rsp+2D0h+var_268], r14
0x140022a38  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140022a3d  mov     [rsp+2D0h+var_258], r14
0x140022a42  mov     r14, [r12+38h]
0x140022a47  test    r14, r14
0x140022a4a  jz      short loc_140022A65
0x140022a4c  lea     rcx, [rbp+1D0h+var_248]
0x140022a50  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140022a55  mov     rbx, r14
0x140022a58  lea     rcx, [rbp+1D0h+var_248]
0x140022a5c  mov     [rbp+1D0h+var_248], rbx
0x140022a60  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140022a65  mov     edx, [r15+38h]
0x140022a69  xor     r9d, r9d
0x140022a6c  mov     rcx, [rsp+2D0h+var_258]
0x140022a71  mov     r8, rdi
0x140022a74  mov     dword ptr [rsp+2D0h+var_298], edx
0x140022a78  mov     rdx, [rbp+1D0h+var_238]
0x140022a7c  mov     [rsp+2D0h+var_2A0], 0
0x140022a85  mov     rax, [rcx]
0x140022a88  mov     dword ptr [rsp+2D0h+var_2A8], 1
0x140022a90  mov     [rsp+2D0h+var_2B0], rdx
0x140022a95  mov     rdx, rbx
0x140022a98  mov     rax, [rax+70h]
0x140022a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022aa1  mov     r14d, eax
0x140022aa4  test    eax, eax
0x140022aa6  js      loc_140022C34
0x140022aac  test    r13, r13
0x140022aaf  jz      short loc_140022B09
0x140022ab1  mov     edx, [rbp+1D0h+arg_20]
0x140022ab7  mov     r8, rsi
0x140022aba  mov     rcx, r13
0x140022abd  call    ?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z; CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)
0x140022ac2  mov     ecx, eax
0x140022ac4  test    eax, eax
0x140022ac6  mov     eax, cs:dword_1400880C8
0x140022acc  js      loc_140022B97
0x140022ad2  cmp     eax, 5
0x140022ad5  jbe     short loc_140022B09
0x140022ad7  mov     eax, [r15+38h]
0x140022adb  lea     rdx, byte_14007EFC9
0x140022ae2  mov     dword ptr [rsp+2D0h+var_258], eax
0x140022ae6  lea     rax, aSyncWaitComple; "Sync wait completed ok for SyncNotify: "...
0x140022aed  mov     [rbp+1D0h+var_230], rax
0x140022af1  lea     rax, [rsp+2D0h+var_258]
0x140022af6  mov     [rsp+2D0h+var_2A8], rax
0x140022afb  lea     rax, [rbp+1D0h+var_230]
0x140022aff  mov     [rsp+2D0h+var_2B0], rax
0x140022b04  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140022b09  mov     r14d, [rsp+2D0h+var_270]
0x140022b0e  lea     rcx, [rbp+1D0h+var_248]
0x140022b12  inc     r14d
0x140022b15  mov     [rsp+2D0h+var_270], r14d
0x140022b1a  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140022b1f  lea     rcx, [rsp+2D0h+var_268]
0x140022b24  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140022b29  lea     r8, [rbp+1D0h+var_250]; void **
0x140022b2d  lea     rdx, [rsp+2D0h+var_260]; void **
0x140022b32  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x140022b37  test    eax, eax
0x140022b39  jnz     loc_1400229FC
0x140022b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b46  lea     rax, WPP_GLOBAL_Control
0x140022b4d  cmp     rcx, rax
0x140022b50  jz      short loc_140022B8F
0x140022b52  test    byte ptr [rcx+1Ch], 1
0x140022b56  jz      short loc_140022B8F
0x140022b58  cmp     byte ptr [rcx+19h], 5
0x140022b5c  jb      short loc_140022B8F
0x140022b5e  mov     ebx, [r15+38h]
0x140022b62  call    RdpX_GetActivityIdPrefix
0x140022b67  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b6e  lea     r8, WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids
0x140022b75  mov     edx, 58h ; 'X'
0x140022b7a  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x140022b7e  mov     r9d, eax
0x140022b81  mov     dword ptr [rsp+2D0h+var_2B0], r14d
0x140022b86  mov     rcx, [rcx+10h]
0x140022b8a  call    WPP_SF_DdD
0x140022b8f  xor     r14d, r14d
0x140022b92  jmp     loc_140022CE3
0x140022b97  cmp     eax, 2
  ... truncated ...
```
