# CTSThread::AddCallback(ITSAsyncCallback *,ITSAsyncResult *,ulong,unsigned __int64,ulong,ITSQueuedCallback * *,uint)

- ea: `0x180022f00`
- end: `0x1800232d0`
- name: `?AddCallback@CTSThread@@UEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@K_KKPEAPEAVITSQueuedCallback@@I@Z`
- size: `976`
- prototype: `__int64 __fastcall(CTSThread *this, struct ITSAsyncCallback *, struct ITSAsyncResult *, char, unsigned __int64, char, struct ITSQueuedCallback **, unsigned int)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800248a0`
- `0x1800249b0`
- `0x180024ac0`
- `0x180024af0`
- `0x180027e10`

## callees

- `0x180001564`
- `0x18000f068`
- `0x18000f08c`
- `0x1800144c8`
- `0x180017330`
- `0x18001c9d0`
- `0x18001d114`
- `0x180021b74`
- `0x180021bac`
- `0x180022390`
- `0x180022f00`
- `0x180026234`
- `0x180026254`
- `0x180026720`
- `0x180026b30`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x180022f67`: `Not adding callback since thread is in state: 0x%x`
- `0x18002303f`: `CreateInstance failed for CTSMsg!`
- `0x1800230d9`: `Unable to copy sp to listmsg`

## pseudocode

```c
__int64 __fastcall CTSThread::AddCallback(
        CTSThread *this,
        struct ITSAsyncCallback *a2,
        struct ITSAsyncResult *a3,
        char a4,
        unsigned __int64 a5,
        char a6,
        struct ITSQueuedCallback **a7,
        unsigned int a8)
{
  CTSThread *v8; // rbx
  CTSReaderWriterLock *v12; // r12
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int Instance; // r15d
  CTSThread *v17; // rsi
  __int64 v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  int ActivityIdPrefix; // eax
  int v23; // edx
  const char *v24; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  _QWORD *v31; // rax
  CTSThread *v32; // rsi
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  struct ITSQueuedCallback **v38; // rbx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  struct CTSMsg *v48; // [rsp+50h] [rbp-20h] BYREF
  __int64 v49; // [rsp+58h] [rbp-18h] BYREF
  const char *v50; // [rsp+60h] [rbp-10h] BYREF
  __int64 v51; // [rsp+B0h] [rbp+40h] BYREF
  struct ITSAsyncCallback *v52; // [rsp+B8h] [rbp+48h]

  v52 = a2;
  v8 = 0;
  v48 = 0;
  v49 = 0;
  v12 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::ReadLock((CTSThread *)((char *)this + 148));
  if ( (unsigned int)(*((_DWORD *)this + 20) - 2) > 1 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      LODWORD(v51) = *((_DWORD *)this + 20);
      v50 = "Not adding callback since thread is in state: 0x%x";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)byte_18003F645,
        v14,
        v15,
        (const unsigned __int16 **)&v50,
        (__int64)&v51);
    }
    Instance = -2092630002;
    goto LABEL_23;
  }
  v17 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 64LL))(*((_QWORD *)this + 24));
  if ( v18 )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v49);
    v8 = (CTSThread *)v18;
    v49 = v18;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v49);
    v17 = (CTSThread *)v18;
  }
  Instance = CTSMsg::CreateInstance(*((_QWORD *)this + 83), v52, a3, a5, a8, a6 & 1, this);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v19, v20, v21);
    v23 = 102;
    v24 = "CreateInstance failed for CTSMsg!";
LABEL_22:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)v24,
      Instance);
LABEL_23:
    CTSReaderWriterLock::ReadUnlock(v12);
    goto LABEL_42;
  }
  if ( v17 != this || (a4 & 1) != 0 )
  {
    v51 = 0;
    Instance = ComPlainSmartPtr<CTSMsg>::CopyTo(&v48, &v51);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_23;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v28, v29, v30);
      v23 = 103;
      v24 = "Unable to copy sp to listmsg";
      goto LABEL_22;
    }
    CTSCriticalSection::Lock((CTSThread *)((char *)this + 104));
    v31 = (_QWORD *)*((_QWORD *)this + 17);
    v32 = (CTSThread *)*((_QWORD *)this + 16);
    v33 = v51 + 88;
    *(_QWORD *)(v51 + 88) = (char *)this + 128;
    *(_QWORD *)(v33 + 8) = v31;
    *v31 = v33;
    ++*((_DWORD *)this + 30);
    *((_QWORD *)this + 17) = v33;
    CTSCriticalSection::UnLock((CTSThread *)((char *)this + 104));
    CTSReaderWriterLock::ReadUnlock(v12);
    if ( v32 != (CTSThread *)((char *)this + 128)
      || v8 == this && *((_DWORD *)this + 47)
      || (Instance = CTSThread::SignalEventQueue(this), Instance >= 0) )
    {
      v38 = a7;
      if ( a7 )
      {
        v51 = 0;
        Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v48 + 5))(
                     *((_QWORD *)v48 + 5),
                     &IID_ITSQueuedCallback,
                     &v51);
        if ( Instance >= 0 )
        {
          v43 = v51;
          *v38 = (struct ITSQueuedCallback *)v51;
          if ( v43 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
          Instance = 0;
          TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v51);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v42 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v39, v40, v41);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              105,
              (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
              v42,
              (__int64)"Unable to QI for IID_ITSQueuedCallback",
              Instance);
          }
          TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v51);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v34, v35, v36);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        v37,
        (__int64)"Failed to signal event queue",
        Instance);
    }
  }
  else
  {
    CTSReaderWriterLock::ReadUnlock(v12);
    CTSThread::RunQueueEvent(this, v48);
    CTSMsg::Terminate((struct CTSMsg *)((char *)v48 + 16));
    Instance = 0;
  }
LABEL_42:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v49);
  TCntPtr<CTSThread>::SafeRelease(&v48, v44, v45, v46);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180022f00  mov     [rsp-38h+arg_10], rbx
0x180022f05  mov     [rsp-38h+arg_8], rdx
0x180022f0a  push    rbp
0x180022f0b  push    rsi
0x180022f0c  push    rdi
0x180022f0d  push    r12
0x180022f0f  push    r13
0x180022f11  push    r14
0x180022f13  push    r15
0x180022f15  mov     rbp, rsp
0x180022f18  sub     rsp, 70h
0x180022f1c  xor     ebx, ebx
0x180022f1e  mov     [rbp+var_20], 0
0x180022f26  mov     [rbp+var_18], rbx
0x180022f2a  mov     r14d, r9d
0x180022f2d  mov     r15, r8
0x180022f30  mov     r13, rcx
0x180022f33  lea     r12, [rcx+94h]
0x180022f3a  mov     rcx, r12; this
0x180022f3d  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x180022f42  mov     eax, [r13+50h]
0x180022f46  sub     eax, 2
0x180022f49  cmp     eax, 1
0x180022f4c  jbe     short loc_180022F94
0x180022f4e  mov     eax, cs:dword_180044008
0x180022f54  cmp     eax, 5
0x180022f57  jbe     short loc_180022F89
0x180022f59  mov     eax, [r13+50h]
0x180022f5d  lea     rdx, byte_18003F645
0x180022f64  mov     dword ptr [rbp+arg_0], eax
0x180022f67  lea     rax, aNotAddingCallb; "Not adding callback since thread is in "...
0x180022f6e  mov     [rbp+var_10], rax
0x180022f72  lea     rax, [rbp+arg_0]
0x180022f76  mov     [rsp+70h+var_48], rax
0x180022f7b  lea     rax, [rbp+var_10]
0x180022f7f  mov     [rsp+70h+var_50], rax
0x180022f84  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180022f89  mov     r15d, 8345000Eh
0x180022f8f  jmp     loc_180023104
0x180022f94  mov     rcx, [r13+0C0h]
0x180022f9b  mov     rax, [rcx]
0x180022f9e  mov     rax, [rax+40h]
0x180022fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fa7  xor     esi, esi
0x180022fa9  mov     rdi, rax
0x180022fac  test    rax, rax
0x180022faf  jz      short loc_180022FCD
0x180022fb1  lea     rcx, [rbp+var_18]
0x180022fb5  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180022fba  mov     rbx, rdi
0x180022fbd  lea     rcx, [rbp+var_18]
0x180022fc1  mov     [rbp+var_18], rbx
0x180022fc5  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180022fca  mov     rsi, rdi
0x180022fcd  mov     eax, dword ptr [rbp+arg_28]
0x180022fd0  lea     rcx, [rbp+var_20]
0x180022fd4  mov     r9, [rbp+arg_20]
0x180022fd8  and     eax, 1
0x180022fdb  mov     rdx, [rbp+arg_8]
0x180022fdf  mov     r8, r15
0x180022fe2  mov     [rsp+70h+var_30], rcx
0x180022fe7  mov     rcx, [r13+298h]
0x180022fee  mov     [rsp+70h+var_40], r13
0x180022ff3  mov     dword ptr [rsp+70h+var_48], eax
0x180022ff7  mov     eax, [rbp+arg_38]
0x180022ffa  mov     dword ptr [rsp+70h+var_50], eax
0x180022ffe  call    ?CreateInstance@CTSMsg@@SAJPEAV?$CTSObjectPool@VCTSMsg@@@@PEAVITSAsyncCallback@@PEAVITSAsyncResult@@_KIHPEAVITSThread@@4PEAPEAV1@@Z; CTSMsg::CreateInstance(CTSObjectPool<CTSMsg> *,ITSAsyncCallback *,ITSAsyncResult *,unsigned __int64,uint,int,ITSThread *,ITSThread *,CTSMsg * *)
0x180023003  mov     r15d, eax
0x180023006  test    eax, eax
0x180023008  jns     short loc_18002304B
0x18002300a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023011  lea     rax, WPP_GLOBAL_Control
0x180023018  cmp     rcx, rax
0x18002301b  jz      loc_180023104
0x180023021  test    byte ptr [rcx+1Ch], 8
0x180023025  jz      loc_180023104
0x18002302b  cmp     byte ptr [rcx+19h], 2
0x18002302f  jb      loc_180023104
0x180023035  call    RdpX_GetActivityIdPrefix
0x18002303a  mov     edx, 66h ; 'f'
0x18002303f  lea     rcx, aCreateinstance_0; "CreateInstance failed for CTSMsg!"
0x180023046  jmp     loc_1800230E0
0x18002304b  cmp     rsi, r13
0x18002304e  jnz     short loc_180023094
0x180023050  test    r14b, 1
0x180023054  jnz     short loc_180023094
0x180023056  mov     rcx, r12; this
0x180023059  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x18002305e  mov     rbx, [rbp+var_20]
0x180023062  mov     rcx, r13; this
0x180023065  mov     rdx, rbx; struct CTSMsg *
0x180023068  call    ?RunQueueEvent@CTSThread@@IEAAJPEAVCTSMsg@@@Z; CTSThread::RunQueueEvent(CTSMsg *)
0x18002306d  lea     rcx, [rbx+10h]; this
0x180023071  call    ?Terminate@CTSMsg@@UEAAJXZ; CTSMsg::Terminate(void)
0x180023076  test    rbx, rbx
0x180023079  jz      short loc_18002308C
0x18002307b  lea     rcx, [rbp+var_20]
0x18002307f  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x180023084  mov     [rbp+var_20], 0
0x18002308c  xor     r15d, r15d
0x18002308f  jmp     loc_1800232A3
0x180023094  lea     rdx, [rbp+arg_0]
0x180023098  mov     [rbp+arg_0], 0
0x1800230a0  lea     rcx, [rbp+var_20]
0x1800230a4  call    ?CopyTo@?$ComPlainSmartPtr@VCTSMsg@@@@QEAAJPEAPEAVCTSMsg@@@Z; ComPlainSmartPtr<CTSMsg>::CopyTo(CTSMsg * *)
0x1800230a9  mov     r15d, eax
0x1800230ac  test    eax, eax
0x1800230ae  jns     short loc_180023111
0x1800230b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230b7  lea     rax, WPP_GLOBAL_Control
0x1800230be  cmp     rcx, rax
0x1800230c1  jz      short loc_180023104
0x1800230c3  test    byte ptr [rcx+1Ch], 8
0x1800230c7  jz      short loc_180023104
0x1800230c9  cmp     byte ptr [rcx+19h], 2
0x1800230cd  jb      short loc_180023104
0x1800230cf  call    RdpX_GetActivityIdPrefix
0x1800230d4  mov     edx, 67h ; 'g'
0x1800230d9  lea     rcx, aUnableToCopySp; "Unable to copy sp to listmsg"
0x1800230e0  mov     dword ptr [rsp+70h+var_48], r15d
0x1800230e5  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800230ec  mov     [rsp+70h+var_50], rcx
0x1800230f1  mov     r9d, eax
0x1800230f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230fb  mov     rcx, [rcx+10h]
0x1800230ff  call    WPP_SF_DsD
0x180023104  mov     rcx, r12; this
0x180023107  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x18002310c  jmp     loc_1800232A3
0x180023111  lea     rcx, [r13+68h]; this
0x180023115  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002311a  mov     r8, [rbp+arg_0]
0x18002311e  lea     rdx, [r13+80h]
0x180023125  mov     rax, [rdx+8]
0x180023129  lea     r14, [r13+80h]
0x180023130  mov     rsi, [r14]
0x180023133  lea     rcx, [r13+68h]; this
0x180023137  add     r8, 58h ; 'X'
0x18002313b  mov     [r8], rdx
0x18002313e  mov     [r8+8], rax
0x180023142  mov     [rax], r8
0x180023145  inc     dword ptr [r13+78h]
0x180023149  mov     [rdx+8], r8
0x18002314d  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180023152  mov     rcx, r12; this
0x180023155  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x18002315a  cmp     rsi, r14
0x18002315d  jnz     loc_1800231E6
0x180023163  cmp     rbx, r13
0x180023166  jnz     short loc_180023172
0x180023168  cmp     dword ptr [r13+0BCh], 0
0x180023170  jnz     short loc_1800231E6
0x180023172  mov     rcx, r13; this
0x180023175  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x18002317a  mov     r15d, eax
0x18002317d  test    eax, eax
0x18002317f  jns     short loc_1800231E6
0x180023181  mov     rcx, cs:WPP_GLOBAL_Control
0x180023188  lea     rax, WPP_GLOBAL_Control
0x18002318f  cmp     rcx, rax
0x180023192  jz      loc_1800232A3
0x180023198  test    byte ptr [rcx+1Ch], 8
0x18002319c  jz      loc_1800232A3
0x1800231a2  cmp     byte ptr [rcx+19h], 2
0x1800231a6  jb      loc_1800232A3
0x1800231ac  call    RdpX_GetActivityIdPrefix
0x1800231b1  lea     rcx, aFailedToSignal; "Failed to signal event queue"
0x1800231b8  mov     dword ptr [rsp+70h+var_48], r15d
0x1800231bd  mov     [rsp+70h+var_50], rcx
0x1800231c2  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800231c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231d0  mov     edx, 68h ; 'h'
0x1800231d5  mov     r9d, eax
0x1800231d8  mov     rcx, [rcx+10h]
0x1800231dc  call    WPP_SF_DsD
0x1800231e1  jmp     loc_1800232A3
0x1800231e6  mov     rbx, [rbp+arg_30]
0x1800231ea  test    rbx, rbx
0x1800231ed  jz      loc_1800232A3
0x1800231f3  mov     rax, [rbp+var_20]
0x1800231f7  lea     r8, [rbp+arg_0]
0x1800231fb  mov     [rbp+arg_0], 0
0x180023203  lea     rdx, IID_ITSQueuedCallback
0x18002320a  mov     rcx, [rax+28h]
0x18002320e  mov     rax, [rcx]
0x180023211  mov     rax, [rax]
0x180023214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023219  mov     r15d, eax
0x18002321c  test    eax, eax
0x18002321e  jns     short loc_18002327F
0x180023220  mov     rcx, cs:WPP_GLOBAL_Control
0x180023227  lea     rax, WPP_GLOBAL_Control
0x18002322e  cmp     rcx, rax
0x180023231  jz      short loc_180023274
0x180023233  test    byte ptr [rcx+1Ch], 8
0x180023237  jz      short loc_180023274
0x180023239  cmp     byte ptr [rcx+19h], 2
0x18002323d  jb      short loc_180023274
0x18002323f  call    RdpX_GetActivityIdPrefix
0x180023244  lea     rcx, aUnableToQiForI; "Unable to QI for IID_ITSQueuedCallback"
0x18002324b  mov     dword ptr [rsp+70h+var_48], r15d
0x180023250  mov     [rsp+70h+var_50], rcx
0x180023255  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18002325c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023263  mov     edx, 69h ; 'i'
0x180023268  mov     r9d, eax
0x18002326b  mov     rcx, [rcx+10h]
0x18002326f  call    WPP_SF_DsD
0x180023274  lea     rcx, [rbp+arg_0]
0x180023278  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18002327d  jmp     short loc_1800232A3
0x18002327f  mov     rcx, [rbp+arg_0]
0x180023283  mov     [rbx], rcx
0x180023286  test    rcx, rcx
0x180023289  jz      short loc_180023297
0x18002328b  mov     rax, [rcx]
0x18002328e  mov     rax, [rax+8]
0x180023292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023297  xor     r15d, r15d
0x18002329a  lea     rcx, [rbp+arg_0]
0x18002329e  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800232a3  lea     rcx, [rbp+var_18]
0x1800232a7  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800232ac  lea     rcx, [rbp+var_20]
0x1800232b0  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x1800232b5  mov     rbx, [rsp+70h+arg_10]
0x1800232bd  mov     eax, r15d
0x1800232c0  add     rsp, 70h
0x1800232c4  pop     r15
0x1800232c6  pop     r14
0x1800232c8  pop     r13
0x1800232ca  pop     r12
0x1800232cc  pop     rdi
0x1800232cd  pop     rsi
0x1800232ce  pop     rbp
0x1800232cf  retn
```
