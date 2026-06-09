# CDocObjectHost::~CDocObjectHost(void)

- ea: `0x18003ee8c`
- end: `0x18003f3c1`
- name: `??1CDocObjectHost@@MEAA@XZ`
- size: `1333`
- prototype: `void __fastcall(CDocObjectHost *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180132a20`

## callees

- `0x18000b9e0`
- `0x180012140`
- `0x18003ee8c`
- `0x18003f3c8`
- `0x18003f474`
- `0x18003f530`
- `0x18003f728`
- `0x18003f8ec`
- `0x180084b88`
- `0x180084bc0`
- `0x180089434`
- `0x18008f810`
- `0x180550010`

## import_xrefs

- `KERNEL32!GlobalDeleteAtom` at `0x18003efe4`
- `KERNEL32!GlobalDeleteAtom` at `0x18003efe4`
- `KERNEL32!LocalFree` at `0x18003f045`
- `KERNEL32!LocalFree` at `0x18003f045`
- `GDI32!DeleteObject` at `0x18003f2e1`
- `GDI32!DeleteObject` at `0x18003f2f3`
- `GDI32!DeleteObject` at `0x18003f2e1`
- `GDI32!DeleteObject` at `0x18003f2f3`
- `USER32!DestroyWindow` at `0x18003f280`
- `USER32!DestroyWindow` at `0x18003f280`
- `USER32!DestroyIcon` at `0x18003f248`
- `USER32!DestroyIcon` at `0x18003f248`
- `USER32!DestroyAcceleratorTable` at `0x18003f05e`
- `USER32!DestroyAcceleratorTable` at `0x18003f05e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003effe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f0ba`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f264`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f3a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003effe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f0ba`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f264`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f3a5`
- `OLEAUT32!__imp_VariantClear` at `0x18003f117`
- `OLEAUT32!__imp_VariantClear` at `0x18003f12c`
- `OLEAUT32!__imp_VariantClear` at `0x18003f117`
- `OLEAUT32!__imp_VariantClear` at `0x18003f12c`
- `SHELL32!__imp_ILFree` at `0x18003f072`
- `SHELL32!__imp_ILFree` at `0x18003f072`
- `iertutil!__imp_DSA_Destroy` at `0x18003f34d`
- `iertutil!__imp_DSA_Destroy` at `0x18003f361`
- `iertutil!__imp_DSA_Destroy` at `0x18003f34d`
- `iertutil!__imp_DSA_Destroy` at `0x18003f361`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x18003f15e`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x18003f19d`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x18003f216`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x18003f15e`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x18003f19d`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x18003f216`
- `iertutil!__imp_DPA_Destroy` at `0x18003f16b`
- `iertutil!__imp_DPA_Destroy` at `0x18003f1aa`
- `iertutil!__imp_DPA_Destroy` at `0x18003f1e3`
- `iertutil!__imp_DPA_Destroy` at `0x18003f220`
- `iertutil!__imp_DPA_Destroy` at `0x18003f16b`
- `iertutil!__imp_DPA_Destroy` at `0x18003f1aa`
- `iertutil!__imp_DPA_Destroy` at `0x18003f1e3`
- `iertutil!__imp_DPA_Destroy` at `0x18003f220`
- `iertutil!__imp_DPA_EnumCallback` at `0x18003f151`
- `iertutil!__imp_DPA_EnumCallback` at `0x18003f190`
- `iertutil!__imp_DPA_EnumCallback` at `0x18003f20c`
- `iertutil!__imp_DPA_EnumCallback` at `0x18003f151`
- `iertutil!__imp_DPA_EnumCallback` at `0x18003f190`
- `iertutil!__imp_DPA_EnumCallback` at `0x18003f20c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f033`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f0c7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f0d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f26e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f033`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f0c7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f0d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f26e`

## pseudocode

```c
void __fastcall CDocObjectHost::~CDocObjectHost(CDocObjectHost *this)
{
  ATOM v2; // cx
  OLECHAR *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  HACCEL v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  VARIANTARG *v10; // rcx
  VARIANTARG *v11; // rcx
  HICON v12; // rcx
  HWND v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  struct _DSA *v19; // rcx
  OLECHAR *v20; // rcx

  *(_QWORD *)this = &CDocObjectHost::`vftable'{for `IDocHostUIHandler2'};
  *((_QWORD *)this + 1) = &CDocObjectHost::`vftable'{for `IDocHostUIHandlerPriv'};
  *((_QWORD *)this + 2) = &CDocObjectHost::`vftable'{for `IDocHostUIControlPriv'};
  *((_QWORD *)this + 3) = &CDocObjectHost::`vftable'{for `IDocHostShowUI'};
  *((_QWORD *)this + 4) = &CDocObjectHost::`vftable'{for `IOleClientSite'};
  *((_QWORD *)this + 5) = &CDocObjectHost::`vftable'{for `IOleDocumentSite'};
  *((_QWORD *)this + 6) = &CDocObjectHost::`vftable'{for `IOleCommandTarget'};
  *((_QWORD *)this + 7) = &CDocObjectHost::`vftable'{for `IOleInPlaceSiteEx'};
  *((_QWORD *)this + 8) = &CDocObjectHost::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 9) = &CDocObjectHost::`vftable'{for `IDocHostObject'};
  *((_QWORD *)this + 10) = &CDocObjectHost::`vftable'{for `IViewObject'};
  *((_QWORD *)this + 11) = &CDocObjectHost::`vftable'{for `IAdviseSink'};
  *((_QWORD *)this + 12) = &CDocObjectHost::`vftable'{for `IDispatch'};
  *((_QWORD *)this + 13) = &CDocObjectHost::`vftable'{for `IPropertyNotifySink'};
  *((_QWORD *)this + 14) = &CDocObjectHost::`vftable'{for `IOleControlSite'};
  *((_QWORD *)this + 15) = &CDocObjectHost::`vftable'{for `CImpWndProc'};
  *((_QWORD *)this + 17) = &CDocObjectHost::`vftable'{for `INewWindowManagerCallback'};
  *((_QWORD *)this + 18) = &CDocObjectHost::`vftable'{for `IPhishingFilterManagerCallback'};
  *((_QWORD *)this + 19) = &CDocObjectHost::`vftable'{for `IZoomEvents'};
  *((_QWORD *)this + 20) = &CDocObjectHost::`vftable'{for `ILayerStateEvents'};
  *((_QWORD *)this + 21) = &CDocObjectHost::`vftable'{for `ILayerCommandHandler'};
  *((_QWORD *)this + 26) = &CDocObjectHost::`vftable'{for `ILayerDynamicStateEvents'};
  *((_QWORD *)this + 27) = &CDocObjectHost::`vftable'{for `IFindInDocumentEvents'};
  *((_QWORD *)this + 28) = &CDocObjectHost::`vftable'{for `IDocHostUIAppProtocol'};
  *((_QWORD *)this + 29) = &CDocObjectHost::`vftable'{for `IObjectProvider'};
  *((_QWORD *)this + 30) = &CDocObjectHost::`vftable'{for `IBFCacheHost'};
  v2 = *((_WORD *)this + 124);
  if ( v2 )
  {
    GlobalDeleteAtom(v2);
    *((_WORD *)this + 124) = 0;
  }
  v3 = (OLECHAR *)*((_QWORD *)this + 279);
  if ( v3 )
    SysFreeString(v3);
  v4 = *((_QWORD *)this + 116);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
    ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 928);
  }
  v5 = (void *)*((_QWORD *)this + 79);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 77);
  if ( v6 )
  {
    LocalFree(v6);
    *((_QWORD *)this + 77) = 0;
  }
  v7 = (HACCEL)*((_QWORD *)this + 67);
  if ( v7 )
  {
    DestroyAcceleratorTable(v7);
    *((_QWORD *)this + 67) = 0;
  }
  ILFree(*((LPITEMIDLIST *)this + 84));
  *((_QWORD *)this + 84) = 0;
  CDocObjectHost::DestroyHostWindow(this);
  CDocObjectHost::_ResetOwners(this);
  v8 = *((_QWORD *)this + 65);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  _InterlockedDecrement(&g_cRefThisDll);
  TLSRelease();
  SysFreeString(*((BSTR *)this + 297));
  CoTaskMemFree(*((LPVOID *)this + 287));
  CoTaskMemFree(*((LPVOID *)this + 288));
  CDocObjectHost::CDOHBindStatusCallback::~CDOHBindStatusCallback((CDocObjectHost *)((char *)this + 1952));
  v9 = *((_QWORD *)this + 188);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = (VARIANTARG *)((char *)this + 1480);
  if ( *((_WORD *)this + 740) == 4095 )
    v10->vt = 8;
  VariantClear(v10);
  v11 = (VARIANTARG *)((char *)this + 1456);
  if ( *((_WORD *)this + 728) == 4095 )
    v11->vt = 8;
  VariantClear(v11);
  *((_QWORD *)this + 176) = &CConsentNotification::`vftable';
  DPA_EnumCallback(*((HDPA *)this + 177), DPA_ReleaseCB<IOpenServiceActivity>, 0);
  DPA_DeleteAllPtrs(*((HDPA *)this + 177));
  DPA_Destroy(*((HDPA *)this + 177));
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 174) = &CConsentNotification::`vftable';
  DPA_EnumCallback(*((HDPA *)this + 175), DPA_ReleaseCB<IOpenServiceActivity>, 0);
  DPA_DeleteAllPtrs(*((HDPA *)this + 175));
  DPA_Destroy(*((HDPA *)this + 175));
  *((_QWORD *)this + 175) = 0;
  *((_QWORD *)this + 172) = &CMediaCaptureConsent::`vftable';
  CConsentNotification::~CConsentNotification((CDocObjectHost *)((char *)this + 1376));
  *((_QWORD *)this + 170) = &CConsentNotification::`vftable';
  CConsentNotification::CleanupNotificationStack((CDocObjectHost *)((char *)this + 1360));
  DPA_Destroy(*((HDPA *)this + 171));
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 167) = &CGeolocationConsent::`vftable';
  DPA_EnumCallback(*((HDPA *)this + 169), DPA_HostConsentCleanup, 0);
  DPA_DeleteAllPtrs(*((HDPA *)this + 169));
  DPA_Destroy(*((HDPA *)this + 169));
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 167) = &CMediaCaptureConsent::`vftable';
  CConsentNotification::~CConsentNotification((CDocObjectHost *)((char *)this + 1336));
  v12 = (HICON)*((_QWORD *)this + 146);
  if ( v12 )
  {
    DestroyIcon(v12);
    *((_QWORD *)this + 146) = 0;
  }
  CSecurityBand::ResetCachedPageActionDetails((CDocObjectHost *)((char *)this + 992));
  SysFreeString(*((BSTR *)this + 140));
  CoTaskMemFree(*((LPVOID *)this + 128));
  v13 = (HWND)*((_QWORD *)this + 149);
  if ( v13 )
  {
    DestroyWindow(v13);
    *((_QWORD *)this + 149) = 0;
  }
  CSecurityBand::_DestroyIconIfNeeded((HICON *)this + 157);
  CSecurityBand::_DestroyIconIfNeeded((HICON *)this + 162);
  CSecurityBand::_DestroyIconIfNeeded((HICON *)this + 163);
  CSecurityBand::_DestroyIconIfNeeded((HICON *)this + 164);
  CSecurityBand::_DestroyIconIfNeeded((HICON *)this + 165);
  CSecurityBand::_DestroyIconIfNeeded((HICON *)this + 166);
  v14 = (void *)*((_QWORD *)this + 158);
  if ( v14 )
    DeleteObject(v14);
  v15 = (void *)*((_QWORD *)this + 159);
  if ( v15 )
    DeleteObject(v15);
  v16 = *((_QWORD *)this + 148);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = *((_QWORD *)this + 107);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = *((_QWORD *)this + 103);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = (struct _DSA *)*((_QWORD *)this + 76);
  if ( v19 )
  {
    DSA_Destroy(v19);
    *((_QWORD *)this + 76) = 0;
  }
  DSA_Destroy(*((HDSA *)this + 68));
  *((_QWORD *)this + 68) = 0;
  IEObjectSignature::CSignature<53440>::Validate((char *)this + 256);
  *((_WORD *)this + 128) = -11439;
  v20 = (OLECHAR *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 20) = &CLayerParticipant::`vftable'{for `ILayerStateEvents'};
  *((_QWORD *)this + 21) = &CLayerOwner<CTabLayer>::`vftable'{for `ILayerCommandHandler'};
  SysFreeString(v20);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>((char *)this + 176);
}

```

## disassembly

```asm
0x18003ee8c  push    rbx
0x18003ee8e  push    rbp
0x18003ee8f  push    rsi
0x18003ee90  push    rdi
0x18003ee91  push    r14
0x18003ee93  sub     rsp, 20h
0x18003ee97  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIHandler2@@@; const CDocObjectHost::`vftable'{for `IDocHostUIHandler2'}
0x18003ee9e  mov     rdi, rcx
0x18003eea1  mov     [rcx], rax
0x18003eea4  xor     r14d, r14d
0x18003eea7  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIHandlerPriv@@@; const CDocObjectHost::`vftable'{for `IDocHostUIHandlerPriv'}
0x18003eeae  mov     [rcx+8], rax
0x18003eeb2  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIControlPriv@@@; const CDocObjectHost::`vftable'{for `IDocHostUIControlPriv'}
0x18003eeb9  mov     [rcx+10h], rax
0x18003eebd  lea     rax, ??_7CDocObjectHost@@6BIDocHostShowUI@@@; const CDocObjectHost::`vftable'{for `IDocHostShowUI'}
0x18003eec4  mov     [rcx+18h], rax
0x18003eec8  lea     rax, ??_7CDocObjectHost@@6BIOleClientSite@@@; const CDocObjectHost::`vftable'{for `IOleClientSite'}
0x18003eecf  mov     [rcx+20h], rax
0x18003eed3  lea     rax, ??_7CDocObjectHost@@6BIOleDocumentSite@@@; const CDocObjectHost::`vftable'{for `IOleDocumentSite'}
0x18003eeda  mov     [rcx+28h], rax
0x18003eede  lea     rax, ??_7CDocObjectHost@@6BIOleCommandTarget@@@; const CDocObjectHost::`vftable'{for `IOleCommandTarget'}
0x18003eee5  mov     [rcx+30h], rax
0x18003eee9  lea     rax, ??_7CDocObjectHost@@6BIOleInPlaceSiteEx@@@; const CDocObjectHost::`vftable'{for `IOleInPlaceSiteEx'}
0x18003eef0  mov     [rcx+38h], rax
0x18003eef4  lea     rax, ??_7CDocObjectHost@@6BIServiceProvider@@@; const CDocObjectHost::`vftable'{for `IServiceProvider'}
0x18003eefb  mov     [rcx+40h], rax
0x18003eeff  lea     rax, ??_7CDocObjectHost@@6BIDocHostObject@@@; const CDocObjectHost::`vftable'{for `IDocHostObject'}
0x18003ef06  mov     [rcx+48h], rax
0x18003ef0a  lea     rax, ??_7CDocObjectHost@@6BIViewObject@@@; const CDocObjectHost::`vftable'{for `IViewObject'}
0x18003ef11  mov     [rcx+50h], rax
0x18003ef15  lea     rax, ??_7CDocObjectHost@@6BIAdviseSink@@@; const CDocObjectHost::`vftable'{for `IAdviseSink'}
0x18003ef1c  mov     [rcx+58h], rax
0x18003ef20  lea     rax, ??_7CDocObjectHost@@6BIDispatch@@@; const CDocObjectHost::`vftable'{for `IDispatch'}
0x18003ef27  mov     [rcx+60h], rax
0x18003ef2b  lea     rax, ??_7CDocObjectHost@@6BIPropertyNotifySink@@@; const CDocObjectHost::`vftable'{for `IPropertyNotifySink'}
0x18003ef32  mov     [rcx+68h], rax
0x18003ef36  lea     rax, ??_7CDocObjectHost@@6BIOleControlSite@@@; const CDocObjectHost::`vftable'{for `IOleControlSite'}
0x18003ef3d  mov     [rcx+70h], rax
0x18003ef41  lea     rax, ??_7CDocObjectHost@@6BCImpWndProc@@@; const CDocObjectHost::`vftable'{for `CImpWndProc'}
0x18003ef48  mov     [rcx+78h], rax
0x18003ef4c  lea     rax, ??_7CDocObjectHost@@6BINewWindowManagerCallback@@@; const CDocObjectHost::`vftable'{for `INewWindowManagerCallback'}
0x18003ef53  mov     [rcx+88h], rax
0x18003ef5a  lea     rax, ??_7CDocObjectHost@@6BIPhishingFilterManagerCallback@@@; const CDocObjectHost::`vftable'{for `IPhishingFilterManagerCallback'}
0x18003ef61  mov     [rcx+90h], rax
0x18003ef68  lea     rax, ??_7CDocObjectHost@@6BIZoomEvents@@@; const CDocObjectHost::`vftable'{for `IZoomEvents'}
0x18003ef6f  mov     [rcx+98h], rax
0x18003ef76  lea     rax, ??_7CDocObjectHost@@6BILayerStateEvents@@@; const CDocObjectHost::`vftable'{for `ILayerStateEvents'}
0x18003ef7d  mov     [rcx+0A0h], rax
0x18003ef84  lea     rax, ??_7CDocObjectHost@@6BILayerCommandHandler@@@; const CDocObjectHost::`vftable'{for `ILayerCommandHandler'}
0x18003ef8b  mov     [rcx+0A8h], rax
0x18003ef92  lea     rax, ??_7CDocObjectHost@@6BILayerDynamicStateEvents@@@; const CDocObjectHost::`vftable'{for `ILayerDynamicStateEvents'}
0x18003ef99  mov     [rcx+0D0h], rax
0x18003efa0  lea     rax, ??_7CDocObjectHost@@6BIFindInDocumentEvents@@@; const CDocObjectHost::`vftable'{for `IFindInDocumentEvents'}
0x18003efa7  mov     [rcx+0D8h], rax
0x18003efae  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIAppProtocol@@@; const CDocObjectHost::`vftable'{for `IDocHostUIAppProtocol'}
0x18003efb5  mov     [rcx+0E0h], rax
0x18003efbc  lea     rax, ??_7CDocObjectHost@@6BIObjectProvider@@@; const CDocObjectHost::`vftable'{for `IObjectProvider'}
0x18003efc3  mov     [rcx+0E8h], rax
0x18003efca  lea     rax, ??_7CDocObjectHost@@6BIBFCacheHost@@@; const CDocObjectHost::`vftable'{for `IBFCacheHost'}
0x18003efd1  mov     [rcx+0F0h], rax
0x18003efd8  movzx   ecx, word ptr [rcx+0F8h]; nAtom
0x18003efdf  test    cx, cx
0x18003efe2  jz      short loc_18003EFF2
0x18003efe4  call    cs:__imp_GlobalDeleteAtom
0x18003efea  mov     [rdi+0F8h], r14w
0x18003eff2  mov     rcx, [rdi+8B8h]; bstrString
0x18003eff9  test    rcx, rcx
0x18003effc  jz      short loc_18003F004
0x18003effe  call    cs:__imp_SysFreeString
0x18003f004  lea     rbx, [rdi+3A0h]
0x18003f00b  mov     rcx, [rbx]
0x18003f00e  test    rcx, rcx
0x18003f011  jz      short loc_18003F027
0x18003f013  mov     rax, [rcx]
0x18003f016  mov     rax, [rax+38h]
0x18003f01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f01f  mov     rcx, rbx
0x18003f022  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x18003f027  mov     rcx, [rdi+278h]; pv
0x18003f02e  test    rcx, rcx
0x18003f031  jz      short loc_18003F039
0x18003f033  call    cs:__imp_CoTaskMemFree
0x18003f039  mov     rcx, [rdi+268h]; hMem
0x18003f040  test    rcx, rcx
0x18003f043  jz      short loc_18003F052
0x18003f045  call    cs:__imp_LocalFree
0x18003f04b  mov     [rdi+268h], r14
0x18003f052  mov     rcx, [rdi+218h]; hAccel
0x18003f059  test    rcx, rcx
0x18003f05c  jz      short loc_18003F06B
0x18003f05e  call    cs:__imp_DestroyAcceleratorTable
0x18003f064  mov     [rdi+218h], r14
0x18003f06b  mov     rcx, [rdi+2A0h]; pidl
0x18003f072  call    cs:__imp_ILFree
0x18003f078  mov     rcx, rdi; this
0x18003f07b  mov     [rdi+2A0h], r14
0x18003f082  call    ?DestroyHostWindow@CDocObjectHost@@QEAAXXZ; CDocObjectHost::DestroyHostWindow(void)
0x18003f087  mov     rcx, rdi; this
0x18003f08a  call    ?_ResetOwners@CDocObjectHost@@IEAAXXZ; CDocObjectHost::_ResetOwners(void)
0x18003f08f  mov     rcx, [rdi+208h]
0x18003f096  test    rcx, rcx
0x18003f099  jz      short loc_18003F0A7
0x18003f09b  mov     rax, [rcx]
0x18003f09e  mov     rax, [rax+10h]
0x18003f0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0a7  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18003f0ae  call    ?TLSRelease@@YAKXZ; TLSRelease(void)
0x18003f0b3  mov     rcx, [rdi+948h]; bstrString
0x18003f0ba  call    cs:__imp_SysFreeString
0x18003f0c0  mov     rcx, [rdi+8F8h]; pv
0x18003f0c7  call    cs:__imp_CoTaskMemFree
0x18003f0cd  mov     rcx, [rdi+900h]; pv
0x18003f0d4  call    cs:__imp_CoTaskMemFree
0x18003f0da  lea     rcx, [rdi+7A0h]; this
0x18003f0e1  call    ??1CDOHBindStatusCallback@CDocObjectHost@@IEAA@XZ; CDocObjectHost::CDOHBindStatusCallback::~CDOHBindStatusCallback(void)
0x18003f0e6  mov     rcx, [rdi+5E0h]
0x18003f0ed  test    rcx, rcx
0x18003f0f0  jz      short loc_18003F0FE
0x18003f0f2  mov     rax, [rcx]
0x18003f0f5  mov     rax, [rax+10h]
0x18003f0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0fe  lea     rcx, [rdi+5C8h]; pvarg
0x18003f105  mov     esi, 0FFFh
0x18003f10a  mov     ebx, 8
0x18003f10f  cmp     [rcx], si
0x18003f112  jnz     short loc_18003F117
0x18003f114  mov     [rcx], bx
0x18003f117  call    cs:__imp_VariantClear
0x18003f11d  lea     rcx, [rdi+5B0h]; pvarg
0x18003f124  cmp     [rcx], si
0x18003f127  jnz     short loc_18003F12C
0x18003f129  mov     [rcx], bx
0x18003f12c  call    cs:__imp_VariantClear
0x18003f132  lea     rbp, ??_7CConsentNotification@@6B@; const CConsentNotification::`vftable'
0x18003f139  xor     r8d, r8d; pData
0x18003f13c  mov     [rdi+580h], rbp
0x18003f143  lea     rdx, ??$DPA_ReleaseCB@UIOpenServiceActivity@@@@YAHPEAUIOpenServiceActivity@@PEAX@Z; pfnCB
0x18003f14a  mov     rcx, [rdi+588h]; hdpa
0x18003f151  call    cs:__imp_DPA_EnumCallback
0x18003f157  mov     rcx, [rdi+588h]; hdpa
0x18003f15e  call    cs:__imp_DPA_DeleteAllPtrs
0x18003f164  mov     rcx, [rdi+588h]; hdpa
0x18003f16b  call    cs:__imp_DPA_Destroy
0x18003f171  mov     [rdi+588h], r14
0x18003f178  lea     rdx, ??$DPA_ReleaseCB@UIOpenServiceActivity@@@@YAHPEAUIOpenServiceActivity@@PEAX@Z; pfnCB
0x18003f17f  mov     [rdi+570h], rbp
0x18003f186  xor     r8d, r8d; pData
0x18003f189  mov     rcx, [rdi+578h]; hdpa
0x18003f190  call    cs:__imp_DPA_EnumCallback
0x18003f196  mov     rcx, [rdi+578h]; hdpa
0x18003f19d  call    cs:__imp_DPA_DeleteAllPtrs
0x18003f1a3  mov     rcx, [rdi+578h]; hdpa
0x18003f1aa  call    cs:__imp_DPA_Destroy
0x18003f1b0  lea     rcx, [rdi+560h]; this
0x18003f1b7  mov     [rdi+578h], r14
0x18003f1be  lea     rsi, ??_7CMediaCaptureConsent@@6B@; const CMediaCaptureConsent::`vftable'
0x18003f1c5  mov     [rcx], rsi
0x18003f1c8  call    ??1CConsentNotification@@UEAA@XZ; CConsentNotification::~CConsentNotification(void)
0x18003f1cd  lea     rbx, [rdi+550h]
0x18003f1d4  mov     rcx, rbx; this
0x18003f1d7  mov     [rbx], rbp
0x18003f1da  call    ?CleanupNotificationStack@CConsentNotification@@QEAAJXZ; CConsentNotification::CleanupNotificationStack(void)
0x18003f1df  mov     rcx, [rbx+8]; hdpa
0x18003f1e3  call    cs:__imp_DPA_Destroy
0x18003f1e9  mov     [rbx+8], r14
0x18003f1ed  lea     rax, ??_7CGeolocationConsent@@6B@; const CGeolocationConsent::`vftable'
0x18003f1f4  lea     rbx, [rdi+538h]
0x18003f1fb  xor     r8d, r8d; pData
0x18003f1fe  mov     [rbx], rax
0x18003f201  lea     rdx, ?DPA_HostConsentCleanup@@YAHPEAUHOSTCONSENT@@PEAX@Z; pfnCB
0x18003f208  mov     rcx, [rbx+10h]; hdpa
0x18003f20c  call    cs:__imp_DPA_EnumCallback
0x18003f212  mov     rcx, [rbx+10h]; hdpa
0x18003f216  call    cs:__imp_DPA_DeleteAllPtrs
0x18003f21c  mov     rcx, [rbx+10h]; hdpa
0x18003f220  call    cs:__imp_DPA_Destroy
0x18003f226  mov     [rbx+10h], r14
0x18003f22a  mov     rcx, rbx; this
0x18003f22d  mov     [rbx], rsi
0x18003f230  call    ??1CConsentNotification@@UEAA@XZ; CConsentNotification::~CConsentNotification(void)
0x18003f235  lea     rbx, [rdi+3E0h]
0x18003f23c  mov     rcx, [rbx+0B0h]; hIcon
0x18003f243  test    rcx, rcx
0x18003f246  jz      short loc_18003F255
0x18003f248  call    cs:__imp_DestroyIcon
0x18003f24e  mov     [rbx+0B0h], r14
0x18003f255  mov     rcx, rbx; this
0x18003f258  call    ?ResetCachedPageActionDetails@CSecurityBand@@QEAAXXZ; CSecurityBand::ResetCachedPageActionDetails(void)
0x18003f25d  mov     rcx, [rbx+80h]; bstrString
0x18003f264  call    cs:__imp_SysFreeString
0x18003f26a  mov     rcx, [rbx+20h]; pv
0x18003f26e  call    cs:__imp_CoTaskMemFree
0x18003f274  mov     rcx, [rbx+0C8h]; hWnd
0x18003f27b  test    rcx, rcx
0x18003f27e  jz      short loc_18003F28D
0x18003f280  call    cs:__imp_DestroyWindow
0x18003f286  mov     [rbx+0C8h], r14
0x18003f28d  lea     rcx, [rbx+108h]; HICON *
0x18003f294  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18003f299  lea     rcx, [rbx+130h]; HICON *
0x18003f2a0  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18003f2a5  lea     rcx, [rbx+138h]; HICON *
0x18003f2ac  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18003f2b1  lea     rcx, [rbx+140h]; HICON *
0x18003f2b8  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18003f2bd  lea     rcx, [rbx+148h]; HICON *
0x18003f2c4  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18003f2c9  lea     rcx, [rbx+150h]; HICON *
0x18003f2d0  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18003f2d5  mov     rcx, [rbx+110h]; ho
0x18003f2dc  test    rcx, rcx
0x18003f2df  jz      short loc_18003F2E7
0x18003f2e1  call    cs:__imp_DeleteObject
0x18003f2e7  mov     rcx, [rbx+118h]; ho
0x18003f2ee  test    rcx, rcx
0x18003f2f1  jz      short loc_18003F2F9
0x18003f2f3  call    cs:__imp_DeleteObject
0x18003f2f9  mov     rcx, [rbx+0C0h]
0x18003f300  test    rcx, rcx
0x18003f303  jz      short loc_18003F311
0x18003f305  mov     rax, [rcx]
0x18003f308  mov     rax, [rax+10h]
0x18003f30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f311  mov     rcx, [rdi+358h]
0x18003f318  test    rcx, rcx
0x18003f31b  jz      short loc_18003F329
0x18003f31d  mov     rax, [rcx]
0x18003f320  mov     rax, [rax+10h]
0x18003f324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f329  mov     rcx, [rdi+338h]
0x18003f330  test    rcx, rcx
0x18003f333  jz      short loc_18003F341
0x18003f335  mov     rax, [rcx]
0x18003f338  mov     rax, [rax+10h]
0x18003f33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f341  mov     rcx, [rdi+260h]; hdsa
0x18003f348  test    rcx, rcx
0x18003f34b  jz      short loc_18003F35A
0x18003f34d  call    cs:__imp_DSA_Destroy
0x18003f353  mov     [rdi+260h], r14
0x18003f35a  mov     rcx, [rdi+220h]; hdsa
0x18003f361  call    cs:__imp_DSA_Destroy
0x18003f367  lea     rbx, [rdi+100h]
0x18003f36e  mov     [rdi+220h], r14
0x18003f375  mov     rcx, rbx
0x18003f378  call    ?Validate@?$CSignature@$0NAMA@@IEObjectSignature@@QEBAXXZ; IEObjectSignature::CSignature<53440>::Validate(void)
0x18003f37d  mov     word ptr [rbx], 0D351h
0x18003f382  lea     rax, ??_7CLayerParticipant@@6BILayerStateEvents@@@; const CLayerParticipant::`vftable'{for `ILayerStateEvents'}
0x18003f389  mov     rcx, [rdi+0B8h]; bstrString
0x18003f390  mov     [rdi+0A0h], rax
0x18003f397  lea     rax, ??_7?$CLayerOwner@VCTabLayer@@@@6BILayerCommandHandler@@@; const CLayerOwner<CTabLayer>::`vftable'{for `ILayerCommandHandler'}
0x18003f39e  mov     [rdi+0A8h], rax
0x18003f3a5  call    cs:__imp_SysFreeString
0x18003f3ab  lea     rcx, [rdi+0B0h]; void *
0x18003f3b2  add     rsp, 20h
0x18003f3b6  pop     r14
0x18003f3b8  pop     rdi
0x18003f3b9  pop     rsi
0x18003f3ba  pop     rbp
0x18003f3bb  pop     rbx
0x18003f3bc  jmp     ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
```
