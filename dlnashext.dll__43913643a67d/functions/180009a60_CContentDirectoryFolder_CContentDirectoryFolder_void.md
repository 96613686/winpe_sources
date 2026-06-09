# CContentDirectoryFolder::~CContentDirectoryFolder(void)

- ea: `0x180009a60`
- end: `0x180009b8f`
- name: `??1CContentDirectoryFolder@@UEAA@XZ`
- size: `303`
- prototype: `void __fastcall(CContentDirectoryFolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013d40`

## callees

- `0x180009a60`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CContentDirectoryFolder::~CContentDirectoryFolder(CContentDirectoryFolder *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx

  *(_QWORD *)this = &CContentDirectoryFolder::`vftable'{for `IDelegateFolder'};
  *((_QWORD *)this + 1) = &CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>'};
  *((_QWORD *)this + 2) = &CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 3) = &CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>'};
  *((_QWORD *)this + 4) = &CContentDirectoryFolder::`vftable'{for `IProviderResolver'};
  *((_QWORD *)this + 5) = &CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>'};
  *((_QWORD *)this + 6) = &CContentDirectoryFolder::`vftable'{for `IFileJunctionOptions'};
  *((_QWORD *)this + 7) = &CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings>'};
  *((_QWORD *)this + 9) = &CContentDirectoryFolder::`vftable';
  v2 = *((_QWORD *)this + 20);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 56LL))(v2, 1);
  *((_QWORD *)this + 20) = 0;
  v3 = *((_QWORD *)this + 19);
  if ( v3 )
  {
    *((_QWORD *)this + 19) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  CoTaskMemFree(v8);
  *((_QWORD *)this + 9) = &CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::`vftable';
  v9 = *((_QWORD *)this + 10);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *((_DWORD *)this + 17) = -1073741823;
}

```

## disassembly

```asm
0x180009a60  mov     [rsp+arg_0], rbx
0x180009a65  push    rdi
0x180009a66  sub     rsp, 20h
0x180009a6a  mov     rbx, rcx
0x180009a6d  lea     rax, ??_7CContentDirectoryFolder@@6BIDelegateFolder@@@; const CContentDirectoryFolder::`vftable'{for `IDelegateFolder'}
0x180009a74  mov     [rcx], rax
0x180009a77  lea     rax, ??_7CContentDirectoryFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIProviderResolver@@UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@@; const CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>'}
0x180009a7e  mov     [rcx+8], rax
0x180009a82  lea     rax, ??_7CContentDirectoryFolder@@6B?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180009a89  mov     [rcx+10h], rax
0x180009a8d  lea     rax, ??_7CContentDirectoryFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIThumbnailHandlerFactory@@UIProviderResolver@@UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@@; const CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>'}
0x180009a94  mov     [rcx+18h], rax
0x180009a98  lea     rax, ??_7CContentDirectoryFolder@@6BIProviderResolver@@@; const CContentDirectoryFolder::`vftable'{for `IProviderResolver'}
0x180009a9f  mov     [rcx+20h], rax
0x180009aa3  lea     rax, ??_7CContentDirectoryFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@@; const CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>'}
0x180009aaa  mov     [rcx+28h], rax
0x180009aae  lea     rax, ??_7CContentDirectoryFolder@@6BIFileJunctionOptions@@@; const CContentDirectoryFolder::`vftable'{for `IFileJunctionOptions'}
0x180009ab5  mov     [rcx+30h], rax
0x180009ab9  lea     rax, ??_7CContentDirectoryFolder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISearchBoxSettings@@@Details@WRL@Microsoft@@@; const CContentDirectoryFolder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISearchBoxSettings>'}
0x180009ac0  mov     [rcx+38h], rax
0x180009ac4  lea     rax, ??_7CContentDirectoryFolder@@6B@; const CContentDirectoryFolder::`vftable'
0x180009acb  mov     [rcx+48h], rax
0x180009acf  mov     rcx, [rcx+0A0h]
0x180009ad6  test    rcx, rcx
0x180009ad9  jz      short loc_180009AEC
0x180009adb  mov     rax, [rcx]
0x180009ade  mov     edx, 1
0x180009ae3  mov     rax, [rax+38h]
0x180009ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aec  xor     edi, edi
0x180009aee  mov     [rbx+0A0h], rdi
0x180009af5  mov     rcx, [rbx+98h]
0x180009afc  test    rcx, rcx
0x180009aff  jz      short loc_180009B15
0x180009b01  mov     [rbx+98h], rdi
0x180009b08  mov     rax, [rcx]
0x180009b0b  mov     rax, [rax+10h]
0x180009b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b14  nop
0x180009b15  mov     rcx, [rbx+78h]; pv
0x180009b19  mov     [rbx+78h], rdi
0x180009b1d  call    cs:__imp_CoTaskMemFree
0x180009b23  mov     rcx, [rbx+70h]; pv
0x180009b27  mov     [rbx+70h], rdi
0x180009b2b  call    cs:__imp_CoTaskMemFree
0x180009b31  mov     rcx, [rbx+68h]; pv
0x180009b35  mov     [rbx+68h], rdi
0x180009b39  call    cs:__imp_CoTaskMemFree
0x180009b3f  mov     rcx, [rbx+60h]; pv
0x180009b43  mov     [rbx+60h], rdi
0x180009b47  call    cs:__imp_CoTaskMemFree
0x180009b4d  mov     rcx, [rbx+58h]; pv
0x180009b51  mov     [rbx+58h], rdi
0x180009b55  call    cs:__imp_CoTaskMemFree
0x180009b5b  nop
0x180009b5c  lea     rax, ??_7?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@6B@; const CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::`vftable'
0x180009b63  mov     [rbx+48h], rax
0x180009b67  mov     rcx, [rbx+50h]
0x180009b6b  test    rcx, rcx
0x180009b6e  jz      short loc_180009B7D
0x180009b70  mov     rax, [rcx]
0x180009b73  mov     rax, [rax+10h]
0x180009b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7c  nop
0x180009b7d  mov     dword ptr [rbx+44h], 0C0000001h
0x180009b84  mov     rbx, [rsp+28h+arg_0]
0x180009b89  add     rsp, 20h
0x180009b8d  pop     rdi
0x180009b8e  retn
```
