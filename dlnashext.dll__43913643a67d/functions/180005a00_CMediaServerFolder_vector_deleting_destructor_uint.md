# CMediaServerFolder::`vector deleting destructor'(uint)

- ea: `0x180005a00`
- end: `0x180005b77`
- name: `??_ECMediaServerFolder@@UEAAPEAXI@Z`
- size: `375`
- prototype: `void *__fastcall(CMediaServerFolder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013bd0`

## callees

- `0x180005a00`
- `0x180011df4`
- `0x1800140e4`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ac9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005b67`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ac9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ad7`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180005b50`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180005b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CMediaServerFolder *__fastcall CMediaServerFolder::`vector deleting destructor'(CMediaServerFolder *this, char a2)
{
  unsigned __int64 i; // rbp
  void *v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  LPITEMIDLIST *v12; // rax

  *(_QWORD *)this = &CMediaServerFolder::`vftable'{for `IDelegateFolder'};
  *((_QWORD *)this + 1) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 3) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &CMediaServerFolder::`vftable'{for `IExplorerPaneVisibility'};
  *((_QWORD *)this + 5) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 6) = &CMediaServerFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'};
  *((_QWORD *)this + 7) = &CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 12) = &CMediaServerFolder::`vftable';
  for ( i = 0; i < *((_QWORD *)this + 16); ++i )
  {
    v12 = (LPITEMIDLIST *)ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt((char *)this + 120);
    ILFree(*v12);
  }
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 15) = 0;
  }
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v6 = *((_QWORD *)this + 19);
  if ( v6 )
  {
    *((_QWORD *)this + 19) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = (void *)*((_QWORD *)this + 15);
  if ( v7 )
    free(v7);
  v8 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  CoTaskMemFree(v8);
  *((_QWORD *)this + 12) = &CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::`vftable';
  v9 = *((_QWORD *)this + 13);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *((_DWORD *)this + 23) = -1073741823;
  v10 = *((_QWORD *)this + 10);
  if ( v10 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005a00  push    rbx
0x180005a02  push    rbp
0x180005a03  push    rsi
0x180005a04  push    rdi
0x180005a05  push    r14
0x180005a07  sub     rsp, 20h
0x180005a0b  mov     esi, edx
0x180005a0d  mov     rbx, rcx
0x180005a10  lea     rax, ??_7CMediaServerFolder@@6BIDelegateFolder@@@; const CMediaServerFolder::`vftable'{for `IDelegateFolder'}
0x180005a17  mov     [rcx], rax
0x180005a1a  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x180005a21  mov     [rcx+8], rax
0x180005a25  lea     rax, ??_7CMediaServerFolder@@6B?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180005a2c  mov     [rcx+10h], rax
0x180005a30  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIThumbnailHandlerFactory@@UIExplorerPaneVisibility@@UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IExplorerPaneVisibility,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x180005a37  mov     [rcx+18h], rax
0x180005a3b  lea     rax, ??_7CMediaServerFolder@@6BIExplorerPaneVisibility@@@; const CMediaServerFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180005a42  mov     [rcx+20h], rax
0x180005a46  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISearchBoxSettings@@UINameSpaceTreeControlFolderCapabilities@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings,INameSpaceTreeControlFolderCapabilities,Microsoft::WRL::FtmBase>'}
0x180005a4d  mov     [rcx+28h], rax
0x180005a51  lea     rax, ??_7CMediaServerFolder@@6BINameSpaceTreeControlFolderCapabilities@@@; const CMediaServerFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'}
0x180005a58  mov     [rcx+30h], rax
0x180005a5c  lea     rax, ??_7CMediaServerFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMediaServerFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005a63  mov     [rcx+38h], rax
0x180005a67  lea     rax, ??_7CMediaServerFolder@@6B@; const CMediaServerFolder::`vftable'
0x180005a6e  mov     [rcx+60h], rax
0x180005a72  xor     r14d, r14d
0x180005a75  mov     ebp, r14d
0x180005a78  cmp     [rcx+80h], r14
0x180005a7f  ja      loc_180005B41
0x180005a85  mov     rcx, [rbx+78h]; Block
0x180005a89  test    rcx, rcx
0x180005a8c  jnz     loc_180005B67
0x180005a92  mov     [rbx+80h], r14
0x180005a99  mov     [rbx+88h], r14
0x180005aa0  mov     rcx, [rbx+98h]
0x180005aa7  test    rcx, rcx
0x180005aaa  jz      short loc_180005AC0
0x180005aac  mov     [rbx+98h], r14
0x180005ab3  mov     rax, [rcx]
0x180005ab6  mov     rax, [rax+10h]
0x180005aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abf  nop
0x180005ac0  mov     rcx, [rbx+78h]; Block
0x180005ac4  test    rcx, rcx
0x180005ac7  jz      short loc_180005ACF
0x180005ac9  call    cs:__imp_free
0x180005acf  mov     rcx, [rbx+70h]; pv
0x180005ad3  mov     [rbx+70h], r14
0x180005ad7  call    cs:__imp_CoTaskMemFree
0x180005add  nop
0x180005ade  lea     rax, ??_7?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@6B@; const CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::`vftable'
0x180005ae5  mov     [rbx+60h], rax
0x180005ae9  mov     rcx, [rbx+68h]
0x180005aed  test    rcx, rcx
0x180005af0  jz      short loc_180005AFF
0x180005af2  mov     rax, [rcx]
0x180005af5  mov     rax, [rax+10h]
0x180005af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005afe  nop
0x180005aff  mov     dword ptr [rbx+5Ch], 0C0000001h
0x180005b06  mov     rcx, [rbx+50h]
0x180005b0a  test    rcx, rcx
0x180005b0d  jz      short loc_180005B20
0x180005b0f  mov     [rbx+50h], r14
0x180005b13  mov     rax, [rcx]
0x180005b16  mov     rax, [rax+10h]
0x180005b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1f  nop
0x180005b20  test    sil, 1
0x180005b24  jz      short loc_180005B33
0x180005b26  mov     edx, 0A0h
0x180005b2b  mov     rcx, rbx; Block
0x180005b2e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005b33  mov     rax, rbx
0x180005b36  add     rsp, 20h
0x180005b3a  pop     r14
0x180005b3c  pop     rdi
0x180005b3d  pop     rsi
0x180005b3e  pop     rbp
0x180005b3f  pop     rbx
0x180005b40  retn
0x180005b41  mov     rdx, rbp
0x180005b44  lea     rcx, [rbx+78h]
0x180005b48  call    ?GetAt@?$CAtlArray@PEAUIPropertyStore@@V?$CElementTraits@PEAUIPropertyStore@@@ATL@@@ATL@@QEAAAEAPEAUIPropertyStore@@_K@Z; ATL::CAtlArray<IPropertyStore *,ATL::CElementTraits<IPropertyStore *>>::GetAt(unsigned __int64)
0x180005b4d  mov     rcx, [rax]; pidl
0x180005b50  call    cs:__imp_ILFree
0x180005b56  inc     rbp
0x180005b59  cmp     rbp, [rbx+80h]
0x180005b60  jb      short loc_180005B41
0x180005b62  jmp     loc_180005A85
0x180005b67  call    cs:__imp_free
0x180005b6d  mov     [rbx+78h], r14
0x180005b71  jmp     loc_180005A92
```
