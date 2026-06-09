# CComposition::~CComposition(void)

- ea: `0x180215134`
- end: `0x180215634`
- name: `??1CComposition@@MEAA@XZ`
- size: `1280`
- prototype: `void __fastcall(CComposition *__hidden this)`
- caller_count: `2`
- callee_count: `44`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180230af0`
- `0x1802364bc`

## callees

- `0x18001c914`
- `0x180025130`
- `0x180025650`
- `0x1800264c0`
- `0x180026eac`
- `0x18002be34`
- `0x180040930`
- `0x180041f20`
- `0x180051680`
- `0x1800667e0`
- `0x180086120`
- `0x1800c11a0`
- `0x1800c29f0`
- `0x1800d0a3c`
- `0x1800d32c0`
- `0x180134900`
- `0x180149228`
- `0x18015a97c`
- `0x1801868ec`
- `0x1801879bc`
- `0x180187eb8`
- `0x1801a3714`
- `0x1801ea568`
- `0x180202b80`
- `0x180215134`
- `0x18021563c`
- `0x18021565c`
- `0x1802157ac`
- `0x180215810`
- `0x180228880`
- `0x18022ffb4`
- `0x180230540`
- `0x1802305cc`
- `0x1802305e8`
- `0x180230604`
- `0x180230674`
- `0x1802306a8`
- `0x1802306cc`
- `0x180230740`
- `0x1802309e4`
- `0x180230a14`
- `0x180231c30`
- `0x1802329c0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18021551b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802155e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18021551b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802155e0`

## string_xrefs

- `0x180215328`: `onecoreuap\windows\dwm\dwmcore\engine\composition.cpp`

## pseudocode

```c
void __fastcall CComposition::~CComposition(CComposition *this)
{
  unsigned int i; // edi
  unsigned int v3; // edi
  unsigned int v4; // esi
  char *v5; // r15
  __int64 v6; // rdx
  CursorVisualData *v7; // rcx
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  void *v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // rbp
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  CursorVisualData *v21; // rcx
  int v22; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v24; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = &CComposition::`vftable';
  CComposition::FlushRoundTripRequests(this);
  for ( i = 0; i < *((_DWORD *)this + 230); ++i )
    CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(*(_QWORD *)(*((_QWORD *)this + 112) + 8LL * i));
  *((_DWORD *)this + 230) = 0;
  v3 = 0;
  v4 = *((_DWORD *)this + 214);
  if ( v4 )
  {
    do
    {
      v5 = (char *)this + 832;
      v24 = *(_QWORD *)(*((_QWORD *)this + 104) + 8LL * v3);
      ReleaseInterface<CProcessAttribution>(&v24);
      ++v3;
    }
    while ( v3 < v4 );
  }
  else
  {
    v5 = (char *)this + 832;
  }
  DynArray<CChannelContext *,1>::Reset(v5, 1);
  CComposition::ReleaseNotificationChannels(this);
  v6 = *((_QWORD *)this + 83);
  *((_QWORD *)this + 83) = 0;
  if ( v6 )
    std::default_delete<CMeshCacheManager>::operator()();
  v7 = (CursorVisualData *)*((_QWORD *)this + 766);
  if ( v7 != *((CursorVisualData **)this + 767) )
  {
    std::_Destroy_range<std::allocator<CursorVisualData>>(v7);
    *((_QWORD *)this + 767) = *((_QWORD *)this + 766);
  }
  v8 = (_QWORD *)((char *)this + 5944);
  std::vector<wil::com_ptr_t<CCompositionSurfaceInfo,wil::err_returncode_policy>>::clear((char *)this + 5944);
  CComposition::UnmapDeferredSharedSectionViews(this);
  v9 = *((_QWORD *)this + 90);
  *((_QWORD *)this + 90) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = (void *)*((_QWORD *)this + 77);
  if ( v10 )
  {
    CRenderTargetManager::~CRenderTargetManager(*((CRenderTargetManager **)this + 77));
    operator delete(v10, 0x2F8u);
  }
  v11 = *((_QWORD *)this + 102);
  if ( v11 )
    CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(v11);
  v12 = *((_QWORD *)this + 79);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = *((_QWORD *)this + 80);
  if ( v13 )
  {
    *((_QWORD *)this + 80) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  while ( *((_QWORD *)this + 811) != *((_QWORD *)this + 812) )
  {
    v14 = *((_QWORD *)this + 813);
    *((_QWORD *)this + 813) = 0;
    v15 = *((_QWORD *)this + 812);
    *((_QWORD *)this + 812) = 0;
    v16 = *((_QWORD *)this + 811);
    *((_QWORD *)this + 811) = 0;
    if ( v16 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(v16, v15);
      std::_Deallocate<16>(v16, (v14 - v16) & 0xFFFFFFFFFFFFFFF8uLL);
    }
  }
  if ( CComposition::HasDelayDeleteResources(this) )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\composition.cpp",
      (const char *)0x8007029CLL,
      v22);
  v17 = *((_QWORD *)this + 78);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  v18 = *((_QWORD *)this + 81);
  if ( v18 )
    CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(v18);
  v19 = *((_QWORD *)this + 84);
  *((_QWORD *)this + 84) = 0;
  if ( v19 )
    std::default_delete<CSceneResourceManager>::operator()();
  CThreadContext::DestroyObjectCaches();
  g_pFrameId = 0;
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>((char *)this + 6512);
  v20 = *((_QWORD *)this + 811);
  if ( v20 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(
      v20,
      *((_QWORD *)this + 812));
    std::_Deallocate<16>(
      *((_QWORD *)this + 811),
      (*((_QWORD *)this + 813) - *((_QWORD *)this + 811)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 811) = 0;
    *((_QWORD *)this + 812) = 0;
    *((_QWORD *)this + 813) = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 6440);
  wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 6432);
  wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 6424);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 6416);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 6400);
  if ( *((_QWORD *)this + 799) )
  {
    *((_QWORD *)this + 799) = 0;
    CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease();
  }
  operator delete(*((void **)this + 783));
  std::_Hash<std::_Umap_traits<CVisual *,CPreWalkVisual,std::_Uhash_compare<CVisual *,std::hash<CVisual *>,std::equal_to<CVisual *>>,std::allocator<std::pair<CVisual * const,CPreWalkVisual>>,0>>::~_Hash<std::_Umap_traits<CVisual *,CPreWalkVisual,std::_Uhash_compare<CVisual *,std::hash<CVisual *>,std::equal_to<CVisual *>>,std::allocator<std::pair<CVisual * const,CPreWalkVisual>>,0>>((char *)this + 6192);
  wil::com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>::~com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>((char *)this + 6184);
  wil::com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>::~com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>((char *)this + 6176);
  std::vector<CLight *>::_Tidy((char *)this + 6152);
  v21 = (CursorVisualData *)*((_QWORD *)this + 766);
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<CursorVisualData>>(v21);
    std::_Deallocate<16>(
      *((_QWORD *)this + 766),
      (*((_QWORD *)this + 768) - *((_QWORD *)this + 766)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 766) = 0;
    *((_QWORD *)this + 767) = 0;
    *((_QWORD *)this + 768) = 0;
  }
  DynArrayImpl<1>::~DynArrayImpl<1>((char *)this + 5968);
  if ( *v8 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(
      *v8,
      *((_QWORD *)this + 744));
    std::_Deallocate<16>(*v8, (*((_QWORD *)this + 745) - *((_QWORD *)this + 743)) & 0xFFFFFFFFFFFFFFF8uLL);
    *v8 = 0;
    *((_QWORD *)this + 744) = 0;
    *((_QWORD *)this + 745) = 0;
  }
  DynArrayImpl<1>::~DynArrayImpl<1>((char *)this + 5904);
  DynArrayImpl<1>::~DynArrayImpl<1>((char *)this + 5872);
  detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::~vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>((char *)this + 5784);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5712));
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>((char *)this + 5688);
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>((char *)this + 5680);
  CDisplayDebugFrameCounter::~CDisplayDebugFrameCounter((CComposition *)((char *)this + 5632));
  DynArrayImpl<1>::~DynArrayImpl<1>((char *)this + 960);
  DynArrayImpl<1>::~DynArrayImpl<1>((char *)this + 928);
  DynArrayImpl<1>::~DynArrayImpl<1>((char *)this + 896);
  DynArrayImpl<1>::~DynArrayImpl<1>(v5);
  CMmcssTask::~CMmcssTask((CComposition *)((char *)this + 728));
  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>((char *)this + 720);
  wil::com_ptr_t<IBitmapResource,wil::err_returncode_policy>::~com_ptr_t<IBitmapResource,wil::err_returncode_policy>((char *)this + 712);
  wil::com_ptr_t<IBitmapResource,wil::err_returncode_policy>::~com_ptr_t<IBitmapResource,wil::err_returncode_policy>((char *)this + 704);
  std::unique_ptr<CSceneResourceManager>::~unique_ptr<CSceneResourceManager>((char *)this + 672);
  std::unique_ptr<CMeshCacheManager>::~unique_ptr<CMeshCacheManager>((char *)this + 664);
  std::unique_ptr<CSuperWetInkManager>::~unique_ptr<CSuperWetInkManager>((char *)this + 656);
  std::unique_ptr<CPreComputeContext>::~unique_ptr<CPreComputeContext>((char *)this + 608);
  detail::vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>::~vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>((char *)this + 552);
  detail::vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>::~vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>((char *)this + 400);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  detail::vector_facade<CResponseItemBase *,detail::buffer_impl<CResponseItemBase *,2,1,detail::liberal_expansion_policy>>::clear((char *)this + 320);
  detail::expandable_buffer_base<COverlayContext *,2>::~expandable_buffer_base<COverlayContext *,2>();
  Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef((__int64 *)this + 39);
  Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef((__int64 *)this + 38);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 240);
  detail::vector_facade<enum IRenderTarget::Type,detail::buffer_impl<enum IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>::~vector_facade<enum IRenderTarget::Type,detail::buffer_impl<enum IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>((char *)this + 24);
}

```

## disassembly

```asm
0x180215134  push    rbx
0x180215136  push    rbp
0x180215137  push    rsi
0x180215138  push    rdi
0x180215139  push    r12
0x18021513b  push    r13
0x18021513d  push    r14
0x18021513f  push    r15
0x180215141  sub     rsp, 28h
0x180215145  lea     rax, ??_7CComposition@@6B@; const CComposition::`vftable'
0x18021514c  mov     rbx, rcx
0x18021514f  mov     [rcx], rax
0x180215152  call    ?FlushRoundTripRequests@CComposition@@AEAAXXZ; CComposition::FlushRoundTripRequests(void)
0x180215157  xor     ebp, ebp
0x180215159  lea     r14, [rbx+380h]
0x180215160  mov     edi, ebp
0x180215162  cmp     [rbx+398h], ebp
0x180215168  jbe     short loc_180215182
0x18021516a  mov     rcx, [r14]
0x18021516d  mov     eax, edi
0x18021516f  mov     rcx, [rcx+rax*8]
0x180215173  call    ?Release@?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@UEAAKXZ; CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(void)
0x180215178  inc     edi
0x18021517a  cmp     edi, [rbx+398h]
0x180215180  jb      short loc_18021516A
0x180215182  mov     [r14+18h], ebp
0x180215186  mov     edi, ebp
0x180215188  mov     esi, [rbx+358h]
0x18021518e  test    esi, esi
0x180215190  jz      short loc_1802151B9
0x180215192  lea     r15, [rbx+340h]
0x180215199  mov     ecx, edi
0x18021519b  mov     rax, [r15]
0x18021519e  mov     rcx, [rax+rcx*8]
0x1802151a2  mov     [rsp+68h+arg_0], rcx
0x1802151a7  lea     rcx, [rsp+68h+arg_0]
0x1802151ac  call    ??$ReleaseInterface@VCProcessAttribution@@@@YAXAEAPEAVCProcessAttribution@@@Z; ReleaseInterface<CProcessAttribution>(CProcessAttribution * &)
0x1802151b1  inc     edi
0x1802151b3  cmp     edi, esi
0x1802151b5  jb      short loc_180215192
0x1802151b7  jmp     short loc_1802151C0
0x1802151b9  lea     r15, [rbx+340h]
0x1802151c0  mov     edx, 1
0x1802151c5  mov     rcx, r15
0x1802151c8  call    ?Reset@?$DynArray@PEAVCChannelContext@@$00@@QEAAXH@Z; DynArray<CChannelContext *,1>::Reset(int)
0x1802151cd  mov     rcx, rbx; this
0x1802151d0  call    ?ReleaseNotificationChannels@CComposition@@AEAAXXZ; CComposition::ReleaseNotificationChannels(void)
0x1802151d5  lea     r12, [rbx+298h]
0x1802151dc  mov     rdx, [r12]
0x1802151e0  mov     [r12], rbp
0x1802151e4  test    rdx, rdx
0x1802151e7  jz      short loc_1802151EE
0x1802151e9  call    ??R?$default_delete@VCMeshCacheManager@@@std@@QEBAXPEAVCMeshCacheManager@@@Z; std::default_delete<CMeshCacheManager>::operator()(CMeshCacheManager *)
0x1802151ee  mov     rdx, [rbx+17F8h]
0x1802151f5  mov     rcx, [rbx+17F0h]
0x1802151fc  cmp     rcx, rdx
0x1802151ff  jz      short loc_180215214
0x180215201  call    ??$_Destroy_range@V?$allocator@UCursorVisualData@@@std@@@std@@YAXPEAUCursorVisualData@@QEAU1@AEAV?$allocator@UCursorVisualData@@@0@@Z; std::_Destroy_range<std::allocator<CursorVisualData>>(CursorVisualData *,CursorVisualData * const,std::allocator<CursorVisualData> &)
0x180215206  mov     rax, [rbx+17F0h]
0x18021520d  mov     [rbx+17F8h], rax
0x180215214  lea     rdi, [rbx+1738h]
0x18021521b  mov     rcx, rdi
0x18021521e  call    ?clear@?$vector@V?$com_ptr_t@VCCompositionSurfaceInfo@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCCompositionSurfaceInfo@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::vector<wil::com_ptr_t<CCompositionSurfaceInfo,wil::err_returncode_policy>>::clear(void)
0x180215223  mov     rcx, rbx; this
0x180215226  call    ?UnmapDeferredSharedSectionViews@CComposition@@IEAAXXZ; CComposition::UnmapDeferredSharedSectionViews(void)
0x18021522b  lea     r13, [rbx+2D0h]
0x180215232  mov     rcx, [r13+0]
0x180215236  mov     [r13+0], rbp
0x18021523a  test    rcx, rcx
0x18021523d  jz      short loc_18021524B
0x18021523f  mov     rax, [rcx]
0x180215242  mov     rax, [rax+10h]
0x180215246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021524b  mov     rsi, [rbx+268h]
0x180215252  test    rsi, rsi
0x180215255  jz      short loc_18021526C
0x180215257  mov     rcx, rsi; this
0x18021525a  call    ??1CRenderTargetManager@@QEAA@XZ; CRenderTargetManager::~CRenderTargetManager(void)
0x18021525f  mov     edx, 2F8h; unsigned __int64
0x180215264  mov     rcx, rsi; void *
0x180215267  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18021526c  mov     rcx, [rbx+330h]
0x180215273  test    rcx, rcx
0x180215276  jz      short loc_18021527D
0x180215278  call    ?Release@?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@UEAAKXZ; CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(void)
0x18021527d  mov     rcx, [rbx+278h]
0x180215284  test    rcx, rcx
0x180215287  jz      short loc_180215295
0x180215289  mov     rax, [rcx]
0x18021528c  mov     rax, [rax+10h]
0x180215290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215295  mov     rcx, [rbx+280h]
0x18021529c  test    rcx, rcx
0x18021529f  jz      short loc_1802152B8
0x1802152a1  mov     [rbx+280h], rbp
0x1802152a8  mov     rax, [rcx]
0x1802152ab  mov     rax, [rax+10h]
0x1802152af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802152b4  jmp     short loc_1802152B8
0x1802152b6  xor     ebp, ebp
0x1802152b8  mov     rax, [rbx+1960h]
0x1802152bf  cmp     [rbx+1958h], rax
0x1802152c6  jz      short loc_180215317
0x1802152c8  mov     rsi, [rbx+1968h]
0x1802152cf  mov     [rbx+1968h], rbp
0x1802152d6  mov     rdx, [rbx+1960h]
0x1802152dd  mov     [rbx+1960h], rbp
0x1802152e4  mov     rbp, [rbx+1958h]
0x1802152eb  mov     qword ptr [rbx+1958h], 0
0x1802152f6  test    rbp, rbp
0x1802152f9  jz      short loc_1802152B6
0x1802152fb  mov     rcx, rbp
0x1802152fe  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x180215303  sub     rsi, rbp
0x180215306  mov     rcx, rbp
0x180215309  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18021530d  mov     rdx, rsi
0x180215310  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180215315  jmp     short loc_1802152B6
0x180215317  mov     rcx, rbx; this
0x18021531a  call    ?HasDelayDeleteResources@CComposition@@QEBA_NXZ; CComposition::HasDelayDeleteResources(void)
0x18021531f  test    al, al
0x180215321  jz      short loc_18021533F
0x180215323  mov     rcx, [rsp+68h]; this
0x180215328  lea     r8, aOnecoreuapWind_180; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18021532f  mov     r9d, 8007029Ch; char *
0x180215335  mov     edx, 0F9h; void *
0x18021533a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18021533f  mov     rcx, [rbx+270h]
0x180215346  test    rcx, rcx
0x180215349  jz      short loc_180215357
0x18021534b  mov     rax, [rcx]
0x18021534e  mov     rax, [rax+8]
0x180215352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215357  mov     rcx, [rbx+288h]
0x18021535e  test    rcx, rcx
0x180215361  jz      short loc_180215368
0x180215363  call    ?Release@?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@UEAAKXZ; CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(void)
0x180215368  lea     rsi, [rbx+2A0h]
0x18021536f  mov     rdx, [rsi]
0x180215372  mov     [rsi], rbp
0x180215375  test    rdx, rdx
0x180215378  jz      short loc_18021537F
0x18021537a  call    ??R?$default_delete@VCSceneResourceManager@@@std@@QEBAXPEAVCSceneResourceManager@@@Z; std::default_delete<CSceneResourceManager>::operator()(CSceneResourceManager *)
0x18021537f  call    ?DestroyObjectCaches@CThreadContext@@SAXXZ; CThreadContext::DestroyObjectCaches(void)
0x180215384  lea     rcx, [rbx+1970h]
0x18021538b  mov     cs:?g_pFrameId@@3PEA_KEA, rbp; unsigned __int64 * g_pFrameId
0x180215392  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180215397  mov     rcx, [rbx+1958h]
0x18021539e  test    rcx, rcx
0x1802153a1  jz      short loc_1802153DE
0x1802153a3  mov     rdx, [rbx+1960h]
0x1802153aa  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x1802153af  mov     rcx, [rbx+1958h]
0x1802153b6  mov     rdx, [rbx+1968h]
0x1802153bd  sub     rdx, rcx
0x1802153c0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802153c4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802153c9  mov     [rbx+1958h], rbp
0x1802153d0  mov     [rbx+1960h], rbp
0x1802153d7  mov     [rbx+1968h], rbp
0x1802153de  lea     rcx, [rbx+1928h]
0x1802153e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802153ea  lea     rcx, [rbx+1920h]
0x1802153f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802153f6  lea     rcx, [rbx+1918h]
0x1802153fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180215402  lea     rcx, [rbx+1910h]
0x180215409  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18021540e  lea     rcx, [rbx+1900h]
0x180215415  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18021541a  mov     rcx, [rbx+18F8h]
0x180215421  test    rcx, rcx
0x180215424  jz      short loc_180215432
0x180215426  mov     [rbx+18F8h], rbp
0x18021542d  call    ?InternalRelease@?$CMILRefCountBaseT@UIUnknown@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease(void)
0x180215432  mov     rcx, [rbx+1878h]; void *
0x180215439  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18021543e  lea     rcx, [rbx+1830h]
0x180215445  call    ??1?$_Hash@V?$_Umap_traits@PEAVCVisual@@VCPreWalkVisual@@V?$_Uhash_compare@PEAVCVisual@@U?$hash@PEAVCVisual@@@std@@U?$equal_to@PEAVCVisual@@@3@@std@@V?$allocator@U?$pair@QEAVCVisual@@VCPreWalkVisual@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<CVisual *,CPreWalkVisual,std::_Uhash_compare<CVisual *,std::hash<CVisual *>,std::equal_to<CVisual *>>,std::allocator<std::pair<CVisual * const,CPreWalkVisual>>,0>>::~_Hash<std::_Umap_traits<CVisual *,CPreWalkVisual,std::_Uhash_compare<CVisual *,std::hash<CVisual *>,std::equal_to<CVisual *>>,std::allocator<std::pair<CVisual * const,CPreWalkVisual>>,0>>(void)
0x18021544a  lea     rcx, [rbx+1828h]
0x180215451  call    ??1?$com_ptr_t@VCDDARenderTarget@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>::~com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>(void)
0x180215456  lea     rcx, [rbx+1820h]
0x18021545d  call    ??1?$com_ptr_t@VCDDARenderTarget@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>::~com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>(void)
0x180215462  lea     rcx, [rbx+1808h]
0x180215469  call    ?_Tidy@?$vector@PEAVCLight@@V?$allocator@PEAVCLight@@@std@@@std@@AEAAXXZ; std::vector<CLight *>::_Tidy(void)
0x18021546e  mov     rcx, [rbx+17F0h]
0x180215475  test    rcx, rcx
0x180215478  jz      short loc_1802154B5
0x18021547a  mov     rdx, [rbx+17F8h]
0x180215481  call    ??$_Destroy_range@V?$allocator@UCursorVisualData@@@std@@@std@@YAXPEAUCursorVisualData@@QEAU1@AEAV?$allocator@UCursorVisualData@@@0@@Z; std::_Destroy_range<std::allocator<CursorVisualData>>(CursorVisualData *,CursorVisualData * const,std::allocator<CursorVisualData> &)
0x180215486  mov     rcx, [rbx+17F0h]
0x18021548d  mov     rdx, [rbx+1800h]
0x180215494  sub     rdx, rcx
0x180215497  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18021549b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802154a0  mov     [rbx+17F0h], rbp
0x1802154a7  mov     [rbx+17F8h], rbp
0x1802154ae  mov     [rbx+1800h], rbp
0x1802154b5  lea     rcx, [rbx+1750h]
0x1802154bc  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x1802154c1  mov     rcx, [rdi]
0x1802154c4  test    rcx, rcx
0x1802154c7  jz      short loc_1802154F0
0x1802154c9  mov     rdx, [rdi+8]
0x1802154cd  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x1802154d2  mov     rdx, [rdi+10h]
0x1802154d6  sub     rdx, [rdi]
0x1802154d9  mov     rcx, [rdi]
0x1802154dc  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802154e0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802154e5  mov     [rdi], rbp
0x1802154e8  mov     [rdi+8], rbp
0x1802154ec  mov     [rdi+10h], rbp
0x1802154f0  lea     rcx, [rbx+1710h]
0x1802154f7  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x1802154fc  lea     rcx, [rbx+16F0h]
0x180215503  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180215508  lea     rcx, [rbx+1698h]
0x18021550f  call    ??1?$vector_facade@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$buffer_impl@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@$07$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::~vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>(void)
0x180215514  lea     rcx, [rbx+1650h]; lpCriticalSection
0x18021551b  call    cs:__imp_DeleteCriticalSection
0x180215521  lea     rcx, [rbx+1638h]
0x180215528  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18021552d  lea     rcx, [rbx+1630h]
0x180215534  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180215539  lea     rcx, [rbx+1600h]; this
0x180215540  call    ??1CDisplayDebugFrameCounter@@QEAA@XZ; CDisplayDebugFrameCounter::~CDisplayDebugFrameCounter(void)
0x180215545  lea     rcx, [rbx+3C0h]
0x18021554c  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180215551  lea     rcx, [rbx+3A0h]
0x180215558  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x18021555d  mov     rcx, r14
0x180215560  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180215565  mov     rcx, r15
0x180215568  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x18021556d  lea     rcx, [rbx+2D8h]; this
0x180215574  call    ??1CMmcssTask@@QEAA@XZ; CMmcssTask::~CMmcssTask(void)
0x180215579  mov     rcx, r13
0x18021557c  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180215581  lea     rcx, [rbx+2C8h]
0x180215588  call    ??1?$com_ptr_t@VIBitmapResource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBitmapResource,wil::err_returncode_policy>::~com_ptr_t<IBitmapResource,wil::err_returncode_policy>(void)
0x18021558d  lea     rcx, [rbx+2C0h]
0x180215594  call    ??1?$com_ptr_t@VIBitmapResource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBitmapResource,wil::err_returncode_policy>::~com_ptr_t<IBitmapResource,wil::err_returncode_policy>(void)
0x180215599  mov     rcx, rsi
0x18021559c  call    ??1?$unique_ptr@VCSceneResourceManager@@U?$default_delete@VCSceneResourceManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSceneResourceManager>::~unique_ptr<CSceneResourceManager>(void)
0x1802155a1  mov     rcx, r12
0x1802155a4  call    ??1?$unique_ptr@VCMeshCacheManager@@U?$default_delete@VCMeshCacheManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMeshCacheManager>::~unique_ptr<CMeshCacheManager>(void)
0x1802155a9  lea     rcx, [rbx+290h]
0x1802155b0  call    ??1?$unique_ptr@VCSuperWetInkManager@@U?$default_delete@VCSuperWetInkManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSuperWetInkManager>::~unique_ptr<CSuperWetInkManager>(void)
0x1802155b5  lea     rcx, [rbx+260h]
0x1802155bc  call    ??1?$unique_ptr@VCPreComputeContext@@U?$default_delete@VCPreComputeContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPreComputeContext>::~unique_ptr<CPreComputeContext>(void)
0x1802155c1  lea     rcx, [rbx+228h]
0x1802155c8  call    ??1?$vector_facade@V?$com_ptr_t@VCVisualTree@@Uerr_returncode_policy@wil@@@wil@@V?$buffer_impl@V?$com_ptr_t@VCVisualTree@@Uerr_returncode_policy@wil@@@wil@@$03$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>::~vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>(void)
0x1802155cd  lea     rcx, [rbx+190h]
0x1802155d4  call    ??1?$vector_facade@PEAVCVisualTree@@V?$buffer_impl@PEAVCVisualTree@@$0BA@$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>::~vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>(void)
0x1802155d9  lea     rcx, [rbx+168h]; lpCriticalSection
0x1802155e0  call    cs:__imp_DeleteCriticalSection
0x1802155e6  lea     rcx, [rbx+140h]
0x1802155ed  call    ?clear@?$vector_facade@PEAVCResponseItemBase@@V?$buffer_impl@PEAVCResponseItemBase@@$01$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAAXXZ; detail::vector_facade<CResponseItemBase *,detail::buffer_impl<CResponseItemBase *,2,1,detail::liberal_expansion_policy>>::clear(void)
0x1802155f2  call    ??1?$expandable_buffer_base@PEAVCOverlayContext@@$01@detail@@QEAA@XZ; detail::expandable_buffer_base<COverlayContext *,2>::~expandable_buffer_base<COverlayContext *,2>(void)
0x1802155f7  lea     rcx, [rbx+138h]
0x1802155fe  call    ?InternalAddRef@?$ComPtr@UIMessageCallSendHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef(void)
0x180215603  lea     rcx, [rbx+130h]
0x18021560a  call    ?InternalAddRef@?$ComPtr@UIMessageCallSendHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef(void)
0x18021560f  lea     rcx, [rbx+0F0h]
0x180215616  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18021561b  lea     rcx, [rbx+18h]
0x18021561f  add     rsp, 28h
0x180215623  pop     r15
0x180215625  pop     r14
0x180215627  pop     r13
0x180215629  pop     r12
0x18021562b  pop     rdi
0x18021562c  pop     rsi
0x18021562d  pop     rbp
0x18021562e  pop     rbx
0x18021562f  jmp     ??1?$vector_facade@W4Type@IRenderTarget@@V?$buffer_impl@W4Type@IRenderTarget@@$03$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<IRenderTarget::Type,detail::buffer_impl<IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>::~vector_facade<IRenderTarget::Type,detail::buffer_impl<IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>(void)
```
