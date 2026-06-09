# CTSThread::internalDispatchSyncCall(ITSAsyncCallback *,ITSAsyncResult *,unsigned __int64,ulong,void *,TSWaitType)

- ea: `0x180027e10`
- end: `0x180028292`
- name: `?internalDispatchSyncCall@CTSThread@@IEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@_KKPEAXW4TSWaitType@@@Z`
- size: `1154`
- prototype: `__int64 __fastcall(_QWORD *, struct ITSAsyncCallback *, struct ITSAsyncResult *, unsigned __int64, unsigned int, void *, unsigned int)`
- caller_count: `3`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024b20`
- `0x180024b50`
- `0x180024b80`

## callees

- `0x18000160c`
- `0x180001bfc`
- `0x180001f98`
- `0x180005f9c`
- `0x18000f068`
- `0x18000f08c`
- `0x18001d114`
- `0x180022f00`
- `0x180024fd0`
- `0x180026234`
- `0x180026254`
- `0x180027e10`
- `0x180029688`
- `0x180029c10`
- `0x180029f60`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x180027eda`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180028195`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180027f89`: `CreateInstance failed for CTSBufferResult!`
- `0x180027eec`: `No current thread, can't dispatch call`
- `0x180028145`: `Sync wait completed ok for pAsyncCallback: 0x%p`
- `0x1800281a7`: `WaitForCompletion timeout: 0x%x`
- `0x180028224`: `Failed to add callback to thread!`

## pseudocode

```c
__int64 __fastcall CTSThread::internalDispatchSyncCall(
        _QWORD *a1,
        struct ITSAsyncCallback *a2,
        struct ITSAsyncResult *a3,
        unsigned __int64 a4,
        unsigned int a5,
        void *a6,
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
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int PooledObject; // esi
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int ActivityIdPrefix; // eax
  unsigned __int64 v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // eax
  int v36; // edx
  const char *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  int v41; // eax
  __int64 v42; // r8
  __int64 v43; // r9
  unsigned int v45[2]; // [rsp+30h] [rbp-59h]
  int v46; // [rsp+58h] [rbp-31h] BYREF
  CTSSyncWaitResult *v47; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int64 v48; // [rsp+68h] [rbp-21h] BYREF
  __int64 v49; // [rsp+70h] [rbp-19h] BYREF
  const char *v50; // [rsp+78h] [rbp-11h] BYREF
  const char *v51; // [rsp+80h] [rbp-9h] BYREF
  const char *v52; // [rsp+88h] [rbp-1h] BYREF
  struct CTSBufferResult *v53; // [rsp+D8h] [rbp+4Fh] BYREF
  struct ITSAsyncCallback *v54; // [rsp+E0h] [rbp+57h]
  unsigned __int64 v55; // [rsp+F0h] [rbp+67h]

  v55 = a4;
  v54 = a2;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v47 = 0;
  v49 = 0;
  v11 = a2;
  v48 = 0;
  v13 = (CTSReaderWriterLock *)((char *)a1 + 148);
  CTSReaderWriterLock::ReadLock((CTSReaderWriterLock *)((char *)a1 + 148));
  v16 = a1[24];
  if ( v16 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, v14, v15, 0);
    if ( v17 )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v49);
      v49 = v17;
      v9 = v17;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v49);
    }
    v11 = v54;
  }
  CTSReaderWriterLock::ReadUnlock(v13);
  if ( !v20 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v53) = 3057;
      v47 = (CTSSyncWaitResult *)"internalDispatchSyncCall";
      v46 = -2147467259;
      v50 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v51 = "No current thread, can't dispatch call";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (__int64)&word_18003F45E,
        v19,
        0,
        (const unsigned __int16 **)&v51,
        (__int64)&v46,
        (const unsigned __int16 **)&v50,
        (__int64)&v53,
        (const unsigned __int16 **)&v47);
    }
    PooledObject = -2092630002;
    goto LABEL_46;
  }
  if ( a6 && a5 )
  {
    v22 = a1[84];
    v53 = 0;
    PooledObject = CTSBufferResult::CreateInstance(v22, a5, a6, &v53);
    if ( PooledObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v23, v24, v25);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"CreateInstance failed for CTSBufferResult!",
          PooledObject);
      }
      TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v53);
      goto LABEL_46;
    }
    v27 = ((unsigned __int64)v53 + 80) & -(__int64)(v53 != 0);
    if ( v27 )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v48);
      v8 = (struct ITSAsyncResult *)v27;
      v48 = v27;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v48);
    }
    TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v53);
  }
  else if ( a3 )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v48);
    v8 = a3;
    v48 = (unsigned __int64)a3;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v48);
  }
  PooledObject = CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(a1[82], &v47);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v28, v29, v30);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        v31,
        (__int64)"Unable to get a SyncWaitResult from pool!",
        PooledObject);
    }
    v7 = v47;
    goto LABEL_46;
  }
  v7 = v47;
  PooledObject = CTSSyncWaitResult::InitializeForReuse(v47, v8);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v35 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v32, v33, v34);
    v36 = 144;
    v37 = "InitializeForReuse failed!";
    goto LABEL_45;
  }
  PooledObject = CTSThread::AddCallback(
                   (CTSThread *)a1,
                   v11,
                   (struct ITSAsyncResult *)(((unsigned __int64)v7 + 80) & -(__int64)(v7 != 0)),
                   0,
                   v55,
                   1,
                   0,
                   0);
  if ( PooledObject < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v35 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v38, v39, v40);
    v36 = 145;
    v37 = "Failed to add callback to thread!";
LABEL_45:
    v45[0] = PooledObject;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v36,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      v35,
      (__int64)v37,
      *(_QWORD *)v45);
    goto LABEL_46;
  }
  v41 = CTSSyncWaitResult::WaitForCompletion(v7, a7, v9);
  if ( v41 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v53) = v41;
      v51 = "internalDispatchSyncCall";
      v46 = 3121;
      v50 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v52 = "WaitForCompletion timeout: 0x%x";
      LODWORD(v47) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)v41,
        (__int64)&dword_18003F3E4,
        v42,
        v43,
        (const unsigned __int16 **)&v52,
        (__int64)&v47,
        (const unsigned __int16 **)&v50,
        (__int64)&v46,
        (const unsigned __int16 **)&v51,
        (__int64)&v53);
    }
    PooledObject = -2092630013;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v53 = v11;
      v51 = "Sync wait completed ok for pAsyncCallback: 0x%p";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)v41,
        (__int64)byte_18003F42D,
        v42,
        v43,
        (const unsigned __int16 **)&v51,
        (__int64)&v53);
    }
    PooledObject = *((_DWORD *)v7 + 24);
  }
LABEL_46:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v49);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v48);
  if ( v7 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 4) + 16LL))(*((_QWORD *)v7 + 4));
  return (unsigned int)PooledObject;
}

```

## disassembly

```asm
0x180027e10  mov     rax, rsp
0x180027e13  mov     [rax+18h], rbx
0x180027e17  mov     [rax+20h], r9
0x180027e1b  mov     [rax+10h], rdx
0x180027e1f  push    rbp
0x180027e20  push    rsi
0x180027e21  push    rdi
0x180027e22  push    r12
0x180027e24  push    r13
0x180027e26  push    r14
0x180027e28  push    r15
0x180027e2a  lea     rbp, [rax-47h]
0x180027e2e  sub     rsp, 90h
0x180027e35  xor     r14d, r14d
0x180027e38  xor     ebx, ebx
0x180027e3a  xor     edi, edi
0x180027e3c  mov     [rbp+3Fh+var_68], r14
0x180027e40  mov     [rbp+3Fh+var_58], rdi
0x180027e44  mov     rsi, r8
0x180027e47  mov     r12, rdx
0x180027e4a  mov     [rbp+3Fh+var_60], rbx
0x180027e4e  mov     r15, rcx
0x180027e51  lea     r13, [rcx+94h]
0x180027e58  mov     rcx, r13; this
0x180027e5b  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x180027e60  mov     rcx, [r15+0C0h]
0x180027e67  xor     r9d, r9d
0x180027e6a  test    rcx, rcx
0x180027e6d  jz      short loc_180027EA6
0x180027e6f  mov     rax, [rcx]
0x180027e72  mov     rax, [rax+40h]
0x180027e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e7b  xor     r9d, r9d
0x180027e7e  mov     r12, rax
0x180027e81  test    rax, rax
0x180027e84  jz      short loc_180027EA2
0x180027e86  lea     rcx, [rbp+3Fh+var_58]
0x180027e8a  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180027e8f  lea     rcx, [rbp+3Fh+var_58]
0x180027e93  mov     [rbp+3Fh+var_58], r12
0x180027e97  mov     rdi, r12
0x180027e9a  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180027e9f  mov     r9, r12
0x180027ea2  mov     r12, [rbp+3Fh+arg_8]
0x180027ea6  mov     rcx, r13; this
0x180027ea9  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x180027eae  xor     r13d, r13d
0x180027eb1  test    r9, r9
0x180027eb4  jnz     short loc_180027F33
0x180027eb6  mov     eax, cs:dword_180044008
0x180027ebc  cmp     eax, 2
0x180027ebf  jbe     short loc_180027F29
0x180027ec1  lea     rax, aInternaldispat; "internalDispatchSyncCall"
0x180027ec8  mov     dword ptr [rbp+3Fh+arg_0], 0BF1h
0x180027ecf  mov     [rbp+3Fh+var_68], rax
0x180027ed3  lea     rdx, word_18003F45E
0x180027eda  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180027ee1  mov     [rbp+3Fh+var_70], 80004005h
0x180027ee8  mov     [rbp+3Fh+var_50], rax
0x180027eec  lea     rax, aNoCurrentThrea; "No current thread, can't dispatch call"
0x180027ef3  mov     [rbp+3Fh+var_48], rax
0x180027ef7  lea     rax, [rbp+3Fh+var_68]
0x180027efb  mov     [rsp+0C0h+var_80], rax
0x180027f00  lea     rax, [rbp+3Fh+arg_0]
0x180027f04  mov     qword ptr [rsp+0C0h+var_88], rax
0x180027f09  lea     rax, [rbp+3Fh+var_50]
0x180027f0d  mov     [rsp+0C0h+var_90], rax
0x180027f12  lea     rax, [rbp+3Fh+var_70]
0x180027f16  mov     qword ptr [rsp+0C0h+var_98], rax
0x180027f1b  lea     rax, [rbp+3Fh+var_48]
0x180027f1f  mov     [rsp+0C0h+var_A0], rax
0x180027f24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180027f29  mov     esi, 8345000Eh
0x180027f2e  jmp     loc_18002824E
0x180027f33  mov     r8, [rbp+3Fh+arg_28]
0x180027f37  test    r8, r8
0x180027f3a  jz      loc_180027FFD
0x180027f40  mov     edx, [rbp+3Fh+arg_20]
0x180027f43  test    edx, edx
0x180027f45  jz      loc_180027FFD
0x180027f4b  mov     rcx, [r15+2A0h]
0x180027f52  lea     r9, [rbp+3Fh+arg_0]
0x180027f56  mov     [rbp+3Fh+arg_0], r13
0x180027f5a  call    ?CreateInstance@CTSBufferResult@@SAJPEAV?$CTSObjectPool@VCTSBufferResult@@@@KPEAXPEAPEAV1@@Z; CTSBufferResult::CreateInstance(CTSObjectPool<CTSBufferResult> *,ulong,void *,CTSBufferResult * *)
0x180027f5f  mov     esi, eax
0x180027f61  test    eax, eax
0x180027f63  jns     short loc_180027FC6
0x180027f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f6c  lea     rax, WPP_GLOBAL_Control
0x180027f73  cmp     rcx, rax
0x180027f76  jz      short loc_180027FB8
0x180027f78  test    byte ptr [rcx+1Ch], 8
0x180027f7c  jz      short loc_180027FB8
0x180027f7e  cmp     byte ptr [rcx+19h], 2
0x180027f82  jb      short loc_180027FB8
0x180027f84  call    RdpX_GetActivityIdPrefix
0x180027f89  lea     rcx, aCreateinstance; "CreateInstance failed for CTSBufferResu"...
0x180027f90  mov     [rsp+0C0h+var_98], esi
0x180027f94  mov     [rsp+0C0h+var_A0], rcx
0x180027f99  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180027fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fa7  mov     edx, 8Eh
0x180027fac  mov     r9d, eax
0x180027faf  mov     rcx, [rcx+10h]
0x180027fb3  call    WPP_SF_DsD
0x180027fb8  lea     rcx, [rbp+3Fh+arg_0]
0x180027fbc  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180027fc1  jmp     loc_18002824E
0x180027fc6  mov     rax, [rbp+3Fh+arg_0]
0x180027fca  lea     rcx, [rax+50h]
0x180027fce  neg     rax
0x180027fd1  sbb     rsi, rsi
0x180027fd4  and     rsi, rcx
0x180027fd7  jz      short loc_180027FF2
0x180027fd9  lea     rcx, [rbp+3Fh+var_60]
0x180027fdd  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180027fe2  mov     rbx, rsi
0x180027fe5  lea     rcx, [rbp+3Fh+var_60]
0x180027fe9  mov     [rbp+3Fh+var_60], rbx
0x180027fed  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180027ff2  lea     rcx, [rbp+3Fh+arg_0]
0x180027ff6  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180027ffb  jmp     short loc_18002801B
0x180027ffd  test    rsi, rsi
0x180028000  jz      short loc_18002801B
0x180028002  lea     rcx, [rbp+3Fh+var_60]
0x180028006  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18002800b  mov     rbx, rsi
0x18002800e  lea     rcx, [rbp+3Fh+var_60]
0x180028012  mov     [rbp+3Fh+var_60], rbx
0x180028016  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002801b  mov     rcx, [r15+290h]
0x180028022  lea     rdx, [rbp+3Fh+var_68]
0x180028026  call    ?GetPooledObject@?$CTSObjectPool@VCTSSyncWaitResult@@@@QEAAJPEAPEAVCTSSyncWaitResult@@H@Z; CTSObjectPool<CTSSyncWaitResult>::GetPooledObject(CTSSyncWaitResult * *,int)
0x18002802b  mov     esi, eax
0x18002802d  test    eax, eax
0x18002802f  jns     short loc_18002808D
0x180028031  mov     rcx, cs:WPP_GLOBAL_Control
0x180028038  lea     rax, WPP_GLOBAL_Control
0x18002803f  cmp     rcx, rax
0x180028042  jz      short loc_180028084
0x180028044  test    byte ptr [rcx+1Ch], 8
0x180028048  jz      short loc_180028084
0x18002804a  cmp     byte ptr [rcx+19h], 2
0x18002804e  jb      short loc_180028084
0x180028050  call    RdpX_GetActivityIdPrefix
0x180028055  lea     rcx, aUnableToGetASy; "Unable to get a SyncWaitResult from poo"...
0x18002805c  mov     [rsp+0C0h+var_98], esi
0x180028060  mov     [rsp+0C0h+var_A0], rcx
0x180028065  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x18002806c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028073  mov     edx, 8Fh
0x180028078  mov     r9d, eax
0x18002807b  mov     rcx, [rcx+10h]
0x18002807f  call    WPP_SF_DsD
0x180028084  mov     r14, [rbp+3Fh+var_68]
0x180028088  jmp     loc_18002824E
0x18002808d  mov     r14, [rbp+3Fh+var_68]
0x180028091  mov     rdx, rbx; struct ITSAsyncResult *
0x180028094  mov     rcx, r14; this
0x180028097  call    ?InitializeForReuse@CTSSyncWaitResult@@QEAAJPEAVITSAsyncResult@@@Z; CTSSyncWaitResult::InitializeForReuse(ITSAsyncResult *)
0x18002809c  mov     esi, eax
0x18002809e  test    eax, eax
0x1800280a0  jns     short loc_1800280E3
0x1800280a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280a9  lea     rax, WPP_GLOBAL_Control
0x1800280b0  cmp     rcx, rax
0x1800280b3  jz      loc_18002824E
0x1800280b9  test    byte ptr [rcx+1Ch], 8
0x1800280bd  jz      loc_18002824E
0x1800280c3  cmp     byte ptr [rcx+19h], 2
0x1800280c7  jb      loc_18002824E
0x1800280cd  call    RdpX_GetActivityIdPrefix
0x1800280d2  mov     edx, 90h
0x1800280d7  lea     rcx, aInitializeforr; "InitializeForReuse failed!"
0x1800280de  jmp     loc_18002822B
0x1800280e3  mov     [rsp+0C0h+var_88], r13d; unsigned int
0x1800280e8  lea     rcx, [r14+50h]
0x1800280ec  mov     [rsp+0C0h+var_90], r13; struct ITSQueuedCallback **
0x1800280f1  mov     rax, r14
0x1800280f4  neg     rax
0x1800280f7  mov     [rsp+0C0h+var_98], 1; unsigned int
0x1800280ff  mov     rax, [rbp+3Fh+arg_18]
0x180028103  mov     rdx, r12; struct ITSAsyncCallback *
0x180028106  sbb     r8, r8
0x180028109  mov     [rsp+0C0h+var_A0], rax; unsigned __int64
0x18002810e  and     r8, rcx; struct ITSAsyncResult *
0x180028111  xor     r9d, r9d; unsigned int
0x180028114  mov     rcx, r15; this
0x180028117  call    ?AddCallback@CTSThread@@UEAAJPEAVITSAsyncCallback@@PEAVITSAsyncResult@@K_KKPEAPEAVITSQueuedCallback@@I@Z; CTSThread::AddCallback(ITSAsyncCallback *,ITSAsyncResult *,ulong,unsigned __int64,ulong,ITSQueuedCallback * *,uint)
0x18002811c  mov     esi, eax
0x18002811e  test    eax, eax
0x180028120  js      loc_1800281FB
0x180028126  mov     edx, [rbp+3Fh+arg_30]
0x180028129  mov     r8, rdi
0x18002812c  mov     rcx, r14
0x18002812f  call    ?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z; CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)
0x180028134  mov     ecx, eax
0x180028136  test    eax, eax
0x180028138  mov     eax, cs:dword_180044008
0x18002813e  js      short loc_18002817B
0x180028140  cmp     eax, 5
0x180028143  jbe     short loc_180028172
0x180028145  lea     rax, aSyncWaitComple; "Sync wait completed ok for pAsyncCallba"...
0x18002814c  mov     [rbp+3Fh+arg_0], r12
0x180028150  mov     [rbp+3Fh+var_48], rax
0x180028154  lea     rdx, byte_18003F42D
0x18002815b  lea     rax, [rbp+3Fh+arg_0]
0x18002815f  mov     qword ptr [rsp+0C0h+var_98], rax
0x180028164  lea     rax, [rbp+3Fh+var_48]
0x180028168  mov     [rsp+0C0h+var_A0], rax
0x18002816d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180028172  mov     esi, [r14+60h]
0x180028176  jmp     loc_18002824E
0x18002817b  cmp     eax, 2
0x18002817e  jbe     short loc_1800281F4
0x180028180  lea     rax, aInternaldispat; "internalDispatchSyncCall"
0x180028187  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x18002818a  mov     [rbp+3Fh+var_48], rax
0x18002818e  lea     rdx, dword_18003F3E4
0x180028195  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002819c  mov     [rbp+3Fh+var_70], 0C31h
0x1800281a3  mov     [rbp+3Fh+var_50], rax
0x1800281a7  lea     rax, aWaitforcomplet; "WaitForCompletion timeout: 0x%x"
0x1800281ae  mov     [rbp+3Fh+var_40], rax
0x1800281b2  lea     rax, [rbp+3Fh+arg_0]
0x1800281b6  mov     [rsp+48h], rax
0x1800281bb  lea     rax, [rbp+3Fh+var_48]
0x1800281bf  mov     [rsp+0C0h+var_80], rax
0x1800281c4  lea     rax, [rbp+3Fh+var_70]
0x1800281c8  mov     qword ptr [rsp+0C0h+var_88], rax
0x1800281cd  lea     rax, [rbp+3Fh+var_50]
0x1800281d1  mov     [rsp+0C0h+var_90], rax
0x1800281d6  lea     rax, [rbp+3Fh+var_68]
0x1800281da  mov     qword ptr [rsp+0C0h+var_98], rax
0x1800281df  lea     rax, [rbp+3Fh+var_40]
0x1800281e3  mov     [rsp+0C0h+var_A0], rax
0x1800281e8  mov     dword ptr [rbp+3Fh+var_68], 80004005h
0x1800281ef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800281f4  mov     esi, 83450003h
0x1800281f9  jmp     short loc_18002824E
0x1800281fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028202  lea     rax, WPP_GLOBAL_Control
0x180028209  cmp     rcx, rax
0x18002820c  jz      short loc_18002824E
0x18002820e  test    byte ptr [rcx+1Ch], 8
0x180028212  jz      short loc_18002824E
0x180028214  cmp     byte ptr [rcx+19h], 2
0x180028218  jb      short loc_18002824E
0x18002821a  call    RdpX_GetActivityIdPrefix
0x18002821f  mov     edx, 91h
0x180028224  lea     rcx, aFailedToAddCal; "Failed to add callback to thread!"
0x18002822b  mov     [rsp+0C0h+var_98], esi
0x18002822f  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180028236  mov     [rsp+0C0h+var_A0], rcx
0x18002823b  mov     r9d, eax
0x18002823e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028245  mov     rcx, [rcx+10h]
0x180028249  call    WPP_SF_DsD
0x18002824e  lea     rcx, [rbp+3Fh+var_58]
0x180028252  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180028257  lea     rcx, [rbp+3Fh+var_60]
0x18002825b  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180028260  test    r14, r14
0x180028263  jz      short loc_180028275
0x180028265  mov     rcx, [r14+20h]
0x180028269  mov     rax, [rcx]
0x18002826c  mov     rax, [rax+10h]
0x180028270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028275  mov     rbx, [rsp+0C0h+arg_10]
0x18002827d  mov     eax, esi
0x18002827f  add     rsp, 90h
0x180028286  pop     r15
0x180028288  pop     r14
0x18002828a  pop     r13
0x18002828c  pop     r12
0x18002828e  pop     rdi
0x18002828f  pop     rsi
0x180028290  pop     rbp
0x180028291  retn
```
