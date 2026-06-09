# HTMLDocumentSource::_Initialize(IUnknown *,IWebPlatformHostSecurityManagerFactory *,bool)

- ea: `0x1809c56b0`
- end: `0x1809c5b48`
- name: `?_Initialize@HTMLDocumentSource@@AEAAJPEAUIUnknown@@PEAUIWebPlatformHostSecurityManagerFactory@@_N@Z`
- size: `1176`
- prototype: `__int64 __fastcall(HTMLDocumentSource *__hidden this, struct IUnknown *, struct IWebPlatformHostSecurityManagerFactory *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1809c3264`

## callees

- `0x180013efc`
- `0x1800c5000`
- `0x1807f1880`
- `0x1808297d0`
- `0x180837be4`
- `0x1809c304c`
- `0x1809c3394`
- `0x1809c56b0`
- `0x1809ec814`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1809c5760`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1809c5760`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1809c5713`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1809c5713`
- `urlmon!CreateURLMonikerEx` at `0x1809c594b`
- `urlmon!CreateURLMonikerEx` at `0x1809c594b`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c5a36`
- `OLEAUT32!__imp_SysAllocString` at `0x1809c5a36`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5839`
- `OLEAUT32!__imp_VariantClear` at `0x1809c59de`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5aab`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5ac5`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5adf`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5aef`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5aff`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5839`
- `OLEAUT32!__imp_VariantClear` at `0x1809c59de`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5aab`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5ac5`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5adf`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5aef`
- `OLEAUT32!__imp_VariantClear` at `0x1809c5aff`
- `OLEAUT32!__imp_VariantCopy` at `0x1809c58eb`
- `OLEAUT32!__imp_VariantCopy` at `0x1809c58eb`

## string_xrefs

- `0x1809c5903`: `__IE_TemplateUrl`
- `0x1809c5874`: `__IE_TemporaryFiles`
- `0x1809c5862`: `res://ieframe.dll/preview.dlg`

## pseudocode

```c
__int64 __fastcall HTMLDocumentSource::_Initialize(
        HTMLDocumentSource *this,
        struct IUnknown *a2,
        struct IWebPlatformHostSecurityManagerFactory *a3,
        char a4)
{
  __int64 *ppv; // rax
  HRESULT Instance; // ebx
  __int64 *v10; // rax
  __int64 *v11; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 *v14; // rax
  bool v15; // bl
  struct PrintManagerOptions **v16; // rax
  const WCHAR *bstrVal; // rdx
  PrintManagerOptions *v18; // rcx
  __int64 v19; // rax
  BSTR v20; // rax
  LONGLONG v22; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  LPMONIKER ppmk; // [rsp+50h] [rbp-B0h] BYREF
  LPUNKNOWN punkOuter; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v26; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvargSrc; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v28; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v29; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v30[8]; // [rsp+D0h] [rbp-30h] BYREF
  int v31; // [rsp+110h] [rbp+10h]
  int v32; // [rsp+138h] [rbp+38h]
  __int64 v33; // [rsp+168h] [rbp+68h]
  int v34; // [rsp+17Ch] [rbp+7Ch]
  struct IWebPlatformHostSecurityManagerFactory *v35; // [rsp+180h] [rbp+80h]
  WCHAR szURL[32]; // [rsp+190h] [rbp+90h] BYREF

  punkOuter = 0;
  ppv = TSmartPointer<ID3D11Device>::operator&((__int64 *)this + 12);
  Instance = CoCreateInstance(
               &CLSID_StdGlobalInterfaceTable,
               0,
               1u,
               &GUID_00000146_0000_0000_c000_000000000046,
               (LPVOID *)ppv);
  if ( Instance >= 0 )
  {
    v10 = TSmartPointer<ID3D11Device>::operator&((__int64 *)&punkOuter);
    Instance = HTMLDocumentSource::QueryInterface(this, &GUID_00000000_0000_0000_c000_000000000046, (void **)v10);
    if ( Instance >= 0 )
    {
      v11 = TSmartPointer<ID3D11Device>::operator&((__int64 *)this + 13);
      Instance = CoCreateFreeThreadedMarshaler(punkOuter, (LPUNKNOWN *)v11);
      if ( Instance >= 0 )
      {
        lpVtbl = a2->lpVtbl;
        v22 = 0;
        QueryInterface = lpVtbl->QueryInterface;
        v14 = TSmartPointer<ID3D11Device>::operator&(&v22);
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
                     a2,
                     &GUID_3050f48b_98b5_11cf_bb82_00aa00bdce0b,
                     v14);
        if ( Instance >= 0 )
        {
          memset(&v29, 0, sizeof(v29));
          v15 = 1;
          if ( (*(int (__fastcall **)(LONGLONG, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v22 + 64LL))(
                 v22,
                 L"__IE_Immersive",
                 0,
                 &v29) >= 0
            && v29.vt == 11
            && v29.iVal == -1 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            if ( (*(int (__fastcall **)(LONGLONG, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v22 + 64LL))(
                   v22,
                   L"__IE_ShrinkToFit",
                   0,
                   &pvarg) < 0
              || pvarg.vt != 11
              || pvarg.iVal != -1 )
            {
              v15 = 0;
            }
            VariantClear(&pvarg);
          }
          v16 = (struct PrintManagerOptions **)TSmartPointer<PrintManagerOptions>::operator&((char *)this + 112);
          Instance = PrintManagerOptions::Create(v15, v16);
          if ( Instance >= 0 )
          {
            memset(&v28, 0, sizeof(v28));
            wcscpy(szURL, L"res://ieframe.dll/priew.dlg");
            memset(&pvargSrc, 0, sizeof(pvargSrc));
            if ( (*(int (__fastcall **)(LONGLONG, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v22 + 64LL))(
                   v22,
                   L"__IE_TemporaryFiles",
                   0,
                   &pvargSrc) >= 0
              && pvargSrc.vt == 8200 )
            {
              VariantCopy((VARIANTARG *)((char *)this + 136), &pvargSrc);
            }
            if ( (*(int (__fastcall **)(LONGLONG, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v22 + 64LL))(
                   v22,
                   L"__IE_TemplateUrl",
                   0,
                   &v28) < 0
              || v28.vt != 8
              || (bstrVal = v28.bstrVal) == 0 )
            {
              bstrVal = szURL;
            }
            ppmk = 0;
            Instance = CreateURLMonikerEx(0, bstrVal, &ppmk, 1u);
            if ( Instance >= 0 )
            {
              v18 = (PrintManagerOptions *)*((_QWORD *)this + 14);
              memset(&pvarg, 0, sizeof(pvarg));
              pvarg.vt = 13;
              Instance = PrintManagerOptions::QueryInterface(
                           v18,
                           &GUID_00000000_0000_0000_c000_000000000046,
                           &pvarg.byref);
              if ( Instance >= 0 )
              {
                v19 = *(_QWORD *)v22;
                v26 = pvarg;
                Instance = (*(__int64 (__fastcall **)(LONGLONG, const unsigned __int16 *, VARIANTARG *, _QWORD))(v19 + 56))(
                             v22,
                             L"__PE_PrintManagerOptions",
                             &v26,
                             0);
                if ( Instance >= 0 )
                {
                  VariantClear(&pvarg);
                  pvarg.vt = 13;
                  pvarg.llVal = v22;
                  (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v22 + 8LL))(v22);
                  memset_0(v30, 0, 0xC0u);
                  memset(&v26, 0, sizeof(v26));
                  v26.vt = 8;
                  v20 = SysAllocString(0);
                  v30[0] = 0;
                  v26.llVal = (LONGLONG)v20;
                  v30[1] = ppmk;
                  v30[4] = &pvarg;
                  v30[7] = &v26;
                  v33 = 0;
                  v31 = 1;
                  v32 = 720;
                  v34 = 1;
                  v35 = a3;
                  Instance = InternalModelessDialog((struct HTMLDLGINFO *)v30, 0);
                  if ( Instance >= 0 )
                    *((_BYTE *)this + 160) = a4;
                  VariantClear(&v26);
                  HTMLDLGINFO::~HTMLDLGINFO((HTMLDLGINFO *)v30);
                }
              }
              VariantClear(&pvarg);
            }
            TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&ppmk);
            VariantClear(&pvargSrc);
            VariantClear(&v28);
          }
          VariantClear(&v29);
        }
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v22);
      }
    }
  }
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>((__int64 *)&punkOuter);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1809c56b0  mov     [rsp-8+arg_18], rbx
0x1809c56b5  push    rbp
0x1809c56b6  push    rsi
0x1809c56b7  push    rdi
0x1809c56b8  push    r14
0x1809c56ba  push    r15
0x1809c56bc  lea     rbp, [rsp-0E0h]
0x1809c56c4  sub     rsp, 1E0h
0x1809c56cb  mov     rax, cs:__security_cookie
0x1809c56d2  xor     rax, rsp
0x1809c56d5  mov     [rbp+100h+var_30], rax
0x1809c56dc  mov     rdi, rcx
0x1809c56df  mov     [rsp+200h+punkOuter], 0
0x1809c56e8  add     rcx, 60h ; '`'
0x1809c56ec  mov     r14b, r9b
0x1809c56ef  mov     r15, r8
0x1809c56f2  mov     rsi, rdx
0x1809c56f5  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809c56fa  xor     edx, edx; pUnkOuter
0x1809c56fc  mov     [rsp+200h+ppv], rax; ppv
0x1809c5701  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1809c5708  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1809c570f  lea     r8d, [rdx+1]; dwClsContext
0x1809c5713  call    cs:__imp_CoCreateInstance
0x1809c571a  nop     dword ptr [rax+rax+00h]
0x1809c571f  mov     ebx, eax
0x1809c5721  test    eax, eax
0x1809c5723  js      loc_1809C5B15
0x1809c5729  lea     rcx, [rsp+200h+punkOuter]
0x1809c572e  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809c5733  mov     r8, rax; void **
0x1809c5736  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1809c573d  mov     rcx, rdi; this
0x1809c5740  call    ?QueryInterface@HTMLDocumentSource@@UEAAJAEBU_GUID@@PEAPEAX@Z; HTMLDocumentSource::QueryInterface(_GUID const &,void * *)
0x1809c5745  mov     ebx, eax
0x1809c5747  test    eax, eax
0x1809c5749  js      loc_1809C5B15
0x1809c574f  lea     rcx, [rdi+68h]
0x1809c5753  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809c5758  mov     rcx, [rsp+200h+punkOuter]; punkOuter
0x1809c575d  mov     rdx, rax; ppunkMarshal
0x1809c5760  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1809c5767  nop     dword ptr [rax+rax+00h]
0x1809c576c  mov     ebx, eax
0x1809c576e  test    eax, eax
0x1809c5770  js      loc_1809C5B15
0x1809c5776  mov     rax, [rsi]
0x1809c5779  lea     rcx, [rsp+200h+var_1D0]
0x1809c577e  mov     [rsp+200h+var_1D0], 0
0x1809c5787  mov     rbx, [rax]
0x1809c578a  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809c578f  mov     r8, rax
0x1809c5792  lea     rdx, _GUID_3050f48b_98b5_11cf_bb82_00aa00bdce0b
0x1809c5799  mov     rax, rbx
0x1809c579c  mov     rcx, rsi
0x1809c579f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c57a4  mov     ebx, eax
0x1809c57a6  test    eax, eax
0x1809c57a8  js      loc_1809C5B0B
0x1809c57ae  mov     rcx, [rsp+200h+var_1D0]
0x1809c57b3  lea     r9, [rbp+100h+var_150]
0x1809c57b7  xor     eax, eax
0x1809c57b9  lea     rdx, aIeImmersive; "__IE_Immersive"
0x1809c57c0  mov     qword ptr [rbp+100h+var_150+10h], rax
0x1809c57c4  xorps   xmm0, xmm0
0x1809c57c7  movups  xmmword ptr [rbp+100h+var_150], xmm0
0x1809c57cb  mov     rax, [rcx]
0x1809c57ce  xor     r8d, r8d
0x1809c57d1  mov     bl, 1
0x1809c57d3  mov     rax, [rax+40h]
0x1809c57d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c57dc  test    eax, eax
0x1809c57de  js      short loc_1809C5845
0x1809c57e0  cmp     word ptr [rbp+100h+var_150], 0Bh
0x1809c57e5  jnz     short loc_1809C5845
0x1809c57e7  or      esi, 0FFFFFFFFh
0x1809c57ea  cmp     si, word ptr [rbp+100h+var_150+8]
0x1809c57ee  jnz     short loc_1809C5845
0x1809c57f0  mov     rcx, [rsp+200h+var_1D0]
0x1809c57f5  lea     r9, [rsp+200h+pvarg]
0x1809c57fa  xor     eax, eax
0x1809c57fc  lea     rdx, aIeShrinktofit; "__IE_ShrinkToFit"
0x1809c5803  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x1809c5808  xorps   xmm0, xmm0
0x1809c580b  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x1809c5810  mov     rax, [rcx]
0x1809c5813  xor     r8d, r8d
0x1809c5816  mov     rax, [rax+40h]
0x1809c581a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c581f  test    eax, eax
0x1809c5821  js      short loc_1809C5832
0x1809c5823  cmp     word ptr [rsp+200h+pvarg], 0Bh
0x1809c5829  jnz     short loc_1809C5832
0x1809c582b  cmp     si, word ptr [rsp+200h+pvarg+8]
0x1809c5830  jz      short loc_1809C5834
0x1809c5832  xor     bl, bl
0x1809c5834  lea     rcx, [rsp+200h+pvarg]; pvarg
0x1809c5839  call    cs:__imp_VariantClear
0x1809c5840  nop     dword ptr [rax+rax+00h]
0x1809c5845  lea     rcx, [rdi+70h]
0x1809c5849  call    ??I?$TSmartPointer@VPrintManagerOptions@@@@QEAAPEAPEAVPrintManagerOptions@@XZ; TSmartPointer<PrintManagerOptions>::operator&(void)
0x1809c584e  mov     rdx, rax; struct PrintManagerOptions **
0x1809c5851  mov     cl, bl; bool
0x1809c5853  call    ?Create@PrintManagerOptions@@SAJ_NPEAPEAV1@@Z; PrintManagerOptions::Create(bool,PrintManagerOptions * *)
0x1809c5858  mov     ebx, eax
0x1809c585a  test    eax, eax
0x1809c585c  js      loc_1809C5AFB
0x1809c5862  movups  xmm1, xmmword ptr cs:aResIeframeDllP_1; "res://ieframe.dll/preview.dlg"
0x1809c5869  mov     rcx, [rsp+200h+var_1D0]
0x1809c586e  lea     r9, [rbp+100h+pvargSrc]
0x1809c5872  xor     eax, eax
0x1809c5874  lea     rdx, aIeTemporaryfil; "__IE_TemporaryFiles"
0x1809c587b  xorps   xmm0, xmm0
0x1809c587e  mov     qword ptr [rbp+100h+var_168+10h], rax
0x1809c5882  movups  xmmword ptr [rbp+100h+var_168], xmm0
0x1809c5886  mov     qword ptr [rbp+100h+pvargSrc+10h], rax
0x1809c588a  xor     r8d, r8d
0x1809c588d  movups  xmm0, xmmword ptr cs:aResIeframeDllP_1+10h; "frame.dll/preview.dlg"
0x1809c5894  movups  xmmword ptr [rbp+100h+szURL], xmm1
0x1809c589b  movups  xmm1, xmmword ptr cs:aResIeframeDllP_1+20h; "l/preview.dlg"
0x1809c58a2  movups  [rbp+100h+var_60], xmm0
0x1809c58a9  movups  xmm0, xmmword ptr cs:aResIeframeDllP_1+2Ch; "iew.dlg"
0x1809c58b0  movups  [rbp+100h+var_50], xmm1
0x1809c58b7  xorps   xmm1, xmm1
0x1809c58ba  movups  [rbp+100h+var_50+0Ch], xmm0
0x1809c58c1  movups  xmmword ptr [rbp+100h+pvargSrc], xmm1
0x1809c58c5  mov     rax, [rcx]
0x1809c58c8  mov     rax, [rax+40h]
0x1809c58cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c58d1  test    eax, eax
0x1809c58d3  js      short loc_1809C58F7
0x1809c58d5  mov     eax, 2008h
0x1809c58da  cmp     word ptr [rbp+100h+pvargSrc], ax
0x1809c58de  jnz     short loc_1809C58F7
0x1809c58e0  lea     rcx, [rdi+88h]; pvargDest
0x1809c58e7  lea     rdx, [rbp+100h+pvargSrc]; pvargSrc
0x1809c58eb  call    cs:__imp_VariantCopy
0x1809c58f2  nop     dword ptr [rax+rax+00h]
0x1809c58f7  mov     rcx, [rsp+200h+var_1D0]
0x1809c58fc  lea     r9, [rbp+100h+var_168]
0x1809c5900  xor     r8d, r8d
0x1809c5903  lea     rdx, aIeTemplateurl; "__IE_TemplateUrl"
0x1809c590a  mov     rax, [rcx]
0x1809c590d  mov     rax, [rax+40h]
0x1809c5911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c5916  mov     ecx, 8
0x1809c591b  test    eax, eax
0x1809c591d  js      short loc_1809C592E
0x1809c591f  cmp     word ptr [rbp+100h+var_168], cx
0x1809c5923  jnz     short loc_1809C592E
0x1809c5925  mov     rdx, qword ptr [rbp+100h+var_168+8]
0x1809c5929  test    rdx, rdx
0x1809c592c  jnz     short loc_1809C5935
0x1809c592e  lea     rdx, [rbp+100h+szURL]; szURL
0x1809c5935  mov     r9d, 1; dwFlags
0x1809c593b  mov     [rsp+200h+ppmk], 0
0x1809c5944  lea     r8, [rsp+200h+ppmk]; ppmk
0x1809c5949  xor     ecx, ecx; pMkCtx
0x1809c594b  call    cs:__imp_CreateURLMonikerEx
0x1809c5952  nop     dword ptr [rax+rax+00h]
0x1809c5957  mov     ebx, eax
0x1809c5959  test    eax, eax
0x1809c595b  js      loc_1809C5AD1
0x1809c5961  mov     rcx, [rdi+70h]; this
0x1809c5965  lea     r8, [rsp+200h+pvarg+8]; void **
0x1809c596a  xor     eax, eax
0x1809c596c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1809c5973  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x1809c5978  xorps   xmm0, xmm0
0x1809c597b  mov     eax, 0Dh
0x1809c5980  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x1809c5985  mov     word ptr [rsp+200h+pvarg], ax
0x1809c598a  call    ?QueryInterface@PrintManagerOptions@@UEAAJAEBU_GUID@@PEAPEAX@Z; PrintManagerOptions::QueryInterface(_GUID const &,void * *)
0x1809c598f  mov     ebx, eax
0x1809c5991  test    eax, eax
0x1809c5993  js      loc_1809C5AC0
0x1809c5999  mov     rcx, [rsp+200h+var_1D0]
0x1809c599e  lea     r8, [rsp+200h+var_1A0]
0x1809c59a3  movups  xmm0, xmmword ptr [rsp+200h+pvarg]
0x1809c59a8  lea     rdx, aPePrintmanager; "__PE_PrintManagerOptions"
0x1809c59af  xor     r9d, r9d
0x1809c59b2  movsd   xmm1, qword ptr [rsp+200h+pvarg+10h]
0x1809c59b8  mov     rax, [rcx]
0x1809c59bb  movaps  xmmword ptr [rsp+200h+var_1A0], xmm0
0x1809c59c0  movsd   qword ptr [rsp+200h+var_1A0+10h], xmm1
0x1809c59c6  mov     rax, [rax+38h]
0x1809c59ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c59cf  mov     ebx, eax
0x1809c59d1  test    eax, eax
0x1809c59d3  js      loc_1809C5AC0
0x1809c59d9  lea     rcx, [rsp+200h+pvarg]; pvarg
0x1809c59de  call    cs:__imp_VariantClear
0x1809c59e5  nop     dword ptr [rax+rax+00h]
0x1809c59ea  mov     rcx, [rsp+200h+var_1D0]
0x1809c59ef  mov     eax, 0Dh
0x1809c59f4  mov     word ptr [rsp+200h+pvarg], ax
0x1809c59f9  mov     qword ptr [rsp+200h+pvarg+8], rcx
0x1809c59fe  mov     rax, [rcx]
0x1809c5a01  mov     rax, [rax+8]
0x1809c5a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809c5a0a  xor     edx, edx; Val
0x1809c5a0c  lea     rcx, [rbp+100h+var_130]; void *
0x1809c5a10  mov     r8d, 0C0h; Size
0x1809c5a16  call    memset_0
0x1809c5a1b  xor     eax, eax
0x1809c5a1d  xorps   xmm0, xmm0
0x1809c5a20  mov     qword ptr [rsp+200h+var_1A0+10h], rax
0x1809c5a25  xor     ecx, ecx; psz
0x1809c5a27  mov     eax, 8
0x1809c5a2c  movups  xmmword ptr [rsp+200h+var_1A0], xmm0
0x1809c5a31  mov     word ptr [rsp+200h+var_1A0], ax
0x1809c5a36  call    cs:__imp_SysAllocString
0x1809c5a3d  nop     dword ptr [rax+rax+00h]
0x1809c5a42  xor     edx, edx; int
0x1809c5a44  mov     [rbp+100h+var_130], 0
0x1809c5a4c  mov     qword ptr [rsp+200h+var_1A0+8], rax
0x1809c5a51  lea     rcx, [rbp+100h+var_130]; struct HTMLDLGINFO *
0x1809c5a55  mov     rax, [rsp+200h+ppmk]
0x1809c5a5a  mov     [rbp+100h+var_128], rax
0x1809c5a5e  lea     rax, [rsp+200h+pvarg]
0x1809c5a63  mov     [rbp+100h+var_110], rax
0x1809c5a67  lea     rax, [rsp+200h+var_1A0]
0x1809c5a6c  mov     [rbp+100h+var_F8], rax
0x1809c5a70  mov     [rbp+100h+var_98], 0
0x1809c5a78  mov     [rbp+100h+var_F0], 1
0x1809c5a7f  mov     [rbp+100h+var_C8], 2D0h
0x1809c5a86  mov     [rbp+100h+var_84], 1
0x1809c5a8d  mov     [rbp+100h+var_80], r15
0x1809c5a94  call    ?InternalModelessDialog@@YAJPEAUHTMLDLGINFO@@H@Z; InternalModelessDialog(HTMLDLGINFO *,int)
0x1809c5a99  mov     ebx, eax
0x1809c5a9b  test    eax, eax
0x1809c5a9d  js      short loc_1809C5AA6
0x1809c5a9f  mov     [rdi+0A0h], r14b
0x1809c5aa6  lea     rcx, [rsp+200h+var_1A0]; pvarg
0x1809c5aab  call    cs:__imp_VariantClear
0x1809c5ab2  nop     dword ptr [rax+rax+00h]
0x1809c5ab7  lea     rcx, [rbp+100h+var_130]; this
0x1809c5abb  call    ??1HTMLDLGINFO@@QEAA@XZ; HTMLDLGINFO::~HTMLDLGINFO(void)
0x1809c5ac0  lea     rcx, [rsp+200h+pvarg]; pvarg
0x1809c5ac5  call    cs:__imp_VariantClear
0x1809c5acc  nop     dword ptr [rax+rax+00h]
0x1809c5ad1  lea     rcx, [rsp+200h+ppmk]; void *
0x1809c5ad6  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809c5adb  lea     rcx, [rbp+100h+pvargSrc]; pvarg
0x1809c5adf  call    cs:__imp_VariantClear
0x1809c5ae6  nop     dword ptr [rax+rax+00h]
0x1809c5aeb  lea     rcx, [rbp+100h+var_168]; pvarg
0x1809c5aef  call    cs:__imp_VariantClear
0x1809c5af6  nop     dword ptr [rax+rax+00h]
0x1809c5afb  lea     rcx, [rbp+100h+var_150]; pvarg
0x1809c5aff  call    cs:__imp_VariantClear
0x1809c5b06  nop     dword ptr [rax+rax+00h]
0x1809c5b0b  lea     rcx, [rsp+200h+var_1D0]; void *
0x1809c5b10  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809c5b15  lea     rcx, [rsp+200h+punkOuter]; void *
0x1809c5b1a  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809c5b1f  mov     eax, ebx
0x1809c5b21  mov     rcx, [rbp+100h+var_30]
0x1809c5b28  xor     rcx, rsp; StackCookie
0x1809c5b2b  call    __security_check_cookie
0x1809c5b30  mov     rbx, [rsp+200h+arg_18]
0x1809c5b38  add     rsp, 1E0h
0x1809c5b3f  pop     r15
0x1809c5b41  pop     r14
0x1809c5b43  pop     rdi
0x1809c5b44  pop     rsi
0x1809c5b45  pop     rbp
0x1809c5b46  retn
```
