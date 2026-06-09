# CContentDirectoryChangeListenerForDms::~CContentDirectoryChangeListenerForDms(void)

- ea: `0x1800226f4`
- end: `0x1800227ba`
- name: `??1CContentDirectoryChangeListenerForDms@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(CContentDirectoryChangeListenerForDms *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800229a0`

## callees

- `0x180001710`
- `0x180006c10`
- `0x1800097c0`
- `0x18000a724`
- `0x1800225b4`
- `0x1800226f4`
- `0x180023a80`
- `0x180024b4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022772`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022772`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180022763`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180022763`

## pseudocode

```c
void __fastcall CContentDirectoryChangeListenerForDms::~CContentDirectoryChangeListenerForDms(
        CContentDirectoryChangeListenerForDms *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9

  *(_QWORD *)this = &CContentDirectoryChangeListenerForDms::`vftable';
  v2 = (_QWORD *)((char *)this + 120);
  *((_QWORD *)this + 1) = &CContentDirectoryChangeListenerForDms::`vftable'{for `Windows::Media::Streaming::Internal::ISystemUpdateIdHandler'};
  *((_QWORD *)this + 2) = &CContentDirectoryChangeListenerForDms::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Media::Streaming::Internal::IContainerUpdateIdsHandler,Windows::Media::Streaming::Internal::IIsAuthorizedOrValidatedHandler,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &CContentDirectoryChangeListenerForDms::`vftable'{for `Windows::Media::Streaming::Internal::IIsAuthorizedOrValidatedHandler'};
  *((_QWORD *)this + 4) = &CContentDirectoryChangeListenerForDms::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v3 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Minimum(
         v2,
         *v2);
  while ( v3 )
  {
    v3 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Successor(
           v2,
           v3,
           v4,
           v3);
    ILFree(*(LPITEMIDLIST *)(v5 + 8));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::~ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>((char *)this + 192);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 176);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::~CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>(v2);
  Windows::Internal::String::~String((CContentDirectoryChangeListenerForDms *)((char *)this + 112));
  *((_DWORD *)this + 17) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>((char *)this + 32);
}

```

## disassembly

```asm
0x1800226f4  push    rbx
0x1800226f6  push    rsi
0x1800226f7  push    rdi
0x1800226f8  push    r14
0x1800226fa  sub     rsp, 28h
0x1800226fe  lea     rax, ??_7CContentDirectoryChangeListenerForDms@@6B@; const CContentDirectoryChangeListenerForDms::`vftable'
0x180022705  mov     rbx, rcx
0x180022708  mov     [rcx], rax
0x18002270b  lea     rsi, [rcx+78h]
0x18002270f  lea     rax, ??_7CContentDirectoryChangeListenerForDms@@6BISystemUpdateIdHandler@Internal@Streaming@Media@Windows@@@; const CContentDirectoryChangeListenerForDms::`vftable'{for `Windows::Media::Streaming::Internal::ISystemUpdateIdHandler'}
0x180022716  mov     [rcx+8], rax
0x18002271a  lea     rax, ??_7CContentDirectoryChangeListenerForDms@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIContainerUpdateIdsHandler@Internal@Streaming@Media@Windows@@UIIsAuthorizedOrValidatedHandler@5678@VFtmBase@23@@Details@WRL@Microsoft@@@; const CContentDirectoryChangeListenerForDms::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Media::Streaming::Internal::IContainerUpdateIdsHandler,Windows::Media::Streaming::Internal::IIsAuthorizedOrValidatedHandler,Microsoft::WRL::FtmBase>'}
0x180022721  mov     [rcx+10h], rax
0x180022725  lea     rax, ??_7CContentDirectoryChangeListenerForDms@@6BIIsAuthorizedOrValidatedHandler@Internal@Streaming@Media@Windows@@@; const CContentDirectoryChangeListenerForDms::`vftable'{for `Windows::Media::Streaming::Internal::IIsAuthorizedOrValidatedHandler'}
0x18002272c  mov     [rcx+18h], rax
0x180022730  lea     rax, ??_7CContentDirectoryChangeListenerForDms@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CContentDirectoryChangeListenerForDms::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180022737  mov     [rcx+20h], rax
0x18002273b  mov     rcx, rsi
0x18002273e  mov     rdx, [rsi]
0x180022741  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::CNode *)
0x180022746  mov     rdi, rax
0x180022749  test    rax, rax
0x18002274c  jz      short loc_18002276E
0x18002274e  mov     rdx, rdi
0x180022751  mov     rcx, rsi
0x180022754  mov     r9, rdi
0x180022757  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::CNode *)
0x18002275c  mov     rcx, [r9+8]; pidl
0x180022760  mov     rdi, rax
0x180022763  call    cs:__imp_ILFree
0x180022769  test    rdi, rdi
0x18002276c  jnz     short loc_18002274E
0x18002276e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180022772  call    cs:__imp_DeleteCriticalSection
0x180022778  lea     rcx, [rbx+0C0h]
0x18002277f  call    ??1?$ComPtr@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::~ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>>(void)
0x180022784  lea     rcx, [rbx+0B0h]
0x18002278b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180022790  mov     rcx, rsi
0x180022793  call    ??1?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@QEAA@XZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::~CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>(void)
0x180022798  lea     rcx, [rbx+70h]; this
0x18002279c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800227a1  lea     rcx, [rbx+20h]
0x1800227a5  mov     dword ptr [rbx+44h], 0C0000001h
0x1800227ac  add     rsp, 28h
0x1800227b0  pop     r14
0x1800227b2  pop     rdi
0x1800227b3  pop     rsi
0x1800227b4  pop     rbx
0x1800227b5  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
```
