# COMSafeControlRoot::getBaseURLFromSite(IUnknown *)

- ea: `0x1012d2e3`
- end: `0x1012d8f8`
- name: `?getBaseURLFromSite@COMSafeControlRoot@@SGPAVString@@PAUIUnknown@@@Z`
- size: `1557`
- prototype: `String *__userpurge@<eax>(IUnknown *pSite@<ecx>)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1012df20`

## callees

- `0x1003fba3`
- `0x1003fe02`
- `0x10040be6`
- `0x10040c44`
- `0x10064cf1`
- `0x10064d24`
- `0x10064e0d`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x10078765`
- `0x1012c790`
- `0x1012d2e3`
- `0x10131626`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012d88f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012d88f`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1012d31a`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1012d31a`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d65e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d898`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d8a1`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d8aa`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d65e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d898`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d8a1`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d8aa`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d5cc`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d61c`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d5cc`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d61c`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d335`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d4ee`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d502`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d335`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d4ee`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d502`
- `OLEAUT32!__imp__VariantClear@4` at `0x1012d8b4`
- `OLEAUT32!__imp__VariantClear@4` at `0x1012d8b4`

## pseudocode

```c
String *__thiscall COMSafeControlRoot::getBaseURLFromSite(IUnknown *pSite)
{
  IUnknown *v1; // edi
  HRESULT v2; // eax
  String *v3; // esi
  String *v4; // edi
  int v5; // eax
  String *v6; // esi
  signed int v7; // eax
  const wchar_t *bstrVal; // esi
  UINT v9; // eax
  ArrayString *v10; // ebx
  int v11; // ecx
  int v12; // eax
  String *p; // esi
  String *v14; // esi
  Exception *v15; // eax
  tagVARIANT varEmpty; // [esp+10h] [ebp-90h] BYREF
  tagVARIANT varIndex; // [esp+20h] [ebp-80h] BYREF
  tagVARIANT varHref; // [esp+30h] [ebp-70h] BYREF
  Exception *v20; // [esp+40h] [ebp-60h]
  wchar_t *bstrHref; // [esp+44h] [ebp-5Ch]
  IUnknown *v22; // [esp+48h] [ebp-58h]
  wchar_t *pOleStr; // [esp+4Ch] [ebp-54h] BYREF
  IXMLDOMDocument *pXmlDoc; // [esp+50h] [ebp-50h] BYREF
  IBindHost *pBH; // [esp+54h] [ebp-4Ch] BYREF
  IMoniker *pMk; // [esp+58h] [ebp-48h] BYREF
  int lLength; // [esp+5Ch] [ebp-44h] BYREF
  int i; // [esp+60h] [ebp-40h]
  IDispatch *pDisp; // [esp+64h] [ebp-3Ch] BYREF
  IServiceProvider *pSP; // [esp+68h] [ebp-38h] BYREF
  wchar_t *pDocURL; // [esp+6Ch] [ebp-34h] BYREF
  IHTMLElement *e; // [esp+70h] [ebp-30h] BYREF
  IHTMLDocument2 *pHtmlDoc; // [esp+74h] [ebp-2Ch] BYREF
  wchar_t *bstrTagName; // [esp+78h] [ebp-28h] BYREF
  IHTMLElementCollection *pAll; // [esp+7Ch] [ebp-24h] BYREF
  String *relativeURL; // [esp+80h] [ebp-20h]
  _reference<String> pResult; // [esp+84h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+88h] [ebp-18h]

  v22 = pSite;
  pSP = 0;
  pBH = 0;
  pMk = 0;
  pHtmlDoc = 0;
  pXmlDoc = 0;
  pOleStr = 0;
  pAll = 0;
  pDisp = 0;
  e = 0;
  pDocURL = 0;
  bstrHref = SysAllocString(L"HREF");
  bstrTagName = 0;
  v20 = 0;
  if ( !bstrHref )
  {
    Exception::throw_E_OUTOFMEMORY();
    goto LABEL_74;
  }
  VariantInit(&varHref);
  relativeURL = 0;
  pResult._p = 0;
  ms_exc.registration.TryLevel = 0;
  v1 = v22;
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IXMLDOMDocument **))v22->QueryInterface)(
         v22->QueryInterface,
         v22,
         &IID_IXMLDOMDocument,
         &pXmlDoc) >= 0 )
  {
    v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMDocument *, wchar_t **), IXMLDOMDocument *, wchar_t **))pXmlDoc->get_url)(
           pXmlDoc->get_url,
           pXmlDoc,
           &pDocURL);
    if ( v2 >= 0 )
    {
      v3 = String::newString(pDocURL);
      release(&pResult._p);
      pResult._p = v3;
      ms_exc.registration.TryLevel = -2;
      v4 = v3;
      goto Cleanup_21;
    }
LABEL_74:
    Exception::throwHR(v2);
    goto LABEL_75;
  }
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IServiceProvider **))v1->QueryInterface)(
         v1->QueryInterface,
         v1,
         &IID_IServiceProvider,
         &pSP) < 0 )
  {
    v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IHTMLDocument2 **))v1->QueryInterface)(
           v1->QueryInterface,
           v1,
           &IID_IHTMLDocument2,
           &pHtmlDoc);
    goto LABEL_7;
  }
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, GUID *, GUID *, IBindHost **))pSP->QueryService)(
         pSP->QueryService,
         pSP,
         &IID_IBindHost,
         &IID_IBindHost,
         &pBH) < 0 )
  {
    if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, SID *, GUID *, IHTMLDocument2 **))pSP->QueryService)(
           pSP->QueryService,
           pSP,
           &SID_SContainerDispatch,
           &IID_IHTMLDocument2,
           &pHtmlDoc) >= 0 )
      goto QueryHTMLDoc;
    v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, GUID *, GUID *, IHTMLDocument2 **))pSP->QueryService)(
           pSP->QueryService,
           pSP,
           &IID_IInternetHostSecurityManager,
           &IID_IHTMLDocument2,
           &pHtmlDoc);
LABEL_7:
    if ( v5 < 0 )
    {
LABEL_8:
      ms_exc.registration.TryLevel = -2;
      v4 = relativeURL;
      goto Cleanup_21;
    }
QueryHTMLDoc:
    v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLDocument2 *, IHTMLElementCollection **), IHTMLDocument2 *, IHTMLElementCollection **))pHtmlDoc->get_all)(
           pHtmlDoc->get_all,
           pHtmlDoc,
           &pAll);
    if ( v2 < 0 )
      goto LABEL_74;
    if ( pAll )
    {
      VariantInit(&varIndex);
      varIndex.vt = 3;
      VariantInit(&varEmpty);
      lLength = 0;
      v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLElementCollection *, int *), IHTMLElementCollection *, int *))pAll->get_length)(
             pAll->get_length,
             pAll,
             &lLength);
      if ( v2 < 0 )
        goto LABEL_74;
      v7 = 0;
      i = 0;
      while ( v7 < lLength )
      {
        varIndex.decVal.Lo32 = v7;
        v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLElementCollection *, tagVARIANT, tagVARIANT, IDispatch **), IHTMLElementCollection *, _DWORD, unsigned int, signed int, unsigned int, _DWORD, unsigned int, unsigned int, unsigned int, IDispatch **))pAll->item)(
               pAll->item,
               pAll,
               *(_DWORD *)&varIndex.vt,
               varIndex.decVal.Hi32,
               v7,
               varIndex.decVal.Mid32,
               *(_DWORD *)&varEmpty.vt,
               varEmpty.decVal.Hi32,
               varEmpty.decVal.Lo32,
               varEmpty.decVal.Mid32,
               &pDisp);
        if ( v2 < 0 )
          goto LABEL_74;
        if ( pDisp )
        {
          if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IDispatch *, GUID *, IHTMLElement **))pDisp->QueryInterface)(
                 pDisp->QueryInterface,
                 pDisp,
                 &IID_IHTMLElement,
                 &e) >= 0 )
          {
            if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLElement *, wchar_t **), IHTMLElement *, wchar_t **))e->get_tagName)(
                   e->get_tagName,
                   e,
                   &bstrTagName) >= 0
              && bstrTagName )
            {
              if ( SysStringLen(bstrTagName) == 4 )
              {
                if ( fastcmpni(bstrTagName, L"BASE", 4u) )
                {
                  v12 = fastcmpni(bstrTagName, L"BODY", 4u);
                  v11 = i;
                  if ( !v12 )
                    v11 = lLength;
                }
                else
                {
                  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLElement *, wchar_t *, int, tagVARIANT *), IHTMLElement *, wchar_t *, _DWORD, tagVARIANT *))e->getAttribute)(
                         e->getAttribute,
                         e,
                         bstrHref,
                         0,
                         &varHref) >= 0
                    && varHref.vt == 8 )
                  {
                    bstrVal = varHref.bstrVal;
                    if ( varHref.decVal.Lo32 )
                    {
                      v9 = SysStringLen(varHref.bstrVal);
                      v10 = String::newString(bstrVal, v9);
                      relativeURL = v10;
                      release(&pResult._p);
                      pResult._p = v10;
                    }
                  }
                  v11 = lLength;
                }
                i = v11;
              }
              SysFreeString(bstrTagName);
              bstrTagName = 0;
            }
            if ( e )
            {
              ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IHTMLElement *))e->Release)(e->Release, e);
              e = 0;
            }
          }
          if ( pDisp )
          {
            ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IDispatch *))pDisp->Release)(
              pDisp->Release,
              pDisp);
            pDisp = 0;
          }
        }
        v7 = ++i;
      }
      if ( pAll )
      {
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IHTMLElementCollection *))pAll->Release)(
          pAll->Release,
          pAll);
        pAll = 0;
      }
      v1 = v22;
    }
    if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLDocument2 *, wchar_t **), IHTMLDocument2 *, wchar_t **))pHtmlDoc->get_URL)(
           pHtmlDoc->get_URL,
           pHtmlDoc,
           &pDocURL) < 0 )
      goto LABEL_8;
    p = relativeURL;
    if ( !relativeURL )
      goto LABEL_52;
    if ( pDocURL && *pDocURL && !AllowBaseTagUrl(v1, relativeURL->_pwsz, pDocURL) )
    {
      assign(&pResult._p, 0);
      p = pResult._p;
      relativeURL = pResult._p;
    }
    if ( !p || (v14 = URL::resolveURL(p, pDocURL), relativeURL = v14, release(&pResult._p), (pResult._p = v14) == 0) )
    {
LABEL_52:
      v4 = String::newString(pDocURL);
      release(&pResult._p);
      pResult._p = v4;
      goto LABEL_54;
    }
LABEL_53:
    v4 = relativeURL;
    goto LABEL_54;
  }
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IBindHost *, wchar_t *, IBindCtx *, IMoniker **, unsigned int), IBindHost *, const wchar_t *, _DWORD, IMoniker **, _DWORD))pBH->CreateMoniker)(
         pBH->CreateMoniker,
         pBH,
         L".",
         0,
         &pMk,
         0) < 0 )
    goto LABEL_8;
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IMoniker *, IBindCtx *, IMoniker *, wchar_t **), IMoniker *, _DWORD, _DWORD, wchar_t **))pMk->GetDisplayName)(
         pMk->GetDisplayName,
         pMk,
         0,
         0,
         &pOleStr) < 0 )
    goto LABEL_53;
  v6 = String::newString(pOleStr);
  release(&pResult._p);
  pResult._p = v6;
  v4 = v6;
LABEL_54:
  ms_exc.registration.TryLevel = -2;
Cleanup_21:
  if ( pMk )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pMk->Release)(pMk->Release, pMk);
    pMk = 0;
  }
  if ( pBH )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IBindHost *))pBH->Release)(pBH->Release, pBH);
    pBH = 0;
  }
  if ( pSP )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IServiceProvider *))pSP->Release)(pSP->Release, pSP);
    pSP = 0;
  }
  if ( pHtmlDoc )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IHTMLDocument2 *))pHtmlDoc->Release)(
      pHtmlDoc->Release,
      pHtmlDoc);
    pHtmlDoc = 0;
  }
  if ( pXmlDoc )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IXMLDOMDocument *))pXmlDoc->Release)(
      pXmlDoc->Release,
      pXmlDoc);
    pXmlDoc = 0;
  }
  if ( e )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IHTMLElement *))e->Release)(e->Release, e);
    e = 0;
  }
  if ( pDisp )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IDispatch *))pDisp->Release)(pDisp->Release, pDisp);
    pDisp = 0;
  }
  if ( pAll )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IHTMLElementCollection *))pAll->Release)(
      pAll->Release,
      pAll);
    pAll = 0;
  }
  CoTaskMemFree(pOleStr);
  SysFreeString(bstrHref);
  SysFreeString(pDocURL);
  SysFreeString(bstrTagName);
  VariantClear(&varHref);
  v15 = v20;
  if ( v20 )
  {
LABEL_75:
    Exception::throwThis(v15);
    JUMPOUT(0x1012D8F1);
  }
  pResult._p = 0;
  release(&pResult._p);
  return v4;
}

```

## disassembly

```asm
0x1012d2e3  push    80h
0x1012d2e8  push    offset stru_1017C868
0x1012d2ed  call    __SEH_prolog4
0x1012d2f2  mov     [ebp+var_58], pSite
0x1012d2f5  xor     ebx, ebx
0x1012d2f7  mov     [ebp+pSP], ebx
0x1012d2fa  mov     [ebp+pBH], ebx
0x1012d2fd  mov     [ebp+pMk], ebx
0x1012d300  mov     [ebp+pHtmlDoc], ebx
0x1012d303  mov     [ebp+pXmlDoc], ebx
0x1012d306  mov     [ebp+pOleStr], ebx
0x1012d309  mov     [ebp+pAll], ebx
0x1012d30c  mov     [ebp+pDisp], ebx
0x1012d30f  mov     [ebp+e], ebx
0x1012d312  mov     [ebp+pDocURL], ebx
0x1012d315  push    offset aHref_0; "HREF"
0x1012d31a  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1012d320  mov     [ebp+bstrHref], eax
0x1012d323  mov     [ebp+bstrTagName], ebx
0x1012d326  mov     [ebp+var_60], ebx
0x1012d329  test    eax, eax
0x1012d32b  jz      loc_1012D8DE
0x1012d331  lea     eax, [ebp+varHref]
0x1012d334  push    eax; pvarg
0x1012d335  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1012d33b  mov     edi, ebx
0x1012d33d  mov     [ebp+relativeURL], edi
0x1012d340  mov     [ebp+pResult._p], edi
0x1012d343  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1012d346  mov     edi, [ebp+var_58]
0x1012d349  mov     eax, [edi]
0x1012d34b  mov     esi, [eax]
0x1012d34d  lea     eax, [ebp+pXmlDoc]
0x1012d350  push    eax
0x1012d351  push    offset _IID_IXMLDOMDocument
0x1012d356  push    edi
0x1012d357  mov     pSite, esi; this
0x1012d359  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d35f  call    esi
0x1012d361  test    eax, eax
0x1012d363  js      short loc_1012D3AA
0x1012d365  mov     pSite, [ebp+pXmlDoc]
0x1012d368  mov     eax, [pSite]
0x1012d36a  mov     esi, [eax+0F4h]
0x1012d370  lea     eax, [ebp+pDocURL]
0x1012d373  push    eax
0x1012d374  push    pSite
0x1012d375  mov     pSite, esi; this
0x1012d377  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d37d  call    esi
0x1012d37f  test    eax, eax
0x1012d381  js      loc_1012D8E3
0x1012d387  mov     pSite, [ebp+pDocURL]; c
0x1012d38a  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1012d38f  mov     esi, eax
0x1012d391  lea     pSite, [ebp+pResult]; ppref
0x1012d394  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012d399  mov     [ebp+pResult._p], esi
0x1012d39c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012d3a3  mov     edi, esi
0x1012d3a5  jmp     Cleanup_21
0x1012d3aa  mov     eax, [edi]
0x1012d3ac  mov     esi, [eax]
0x1012d3ae  lea     eax, [ebp+pSP]
0x1012d3b1  push    eax
0x1012d3b2  push    offset _IID_IServiceProvider
0x1012d3b7  push    edi
0x1012d3b8  mov     pSite, esi; this
0x1012d3ba  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d3c0  call    esi
0x1012d3c2  test    eax, eax
0x1012d3c4  jns     short loc_1012D3F5
0x1012d3c6  mov     eax, [edi]
0x1012d3c8  mov     esi, [eax]
0x1012d3ca  lea     eax, [ebp+pHtmlDoc]
0x1012d3cd  push    eax
0x1012d3ce  push    offset _IID_IHTMLDocument2
0x1012d3d3  push    edi
0x1012d3d4  mov     pSite, esi; this
0x1012d3d6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d3dc  call    esi
0x1012d3de  test    eax, eax
0x1012d3e0  jns     QueryHTMLDoc
0x1012d3e6  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012d3ed  mov     edi, [ebp+relativeURL]
0x1012d3f0  jmp     Cleanup_21
0x1012d3f5  mov     pSite, [ebp+pSP]
0x1012d3f8  mov     eax, [pSite]
0x1012d3fa  mov     esi, [eax+0Ch]
0x1012d3fd  lea     eax, [ebp+pBH]
0x1012d400  push    eax
0x1012d401  mov     eax, offset _IID_IBindHost
0x1012d406  push    eax
0x1012d407  push    eax
0x1012d408  push    pSite
0x1012d409  mov     pSite, esi; this
0x1012d40b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d411  call    esi
0x1012d413  test    eax, eax
0x1012d415  js      short loc_1012D476
0x1012d417  mov     pSite, [ebp+pBH]
0x1012d41a  mov     eax, [pSite]
0x1012d41c  mov     esi, [eax+0Ch]
0x1012d41f  push    ebx
0x1012d420  lea     eax, [ebp+pMk]
0x1012d423  push    eax
0x1012d424  push    ebx
0x1012d425  push    offset asc_100351E8; "."
0x1012d42a  push    pSite
0x1012d42b  mov     pSite, esi; this
0x1012d42d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d433  call    esi
0x1012d435  test    eax, eax
0x1012d437  js      short loc_1012D3E6
0x1012d439  mov     pSite, [ebp+pMk]
0x1012d43c  mov     eax, [pSite]
0x1012d43e  mov     esi, [eax+50h]
0x1012d441  lea     eax, [ebp+pOleStr]
0x1012d444  push    eax
0x1012d445  push    ebx
0x1012d446  push    ebx
0x1012d447  push    pSite
0x1012d448  mov     pSite, esi; this
0x1012d44a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d450  call    esi
0x1012d452  test    eax, eax
0x1012d454  js      loc_1012D763
0x1012d45a  mov     pSite, [ebp+pOleStr]; c
0x1012d45d  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1012d462  mov     esi, eax
0x1012d464  lea     pSite, [ebp+pResult]; ppref
0x1012d467  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012d46c  mov     [ebp+pResult._p], esi
0x1012d46f  mov     edi, esi
0x1012d471  jmp     loc_1012D766
0x1012d476  mov     pSite, [ebp+pSP]
0x1012d479  mov     eax, [pSite]
0x1012d47b  mov     esi, [eax+0Ch]
0x1012d47e  lea     eax, [ebp+pHtmlDoc]
0x1012d481  push    eax
0x1012d482  push    offset _IID_IHTMLDocument2
0x1012d487  push    offset _SID_SContainerDispatch
0x1012d48c  push    pSite
0x1012d48d  mov     pSite, esi; this
0x1012d48f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d495  call    esi
0x1012d497  test    eax, eax
0x1012d499  jns     short QueryHTMLDoc
0x1012d49b  mov     pSite, [ebp+pSP]
0x1012d49e  mov     eax, [pSite]
0x1012d4a0  mov     esi, [eax+0Ch]
0x1012d4a3  lea     eax, [ebp+pHtmlDoc]
0x1012d4a6  push    eax
0x1012d4a7  push    offset _IID_IHTMLDocument2
0x1012d4ac  push    offset _IID_IInternetHostSecurityManager
0x1012d4b1  push    pSite
0x1012d4b2  mov     pSite, esi; this
0x1012d4b4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d4ba  call    esi
0x1012d4bc  jmp     loc_1012D3DE
0x1012d4c1  mov     pSite, [ebp+pHtmlDoc]
0x1012d4c4  mov     eax, [pSite]
0x1012d4c6  mov     esi, [eax+20h]
0x1012d4c9  lea     eax, [ebp+pAll]
0x1012d4cc  push    eax
0x1012d4cd  push    pSite
0x1012d4ce  mov     pSite, esi; this
0x1012d4d0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d4d6  call    esi
0x1012d4d8  test    eax, eax
0x1012d4da  js      loc_1012D8E3
0x1012d4e0  cmp     [ebp+pAll], 0
0x1012d4e4  jz      loc_1012D6D6
0x1012d4ea  lea     eax, [ebp+varIndex]
0x1012d4ed  push    eax; pvarg
0x1012d4ee  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1012d4f4  push    3
0x1012d4f6  pop     eax
0x1012d4f7  mov     word ptr [ebp+varIndex.___u0], ax
0x1012d4fb  lea     eax, [ebp+varEmpty]
0x1012d501  push    eax; pvarg
0x1012d502  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1012d508  mov     [ebp+lLength], ebx
0x1012d50b  mov     pSite, [ebp+pAll]
0x1012d50e  mov     eax, [pSite]
0x1012d510  mov     esi, [eax+24h]
0x1012d513  lea     eax, [ebp+lLength]
0x1012d516  push    eax
0x1012d517  push    pSite
0x1012d518  mov     pSite, esi; this
0x1012d51a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d520  call    esi
0x1012d522  test    eax, eax
0x1012d524  js      loc_1012D8E3
0x1012d52a  mov     eax, ebx
0x1012d52c  mov     [ebp+i], ebx
0x1012d52f  cmp     eax, [ebp+lLength]
0x1012d532  jge     loc_1012D6B3
0x1012d538  mov     dword ptr [ebp+varIndex.___u0+8], eax
0x1012d53b  mov     pSite, [ebp+pAll]
0x1012d53e  mov     eax, [pSite]
0x1012d540  mov     ebx, [eax+2Ch]
0x1012d543  lea     eax, [ebp+pDisp]
0x1012d546  push    eax
0x1012d547  sub     esp, 10h
0x1012d54a  lea     esi, [ebp+varEmpty]
0x1012d550  mov     edi, esp
0x1012d552  movsd
0x1012d553  movsd
0x1012d554  movsd
0x1012d555  movsd
0x1012d556  sub     esp, 10h
0x1012d559  lea     esi, [ebp+varIndex]
0x1012d55c  mov     edi, esp
0x1012d55e  movsd
0x1012d55f  movsd
0x1012d560  movsd
0x1012d561  movsd
0x1012d562  push    pSite
0x1012d563  mov     pSite, ebx; this
0x1012d565  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d56b  call    ebx
0x1012d56d  test    eax, eax
0x1012d56f  js      loc_1012D8E3
0x1012d575  mov     pSite, [ebp+pDisp]
0x1012d578  test    pSite, pSite
0x1012d57a  jz      loc_1012D6A7
0x1012d580  mov     eax, [pSite]
0x1012d582  mov     esi, [eax]
0x1012d584  lea     eax, [ebp+e]
0x1012d587  push    eax
0x1012d588  push    offset _IID_IHTMLElement
0x1012d58d  push    pSite
0x1012d58e  mov     pSite, esi; this
0x1012d590  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d596  call    esi
0x1012d598  test    eax, eax
0x1012d59a  js      loc_1012D689
0x1012d5a0  mov     pSite, [ebp+e]
0x1012d5a3  mov     eax, [pSite]
0x1012d5a5  mov     esi, [eax+38h]
0x1012d5a8  lea     eax, [ebp+bstrTagName]
0x1012d5ab  push    eax
0x1012d5ac  push    pSite
0x1012d5ad  mov     pSite, esi; this
0x1012d5af  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d5b5  call    esi
0x1012d5b7  test    eax, eax
0x1012d5b9  js      loc_1012D66B
0x1012d5bf  cmp     [ebp+bstrTagName], 0
0x1012d5c3  jz      loc_1012D66B
0x1012d5c9  push    [ebp+bstrTagName]; pbstr
0x1012d5cc  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x1012d5d2  cmp     eax, 4
0x1012d5d5  jnz     loc_1012D65B
0x1012d5db  push    eax; count
0x1012d5dc  mov     edx, offset aBase; "BASE"
0x1012d5e1  mov     pSite, [ebp+bstrTagName]; first
0x1012d5e4  call    ?fastcmpni@@YGHPBG0I@Z; fastcmpni(ushort const *,ushort const *,uint)
0x1012d5e9  test    eax, eax
0x1012d5eb  jnz     short loc_1012D640
0x1012d5ed  mov     pSite, [ebp+e]
0x1012d5f0  mov     eax, [pSite]
0x1012d5f2  mov     esi, [eax+20h]
0x1012d5f5  lea     eax, [ebp+varHref]
0x1012d5f8  push    eax
0x1012d5f9  push    0
0x1012d5fb  push    [ebp+bstrHref]
0x1012d5fe  push    pSite
0x1012d5ff  mov     pSite, esi; this
0x1012d601  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d607  call    esi
0x1012d609  test    eax, eax
0x1012d60b  js      short loc_1012D63B
0x1012d60d  cmp     word ptr [ebp+varHref.___u0], 8
0x1012d612  jnz     short loc_1012D63B
0x1012d614  mov     esi, dword ptr [ebp+varHref.___u0+8]
0x1012d617  test    esi, esi
0x1012d619  jz      short loc_1012D63B
0x1012d61b  push    esi; pbstr
0x1012d61c  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x1012d622  mov     edx, eax; length
0x1012d624  mov     pSite, esi; c
0x1012d626  call    ?newString@String@@SGPAV1@PBGH@Z; String::newString(ushort const *,int)
0x1012d62b  mov     ebx, eax
0x1012d62d  mov     [ebp+relativeURL], ebx
0x1012d630  lea     pSite, [ebp+pResult]; ppref
0x1012d633  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012d638  mov     [ebp+pResult._p], ebx
0x1012d63b  mov     pSite, [ebp+lLength]
0x1012d63e  jmp     short loc_1012D658
0x1012d640  push    4; count
0x1012d642  mov     edx, offset aBody; "BODY"
0x1012d647  mov     pSite, [ebp+bstrTagName]; first
0x1012d64a  call    ?fastcmpni@@YGHPBG0I@Z; fastcmpni(ushort const *,ushort const *,uint)
0x1012d64f  mov     pSite, [ebp+i]
0x1012d652  test    eax, eax
0x1012d654  cmovz   pSite, [ebp+lLength]
0x1012d658  mov     [ebp+i], pSite
0x1012d65b  push    [ebp+bstrTagName]; bstrString
  ... truncated ...
```
