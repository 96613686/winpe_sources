# CDocObjectHost::~CDocObjectHost(void)

- ea: `0x180040ee8`
- end: `0x1800414d1`
- name: `??1CDocObjectHost@@MEAA@XZ`
- size: `1513`
- prototype: `void __fastcall(CDocObjectHost *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180140bf0`

## callees

- `0x180005030`
- `0x18001546c`
- `0x180040ee8`
- `0x1800414d8`
- `0x180041590`
- `0x180041684`
- `0x1800418a0`
- `0x180041a64`
- `0x18008b1d0`
- `0x18008b210`
- `0x18008f36c`
- `0x1800965d0`
- `0x180594010`

## import_xrefs

- `KERNEL32!GlobalDeleteAtom` at `0x180041040`
- `KERNEL32!GlobalDeleteAtom` at `0x180041040`
- `KERNEL32!LocalFree` at `0x1800410b3`
- `KERNEL32!LocalFree` at `0x1800410b3`
- `GDI32!DeleteObject` at `0x1800413d3`
- `GDI32!DeleteObject` at `0x1800413eb`
- `GDI32!DeleteObject` at `0x1800413d3`
- `GDI32!DeleteObject` at `0x1800413eb`
- `USER32!DestroyWindow` at `0x18004136c`
- `USER32!DestroyWindow` at `0x18004136c`
- `USER32!DestroyIcon` at `0x180041322`
- `USER32!DestroyIcon` at `0x180041322`
- `USER32!DestroyAcceleratorTable` at `0x1800410d2`
- `USER32!DestroyAcceleratorTable` at `0x1800410d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180041060`
- `OLEAUT32!__imp_SysFreeString` at `0x18004113a`
- `OLEAUT32!__imp_SysFreeString` at `0x180041344`
- `OLEAUT32!__imp_SysFreeString` at `0x1800414af`
- `OLEAUT32!__imp_SysFreeString` at `0x180041060`
- `OLEAUT32!__imp_SysFreeString` at `0x18004113a`
- `OLEAUT32!__imp_SysFreeString` at `0x180041344`
- `OLEAUT32!__imp_SysFreeString` at `0x1800414af`
- `OLEAUT32!__imp_VariantClear` at `0x1800411a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800411c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800411a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800411c4`
- `SHELL32!__imp_ILFree` at `0x1800410ec`
- `SHELL32!__imp_ILFree` at `0x1800410ec`
- `iertutil!__imp_DSA_Destroy` at `0x18004144b`
- `iertutil!__imp_DSA_Destroy` at `0x180041465`
- `iertutil!__imp_DSA_Destroy` at `0x18004144b`
- `iertutil!__imp_DSA_Destroy` at `0x180041465`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x180041202`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x180041253`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x1800412e4`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x180041202`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x180041253`
- `iertutil!__imp_DPA_DeleteAllPtrs` at `0x1800412e4`
- `iertutil!__imp_DPA_Destroy` at `0x180041215`
- `iertutil!__imp_DPA_Destroy` at `0x180041266`
- `iertutil!__imp_DPA_Destroy` at `0x1800412a5`
- `iertutil!__imp_DPA_Destroy` at `0x1800412f4`
- `iertutil!__imp_DPA_Destroy` at `0x180041215`
- `iertutil!__imp_DPA_Destroy` at `0x180041266`
- `iertutil!__imp_DPA_Destroy` at `0x1800412a5`
- `iertutil!__imp_DPA_Destroy` at `0x1800412f4`
- `iertutil!__imp_DPA_EnumCallback` at `0x1800411ef`
- `iertutil!__imp_DPA_EnumCallback` at `0x180041240`
- `iertutil!__imp_DPA_EnumCallback` at `0x1800412d4`
- `iertutil!__imp_DPA_EnumCallback` at `0x1800411ef`
- `iertutil!__imp_DPA_EnumCallback` at `0x180041240`
- `iertutil!__imp_DPA_EnumCallback` at `0x1800412d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18004109b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18004114d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180041160`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180041354`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18004109b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18004114d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180041160`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180041354`

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
0x180040ee8  push    rbx
0x180040eea  push    rbp
0x180040eeb  push    rsi
0x180040eec  push    rdi
0x180040eed  push    r14
0x180040eef  sub     rsp, 20h
0x180040ef3  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIHandler2@@@; const CDocObjectHost::`vftable'{for `IDocHostUIHandler2'}
0x180040efa  mov     rdi, rcx
0x180040efd  mov     [rcx], rax
0x180040f00  xor     r14d, r14d
0x180040f03  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIHandlerPriv@@@; const CDocObjectHost::`vftable'{for `IDocHostUIHandlerPriv'}
0x180040f0a  mov     [rcx+8], rax
0x180040f0e  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIControlPriv@@@; const CDocObjectHost::`vftable'{for `IDocHostUIControlPriv'}
0x180040f15  mov     [rcx+10h], rax
0x180040f19  lea     rax, ??_7CDocObjectHost@@6BIDocHostShowUI@@@; const CDocObjectHost::`vftable'{for `IDocHostShowUI'}
0x180040f20  mov     [rcx+18h], rax
0x180040f24  lea     rax, ??_7CDocObjectHost@@6BIOleClientSite@@@; const CDocObjectHost::`vftable'{for `IOleClientSite'}
0x180040f2b  mov     [rcx+20h], rax
0x180040f2f  lea     rax, ??_7CDocObjectHost@@6BIOleDocumentSite@@@; const CDocObjectHost::`vftable'{for `IOleDocumentSite'}
0x180040f36  mov     [rcx+28h], rax
0x180040f3a  lea     rax, ??_7CDocObjectHost@@6BIOleCommandTarget@@@; const CDocObjectHost::`vftable'{for `IOleCommandTarget'}
0x180040f41  mov     [rcx+30h], rax
0x180040f45  lea     rax, ??_7CDocObjectHost@@6BIOleInPlaceSiteEx@@@; const CDocObjectHost::`vftable'{for `IOleInPlaceSiteEx'}
0x180040f4c  mov     [rcx+38h], rax
0x180040f50  lea     rax, ??_7CDocObjectHost@@6BIServiceProvider@@@; const CDocObjectHost::`vftable'{for `IServiceProvider'}
0x180040f57  mov     [rcx+40h], rax
0x180040f5b  lea     rax, ??_7CDocObjectHost@@6BIDocHostObject@@@; const CDocObjectHost::`vftable'{for `IDocHostObject'}
0x180040f62  mov     [rcx+48h], rax
0x180040f66  lea     rax, ??_7CDocObjectHost@@6BIViewObject@@@; const CDocObjectHost::`vftable'{for `IViewObject'}
0x180040f6d  mov     [rcx+50h], rax
0x180040f71  lea     rax, ??_7CDocObjectHost@@6BIAdviseSink@@@; const CDocObjectHost::`vftable'{for `IAdviseSink'}
0x180040f78  mov     [rcx+58h], rax
0x180040f7c  lea     rax, ??_7CDocObjectHost@@6BIDispatch@@@; const CDocObjectHost::`vftable'{for `IDispatch'}
0x180040f83  mov     [rcx+60h], rax
0x180040f87  lea     rax, ??_7CDocObjectHost@@6BIPropertyNotifySink@@@; const CDocObjectHost::`vftable'{for `IPropertyNotifySink'}
0x180040f8e  mov     [rcx+68h], rax
0x180040f92  lea     rax, ??_7CDocObjectHost@@6BIOleControlSite@@@; const CDocObjectHost::`vftable'{for `IOleControlSite'}
0x180040f99  mov     [rcx+70h], rax
0x180040f9d  lea     rax, ??_7CDocObjectHost@@6BCImpWndProc@@@; const CDocObjectHost::`vftable'{for `CImpWndProc'}
0x180040fa4  mov     [rcx+78h], rax
0x180040fa8  lea     rax, ??_7CDocObjectHost@@6BINewWindowManagerCallback@@@; const CDocObjectHost::`vftable'{for `INewWindowManagerCallback'}
0x180040faf  mov     [rcx+88h], rax
0x180040fb6  lea     rax, ??_7CDocObjectHost@@6BIPhishingFilterManagerCallback@@@; const CDocObjectHost::`vftable'{for `IPhishingFilterManagerCallback'}
0x180040fbd  mov     [rcx+90h], rax
0x180040fc4  lea     rax, ??_7CDocObjectHost@@6BIZoomEvents@@@; const CDocObjectHost::`vftable'{for `IZoomEvents'}
0x180040fcb  mov     [rcx+98h], rax
0x180040fd2  lea     rax, ??_7CDocObjectHost@@6BILayerStateEvents@@@; const CDocObjectHost::`vftable'{for `ILayerStateEvents'}
0x180040fd9  mov     [rcx+0A0h], rax
0x180040fe0  lea     rax, ??_7CDocObjectHost@@6BILayerCommandHandler@@@; const CDocObjectHost::`vftable'{for `ILayerCommandHandler'}
0x180040fe7  mov     [rcx+0A8h], rax
0x180040fee  lea     rax, ??_7CDocObjectHost@@6BILayerDynamicStateEvents@@@; const CDocObjectHost::`vftable'{for `ILayerDynamicStateEvents'}
0x180040ff5  mov     [rcx+0D0h], rax
0x180040ffc  lea     rax, ??_7CDocObjectHost@@6BIFindInDocumentEvents@@@; const CDocObjectHost::`vftable'{for `IFindInDocumentEvents'}
0x180041003  mov     [rcx+0D8h], rax
0x18004100a  lea     rax, ??_7CDocObjectHost@@6BIDocHostUIAppProtocol@@@; const CDocObjectHost::`vftable'{for `IDocHostUIAppProtocol'}
0x180041011  mov     [rcx+0E0h], rax
0x180041018  lea     rax, ??_7CDocObjectHost@@6BIObjectProvider@@@; const CDocObjectHost::`vftable'{for `IObjectProvider'}
0x18004101f  mov     [rcx+0E8h], rax
0x180041026  lea     rax, ??_7CDocObjectHost@@6BIBFCacheHost@@@; const CDocObjectHost::`vftable'{for `IBFCacheHost'}
0x18004102d  mov     [rcx+0F0h], rax
0x180041034  movzx   ecx, word ptr [rcx+0F8h]; nAtom
0x18004103b  test    cx, cx
0x18004103e  jz      short loc_180041054
0x180041040  call    cs:__imp_GlobalDeleteAtom
0x180041047  nop     dword ptr [rax+rax+00h]
0x18004104c  mov     [rdi+0F8h], r14w
0x180041054  mov     rcx, [rdi+8B8h]; bstrString
0x18004105b  test    rcx, rcx
0x18004105e  jz      short loc_18004106C
0x180041060  call    cs:__imp_SysFreeString
0x180041067  nop     dword ptr [rax+rax+00h]
0x18004106c  lea     rbx, [rdi+3A0h]
0x180041073  mov     rcx, [rbx]
0x180041076  test    rcx, rcx
0x180041079  jz      short loc_18004108F
0x18004107b  mov     rax, [rcx]
0x18004107e  mov     rax, [rax+38h]
0x180041082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041087  mov     rcx, rbx
0x18004108a  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x18004108f  mov     rcx, [rdi+278h]; pv
0x180041096  test    rcx, rcx
0x180041099  jz      short loc_1800410A7
0x18004109b  call    cs:__imp_CoTaskMemFree
0x1800410a2  nop     dword ptr [rax+rax+00h]
0x1800410a7  mov     rcx, [rdi+268h]; hMem
0x1800410ae  test    rcx, rcx
0x1800410b1  jz      short loc_1800410C6
0x1800410b3  call    cs:__imp_LocalFree
0x1800410ba  nop     dword ptr [rax+rax+00h]
0x1800410bf  mov     [rdi+268h], r14
0x1800410c6  mov     rcx, [rdi+218h]; hAccel
0x1800410cd  test    rcx, rcx
0x1800410d0  jz      short loc_1800410E5
0x1800410d2  call    cs:__imp_DestroyAcceleratorTable
0x1800410d9  nop     dword ptr [rax+rax+00h]
0x1800410de  mov     [rdi+218h], r14
0x1800410e5  mov     rcx, [rdi+2A0h]; pidl
0x1800410ec  call    cs:__imp_ILFree
0x1800410f3  nop     dword ptr [rax+rax+00h]
0x1800410f8  mov     rcx, rdi; this
0x1800410fb  mov     [rdi+2A0h], r14
0x180041102  call    ?DestroyHostWindow@CDocObjectHost@@QEAAXXZ; CDocObjectHost::DestroyHostWindow(void)
0x180041107  mov     rcx, rdi; this
0x18004110a  call    ?_ResetOwners@CDocObjectHost@@IEAAXXZ; CDocObjectHost::_ResetOwners(void)
0x18004110f  mov     rcx, [rdi+208h]
0x180041116  test    rcx, rcx
0x180041119  jz      short loc_180041127
0x18004111b  mov     rax, [rcx]
0x18004111e  mov     rax, [rax+10h]
0x180041122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041127  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18004112e  call    ?TLSRelease@@YAKXZ; TLSRelease(void)
0x180041133  mov     rcx, [rdi+948h]; bstrString
0x18004113a  call    cs:__imp_SysFreeString
0x180041141  nop     dword ptr [rax+rax+00h]
0x180041146  mov     rcx, [rdi+8F8h]; pv
0x18004114d  call    cs:__imp_CoTaskMemFree
0x180041154  nop     dword ptr [rax+rax+00h]
0x180041159  mov     rcx, [rdi+900h]; pv
0x180041160  call    cs:__imp_CoTaskMemFree
0x180041167  nop     dword ptr [rax+rax+00h]
0x18004116c  lea     rcx, [rdi+7A0h]; this
0x180041173  call    ??1CDOHBindStatusCallback@CDocObjectHost@@IEAA@XZ; CDocObjectHost::CDOHBindStatusCallback::~CDOHBindStatusCallback(void)
0x180041178  mov     rcx, [rdi+5E0h]
0x18004117f  test    rcx, rcx
0x180041182  jz      short loc_180041190
0x180041184  mov     rax, [rcx]
0x180041187  mov     rax, [rax+10h]
0x18004118b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041190  lea     rcx, [rdi+5C8h]; pvarg
0x180041197  mov     esi, 0FFFh
0x18004119c  mov     ebx, 8
0x1800411a1  cmp     [rcx], si
0x1800411a4  jnz     short loc_1800411A9
0x1800411a6  mov     [rcx], bx
0x1800411a9  call    cs:__imp_VariantClear
0x1800411b0  nop     dword ptr [rax+rax+00h]
0x1800411b5  lea     rcx, [rdi+5B0h]; pvarg
0x1800411bc  cmp     [rcx], si
0x1800411bf  jnz     short loc_1800411C4
0x1800411c1  mov     [rcx], bx
0x1800411c4  call    cs:__imp_VariantClear
0x1800411cb  nop     dword ptr [rax+rax+00h]
0x1800411d0  lea     rbp, ??_7CConsentNotification@@6B@; const CConsentNotification::`vftable'
0x1800411d7  xor     r8d, r8d; pData
0x1800411da  mov     [rdi+580h], rbp
0x1800411e1  lea     rdx, ??$DPA_ReleaseCB@UIOpenServiceActivity@@@@YAHPEAUIOpenServiceActivity@@PEAX@Z; pfnCB
0x1800411e8  mov     rcx, [rdi+588h]; hdpa
0x1800411ef  call    cs:__imp_DPA_EnumCallback
0x1800411f6  nop     dword ptr [rax+rax+00h]
0x1800411fb  mov     rcx, [rdi+588h]; hdpa
0x180041202  call    cs:__imp_DPA_DeleteAllPtrs
0x180041209  nop     dword ptr [rax+rax+00h]
0x18004120e  mov     rcx, [rdi+588h]; hdpa
0x180041215  call    cs:__imp_DPA_Destroy
0x18004121c  nop     dword ptr [rax+rax+00h]
0x180041221  mov     [rdi+588h], r14
0x180041228  lea     rdx, ??$DPA_ReleaseCB@UIOpenServiceActivity@@@@YAHPEAUIOpenServiceActivity@@PEAX@Z; pfnCB
0x18004122f  mov     [rdi+570h], rbp
0x180041236  xor     r8d, r8d; pData
0x180041239  mov     rcx, [rdi+578h]; hdpa
0x180041240  call    cs:__imp_DPA_EnumCallback
0x180041247  nop     dword ptr [rax+rax+00h]
0x18004124c  mov     rcx, [rdi+578h]; hdpa
0x180041253  call    cs:__imp_DPA_DeleteAllPtrs
0x18004125a  nop     dword ptr [rax+rax+00h]
0x18004125f  mov     rcx, [rdi+578h]; hdpa
0x180041266  call    cs:__imp_DPA_Destroy
0x18004126d  nop     dword ptr [rax+rax+00h]
0x180041272  lea     rcx, [rdi+560h]; this
0x180041279  mov     [rdi+578h], r14
0x180041280  lea     rsi, ??_7CMediaCaptureConsent@@6B@; const CMediaCaptureConsent::`vftable'
0x180041287  mov     [rcx], rsi
0x18004128a  call    ??1CConsentNotification@@UEAA@XZ; CConsentNotification::~CConsentNotification(void)
0x18004128f  lea     rbx, [rdi+550h]
0x180041296  mov     rcx, rbx; this
0x180041299  mov     [rbx], rbp
0x18004129c  call    ?CleanupNotificationStack@CConsentNotification@@QEAAJXZ; CConsentNotification::CleanupNotificationStack(void)
0x1800412a1  mov     rcx, [rbx+8]; hdpa
0x1800412a5  call    cs:__imp_DPA_Destroy
0x1800412ac  nop     dword ptr [rax+rax+00h]
0x1800412b1  mov     [rbx+8], r14
0x1800412b5  lea     rax, ??_7CGeolocationConsent@@6B@; const CGeolocationConsent::`vftable'
0x1800412bc  lea     rbx, [rdi+538h]
0x1800412c3  xor     r8d, r8d; pData
0x1800412c6  mov     [rbx], rax
0x1800412c9  lea     rdx, ?DPA_HostConsentCleanup@@YAHPEAUHOSTCONSENT@@PEAX@Z; pfnCB
0x1800412d0  mov     rcx, [rbx+10h]; hdpa
0x1800412d4  call    cs:__imp_DPA_EnumCallback
0x1800412db  nop     dword ptr [rax+rax+00h]
0x1800412e0  mov     rcx, [rbx+10h]; hdpa
0x1800412e4  call    cs:__imp_DPA_DeleteAllPtrs
0x1800412eb  nop     dword ptr [rax+rax+00h]
0x1800412f0  mov     rcx, [rbx+10h]; hdpa
0x1800412f4  call    cs:__imp_DPA_Destroy
0x1800412fb  nop     dword ptr [rax+rax+00h]
0x180041300  mov     [rbx+10h], r14
0x180041304  mov     rcx, rbx; this
0x180041307  mov     [rbx], rsi
0x18004130a  call    ??1CConsentNotification@@UEAA@XZ; CConsentNotification::~CConsentNotification(void)
0x18004130f  lea     rbx, [rdi+3E0h]
0x180041316  mov     rcx, [rbx+0B0h]; hIcon
0x18004131d  test    rcx, rcx
0x180041320  jz      short loc_180041335
0x180041322  call    cs:__imp_DestroyIcon
0x180041329  nop     dword ptr [rax+rax+00h]
0x18004132e  mov     [rbx+0B0h], r14
0x180041335  mov     rcx, rbx; this
0x180041338  call    ?ResetCachedPageActionDetails@CSecurityBand@@QEAAXXZ; CSecurityBand::ResetCachedPageActionDetails(void)
0x18004133d  mov     rcx, [rbx+80h]; bstrString
0x180041344  call    cs:__imp_SysFreeString
0x18004134b  nop     dword ptr [rax+rax+00h]
0x180041350  mov     rcx, [rbx+20h]; pv
0x180041354  call    cs:__imp_CoTaskMemFree
0x18004135b  nop     dword ptr [rax+rax+00h]
0x180041360  mov     rcx, [rbx+0C8h]; hWnd
0x180041367  test    rcx, rcx
0x18004136a  jz      short loc_18004137F
0x18004136c  call    cs:__imp_DestroyWindow
0x180041373  nop     dword ptr [rax+rax+00h]
0x180041378  mov     [rbx+0C8h], r14
0x18004137f  lea     rcx, [rbx+108h]; HICON *
0x180041386  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x18004138b  lea     rcx, [rbx+130h]; HICON *
0x180041392  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x180041397  lea     rcx, [rbx+138h]; HICON *
0x18004139e  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x1800413a3  lea     rcx, [rbx+140h]; HICON *
0x1800413aa  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x1800413af  lea     rcx, [rbx+148h]; HICON *
0x1800413b6  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x1800413bb  lea     rcx, [rbx+150h]; HICON *
0x1800413c2  call    ?_DestroyIconIfNeeded@CSecurityBand@@CAXPEAPEAUHICON__@@@Z; CSecurityBand::_DestroyIconIfNeeded(HICON__ * *)
0x1800413c7  mov     rcx, [rbx+110h]; ho
0x1800413ce  test    rcx, rcx
0x1800413d1  jz      short loc_1800413DF
0x1800413d3  call    cs:__imp_DeleteObject
0x1800413da  nop     dword ptr [rax+rax+00h]
0x1800413df  mov     rcx, [rbx+118h]; ho
0x1800413e6  test    rcx, rcx
0x1800413e9  jz      short loc_1800413F7
0x1800413eb  call    cs:__imp_DeleteObject
0x1800413f2  nop     dword ptr [rax+rax+00h]
0x1800413f7  mov     rcx, [rbx+0C0h]
0x1800413fe  test    rcx, rcx
0x180041401  jz      short loc_18004140F
0x180041403  mov     rax, [rcx]
0x180041406  mov     rax, [rax+10h]
0x18004140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004140f  mov     rcx, [rdi+358h]
0x180041416  test    rcx, rcx
0x180041419  jz      short loc_180041427
0x18004141b  mov     rax, [rcx]
0x18004141e  mov     rax, [rax+10h]
0x180041422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041427  mov     rcx, [rdi+338h]
0x18004142e  test    rcx, rcx
0x180041431  jz      short loc_18004143F
0x180041433  mov     rax, [rcx]
0x180041436  mov     rax, [rax+10h]
0x18004143a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004143f  mov     rcx, [rdi+260h]; hdsa
0x180041446  test    rcx, rcx
0x180041449  jz      short loc_18004145E
0x18004144b  call    cs:__imp_DSA_Destroy
0x180041452  nop     dword ptr [rax+rax+00h]
0x180041457  mov     [rdi+260h], r14
0x18004145e  mov     rcx, [rdi+220h]; hdsa
0x180041465  call    cs:__imp_DSA_Destroy
0x18004146c  nop     dword ptr [rax+rax+00h]
0x180041471  lea     rbx, [rdi+100h]
0x180041478  mov     [rdi+220h], r14
0x18004147f  mov     rcx, rbx
0x180041482  call    ?Validate@?$CSignature@$0NAMA@@IEObjectSignature@@QEBAXXZ; IEObjectSignature::CSignature<53440>::Validate(void)
0x180041487  mov     word ptr [rbx], 0D351h
0x18004148c  lea     rax, ??_7CLayerParticipant@@6BILayerStateEvents@@@; const CLayerParticipant::`vftable'{for `ILayerStateEvents'}
0x180041493  mov     rcx, [rdi+0B8h]; bstrString
0x18004149a  mov     [rdi+0A0h], rax
0x1800414a1  lea     rax, ??_7?$CLayerOwner@VCTabLayer@@@@6BILayerCommandHandler@@@; const CLayerOwner<CTabLayer>::`vftable'{for `ILayerCommandHandler'}
0x1800414a8  mov     [rdi+0A8h], rax
0x1800414af  call    cs:__imp_SysFreeString
0x1800414b6  nop     dword ptr [rax+rax+00h]
0x1800414bb  lea     rcx, [rdi+0B0h]; void *
0x1800414c2  add     rsp, 20h
0x1800414c6  pop     r14
0x1800414c8  pop     rdi
0x1800414c9  pop     rsi
0x1800414ca  pop     rbp
0x1800414cb  pop     rbx
0x1800414cc  jmp     ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
```
