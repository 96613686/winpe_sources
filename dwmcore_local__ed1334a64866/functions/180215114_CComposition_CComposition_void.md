# CComposition::~CComposition(void)

- ea: `0x180215114`
- end: `0x180215614`
- name: `??1CComposition@@MEAA@XZ`
- size: `1280`
- prototype: `void __fastcall(CComposition *__hidden this)`
- caller_count: `2`
- callee_count: `44`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180230ad0`
- `0x18023649c`

## callees

- `0x180009bf8`
- `0x18000a254`
- `0x18000a7f4`
- `0x18000abb8`
- `0x180015cf0`
- `0x180017040`
- `0x18001ce34`
- `0x180020010`
- `0x1800441f0`
- `0x18005d700`
- `0x180079f2c`
- `0x180098940`
- `0x18009ac80`
- `0x1800c5750`
- `0x1800d32ac`
- `0x1800d5b30`
- `0x180112fc0`
- `0x18014e7b8`
- `0x180184d4c`
- `0x180185d7c`
- `0x180186278`
- `0x1801a32a8`
- `0x1801ea868`
- `0x180202b60`
- `0x180215114`
- `0x18021561c`
- `0x18021563c`
- `0x18021578c`
- `0x1802157f0`
- `0x180228860`
- `0x18022ff94`
- `0x180230520`
- `0x1802305ac`
- `0x1802305c8`
- `0x1802305e4`
- `0x180230654`
- `0x180230688`
- `0x1802306ac`
- `0x180230720`
- `0x1802309c4`
- `0x1802309f4`
- `0x180231c10`
- `0x1802329a0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802154fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802155c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802154fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802155c0`

## string_xrefs

- `0x180215308`: `onecoreuap\windows\dwm\dwmcore\engine\composition.cpp`

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
  Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef((char *)this + 312);
  Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef((char *)this + 304);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 240);
  detail::vector_facade<enum IRenderTarget::Type,detail::buffer_impl<enum IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>::~vector_facade<enum IRenderTarget::Type,detail::buffer_impl<enum IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>((char *)this + 24);
}

```

## disassembly

```asm
0x180215114  push    rbx
0x180215116  push    rbp
0x180215117  push    rsi
0x180215118  push    rdi
0x180215119  push    r12
0x18021511b  push    r13
0x18021511d  push    r14
0x18021511f  push    r15
0x180215121  sub     rsp, 28h
0x180215125  lea     rax, ??_7CComposition@@6B@; const CComposition::`vftable'
0x18021512c  mov     rbx, rcx
0x18021512f  mov     [rcx], rax
0x180215132  call    ?FlushRoundTripRequests@CComposition@@AEAAXXZ; CComposition::FlushRoundTripRequests(void)
0x180215137  xor     ebp, ebp
0x180215139  lea     r14, [rbx+380h]
0x180215140  mov     edi, ebp
0x180215142  cmp     [rbx+398h], ebp
0x180215148  jbe     short loc_180215162
0x18021514a  mov     rcx, [r14]
0x18021514d  mov     eax, edi
0x18021514f  mov     rcx, [rcx+rax*8]
0x180215153  call    ?Release@?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@UEAAKXZ; CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(void)
0x180215158  inc     edi
0x18021515a  cmp     edi, [rbx+398h]
0x180215160  jb      short loc_18021514A
0x180215162  mov     [r14+18h], ebp
0x180215166  mov     edi, ebp
0x180215168  mov     esi, [rbx+358h]
0x18021516e  test    esi, esi
0x180215170  jz      short loc_180215199
0x180215172  lea     r15, [rbx+340h]
0x180215179  mov     ecx, edi
0x18021517b  mov     rax, [r15]
0x18021517e  mov     rcx, [rax+rcx*8]
0x180215182  mov     [rsp+68h+arg_0], rcx
0x180215187  lea     rcx, [rsp+68h+arg_0]
0x18021518c  call    ??$ReleaseInterface@VCProcessAttribution@@@@YAXAEAPEAVCProcessAttribution@@@Z; ReleaseInterface<CProcessAttribution>(CProcessAttribution * &)
0x180215191  inc     edi
0x180215193  cmp     edi, esi
0x180215195  jb      short loc_180215172
0x180215197  jmp     short loc_1802151A0
0x180215199  lea     r15, [rbx+340h]
0x1802151a0  mov     edx, 1
0x1802151a5  mov     rcx, r15
0x1802151a8  call    ?Reset@?$DynArray@PEAVCChannelContext@@$00@@QEAAXH@Z; DynArray<CChannelContext *,1>::Reset(int)
0x1802151ad  mov     rcx, rbx; this
0x1802151b0  call    ?ReleaseNotificationChannels@CComposition@@AEAAXXZ; CComposition::ReleaseNotificationChannels(void)
0x1802151b5  lea     r12, [rbx+298h]
0x1802151bc  mov     rdx, [r12]
0x1802151c0  mov     [r12], rbp
0x1802151c4  test    rdx, rdx
0x1802151c7  jz      short loc_1802151CE
0x1802151c9  call    ??R?$default_delete@VCMeshCacheManager@@@std@@QEBAXPEAVCMeshCacheManager@@@Z; std::default_delete<CMeshCacheManager>::operator()(CMeshCacheManager *)
0x1802151ce  mov     rdx, [rbx+17F8h]
0x1802151d5  mov     rcx, [rbx+17F0h]
0x1802151dc  cmp     rcx, rdx
0x1802151df  jz      short loc_1802151F4
0x1802151e1  call    ??$_Destroy_range@V?$allocator@UCursorVisualData@@@std@@@std@@YAXPEAUCursorVisualData@@QEAU1@AEAV?$allocator@UCursorVisualData@@@0@@Z; std::_Destroy_range<std::allocator<CursorVisualData>>(CursorVisualData *,CursorVisualData * const,std::allocator<CursorVisualData> &)
0x1802151e6  mov     rax, [rbx+17F0h]
0x1802151ed  mov     [rbx+17F8h], rax
0x1802151f4  lea     rdi, [rbx+1738h]
0x1802151fb  mov     rcx, rdi
0x1802151fe  call    ?clear@?$vector@V?$com_ptr_t@VCCompositionSurfaceInfo@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCCompositionSurfaceInfo@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::vector<wil::com_ptr_t<CCompositionSurfaceInfo,wil::err_returncode_policy>>::clear(void)
0x180215203  mov     rcx, rbx; this
0x180215206  call    ?UnmapDeferredSharedSectionViews@CComposition@@IEAAXXZ; CComposition::UnmapDeferredSharedSectionViews(void)
0x18021520b  lea     r13, [rbx+2D0h]
0x180215212  mov     rcx, [r13+0]
0x180215216  mov     [r13+0], rbp
0x18021521a  test    rcx, rcx
0x18021521d  jz      short loc_18021522B
0x18021521f  mov     rax, [rcx]
0x180215222  mov     rax, [rax+10h]
0x180215226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021522b  mov     rsi, [rbx+268h]
0x180215232  test    rsi, rsi
0x180215235  jz      short loc_18021524C
0x180215237  mov     rcx, rsi; this
0x18021523a  call    ??1CRenderTargetManager@@QEAA@XZ; CRenderTargetManager::~CRenderTargetManager(void)
0x18021523f  mov     edx, 2F8h; unsigned __int64
0x180215244  mov     rcx, rsi; void *
0x180215247  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18021524c  mov     rcx, [rbx+330h]
0x180215253  test    rcx, rcx
0x180215256  jz      short loc_18021525D
0x180215258  call    ?Release@?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@UEAAKXZ; CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(void)
0x18021525d  mov     rcx, [rbx+278h]
0x180215264  test    rcx, rcx
0x180215267  jz      short loc_180215275
0x180215269  mov     rax, [rcx]
0x18021526c  mov     rax, [rax+10h]
0x180215270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215275  mov     rcx, [rbx+280h]
0x18021527c  test    rcx, rcx
0x18021527f  jz      short loc_180215298
0x180215281  mov     [rbx+280h], rbp
0x180215288  mov     rax, [rcx]
0x18021528b  mov     rax, [rax+10h]
0x18021528f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215294  jmp     short loc_180215298
0x180215296  xor     ebp, ebp
0x180215298  mov     rax, [rbx+1960h]
0x18021529f  cmp     [rbx+1958h], rax
0x1802152a6  jz      short loc_1802152F7
0x1802152a8  mov     rsi, [rbx+1968h]
0x1802152af  mov     [rbx+1968h], rbp
0x1802152b6  mov     rdx, [rbx+1960h]
0x1802152bd  mov     [rbx+1960h], rbp
0x1802152c4  mov     rbp, [rbx+1958h]
0x1802152cb  mov     qword ptr [rbx+1958h], 0
0x1802152d6  test    rbp, rbp
0x1802152d9  jz      short loc_180215296
0x1802152db  mov     rcx, rbp
0x1802152de  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x1802152e3  sub     rsi, rbp
0x1802152e6  mov     rcx, rbp
0x1802152e9  and     rsi, 0FFFFFFFFFFFFFFF8h
0x1802152ed  mov     rdx, rsi
0x1802152f0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802152f5  jmp     short loc_180215296
0x1802152f7  mov     rcx, rbx; this
0x1802152fa  call    ?HasDelayDeleteResources@CComposition@@QEBA_NXZ; CComposition::HasDelayDeleteResources(void)
0x1802152ff  test    al, al
0x180215301  jz      short loc_18021531F
0x180215303  mov     rcx, [rsp+68h]; this
0x180215308  lea     r8, aOnecoreuapWind_180; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18021530f  mov     r9d, 8007029Ch; char *
0x180215315  mov     edx, 0F9h; void *
0x18021531a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18021531f  mov     rcx, [rbx+270h]
0x180215326  test    rcx, rcx
0x180215329  jz      short loc_180215337
0x18021532b  mov     rax, [rcx]
0x18021532e  mov     rax, [rax+8]
0x180215332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180215337  mov     rcx, [rbx+288h]
0x18021533e  test    rcx, rcx
0x180215341  jz      short loc_180215348
0x180215343  call    ?Release@?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@UEAAKXZ; CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>::Release(void)
0x180215348  lea     rsi, [rbx+2A0h]
0x18021534f  mov     rdx, [rsi]
0x180215352  mov     [rsi], rbp
0x180215355  test    rdx, rdx
0x180215358  jz      short loc_18021535F
0x18021535a  call    ??R?$default_delete@VCSceneResourceManager@@@std@@QEBAXPEAVCSceneResourceManager@@@Z; std::default_delete<CSceneResourceManager>::operator()(CSceneResourceManager *)
0x18021535f  call    ?DestroyObjectCaches@CThreadContext@@SAXXZ; CThreadContext::DestroyObjectCaches(void)
0x180215364  lea     rcx, [rbx+1970h]
0x18021536b  mov     cs:?g_pFrameId@@3PEA_KEA, rbp; unsigned __int64 * g_pFrameId
0x180215372  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180215377  mov     rcx, [rbx+1958h]
0x18021537e  test    rcx, rcx
0x180215381  jz      short loc_1802153BE
0x180215383  mov     rdx, [rbx+1960h]
0x18021538a  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x18021538f  mov     rcx, [rbx+1958h]
0x180215396  mov     rdx, [rbx+1968h]
0x18021539d  sub     rdx, rcx
0x1802153a0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802153a4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802153a9  mov     [rbx+1958h], rbp
0x1802153b0  mov     [rbx+1960h], rbp
0x1802153b7  mov     [rbx+1968h], rbp
0x1802153be  lea     rcx, [rbx+1928h]
0x1802153c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802153ca  lea     rcx, [rbx+1920h]
0x1802153d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802153d6  lea     rcx, [rbx+1918h]
0x1802153dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802153e2  lea     rcx, [rbx+1910h]
0x1802153e9  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1802153ee  lea     rcx, [rbx+1900h]
0x1802153f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802153fa  mov     rcx, [rbx+18F8h]
0x180215401  test    rcx, rcx
0x180215404  jz      short loc_180215412
0x180215406  mov     [rbx+18F8h], rbp
0x18021540d  call    ?InternalRelease@?$CMILRefCountBaseT@UIUnknown@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease(void)
0x180215412  mov     rcx, [rbx+1878h]; void *
0x180215419  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18021541e  lea     rcx, [rbx+1830h]
0x180215425  call    ??1?$_Hash@V?$_Umap_traits@PEAVCVisual@@VCPreWalkVisual@@V?$_Uhash_compare@PEAVCVisual@@U?$hash@PEAVCVisual@@@std@@U?$equal_to@PEAVCVisual@@@3@@std@@V?$allocator@U?$pair@QEAVCVisual@@VCPreWalkVisual@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<CVisual *,CPreWalkVisual,std::_Uhash_compare<CVisual *,std::hash<CVisual *>,std::equal_to<CVisual *>>,std::allocator<std::pair<CVisual * const,CPreWalkVisual>>,0>>::~_Hash<std::_Umap_traits<CVisual *,CPreWalkVisual,std::_Uhash_compare<CVisual *,std::hash<CVisual *>,std::equal_to<CVisual *>>,std::allocator<std::pair<CVisual * const,CPreWalkVisual>>,0>>(void)
0x18021542a  lea     rcx, [rbx+1828h]
0x180215431  call    ??1?$com_ptr_t@VCDDARenderTarget@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>::~com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>(void)
0x180215436  lea     rcx, [rbx+1820h]
0x18021543d  call    ??1?$com_ptr_t@VCDDARenderTarget@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>::~com_ptr_t<CDDARenderTarget,wil::err_returncode_policy>(void)
0x180215442  lea     rcx, [rbx+1808h]
0x180215449  call    ?_Tidy@?$vector@PEAVCLight@@V?$allocator@PEAVCLight@@@std@@@std@@AEAAXXZ; std::vector<CLight *>::_Tidy(void)
0x18021544e  mov     rcx, [rbx+17F0h]
0x180215455  test    rcx, rcx
0x180215458  jz      short loc_180215495
0x18021545a  mov     rdx, [rbx+17F8h]
0x180215461  call    ??$_Destroy_range@V?$allocator@UCursorVisualData@@@std@@@std@@YAXPEAUCursorVisualData@@QEAU1@AEAV?$allocator@UCursorVisualData@@@0@@Z; std::_Destroy_range<std::allocator<CursorVisualData>>(CursorVisualData *,CursorVisualData * const,std::allocator<CursorVisualData> &)
0x180215466  mov     rcx, [rbx+17F0h]
0x18021546d  mov     rdx, [rbx+1800h]
0x180215474  sub     rdx, rcx
0x180215477  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18021547b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180215480  mov     [rbx+17F0h], rbp
0x180215487  mov     [rbx+17F8h], rbp
0x18021548e  mov     [rbx+1800h], rbp
0x180215495  lea     rcx, [rbx+1750h]
0x18021549c  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x1802154a1  mov     rcx, [rdi]
0x1802154a4  test    rcx, rcx
0x1802154a7  jz      short loc_1802154D0
0x1802154a9  mov     rdx, [rdi+8]
0x1802154ad  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x1802154b2  mov     rdx, [rdi+10h]
0x1802154b6  sub     rdx, [rdi]
0x1802154b9  mov     rcx, [rdi]
0x1802154bc  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802154c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802154c5  mov     [rdi], rbp
0x1802154c8  mov     [rdi+8], rbp
0x1802154cc  mov     [rdi+10h], rbp
0x1802154d0  lea     rcx, [rbx+1710h]
0x1802154d7  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x1802154dc  lea     rcx, [rbx+16F0h]
0x1802154e3  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x1802154e8  lea     rcx, [rbx+1698h]
0x1802154ef  call    ??1?$vector_facade@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$buffer_impl@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@$07$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::~vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>(void)
0x1802154f4  lea     rcx, [rbx+1650h]; lpCriticalSection
0x1802154fb  call    cs:__imp_DeleteCriticalSection
0x180215501  lea     rcx, [rbx+1638h]
0x180215508  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18021550d  lea     rcx, [rbx+1630h]
0x180215514  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180215519  lea     rcx, [rbx+1600h]; this
0x180215520  call    ??1CDisplayDebugFrameCounter@@QEAA@XZ; CDisplayDebugFrameCounter::~CDisplayDebugFrameCounter(void)
0x180215525  lea     rcx, [rbx+3C0h]
0x18021552c  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180215531  lea     rcx, [rbx+3A0h]
0x180215538  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x18021553d  mov     rcx, r14
0x180215540  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180215545  mov     rcx, r15
0x180215548  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x18021554d  lea     rcx, [rbx+2D8h]; this
0x180215554  call    ??1CMmcssTask@@QEAA@XZ; CMmcssTask::~CMmcssTask(void)
0x180215559  mov     rcx, r13
0x18021555c  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180215561  lea     rcx, [rbx+2C8h]
0x180215568  call    ??1?$com_ptr_t@VIBitmapResource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBitmapResource,wil::err_returncode_policy>::~com_ptr_t<IBitmapResource,wil::err_returncode_policy>(void)
0x18021556d  lea     rcx, [rbx+2C0h]
0x180215574  call    ??1?$com_ptr_t@VIBitmapResource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBitmapResource,wil::err_returncode_policy>::~com_ptr_t<IBitmapResource,wil::err_returncode_policy>(void)
0x180215579  mov     rcx, rsi
0x18021557c  call    ??1?$unique_ptr@VCSceneResourceManager@@U?$default_delete@VCSceneResourceManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSceneResourceManager>::~unique_ptr<CSceneResourceManager>(void)
0x180215581  mov     rcx, r12
0x180215584  call    ??1?$unique_ptr@VCMeshCacheManager@@U?$default_delete@VCMeshCacheManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CMeshCacheManager>::~unique_ptr<CMeshCacheManager>(void)
0x180215589  lea     rcx, [rbx+290h]
0x180215590  call    ??1?$unique_ptr@VCSuperWetInkManager@@U?$default_delete@VCSuperWetInkManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<CSuperWetInkManager>::~unique_ptr<CSuperWetInkManager>(void)
0x180215595  lea     rcx, [rbx+260h]
0x18021559c  call    ??1?$unique_ptr@VCPreComputeContext@@U?$default_delete@VCPreComputeContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPreComputeContext>::~unique_ptr<CPreComputeContext>(void)
0x1802155a1  lea     rcx, [rbx+228h]
0x1802155a8  call    ??1?$vector_facade@V?$com_ptr_t@VCVisualTree@@Uerr_returncode_policy@wil@@@wil@@V?$buffer_impl@V?$com_ptr_t@VCVisualTree@@Uerr_returncode_policy@wil@@@wil@@$03$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>::~vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>(void)
0x1802155ad  lea     rcx, [rbx+190h]
0x1802155b4  call    ??1?$vector_facade@PEAVCVisualTree@@V?$buffer_impl@PEAVCVisualTree@@$0BA@$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>::~vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>(void)
0x1802155b9  lea     rcx, [rbx+168h]; lpCriticalSection
0x1802155c0  call    cs:__imp_DeleteCriticalSection
0x1802155c6  lea     rcx, [rbx+140h]
0x1802155cd  call    ?clear@?$vector_facade@PEAVCResponseItemBase@@V?$buffer_impl@PEAVCResponseItemBase@@$01$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAAXXZ; detail::vector_facade<CResponseItemBase *,detail::buffer_impl<CResponseItemBase *,2,1,detail::liberal_expansion_policy>>::clear(void)
0x1802155d2  call    ??1?$expandable_buffer_base@PEAVCOverlayContext@@$01@detail@@QEAA@XZ; detail::expandable_buffer_base<COverlayContext *,2>::~expandable_buffer_base<COverlayContext *,2>(void)
0x1802155d7  lea     rcx, [rbx+138h]
0x1802155de  call    ?InternalAddRef@?$ComPtr@UIMessageCallSendHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef(void)
0x1802155e3  lea     rcx, [rbx+130h]
0x1802155ea  call    ?InternalAddRef@?$ComPtr@UIMessageCallSendHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMessageCallSendHost>::InternalAddRef(void)
0x1802155ef  lea     rcx, [rbx+0F0h]
0x1802155f6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802155fb  lea     rcx, [rbx+18h]
0x1802155ff  add     rsp, 28h
0x180215603  pop     r15
0x180215605  pop     r14
0x180215607  pop     r13
0x180215609  pop     r12
0x18021560b  pop     rdi
0x18021560c  pop     rsi
0x18021560d  pop     rbp
0x18021560e  pop     rbx
0x18021560f  jmp     ??1?$vector_facade@W4Type@IRenderTarget@@V?$buffer_impl@W4Type@IRenderTarget@@$03$00Vliberal_expansion_policy@detail@@@detail@@@detail@@QEAA@XZ; detail::vector_facade<IRenderTarget::Type,detail::buffer_impl<IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>::~vector_facade<IRenderTarget::Type,detail::buffer_impl<IRenderTarget::Type,4,1,detail::liberal_expansion_policy>>(void)
```
