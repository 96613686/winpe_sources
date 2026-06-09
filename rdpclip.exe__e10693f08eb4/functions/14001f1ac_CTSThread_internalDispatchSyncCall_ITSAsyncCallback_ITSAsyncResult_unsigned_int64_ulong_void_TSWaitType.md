# CTSThread::internalDispatchSyncCall(ITSAsyncCallback *,ITSAsyncResult *,unsigned __int64,ulong,void *,TSWaitType)

- ea: `0x14001f1ac`
- end: `0x14001f62e`
- name: `?internalDispatchSyncCall@CTSThread@@IEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@_KKPEAXW4TSWaitType@@@Z`
- size: `1154`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c180`
- `0x14001c1b0`
- `0x14001c1e0`

## callees

- `0x1400014d4`
- `0x1400015ec`
- `0x140001a2c`
- `0x140004cf4`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x140010500`
- `0x140010528`
- `0x14001a520`
- `0x14001c660`
- `0x14001f1ac`
- `0x1400245dc`
- `0x140024e24`
- `0x140025450`
- `0x1400256b4`
- `0x14006b010`

## string_xrefs

- `0x14001f276`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001f531`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001f325`: `CreateInstance failed for CTSBufferResult!`
- `0x14001f288`: `No current thread, can't dispatch call`
- `0x14001f4e1`: `Sync wait completed ok for pAsyncCallback: 0x%p`
- `0x14001f543`: `WaitForCompletion timeout: 0x%x`
- `0x14001f5c0`: `Failed to add callback to thread!`

## pseudocode

```c
__int64 __fastcall CTSThread::internalDispatchSyncCall(
        _QWORD *a1,
        struct ITSAsyncCallback *a2,
        struct ITSAsyncResult *a3,
        unsigned __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  CTSSyncWaitResult *v7; // r14
  struct ITSAsyncResult *v8; // rbx
  __int64 v9; // rdi
  struct ITSAsyncCallback *v11; // r12
  CTSReaderWriterLock *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r12
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // r9
  int PooledObject; // esi
  __int64 v22; // rcx
  int ActivityIdPrefix; // eax
  __int64 v24; // rsi
  int v25; // eax
  int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  unsigned int v33[2]; // [rsp+30h] [rbp-59h]
  int v34; // [rsp+58h] [rbp-31h] BYREF
  CTSSyncWaitResult *v35; // [rsp+60h] [rbp-29h] BYREF
  __int64 v36; // [rsp+68h] [rbp-21h] BYREF
  __int64 v37; // [rsp+70h] [rbp-19h] BYREF
  const char *v38; // [rsp+78h] [rbp-11h] BYREF
  const char *v39; // [rsp+80h] [rbp-9h] BYREF
  const char *v40; // [rsp+88h] [rbp-1h] BYREF
  struct ITSAsyncCallback *v41; // [rsp+D8h] [rbp+4Fh] BYREF
  struct ITSAsyncCallback *v42; // [rsp+E0h] [rbp+57h]
  unsigned __int64 v43; // [rsp+F0h] [rbp+67h]

  v43 = a4;
  v42 = a2;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v35 = 0;
  v37 = 0;
  v11 = a2;
  v36 = 0;
  v13 = (CTSReaderWriterLock *)((char *)a1 + 148);
  CTSReaderWriterLock::ReadLock((CTSReaderWriterLock *)((char *)a1 + 148));
  v16 = a1[24];
  if ( v16 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v14, v15, 0);
    if ( v17 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v37);
      v37 = v17;
      v9 = v17;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v37);
    }
    v11 = v42;
  }
  CTSReaderWriterLock::ReadUnlock(v13);
  if ( !v20 )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v41) = 3057;
      v35 = (CTSSyncWaitResult *)"internalDispatchSyncCall";
      v34 = -2147467259;
      v38 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v39 = "No current thread, can't dispatch call";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)byte_14007E34B,
        v19,
        0,
        (__int64)&v39,
        (__int64)&v34,
        (__int64)&v38,
        (__int64)&v41,
        (__int64)&v35);
    }
    PooledObject = -2092630002;
    goto LABEL_46;
  }
  if ( a6 && a5 )
  {
    v22 = a1[84];
    v41 = 0;
    PooledObject = CTSBufferResult::CreateInstance(v22, a5, a6, &v41);
    if ( PooledObject < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"CreateInstance failed for CTSBufferResult!",
          PooledObject);
      }
      TCntPtr<CRdpClipMainWnd>::SafeRelease(&v41);
      goto LABEL_46;
    }
    v24 = ((unsigned __int64)v41 + 80) & -(__int64)(v41 != 0);
    if ( v24 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v36);
      v8 = (struct ITSAsyncResult *)v24;
      v36 = v24;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v36);
    }
    TCntPtr<CRdpClipMainWnd>::SafeRelease(&v41);
  }
  else if ( a3 )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v36);
    v8 = a3;
    v36 = (__int64)a3;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v36);
  }
  PooledObject = CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(a1[82], &v35);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        v25,
        (__int64)"Unable to get a SyncWaitResult from pool!",
        PooledObject);
    }
    v7 = v35;
    goto LABEL_46;
  }
  v7 = v35;
  PooledObject = CTSSyncWaitResult::InitializeForReuse(v35, v8);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v27 = 144;
    v28 = "InitializeForReuse failed!";
    goto LABEL_45;
  }
  PooledObject = CTSThread::AddCallback(
                   (CTSThread *)a1,
                   v11,
                   (struct ITSAsyncResult *)(((unsigned __int64)v7 + 80) & -(__int64)(v7 != 0)),
                   0,
                   v43,
                   1u,
                   0,
                   0);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v27 = 145;
    v28 = "Failed to add callback to thread!";
LABEL_45:
    v33[0] = PooledObject;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      v26,
      (__int64)v28,
      *(_QWORD *)v33);
    goto LABEL_46;
  }
  v29 = CTSSyncWaitResult::WaitForCompletion((__int64)v7, a7, v9);
  if ( v29 < 0 )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v41) = v29;
      v39 = "internalDispatchSyncCall";
      v34 = 3121;
      v38 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v40 = "WaitForCompletion timeout: 0x%x";
      LODWORD(v35) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v29,
        (unsigned int)byte_14007E2D1,
        v30,
        v31,
        (__int64)&v40,
        (__int64)&v35,
        (__int64)&v38,
        (__int64)&v34,
        (__int64)&v39,
        (__int64)&v41);
    }
    PooledObject = -2092630013;
  }
  else
  {
    if ( (unsigned int)dword_1400880C8 > 5 )
    {
      v41 = v11;
      v39 = "Sync wait completed ok for pAsyncCallback: 0x%p";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v29,
        (unsigned int)word_14007E31A,
        v30,
        v31,
        (__int64)&v39,
        (__int64)&v41);
    }
    PooledObject = *((_DWORD *)v7 + 24);
  }
LABEL_46:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v37);
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v36);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 4) + 16LL))(*((_QWORD *)v7 + 4));
  return (unsigned int)PooledObject;
}

```

## disassembly

```asm
0x14001f1ac  mov     rax, rsp
0x14001f1af  mov     [rax+18h], rbx
0x14001f1b3  mov     [rax+20h], r9
0x14001f1b7  mov     [rax+10h], rdx
0x14001f1bb  push    rbp
0x14001f1bc  push    rsi
0x14001f1bd  push    rdi
0x14001f1be  push    r12
0x14001f1c0  push    r13
0x14001f1c2  push    r14
0x14001f1c4  push    r15
0x14001f1c6  lea     rbp, [rax-47h]
0x14001f1ca  sub     rsp, 90h
0x14001f1d1  xor     r14d, r14d
0x14001f1d4  xor     ebx, ebx
0x14001f1d6  xor     edi, edi
0x14001f1d8  mov     [rbp+3Fh+var_68], r14
0x14001f1dc  mov     [rbp+3Fh+var_58], rdi
0x14001f1e0  mov     rsi, r8
0x14001f1e3  mov     r12, rdx
0x14001f1e6  mov     [rbp+3Fh+var_60], rbx
0x14001f1ea  mov     r15, rcx
0x14001f1ed  lea     r13, [rcx+94h]
0x14001f1f4  mov     rcx, r13; this
0x14001f1f7  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x14001f1fc  mov     rcx, [r15+0C0h]
0x14001f203  xor     r9d, r9d
0x14001f206  test    rcx, rcx
0x14001f209  jz      short loc_14001F242
0x14001f20b  mov     rax, [rcx]
0x14001f20e  mov     rax, [rax+40h]
0x14001f212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f217  xor     r9d, r9d
0x14001f21a  mov     r12, rax
0x14001f21d  test    rax, rax
0x14001f220  jz      short loc_14001F23E
0x14001f222  lea     rcx, [rbp+3Fh+var_58]
0x14001f226  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14001f22b  lea     rcx, [rbp+3Fh+var_58]
0x14001f22f  mov     [rbp+3Fh+var_58], r12
0x14001f233  mov     rdi, r12
0x14001f236  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14001f23b  mov     r9, r12
0x14001f23e  mov     r12, [rbp+3Fh+arg_8]
0x14001f242  mov     rcx, r13; this
0x14001f245  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x14001f24a  xor     r13d, r13d
0x14001f24d  test    r9, r9
0x14001f250  jnz     short loc_14001F2CF
0x14001f252  mov     eax, cs:dword_1400880C8
0x14001f258  cmp     eax, 2
0x14001f25b  jbe     short loc_14001F2C5
0x14001f25d  lea     rax, aInternaldispat; "internalDispatchSyncCall"
0x14001f264  mov     dword ptr [rbp+3Fh+arg_0], 0BF1h
0x14001f26b  mov     [rbp+3Fh+var_68], rax
0x14001f26f  lea     rdx, byte_14007E34B
0x14001f276  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001f27d  mov     [rbp+3Fh+var_70], 80004005h
0x14001f284  mov     [rbp+3Fh+var_50], rax
0x14001f288  lea     rax, aNoCurrentThrea; "No current thread, can't dispatch call"
0x14001f28f  mov     [rbp+3Fh+var_48], rax
0x14001f293  lea     rax, [rbp+3Fh+var_68]
0x14001f297  mov     [rsp+0C0h+var_80], rax
0x14001f29c  lea     rax, [rbp+3Fh+arg_0]
0x14001f2a0  mov     qword ptr [rsp+0C0h+var_88], rax
0x14001f2a5  lea     rax, [rbp+3Fh+var_50]
0x14001f2a9  mov     [rsp+0C0h+var_90], rax
0x14001f2ae  lea     rax, [rbp+3Fh+var_70]
0x14001f2b2  mov     qword ptr [rsp+0C0h+var_98], rax
0x14001f2b7  lea     rax, [rbp+3Fh+var_48]
0x14001f2bb  mov     [rsp+0C0h+var_A0], rax
0x14001f2c0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001f2c5  mov     esi, 8345000Eh
0x14001f2ca  jmp     loc_14001F5EA
0x14001f2cf  mov     r8, [rbp+3Fh+arg_28]
0x14001f2d3  test    r8, r8
0x14001f2d6  jz      loc_14001F399
0x14001f2dc  mov     edx, [rbp+3Fh+arg_20]
0x14001f2df  test    edx, edx
0x14001f2e1  jz      loc_14001F399
0x14001f2e7  mov     rcx, [r15+2A0h]
0x14001f2ee  lea     r9, [rbp+3Fh+arg_0]
0x14001f2f2  mov     [rbp+3Fh+arg_0], r13
0x14001f2f6  call    ?CreateInstance@CTSBufferResult@@SAJPEAV?$CTSObjectPool@VCTSBufferResult@@@@KPEAXPEAPEAV1@@Z; CTSBufferResult::CreateInstance(CTSObjectPool<CTSBufferResult> *,ulong,void *,CTSBufferResult * *)
0x14001f2fb  mov     esi, eax
0x14001f2fd  test    eax, eax
0x14001f2ff  jns     short loc_14001F362
0x14001f301  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f308  lea     rax, WPP_GLOBAL_Control
0x14001f30f  cmp     rcx, rax
0x14001f312  jz      short loc_14001F354
0x14001f314  test    byte ptr [rcx+1Ch], 8
0x14001f318  jz      short loc_14001F354
0x14001f31a  cmp     byte ptr [rcx+19h], 2
0x14001f31e  jb      short loc_14001F354
0x14001f320  call    RdpX_GetActivityIdPrefix
0x14001f325  lea     rcx, aCreateinstance; "CreateInstance failed for CTSBufferResu"...
0x14001f32c  mov     [rsp+0C0h+var_98], esi
0x14001f330  mov     [rsp+0C0h+var_A0], rcx
0x14001f335  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001f33c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f343  mov     edx, 8Eh
0x14001f348  mov     r9d, eax
0x14001f34b  mov     rcx, [rcx+10h]
0x14001f34f  call    WPP_SF_DsD
0x14001f354  lea     rcx, [rbp+3Fh+arg_0]
0x14001f358  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001f35d  jmp     loc_14001F5EA
0x14001f362  mov     rax, [rbp+3Fh+arg_0]
0x14001f366  lea     rcx, [rax+50h]
0x14001f36a  neg     rax
0x14001f36d  sbb     rsi, rsi
0x14001f370  and     rsi, rcx
0x14001f373  jz      short loc_14001F38E
0x14001f375  lea     rcx, [rbp+3Fh+var_60]
0x14001f379  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14001f37e  mov     rbx, rsi
0x14001f381  lea     rcx, [rbp+3Fh+var_60]
0x14001f385  mov     [rbp+3Fh+var_60], rbx
0x14001f389  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14001f38e  lea     rcx, [rbp+3Fh+arg_0]
0x14001f392  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001f397  jmp     short loc_14001F3B7
0x14001f399  test    rsi, rsi
0x14001f39c  jz      short loc_14001F3B7
0x14001f39e  lea     rcx, [rbp+3Fh+var_60]
0x14001f3a2  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14001f3a7  mov     rbx, rsi
0x14001f3aa  lea     rcx, [rbp+3Fh+var_60]
0x14001f3ae  mov     [rbp+3Fh+var_60], rbx
0x14001f3b2  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14001f3b7  mov     rcx, [r15+290h]
0x14001f3be  lea     rdx, [rbp+3Fh+var_68]
0x14001f3c2  call    ?GetPooledObject@?$CTSObjectPool@VCTSSyncWaitResult@@@@QEAAJPEAPEAVCTSSyncWaitResult@@H@Z; CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(CTSSyncWaitResult * *,int)
0x14001f3c7  mov     esi, eax
0x14001f3c9  test    eax, eax
0x14001f3cb  jns     short loc_14001F429
0x14001f3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3d4  lea     rax, WPP_GLOBAL_Control
0x14001f3db  cmp     rcx, rax
0x14001f3de  jz      short loc_14001F420
0x14001f3e0  test    byte ptr [rcx+1Ch], 8
0x14001f3e4  jz      short loc_14001F420
0x14001f3e6  cmp     byte ptr [rcx+19h], 2
0x14001f3ea  jb      short loc_14001F420
0x14001f3ec  call    RdpX_GetActivityIdPrefix
0x14001f3f1  lea     rcx, aUnableToGetASy; "Unable to get a SyncWaitResult from poo"...
0x14001f3f8  mov     [rsp+0C0h+var_98], esi
0x14001f3fc  mov     [rsp+0C0h+var_A0], rcx
0x14001f401  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001f408  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f40f  mov     edx, 8Fh
0x14001f414  mov     r9d, eax
0x14001f417  mov     rcx, [rcx+10h]
0x14001f41b  call    WPP_SF_DsD
0x14001f420  mov     r14, [rbp+3Fh+var_68]
0x14001f424  jmp     loc_14001F5EA
0x14001f429  mov     r14, [rbp+3Fh+var_68]
0x14001f42d  mov     rdx, rbx; struct ITSAsyncResult *
0x14001f430  mov     rcx, r14; this
0x14001f433  call    ?InitializeForReuse@CTSSyncWaitResult@@QEAAJPEAVITSAsyncResult@@@Z; CTSSyncWaitResult::InitializeForReuse(ITSAsyncResult *)
0x14001f438  mov     esi, eax
0x14001f43a  test    eax, eax
0x14001f43c  jns     short loc_14001F47F
0x14001f43e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f445  lea     rax, WPP_GLOBAL_Control
0x14001f44c  cmp     rcx, rax
0x14001f44f  jz      loc_14001F5EA
0x14001f455  test    byte ptr [rcx+1Ch], 8
0x14001f459  jz      loc_14001F5EA
0x14001f45f  cmp     byte ptr [rcx+19h], 2
0x14001f463  jb      loc_14001F5EA
0x14001f469  call    RdpX_GetActivityIdPrefix
0x14001f46e  mov     edx, 90h
0x14001f473  lea     rcx, aInitializeforr; "InitializeForReuse failed!"
0x14001f47a  jmp     loc_14001F5C7
0x14001f47f  mov     [rsp+0C0h+var_88], r13d; unsigned int
0x14001f484  lea     rcx, [r14+50h]
0x14001f488  mov     [rsp+0C0h+var_90], r13; struct ITSQueuedCallback **
0x14001f48d  mov     rax, r14
0x14001f490  neg     rax
0x14001f493  mov     [rsp+0C0h+var_98], 1; unsigned int
0x14001f49b  mov     rax, [rbp+3Fh+arg_18]
0x14001f49f  mov     rdx, r12; struct ITSAsyncCallback *
0x14001f4a2  sbb     r8, r8
0x14001f4a5  mov     [rsp+0C0h+var_A0], rax; unsigned __int64
0x14001f4aa  and     r8, rcx; struct ITSAsyncResult *
0x14001f4ad  xor     r9d, r9d; unsigned int
0x14001f4b0  mov     rcx, r15; this
0x14001f4b3  call    ?AddCallback@CTSThread@@UEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@K_KKPEAPEAVITSQueuedCallback@@I@Z; CTSThread::AddCallback(ITSAsyncCallback *,ITSAsyncResult *,ulong,unsigned __int64,ulong,ITSQueuedCallback * *,uint)
0x14001f4b8  mov     esi, eax
0x14001f4ba  test    eax, eax
0x14001f4bc  js      loc_14001F597
0x14001f4c2  mov     edx, [rbp+3Fh+arg_30]
0x14001f4c5  mov     r8, rdi
0x14001f4c8  mov     rcx, r14
0x14001f4cb  call    ?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z; CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)
0x14001f4d0  mov     ecx, eax
0x14001f4d2  test    eax, eax
0x14001f4d4  mov     eax, cs:dword_1400880C8
0x14001f4da  js      short loc_14001F517
0x14001f4dc  cmp     eax, 5
0x14001f4df  jbe     short loc_14001F50E
0x14001f4e1  lea     rax, aSyncWaitComple_0; "Sync wait completed ok for pAsyncCallba"...
0x14001f4e8  mov     [rbp+3Fh+arg_0], r12
0x14001f4ec  mov     [rbp+3Fh+var_48], rax
0x14001f4f0  lea     rdx, word_14007E31A
0x14001f4f7  lea     rax, [rbp+3Fh+arg_0]
0x14001f4fb  mov     qword ptr [rsp+0C0h+var_98], rax
0x14001f500  lea     rax, [rbp+3Fh+var_48]
0x14001f504  mov     [rsp+0C0h+var_A0], rax
0x14001f509  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x14001f50e  mov     esi, [r14+60h]
0x14001f512  jmp     loc_14001F5EA
0x14001f517  cmp     eax, 2
0x14001f51a  jbe     short loc_14001F590
0x14001f51c  lea     rax, aInternaldispat; "internalDispatchSyncCall"
0x14001f523  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x14001f526  mov     [rbp+3Fh+var_48], rax
0x14001f52a  lea     rdx, byte_14007E2D1
0x14001f531  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001f538  mov     [rbp+3Fh+var_70], 0C31h
0x14001f53f  mov     [rbp+3Fh+var_50], rax
0x14001f543  lea     rax, aWaitforcomplet; "WaitForCompletion timeout: 0x%x"
0x14001f54a  mov     [rbp+3Fh+var_40], rax
0x14001f54e  lea     rax, [rbp+3Fh+arg_0]
0x14001f552  mov     [rsp+48h], rax
0x14001f557  lea     rax, [rbp+3Fh+var_48]
0x14001f55b  mov     [rsp+0C0h+var_80], rax
0x14001f560  lea     rax, [rbp+3Fh+var_70]
0x14001f564  mov     qword ptr [rsp+0C0h+var_88], rax
0x14001f569  lea     rax, [rbp+3Fh+var_50]
0x14001f56d  mov     [rsp+0C0h+var_90], rax
0x14001f572  lea     rax, [rbp+3Fh+var_68]
0x14001f576  mov     qword ptr [rsp+0C0h+var_98], rax
0x14001f57b  lea     rax, [rbp+3Fh+var_40]
0x14001f57f  mov     [rsp+0C0h+var_A0], rax
0x14001f584  mov     dword ptr [rbp+3Fh+var_68], 80004005h
0x14001f58b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001f590  mov     esi, 83450003h
0x14001f595  jmp     short loc_14001F5EA
0x14001f597  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f59e  lea     rax, WPP_GLOBAL_Control
0x14001f5a5  cmp     rcx, rax
0x14001f5a8  jz      short loc_14001F5EA
0x14001f5aa  test    byte ptr [rcx+1Ch], 8
0x14001f5ae  jz      short loc_14001F5EA
0x14001f5b0  cmp     byte ptr [rcx+19h], 2
0x14001f5b4  jb      short loc_14001F5EA
0x14001f5b6  call    RdpX_GetActivityIdPrefix
0x14001f5bb  mov     edx, 91h
0x14001f5c0  lea     rcx, aFailedToAddCal; "Failed to add callback to thread!"
0x14001f5c7  mov     [rsp+0C0h+var_98], esi
0x14001f5cb  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001f5d2  mov     [rsp+0C0h+var_A0], rcx
0x14001f5d7  mov     r9d, eax
0x14001f5da  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5e1  mov     rcx, [rcx+10h]
0x14001f5e5  call    WPP_SF_DsD
0x14001f5ea  lea     rcx, [rbp+3Fh+var_58]
0x14001f5ee  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14001f5f3  lea     rcx, [rbp+3Fh+var_60]
0x14001f5f7  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14001f5fc  test    r14, r14
0x14001f5ff  jz      short loc_14001F611
0x14001f601  mov     rcx, [r14+20h]
0x14001f605  mov     rax, [rcx]
0x14001f608  mov     rax, [rax+10h]
0x14001f60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f611  mov     rbx, [rsp+0C0h+arg_10]
0x14001f619  mov     eax, esi
0x14001f61b  add     rsp, 90h
0x14001f622  pop     r15
0x14001f624  pop     r14
0x14001f626  pop     r13
0x14001f628  pop     r12
0x14001f62a  pop     rdi
0x14001f62b  pop     rsi
0x14001f62c  pop     rbp
0x14001f62d  retn
```
