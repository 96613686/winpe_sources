# Microsoft::WRL::SimpleClassFactory<CMediaServerFolder,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005470`
- end: `0x18000571b`
- name: `?CreateInstance@?$SimpleClassFactory@VCMediaServerFolder@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `683`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005470`
- `0x180005730`
- `0x180005750`
- `0x180005770`
- `0x180005f60`
- `0x180011954`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800054e8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800054e8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800056bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800056bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CMediaServerFolder,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  char *v6; // rax
  char *v7; // rdi
  __int64 v8; // rcx
  __int64 *v9; // rsi
  LPUNKNOWN v10; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v12; // rcx
  LPUNKNOWN v13; // rcx
  _QWORD *v14; // rcx
  signed __int32 i; // edx
  unsigned int v16; // ebx
  LPUNKNOWN ppunkMarshal; // [rsp+78h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  else
  {
    ppunkMarshal = 0;
    v6 = (char *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(v6 + 8);
      Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(v7 + 16);
      *(_QWORD *)(v8 + 40) = &Microsoft::WRL::FtmBase::`vftable';
      v9 = (__int64 *)(v8 + 64);
      *(_QWORD *)(v8 + 64) = 0;
      ppunkMarshal = 0;
      if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
      {
        v10 = ppunkMarshal;
        QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
        v12 = *v9;
        if ( *v9 )
        {
          *v9 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
          v10,
          &GUID_00000003_0000_0000_c000_000000000046,
          v9);
      }
      v13 = ppunkMarshal;
      if ( ppunkMarshal )
      {
        ppunkMarshal = 0;
        ((void (__fastcall *)(LPUNKNOWN))v13->lpVtbl->Release)(v13);
      }
      *((_DWORD *)v7 + 23) = 1;
      *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IDelegateFolder'};
      *((_QWORD *)v7 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v7 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
      *((_QWORD *)v7 + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v7 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IExplorerPaneVisibility'};
      *((_QWORD *)v7 + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v7 + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `INameSpaceTreeControlFolderCapabilities'};
      *((_QWORD *)v7 + 7) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::CItemIDFactory<CDSFOLDER_ITEMID,1158816290>(v7 + 96);
      *(_QWORD *)v7 = &CMediaServerFolder::`vftable'{for `IDelegateFolder'};
      *((_QWORD *)v7 + 1) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v7 + 2) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
      *((_QWORD *)v7 + 3) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v7 + 4) = &CMediaServerFolder::`vftable'{for `IExplorerPaneVisibility'};
      *((_QWORD *)v7 + 5) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v7 + 6) = &CMediaServerFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'};
      *((_QWORD *)v7 + 7) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *v14 = &CMediaServerFolder::`vftable';
      *((_QWORD *)v7 + 14) = 0;
      *((_QWORD *)v7 + 15) = 0;
      *((_QWORD *)v7 + 16) = 0;
      *((_QWORD *)v7 + 17) = 0;
      *((_DWORD *)v7 + 36) = 0;
      *((_QWORD *)v7 + 19) = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
      for ( i = *((_DWORD *)v7 + 23); i != 0x7FFFFFFF; i = *((_DWORD *)v7 + 23) )
      {
        if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v7 + 23, i - 1, i) )
          break;
      }
      if ( i == 1 )
      {
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
        if ( Microsoft::WRL::Details::ModuleBase::module_ )
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                               + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      v16 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v7)(v7, a3, a4);
      if ( v7 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
      return v16;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180005470  push    rbx
0x180005472  push    rbp
0x180005473  push    rsi
0x180005474  push    rdi
0x180005475  push    r12
0x180005477  push    r13
0x180005479  push    r14
0x18000547b  push    r15
0x18000547d  sub     rsp, 28h
0x180005481  mov     r15, r9
0x180005484  mov     r12, r8
0x180005487  xor     r13d, r13d
0x18000548a  mov     [r9], r13
0x18000548d  test    rdx, rdx
0x180005490  jnz     loc_1800056B8
0x180005496  mov     [rsp+68h+ppunkMarshal], r13
0x18000549b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800054a2  mov     ecx, 0A0h; unsigned __int64
0x1800054a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800054ac  mov     rdi, rax
0x1800054af  test    rax, rax
0x1800054b2  jz      loc_18000570A
0x1800054b8  lea     rcx, [rax+8]
0x1800054bc  call    ??0?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x1800054c1  lea     rcx, [rdi+10h]
0x1800054c5  call    ??0?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x1800054ca  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800054d1  mov     [rcx+28h], rax
0x1800054d5  lea     rsi, [rcx+40h]
0x1800054d9  mov     [rsi], r13
0x1800054dc  mov     [rsp+68h+ppunkMarshal], r13
0x1800054e1  lea     rdx, [rsp+68h+ppunkMarshal]; ppunkMarshal
0x1800054e6  xor     ecx, ecx; punkOuter
0x1800054e8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800054ee  test    eax, eax
0x1800054f0  js      short loc_18000552B
0x1800054f2  mov     rbx, [rsp+68h+ppunkMarshal]
0x1800054f7  mov     rax, [rbx]
0x1800054fa  mov     rbp, [rax]
0x1800054fd  mov     rcx, [rsi]
0x180005500  test    rcx, rcx
0x180005503  jz      short loc_180005515
0x180005505  mov     [rsi], r13
0x180005508  mov     rdx, [rcx]
0x18000550b  mov     rax, [rdx+10h]
0x18000550f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005514  nop
0x180005515  mov     r8, rsi
0x180005518  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000551f  mov     rcx, rbx
0x180005522  mov     rax, rbp
0x180005525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552a  nop
0x18000552b  mov     rcx, [rsp+68h+ppunkMarshal]
0x180005530  test    rcx, rcx
0x180005533  jz      short loc_180005547
0x180005535  mov     [rsp+68h+ppunkMarshal], r13
0x18000553a  mov     rax, [rcx]
0x18000553d  mov     rax, [rax+10h]
0x180005541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005546  nop
0x180005547  mov     dword ptr [rdi+5Ch], 1
0x18000554e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6BIDelegateFolder@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IDelegateFolder'}
0x180005555  mov     [rdi], rax
0x180005558  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x18000555f  mov     [rdi+8], rax
0x180005563  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x18000556a  mov     [rdi+10h], rax
0x18000556e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x180005575  mov     [rdi+18h], rax
0x180005579  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6BIExplorerPaneVisibility@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `IExplorerPaneVisibility'}
0x180005580  mov     [rdi+20h], rax
0x180005584  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x18000558b  mov     [rdi+28h], rax
0x18000558f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6BINameSpaceTreeControlFolderCapabilities@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `INameSpaceTreeControlFolderCapabilities'}
0x180005596  mov     [rdi+30h], rax
0x18000559a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800055a1  mov     [rdi+38h], rax
0x1800055a5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800055ac  test    rcx, rcx
0x1800055af  jz      short loc_1800055BE
0x1800055b1  mov     rax, [rcx]
0x1800055b4  mov     rax, [rax+8]
0x1800055b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bd  nop
0x1800055be  lea     rcx, [rdi+60h]
0x1800055c2  call    ??0?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@IEAA@XZ; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::CItemIDFactory<CDSFOLDER_ITEMID,1158816290>(void)
0x1800055c7  lea     rdx, ??_7CMediaServerFolder@@6BIDelegateFolder@@@; const CMediaServerFolder::`vftable'{for `IDelegateFolder'}
0x1800055ce  mov     [rdi], rdx
0x1800055d1  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x1800055d8  mov     [rdi+8], rax
0x1800055dc  lea     rax, ??_7CMediaServerFolder@@6B?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800055e3  mov     [rdi+10h], rax
0x1800055e7  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x1800055ee  mov     [rdi+18h], rax
0x1800055f2  lea     rax, ??_7CMediaServerFolder@@6BIExplorerPaneVisibility@@@; const CMediaServerFolder::`vftable'{for `IExplorerPaneVisibility'}
0x1800055f9  mov     [rdi+20h], rax
0x1800055fd  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x180005604  mov     [rdi+28h], rax
0x180005608  lea     rax, ??_7CMediaServerFolder@@6BINameSpaceTreeControlFolderCapabilities@@@; const CMediaServerFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'}
0x18000560f  mov     [rdi+30h], rax
0x180005613  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000561a  mov     [rdi+38h], rax
0x18000561e  lea     rax, ??_7CMediaServerFolder@@6B@; const CMediaServerFolder::`vftable'
0x180005625  mov     [rcx], rax
0x180005628  mov     [rdi+70h], r13
0x18000562c  mov     [rdi+78h], r13
0x180005630  mov     [rdi+80h], r13
0x180005637  mov     [rdi+88h], r13
0x18000563e  mov     [rdi+90h], r13d
0x180005645  mov     [rdi+98h], r13
0x18000564c  mov     rax, [rdi]
0x18000564f  mov     rcx, rdi
0x180005652  mov     rax, [rax+8]
0x180005656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565b  nop
0x18000565c  mov     edx, [rdi+5Ch]
0x18000565f  cmp     edx, 7FFFFFFFh
0x180005665  jz      short loc_180005673
0x180005667  lea     ecx, [rdx-1]
0x18000566a  mov     eax, edx
0x18000566c  lock cmpxchg [rdi+5Ch], ecx
0x180005671  jnz     short loc_1800056CC
0x180005673  lea     eax, [rdx-1]
0x180005676  test    eax, eax
0x180005678  jz      short loc_1800056D9
0x18000567a  mov     rax, [rdi]
0x18000567d  mov     r8, r15
0x180005680  mov     rdx, r12
0x180005683  mov     rcx, rdi
0x180005686  mov     rax, [rax]
0x180005689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568e  mov     ebx, eax
0x180005690  test    rdi, rdi
0x180005693  jz      short loc_1800056A5
0x180005695  mov     rcx, [rdi]
0x180005698  mov     rax, [rcx+10h]
0x18000569c  mov     rcx, rdi
0x18000569f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a4  nop
0x1800056a5  mov     eax, ebx
0x1800056a7  add     rsp, 28h
0x1800056ab  pop     r15
0x1800056ad  pop     r14
0x1800056af  pop     r13
0x1800056b1  pop     r12
0x1800056b3  pop     rdi
0x1800056b4  pop     rsi
0x1800056b5  pop     rbp
0x1800056b6  pop     rbx
0x1800056b7  retn
0x1800056b8  xor     edx, edx
0x1800056ba  mov     ecx, 80040110h
0x1800056bf  call    cs:__imp_RoOriginateError
0x1800056c5  mov     eax, 80040110h
0x1800056ca  jmp     short loc_1800056A7
0x1800056cc  mov     edx, [rdi+5Ch]
0x1800056cf  cmp     edx, 7FFFFFFFh
0x1800056d5  jnz     short loc_180005667
0x1800056d7  jmp     short loc_180005673
0x1800056d9  mov     rax, [rdi]
0x1800056dc  mov     edx, 1
0x1800056e1  mov     rcx, rdi
0x1800056e4  mov     rax, [rax+20h]
0x1800056e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ed  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800056f4  test    rcx, rcx
0x1800056f7  jz      short loc_18000567A
0x1800056f9  mov     rax, [rcx]
0x1800056fc  mov     rax, [rax+10h]
0x180005700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005705  jmp     loc_18000567A
0x18000570a  lea     rcx, [rsp+68h+ppunkMarshal]
0x18000570f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005714  mov     eax, 8007000Eh
0x180005719  jmp     short loc_1800056A7
```
