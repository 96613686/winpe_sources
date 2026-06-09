# CContainer::Create(HWND__ *,tagRECT *,int)

- ea: `0x18001745c`
- end: `0x180017a31`
- name: `?Create@CContainer@@QEAAJPEAUHWND__@@PEAUtagRECT@@H@Z`
- size: `1493`
- prototype: `__int64 __fastcall(struct IUnknown *this, HWND, struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006eaf4`

## callees

- `0x180001728`
- `0x1800170bc`
- `0x1800170dc`
- `0x1800170fc`
- `0x180017120`
- `0x180017144`
- `0x180017168`
- `0x18001718c`
- `0x1800171b0`
- `0x1800171d0`
- `0x18001745c`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `ole32!OleCreate` at `0x180017782`
- `ole32!OleCreate` at `0x1800177b7`
- `ole32!OleCreate` at `0x180017782`
- `ole32!OleCreate` at `0x1800177b7`
- `ole32!StgCreateDocfile` at `0x1800174e3`
- `ole32!StgCreateDocfile` at `0x1800174e3`
- `ole32!OleSetContainedObject` at `0x180017873`
- `ole32!OleSetContainedObject` at `0x180017873`

## pseudocode

```c
__int64 __fastcall CContainer::Create(struct IUnknown *this, struct IUnknownVtbl *a2, struct tagRECT *a3, int a4)
{
  LPSTORAGE *v4; // r15
  CIOleClientSite *v9; // rax
  struct IUnknownVtbl *v10; // rcx
  CIOleControlSite *v11; // rax
  struct IUnknownVtbl *v12; // rcx
  CIAdviseSink *v13; // rax
  struct IUnknownVtbl *v14; // rcx
  CIOleInPlaceSite *v15; // rax
  struct IUnknownVtbl *v16; // rcx
  CIOleInPlaceFrame *v17; // rax
  struct IUnknownVtbl *v18; // rcx
  struct IUnknownVtbl *v19; // rax
  CIOleItemContainer *v20; // rax
  struct IUnknownVtbl *v21; // rcx
  CDocHostUIHandler *v22; // rax
  struct IUnknownVtbl *v23; // rcx
  CDocHostShowUI *v24; // rax
  struct IUnknownVtbl *v25; // rcx
  CInternetSecurityManager *v26; // rax
  struct IUnknownVtbl *v27; // rcx
  unsigned int v28; // edi
  int v29; // eax
  LPUNKNOWN *v30; // rdi
  unsigned int v31; // esi
  LPUNKNOWN v32; // rcx
  LPUNKNOWN v33; // rcx
  _DWORD *v34; // rax
  LPUNKNOWN v35; // rcx
  CIOleClientSite *v36; // [rsp+40h] [rbp-29h] BYREF
  __int64 v37; // [rsp+48h] [rbp-21h] BYREF
  _DWORD *v38; // [rsp+50h] [rbp-19h] BYREF
  LPVOID ppvObj; // [rsp+58h] [rbp-11h] BYREF
  __int64 v40; // [rsp+60h] [rbp-9h] BYREF
  IID rclsid; // [rsp+68h] [rbp-1h] BYREF
  IID v42; // [rsp+78h] [rbp+Fh] BYREF

  v4 = (LPSTORAGE *)&this[2];
  this[4].lpVtbl = a2;
  v42.Data1 = -357422397;
  *(_DWORD *)&v42.Data2 = 298791105;
  *(_DWORD *)v42.Data4 = 60327;
  *(_DWORD *)&v42.Data4[4] = 195976128;
  ppvObj = 0;
  rclsid.Data1 = -2007565983;
  *(_DWORD *)&rclsid.Data2 = 298857482;
  *(_DWORD *)rclsid.Data4 = -1073714263;
  *(_DWORD *)&rclsid.Data4[4] = -1576675505;
  if ( StgCreateDocfile(0, 0x4010012u, 0, (IStorage **)&this[2]) )
    return 2147500037LL;
  v9 = (CIOleClientSite *)operator new(0x20u);
  v36 = v9;
  if ( v9 )
    v10 = (struct IUnknownVtbl *)CIOleClientSite::CIOleClientSite(v9, (struct CContainer *)this);
  else
    v10 = 0;
  this[8].lpVtbl = v10;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v10->QueryInterface + 1))(v10);
  v11 = (CIOleControlSite *)operator new(0x20u);
  v36 = v11;
  if ( v11 )
    v12 = (struct IUnknownVtbl *)CIOleControlSite::CIOleControlSite(v11, (struct CContainer *)this);
  else
    v12 = 0;
  this[12].lpVtbl = v12;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v12->QueryInterface + 1))(v12);
  v13 = (CIAdviseSink *)operator new(0x20u);
  v36 = v13;
  if ( v13 )
    v14 = (struct IUnknownVtbl *)CIAdviseSink::CIAdviseSink(v13, (struct CContainer *)this);
  else
    v14 = 0;
  this[6].lpVtbl = v14;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v14->QueryInterface + 1))(v14);
  v15 = (CIOleInPlaceSite *)operator new(0x20u);
  v36 = v15;
  if ( v15 )
    v16 = (struct IUnknownVtbl *)CIOleInPlaceSite::CIOleInPlaceSite(v15, (struct CContainer *)this);
  else
    v16 = 0;
  this[7].lpVtbl = v16;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v16->QueryInterface + 1))(v16);
  v17 = (CIOleInPlaceFrame *)operator new(0x20u);
  v36 = v17;
  if ( v17 )
    v18 = (struct IUnknownVtbl *)CIOleInPlaceFrame::CIOleInPlaceFrame(v17, (struct CContainer *)this);
  else
    v18 = 0;
  this[9].lpVtbl = v18;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v18->QueryInterface + 1))(v18);
  if ( a4 )
  {
    v19 = (struct IUnknownVtbl *)operator new(0x60u);
    v36 = (CIOleClientSite *)v19;
    if ( v19 )
    {
      v19->QueryInterface = (HRESULT (__stdcall *)(IUnknown *, const IID *const, void **))&CUnknownObject::`vftable';
      v19[1].QueryInterface = (HRESULT (__stdcall *)(IUnknown *, const IID *const, void **))&CUnknownObject::CPrivateUnknownObject::`vftable';
      LODWORD(v19[1].AddRef) = 1;
      v19->AddRef = (ULONG (__stdcall *)(IUnknown *))this;
      _InterlockedAdd(&g_cLocks, 1u);
      v19[2].AddRef = (ULONG (__stdcall *)(IUnknown *))this;
      v19->QueryInterface = (HRESULT (__stdcall *)(IUnknown *, const IID *const, void **))&CAutomateContent::`vftable'{for `CUnknownObject'};
      v19[1].Release = (ULONG (__stdcall *)(IUnknown *))&CAutomateContent::`vftable'{for `IDispatch'};
      LODWORD(v19[2].QueryInterface) = 0;
      HIDWORD(v19[3].Release) = 0;
      LODWORD(v19[3].QueryInterface) = 1;
      v19[3].AddRef = 0;
    }
    else
    {
      v19 = 0;
    }
    this[11].lpVtbl = v19;
    (*((void (__fastcall **)(ULONG (__stdcall **)(IUnknown *)))v19[1].Release + 1))(&v19[1].Release);
  }
  v20 = (CIOleItemContainer *)operator new(0x18u);
  v36 = v20;
  if ( v20 )
    v21 = (struct IUnknownVtbl *)CIOleItemContainer::CIOleItemContainer(v20, this);
  else
    v21 = 0;
  this[10].lpVtbl = v21;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v21->QueryInterface + 1))(v21);
  v22 = (CDocHostUIHandler *)operator new(0x18u);
  v36 = v22;
  if ( v22 )
    v23 = (struct IUnknownVtbl *)CDocHostUIHandler::CDocHostUIHandler(v22, this);
  else
    v23 = 0;
  this[13].lpVtbl = v23;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v23->QueryInterface + 1))(v23);
  v24 = (CDocHostShowUI *)operator new(0x18u);
  v36 = v24;
  if ( v24 )
    v25 = (struct IUnknownVtbl *)CDocHostShowUI::CDocHostShowUI(v24, this);
  else
    v25 = 0;
  this[14].lpVtbl = v25;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v25->QueryInterface + 1))(v25);
  v26 = (CInternetSecurityManager *)operator new(0x20u);
  v36 = v26;
  if ( v26 )
    v27 = (struct IUnknownVtbl *)CInternetSecurityManager::CInternetSecurityManager(v26, this);
  else
    v27 = 0;
  this[16].lpVtbl = v27;
  (*((void (__fastcall **)(struct IUnknownVtbl *))v27->QueryInterface + 1))(v27);
  if ( OleCreate(&rclsid, &IID_IOleObject, 0, 0, (LPOLECLIENTSITE)this[8].lpVtbl, *v4, &ppvObj) )
  {
    v28 = OleCreate(&v42, &IID_IOleObject, 0, 0, (LPOLECLIENTSITE)this[8].lpVtbl, *v4, &ppvObj);
    if ( v28 )
    {
      ((void (__fastcall *)(LPSTORAGE))(*v4)->lpVtbl->Release)(*v4);
      (*((void (__fastcall **)(struct IUnknownVtbl *))this[8].lpVtbl->QueryInterface + 2))(this[8].lpVtbl);
      return v28;
    }
    v29 = 0;
  }
  else
  {
    v29 = 1;
  }
  LODWORD(this[5].lpVtbl) = v29;
  v30 = (LPUNKNOWN *)&this[3];
  v31 = -2147467259;
  if ( !(**(unsigned int (__fastcall ***)(LPVOID, GUID *, struct IUnknown *))ppvObj)(ppvObj, &IID_IOleObject, this + 3) )
  {
    v32 = *v30;
    v40 = 0;
    if ( ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))v32->lpVtbl->QueryInterface)(
           v32,
           &IID_IViewObject2,
           &v40) >= 0 )
    {
      (*(void (__fastcall **)(__int64, __int64, __int64, struct IUnknownVtbl *))(*(_QWORD *)v40 + 56LL))(
        v40,
        1,
        2,
        this[6].lpVtbl);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    OleSetContainedObject(*v30, 1);
    v33 = *v30;
    v36 = 0;
    if ( !((unsigned __int64 (__fastcall *)(LPUNKNOWN, GUID *, CIOleClientSite **))v33->lpVtbl->QueryInterface)(
            v33,
            &IID_IDispatch,
            &v36) )
    {
      v34 = operator new(0x10u);
      v38 = v34;
      if ( v34 )
      {
        *(_QWORD *)v34 = v36;
        v34[2] = 1;
      }
      else
      {
        v34 = 0;
      }
      this[19].lpVtbl = (struct IUnknownVtbl *)v34;
    }
    if ( a4 )
    {
      v35 = *v30;
      v38 = 0;
      if ( ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, _DWORD **))v35->lpVtbl->QueryInterface)(
             v35,
             &IID_IConnectionPointContainer,
             &v38) >= 0 )
      {
        v37 = 0;
        if ( (*(int (__fastcall **)(_DWORD *, GUID *, __int64 *))(*(_QWORD *)v38 + 32LL))(
               v38,
               &DIID_DWebBrowserEvents2,
               &v37) >= 0
          || (*(int (__fastcall **)(_DWORD *, GUID *, __int64 *))(*(_QWORD *)v38 + 32LL))(
               v38,
               &DIID_DWebBrowserEvents,
               &v37) >= 0 )
        {
          (*(void (__fastcall **)(__int64, __int64, struct IUnknown *))(*(_QWORD *)v37 + 40LL))(
            v37,
            (__int64)&this[11].lpVtbl[1].Release & -(__int64)(this[11].lpVtbl != 0),
            this + 17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v38 + 16LL))(v38);
      }
    }
    if ( ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, struct IUnknown *))(*v30)->lpVtbl->QueryInterface)(
           *v30,
           &IID_IOleCommandTarget,
           this + 21) < 0 )
      this[21].lpVtbl = 0;
    ((void (__fastcall *)(LPUNKNOWN, __int64, _QWORD, struct IUnknownVtbl *, int, struct IUnknownVtbl *, struct tagRECT *))(*v30)->lpVtbl[3].Release)(
      *v30,
      0xFFFFFFFFLL,
      0,
      this[8].lpVtbl,
      -1,
      this[4].lpVtbl,
      a3);
    v31 = 0;
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppvObj + 16LL))(ppvObj);
  if ( !v31 )
    return 0;
  ((void (__fastcall *)(LPSTORAGE))(*v4)->lpVtbl->Release)(*v4);
  (*((void (__fastcall **)(struct IUnknownVtbl *))this[8].lpVtbl->QueryInterface + 2))(this[8].lpVtbl);
  return v31;
}

```

## disassembly

```asm
0x18001745c  mov     [rsp-8+arg_8], rbx
0x180017461  push    rbp
0x180017462  push    rsi
0x180017463  push    rdi
0x180017464  push    r12
0x180017466  push    r13
0x180017468  push    r14
0x18001746a  push    r15
0x18001746c  lea     rbp, [rsp-27h]
0x180017471  sub     rsp, 90h
0x180017478  mov     rax, cs:__security_cookie
0x18001747f  xor     rax, rsp
0x180017482  mov     [rbp+57h+var_38], rax
0x180017486  lea     r15, [rcx+10h]
0x18001748a  mov     [rcx+20h], rdx
0x18001748e  mov     r14d, r9d
0x180017491  mov     [rbp+57h+var_48.Data1], 0EAB22AC3h
0x180017498  mov     r12, r8
0x18001749b  mov     dword ptr [rbp+57h+var_48.Data2], 11CF30C1h
0x1800174a2  mov     rbx, rcx
0x1800174a5  mov     dword ptr [rbp+57h+var_48.Data4], 0EBA7h
0x1800174ac  xor     r13d, r13d
0x1800174af  mov     dword ptr [rbp+57h+var_48.Data4+4], 0BAE5BC0h
0x1800174b6  mov     r9, r15; ppstgOpen
0x1800174b9  mov     [rbp+57h+var_68], r13
0x1800174bd  xor     r8d, r8d; reserved
0x1800174c0  mov     [rbp+57h+rclsid.Data1], 8856F961h
0x1800174c7  mov     edx, 4010012h; grfMode
0x1800174cc  mov     dword ptr [rbp+57h+rclsid.Data2], 11D0340Ah
0x1800174d3  xor     ecx, ecx; pwcsName
0x1800174d5  mov     dword ptr [rbp+57h+rclsid.Data4], 0C0006BA9h
0x1800174dc  mov     dword ptr [rbp+57h+rclsid.Data4+4], 0A205D74Fh
0x1800174e3  call    cs:__imp_StgCreateDocfile
0x1800174e9  test    eax, eax
0x1800174eb  jz      short loc_1800174F7
0x1800174ed  mov     eax, 80004005h
0x1800174f2  jmp     loc_180017A0A
0x1800174f7  mov     esi, 20h ; ' '
0x1800174fc  mov     ecx, esi; Size
0x1800174fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017503  mov     [rbp+57h+var_80], rax
0x180017507  test    rax, rax
0x18001750a  jz      short loc_18001751C
0x18001750c  mov     rdx, rbx; struct CContainer *
0x18001750f  mov     rcx, rax; this
0x180017512  call    ??0CIOleClientSite@@QEAA@PEAVCContainer@@@Z; CIOleClientSite::CIOleClientSite(CContainer *)
0x180017517  mov     rcx, rax
0x18001751a  jmp     short loc_18001751F
0x18001751c  mov     rcx, r13
0x18001751f  mov     [rbx+40h], rcx
0x180017523  mov     rax, [rcx]
0x180017526  mov     rax, [rax+8]
0x18001752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001752f  mov     rcx, rsi; Size
0x180017532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017537  mov     [rbp+57h+var_80], rax
0x18001753b  test    rax, rax
0x18001753e  jz      short loc_180017550
0x180017540  mov     rdx, rbx; struct CContainer *
0x180017543  mov     rcx, rax; this
0x180017546  call    ??0CIOleControlSite@@QEAA@PEAVCContainer@@@Z; CIOleControlSite::CIOleControlSite(CContainer *)
0x18001754b  mov     rcx, rax
0x18001754e  jmp     short loc_180017553
0x180017550  mov     rcx, r13
0x180017553  mov     [rbx+60h], rcx
0x180017557  mov     rax, [rcx]
0x18001755a  mov     rax, [rax+8]
0x18001755e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017563  mov     rcx, rsi; Size
0x180017566  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001756b  mov     [rbp+57h+var_80], rax
0x18001756f  test    rax, rax
0x180017572  jz      short loc_180017584
0x180017574  mov     rdx, rbx; struct CContainer *
0x180017577  mov     rcx, rax; this
0x18001757a  call    ??0CIAdviseSink@@QEAA@PEAVCContainer@@@Z; CIAdviseSink::CIAdviseSink(CContainer *)
0x18001757f  mov     rcx, rax
0x180017582  jmp     short loc_180017587
0x180017584  mov     rcx, r13
0x180017587  mov     [rbx+30h], rcx
0x18001758b  mov     rax, [rcx]
0x18001758e  mov     rax, [rax+8]
0x180017592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017597  mov     rcx, rsi; Size
0x18001759a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001759f  mov     [rbp+57h+var_80], rax
0x1800175a3  test    rax, rax
0x1800175a6  jz      short loc_1800175B8
0x1800175a8  mov     rdx, rbx; struct CContainer *
0x1800175ab  mov     rcx, rax; this
0x1800175ae  call    ??0CIOleInPlaceSite@@QEAA@PEAVCContainer@@@Z; CIOleInPlaceSite::CIOleInPlaceSite(CContainer *)
0x1800175b3  mov     rcx, rax
0x1800175b6  jmp     short loc_1800175BB
0x1800175b8  mov     rcx, r13
0x1800175bb  mov     [rbx+38h], rcx
0x1800175bf  mov     rax, [rcx]
0x1800175c2  mov     rax, [rax+8]
0x1800175c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175cb  mov     rcx, rsi; Size
0x1800175ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800175d3  mov     [rbp+57h+var_80], rax
0x1800175d7  test    rax, rax
0x1800175da  jz      short loc_1800175EC
0x1800175dc  mov     rdx, rbx; struct CContainer *
0x1800175df  mov     rcx, rax; this
0x1800175e2  call    ??0CIOleInPlaceFrame@@QEAA@PEAVCContainer@@@Z; CIOleInPlaceFrame::CIOleInPlaceFrame(CContainer *)
0x1800175e7  mov     rcx, rax
0x1800175ea  jmp     short loc_1800175EF
0x1800175ec  mov     rcx, r13
0x1800175ef  mov     [rbx+48h], rcx
0x1800175f3  mov     rax, [rcx]
0x1800175f6  mov     rax, [rax+8]
0x1800175fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ff  mov     edi, 1
0x180017604  test    r14d, r14d
0x180017607  jz      short loc_18001767E
0x180017609  lea     ecx, [rdi+5Fh]; Size
0x18001760c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017611  mov     [rbp+57h+var_80], rax
0x180017615  test    rax, rax
0x180017618  jz      short loc_180017667
0x18001761a  lea     rcx, ??_7CUnknownObject@@6B@; const CUnknownObject::`vftable'
0x180017621  mov     [rax], rcx
0x180017624  lea     rcx, ??_7CPrivateUnknownObject@CUnknownObject@@6B@; const CUnknownObject::CPrivateUnknownObject::`vftable'
0x18001762b  mov     [rax+18h], rcx
0x18001762f  mov     [rax+20h], edi
0x180017632  mov     [rax+8], rbx
0x180017636  lock add cs:?g_cLocks@@3JA, edi; long g_cLocks
0x18001763d  lea     rcx, ??_7CAutomateContent@@6BCUnknownObject@@@; const CAutomateContent::`vftable'{for `CUnknownObject'}
0x180017644  mov     [rax+38h], rbx
0x180017648  mov     [rax], rcx
0x18001764b  lea     rcx, ??_7CAutomateContent@@6BIDispatch@@@; const CAutomateContent::`vftable'{for `IDispatch'}
0x180017652  mov     [rax+28h], rcx
0x180017656  mov     [rax+30h], r13d
0x18001765a  mov     [rax+5Ch], r13d
0x18001765e  mov     [rax+48h], edi
0x180017661  mov     [rax+50h], r13
0x180017665  jmp     short loc_18001766A
0x180017667  mov     rax, r13
0x18001766a  lea     rcx, [rax+28h]
0x18001766e  mov     [rbx+58h], rax
0x180017672  mov     rax, [rcx]
0x180017675  mov     rax, [rax+8]
0x180017679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001767e  mov     ecx, 18h; Size
0x180017683  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017688  mov     [rbp+57h+var_80], rax
0x18001768c  test    rax, rax
0x18001768f  jz      short loc_1800176A1
0x180017691  mov     rdx, rbx; struct IUnknown *
0x180017694  mov     rcx, rax; this
0x180017697  call    ??0CIOleItemContainer@@QEAA@PEAUIUnknown@@@Z; CIOleItemContainer::CIOleItemContainer(IUnknown *)
0x18001769c  mov     rcx, rax
0x18001769f  jmp     short loc_1800176A4
0x1800176a1  mov     rcx, r13
0x1800176a4  mov     [rbx+50h], rcx
0x1800176a8  mov     rax, [rcx]
0x1800176ab  mov     rax, [rax+8]
0x1800176af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b4  mov     ecx, 18h; Size
0x1800176b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800176be  mov     [rbp+57h+var_80], rax
0x1800176c2  test    rax, rax
0x1800176c5  jz      short loc_1800176D7
0x1800176c7  mov     rdx, rbx; struct IUnknown *
0x1800176ca  mov     rcx, rax; this
0x1800176cd  call    ??0CDocHostUIHandler@@QEAA@PEAUIUnknown@@@Z; CDocHostUIHandler::CDocHostUIHandler(IUnknown *)
0x1800176d2  mov     rcx, rax
0x1800176d5  jmp     short loc_1800176DA
0x1800176d7  mov     rcx, r13
0x1800176da  mov     [rbx+68h], rcx
0x1800176de  mov     rax, [rcx]
0x1800176e1  mov     rax, [rax+8]
0x1800176e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176ea  mov     ecx, 18h; Size
0x1800176ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800176f4  mov     [rbp+57h+var_80], rax
0x1800176f8  test    rax, rax
0x1800176fb  jz      short loc_18001770D
0x1800176fd  mov     rdx, rbx; struct IUnknown *
0x180017700  mov     rcx, rax; this
0x180017703  call    ??0CDocHostShowUI@@QEAA@PEAUIUnknown@@@Z; CDocHostShowUI::CDocHostShowUI(IUnknown *)
0x180017708  mov     rcx, rax
0x18001770b  jmp     short loc_180017710
0x18001770d  mov     rcx, r13
0x180017710  mov     [rbx+70h], rcx
0x180017714  mov     rax, [rcx]
0x180017717  mov     rax, [rax+8]
0x18001771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017720  mov     rcx, rsi; Size
0x180017723  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017728  mov     [rbp+57h+var_80], rax
0x18001772c  test    rax, rax
0x18001772f  jz      short loc_180017741
0x180017731  mov     rdx, rbx; struct IUnknown *
0x180017734  mov     rcx, rax; this
0x180017737  call    ??0CInternetSecurityManager@@QEAA@PEAUIUnknown@@@Z; CInternetSecurityManager::CInternetSecurityManager(IUnknown *)
0x18001773c  mov     rcx, rax
0x18001773f  jmp     short loc_180017744
0x180017741  mov     rcx, r13
0x180017744  mov     [rbx+80h], rcx
0x18001774b  mov     rax, [rcx]
0x18001774e  mov     rax, [rax+8]
0x180017752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017757  lea     rax, [rbp+57h+var_68]
0x18001775b  xor     r9d, r9d; pFormatEtc
0x18001775e  mov     [rsp+0C0h+ppvObj], rax; ppvObj
0x180017763  lea     rdx, IID_IOleObject; riid
0x18001776a  mov     rax, [r15]
0x18001776d  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180017771  mov     [rsp+0C0h+pStg], rax; pStg
0x180017776  xor     r8d, r8d; renderopt
0x180017779  mov     rax, [rbx+40h]
0x18001777d  mov     [rsp+0C0h+pClientSite], rax; pClientSite
0x180017782  call    cs:__imp_OleCreate
0x180017788  test    eax, eax
0x18001778a  jz      short loc_1800177EE
0x18001778c  lea     rax, [rbp+57h+var_68]
0x180017790  xor     r9d, r9d; pFormatEtc
0x180017793  mov     [rsp+0C0h+ppvObj], rax; ppvObj
0x180017798  lea     rdx, IID_IOleObject; riid
0x18001779f  mov     rax, [r15]
0x1800177a2  lea     rcx, [rbp+57h+var_48]; rclsid
0x1800177a6  mov     [rsp+0C0h+pStg], rax; pStg
0x1800177ab  xor     r8d, r8d; renderopt
0x1800177ae  mov     rax, [rbx+40h]
0x1800177b2  mov     [rsp+0C0h+pClientSite], rax; pClientSite
0x1800177b7  call    cs:__imp_OleCreate
0x1800177bd  mov     edi, eax
0x1800177bf  test    eax, eax
0x1800177c1  jz      short loc_1800177E9
0x1800177c3  mov     rcx, [r15]
0x1800177c6  mov     rdx, [rcx]
0x1800177c9  mov     rax, [rdx+10h]
0x1800177cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177d2  mov     rcx, [rbx+40h]
0x1800177d6  mov     rdx, [rcx]
0x1800177d9  mov     rax, [rdx+10h]
0x1800177dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177e2  mov     eax, edi
0x1800177e4  jmp     loc_180017A0A
0x1800177e9  mov     eax, r13d
0x1800177ec  jmp     short loc_1800177F0
0x1800177ee  mov     eax, edi
0x1800177f0  mov     [rbx+28h], eax
0x1800177f3  lea     rdi, [rbx+18h]
0x1800177f7  mov     rcx, [rbp+57h+var_68]
0x1800177fb  lea     rdx, IID_IOleObject
0x180017802  mov     r8, rdi
0x180017805  mov     esi, 80004005h
0x18001780a  mov     rax, [rcx]
0x18001780d  mov     rax, [rax]
0x180017810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017815  test    eax, eax
0x180017817  jnz     loc_1800179D1
0x18001781d  mov     rcx, [rdi]
0x180017820  lea     r8, [rbp+57h+var_60]
0x180017824  mov     [rbp+57h+var_60], r13
0x180017828  lea     rdx, IID_IViewObject2
0x18001782f  mov     rax, [rcx]
0x180017832  mov     rax, [rax]
0x180017835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001783a  test    eax, eax
0x18001783c  js      short loc_18001786B
0x18001783e  mov     rcx, [rbp+57h+var_60]
0x180017842  mov     edx, 1
0x180017847  mov     r9, [rbx+30h]
0x18001784b  mov     rax, [rcx]
0x18001784e  lea     r8d, [rdx+1]
0x180017852  mov     rax, [rax+38h]
0x180017856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001785b  mov     rcx, [rbp+57h+var_60]
0x18001785f  mov     rax, [rcx]
0x180017862  mov     rax, [rax+10h]
0x180017866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001786b  mov     rcx, [rdi]; pUnknown
0x18001786e  mov     edx, 1; fContained
0x180017873  call    cs:__imp_OleSetContainedObject
0x180017879  mov     rcx, [rdi]
0x18001787c  lea     r8, [rbp+57h+var_80]
0x180017880  mov     [rbp+57h+var_80], r13
0x180017884  lea     rdx, IID_IDispatch
0x18001788b  mov     rax, [rcx]
0x18001788e  mov     rax, [rax]
0x180017891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017896  test    eax, eax
0x180017898  jnz     short loc_1800178C5
0x18001789a  lea     ecx, [rax+10h]; Size
0x18001789d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800178a2  mov     [rbp+57h+var_70], rax
0x1800178a6  test    rax, rax
0x1800178a9  jz      short loc_1800178BB
0x1800178ab  mov     rcx, [rbp+57h+var_80]
0x1800178af  mov     [rax], rcx
0x1800178b2  mov     dword ptr [rax+8], 1
0x1800178b9  jmp     short loc_1800178BE
0x1800178bb  mov     rax, r13
0x1800178be  mov     [rbx+98h], rax
0x1800178c5  test    r14d, r14d
0x1800178c8  jz      loc_18001797D
  ... truncated ...
```
