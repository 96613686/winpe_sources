# CDLNAShextPropertyStore::RuntimeClassInitialize(CContentDirectoryFolder *,_ITEMID_CHILD const *)

- ea: `0x18002862c`
- end: `0x1800286b4`
- name: `?RuntimeClassInitialize@CDLNAShextPropertyStore@@QEAAJPEAVCContentDirectoryFolder@@PEFBU_ITEMID_CHILD@@@Z`
- size: `136`
- prototype: `int(CDLNAShextPropertyStore *__hidden this, struct CContentDirectoryFolder *, const struct _ITEMID_CHILD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014e48`

## callees

- `0x180001710`
- `0x18000b018`
- `0x18000e6b0`
- `0x180016728`
- `0x18002862c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002867d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002867d`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x180028668`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x180028668`

## pseudocode

```c
__int64 __fastcall CDLNAShextPropertyStore::RuntimeClassInitialize(
        CDLNAShextPropertyStore *this,
        struct CContentDirectoryFolder *a2,
        const ITEMIDLIST *a3)
{
  struct CContentDirectoryFolder *v4; // r10
  __int64 v6; // rcx
  LPITEMIDLIST v7; // rax
  void *v8; // rcx
  LPITEMIDLIST v9; // rbx
  __int64 v11; // rdx

  v4 = a2;
  if ( *((struct CContentDirectoryFolder **)this + 4) != a2 )
  {
    if ( a2 )
      Microsoft::WRL::Details::SafeUnknownIncrementReference(
        (struct CContentDirectoryFolder *)((char *)a2 + 68),
        (volatile int *)a2);
    v6 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v4;
    if ( v6 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::Release(v6);
  }
  v7 = ILCloneFirst(a3);
  v8 = (void *)*((_QWORD *)this + 5);
  v9 = v7;
  *((_QWORD *)this + 5) = 0;
  CoTaskMemFree(v8);
  *((_QWORD *)this + 5) = v9;
  if ( !v9 )
    return 2147942414LL;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 24);
  return CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyStorageFromIDList(
           *((_QWORD *)this + 5),
           v11,
           (char *)this + 24);
}

```

## disassembly

```asm
0x18002862c  mov     [rsp+arg_0], rbx
0x180028631  push    rdi
0x180028632  sub     rsp, 20h
0x180028636  mov     rbx, r8
0x180028639  mov     r10, rdx
0x18002863c  mov     rdi, rcx
0x18002863f  cmp     [rcx+20h], rdx
0x180028643  jz      short loc_180028665
0x180028645  test    rdx, rdx
0x180028648  jz      short loc_180028653
0x18002864a  lea     rcx, [rdx+44h]; this
0x18002864e  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180028653  mov     rcx, [rdi+20h]
0x180028657  mov     [rdi+20h], r10
0x18002865b  test    rcx, rcx
0x18002865e  jz      short loc_180028665
0x180028660  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIProviderResolver@@UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::Release(void)
0x180028665  mov     rcx, rbx; pidl
0x180028668  call    cs:__imp_ILCloneFirst
0x18002866e  mov     rcx, [rdi+28h]; pv
0x180028672  mov     rbx, rax
0x180028675  mov     qword ptr [rdi+28h], 0
0x18002867d  call    cs:__imp_CoTaskMemFree
0x180028683  mov     [rdi+28h], rbx
0x180028687  test    rbx, rbx
0x18002868a  jnz     short loc_180028693
0x18002868c  mov     eax, 8007000Eh
0x180028691  jmp     short loc_1800286A9
0x180028693  lea     rcx, [rdi+18h]
0x180028697  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002869c  mov     rcx, [rdi+28h]
0x1800286a0  lea     r8, [rdi+18h]
0x1800286a4  call    ?GetPropertyStorageFromIDList@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x1800286a9  mov     rbx, [rsp+28h+arg_0]
0x1800286ae  add     rsp, 20h
0x1800286b2  pop     rdi
0x1800286b3  retn
```
