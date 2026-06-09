# HTMLDocumentSource::_Initialize(IUnknown *,IWebPlatformHostSecurityManagerFactory *,bool)

- ea: `0x1809b5ce4`
- end: `0x1809b6133`
- name: `?_Initialize@HTMLDocumentSource@@AEAAJPEAUIUnknown@@PEAUIWebPlatformHostSecurityManagerFactory@@_N@Z`
- size: `1103`
- prototype: `__int64 __fastcall(HTMLDocumentSource *__hidden this, struct IUnknown *, struct IWebPlatformHostSecurityManagerFactory *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1809b3ab8`

## callees

- `0x1801af6e0`
- `0x1801b0510`
- `0x1807e5680`
- `0x180822e50`
- `0x1808342c4`
- `0x1809b38c4`
- `0x1809b3be0`
- `0x1809b5ce4`
- `0x1809db94c`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1809b5d8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1809b5d8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1809b5d47`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1809b5d47`
- `urlmon!CreateURLMonikerEx` at `0x1809b5f67`
- `urlmon!CreateURLMonikerEx` at `0x1809b5f67`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b6046`
- `OLEAUT32!__imp_SysAllocString` at `0x1809b6046`
- `OLEAUT32!__imp_VariantClear` at `0x1809b5e61`
- `OLEAUT32!__imp_VariantClear` at `0x1809b5ff4`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60b5`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60c9`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60dd`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60e7`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60f1`
- `OLEAUT32!__imp_VariantClear` at `0x1809b5e61`
- `OLEAUT32!__imp_VariantClear` at `0x1809b5ff4`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60b5`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60c9`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60dd`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60e7`
- `OLEAUT32!__imp_VariantClear` at `0x1809b60f1`
- `OLEAUT32!__imp_VariantCopy` at `0x1809b5f0d`
- `OLEAUT32!__imp_VariantCopy` at `0x1809b5f0d`

## string_xrefs

- `0x1809b5f1f`: `__IE_TemplateUrl`
- `0x1809b5e96`: `__IE_TemporaryFiles`
- `0x1809b5e84`: `res://ieframe.dll/preview.dlg`

## pseudocode

```c
__int64 __fastcall HTMLDocumentSource::_Initialize(
        HTMLDocumentSource *this,
        struct IUnknown *a2,
        struct IWebPlatformHostSecurityManagerFactory *a3,
        char a4)
{
  LPVOID *ppv; // rax
  HRESULT Instance; // ebx
  void **v10; // rax
  LPUNKNOWN *v11; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v14; // rax
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
  ppv = (LPVOID *)TSmartPointer<ID3D11Device>::operator&((char *)this + 96);
  Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, ppv);
  if ( Instance >= 0 )
  {
    v10 = (void **)TSmartPointer<ID3D11Device>::operator&(&punkOuter);
    Instance = HTMLDocumentSource::QueryInterface(this, &GUID_00000000_0000_0000_c000_000000000046, v10);
    if ( Instance >= 0 )
    {
      v11 = (LPUNKNOWN *)TSmartPointer<ID3D11Device>::operator&((char *)this + 104);
      Instance = CoCreateFreeThreadedMarshaler(punkOuter, v11);
      if ( Instance >= 0 )
      {
        lpVtbl = a2->lpVtbl;
        v22 = 0;
        QueryInterface = lpVtbl->QueryInterface;
        v14 = TSmartPointer<ID3D11Device>::operator&(&v22);
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))QueryInterface)(
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
            TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&ppmk);
            VariantClear(&pvargSrc);
            VariantClear(&v28);
          }
          VariantClear(&v29);
        }
        TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v22);
      }
    }
  }
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&punkOuter);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1809b5ce4  mov     [rsp-8+arg_18], rbx
0x1809b5ce9  push    rbp
0x1809b5cea  push    rsi
0x1809b5ceb  push    rdi
0x1809b5cec  push    r14
0x1809b5cee  push    r15
0x1809b5cf0  lea     rbp, [rsp-0E0h]
0x1809b5cf8  sub     rsp, 1E0h
0x1809b5cff  mov     rax, cs:__security_cookie
0x1809b5d06  xor     rax, rsp
0x1809b5d09  mov     [rbp+100h+var_30], rax
0x1809b5d10  mov     rdi, rcx
0x1809b5d13  mov     [rsp+200h+punkOuter], 0
0x1809b5d1c  add     rcx, 60h ; '`'
0x1809b5d20  mov     r14b, r9b
0x1809b5d23  mov     r15, r8
0x1809b5d26  mov     rsi, rdx
0x1809b5d29  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809b5d2e  xor     edx, edx; pUnkOuter
0x1809b5d30  mov     [rsp+200h+ppv], rax; ppv
0x1809b5d35  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1809b5d3c  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1809b5d43  lea     r8d, [rdx+1]; dwClsContext
0x1809b5d47  call    cs:__imp_CoCreateInstance
0x1809b5d4d  mov     ebx, eax
0x1809b5d4f  test    eax, eax
0x1809b5d51  js      loc_1809B6101
0x1809b5d57  lea     rcx, [rsp+200h+punkOuter]
0x1809b5d5c  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809b5d61  mov     r8, rax; void **
0x1809b5d64  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1809b5d6b  mov     rcx, rdi; this
0x1809b5d6e  call    ?QueryInterface@HTMLDocumentSource@@UEAAJAEBU_GUID@@PEAPEAX@Z; HTMLDocumentSource::QueryInterface(_GUID const &,void * *)
0x1809b5d73  mov     ebx, eax
0x1809b5d75  test    eax, eax
0x1809b5d77  js      loc_1809B6101
0x1809b5d7d  lea     rcx, [rdi+68h]
0x1809b5d81  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809b5d86  mov     rcx, [rsp+200h+punkOuter]; punkOuter
0x1809b5d8b  mov     rdx, rax; ppunkMarshal
0x1809b5d8e  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1809b5d94  mov     ebx, eax
0x1809b5d96  test    eax, eax
0x1809b5d98  js      loc_1809B6101
0x1809b5d9e  mov     rax, [rsi]
0x1809b5da1  lea     rcx, [rsp+200h+var_1D0]
0x1809b5da6  mov     [rsp+200h+var_1D0], 0
0x1809b5daf  mov     rbx, [rax]
0x1809b5db2  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x1809b5db7  mov     r8, rax
0x1809b5dba  lea     rdx, _GUID_3050f48b_98b5_11cf_bb82_00aa00bdce0b
0x1809b5dc1  mov     rax, rbx
0x1809b5dc4  mov     rcx, rsi
0x1809b5dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b5dcc  mov     ebx, eax
0x1809b5dce  test    eax, eax
0x1809b5dd0  js      loc_1809B60F7
0x1809b5dd6  mov     rcx, [rsp+200h+var_1D0]
0x1809b5ddb  lea     r9, [rbp+100h+var_150]
0x1809b5ddf  xor     eax, eax
0x1809b5de1  lea     rdx, aIeImmersive; "__IE_Immersive"
0x1809b5de8  mov     qword ptr [rbp+100h+var_150+10h], rax
0x1809b5dec  xorps   xmm0, xmm0
0x1809b5def  movups  xmmword ptr [rbp+100h+var_150], xmm0
0x1809b5df3  mov     rax, [rcx]
0x1809b5df6  xor     r8d, r8d
0x1809b5df9  mov     bl, 1
0x1809b5dfb  mov     rax, [rax+40h]
0x1809b5dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b5e04  test    eax, eax
0x1809b5e06  js      short loc_1809B5E67
0x1809b5e08  cmp     word ptr [rbp+100h+var_150], 0Bh
0x1809b5e0d  jnz     short loc_1809B5E67
0x1809b5e0f  or      esi, 0FFFFFFFFh
0x1809b5e12  cmp     si, word ptr [rbp+100h+var_150+8]
0x1809b5e16  jnz     short loc_1809B5E67
0x1809b5e18  mov     rcx, [rsp+200h+var_1D0]
0x1809b5e1d  lea     r9, [rsp+200h+pvarg]
0x1809b5e22  xor     eax, eax
0x1809b5e24  lea     rdx, aIeShrinktofit; "__IE_ShrinkToFit"
0x1809b5e2b  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x1809b5e30  xorps   xmm0, xmm0
0x1809b5e33  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x1809b5e38  mov     rax, [rcx]
0x1809b5e3b  xor     r8d, r8d
0x1809b5e3e  mov     rax, [rax+40h]
0x1809b5e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b5e47  test    eax, eax
0x1809b5e49  js      short loc_1809B5E5A
0x1809b5e4b  cmp     word ptr [rsp+200h+pvarg], 0Bh
0x1809b5e51  jnz     short loc_1809B5E5A
0x1809b5e53  cmp     si, word ptr [rsp+200h+pvarg+8]
0x1809b5e58  jz      short loc_1809B5E5C
0x1809b5e5a  xor     bl, bl
0x1809b5e5c  lea     rcx, [rsp+200h+pvarg]; pvarg
0x1809b5e61  call    cs:__imp_VariantClear
0x1809b5e67  lea     rcx, [rdi+70h]
0x1809b5e6b  call    ??I?$TSmartPointer@VPrintManagerOptions@@@@QEAAPEAPEAVPrintManagerOptions@@XZ; TSmartPointer<PrintManagerOptions>::operator&(void)
0x1809b5e70  mov     rdx, rax; struct PrintManagerOptions **
0x1809b5e73  mov     cl, bl; bool
0x1809b5e75  call    ?Create@PrintManagerOptions@@SAJ_NPEAPEAV1@@Z; PrintManagerOptions::Create(bool,PrintManagerOptions * *)
0x1809b5e7a  mov     ebx, eax
0x1809b5e7c  test    eax, eax
0x1809b5e7e  js      loc_1809B60ED
0x1809b5e84  movups  xmm1, xmmword ptr cs:aResIeframeDllP_1; "res://ieframe.dll/preview.dlg"
0x1809b5e8b  mov     rcx, [rsp+200h+var_1D0]
0x1809b5e90  lea     r9, [rbp+100h+pvargSrc]
0x1809b5e94  xor     eax, eax
0x1809b5e96  lea     rdx, aIeTemporaryfil; "__IE_TemporaryFiles"
0x1809b5e9d  xorps   xmm0, xmm0
0x1809b5ea0  mov     qword ptr [rbp+100h+var_168+10h], rax
0x1809b5ea4  movups  xmmword ptr [rbp+100h+var_168], xmm0
0x1809b5ea8  mov     qword ptr [rbp+100h+pvargSrc+10h], rax
0x1809b5eac  xor     r8d, r8d
0x1809b5eaf  movups  xmm0, xmmword ptr cs:aResIeframeDllP_1+10h; "frame.dll/preview.dlg"
0x1809b5eb6  movups  xmmword ptr [rbp+100h+szURL], xmm1
0x1809b5ebd  movups  xmm1, xmmword ptr cs:aResIeframeDllP_1+20h; "l/preview.dlg"
0x1809b5ec4  movups  [rbp+100h+var_60], xmm0
0x1809b5ecb  movups  xmm0, xmmword ptr cs:aResIeframeDllP_1+2Ch; "iew.dlg"
0x1809b5ed2  movups  [rbp+100h+var_50], xmm1
0x1809b5ed9  xorps   xmm1, xmm1
0x1809b5edc  movups  [rbp+100h+var_50+0Ch], xmm0
0x1809b5ee3  movups  xmmword ptr [rbp+100h+pvargSrc], xmm1
0x1809b5ee7  mov     rax, [rcx]
0x1809b5eea  mov     rax, [rax+40h]
0x1809b5eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b5ef3  test    eax, eax
0x1809b5ef5  js      short loc_1809B5F13
0x1809b5ef7  mov     eax, 2008h
0x1809b5efc  cmp     word ptr [rbp+100h+pvargSrc], ax
0x1809b5f00  jnz     short loc_1809B5F13
0x1809b5f02  lea     rcx, [rdi+88h]; pvargDest
0x1809b5f09  lea     rdx, [rbp+100h+pvargSrc]; pvargSrc
0x1809b5f0d  call    cs:__imp_VariantCopy
0x1809b5f13  mov     rcx, [rsp+200h+var_1D0]
0x1809b5f18  lea     r9, [rbp+100h+var_168]
0x1809b5f1c  xor     r8d, r8d
0x1809b5f1f  lea     rdx, aIeTemplateurl; "__IE_TemplateUrl"
0x1809b5f26  mov     rax, [rcx]
0x1809b5f29  mov     rax, [rax+40h]
0x1809b5f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b5f32  mov     ecx, 8
0x1809b5f37  test    eax, eax
0x1809b5f39  js      short loc_1809B5F4A
0x1809b5f3b  cmp     word ptr [rbp+100h+var_168], cx
0x1809b5f3f  jnz     short loc_1809B5F4A
0x1809b5f41  mov     rdx, qword ptr [rbp+100h+var_168+8]
0x1809b5f45  test    rdx, rdx
0x1809b5f48  jnz     short loc_1809B5F51
0x1809b5f4a  lea     rdx, [rbp+100h+szURL]; szURL
0x1809b5f51  mov     r9d, 1; dwFlags
0x1809b5f57  mov     [rsp+200h+ppmk], 0
0x1809b5f60  lea     r8, [rsp+200h+ppmk]; ppmk
0x1809b5f65  xor     ecx, ecx; pMkCtx
0x1809b5f67  call    cs:__imp_CreateURLMonikerEx
0x1809b5f6d  mov     ebx, eax
0x1809b5f6f  test    eax, eax
0x1809b5f71  js      loc_1809B60CF
0x1809b5f77  mov     rcx, [rdi+70h]; this
0x1809b5f7b  lea     r8, [rsp+200h+pvarg+8]; void **
0x1809b5f80  xor     eax, eax
0x1809b5f82  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1809b5f89  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x1809b5f8e  xorps   xmm0, xmm0
0x1809b5f91  mov     eax, 0Dh
0x1809b5f96  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x1809b5f9b  mov     word ptr [rsp+200h+pvarg], ax
0x1809b5fa0  call    ?QueryInterface@PrintManagerOptions@@UEAAJAEBU_GUID@@PEAPEAX@Z; PrintManagerOptions::QueryInterface(_GUID const &,void * *)
0x1809b5fa5  mov     ebx, eax
0x1809b5fa7  test    eax, eax
0x1809b5fa9  js      loc_1809B60C4
0x1809b5faf  mov     rcx, [rsp+200h+var_1D0]
0x1809b5fb4  lea     r8, [rsp+200h+var_1A0]
0x1809b5fb9  movups  xmm0, xmmword ptr [rsp+200h+pvarg]
0x1809b5fbe  lea     rdx, aPePrintmanager; "__PE_PrintManagerOptions"
0x1809b5fc5  xor     r9d, r9d
0x1809b5fc8  movsd   xmm1, qword ptr [rsp+200h+pvarg+10h]
0x1809b5fce  mov     rax, [rcx]
0x1809b5fd1  movaps  xmmword ptr [rsp+200h+var_1A0], xmm0
0x1809b5fd6  movsd   qword ptr [rsp+200h+var_1A0+10h], xmm1
0x1809b5fdc  mov     rax, [rax+38h]
0x1809b5fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b5fe5  mov     ebx, eax
0x1809b5fe7  test    eax, eax
0x1809b5fe9  js      loc_1809B60C4
0x1809b5fef  lea     rcx, [rsp+200h+pvarg]; pvarg
0x1809b5ff4  call    cs:__imp_VariantClear
0x1809b5ffa  mov     rcx, [rsp+200h+var_1D0]
0x1809b5fff  mov     eax, 0Dh
0x1809b6004  mov     word ptr [rsp+200h+pvarg], ax
0x1809b6009  mov     qword ptr [rsp+200h+pvarg+8], rcx
0x1809b600e  mov     rax, [rcx]
0x1809b6011  mov     rax, [rax+8]
0x1809b6015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1809b601a  xor     edx, edx; Val
0x1809b601c  lea     rcx, [rbp+100h+var_130]; void *
0x1809b6020  mov     r8d, 0C0h; Size
0x1809b6026  call    memset_0
0x1809b602b  xor     eax, eax
0x1809b602d  xorps   xmm0, xmm0
0x1809b6030  mov     qword ptr [rsp+200h+var_1A0+10h], rax
0x1809b6035  xor     ecx, ecx; psz
0x1809b6037  mov     eax, 8
0x1809b603c  movups  xmmword ptr [rsp+200h+var_1A0], xmm0
0x1809b6041  mov     word ptr [rsp+200h+var_1A0], ax
0x1809b6046  call    cs:__imp_SysAllocString
0x1809b604c  xor     edx, edx; int
0x1809b604e  mov     [rbp+100h+var_130], 0
0x1809b6056  mov     qword ptr [rsp+200h+var_1A0+8], rax
0x1809b605b  lea     rcx, [rbp+100h+var_130]; struct HTMLDLGINFO *
0x1809b605f  mov     rax, [rsp+200h+ppmk]
0x1809b6064  mov     [rbp+100h+var_128], rax
0x1809b6068  lea     rax, [rsp+200h+pvarg]
0x1809b606d  mov     [rbp+100h+var_110], rax
0x1809b6071  lea     rax, [rsp+200h+var_1A0]
0x1809b6076  mov     [rbp+100h+var_F8], rax
0x1809b607a  mov     [rbp+100h+var_98], 0
0x1809b6082  mov     [rbp+100h+var_F0], 1
0x1809b6089  mov     [rbp+100h+var_C8], 2D0h
0x1809b6090  mov     [rbp+100h+var_84], 1
0x1809b6097  mov     [rbp+100h+var_80], r15
0x1809b609e  call    ?InternalModelessDialog@@YAJPEAUHTMLDLGINFO@@H@Z; InternalModelessDialog(HTMLDLGINFO *,int)
0x1809b60a3  mov     ebx, eax
0x1809b60a5  test    eax, eax
0x1809b60a7  js      short loc_1809B60B0
0x1809b60a9  mov     [rdi+0A0h], r14b
0x1809b60b0  lea     rcx, [rsp+200h+var_1A0]; pvarg
0x1809b60b5  call    cs:__imp_VariantClear
0x1809b60bb  lea     rcx, [rbp+100h+var_130]; this
0x1809b60bf  call    ??1HTMLDLGINFO@@QEAA@XZ; HTMLDLGINFO::~HTMLDLGINFO(void)
0x1809b60c4  lea     rcx, [rsp+200h+pvarg]; pvarg
0x1809b60c9  call    cs:__imp_VariantClear
0x1809b60cf  lea     rcx, [rsp+200h+ppmk]; void *
0x1809b60d4  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809b60d9  lea     rcx, [rbp+100h+pvargSrc]; pvarg
0x1809b60dd  call    cs:__imp_VariantClear
0x1809b60e3  lea     rcx, [rbp+100h+var_168]; pvarg
0x1809b60e7  call    cs:__imp_VariantClear
0x1809b60ed  lea     rcx, [rbp+100h+var_150]; pvarg
0x1809b60f1  call    cs:__imp_VariantClear
0x1809b60f7  lea     rcx, [rsp+200h+var_1D0]; void *
0x1809b60fc  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809b6101  lea     rcx, [rsp+200h+punkOuter]; void *
0x1809b6106  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x1809b610b  mov     eax, ebx
0x1809b610d  mov     rcx, [rbp+100h+var_30]
0x1809b6114  xor     rcx, rsp; StackCookie
0x1809b6117  call    __security_check_cookie
0x1809b611c  mov     rbx, [rsp+200h+arg_18]
0x1809b6124  add     rsp, 1E0h
0x1809b612b  pop     r15
0x1809b612d  pop     r14
0x1809b612f  pop     rdi
0x1809b6130  pop     rsi
0x1809b6131  pop     rbp
0x1809b6132  retn
```
