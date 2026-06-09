# CDVDProt::Start(ushort const *,IInternetProtocolSink *,IInternetBindInfo *,ulong,unsigned __int64)

- ea: `0x1800d6240`
- end: `0x1800d6935`
- name: `?Start@CDVDProt@@UEAAJPEBGPEAUIInternetProtocolSink@@PEAUIInternetBindInfo@@K_K@Z`
- size: `1781`
- prototype: `__int64 __fastcall(CDVDProt *this, const unsigned __int16 *, struct IUnknown *, struct IInternetBindInfo *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004640`
- `0x180004b54`
- `0x180005528`
- `0x180006b38`
- `0x18000dc54`
- `0x18000e518`
- `0x18000ef3c`
- `0x18000ff74`
- `0x18001414c`
- `0x1800149b0`
- `0x1800191f0`
- `0x18001a0f8`
- `0x180030cb4`
- `0x18003fd00`
- `0x18007c4c0`
- `0x18007c698`
- `0x18008061c`
- `0x1800d6240`
- `0x1800eedf4`
- `0x1800eee0c`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800d6563`
- `ole32!CoCreateInstance` at `0x1800d6563`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d6486`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d65d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d6636`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d6486`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d65d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d6636`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d6496`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d651f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d65e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d6616`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d6496`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d651f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d65e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d6616`
- `OLEAUT32!__imp_VariantClear` at `0x1800d64ac`
- `OLEAUT32!__imp_VariantClear` at `0x1800d6535`
- `OLEAUT32!__imp_VariantClear` at `0x1800d66a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800d6758`
- `OLEAUT32!__imp_VariantClear` at `0x1800d684d`
- `OLEAUT32!__imp_VariantClear` at `0x1800d64ac`
- `OLEAUT32!__imp_VariantClear` at `0x1800d6535`
- `OLEAUT32!__imp_VariantClear` at `0x1800d66a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800d6758`
- `OLEAUT32!__imp_VariantClear` at `0x1800d684d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDVDProt::Start(
        CDVDProt *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        struct IInternetBindInfo *a4)
{
  struct IUnknown **v8; // rdi
  struct IUnknown *v9; // rcx
  HRESULT Instance; // ebx
  int v11; // esi
  struct IInternetBindInfoVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  struct IUnknown *v14; // rdx
  BSTR v15; // rax
  OLECHAR *v16; // rbx
  BSTR v17; // rax
  OLECHAR *v18; // rbx
  int v19; // eax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rsi
  __int64 v24; // r14
  _QWORD *i; // rbx
  struct IUnknown *v26; // rcx
  struct IUnknownVtbl *v27; // rax
  int v28; // eax
  bool v29; // sf
  __int64 v30; // rdx
  struct IUnknown *ppv; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v32; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v33; // [rsp+40h] [rbp-99h] BYREF
  int v34; // [rsp+48h] [rbp-91h] BYREF
  VARIANTARG v35; // [rsp+50h] [rbp-89h] BYREF
  __int64 v36; // [rsp+68h] [rbp-71h] BYREF
  _QWORD *v37; // [rsp+70h] [rbp-69h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp-61h] BYREF
  __int64 v39; // [rsp+80h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v41[8]; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v42[24]; // [rsp+A8h] [rbp-31h] BYREF
  GUID Buf1; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v44; // [rsp+D0h] [rbp-9h]

  if ( !a3 )
    return 2147500035LL;
  v8 = (struct IUnknown **)((char *)this + 16);
  ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
    (char *)this + 16,
    a2);
  ATL::AtlComPtrAssign(v8, a3);
  ((void (__fastcall *)(struct IUnknown *, __int64, _QWORD))(*v8)->lpVtbl[1].Release)(*v8, 1, 0);
  v9 = *v8;
  if ( !a4 )
  {
    Instance = -2147467262;
    ((void (__fastcall *)(struct IUnknown *, __int64, _QWORD, _QWORD))v9->lpVtbl[2].QueryInterface)(
      v9,
      2147500034LL,
      0,
      0);
    return (unsigned int)Instance;
  }
  v11 = IsSafeSite(v9);
  if ( v11 < 0
    || (lpVtbl = a4->lpVtbl,
        v34 = 0,
        String1 = 0,
        v11 = ((__int64 (__fastcall *)(struct IInternetBindInfo *, __int64, wchar_t **, __int64, int *))lpVtbl->GetBindString)(
                a4,
                16,
                &String1,
                1,
                &v34),
        v11 < 0) )
  {
    ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(
      *v8,
      (unsigned int)v11,
      0,
      0);
    return (unsigned int)v11;
  }
  if ( wcscmp_0(String1, L"TRUE") )
  {
    ((void (__fastcall *)(struct IUnknown *, __int64, _QWORD))(*v8)->lpVtbl[1].Release)(*v8, 12, 0);
    ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(*v8, 0, 0, 0);
    ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(v8, v13);
    return 0;
  }
  Instance = ((__int64 (__fastcall *)(struct IInternetBindInfo *, __int64, wchar_t **, __int64, int *))a4->lpVtbl->GetBindString)(
               a4,
               17,
               &String1,
               1,
               &v34);
  if ( Instance >= 0 )
  {
    v39 = 0;
    swscanf(String1, L"%I64d", &v39);
    if ( !v39 )
    {
      Instance = -2147467262;
      ((void (__fastcall *)(struct IUnknown *, __int64, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(
        *v8,
        2147500034LL,
        0,
        0);
LABEL_69:
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v39);
      return (unsigned int)Instance;
    }
    v14 = *v8;
    ppv = 0;
    v32 = 0;
    ATL::CComQIPtr<IServiceProvider,&__s_GUID const _GUID_6d5140c1_7436_11ce_8034_00aa006009fa>::CComQIPtr<IServiceProvider,&__s_GUID const _GUID_6d5140c1_7436_11ce_8034_00aa006009fa>(
      &v33,
      v14);
    if ( v33
      && (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v33 + 24LL))(
           v33,
           &IID_IWebBrowserApp,
           &IID_IWebBrowser2,
           &v32) >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v15 = SysAllocString(L"B0EDF163-910A-11D2-B632-00C04F79498E");
      v16 = v15;
      if ( !v15 )
      {
        SysFreeString(0);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
        goto LABEL_21;
      }
      if ( (*(int (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v32 + 280LL))(v32, v15, &pvarg) >= 0
        && (pvarg.vt == 13 || pvarg.vt == 9) )
      {
        ATL::AtlComQIPtrAssign(&ppv, pvarg.punkVal, &GUID_b0edf162_910a_11d2_b632_00c04f79498e);
      }
      SysFreeString(v16);
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
    }
    if ( !ppv )
    {
      Instance = CoCreateInstance(&CLSID_MSVidCtl, 0, 1u, &GUID_b0edf162_910a_11d2_b632_00c04f79498e, (LPVOID *)&ppv);
      if ( Instance < 0 )
      {
        ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(
          *v8,
          (unsigned int)Instance,
          0,
          0);
LABEL_32:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v33);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        goto LABEL_69;
      }
      if ( v32 )
      {
        *(_QWORD *)&Buf1.Data1 = 13;
        *(_QWORD *)Buf1.Data4 = ppv;
        v17 = SysAllocString(L"B0EDF163-910A-11D2-B632-00C04F79498E");
        v18 = v17;
        if ( !v17 )
        {
          SysFreeString(0);
LABEL_21:
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v33);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
          Instance = -2147418113;
          goto LABEL_69;
        }
        v44 = 0;
        (*(void (__fastcall **)(__int64, BSTR, GUID *))(*(_QWORD *)v32 + 272LL))(v32, v17, &Buf1);
        SysFreeString(v18);
      }
      v35.vt = 0;
      ATL::CComVariant::InternalClear((ATL::CComVariant *)&v35);
      v35.vt = 8;
      v35.llVal = (LONGLONG)SysAllocString(a2);
      if ( !v35.llVal && a2 )
      {
        v35.lVal = -2147024882;
        v35.vt = 10;
      }
      v19 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))ppv->lpVtbl[13].Release)(ppv, &v35);
      Instance = v19;
      if ( v19 < 0 )
      {
        ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(
          *v8,
          (unsigned int)v19,
          0,
          0);
LABEL_42:
        if ( v35.vt == 4095 )
          v35.vt = 8;
        VariantClear(&v35);
        goto LABEL_32;
      }
      v36 = 0;
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))ppv->lpVtbl[9].Release)(ppv, &v36);
      if ( Instance < 0 )
        goto LABEL_46;
      if ( v36 )
        v20 = v36 - 24;
      else
        v20 = 0;
      operator new(0x48u);
      v21 = std::vector<DSPin>::vector<DSPin>(v42);
      v23 = CTypedDevices<IMSVidFeatures,IMSVidFeature,&_GUID const CLSID_MSVidFeatures,&unsigned short const near * const STR_FEATURES_PROGID,252>::CTypedDevices<IMSVidFeatures,IMSVidFeature,&_GUID const CLSID_MSVidFeatures,&unsigned short const near * const STR_FEATURES_PROGID,252>(
              v22,
              v21);
      std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v42);
      if ( !v23 )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v36);
        if ( v35.vt == 4095 )
          v35.vt = 8;
        VariantClear(&v35);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v33);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        Instance = -2147024882;
        goto LABEL_69;
      }
      v24 = v20 + 48;
      std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
        v20 + 48,
        &v37);
      for ( i = v37; i != *(_QWORD **)std::vector<ATL::CComBSTR>::end(v24, v41); ++i )
      {
        ATL::CComQIPtr<IMSVidFeature,&__s_GUID const _GUID_37b03547_a4c8_11d2_b634_00c04f79498e>::CComQIPtr<IMSVidFeature,&__s_GUID const _GUID_37b03547_a4c8_11d2_b634_00c04f79498e>(
          &v37,
          *i);
        Buf1 = GUID_NULL;
        if ( (*(int (__fastcall **)(_QWORD *, GUID *))(*v37 + 112LL))(v37, &Buf1) >= 0
          && !memcmp_0(&Buf1, &CLSID_MSVidClosedCaptioning, 0x10u) )
        {
          std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
            v23 + 48,
            i);
        }
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v37);
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64))ppv->lpVtbl[13].QueryInterface)(ppv, v23 + 24);
      if ( Instance < 0 )
      {
LABEL_46:
        ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(
          *v8,
          (unsigned int)Instance,
          0,
          0);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v36);
        goto LABEL_42;
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v36);
      if ( v35.vt == 4095 )
        v35.vt = 8;
      VariantClear(&v35);
    }
    Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v39 + 72LL))(v39, L"IUnknown Pointer");
    if ( Instance >= 0 )
    {
      v28 = ((__int64 (__fastcall *)(struct IUnknown *))ppv->lpVtbl[14].Release)(ppv);
      v26 = *v8;
      Instance = v28;
      v29 = v28 < 0;
      v27 = (*v8)->lpVtbl;
      if ( !v29 )
      {
        ((void (__fastcall *)(struct IUnknown *, __int64))v27[1].AddRef)(v26, 29);
        ((void (__fastcall *)(struct IUnknown *, __int64, _QWORD))(*v8)->lpVtbl[1].Release)(*v8, 12, 0);
        ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(*v8, 0, 0, 0);
        ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(v8, v30);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v33);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        Instance = 0;
        goto LABEL_69;
      }
    }
    else
    {
      v26 = *v8;
      v27 = (*v8)->lpVtbl;
    }
    ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))v27[2].QueryInterface)(
      v26,
      (unsigned int)Instance,
      0,
      0);
    goto LABEL_32;
  }
  ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))(*v8)->lpVtbl[2].QueryInterface)(
    *v8,
    (unsigned int)Instance,
    0,
    0);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800d6240  push    rbp
0x1800d6242  push    rbx
0x1800d6243  push    rsi
0x1800d6244  push    rdi
0x1800d6245  push    r12
0x1800d6247  push    r13
0x1800d6249  push    r14
0x1800d624b  lea     rbp, [rsp-17h]
0x1800d6250  sub     rsp, 0F0h
0x1800d6257  mov     rax, cs:__security_cookie
0x1800d625e  xor     rax, rsp
0x1800d6261  mov     [rbp+47h+var_40], rax
0x1800d6265  mov     rbx, r9
0x1800d6268  mov     rsi, r8
0x1800d626b  mov     r14, rdx
0x1800d626e  test    r8, r8
0x1800d6271  jnz     short loc_1800D627D
0x1800d6273  mov     eax, 80004003h
0x1800d6278  jmp     loc_1800D6917
0x1800d627d  lea     rdi, [rcx+10h]
0x1800d6281  mov     rcx, rdi
0x1800d6284  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x1800d6289  mov     rdx, rsi; struct IUnknown *
0x1800d628c  mov     rcx, rdi; struct IUnknown **
0x1800d628f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800d6294  mov     rcx, [rdi]
0x1800d6297  xor     r9d, r9d
0x1800d629a  xor     r8d, r8d
0x1800d629d  mov     rax, [rcx]
0x1800d62a0  lea     r12d, [r9+1]
0x1800d62a4  mov     edx, r12d
0x1800d62a7  mov     rax, [rax+28h]
0x1800d62ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d62b0  mov     rcx, [rdi]; struct IUnknown *
0x1800d62b3  test    rbx, rbx
0x1800d62b6  jnz     short loc_1800D62D6
0x1800d62b8  mov     rax, [rcx]
0x1800d62bb  mov     ebx, 80004002h
0x1800d62c0  mov     rax, [rax+30h]
0x1800d62c4  xor     r9d, r9d
0x1800d62c7  mov     edx, ebx
0x1800d62c9  xor     r8d, r8d
0x1800d62cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d62d1  jmp     loc_1800D6915
0x1800d62d6  call    ?IsSafeSite@@YAJPEAUIUnknown@@@Z; IsSafeSite(IUnknown *)
0x1800d62db  mov     esi, eax
0x1800d62dd  test    eax, eax
0x1800d62df  jns     short loc_1800D62FF
0x1800d62e1  mov     rcx, [rdi]
0x1800d62e4  xor     r9d, r9d
0x1800d62e7  xor     r8d, r8d
0x1800d62ea  mov     rdx, [rcx]
0x1800d62ed  mov     rax, [rdx+30h]
0x1800d62f1  mov     edx, esi
0x1800d62f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d62f8  mov     eax, esi
0x1800d62fa  jmp     loc_1800D6917
0x1800d62ff  mov     rax, [rbx]
0x1800d6302  lea     rcx, [rsp+120h+var_D8]
0x1800d6307  mov     [rsp+120h+ppv], rcx
0x1800d630c  lea     r8, [rbp+47h+String1]
0x1800d6310  mov     r9d, r12d
0x1800d6313  mov     [rsp+120h+var_D8], 0
0x1800d631b  mov     edx, 10h
0x1800d6320  mov     [rbp+47h+String1], 0
0x1800d6328  mov     rax, [rax+20h]
0x1800d632c  mov     rcx, rbx
0x1800d632f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6334  mov     esi, eax
0x1800d6336  test    eax, eax
0x1800d6338  js      short loc_1800D62E1
0x1800d633a  mov     rcx, [rbp+47h+String1]; String1
0x1800d633e  lea     rdx, aTrue_0; "TRUE"
0x1800d6345  call    wcscmp_0
0x1800d634a  test    eax, eax
0x1800d634c  jz      short loc_1800D638D
0x1800d634e  mov     rcx, [rdi]
0x1800d6351  xor     r9d, r9d
0x1800d6354  xor     r8d, r8d
0x1800d6357  mov     rax, [rcx]
0x1800d635a  lea     edx, [r9+0Ch]
0x1800d635e  mov     rax, [rax+28h]
0x1800d6362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6367  mov     rcx, [rdi]
0x1800d636a  xor     r9d, r9d
0x1800d636d  xor     r8d, r8d
0x1800d6370  xor     edx, edx
0x1800d6372  mov     rax, [rcx]
0x1800d6375  mov     rax, [rax+30h]
0x1800d6379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d637e  mov     rcx, rdi
0x1800d6381  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x1800d6386  xor     eax, eax
0x1800d6388  jmp     loc_1800D6917
0x1800d638d  mov     rax, [rbx]
0x1800d6390  lea     rcx, [rsp+120h+var_D8]
0x1800d6395  mov     [rsp+120h+ppv], rcx
0x1800d639a  lea     r8, [rbp+47h+String1]
0x1800d639e  mov     r9d, r12d
0x1800d63a1  mov     edx, 11h
0x1800d63a6  mov     rcx, rbx
0x1800d63a9  mov     rax, [rax+20h]
0x1800d63ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d63b2  mov     ebx, eax
0x1800d63b4  test    eax, eax
0x1800d63b6  jns     short loc_1800D63C7
0x1800d63b8  mov     rcx, [rdi]
0x1800d63bb  mov     rdx, [rcx]
0x1800d63be  mov     rax, [rdx+30h]
0x1800d63c2  jmp     loc_1800D62C4
0x1800d63c7  mov     rcx, [rbp+47h+String1]; Buffer
0x1800d63cb  lea     r8, [rbp+47h+var_A0]
0x1800d63cf  lea     rdx, aI64d; "%I64d"
0x1800d63d6  mov     [rbp+47h+var_A0], 0
0x1800d63de  call    swscanf
0x1800d63e3  cmp     [rbp+47h+var_A0], 0
0x1800d63e8  jnz     short loc_1800D640B
0x1800d63ea  mov     rcx, [rdi]
0x1800d63ed  mov     ebx, 80004002h
0x1800d63f2  xor     r9d, r9d
0x1800d63f5  xor     r8d, r8d
0x1800d63f8  mov     edx, ebx
0x1800d63fa  mov     rax, [rcx]
0x1800d63fd  mov     rax, [rax+30h]
0x1800d6401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6406  jmp     loc_1800D690C
0x1800d640b  mov     rdx, [rdi]
0x1800d640e  lea     rcx, [rsp+120h+var_E0]
0x1800d6413  mov     [rsp+120h+var_F0], 0
0x1800d641c  mov     [rsp+120h+var_E8], 0
0x1800d6425  call    ??0?$CComQIPtr@UIServiceProvider@@$1?_GUID_6d5140c1_7436_11ce_8034_00aa006009fa@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IServiceProvider,&__s_GUID const _GUID_6d5140c1_7436_11ce_8034_00aa006009fa>::CComQIPtr<IServiceProvider,&__s_GUID const _GUID_6d5140c1_7436_11ce_8034_00aa006009fa>(IUnknown *)
0x1800d642a  mov     rcx, [rsp+120h+var_E0]
0x1800d642f  lea     rsi, _GUID_b0edf162_910a_11d2_b632_00c04f79498e
0x1800d6436  mov     r13d, 0FFFh
0x1800d643c  mov     r12d, 8
0x1800d6442  test    rcx, rcx
0x1800d6445  jz      loc_1800D653B
0x1800d644b  mov     rax, [rcx]
0x1800d644e  lea     r9, [rsp+120h+var_E8]
0x1800d6453  lea     r8, IID_IWebBrowser2
0x1800d645a  lea     rdx, IID_IWebBrowserApp
0x1800d6461  mov     rax, [rax+18h]
0x1800d6465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d646a  test    eax, eax
0x1800d646c  js      loc_1800D653B
0x1800d6472  xorps   xmm0, xmm0
0x1800d6475  lea     rcx, aB0edf163910a11; "B0EDF163-910A-11D2-B632-00C04F79498E"
0x1800d647c  xor     eax, eax
0x1800d647e  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x1800d6482  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x1800d6486  call    cs:__imp_SysAllocString
0x1800d648c  mov     rbx, rax
0x1800d648f  test    rax, rax
0x1800d6492  jnz     short loc_1800D64DA
0x1800d6494  xor     ecx, ecx; bstrString
0x1800d6496  call    cs:__imp_SysFreeString
0x1800d649c  cmp     word ptr [rbp+47h+pvarg], r13w
0x1800d64a1  jnz     short loc_1800D64A8
0x1800d64a3  mov     word ptr [rbp+47h+pvarg], r12w
0x1800d64a8  lea     rcx, [rbp+47h+pvarg]; pvarg
0x1800d64ac  call    cs:__imp_VariantClear
0x1800d64b2  lea     rcx, [rsp+120h+var_E0]
0x1800d64b7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d64bc  lea     rcx, [rsp+120h+var_E8]
0x1800d64c1  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d64c6  lea     rcx, [rsp+120h+var_F0]
0x1800d64cb  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d64d0  mov     ebx, 8000FFFFh
0x1800d64d5  jmp     loc_1800D690C
0x1800d64da  mov     rcx, [rsp+120h+var_E8]
0x1800d64df  lea     r8, [rbp+47h+pvarg]
0x1800d64e3  mov     rdx, rbx
0x1800d64e6  mov     rax, [rcx]
0x1800d64e9  mov     rax, [rax+118h]
0x1800d64f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d64f5  test    eax, eax
0x1800d64f7  js      short loc_1800D651C
0x1800d64f9  mov     eax, 0Dh
0x1800d64fe  cmp     word ptr [rbp+47h+pvarg], ax
0x1800d6502  jz      short loc_1800D650B
0x1800d6504  cmp     word ptr [rbp+47h+pvarg], 9
0x1800d6509  jnz     short loc_1800D651C
0x1800d650b  mov     rdx, qword ptr [rbp+47h+pvarg+8]; struct IUnknown *
0x1800d650f  lea     rcx, [rsp+120h+var_F0]; struct IUnknown **
0x1800d6514  mov     r8, rsi; struct _GUID *
0x1800d6517  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x1800d651c  mov     rcx, rbx; bstrString
0x1800d651f  call    cs:__imp_SysFreeString
0x1800d6525  cmp     word ptr [rbp+47h+pvarg], r13w
0x1800d652a  jnz     short loc_1800D6531
0x1800d652c  mov     word ptr [rbp+47h+pvarg], r12w
0x1800d6531  lea     rcx, [rbp+47h+pvarg]; pvarg
0x1800d6535  call    cs:__imp_VariantClear
0x1800d653b  mov     r8, [rsp+120h+var_F0]
0x1800d6540  test    r8, r8
0x1800d6543  jnz     loc_1800D6858
0x1800d6549  xor     edx, edx; pUnkOuter
0x1800d654b  lea     rax, [rsp+120h+var_F0]
0x1800d6550  mov     r9, rsi; riid
0x1800d6553  mov     [rsp+120h+ppv], rax; ppv
0x1800d6558  lea     rcx, CLSID_MSVidCtl; rclsid
0x1800d655f  lea     r8d, [rdx+1]; dwClsContext
0x1800d6563  call    cs:__imp_CoCreateInstance
0x1800d6569  mov     ebx, eax
0x1800d656b  test    eax, eax
0x1800d656d  jns     short loc_1800D65A9
0x1800d656f  mov     rcx, [rdi]
0x1800d6572  mov     rdx, [rcx]
0x1800d6575  mov     rax, [rdx+30h]
0x1800d6579  xor     r9d, r9d
0x1800d657c  mov     edx, ebx
0x1800d657e  xor     r8d, r8d
0x1800d6581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6586  lea     rcx, [rsp+120h+var_E0]
0x1800d658b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d6590  lea     rcx, [rsp+120h+var_E8]
0x1800d6595  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d659a  lea     rcx, [rsp+120h+var_F0]
0x1800d659f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d65a4  jmp     loc_1800D690C
0x1800d65a9  cmp     [rsp+120h+var_E8], 0
0x1800d65af  jz      short loc_1800D661C
0x1800d65b1  xorps   xmm0, xmm0
0x1800d65b4  lea     rcx, aB0edf163910a11; "B0EDF163-910A-11D2-B632-00C04F79498E"
0x1800d65bb  movups  [rbp+47h+Buf1], xmm0
0x1800d65bf  xor     esi, esi
0x1800d65c1  lea     eax, [rsi+0Dh]
0x1800d65c4  mov     word ptr [rbp+47h+Buf1], ax
0x1800d65c8  mov     rax, [rsp+120h+var_F0]
0x1800d65cd  mov     qword ptr [rbp+47h+Buf1+8], rax
0x1800d65d1  call    cs:__imp_SysAllocString
0x1800d65d7  mov     rbx, rax
0x1800d65da  test    rax, rax
0x1800d65dd  jnz     short loc_1800D65EC
0x1800d65df  xor     ecx, ecx; bstrString
0x1800d65e1  call    cs:__imp_SysFreeString
0x1800d65e7  jmp     loc_1800D64B2
0x1800d65ec  mov     rcx, [rsp+120h+var_E8]
0x1800d65f1  lea     r8, [rbp+47h+Buf1]
0x1800d65f5  movups  xmm0, [rbp+47h+Buf1]
0x1800d65f9  mov     rdx, rbx
0x1800d65fc  mov     [rbp+47h+var_50], rsi
0x1800d6600  mov     rax, [rcx]
0x1800d6603  movaps  [rbp+47h+Buf1], xmm0
0x1800d6607  mov     rax, [rax+110h]
0x1800d660e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6613  mov     rcx, rbx; bstrString
0x1800d6616  call    cs:__imp_SysFreeString
0x1800d661c  xor     eax, eax
0x1800d661e  lea     rcx, [rsp+120h+var_D0]; this
0x1800d6623  mov     word ptr [rsp+120h+var_D0], ax
0x1800d6628  call    ?InternalClear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::InternalClear(void)
0x1800d662d  mov     rcx, r14; psz
0x1800d6630  mov     word ptr [rsp+120h+var_D0], r12w
0x1800d6636  call    cs:__imp_SysAllocString
0x1800d663c  mov     qword ptr [rsp+120h+var_D0+8], rax
0x1800d6641  test    rax, rax
0x1800d6644  jnz     short loc_1800D665D
0x1800d6646  test    r14, r14
0x1800d6649  jz      short loc_1800D665D
0x1800d664b  mov     eax, 0Ah
0x1800d6650  mov     dword ptr [rsp+120h+var_D0+8], 8007000Eh
0x1800d6658  mov     word ptr [rsp+120h+var_D0], ax
0x1800d665d  mov     rcx, [rsp+120h+var_F0]
0x1800d6662  lea     rdx, [rsp+120h+var_D0]
0x1800d6667  mov     rax, [rcx]
0x1800d666a  mov     rax, [rax+148h]
0x1800d6671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6676  mov     ebx, eax
0x1800d6678  test    eax, eax
0x1800d667a  jns     short loc_1800D66B1
0x1800d667c  mov     rcx, [rdi]
0x1800d667f  xor     r9d, r9d
0x1800d6682  xor     r8d, r8d
0x1800d6685  mov     edx, ebx
0x1800d6687  mov     rax, [rcx]
0x1800d668a  mov     rax, [rax+30h]
0x1800d668e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6693  cmp     word ptr [rsp+120h+var_D0], r13w
0x1800d6699  jnz     short loc_1800D66A1
0x1800d669b  mov     word ptr [rsp+120h+var_D0], r12w
0x1800d66a1  lea     rcx, [rsp+120h+var_D0]; pvarg
0x1800d66a6  call    cs:__imp_VariantClear
0x1800d66ac  jmp     loc_1800D6586
0x1800d66b1  mov     rcx, [rsp+120h+var_F0]
0x1800d66b6  lea     rdx, [rbp+47h+var_B8]
0x1800d66ba  mov     [rbp+47h+var_B8], 0
0x1800d66c2  mov     rax, [rcx]
0x1800d66c5  mov     rax, [rax+0E8h]
0x1800d66cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d66d1  mov     ebx, eax
0x1800d66d3  test    eax, eax
0x1800d66d5  jns     short loc_1800D66F9
0x1800d66d7  mov     rcx, [rdi]
0x1800d66da  xor     r9d, r9d
0x1800d66dd  xor     r8d, r8d
0x1800d66e0  mov     edx, ebx
0x1800d66e2  mov     rax, [rcx]
0x1800d66e5  mov     rax, [rax+30h]
0x1800d66e9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
