# CEffectCompilationService::BeginCompile(CCompiledEffectTemplate *,Windows::UI::Composition::IEffectDescription *,CEffectCompilationTask * *)

- ea: `0x1800f5f88`
- end: `0x1800f63dd`
- name: `?BeginCompile@CEffectCompilationService@@QEAAJPEAVCCompiledEffectTemplate@@PEAUIEffectDescription@Composition@UI@Windows@@PEAPEAVCEffectCompilationTask@@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(CEffectCompilationService *__hidden this, struct CCompiledEffectTemplate *, struct Windows::UI::Composition::IEffectDescription *, struct CEffectCompilationTask **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f5c74`

## callees

- `0x18004a92c`
- `0x18004b77c`
- `0x18004deb0`
- `0x180050270`
- `0x180055f50`
- `0x1800c4d4c`
- `0x1800f5f88`
- `0x1800f63e4`
- `0x1800f6490`
- `0x18014613c`
- `0x1801c15a8`
- `0x1801e38ec`
- `0x1801ef800`
- `0x180204120`
- `0x18021bfd4`
- `0x1802341d8`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f60f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f61cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f60f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f61cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f6072`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f6072`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f60e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f60e9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f6108`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f6108`

## pseudocode

```c
__int64 __fastcall CEffectCompilationService::BeginCompile(
        CEffectCompilationService *this,
        struct CCompiledEffectTemplate *a2,
        struct Windows::UI::Composition::IEffectDescription *a3,
        struct CEffectCompilationTask **a4)
{
  __int64 v4; // rax
  PTP_WORK *v6; // rdi
  CNotificationResource *v8; // r12
  char *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // r12
  PTP_WORK *v14; // rbx
  unsigned __int8 v15; // r13
  int v16; // eax
  int v17; // ebx
  __int64 *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  unsigned int v22; // edx
  int v23; // esi
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  struct CEffectCompilationTask *v27; // rax
  unsigned int v29; // eax
  int v30; // r9d
  CEffectCompilationTask *v31; // rax
  CEffectCompilationTask *v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int (__fastcall *v35)(struct Windows::UI::Composition::IEffectDescription *, PVOID *); // rbx
  const char *v36; // r15
  PVOID v37; // rcx
  char v38; // bl
  unsigned int ChannelCallbackId; // eax
  int v40; // edx
  int v41; // eax
  _QWORD v42[2]; // [rsp+40h] [rbp-28h] BYREF
  char v43[24]; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  PVOID pv; // [rsp+B0h] [rbp+48h] BYREF
  struct CCompiledEffectTemplate *v46; // [rsp+B8h] [rbp+50h]
  char *v47; // [rsp+C0h] [rbp+58h]
  struct CEffectCompilationTask **v48; // [rsp+C8h] [rbp+60h]

  v48 = a4;
  v46 = a2;
  v4 = *(_QWORD *)a3;
  v6 = 0;
  v42[1] = a3;
  pv = 0;
  v8 = a2;
  v9 = (char *)this + 96;
  v42[0] = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(v4 + 104))(a3);
  v10 = *((_QWORD *)this + 15);
  v11 = 2LL * (v42[0] & *((_QWORD *)this + 18));
  v47 = (char *)this + 96;
  v12 = *(_QWORD **)(v10 + 8 * v11 + 8);
  if ( v12 == *((_QWORD **)this + 13) )
  {
LABEL_7:
    v12 = 0;
    goto LABEL_8;
  }
  v13 = *(_QWORD **)(v10 + 8 * v11);
  while ( 1 )
  {
    if ( v42[0] != v12[2] )
      goto LABEL_4;
    if ( (*(unsigned __int8 (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *, _QWORD))(*(_QWORD *)a3 + 96LL))(
           a3,
           v12[3]) )
    {
      break;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_4:
    if ( v12 == v13 )
    {
      v8 = v46;
      goto LABEL_7;
    }
    v12 = (_QWORD *)v12[1];
  }
  v8 = v46;
LABEL_8:
  if ( !v12 )
    v12 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v12 == *((_QWORD **)this + 13) )
  {
    v31 = (CEffectCompilationTask *)DefaultHeap::AllocClear(0x68u);
    if ( !v31 )
      ModuleFailFastForHRESULT(-2147024882, retaddr);
    v32 = CEffectCompilationTask::CEffectCompilationTask(v31, this, a3);
    Microsoft::WRL::ComPtr<CManipulationContext>::operator=(&pv, v32);
    v6 = (PTP_WORK *)pv;
    if ( !pv )
    {
      v17 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x70u, 0);
      goto LABEL_31;
    }
    if ( CCommonRegistryData::EnableEffectCaching )
      std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::emplace<EffectDescriptionKey &,CEffectCompilationTask *>(
        (char *)this + 96,
        v43,
        v42,
        &pv);
    v33 = CEffectCompilationTask::Initialize(v6);
    v17 = v33;
    if ( v33 >= 0 )
    {
      v15 = 0;
      goto LABEL_14;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0x77u, 0);
  }
  else
  {
    v14 = (PTP_WORK *)v12[4];
    v15 = 1;
    if ( v14 )
    {
      (*(void (__fastcall **)(PTP_WORK *))*v14)(v14);
      v6 = v14;
    }
    CEffectCompilationService::TryReviveDeadTask(this, (const struct CEffectCompilationTask *)v6);
LABEL_14:
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    {
      v34 = *(_QWORD *)a3;
      pv = 0;
      v35 = *(int (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *, PVOID *))(v34 + 88);
      Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&pv);
      if ( v35(a3, &pv) >= 0 )
        v36 = (const char *)(*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)pv + 16LL))(pv);
      else
        v36 = "null";
      if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
      {
        v38 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(*(_QWORD *)a3 + 80LL))(a3);
        ChannelCallbackId = CNotificationResource::GetChannelCallbackId(v8);
        McTemplateU0pdsddt_EventWriteTransfer(v15, v40, (_DWORD)v6, ChannelCallbackId, (__int64)v36, v40, v38, v15);
      }
      v37 = pv;
      if ( pv )
      {
        pv = 0;
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    v16 = CEffectCompilationTask::AddTemplate_RenderThread((CEffectCompilationTask *)v6, v8);
    v17 = v16;
    if ( v16 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v18 = (__int64 *)((char *)this + 64);
      v19 = 0;
      v20 = *((_QWORD *)this + 8);
      v21 = *((unsigned int *)this + 22);
      while ( (unsigned int)v19 < (unsigned int)v21 )
      {
        if ( v6 == *(PTP_WORK **)(v20 + 8 * v19) )
          goto LABEL_26;
        v19 = (unsigned int)(v19 + 1);
      }
      v22 = v21 + 1;
      pv = v6;
      if ( (int)v21 + 1 < (unsigned int)v21 )
      {
        v17 = -2147024362;
        v29 = 183;
        v23 = -2147024362;
        v30 = -2147024362;
      }
      else
      {
        if ( v22 <= *((_DWORD *)this + 21) )
        {
          *(_QWORD *)(v20 + 8 * v21) = v6;
          v23 = 0;
          *((_DWORD *)this + 22) = v22;
LABEL_23:
          if ( *((_BYTE *)v6 + 96) )
          {
            v24 = *v18;
            v25 = *((unsigned int *)this + 50);
            v26 = *(_QWORD *)(*v18 + 8LL * (unsigned int)(*((_DWORD *)this + 22) - 1));
            *(_QWORD *)(v24 + 8LL * (unsigned int)(*((_DWORD *)this + 22) - 1)) = *(_QWORD *)(*v18 + 8 * v25);
            *(_QWORD *)(v24 + 8 * v25) = v26;
            ++*((_DWORD *)this + 50);
            SetEvent(*((HANDLE *)this + 7));
          }
          v17 = v23;
LABEL_26:
          if ( this != (CEffectCompilationService *)-16LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
          if ( !v15 )
            SubmitThreadpoolWork(v6[8]);
          v27 = (struct CEffectCompilationTask *)v6;
          v6 = 0;
          *v48 = v27;
          if ( v17 < 0 )
            goto LABEL_35;
LABEL_31:
          if ( v6 )
            (*((void (__fastcall **)(PTP_WORK *))*v6 + 1))(v6);
          return (unsigned int)v17;
        }
        v41 = DynArrayImpl<0>::AddMultipleAndSet((char *)this + 64, 8, 1, &pv);
        v23 = v41;
        if ( v41 >= 0 )
          goto LABEL_23;
        v17 = v41;
        v30 = v41;
        v29 = 194;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v30, v29, 0);
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v23, 0x9Cu, 0);
      if ( this != (CEffectCompilationService *)-16LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_35;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v16, 0x94u, 0);
LABEL_35:
    v9 = v47;
  }
  if ( v6 )
  {
    std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::_Erase<EffectDescriptionKey>(
      v9,
      v42);
    goto LABEL_31;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800f5f88  mov     [rsp-40h+arg_18], r9
0x1800f5f8d  mov     [rsp-40h+arg_8], rdx
0x1800f5f92  push    rbp
0x1800f5f93  push    rbx
0x1800f5f94  push    rsi
0x1800f5f95  push    rdi
0x1800f5f96  push    r12
0x1800f5f98  push    r13
0x1800f5f9a  push    r14
0x1800f5f9c  push    r15
0x1800f5f9e  mov     rbp, rsp
0x1800f5fa1  sub     rsp, 68h
0x1800f5fa5  mov     rax, [r8]
0x1800f5fa8  mov     r14, rcx
0x1800f5fab  xor     edi, edi
0x1800f5fad  mov     [rbp+var_20], r8
0x1800f5fb1  mov     rcx, r8
0x1800f5fb4  mov     [rbp+pv], rdi
0x1800f5fb8  mov     rsi, r8
0x1800f5fbb  mov     r12, rdx
0x1800f5fbe  mov     rax, [rax+68h]
0x1800f5fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5fc7  lea     r13, [r14+60h]
0x1800f5fcb  mov     [rbp+var_28], rax
0x1800f5fcf  mov     rcx, [r13+30h]
0x1800f5fd3  mov     r15, rax
0x1800f5fd6  mov     rdx, [r13+18h]
0x1800f5fda  and     rcx, rax
0x1800f5fdd  add     rcx, rcx
0x1800f5fe0  mov     [rbp+arg_10], r13
0x1800f5fe4  mov     rbx, [rdx+rcx*8+8]
0x1800f5fe9  cmp     rbx, [r13+8]
0x1800f5fed  jz      short loc_1800F600C
0x1800f5fef  mov     r12, [rdx+rcx*8]
0x1800f5ff3  cmp     r15, [rbx+10h]
0x1800f5ff7  jz      loc_1800F6350
0x1800f5ffd  cmp     rbx, r12
0x1800f6000  jz      short loc_1800F6008
0x1800f6002  mov     rbx, [rbx+8]
0x1800f6006  jmp     short loc_1800F5FF3
0x1800f6008  mov     r12, [rbp+arg_8]
0x1800f600c  xor     ebx, ebx
0x1800f600e  test    rbx, rbx
0x1800f6011  jz      loc_1800F637A
0x1800f6017  cmp     rbx, [r14+68h]
0x1800f601b  jz      loc_1800F61D5
0x1800f6021  mov     rbx, [rbx+20h]
0x1800f6025  mov     r13b, 1
0x1800f6028  test    rbx, rbx
0x1800f602b  jz      short loc_1800F603E
0x1800f602d  mov     rax, [rbx]
0x1800f6030  mov     rcx, rbx
0x1800f6033  mov     rax, [rax]
0x1800f6036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f603b  mov     rdi, rbx
0x1800f603e  mov     rdx, rdi; struct CEffectCompilationTask *
0x1800f6041  mov     rcx, r14; this
0x1800f6044  call    ?TryReviveDeadTask@CEffectCompilationService@@AEAAXPEBVCEffectCompilationTask@@@Z; CEffectCompilationService::TryReviveDeadTask(CEffectCompilationTask const *)
0x1800f6049  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1800f6050  jnz     loc_1800F6236
0x1800f6056  mov     rdx, r12; struct CCompiledEffectTemplate *
0x1800f6059  mov     rcx, rdi; this
0x1800f605c  call    ?AddTemplate_RenderThread@CEffectCompilationTask@@AEAAJPEAVCCompiledEffectTemplate@@@Z; CEffectCompilationTask::AddTemplate_RenderThread(CCompiledEffectTemplate *)
0x1800f6061  mov     ebx, eax
0x1800f6063  test    eax, eax
0x1800f6065  js      loc_1800F6145
0x1800f606b  lea     r12, [r14+10h]
0x1800f606f  mov     rcx, r12; lpCriticalSection
0x1800f6072  call    cs:__imp_EnterCriticalSection
0x1800f6078  lea     r15, [r14+40h]
0x1800f607c  xor     edx, edx
0x1800f607e  mov     r8, [r15]
0x1800f6081  mov     ecx, [r15+18h]
0x1800f6085  cmp     edx, ecx
0x1800f6087  jnb     short loc_1800F6093
0x1800f6089  cmp     rdi, [r8+rdx*8]
0x1800f608d  jz      short loc_1800F60F1
0x1800f608f  inc     edx
0x1800f6091  jmp     short loc_1800F6085
0x1800f6093  lea     edx, [rcx+1]
0x1800f6096  mov     [rbp+pv], rdi
0x1800f609a  cmp     edx, ecx
0x1800f609c  jb      loc_1800F617D
0x1800f60a2  cmp     edx, [r15+14h]
0x1800f60a6  ja      loc_1800F63AF
0x1800f60ac  mov     [r8+rcx*8], rdi
0x1800f60b0  xor     esi, esi
0x1800f60b2  mov     [r15+18h], edx
0x1800f60b6  cmp     byte ptr [rdi+60h], 0
0x1800f60ba  jz      short loc_1800F60EF
0x1800f60bc  mov     r9, [r15]
0x1800f60bf  mov     ecx, [r14+58h]
0x1800f60c3  mov     r8d, [r14+0C8h]
0x1800f60ca  dec     ecx
0x1800f60cc  mov     edx, ecx
0x1800f60ce  mov     rcx, [r9+rcx*8]
0x1800f60d2  mov     rax, [r9+r8*8]
0x1800f60d6  mov     [r9+rdx*8], rax
0x1800f60da  mov     [r9+r8*8], rcx
0x1800f60de  inc     dword ptr [r14+0C8h]
0x1800f60e5  mov     rcx, [r14+38h]; hEvent
0x1800f60e9  call    cs:__imp_SetEvent
0x1800f60ef  mov     ebx, esi
0x1800f60f1  test    r12, r12
0x1800f60f4  jz      short loc_1800F60FF
0x1800f60f6  mov     rcx, r12; lpCriticalSection
0x1800f60f9  call    cs:__imp_LeaveCriticalSection
0x1800f60ff  test    r13b, r13b
0x1800f6102  jnz     short loc_1800F610E
0x1800f6104  mov     rcx, [rdi+40h]; pwk
0x1800f6108  call    cs:__imp_SubmitThreadpoolWork
0x1800f610e  mov     rcx, [rbp+arg_18]
0x1800f6112  mov     rax, rdi
0x1800f6115  xor     edi, edi
0x1800f6117  mov     [rcx], rax
0x1800f611a  test    ebx, ebx
0x1800f611c  js      short loc_1800F6166
0x1800f611e  test    rdi, rdi
0x1800f6121  jz      short loc_1800F6132
0x1800f6123  mov     rax, [rdi]
0x1800f6126  mov     rcx, rdi
0x1800f6129  mov     rax, [rax+8]
0x1800f612d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6132  mov     eax, ebx
0x1800f6134  add     rsp, 68h
0x1800f6138  pop     r15
0x1800f613a  pop     r14
0x1800f613c  pop     r13
0x1800f613e  pop     r12
0x1800f6140  pop     rdi
0x1800f6141  pop     rsi
0x1800f6142  pop     rbx
0x1800f6143  pop     rbp
0x1800f6144  retn
0x1800f6145  xor     edx, edx; int *
0x1800f6147  mov     [rsp+68h+var_40], 0; void *
0x1800f6150  mov     r9d, eax; int
0x1800f6153  mov     [rsp+68h+var_48], 94h; unsigned int
0x1800f615b  xor     r8d, r8d; unsigned int
0x1800f615e  lea     ecx, [rdx+14h]; unsigned int
0x1800f6161  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f6166  mov     r13, [rbp+arg_10]
0x1800f616a  test    rdi, rdi
0x1800f616d  jz      short loc_1800F6132
0x1800f616f  lea     rdx, [rbp+var_28]
0x1800f6173  mov     rcx, r13
0x1800f6176  call    ??$_Erase@UEffectDescriptionKey@@@?$_Hash@V?$_Umap_traits@UEffectDescriptionKey@@PEAVCEffectCompilationTask@@V?$_Uhash_compare@UEffectDescriptionKey@@U?$hash@UEffectDescriptionKey@@@std@@U?$equal_to@UEffectDescriptionKey@@@3@@std@@V?$allocator@U?$pair@$$CBUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@std@@@4@$0A@@std@@@std@@AEAA_KAEBUEffectDescriptionKey@@@Z; std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::_Erase<EffectDescriptionKey>(EffectDescriptionKey const &)
0x1800f617b  jmp     short loc_1800F611E
0x1800f617d  mov     ebx, 80070216h
0x1800f6182  mov     eax, 0B7h
0x1800f6187  mov     esi, ebx
0x1800f6189  mov     r9d, ebx; int
0x1800f618c  xor     ecx, ecx
0x1800f618e  xor     edx, edx; int *
0x1800f6190  mov     [rsp+68h+var_40], rcx; void *
0x1800f6195  xor     r8d, r8d; unsigned int
0x1800f6198  mov     [rsp+68h+var_48], eax; unsigned int
0x1800f619c  lea     ecx, [rdx+14h]; unsigned int
0x1800f619f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f61a4  xor     edx, edx; int *
0x1800f61a6  mov     [rsp+68h+var_40], 0; void *
0x1800f61af  mov     r9d, esi; int
0x1800f61b2  mov     [rsp+68h+var_48], 9Ch; unsigned int
0x1800f61ba  xor     r8d, r8d; unsigned int
0x1800f61bd  lea     ecx, [rdx+14h]; unsigned int
0x1800f61c0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f61c5  test    r12, r12
0x1800f61c8  jz      short loc_1800F6166
0x1800f61ca  mov     rcx, r12; lpCriticalSection
0x1800f61cd  call    cs:__imp_LeaveCriticalSection
0x1800f61d3  jmp     short loc_1800F6166
0x1800f61d5  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800f61da  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x1800f61df  test    rax, rax
0x1800f61e2  jz      loc_1800F6383
0x1800f61e8  mov     r8, rsi; struct Windows::UI::Composition::IEffectDescription *
0x1800f61eb  mov     rdx, r14; struct CEffectCompilationService *
0x1800f61ee  mov     rcx, rax; this
0x1800f61f1  call    ??0CEffectCompilationTask@@AEAA@PEAVCEffectCompilationService@@PEAUIEffectDescription@Composition@UI@Windows@@@Z; CEffectCompilationTask::CEffectCompilationTask(CEffectCompilationService *,Windows::UI::Composition::IEffectDescription *)
0x1800f61f6  mov     rdx, rax
0x1800f61f9  lea     rcx, [rbp+pv]
0x1800f61fd  call    ??4?$ComPtr@VCManipulationContext@@@WRL@Microsoft@@QEAAAEAV012@PEAVCManipulationContext@@@Z; Microsoft::WRL::ComPtr<CManipulationContext>::operator=(CManipulationContext *)
0x1800f6202  mov     rdi, [rbp+pv]
0x1800f6206  test    rdi, rdi
0x1800f6209  jz      loc_1800F630D
0x1800f620f  cmp     cs:?EnableEffectCaching@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, 0; details::CRegistryKey<bool,bool> const CCommonRegistryData::EnableEffectCaching
0x1800f6216  jnz     loc_1800F6392
0x1800f621c  mov     rcx, rdi; pv
0x1800f621f  call    ?Initialize@CEffectCompilationTask@@AEAAJXZ; CEffectCompilationTask::Initialize(void)
0x1800f6224  mov     ebx, eax
0x1800f6226  test    eax, eax
0x1800f6228  js      loc_1800F62E7
0x1800f622e  xor     r13b, r13b
0x1800f6231  jmp     loc_1800F6049
0x1800f6236  mov     rax, [rsi]
0x1800f6239  lea     rcx, [rbp+pv]
0x1800f623d  mov     [rbp+pv], 0
0x1800f6245  mov     rbx, [rax+58h]
0x1800f6249  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x1800f624e  lea     rdx, [rbp+pv]
0x1800f6252  mov     rcx, rsi
0x1800f6255  mov     rax, rbx
0x1800f6258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f625d  test    eax, eax
0x1800f625f  jns     loc_1800F6338
0x1800f6265  lea     r15, aNull_1; "null"
0x1800f626c  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1800f6273  jnz     short loc_1800F629B
0x1800f6275  mov     rcx, [rbp+pv]
0x1800f6279  test    rcx, rcx
0x1800f627c  jz      loc_1800F6056
0x1800f6282  mov     [rbp+pv], 0
0x1800f628a  mov     rax, [rcx]
0x1800f628d  mov     rax, [rax+8]
0x1800f6291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6296  jmp     loc_1800F6056
0x1800f629b  mov     rax, [rsi]
0x1800f629e  mov     rcx, rsi
0x1800f62a1  mov     rax, [rax+20h]
0x1800f62a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f62aa  mov     rcx, [rsi]
0x1800f62ad  mov     ebx, eax
0x1800f62af  mov     rax, [rcx+50h]
0x1800f62b3  mov     rcx, rsi
0x1800f62b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f62bb  mov     rcx, r12; this
0x1800f62be  mov     edx, eax
0x1800f62c0  call    ?GetChannelCallbackId@CNotificationResource@@IEBAIXZ; CNotificationResource::GetChannelCallbackId(void)
0x1800f62c5  movzx   ecx, r13b
0x1800f62c9  mov     r9d, eax
0x1800f62cc  mov     [rsp+68h+var_30], ecx
0x1800f62d0  mov     r8, rdi
0x1800f62d3  mov     [rsp+68h+var_38], ebx
0x1800f62d7  mov     dword ptr [rsp+68h+var_40], edx
0x1800f62db  mov     qword ptr [rsp+68h+var_48], r15
0x1800f62e0  call    McTemplateU0pdsddt_EventWriteTransfer
0x1800f62e5  jmp     short loc_1800F6275
0x1800f62e7  xor     edx, edx; int *
0x1800f62e9  mov     [rsp+68h+var_40], 0; void *
0x1800f62f2  mov     r9d, eax; int
0x1800f62f5  mov     [rsp+68h+var_48], 77h ; 'w'; unsigned int
0x1800f62fd  xor     r8d, r8d; unsigned int
0x1800f6300  lea     ecx, [rdx+14h]; unsigned int
0x1800f6303  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f6308  jmp     loc_1800F616A
0x1800f630d  xor     edx, edx; int *
0x1800f630f  mov     [rsp+68h+var_40], 0; void *
0x1800f6318  mov     ebx, 8007000Eh
0x1800f631d  mov     [rsp+68h+var_48], 70h ; 'p'; unsigned int
0x1800f6325  mov     r9d, ebx; int
0x1800f6328  xor     r8d, r8d; unsigned int
0x1800f632b  lea     ecx, [rdx+14h]; unsigned int
0x1800f632e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f6333  jmp     loc_1800F611E
0x1800f6338  mov     rcx, [rbp+pv]
0x1800f633c  mov     rax, [rcx]
0x1800f633f  mov     rax, [rax+10h]
0x1800f6343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6348  mov     r15, rax
0x1800f634b  jmp     loc_1800F626C
0x1800f6350  mov     rax, [rsi]
0x1800f6353  mov     rcx, rsi
0x1800f6356  mov     rdx, [rbx+18h]
0x1800f635a  mov     rax, [rax+60h]
0x1800f635e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6363  test    al, al
0x1800f6365  jz      short loc_1800F6370
0x1800f6367  mov     r12, [rbp+arg_8]
0x1800f636b  jmp     loc_1800F600E
0x1800f6370  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800f6375  jmp     loc_1800F5FFD
0x1800f637a  mov     rbx, [r13+8]
0x1800f637e  jmp     loc_1800F6017
0x1800f6383  mov     rdx, [rbp+40h]; void *
0x1800f6387  mov     ecx, 8007000Eh; int
0x1800f638c  call    ModuleFailFastForHRESULT
0x1800f6392  lea     r9, [rbp+pv]
0x1800f6396  mov     [rbp+pv], rdi
0x1800f639a  lea     r8, [rbp+var_28]
0x1800f639e  mov     rcx, r13
0x1800f63a1  lea     rdx, [rbp+var_18]
0x1800f63a5  call    ??$emplace@AEAUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@?$_Hash@V?$_Umap_traits@UEffectDescriptionKey@@PEAVCEffectCompilationTask@@V?$_Uhash_compare@UEffectDescriptionKey@@U?$hash@UEffectDescriptionKey@@@std@@U?$equal_to@UEffectDescriptionKey@@@3@@std@@V?$allocator@U?$pair@$$CBUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@std@@@std@@@std@@@std@@_N@1@AEAUEffectDescriptionKey@@$$QEAPEAVCEffectCompilationTask@@@Z; std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::emplace<EffectDescriptionKey &,CEffectCompilationTask *>(EffectDescriptionKey &,CEffectCompilationTask * &&)
0x1800f63aa  jmp     loc_1800F621C
0x1800f63af  mov     edx, 8
0x1800f63b4  lea     r9, [rbp+pv]
0x1800f63b8  mov     rcx, r15
0x1800f63bb  lea     r8d, [rdx-7]
0x1800f63bf  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800f63c4  mov     esi, eax
0x1800f63c6  test    eax, eax
0x1800f63c8  jns     loc_1800F60B6
0x1800f63ce  mov     ebx, eax
0x1800f63d0  mov     r9d, eax
0x1800f63d3  mov     eax, 0C2h
0x1800f63d8  jmp     loc_1800F618C
```
