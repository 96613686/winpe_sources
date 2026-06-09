# CComposition::PreRender(bool *)

- ea: `0x18012fe64`
- end: `0x180130315`
- name: `?PreRender@CComposition@@IEAAJPEA_N@Z`
- size: `1201`
- prototype: `__int64 __fastcall(CComposition *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801308e0`

## callees

- `0x1800174a0`
- `0x18002f9e0`
- `0x180050270`
- `0x180056f7c`
- `0x1800c08f0`
- `0x1800d0b90`
- `0x18012e380`
- `0x18012e3d0`
- `0x18012e654`
- `0x18012e6f4`
- `0x18012eac0`
- `0x18012eb70`
- `0x18012ee30`
- `0x18012ee60`
- `0x18012eeb8`
- `0x18012f0d4`
- `0x18012f180`
- `0x18012f2a8`
- `0x18012f2d8`
- `0x18012f2f8`
- `0x18012f390`
- `0x18012f444`
- `0x18012f7d4`
- `0x18012fe64`
- `0x1801328b0`
- `0x180132b30`
- `0x180134f5c`
- `0x180136cf0`
- `0x180184ea4`
- `0x1801acb70`
- `0x180259200`
- `0x18025933c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180130000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180130056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180130146`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180130000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180130056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180130146`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18013000d`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180130063`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180130153`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18013000d`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180130063`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180130153`

## pseudocode

```c
__int64 __fastcall CComposition::PreRender(CComposition *this, bool *a2)
{
  CTreeLock *v2; // r12
  CDebugVisualImage *v4; // rbx
  unsigned int i; // edi
  __int64 v7; // rdx
  wil::details *v8; // rcx
  int v9; // eax
  int v10; // r14d
  CManipulationManager *v11; // rcx
  CManipulationManager *v12; // rcx
  int v14; // eax
  unsigned __int64 v15; // rcx
  HANDLE CurrentThread; // rax
  BOOL v17; // eax
  int v18; // eax
  unsigned __int64 v19; // rcx
  HANDLE v20; // rax
  BOOL v21; // eax
  int v22; // eax
  CComposition *v23; // rcx
  bool v24; // al
  CSceneResourceManager *v25; // rcx
  unsigned __int64 v26; // rcx
  HANDLE v27; // rax
  BOOL v28; // eax
  int v29; // eax
  int v30; // edi
  CExpressionManager *v31; // r15
  unsigned __int64 v32; // rdi
  int v33; // eax
  int v34; // edi
  int v35; // eax
  struct CDebugVisualImage *v36; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int64 CycleTime; // [rsp+78h] [rbp+48h] BYREF

  v2 = (CComposition *)((char *)this + 5696);
  *a2 = 1;
  v4 = 0;
  v36 = 0;
  CTreeLock::AcquireExclusive((CComposition *)((char *)this + 5696));
  if ( (__int64)(*((_QWORD *)this + 724) - *((_QWORD *)this + 723)) >> 3 )
    detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::clear_region();
  CComposition::DestroyDelayDeleteResources(this);
  CEffectCompilationService::HandleCompletedTasks(*((CEffectCompilationService **)this + 81));
  for ( i = 0; i < *((_DWORD *)this + 214); ++i )
  {
    v7 = *(_QWORD *)(*((_QWORD *)this + 104) + 8LL * i);
    if ( v7 )
    {
      v8 = *(wil::details **)(v7 + 48);
      if ( v8 )
      {
        if ( *(_BYTE *)(v7 + 121) && !*(_DWORD *)(v7 + 144) )
        {
          *(_BYTE *)(v7 + 121) = 0;
          wil::details::SetEvent(v8, (void *)v7);
        }
      }
    }
  }
  v9 = CComposition::BeginCompositionFrame(this);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v14 = CComposition::ProcessBatches(this);
    v10 = v14;
    if ( v14 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A6A8, 3u, v14, 0xC5Eu, 0);
    }
    else
    {
      CExpressionManager::NotifyBatchProcessingComplete(*((CExpressionManager **)this + 102));
      v15 = 0;
      CycleTime = 0;
      if ( ::CycleTime )
      {
        CurrentThread = GetCurrentThread();
        v17 = QueryThreadCycleTime(CurrentThread, &CycleTime);
        v15 = CycleTime;
        if ( v17 )
          qword_1803BADB0 += CycleTime - ::CycleTime;
      }
      ::CycleTime = v15;
      v18 = CComposition::ProcessSurfaceUpdates(this);
      v10 = v18;
      if ( v18 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A6A8, 3u, v18, 0xC63u, 0);
      }
      else
      {
        v19 = 0;
        CycleTime = 0;
        if ( ::CycleTime )
        {
          v20 = GetCurrentThread();
          v21 = QueryThreadCycleTime(v20, &CycleTime);
          v19 = CycleTime;
          if ( v21 )
            qword_1803BADB8 += CycleTime - ::CycleTime;
        }
        ::CycleTime = v19;
        if ( g_pDebugVisual )
        {
          v35 = CDebugVisualImage::Create(this, g_pDebugVisual, &v36);
          v4 = v36;
          if ( v35 >= 0 )
            *((_BYTE *)this + 6408) = 1;
        }
        v22 = CRenderTargetManager::CheckOcclusionState(*((CRenderTargetManager **)this + 77));
        v10 = v22;
        if ( v22 < 0 )
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A6A8, 3u, v22, 0xC71u, 0);
        (*(void (__fastcall **)(CComposition *))(*(_QWORD *)this + 32LL))(this);
        v24 = CComposition::ClearCaches(v23);
        v25 = (CSceneResourceManager *)*((_QWORD *)this + 84);
        *a2 = v24;
        if ( (__int64)(*((_QWORD *)v25 + 6) - *((_QWORD *)v25 + 5)) >> 3 )
          CSceneResourceManager::EnsureSceneCompositor(v25);
        else
          CSceneResourceManager::ReleaseSceneCompositor(v25);
        if ( CComposition::TotallyOccluded(this) )
        {
          dword_1803BAD70 |= 0x200u;
          v31 = (CExpressionManager *)*((_QWORD *)this + 102);
          if ( *((_QWORD *)v31 + 64) )
          {
            v32 = *((_QWORD *)this + 110);
            CExpressionManager::Invalidate(*((CExpressionManager **)this + 102));
            CExpressionManager::UpdateExpressions(v31, v32);
          }
          CExpressionManager::ShrinkQueuedStateChanges(v31);
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 78) + 48LL))(*((_QWORD *)this + 78))
            || *((_DWORD *)this + 1482) )
          {
            *((_BYTE *)this + 6408) = 1;
          }
        }
        else
        {
          CSuperWetInkManager::DirtyActiveInk(*((CSuperWetInkManager **)this + 82));
          CComposition::UpdateAnimateResources(this);
          CComposition::UpdateExpressions(this);
          v26 = 0;
          CycleTime = 0;
          if ( ::CycleTime )
          {
            v27 = GetCurrentThread();
            v28 = QueryThreadCycleTime(v27, &CycleTime);
            v26 = CycleTime;
            if ( v28 )
              qword_1803BADC0 += CycleTime - ::CycleTime;
          }
          ::CycleTime = v26;
          DataProviderManager::PostExpressionsUpdated(*((DataProviderManager **)this + 799));
          CSceneResourceManager::FrameTick(*((CSceneResourceManager **)this + 84));
          v29 = CComposition::CleanTrees(this);
          v30 = v29;
          if ( v29 < 0 )
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A6A8, 3u, v29, 0xC90u, 0);
          if ( !v10 || v10 >= 0 && v30 < 0 )
            v10 = v30;
        }
      }
    }
  }
  else
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A6A8, 3u, v9, 0xC5Bu, 0);
  }
  v11 = (CManipulationManager *)*((_QWORD *)this + 80);
  if ( v11 )
    CManipulationManager::ReleasePendingReferences(v11);
  if ( *((_BYTE *)this + 6408) )
  {
    v33 = CComposition::CleanTrees(this);
    v34 = v33;
    if ( v33 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_18032A6A8, 3u, v33, 0xCAFu, 0);
    if ( !v10 || v10 >= 0 && v34 < 0 )
      v10 = v34;
  }
  CComposition::CleanPossibleDirtyInputSinkList(this);
  if ( v4 )
    CDebugVisualImage::LockAndRead(v4);
  CTreeLock::ReleaseExclusive(v2);
  if ( *((_BYTE *)this + 6456) )
  {
    v12 = *(CManipulationManager **)(*((_QWORD *)this + 79) + 24LL);
    if ( v12 )
      (*(void (__fastcall **)(CManipulationManager *))(*(_QWORD *)v12 + 16LL))(v12);
    *((_BYTE *)this + 6456) = 0;
  }
  CManipulationManager::WakeMTForMidmanipulationUpdateIfNecessary(v12);
  wil::com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>::~com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>(&v36);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18012fe64  mov     [rsp-38h+arg_10], rbx
0x18012fe69  push    rbp
0x18012fe6a  push    rsi
0x18012fe6b  push    rdi
0x18012fe6c  push    r12
0x18012fe6e  push    r13
0x18012fe70  push    r14
0x18012fe72  push    r15
0x18012fe74  mov     rbp, rsp
0x18012fe77  sub     rsp, 30h
0x18012fe7b  lea     r12, [rcx+1640h]
0x18012fe82  mov     byte ptr [rdx], 1
0x18012fe85  mov     rsi, rcx
0x18012fe88  xor     r13d, r13d
0x18012fe8b  mov     ebx, r13d
0x18012fe8e  mov     rcx, r12; this
0x18012fe91  mov     [rbp+arg_0], rbx
0x18012fe95  mov     r15, rdx
0x18012fe98  call    ?AcquireExclusive@CTreeLock@@QEAAXXZ; CTreeLock::AcquireExclusive(void)
0x18012fe9d  lea     rcx, [rsi+1698h]
0x18012fea4  mov     r8, [rcx+8]
0x18012fea8  sub     r8, [rcx]
0x18012feab  sar     r8, 3
0x18012feaf  test    r8, r8
0x18012feb2  jnz     loc_180130297
0x18012feb8  mov     rcx, rsi; this
0x18012febb  call    ?DestroyDelayDeleteResources@CComposition@@QEAAXXZ; CComposition::DestroyDelayDeleteResources(void)
0x18012fec0  mov     rcx, [rsi+288h]; this
0x18012fec7  call    ?HandleCompletedTasks@CEffectCompilationService@@QEAAXXZ; CEffectCompilationService::HandleCompletedTasks(void)
0x18012fecc  mov     edi, r13d
0x18012fecf  cmp     [rsi+358h], r13d
0x18012fed6  jbe     short loc_18012FF07
0x18012fed8  mov     rax, [rsi+340h]
0x18012fedf  mov     ecx, edi
0x18012fee1  mov     rdx, [rax+rcx*8]; void *
0x18012fee5  test    rdx, rdx
0x18012fee8  jz      short loc_18012FEFD
0x18012feea  mov     rcx, [rdx+30h]; this
0x18012feee  test    rcx, rcx
0x18012fef1  jz      short loc_18012FEFD
0x18012fef3  cmp     [rdx+79h], r13b
0x18012fef7  jnz     loc_1801301D2
0x18012fefd  inc     edi
0x18012feff  cmp     edi, [rsi+358h]
0x18012ff05  jb      short loc_18012FED8
0x18012ff07  mov     rcx, rsi; this
0x18012ff0a  call    ?BeginCompositionFrame@CComposition@@IEAAJXZ; CComposition::BeginCompositionFrame(void)
0x18012ff0f  mov     r14d, eax
0x18012ff12  test    eax, eax
0x18012ff14  jns     loc_18012FFD1
0x18012ff1a  mov     [rsp+30h+var_8], r13; void *
0x18012ff1f  mov     [rsp+30h+var_10], 0C5Bh; unsigned int
0x18012ff27  mov     r8d, 3; unsigned int
0x18012ff2d  lea     rdx, qword_18032A6A8; int *
0x18012ff34  mov     r9d, eax; int
0x18012ff37  lea     ecx, [r8+11h]; unsigned int
0x18012ff3b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18012ff40  mov     rcx, [rsi+280h]; this
0x18012ff47  test    rcx, rcx
0x18012ff4a  jz      short loc_18012FF51
0x18012ff4c  call    ?ReleasePendingReferences@CManipulationManager@@QEAAXXZ; CManipulationManager::ReleasePendingReferences(void)
0x18012ff51  mov     al, [rsi+1908h]
0x18012ff57  test    al, al
0x18012ff59  jnz     loc_1801302A1
0x18012ff5f  mov     rcx, rsi; this
0x18012ff62  call    ?CleanPossibleDirtyInputSinkList@CComposition@@QEAAJXZ; CComposition::CleanPossibleDirtyInputSinkList(void)
0x18012ff67  test    rbx, rbx
0x18012ff6a  jz      short loc_18012FF74
0x18012ff6c  mov     rcx, rbx; this
0x18012ff6f  call    ?LockAndRead@CDebugVisualImage@@QEAAXXZ; CDebugVisualImage::LockAndRead(void)
0x18012ff74  mov     rcx, r12; this
0x18012ff77  call    ?ReleaseExclusive@CTreeLock@@QEAAXXZ; CTreeLock::ReleaseExclusive(void)
0x18012ff7c  cmp     [rsi+1938h], r13b
0x18012ff83  jz      short loc_18012FFA8
0x18012ff85  mov     rax, [rsi+278h]
0x18012ff8c  mov     rcx, [rax+18h]
0x18012ff90  test    rcx, rcx
0x18012ff93  jz      short loc_18012FFA1
0x18012ff95  mov     rax, [rcx]
0x18012ff98  mov     rax, [rax+10h]
0x18012ff9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ffa1  mov     [rsi+1938h], r13b
0x18012ffa8  call    ?WakeMTForMidmanipulationUpdateIfNecessary@CManipulationManager@@QEAAXXZ; CManipulationManager::WakeMTForMidmanipulationUpdateIfNecessary(void)
0x18012ffad  lea     rcx, [rbp+arg_0]
0x18012ffb1  call    ??1?$com_ptr_t@VCDebugVisualImage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>::~com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>(void)
0x18012ffb6  mov     rbx, [rsp+30h+arg_10]
0x18012ffbe  mov     eax, r14d
0x18012ffc1  add     rsp, 30h
0x18012ffc5  pop     r15
0x18012ffc7  pop     r14
0x18012ffc9  pop     r13
0x18012ffcb  pop     r12
0x18012ffcd  pop     rdi
0x18012ffce  pop     rsi
0x18012ffcf  pop     rbp
0x18012ffd0  retn
0x18012ffd1  mov     rcx, rsi; this
0x18012ffd4  call    ?ProcessBatches@CComposition@@IEAAJXZ; CComposition::ProcessBatches(void)
0x18012ffd9  mov     r14d, eax
0x18012ffdc  test    eax, eax
0x18012ffde  js      loc_180130207
0x18012ffe4  mov     rcx, [rsi+330h]; this
0x18012ffeb  call    ?NotifyBatchProcessingComplete@CExpressionManager@@QEAAXXZ; CExpressionManager::NotifyBatchProcessingComplete(void)
0x18012fff0  cmp     cs:CycleTime, r13
0x18012fff7  mov     rcx, r13
0x18012fffa  mov     [rbp+CycleTime], rcx
0x18012fffe  jz      short loc_18013002C
0x180130000  call    cs:__imp_GetCurrentThread
0x180130006  mov     rcx, rax; ThreadHandle
0x180130009  lea     rdx, [rbp+CycleTime]; CycleTime
0x18013000d  call    cs:__imp_QueryThreadCycleTime
0x180130013  mov     rcx, [rbp+CycleTime]
0x180130017  test    eax, eax
0x180130019  jz      short loc_18013002C
0x18013001b  mov     rax, rcx
0x18013001e  sub     rax, cs:CycleTime
0x180130025  add     cs:qword_1803BADB0, rax
0x18013002c  mov     cs:CycleTime, rcx
0x180130033  mov     rcx, rsi; this
0x180130036  call    ?ProcessSurfaceUpdates@CComposition@@IEAAJXZ; CComposition::ProcessSurfaceUpdates(void)
0x18013003b  mov     r14d, eax
0x18013003e  test    eax, eax
0x180130040  js      loc_180130219
0x180130046  cmp     cs:CycleTime, r13
0x18013004d  mov     rcx, r13
0x180130050  mov     [rbp+CycleTime], rcx
0x180130054  jz      short loc_180130082
0x180130056  call    cs:__imp_GetCurrentThread
0x18013005c  mov     rcx, rax; ThreadHandle
0x18013005f  lea     rdx, [rbp+CycleTime]; CycleTime
0x180130063  call    cs:__imp_QueryThreadCycleTime
0x180130069  mov     rcx, [rbp+CycleTime]
0x18013006d  test    eax, eax
0x18013006f  jz      short loc_180130082
0x180130071  mov     rax, rcx
0x180130074  sub     rax, cs:CycleTime
0x18013007b  add     cs:qword_1803BADB8, rax
0x180130082  mov     rdx, cs:?g_pDebugVisual@@3PEAVCVisual@@EA; struct CVisual *
0x180130089  mov     cs:CycleTime, rcx
0x180130090  test    rdx, rdx
0x180130093  jnz     loc_1801302F1
0x180130099  mov     rcx, [rsi+268h]; this
0x1801300a0  call    ?CheckOcclusionState@CRenderTargetManager@@QEAAJXZ; CRenderTargetManager::CheckOcclusionState(void)
0x1801300a5  mov     r14d, eax
0x1801300a8  test    eax, eax
0x1801300aa  jns     short loc_1801300D2
0x1801300ac  mov     r8d, 3; unsigned int
0x1801300b2  mov     [rsp+30h+var_8], r13; void *
0x1801300b7  mov     r9d, eax; int
0x1801300ba  mov     [rsp+30h+var_10], 0C71h; unsigned int
0x1801300c2  lea     rdx, qword_18032A6A8; int *
0x1801300c9  lea     ecx, [r8+11h]; unsigned int
0x1801300cd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801300d2  mov     rax, [rsi]
0x1801300d5  mov     rcx, rsi
0x1801300d8  mov     rax, [rax+20h]
0x1801300dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801300e1  call    ?ClearCaches@CComposition@@IEBA_NXZ; CComposition::ClearCaches(void)
0x1801300e6  mov     rcx, [rsi+2A0h]; this
0x1801300ed  mov     [r15], al
0x1801300f0  mov     rax, [rcx+30h]
0x1801300f4  sub     rax, [rcx+28h]
0x1801300f8  sar     rax, 3
0x1801300fc  test    rax, rax
0x1801300ff  jnz     loc_1801301FD
0x180130105  call    ?ReleaseSceneCompositor@CSceneResourceManager@@AEAAXXZ; CSceneResourceManager::ReleaseSceneCompositor(void)
0x18013010a  mov     rcx, rsi; this
0x18013010d  call    ?TotallyOccluded@CComposition@@QEBA_NXZ; CComposition::TotallyOccluded(void)
0x180130112  test    al, al
0x180130114  jnz     loc_18013022B
0x18013011a  mov     rcx, [rsi+290h]; this
0x180130121  call    ?DirtyActiveInk@CSuperWetInkManager@@QEAAXXZ; CSuperWetInkManager::DirtyActiveInk(void)
0x180130126  mov     rcx, rsi; this
0x180130129  call    ?UpdateAnimateResources@CComposition@@IEAAXXZ; CComposition::UpdateAnimateResources(void)
0x18013012e  mov     rcx, rsi; this
0x180130131  call    ?UpdateExpressions@CComposition@@QEAAXXZ; CComposition::UpdateExpressions(void)
0x180130136  cmp     cs:CycleTime, r13
0x18013013d  mov     rcx, r13
0x180130140  mov     [rbp+CycleTime], rcx
0x180130144  jz      short loc_180130172
0x180130146  call    cs:__imp_GetCurrentThread
0x18013014c  mov     rcx, rax; ThreadHandle
0x18013014f  lea     rdx, [rbp+CycleTime]; CycleTime
0x180130153  call    cs:__imp_QueryThreadCycleTime
0x180130159  mov     rcx, [rbp+CycleTime]
0x18013015d  test    eax, eax
0x18013015f  jz      short loc_180130172
0x180130161  mov     rax, rcx
0x180130164  sub     rax, cs:CycleTime
0x18013016b  add     cs:qword_1803BADC0, rax
0x180130172  mov     cs:CycleTime, rcx
0x180130179  mov     rcx, [rsi+18F8h]; this
0x180130180  call    ?PostExpressionsUpdated@DataProviderManager@@QEAAXXZ; DataProviderManager::PostExpressionsUpdated(void)
0x180130185  mov     rcx, [rsi+2A0h]; this
0x18013018c  call    ?FrameTick@CSceneResourceManager@@QEAAXXZ; CSceneResourceManager::FrameTick(void)
0x180130191  mov     rcx, rsi; this
0x180130194  call    ?CleanTrees@CComposition@@IEAAJXZ; CComposition::CleanTrees(void)
0x180130199  mov     edi, eax
0x18013019b  test    eax, eax
0x18013019d  jns     short loc_1801301C5
0x18013019f  mov     r8d, 3; unsigned int
0x1801301a5  mov     [rsp+30h+var_8], r13; void *
0x1801301aa  mov     r9d, eax; int
0x1801301ad  mov     [rsp+30h+var_10], 0C90h; unsigned int
0x1801301b5  lea     rdx, qword_18032A6A8; int *
0x1801301bc  lea     ecx, [r8+11h]; unsigned int
0x1801301c0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801301c5  test    r14d, r14d
0x1801301c8  jnz     short loc_1801301ED
0x1801301ca  mov     r14d, edi
0x1801301cd  jmp     loc_18012FF40
0x1801301d2  cmp     [rdx+90h], r13d
0x1801301d9  jnz     loc_18012FEFD
0x1801301df  mov     [rdx+79h], r13b
0x1801301e3  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1801301e8  jmp     loc_18012FEFD
0x1801301ed  js      loc_18012FF40
0x1801301f3  test    edi, edi
0x1801301f5  jns     loc_18012FF40
0x1801301fb  jmp     short loc_1801301CA
0x1801301fd  call    ?EnsureSceneCompositor@CSceneResourceManager@@AEAAJXZ; CSceneResourceManager::EnsureSceneCompositor(void)
0x180130202  jmp     loc_18013010A
0x180130207  mov     [rsp+30h+var_8], r13
0x18013020c  mov     [rsp+30h+var_10], 0C5Eh
0x180130214  jmp     loc_18012FF27
0x180130219  mov     [rsp+30h+var_8], r13
0x18013021e  mov     [rsp+30h+var_10], 0C63h
0x180130226  jmp     loc_18012FF27
0x18013022b  bts     cs:dword_1803BAD70, 9
0x180130233  mov     r15, [rsi+330h]
0x18013023a  cmp     [r15+200h], r13
0x180130241  jnz     short loc_18013027B
0x180130243  mov     rcx, r15; this
0x180130246  call    ?ShrinkQueuedStateChanges@CExpressionManager@@AEAAXXZ; CExpressionManager::ShrinkQueuedStateChanges(void)
0x18013024b  mov     rcx, [rsi+270h]
0x180130252  mov     rax, [rcx]
0x180130255  mov     rax, [rax+30h]
0x180130259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013025e  test    al, al
0x180130260  jnz     short loc_18013026F
0x180130262  cmp     [rsi+1728h], r13d
0x180130269  jz      loc_18012FF40
0x18013026f  mov     byte ptr [rsi+1908h], 1
0x180130276  jmp     loc_18012FF40
0x18013027b  mov     rdi, [rsi+370h]
0x180130282  mov     rcx, r15; this
0x180130285  call    ?Invalidate@CExpressionManager@@QEAAXXZ; CExpressionManager::Invalidate(void)
0x18013028a  mov     rdx, rdi; unsigned __int64
0x18013028d  mov     rcx, r15; this
0x180130290  call    ?UpdateExpressions@CExpressionManager@@QEAAX_K@Z; CExpressionManager::UpdateExpressions(unsigned __int64)
0x180130295  jmp     short loc_180130243
0x180130297  call    ?clear_region@?$vector_facade@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$buffer_impl@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@$07$00Vliberal_expansion_policy@detail@@@detail@@@detail@@IEAAX_K0@Z; detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::clear_region(unsigned __int64,unsigned __int64)
0x18013029c  jmp     loc_18012FEB8
0x1801302a1  mov     rcx, rsi; this
0x1801302a4  call    ?CleanTrees@CComposition@@IEAAJXZ; CComposition::CleanTrees(void)
0x1801302a9  mov     edi, eax
0x1801302ab  test    eax, eax
0x1801302ad  jns     short loc_1801302D5
0x1801302af  mov     r8d, 3; unsigned int
0x1801302b5  mov     [rsp+30h+var_8], r13; void *
0x1801302ba  mov     r9d, eax; int
0x1801302bd  mov     [rsp+30h+var_10], 0CAFh; unsigned int
0x1801302c5  lea     rdx, qword_18032A6A8; int *
0x1801302cc  lea     ecx, [r8+11h]; unsigned int
0x1801302d0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801302d5  test    r14d, r14d
0x1801302d8  jz      loc_1802A6C0C
0x1801302de  js      loc_18012FF5F
0x1801302e4  test    edi, edi
0x1801302e6  jns     loc_18012FF5F
0x1801302ec  jmp     loc_1802A6C0C
0x1801302f1  lea     r8, [rbp+arg_0]; struct CDebugVisualImage **
0x1801302f5  mov     rcx, rsi; struct CComposition *
0x1801302f8  call    ?Create@CDebugVisualImage@@SAJPEAVCComposition@@PEAVCVisual@@PEAPEAV1@@Z; CDebugVisualImage::Create(CComposition *,CVisual *,CDebugVisualImage * *)
0x1801302fd  mov     rbx, [rbp+arg_0]
0x180130301  test    eax, eax
0x180130303  js      loc_180130099
0x180130309  mov     byte ptr [rsi+1908h], 1
0x180130310  jmp     loc_180130099
0x1802a6c0c  mov     r14d, edi
0x1802a6c0f  jmp     loc_18012FF5F
```
