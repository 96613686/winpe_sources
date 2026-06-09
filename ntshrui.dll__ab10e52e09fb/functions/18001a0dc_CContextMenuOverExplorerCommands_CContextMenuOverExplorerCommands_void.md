# CContextMenuOverExplorerCommands::~CContextMenuOverExplorerCommands(void)

- ea: `0x18001a0dc`
- end: `0x18001a19b`
- name: `??1CContextMenuOverExplorerCommands@@MEAA@XZ`
- size: `191`
- prototype: `void __fastcall(CContextMenuOverExplorerCommands *__hidden this)`
- caller_count: `12`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a04c`
- `0x18001a0c0`
- `0x18002cda8`
- `0x18002cf28`
- `0x18002cff0`
- `0x18002d078`
- `0x18002d6a0`
- `0x18002d6e8`
- `0x18002d7b0`
- `0x180034510`
- `0x18003a8d8`
- `0x18003aac8`

## callees

- `0x180008900`
- `0x18001a0dc`
- `0x18001a1a4`
- `0x180023924`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a168`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a177`
- `SHELL32!__imp_ILFree` at `0x18001a155`
- `SHELL32!__imp_ILFree` at `0x18001a155`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CContextMenuOverExplorerCommands::~CContextMenuOverExplorerCommands(
        CContextMenuOverExplorerCommands *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  HKEY v4; // rcx

  *(_QWORD *)this = &CContextMenuOverExplorerCommands::`vftable';
  *((_QWORD *)this + 3) = &CContextMenuOverExplorerCommands::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 4) = &CContextMenuOverExplorerCommands::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IContextMenu3,IContextMenu2,IContextMenu,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>'};
  SafeRelease<IShellItemArray>((char *)this + 48);
  SafeRelease<IShellItemArray>((char *)this + 56);
  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  ILFree(*((LPITEMIDLIST *)this + 10));
  SafeRelease<IShellItemArray>((char *)this + 88);
  CoTaskMemFree(*((LPVOID *)this + 12));
  v4 = (HKEY)*((_QWORD *)this + 13);
  if ( v4 )
    RegCloseKey(v4);
  wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>((char *)this + 128);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease((char *)this + 16);
}

```

## disassembly

```asm
0x18001a0dc  push    rbx
0x18001a0de  sub     rsp, 20h
0x18001a0e2  mov     rbx, rcx
0x18001a0e5  lea     rax, ??_7CContextMenuOverExplorerCommands@@6B@; const CContextMenuOverExplorerCommands::`vftable'
0x18001a0ec  mov     [rcx], rax
0x18001a0ef  lea     rax, ??_7CContextMenuOverExplorerCommands@@6BIShellExtInit@@@; const CContextMenuOverExplorerCommands::`vftable'{for `IShellExtInit'}
0x18001a0f6  mov     [rcx+18h], rax
0x18001a0fa  lea     rax, ??_7CContextMenuOverExplorerCommands@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIContextMenu3@@UIContextMenu2@@UIContextMenu@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@@Details@WRL@Microsoft@@@; const CContextMenuOverExplorerCommands::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IContextMenu3,IContextMenu2,IContextMenu,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>>'}
0x18001a101  mov     [rcx+20h], rax
0x18001a105  add     rcx, 30h ; '0'
0x18001a109  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18001a10e  lea     rcx, [rbx+38h]
0x18001a112  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18001a117  mov     rcx, [rbx+40h]
0x18001a11b  mov     qword ptr [rbx+40h], 0
0x18001a123  test    rcx, rcx
0x18001a126  jz      short loc_18001A134
0x18001a128  mov     rax, [rcx]
0x18001a12b  mov     rax, [rax+10h]
0x18001a12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a134  mov     rcx, [rbx+48h]
0x18001a138  mov     qword ptr [rbx+48h], 0
0x18001a140  test    rcx, rcx
0x18001a143  jz      short loc_18001A151
0x18001a145  mov     rax, [rcx]
0x18001a148  mov     rax, [rax+10h]
0x18001a14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a151  mov     rcx, [rbx+50h]; pidl
0x18001a155  call    cs:__imp_ILFree
0x18001a15b  lea     rcx, [rbx+58h]
0x18001a15f  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18001a164  mov     rcx, [rbx+60h]; pv
0x18001a168  call    cs:__imp_CoTaskMemFree
0x18001a16e  mov     rcx, [rbx+68h]; hKey
0x18001a172  test    rcx, rcx
0x18001a175  jz      short loc_18001A17E
0x18001a177  call    cs:__imp_RegCloseKey
0x18001a17d  nop
0x18001a17e  lea     rcx, [rbx+80h]
0x18001a185  call    ??1?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(void)
0x18001a18a  nop
0x18001a18b  lea     rcx, [rbx+10h]
0x18001a18f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001a194  nop
0x18001a195  add     rsp, 20h
0x18001a199  pop     rbx
0x18001a19a  retn
```
