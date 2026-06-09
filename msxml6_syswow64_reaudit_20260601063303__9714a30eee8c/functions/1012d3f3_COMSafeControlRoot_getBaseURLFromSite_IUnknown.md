# COMSafeControlRoot::getBaseURLFromSite(IUnknown *)

- ea: `0x1012d3f3`
- end: `0x1012da08`
- name: `?getBaseURLFromSite@COMSafeControlRoot@@SGPAVString@@PAUIUnknown@@@Z`
- size: `1557`
- prototype: `String *__thiscall(IUnknown *pSite)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1012e030`

## callees

- `0x1003fb13`
- `0x1003fd72`
- `0x10040b56`
- `0x10040bb4`
- `0x10064c51`
- `0x10064c84`
- `0x10064d6d`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100787a5`
- `0x1012c8a0`
- `0x1012d3f3`
- `0x10131736`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012d99f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012d99f`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1012d42a`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1012d42a`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d76e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d9a8`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d9b1`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d9ba`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d76e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d9a8`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d9b1`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012d9ba`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d6dc`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d72c`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d6dc`
- `OLEAUT32!__imp__SysStringLen@4` at `0x1012d72c`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d445`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d5fe`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d612`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d445`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d5fe`
- `OLEAUT32!__imp__VariantInit@4` at `0x1012d612`
- `OLEAUT32!__imp__VariantClear@4` at `0x1012d9c4`
- `OLEAUT32!__imp__VariantClear@4` at `0x1012d9c4`

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
  String *v10; // ebx
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
    JUMPOUT(0x1012DA01);
  }
  pResult._p = 0;
  release(&pResult._p);
  return v4;
}

```

## disassembly

```asm
0x1012d3f3  push    80h
0x1012d3f8  push    offset stru_1017C958
0x1012d3fd  call    __SEH_prolog4
0x1012d402  mov     [ebp+var_58], pSite
0x1012d405  xor     ebx, ebx
0x1012d407  mov     [ebp+pSP], ebx
0x1012d40a  mov     [ebp+pBH], ebx
0x1012d40d  mov     [ebp+pMk], ebx
0x1012d410  mov     [ebp+pHtmlDoc], ebx
0x1012d413  mov     [ebp+pXmlDoc], ebx
0x1012d416  mov     [ebp+pOleStr], ebx
0x1012d419  mov     [ebp+pAll], ebx
0x1012d41c  mov     [ebp+pDisp], ebx
0x1012d41f  mov     [ebp+e], ebx
0x1012d422  mov     [ebp+pDocURL], ebx
0x1012d425  push    offset aHref_0; "HREF"
0x1012d42a  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1012d430  mov     [ebp+bstrHref], eax
0x1012d433  mov     [ebp+bstrTagName], ebx
0x1012d436  mov     [ebp+var_60], ebx
0x1012d439  test    eax, eax
0x1012d43b  jz      loc_1012D9EE
0x1012d441  lea     eax, [ebp+varHref]
0x1012d444  push    eax; pvarg
0x1012d445  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1012d44b  mov     edi, ebx
0x1012d44d  mov     [ebp+relativeURL], edi
0x1012d450  mov     [ebp+pResult._p], edi
0x1012d453  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1012d456  mov     edi, [ebp+var_58]
0x1012d459  mov     eax, [edi]
0x1012d45b  mov     esi, [eax]
0x1012d45d  lea     eax, [ebp+pXmlDoc]
0x1012d460  push    eax
0x1012d461  push    offset _IID_IXMLDOMDocument
0x1012d466  push    edi
0x1012d467  mov     pSite, esi; this
0x1012d469  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d46f  call    esi
0x1012d471  test    eax, eax
0x1012d473  js      short loc_1012D4BA
0x1012d475  mov     pSite, [ebp+pXmlDoc]
0x1012d478  mov     eax, [pSite]
0x1012d47a  mov     esi, [eax+0F4h]
0x1012d480  lea     eax, [ebp+pDocURL]
0x1012d483  push    eax
0x1012d484  push    pSite
0x1012d485  mov     pSite, esi; this
0x1012d487  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d48d  call    esi
0x1012d48f  test    eax, eax
0x1012d491  js      loc_1012D9F3
0x1012d497  mov     pSite, [ebp+pDocURL]; c
0x1012d49a  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1012d49f  mov     esi, eax
0x1012d4a1  lea     pSite, [ebp+pResult]; ppref
0x1012d4a4  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012d4a9  mov     [ebp+pResult._p], esi
0x1012d4ac  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012d4b3  mov     edi, esi
0x1012d4b5  jmp     Cleanup_21
0x1012d4ba  mov     eax, [edi]
0x1012d4bc  mov     esi, [eax]
0x1012d4be  lea     eax, [ebp+pSP]
0x1012d4c1  push    eax
0x1012d4c2  push    offset _IID_IServiceProvider
0x1012d4c7  push    edi
0x1012d4c8  mov     pSite, esi; this
0x1012d4ca  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d4d0  call    esi
0x1012d4d2  test    eax, eax
0x1012d4d4  jns     short loc_1012D505
0x1012d4d6  mov     eax, [edi]
0x1012d4d8  mov     esi, [eax]
0x1012d4da  lea     eax, [ebp+pHtmlDoc]
0x1012d4dd  push    eax
0x1012d4de  push    offset _IID_IHTMLDocument2
0x1012d4e3  push    edi
0x1012d4e4  mov     pSite, esi; this
0x1012d4e6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d4ec  call    esi
0x1012d4ee  test    eax, eax
0x1012d4f0  jns     QueryHTMLDoc
0x1012d4f6  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012d4fd  mov     edi, [ebp+relativeURL]
0x1012d500  jmp     Cleanup_21
0x1012d505  mov     pSite, [ebp+pSP]
0x1012d508  mov     eax, [pSite]
0x1012d50a  mov     esi, [eax+0Ch]
0x1012d50d  lea     eax, [ebp+pBH]
0x1012d510  push    eax
0x1012d511  mov     eax, offset _IID_IBindHost
0x1012d516  push    eax
0x1012d517  push    eax
0x1012d518  push    pSite
0x1012d519  mov     pSite, esi; this
0x1012d51b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d521  call    esi
0x1012d523  test    eax, eax
0x1012d525  js      short loc_1012D586
0x1012d527  mov     pSite, [ebp+pBH]
0x1012d52a  mov     eax, [pSite]
0x1012d52c  mov     esi, [eax+0Ch]
0x1012d52f  push    ebx
0x1012d530  lea     eax, [ebp+pMk]
0x1012d533  push    eax
0x1012d534  push    ebx
0x1012d535  push    offset asc_100351B8; "."
0x1012d53a  push    pSite
0x1012d53b  mov     pSite, esi; this
0x1012d53d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d543  call    esi
0x1012d545  test    eax, eax
0x1012d547  js      short loc_1012D4F6
0x1012d549  mov     pSite, [ebp+pMk]
0x1012d54c  mov     eax, [pSite]
0x1012d54e  mov     esi, [eax+50h]
0x1012d551  lea     eax, [ebp+pOleStr]
0x1012d554  push    eax
0x1012d555  push    ebx
0x1012d556  push    ebx
0x1012d557  push    pSite
0x1012d558  mov     pSite, esi; this
0x1012d55a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d560  call    esi
0x1012d562  test    eax, eax
0x1012d564  js      loc_1012D873
0x1012d56a  mov     pSite, [ebp+pOleStr]; c
0x1012d56d  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1012d572  mov     esi, eax
0x1012d574  lea     pSite, [ebp+pResult]; ppref
0x1012d577  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012d57c  mov     [ebp+pResult._p], esi
0x1012d57f  mov     edi, esi
0x1012d581  jmp     loc_1012D876
0x1012d586  mov     pSite, [ebp+pSP]
0x1012d589  mov     eax, [pSite]
0x1012d58b  mov     esi, [eax+0Ch]
0x1012d58e  lea     eax, [ebp+pHtmlDoc]
0x1012d591  push    eax
0x1012d592  push    offset _IID_IHTMLDocument2
0x1012d597  push    offset _SID_SContainerDispatch
0x1012d59c  push    pSite
0x1012d59d  mov     pSite, esi; this
0x1012d59f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d5a5  call    esi
0x1012d5a7  test    eax, eax
0x1012d5a9  jns     short QueryHTMLDoc
0x1012d5ab  mov     pSite, [ebp+pSP]
0x1012d5ae  mov     eax, [pSite]
0x1012d5b0  mov     esi, [eax+0Ch]
0x1012d5b3  lea     eax, [ebp+pHtmlDoc]
0x1012d5b6  push    eax
0x1012d5b7  push    offset _IID_IHTMLDocument2
0x1012d5bc  push    offset _IID_IInternetHostSecurityManager
0x1012d5c1  push    pSite
0x1012d5c2  mov     pSite, esi; this
0x1012d5c4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d5ca  call    esi
0x1012d5cc  jmp     loc_1012D4EE
0x1012d5d1  mov     pSite, [ebp+pHtmlDoc]
0x1012d5d4  mov     eax, [pSite]
0x1012d5d6  mov     esi, [eax+20h]
0x1012d5d9  lea     eax, [ebp+pAll]
0x1012d5dc  push    eax
0x1012d5dd  push    pSite
0x1012d5de  mov     pSite, esi; this
0x1012d5e0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d5e6  call    esi
0x1012d5e8  test    eax, eax
0x1012d5ea  js      loc_1012D9F3
0x1012d5f0  cmp     [ebp+pAll], 0
0x1012d5f4  jz      loc_1012D7E6
0x1012d5fa  lea     eax, [ebp+varIndex]
0x1012d5fd  push    eax; pvarg
0x1012d5fe  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1012d604  push    3
0x1012d606  pop     eax
0x1012d607  mov     word ptr [ebp+varIndex.___u0], ax
0x1012d60b  lea     eax, [ebp+varEmpty]
0x1012d611  push    eax; pvarg
0x1012d612  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1012d618  mov     [ebp+lLength], ebx
0x1012d61b  mov     pSite, [ebp+pAll]
0x1012d61e  mov     eax, [pSite]
0x1012d620  mov     esi, [eax+24h]
0x1012d623  lea     eax, [ebp+lLength]
0x1012d626  push    eax
0x1012d627  push    pSite
0x1012d628  mov     pSite, esi; this
0x1012d62a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d630  call    esi
0x1012d632  test    eax, eax
0x1012d634  js      loc_1012D9F3
0x1012d63a  mov     eax, ebx
0x1012d63c  mov     [ebp+i], ebx
0x1012d63f  cmp     eax, [ebp+lLength]
0x1012d642  jge     loc_1012D7C3
0x1012d648  mov     dword ptr [ebp+varIndex.___u0+8], eax
0x1012d64b  mov     pSite, [ebp+pAll]
0x1012d64e  mov     eax, [pSite]
0x1012d650  mov     ebx, [eax+2Ch]
0x1012d653  lea     eax, [ebp+pDisp]
0x1012d656  push    eax
0x1012d657  sub     esp, 10h
0x1012d65a  lea     esi, [ebp+varEmpty]
0x1012d660  mov     edi, esp
0x1012d662  movsd
0x1012d663  movsd
0x1012d664  movsd
0x1012d665  movsd
0x1012d666  sub     esp, 10h
0x1012d669  lea     esi, [ebp+varIndex]
0x1012d66c  mov     edi, esp
0x1012d66e  movsd
0x1012d66f  movsd
0x1012d670  movsd
0x1012d671  movsd
0x1012d672  push    pSite
0x1012d673  mov     pSite, ebx; this
0x1012d675  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d67b  call    ebx
0x1012d67d  test    eax, eax
0x1012d67f  js      loc_1012D9F3
0x1012d685  mov     pSite, [ebp+pDisp]
0x1012d688  test    pSite, pSite
0x1012d68a  jz      loc_1012D7B7
0x1012d690  mov     eax, [pSite]
0x1012d692  mov     esi, [eax]
0x1012d694  lea     eax, [ebp+e]
0x1012d697  push    eax
0x1012d698  push    offset _IID_IHTMLElement
0x1012d69d  push    pSite
0x1012d69e  mov     pSite, esi; this
0x1012d6a0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d6a6  call    esi
0x1012d6a8  test    eax, eax
0x1012d6aa  js      loc_1012D799
0x1012d6b0  mov     pSite, [ebp+e]
0x1012d6b3  mov     eax, [pSite]
0x1012d6b5  mov     esi, [eax+38h]
0x1012d6b8  lea     eax, [ebp+bstrTagName]
0x1012d6bb  push    eax
0x1012d6bc  push    pSite
0x1012d6bd  mov     pSite, esi; this
0x1012d6bf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d6c5  call    esi
0x1012d6c7  test    eax, eax
0x1012d6c9  js      loc_1012D77B
0x1012d6cf  cmp     [ebp+bstrTagName], 0
0x1012d6d3  jz      loc_1012D77B
0x1012d6d9  push    [ebp+bstrTagName]; pbstr
0x1012d6dc  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x1012d6e2  cmp     eax, 4
0x1012d6e5  jnz     loc_1012D76B
0x1012d6eb  push    eax; count
0x1012d6ec  mov     edx, offset aBase; "BASE"
0x1012d6f1  mov     pSite, [ebp+bstrTagName]; first
0x1012d6f4  call    ?fastcmpni@@YGHPBG0I@Z; fastcmpni(ushort const *,ushort const *,uint)
0x1012d6f9  test    eax, eax
0x1012d6fb  jnz     short loc_1012D750
0x1012d6fd  mov     pSite, [ebp+e]
0x1012d700  mov     eax, [pSite]
0x1012d702  mov     esi, [eax+20h]
0x1012d705  lea     eax, [ebp+varHref]
0x1012d708  push    eax
0x1012d709  push    0
0x1012d70b  push    [ebp+bstrHref]
0x1012d70e  push    pSite
0x1012d70f  mov     pSite, esi; this
0x1012d711  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d717  call    esi
0x1012d719  test    eax, eax
0x1012d71b  js      short loc_1012D74B
0x1012d71d  cmp     word ptr [ebp+varHref.___u0], 8
0x1012d722  jnz     short loc_1012D74B
0x1012d724  mov     esi, dword ptr [ebp+varHref.___u0+8]
0x1012d727  test    esi, esi
0x1012d729  jz      short loc_1012D74B
0x1012d72b  push    esi; pbstr
0x1012d72c  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x1012d732  mov     edx, eax; length
0x1012d734  mov     pSite, esi; c
0x1012d736  call    ?newString@String@@SGPAV1@PBGH@Z; String::newString(ushort const *,int)
0x1012d73b  mov     ebx, eax
0x1012d73d  mov     [ebp+relativeURL], ebx
0x1012d740  lea     pSite, [ebp+pResult]; ppref
0x1012d743  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012d748  mov     [ebp+pResult._p], ebx
0x1012d74b  mov     pSite, [ebp+lLength]
0x1012d74e  jmp     short loc_1012D768
0x1012d750  push    4; count
0x1012d752  mov     edx, offset aBody; "BODY"
0x1012d757  mov     pSite, [ebp+bstrTagName]; first
0x1012d75a  call    ?fastcmpni@@YGHPBG0I@Z; fastcmpni(ushort const *,ushort const *,uint)
0x1012d75f  mov     pSite, [ebp+i]
0x1012d762  test    eax, eax
0x1012d764  cmovz   pSite, [ebp+lLength]
0x1012d768  mov     [ebp+i], pSite
0x1012d76b  push    [ebp+bstrTagName]; bstrString
  ... truncated ...
```
