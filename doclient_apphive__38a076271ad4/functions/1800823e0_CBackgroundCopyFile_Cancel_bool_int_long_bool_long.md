# CBackgroundCopyFile::Cancel(bool,int,long,bool,long)

- ea: `0x1800823e0`
- end: `0x1800828df`
- name: `?Cancel@CBackgroundCopyFile@@QEAAJ_NHJ0J@Z`
- size: `1279`
- prototype: `__int64 __usercall@<rax>(CBackgroundCopyFile *__hidden this@<rcx>, bool@<dl>, int@<r8d>, int@<r9d>, bool, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180092518`

## callees

- `0x180009ab4`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x180027288`
- `0x180036e68`
- `0x180036ea8`
- `0x18007ca54`
- `0x1800813e0`
- `0x1800823e0`
- `0x180084fec`
- `0x18008507c`
- `0x1800869e0`
- `0x180086aec`
- `0x180086bf8`
- `0x180086d30`
- `0x1800943c4`
- `0x180096c4c`
- `0x1800970d4`
- `0x1800a1f08`
- `0x1800a5c88`
- `0x1800a9090`
- `0x1800b7c60`
- `0x1800f82f0`
- `0x1800f8314`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800825ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800825ba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800825a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800825a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008261a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008261a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082870`

## string_xrefs

- `0x180082582`: `CBackgroundCopyFile::Cancel`
- `0x18008256d`: `Deleted destination (or temporary) file: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CBackgroundCopyFile::Cancel(
        volatile signed __int32 **this,
        char a2,
        int a3,
        int a4,
        bool a5,
        __int64 a6)
{
  char v6; // r12
  CBackgroundCopyFile *v7; // rbx
  CBackgroundCopyFile *v8; // r15
  volatile signed __int32 *v9; // rsi
  char *v10; // rsi
  int v11; // eax
  char v12; // r13
  int v13; // eax
  __int64 v14; // r14
  const char *v15; // rcx
  int v16; // eax
  const char *v17; // r9
  HANDLE v18; // r14
  wil::details::in1diag3 *v19; // rcx
  int v20; // eax
  bool v21; // r14
  bool v22; // zf
  char v23; // al
  int v24; // edx
  void *v25; // r14
  __int64 v26; // rcx
  void *v27; // rax
  char IsEnabled; // al
  int v29; // edx
  __int64 v30; // rcx
  struct CGlobalObjects *v31; // rax
  const char *v32; // r9
  __int64 result; // rax
  HANDLE Token; // [rsp+40h] [rbp-D8h] BYREF
  void *Block; // [rsp+48h] [rbp-D0h] BYREF
  int v36[2]; // [rsp+50h] [rbp-C8h] BYREF
  int v37[2]; // [rsp+58h] [rbp-C0h] BYREF
  __int128 v38; // [rsp+60h] [rbp-B8h]
  CBackgroundCopyFile *v39; // [rsp+70h] [rbp-A8h]
  __int64 v40; // [rsp+78h] [rbp-A0h]
  _BYTE v41[72]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v42; // [rsp+C8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  __int64 v45; // [rsp+130h] [rbp+18h] BYREF
  __int64 v46; // [rsp+138h] [rbp+20h] BYREF

  LODWORD(v46) = a4;
  LODWORD(v45) = a3;
  v6 = a2;
  v7 = (CBackgroundCopyFile *)this;
  Block = this;
  v8 = (CBackgroundCopyFile *)this;
  this[48] = 0;
  v9 = this[49];
  this[49] = 0;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  *((_BYTE *)v7 + 492) = 0;
  v40 = 1;
  v39 = v7;
  v10 = (char *)v7 + 264;
  v38 = (unsigned __int64)v7 + 264;
  v11 = mtx_do_lock((char *)v7 + 264);
  try
  {
    if ( v11 )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v7 + 85) == 0x7FFFFFFF )
    {
      *((_DWORD *)v7 + 85) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v12 = 1;
    BYTE8(v38) = 1;
    v13 = *((_DWORD *)v7 + 122);
    if ( (v13 & 4) != 0 )
      goto LABEL_44;
    *((_BYTE *)v7 + 495) &= ~1u;
    *((_DWORD *)v7 + 122) = v13 & 0xFFFFFFBF;
    CBackgroundCopyFile::_EndProgressMonitoring(v7);
    CBackgroundCopyFile::_ShutdownDownloadSink(v7);
    CStopwatchMT::Stop((CBackgroundCopyFile *)((char *)v7 + 232));
    if ( a5 )
    {
      v14 = (__int64)v7 + (*((_QWORD *)v7 + 12) != 0 ? 0x20 : 0) + 48;
      if ( *(_QWORD *)(v14 + 16) )
      {
        try
        {
          Token = 0;
          CJobSharedData::ImpersonateOwner(*((CJobSharedData **)v7 + 4), (int)&Token);
          v15 = (const char *)v14;
          if ( *(_QWORD *)(v14 + 24) > 0xFu )
            v15 = *(const char **)v14;
          v16 = CFile::Delete(v15);
          if ( *(_QWORD *)(v14 + 24) > 0xFu )
            v14 = *(_QWORD *)v14;
          LogResult(
            5u,
            "CBackgroundCopyFile::Cancel",
            0x378u,
            v16,
            "Deleted destination (or temporary) file: %s",
            (const char *)v14);
          v18 = Token;
          if ( Token != (HANDLE)-1LL )
          {
            if ( !SetThreadToken(0, Token) )
              wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
            if ( v18 )
              CloseHandle(v18);
          }
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x37A,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
            v17);
          v6 = a2;
          v12 = BYTE8(v38);
          v10 = (char *)v38;
          v7 = (CBackgroundCopyFile *)Block;
          v8 = (CBackgroundCopyFile *)Block;
        }
      }
    }
    v20 = *((_DWORD *)v7 + 122);
    if ( (v20 & 1) != 0 )
    {
      v31 = CGlobalObjects::Instance();
      CTelemetryLogger::ClearAllEventsInfo(*((_QWORD *)v31 + 4), (char *)v7 + 144);
    }
    else
    {
      v21 = (v20 & 0x10) != 0 && (*((_BYTE *)v7 + 495) & 2) == 0;
      if ( !v10 )
        std::_Throw_system_error(1);
      v22 = (*((_DWORD *)v10 + 19))-- == 1;
      if ( v22 )
      {
        *((_DWORD *)v10 + 18) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v10 + 2);
      }
      v12 = 0;
      BYTE8(v38) = 0;
      CDownloadManager::Suspend(*(CDownloadManager **)(*((_QWORD *)v7 + 4) + 8LL), v7);
      if ( !v6 )
      {
        memset(v41, 0, sizeof(v41));
        v42 = 0;
        v26 = *((_QWORD *)v7 + 43);
        if ( v26 )
        {
          v27 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 72LL))(v26);
          CPeerTypeMap::operator=(v41, v27);
        }
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::GetImpl'::`2'::impl);
        v30 = *((_QWORD *)v8 + 26);
        Token = 0;
        *(_QWORD *)v37 = v30;
        *(_QWORD *)v36 = v7;
        if ( IsEnabled )
          std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadCanceled> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,CPeerTypeMap &,long &,long &,0>(
            (int)&Token,
            v29,
            (int)v36,
            (int)v37,
            (struct CPeerTypeMap *)v41,
            (__int64)&v46,
            (__int64)&a6);
        else
          std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadCanceled> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,CPeerTypeMap &,long &,int &,0>(
            (int)&Token,
            v29,
            (int)v36,
            (int)v37,
            (struct CPeerTypeMap *)v41,
            (__int64)&v46,
            (__int64)&v45);
        CDownloadManager::FireTelemetry(*(_QWORD *)(*((_QWORD *)v7 + 4) + 8LL), v7, &Token);
        goto LABEL_40;
      }
      if ( v21 )
      {
        v23 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::GetImpl'::`2'::impl);
        *(_QWORD *)v36 = *((_QWORD *)v8 + 26);
        if ( v23 )
        {
          Block = 0;
          Token = v7;
          std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadPaused> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,long &,long &,0>(
            (unsigned int)&Block,
            v24,
            (unsigned int)&Token,
            (unsigned int)v36,
            (__int64)&v46,
            (__int64)&a6);
          CDownloadManager::FireTelemetry(*(_QWORD *)(*((_QWORD *)v7 + 4) + 8LL), v7, &Block);
          v25 = Block;
          goto LABEL_41;
        }
        Token = 0;
        LODWORD(Block) = 0;
        *(_QWORD *)v37 = v7;
        std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadPaused> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,long,int &,0>(
          (unsigned int)&Token,
          v24,
          (unsigned int)v37,
          (unsigned int)v36,
          (__int64)&Block,
          (__int64)&v45);
        CDownloadManager::FireTelemetry(*(_QWORD *)(*((_QWORD *)v7 + 4) + 8LL), v7, &Token);
LABEL_40:
        v25 = Token;
LABEL_41:
        if ( v25 )
        {
          std::_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>::~_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>(v25);
          operator delete(v25);
        }
      }
    }
LABEL_44:
    if ( v12 )
    {
      v22 = (*((_DWORD *)v10 + 19))-- == 1;
      if ( v22 )
      {
        *((_DWORD *)v10 + 18) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v10 + 2);
      }
    }
    CBackgroundCopyFile::_DetachDownloadRequest(v7);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3BE,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x1800823e0  mov     dword ptr [rsp+arg_18], r9d
0x1800823e5  mov     dword ptr [rsp+arg_10], r8d
0x1800823ea  mov     [rsp+arg_8], dl
0x1800823ee  push    rbx
0x1800823ef  push    rsi
0x1800823f0  push    r12
0x1800823f2  push    r13
0x1800823f4  push    r14
0x1800823f6  push    r15
0x1800823f8  sub     rsp, 0E8h
0x1800823ff  mov     rax, cs:__security_cookie
0x180082406  xor     rax, rsp
0x180082409  mov     [rsp+118h+var_48], rax
0x180082411  mov     r12b, dl
0x180082414  mov     rbx, rcx
0x180082417  mov     [rsp+118h+Block], rcx
0x18008241c  mov     r15, rcx
0x18008241f  mov     qword ptr [rcx+180h], 0
0x18008242a  mov     rsi, [rcx+188h]
0x180082431  mov     qword ptr [rcx+188h], 0
0x18008243c  test    rsi, rsi
0x18008243f  jz      short loc_180082478
0x180082441  or      eax, 0FFFFFFFFh
0x180082444  lock xadd [rsi+8], eax
0x180082449  cmp     eax, 1
0x18008244c  jnz     short loc_180082478
0x18008244e  mov     rax, [rsi]
0x180082451  mov     rcx, rsi
0x180082454  mov     rax, [rax]
0x180082457  call    _guard_dispatch_icall
0x18008245c  or      eax, 0FFFFFFFFh
0x18008245f  lock xadd [rsi+0Ch], eax
0x180082464  cmp     eax, 1
0x180082467  jnz     short loc_180082478
0x180082469  mov     rax, [rsi]
0x18008246c  mov     rcx, rsi
0x18008246f  mov     rax, [rax+8]
0x180082473  call    _guard_dispatch_icall
0x180082478  xor     eax, eax
0x18008247a  xchg    al, [rbx+1ECh]
0x180082480  xorps   xmm0, xmm0
0x180082483  movups  [rsp+118h+var_A8], xmm0
0x180082488  mov     qword ptr [rsp+118h+var_A8], rbx
0x18008248d  mov     byte ptr [rsp+118h+var_A8+8], 1
0x180082492  movups  [rsp+118h+var_B8], xmm0
0x180082497  lea     rsi, [rbx+108h]
0x18008249e  mov     qword ptr [rsp+118h+var_B8], rsi
0x1800824a3  mov     byte ptr [rsp+118h+var_B8+8], 0
0x1800824a8  mov     rcx, rsi
0x1800824ab  call    mtx_do_lock
0x1800824b0  test    eax, eax
0x1800824b2  jnz     loc_1800828B1
0x1800824b8  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x1800824bf  jz      loc_1800828BB
0x1800824c5  mov     r13b, 1
0x1800824c8  mov     byte ptr [rsp+118h+var_B8+8], r13b
0x1800824cd  mov     eax, [rbx+1E8h]
0x1800824d3  test    al, 4
0x1800824d5  jnz     loc_18008285A
0x1800824db  and     byte ptr [rbx+1EFh], 0FEh
0x1800824e2  and     eax, 0FFFFFFBFh
0x1800824e5  mov     [rbx+1E8h], eax
0x1800824eb  mov     rcx, rbx; this
0x1800824ee  call    ?_EndProgressMonitoring@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_EndProgressMonitoring(void)
0x1800824f3  mov     rcx, rbx; this
0x1800824f6  call    ?_ShutdownDownloadSink@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_ShutdownDownloadSink(void)
0x1800824fb  lea     rcx, [rbx+0E8h]; this
0x180082502  call    ?Stop@CStopwatchMT@@QEAAXXZ; CStopwatchMT::Stop(void)
0x180082507  cmp     [rsp+118h+arg_20], 0
0x18008250f  jz      loc_1800825DD
0x180082515  mov     rax, [rbx+60h]
0x180082519  neg     rax
0x18008251c  sbb     rcx, rcx
0x18008251f  and     ecx, 20h
0x180082522  lea     r14, [rbx+30h]
0x180082526  add     r14, rcx
0x180082529  cmp     qword ptr [r14+10h], 0
0x18008252e  jz      loc_1800825DD
0x180082534  mov     [rsp+118h+Token], 0
0x18008253d  lea     rdx, [rsp+118h+Token]; int
0x180082542  mov     rcx, [rbx+20h]; this
0x180082546  call    ?ImpersonateOwner@CJobSharedData@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; CJobSharedData::ImpersonateOwner(void)
0x18008254b  nop
0x18008254c  mov     rcx, r14
0x18008254f  cmp     qword ptr [r14+18h], 0Fh
0x180082554  jbe     short loc_180082559
0x180082556  mov     rcx, [r14]; char *
0x180082559  call    ?Delete@CFile@@SAJPEBD@Z; CFile::Delete(char const *)
0x18008255e  cmp     qword ptr [r14+18h], 0Fh
0x180082563  jbe     short loc_180082568
0x180082565  mov     r14, [r14]
0x180082568  mov     [rsp+118h+var_F0], r14
0x18008256d  lea     rcx, aDeletedDestina; "Deleted destination (or temporary) file"...
0x180082574  mov     [rsp+118h+var_F8], rcx; char *
0x180082579  mov     r9d, eax; int
0x18008257c  mov     r8d, 378h; unsigned int
0x180082582  lea     rdx, aCbackgroundcop_16; "CBackgroundCopyFile::Cancel"
0x180082589  mov     ecx, 5; unsigned __int8
0x18008258e  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x180082593  nop
0x180082594  mov     r14, [rsp+118h+Token]
0x180082599  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008259d  jz      short loc_1800825C1
0x18008259f  mov     rdx, r14; Token
0x1800825a2  xor     ecx, ecx; Thread
0x1800825a4  call    cs:__imp_SetThreadToken
0x1800825aa  test    eax, eax
0x1800825ac  jz      loc_1800828CD
0x1800825b2  test    r14, r14
0x1800825b5  jz      short loc_1800825C1
0x1800825b7  mov     rcx, r14; hObject
0x1800825ba  call    cs:__imp_CloseHandle
0x1800825c0  nop
0x1800825c1  jmp     short loc_1800825DD
0x1800825c3  mov     r12b, [rsp+118h+arg_8]
0x1800825cb  mov     r13b, byte ptr [rsp+118h+var_B8+8]
0x1800825d0  mov     rsi, qword ptr [rsp+118h+var_B8]
0x1800825d5  mov     rbx, [rsp+118h+Block]
0x1800825da  mov     r15, rbx
0x1800825dd  mov     eax, [rbx+1E8h]
0x1800825e3  test    al, 1
0x1800825e5  jnz     loc_180082844
0x1800825eb  test    al, 10h
0x1800825ed  jz      short loc_1800825FD
0x1800825ef  test    byte ptr [rbx+1EFh], 2
0x1800825f6  jnz     short loc_1800825FD
0x1800825f8  mov     r14b, 1
0x1800825fb  jmp     short loc_180082600
0x1800825fd  xor     r14b, r14b
0x180082600  test    rsi, rsi
0x180082603  jz      loc_1800828D3
0x180082609  sub     dword ptr [rsi+4Ch], 1
0x18008260d  jnz     short loc_180082620
0x18008260f  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x180082616  lea     rcx, [rsi+10h]; SRWLock
0x18008261a  call    cs:__imp_ReleaseSRWLockExclusive
0x180082620  xor     r13b, r13b
0x180082623  mov     byte ptr [rsp+118h+var_B8+8], r13b
0x180082628  mov     rcx, [rbx+20h]
0x18008262c  mov     rdx, rbx; struct IDownloadRequest *
0x18008262f  mov     rcx, [rcx+8]; this
0x180082633  call    ?Suspend@CDownloadManager@@QEAAJAEBVIDownloadRequest@@@Z; CDownloadManager::Suspend(IDownloadRequest const &)
0x180082638  test    r12b, r12b
0x18008263b  jz      loc_18008271B
0x180082641  test    r14b, r14b
0x180082644  jz      loc_18008285A
0x18008264a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::GetImpl(void)'::`2'::impl
0x180082651  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::__private_IsEnabled(void)
0x180082656  mov     rcx, [r15+0D0h]
0x18008265d  mov     qword ptr [rsp+118h+var_C8], rcx
0x180082662  lea     r9, [rsp+118h+var_C8]
0x180082667  test    al, al
0x180082669  jz      short loc_1800826C3
0x18008266b  mov     [rsp+118h+Block], 0
0x180082674  mov     [rsp+118h+Token], rbx
0x180082679  lea     rax, [rsp+118h+arg_28]
0x180082681  mov     [rsp+118h+var_F0], rax
0x180082686  lea     rax, [rsp+118h+arg_18]
0x18008268e  mov     [rsp+118h+var_F8], rax
0x180082693  lea     r8, [rsp+118h+Token]
0x180082698  lea     rcx, [rsp+118h+Block]
0x18008269d  call    ??$make_unique@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@AEBU?$in_place_type_t@UEventDataDownloadPaused@@@2@PEAVCBackgroundCopyFile@@PEAVTraceLoggingCorrelationVector@@AEAJAEAJ$0A@@std@@YA?AV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@0@AEBU?$in_place_type_t@UEventDataDownloadPaused@@@0@$$QEAPEAVCBackgroundCopyFile@@$$QEAPEAVTraceLoggingCorrelationVector@@AEAJ3@Z; std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadPaused> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,long &,long &,0>(std::in_place_type_t<EventDataDownloadPaused> const &,CBackgroundCopyFile * &&,TraceLoggingCorrelationVector * &&,long &,long &)
0x1800826a2  nop
0x1800826a3  mov     rcx, [rbx+20h]
0x1800826a7  lea     r8, [rsp+118h+Block]
0x1800826ac  mov     rdx, rbx
0x1800826af  mov     rcx, [rcx+8]
0x1800826b3  call    ?FireTelemetry@CDownloadManager@@QEAAXAEBVIDownloadRequest@@$$QEAV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@std@@@Z; CDownloadManager::FireTelemetry(IDownloadRequest const &,std::unique_ptr<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>> &&)
0x1800826b8  nop
0x1800826b9  mov     r14, [rsp+118h+Block]
0x1800826be  jmp     loc_180082828
0x1800826c3  mov     [rsp+118h+Token], 0
0x1800826cc  mov     dword ptr [rsp+118h+Block], 0
0x1800826d4  mov     qword ptr [rsp+118h+var_C0], rbx
0x1800826d9  lea     rax, [rsp+118h+arg_10]
0x1800826e1  mov     [rsp+118h+var_F0], rax
0x1800826e6  lea     rax, [rsp+118h+Block]
0x1800826eb  mov     [rsp+118h+var_F8], rax
0x1800826f0  lea     r8, [rsp+118h+var_C0]
0x1800826f5  lea     rcx, [rsp+118h+Token]
0x1800826fa  call    ??$make_unique@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@AEBU?$in_place_type_t@UEventDataDownloadPaused@@@2@PEAVCBackgroundCopyFile@@PEAVTraceLoggingCorrelationVector@@JAEAH$0A@@std@@YA?AV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@0@AEBU?$in_place_type_t@UEventDataDownloadPaused@@@0@$$QEAPEAVCBackgroundCopyFile@@$$QEAPEAVTraceLoggingCorrelationVector@@$$QEAJAEAH@Z; std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadPaused> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,long,int &,0>(std::in_place_type_t<EventDataDownloadPaused> const &,CBackgroundCopyFile * &&,TraceLoggingCorrelationVector * &&,long &&,int &)
0x1800826ff  nop
0x180082700  mov     rcx, [rbx+20h]
0x180082704  lea     r8, [rsp+118h+Token]
0x180082709  mov     rdx, rbx
0x18008270c  mov     rcx, [rcx+8]
0x180082710  call    ?FireTelemetry@CDownloadManager@@QEAAXAEBVIDownloadRequest@@$$QEAV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@std@@@Z; CDownloadManager::FireTelemetry(IDownloadRequest const &,std::unique_ptr<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>> &&)
0x180082715  nop
0x180082716  jmp     loc_180082823
0x18008271b  xor     edx, edx; Val
0x18008271d  lea     r8d, [rdx+48h]; Size
0x180082721  lea     rcx, [rsp+118h+var_98]; void *
0x180082729  call    memset
0x18008272e  mov     [rsp+118h+var_50], 0
0x18008273a  mov     rcx, [rbx+158h]
0x180082741  test    rcx, rcx
0x180082744  jz      short loc_180082762
0x180082746  mov     rax, [rcx]
0x180082749  mov     rax, [rax+48h]
0x18008274d  call    _guard_dispatch_icall
0x180082752  mov     rdx, rax; Src
0x180082755  lea     rcx, [rsp+118h+var_98]; void *
0x18008275d  call    ??4CPeerTypeMap@@QEAAAEAV0@AEBV0@@Z; CPeerTypeMap::operator=(CPeerTypeMap const &)
0x180082762  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::GetImpl(void)'::`2'::impl
0x180082769  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57081303_TelemetryEventUpdates>::__private_IsEnabled(void)
0x18008276e  mov     rcx, [r15+0D0h]
0x180082775  mov     [rsp+118h+Token], 0
0x18008277e  mov     qword ptr [rsp+118h+var_C0], rcx
0x180082783  mov     qword ptr [rsp+118h+var_C8], rbx
0x180082788  lea     r9, [rsp+118h+var_C0]; int
0x18008278d  lea     r8, [rsp+118h+var_C8]; int
0x180082792  lea     rcx, [rsp+118h+Token]; int
0x180082797  test    al, al
0x180082799  jz      short loc_1800827E0
0x18008279b  lea     rax, [rsp+118h+arg_28]
0x1800827a3  mov     [rsp+118h+var_E8], rax; __int64
0x1800827a8  lea     rax, [rsp+118h+arg_18]
0x1800827b0  mov     [rsp+118h+var_F0], rax; __int64
0x1800827b5  lea     rax, [rsp+118h+var_98]
0x1800827bd  mov     [rsp+118h+var_F8], rax; struct CPeerTypeMap *
0x1800827c2  call    ??$make_unique@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@AEBU?$in_place_type_t@UEventDataDownloadCanceled@@@2@PEAVCBackgroundCopyFile@@PEAVTraceLoggingCorrelationVector@@AEAVCPeerTypeMap@@AEAJAEAJ$0A@@std@@YA?AV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@0@AEBU?$in_place_type_t@UEventDataDownloadCanceled@@@0@$$QEAPEAVCBackgroundCopyFile@@$$QEAPEAVTraceLoggingCorrelationVector@@AEAVCPeerTypeMap@@AEAJ4@Z; std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadCanceled> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,CPeerTypeMap &,long &,long &,0>(std::in_place_type_t<EventDataDownloadCanceled> const &,CBackgroundCopyFile * &&,TraceLoggingCorrelationVector * &&,CPeerTypeMap &,long &,long &)
0x1800827c7  nop
0x1800827c8  mov     rcx, [rbx+20h]
0x1800827cc  lea     r8, [rsp+118h+Token]
0x1800827d1  mov     rdx, rbx
0x1800827d4  mov     rcx, [rcx+8]
0x1800827d8  call    ?FireTelemetry@CDownloadManager@@QEAAXAEBVIDownloadRequest@@$$QEAV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@std@@@Z; CDownloadManager::FireTelemetry(IDownloadRequest const &,std::unique_ptr<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>> &&)
0x1800827dd  nop
0x1800827de  jmp     short loc_180082823
0x1800827e0  lea     rax, [rsp+118h+arg_10]
0x1800827e8  mov     [rsp+118h+var_E8], rax; __int64
0x1800827ed  lea     rax, [rsp+118h+arg_18]
0x1800827f5  mov     [rsp+118h+var_F0], rax; __int64
0x1800827fa  lea     rax, [rsp+118h+var_98]
0x180082802  mov     [rsp+118h+var_F8], rax; struct CPeerTypeMap *
0x180082807  call    ??$make_unique@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@AEBU?$in_place_type_t@UEventDataDownloadCanceled@@@2@PEAVCBackgroundCopyFile@@PEAVTraceLoggingCorrelationVector@@AEAVCPeerTypeMap@@AEAJAEAH$0A@@std@@YA?AV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@0@AEBU?$in_place_type_t@UEventDataDownloadCanceled@@@0@$$QEAPEAVCBackgroundCopyFile@@$$QEAPEAVTraceLoggingCorrelationVector@@AEAVCPeerTypeMap@@AEAJAEAH@Z; std::make_unique<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>,std::in_place_type_t<EventDataDownloadCanceled> const &,CBackgroundCopyFile *,TraceLoggingCorrelationVector *,CPeerTypeMap &,long &,int &,0>(std::in_place_type_t<EventDataDownloadCanceled> const &,CBackgroundCopyFile * &&,TraceLoggingCorrelationVector * &&,CPeerTypeMap &,long &,int &)
0x18008280c  nop
0x18008280d  mov     rcx, [rbx+20h]
0x180082811  lea     r8, [rsp+118h+Token]
0x180082816  mov     rdx, rbx
0x180082819  mov     rcx, [rcx+8]
0x18008281d  call    ?FireTelemetry@CDownloadManager@@QEAAXAEBVIDownloadRequest@@$$QEAV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@std@@@Z; CDownloadManager::FireTelemetry(IDownloadRequest const &,std::unique_ptr<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>> &&)
0x180082822  nop
0x180082823  mov     r14, [rsp+118h+Token]
0x180082828  test    r14, r14
0x18008282b  jz      short loc_18008285A
0x18008282d  mov     rcx, r14
0x180082830  call    ??1?$_Variant_destroy_layer_@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@QEAA@XZ; std::_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>::~_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>(void)
0x180082835  mov     edx, 248h
0x18008283a  mov     rcx, r14; Block
0x18008283d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082842  jmp     short loc_18008285A
0x180082844  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x180082849  lea     rdx, [rbx+90h]
0x180082850  mov     rcx, [rax+20h]
0x180082854  call    ?ClearAllEventsInfo@CTelemetryLogger@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CTelemetryLogger::ClearAllEventsInfo(std::string const &)
0x180082859  nop
0x18008285a  test    r13b, r13b
0x18008285d  jz      short loc_180082877
0x18008285f  sub     dword ptr [rsi+4Ch], 1
0x180082863  jnz     short loc_180082877
0x180082865  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x18008286c  lea     rcx, [rsi+10h]; SRWLock
0x180082870  call    cs:__imp_ReleaseSRWLockExclusive
0x180082876  nop
0x180082877  mov     rcx, rbx; this
0x18008287a  call    ?_DetachDownloadRequest@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_DetachDownloadRequest(void)
0x18008287f  nop
0x180082880  xor     eax, eax
0x180082882  jmp     short loc_18008288F
0x180082884  mov     eax, dword ptr [rsp+118h+Block]
0x180082888  jmp     short loc_18008288F
0x18008288a  mov     eax, 8007000Eh
0x18008288f  mov     rcx, [rsp+118h+var_48]
0x180082897  xor     rcx, rsp; StackCookie
0x18008289a  call    __security_check_cookie
0x18008289f  add     rsp, 0E8h
0x1800828a6  pop     r15
0x1800828a8  pop     r14
0x1800828aa  pop     r13
0x1800828ac  pop     r12
0x1800828ae  pop     rsi
0x1800828af  pop     rbx
0x1800828b0  retn
0x1800828b1  mov     ecx, 5; int
0x1800828b6  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800828bb  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x1800828c2  mov     ecx, 6; int
0x1800828c7  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800828cd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800828d3  mov     ecx, 1
0x1800828d8  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
