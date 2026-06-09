# COMSafeControlRoot::getBaseURLFromSite(IUnknown *)

- ea: `0x180150db8`
- end: `0x180151521`
- name: `?getBaseURLFromSite@COMSafeControlRoot@@SAPEAVString@@PEAUIUnknown@@@Z`
- size: `1897`
- prototype: `String *__fastcall(IUnknown *pSite)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180151c70`

## callees

- `0x180009490`
- `0x18000d688`
- `0x18000d7d0`
- `0x18003d048`
- `0x1800644e8`
- `0x180084874`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800bc3b0`
- `0x1800bc3e8`
- `0x1800bc400`
- `0x1801501a0`
- `0x180150db8`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015148d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015148d`
- `OLEAUT32!__imp_SysAllocString` at `0x180150e0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180150e0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180151237`
- `OLEAUT32!__imp_SysFreeString` at `0x180151496`
- `OLEAUT32!__imp_SysFreeString` at `0x1801514a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801514ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180151237`
- `OLEAUT32!__imp_SysFreeString` at `0x180151496`
- `OLEAUT32!__imp_SysFreeString` at `0x1801514a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801514ac`
- `OLEAUT32!__imp_SysStringLen` at `0x180151177`
- `OLEAUT32!__imp_SysStringLen` at `0x1801511dc`
- `OLEAUT32!__imp_SysStringLen` at `0x180151177`
- `OLEAUT32!__imp_SysStringLen` at `0x1801511dc`
- `OLEAUT32!__imp_VariantInit` at `0x180150e4c`
- `OLEAUT32!__imp_VariantInit` at `0x18015102e`
- `OLEAUT32!__imp_VariantInit` at `0x18015105e`
- `OLEAUT32!__imp_VariantInit` at `0x180150e4c`
- `OLEAUT32!__imp_VariantInit` at `0x18015102e`
- `OLEAUT32!__imp_VariantInit` at `0x18015105e`
- `OLEAUT32!__imp_VariantClear` at `0x1801514ba`
- `OLEAUT32!__imp_VariantClear` at `0x1801514ba`

## pseudocode

```c
_CodebaseString *__fastcall COMSafeControlRoot::getBaseURLFromSite(IUnknown *pSite)
{
  wchar_t *v2; // r15
  _CodebaseString *p; // rdi
  HRESULT v4; // eax
  wchar_t *v5; // rcx
  HRESULT v6; // eax
  HRESULT v7; // eax
  signed int i; // esi
  IHTMLElementCollection_vtbl *v9; // rax
  HRESULT v10; // eax
  const wchar_t *bstrVal; // rsi
  UINT v12; // eax
  IHTMLDocument2 *pHtmlDoc; // [rsp+38h] [rbp-110h] BYREF
  IHTMLElement *e; // [rsp+40h] [rbp-108h] BYREF
  wchar_t *pDocURL; // [rsp+48h] [rbp-100h] BYREF
  wchar_t *bstrTagName; // [rsp+50h] [rbp-F8h] BYREF
  IServiceProvider *pSP; // [rsp+58h] [rbp-F0h] BYREF
  IDispatch *pDisp; // [rsp+60h] [rbp-E8h] BYREF
  IMoniker *pMk; // [rsp+68h] [rbp-E0h] BYREF
  IBindHost *pBH; // [rsp+70h] [rbp-D8h] BYREF
  IXMLDOMDocument *pXmlDoc; // [rsp+78h] [rbp-D0h] BYREF
  wchar_t *pOleStr; // [rsp+80h] [rbp-C8h] BYREF
  tagVARIANT varIndex; // [rsp+88h] [rbp-C0h] BYREF
  tagVARIANT varHref; // [rsp+A0h] [rbp-A8h] BYREF
  wchar_t *bstrHref; // [rsp+B8h] [rbp-90h]
  tagVARIANT varEmpty; // [rsp+C0h] [rbp-88h] BYREF
  tagVARIANT v28; // [rsp+E0h] [rbp-68h] BYREF
  tagVARIANT v29; // [rsp+100h] [rbp-48h] BYREF
  int lLength; // [rsp+158h] [rbp+10h] BYREF
  _reference<String> pResult; // [rsp+160h] [rbp+18h] BYREF
  IHTMLElementCollection *pAll; // [rsp+168h] [rbp+20h] BYREF

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
  v2 = SysAllocString(L"HREF");
  bstrHref = v2;
  bstrTagName = 0;
  if ( !v2 )
    Exception::throw_E_OUTOFMEMORY();
  memset(&varHref, 0, sizeof(varHref));
  VariantInit(&varHref);
  p = 0;
  pResult._p = 0;
  if ( pSite->QueryInterface(pSite, &IID_IXMLDOMDocument, (void **)&pXmlDoc) >= 0 )
  {
    v4 = pXmlDoc->get_url(pXmlDoc, &pDocURL);
    if ( v4 < 0 )
      Exception::throwHR(v4);
    p = (_CodebaseString *)String::newString(pDocURL);
    release(&pResult._p);
    pResult._p = p;
    goto $Cleanup_21;
  }
  if ( pSite->QueryInterface(pSite, &IID_IServiceProvider, (void **)&pSP) >= 0 )
  {
    if ( pSP->QueryService(pSP, &IID_IBindHost, &IID_IBindHost, (void **)&pBH) >= 0 )
    {
      if ( pBH->CreateMoniker(pBH, (wchar_t *)L".", 0, &pMk, 0) < 0 || pMk->GetDisplayName(pMk, 0, 0, &pOleStr) < 0 )
        goto $Cleanup_21;
      v5 = pOleStr;
LABEL_50:
      p = (_CodebaseString *)String::newString(v5);
      release(&pResult._p);
      pResult._p = p;
      goto $Cleanup_21;
    }
    if ( pSP->QueryService(pSP, (const _GUID *)&SID_SContainerDispatch, &IID_IHTMLDocument2, (void **)&pHtmlDoc) < 0
      && pSP->QueryService(pSP, &IID_IInternetHostSecurityManager, &IID_IHTMLDocument2, (void **)&pHtmlDoc) < 0 )
    {
      goto $Cleanup_21;
    }
  }
  else if ( pSite->QueryInterface(pSite, &IID_IHTMLDocument2, (void **)&pHtmlDoc) < 0 )
  {
    goto $Cleanup_21;
  }
  v6 = pHtmlDoc->get_all(pHtmlDoc, &pAll);
  if ( v6 < 0 )
    Exception::throwHR(v6);
  if ( pAll )
  {
    memset(&varIndex, 0, sizeof(varIndex));
    VariantInit(&varIndex);
    varIndex.vt = 3;
    memset(&varEmpty, 0, sizeof(varEmpty));
    VariantInit(&varEmpty);
    lLength = 0;
    v7 = pAll->get_length(pAll, &lLength);
    if ( v7 < 0 )
      Exception::throwHR(v7);
    for ( i = 0; i < lLength; ++i )
    {
      varIndex.decVal.Lo32 = i;
      v9 = pAll->__vftable;
      v28 = varEmpty;
      v29 = varIndex;
      v10 = ((__int64 (__fastcall *)(IHTMLElementCollection *, tagVARIANT *, tagVARIANT *, IDispatch **))v9->item)(
              pAll,
              &v29,
              &v28,
              &pDisp);
      if ( v10 < 0 )
        Exception::throwHR(v10);
      if ( pDisp )
      {
        if ( pDisp->QueryInterface(pDisp, &IID_IHTMLElement, (void **)&e) >= 0 )
        {
          if ( e->get_tagName(e, &bstrTagName) >= 0 && bstrTagName )
          {
            if ( SysStringLen(bstrTagName) == 4 )
            {
              if ( fastcmpni(bstrTagName, L"BASE", 4u) )
              {
                if ( !fastcmpni(bstrTagName, L"BODY", 4u) )
                  i = lLength;
              }
              else
              {
                if ( e->getAttribute(e, v2, 0, &varHref) >= 0 && varHref.vt == 8 )
                {
                  bstrVal = varHref.bstrVal;
                  if ( varHref.llVal )
                  {
                    v12 = SysStringLen(varHref.bstrVal);
                    p = String::newString(bstrVal, v12);
                    release(&pResult._p);
                    pResult._p = p;
                  }
                }
                i = lLength;
              }
            }
            SysFreeString(bstrTagName);
            bstrTagName = 0;
          }
          if ( e )
          {
            e->Release(e);
            e = 0;
          }
        }
        if ( pDisp )
        {
          pDisp->Release(pDisp);
          pDisp = 0;
        }
      }
    }
    if ( pAll )
    {
      pAll->Release(pAll);
      pAll = 0;
    }
  }
  if ( pHtmlDoc->get_URL(pHtmlDoc, &pDocURL) >= 0 )
  {
    if ( !p )
      goto LABEL_49;
    if ( pDocURL && *pDocURL && !AllowBaseTagUrl(pSite, p->_pwsz, pDocURL) )
    {
      assign(&pResult._p, 0);
      p = (_CodebaseString *)pResult._p;
    }
    if ( !p || (p = (_CodebaseString *)URL::resolveURL(p, pDocURL), release(&pResult._p), (pResult._p = p) == 0) )
    {
LABEL_49:
      v5 = pDocURL;
      goto LABEL_50;
    }
  }
$Cleanup_21:
  if ( pMk )
  {
    pMk->Release(pMk);
    pMk = 0;
  }
  if ( pBH )
  {
    pBH->Release(pBH);
    pBH = 0;
  }
  if ( pSP )
  {
    pSP->Release(pSP);
    pSP = 0;
  }
  if ( pHtmlDoc )
  {
    pHtmlDoc->Release(pHtmlDoc);
    pHtmlDoc = 0;
  }
  if ( pXmlDoc )
  {
    pXmlDoc->Release(pXmlDoc);
    pXmlDoc = 0;
  }
  if ( e )
  {
    e->Release(e);
    e = 0;
  }
  if ( pDisp )
  {
    pDisp->Release(pDisp);
    pDisp = 0;
  }
  if ( pAll )
  {
    pAll->Release(pAll);
    pAll = 0;
  }
  CoTaskMemFree(pOleStr);
  SysFreeString(v2);
  SysFreeString(pDocURL);
  SysFreeString(bstrTagName);
  VariantClear(&varHref);
  pResult._p = 0;
  release(&pResult._p);
  return p;
}

```

## disassembly

```asm
0x180150db8  mov     rax, rsp
0x180150dbb  mov     [rax+8], rbx
0x180150dbf  push    rsi
0x180150dc0  push    rdi
0x180150dc1  push    r12
0x180150dc3  push    r14
0x180150dc5  push    r15
0x180150dc7  sub     rsp, 120h
0x180150dce  mov     r14, pSite
0x180150dd1  xor     ebx, ebx
0x180150dd3  mov     [rsp+148h+pSP], rbx
0x180150dd8  mov     [rsp+148h+pBH], rbx
0x180150ddd  mov     [rsp+148h+pMk], rbx
0x180150de2  mov     [rsp+148h+pHtmlDoc], rbx
0x180150de7  mov     [rsp+148h+pXmlDoc], rbx
0x180150dec  mov     [rax-0C8h], rbx
0x180150df3  mov     [rax+20h], rbx
0x180150df7  mov     [rsp+148h+pDisp], rbx
0x180150dfc  mov     [rsp+148h+e], rbx
0x180150e01  mov     [rsp+148h+pDocURL], rbx
0x180150e06  lea     pSite, aHref; "HREF"
0x180150e0d  call    cs:__imp_SysAllocString
0x180150e13  mov     r15, rax
0x180150e16  mov     [rsp+148h+bstrHref], rax
0x180150e1e  mov     [rsp+148h+bstrTagName], rbx
0x180150e23  test    rax, rax
0x180150e26  jz      loc_1801514F5
0x180150e2c  mov     r12, rbx
0x180150e2f  xorps   xmm0, xmm0
0x180150e32  xor     eax, eax
0x180150e34  movups  xmmword ptr [rsp+148h+varHref.___u0], xmm0
0x180150e3c  mov     [rsp+148h+varHref.pRecInfo], rax
0x180150e44  lea     pSite, [rsp+148h+varHref]; pvarg
0x180150e4c  call    cs:__imp_VariantInit
0x180150e52  mov     rdi, rbx
0x180150e55  mov     [rsp+148h+pResult._p], rbx
0x180150e5d  mov     rax, [r14]
0x180150e60  lea     r8, [rsp+148h+pXmlDoc]
0x180150e65  lea     rdx, IID_IXMLDOMDocument
0x180150e6c  mov     pSite, r14
0x180150e6f  mov     rax, [rax]
0x180150e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150e77  test    eax, eax
0x180150e79  js      short loc_180150EC3
0x180150e7b  mov     pSite, [rsp+148h+pXmlDoc]
0x180150e80  mov     rax, [pSite]
0x180150e83  lea     rdx, [rsp+148h+pDocURL]
0x180150e88  mov     rax, [rax+1E8h]
0x180150e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150e94  test    eax, eax
0x180150e96  js      loc_1801514FB
0x180150e9c  mov     pSite, [rsp+148h+pDocURL]; c
0x180150ea1  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180150ea6  mov     rdi, rax
0x180150ea9  lea     pSite, [rsp+148h+pResult]; ppref
0x180150eb1  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180150eb6  mov     [rsp+148h+pResult._p], rdi
0x180150ebe  jmp     $Cleanup_21
0x180150ec3  mov     rax, [r14]
0x180150ec6  lea     r8, [rsp+148h+pSP]
0x180150ecb  lea     rdx, IID_IServiceProvider
0x180150ed2  mov     pSite, r14
0x180150ed5  mov     rax, [rax]
0x180150ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150edd  test    eax, eax
0x180150edf  jns     short loc_180150F08
0x180150ee1  mov     rax, [r14]
0x180150ee4  lea     r8, [rsp+148h+pHtmlDoc]
0x180150ee9  lea     rdx, IID_IHTMLDocument2
0x180150ef0  mov     pSite, r14
0x180150ef3  mov     rax, [rax]
0x180150ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150efb  test    eax, eax
0x180150efd  jns     $QueryHTMLDoc
0x180150f03  jmp     $Cleanup_21
0x180150f08  mov     pSite, [rsp+148h+pSP]
0x180150f0d  mov     rax, [pSite]
0x180150f10  lea     r9, [rsp+148h+pBH]
0x180150f15  lea     rdx, IID_IBindHost
0x180150f1c  mov     r8, rdx
0x180150f1f  mov     rax, [rax+18h]
0x180150f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150f28  test    eax, eax
0x180150f2a  js      short loc_180150F8E
0x180150f2c  mov     pSite, [rsp+148h+pBH]
0x180150f31  mov     rax, [pSite]
0x180150f34  mov     [rsp+148h+var_128], ebx
0x180150f38  lea     r9, [rsp+148h+pMk]
0x180150f3d  xor     r8d, r8d
0x180150f40  lea     rdx, asc_1801BF9D0; "."
0x180150f47  mov     rax, [rax+18h]
0x180150f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150f50  test    eax, eax
0x180150f52  js      $Cleanup_21
0x180150f58  mov     pSite, [rsp+148h+pMk]
0x180150f5d  mov     rax, [pSite]
0x180150f60  lea     r9, [rsp+148h+pOleStr]
0x180150f68  xor     r8d, r8d
0x180150f6b  xor     edx, edx
0x180150f6d  mov     rax, [rax+0A0h]
0x180150f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150f79  test    eax, eax
0x180150f7b  js      loc_180151352
0x180150f81  mov     pSite, [rsp+148h+pOleStr]
0x180150f89  jmp     loc_180151335
0x180150f8e  mov     pSite, [rsp+148h+pSP]
0x180150f93  mov     rax, [pSite]
0x180150f96  lea     r9, [rsp+148h+pHtmlDoc]
0x180150f9b  lea     r8, IID_IHTMLDocument2
0x180150fa2  lea     rdx, SID_SContainerDispatch
0x180150fa9  mov     rax, [rax+18h]
0x180150fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150fb2  test    eax, eax
0x180150fb4  jns     short $QueryHTMLDoc
0x180150fb6  mov     pSite, [rsp+148h+pSP]
0x180150fbb  mov     rax, [pSite]
0x180150fbe  lea     r9, [rsp+148h+pHtmlDoc]
0x180150fc3  lea     r8, IID_IHTMLDocument2
0x180150fca  lea     rdx, IID_IInternetHostSecurityManager
0x180150fd1  mov     rax, [rax+18h]
0x180150fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150fda  test    eax, eax
0x180150fdc  js      $Cleanup_21
0x180150fe2  mov     pSite, [rsp+148h+pHtmlDoc]
0x180150fe7  mov     rax, [pSite]
0x180150fea  lea     rdx, [rsp+148h+pAll]
0x180150ff2  mov     rax, [rax+40h]
0x180150ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180150ffb  test    eax, eax
0x180150ffd  js      loc_180151502
0x180151003  cmp     [rsp+148h+pAll], rbx
0x18015100b  jz      loc_1801512A4
0x180151011  xorps   xmm0, xmm0
0x180151014  xor     eax, eax
0x180151016  movups  xmmword ptr [rsp+148h+varIndex.___u0], xmm0
0x18015101e  mov     [rsp+148h+varIndex.pRecInfo], rax
0x180151026  lea     pSite, [rsp+148h+varIndex]; pvarg
0x18015102e  call    cs:__imp_VariantInit
0x180151034  mov     eax, 3
0x180151039  mov     word ptr [rsp+148h+varIndex.___u0], ax
0x180151041  xorps   xmm0, xmm0
0x180151044  xor     eax, eax
0x180151046  movups  xmmword ptr [rsp+148h+varEmpty.___u0], xmm0
0x18015104e  mov     [rsp+148h+varEmpty.pRecInfo], rax
0x180151056  lea     pSite, [rsp+148h+varEmpty]; pvarg
0x18015105e  call    cs:__imp_VariantInit
0x180151064  mov     [rsp+148h+lLength], ebx
0x18015106b  mov     pSite, [rsp+148h+pAll]
0x180151073  mov     rax, [pSite]
0x180151076  lea     rdx, [rsp+148h+lLength]
0x18015107e  mov     rax, [rax+48h]
0x180151082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151087  test    eax, eax
0x180151089  js      loc_180151509
0x18015108f  mov     esi, ebx
0x180151091  mov     [rsp+148h+i], ebx
0x180151095  cmp     esi, [rsp+148h+lLength]
0x18015109c  jge     loc_180151283
0x1801510a2  mov     dword ptr [rsp+148h+varIndex.___u0+8], esi
0x1801510a9  mov     pSite, [rsp+148h+pAll]
0x1801510b1  mov     rax, [pSite]
0x1801510b4  movups  xmm0, xmmword ptr [rsp+148h+varEmpty.___u0]
0x1801510bc  movaps  [rsp+148h+var_68], xmm0
0x1801510c4  movsd   xmm1, [rsp+148h+varEmpty.pRecInfo]
0x1801510cd  movsd   [rsp+148h+var_58], xmm1
0x1801510d6  movups  xmm0, xmmword ptr [rsp+148h+varIndex.___u0]
0x1801510de  movaps  [rsp+148h+var_48], xmm0
0x1801510e6  movsd   xmm1, [rsp+148h+varIndex.pRecInfo]
0x1801510ef  movsd   [rsp+148h+var_38], xmm1
0x1801510f8  lea     r9, [rsp+148h+pDisp]
0x1801510fd  lea     r8, [rsp+148h+var_68]
0x180151105  lea     rdx, [rsp+148h+var_48]
0x18015110d  mov     rax, [rax+58h]
0x180151111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151116  test    eax, eax
0x180151118  js      loc_180151510
0x18015111e  mov     pSite, [rsp+148h+pDisp]
0x180151123  test    pSite, pSite
0x180151126  jz      loc_180151278
0x18015112c  mov     rax, [pSite]
0x18015112f  lea     r8, [rsp+148h+e]
0x180151134  lea     rdx, IID_IHTMLElement
0x18015113b  mov     rax, [rax]
0x18015113e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151143  test    eax, eax
0x180151145  js      loc_18015125D
0x18015114b  mov     pSite, [rsp+148h+e]
0x180151150  mov     rax, [pSite]
0x180151153  lea     rdx, [rsp+148h+bstrTagName]
0x180151158  mov     rax, [rax+70h]
0x18015115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151161  test    eax, eax
0x180151163  js      loc_180151242
0x180151169  mov     pSite, [rsp+148h+bstrTagName]; pbstr
0x18015116e  test    pSite, pSite
0x180151171  jz      loc_180151242
0x180151177  call    cs:__imp_SysStringLen
0x18015117d  cmp     eax, 4
0x180151180  jnz     loc_180151232
0x180151186  mov     r8d, eax; count
0x180151189  lea     rdx, aBase; "BASE"
0x180151190  mov     pSite, [rsp+148h+bstrTagName]; first
0x180151195  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x18015119a  test    eax, eax
0x18015119c  jnz     short loc_18015120D
0x18015119e  mov     pSite, [rsp+148h+e]
0x1801511a3  mov     rax, [pSite]
0x1801511a6  lea     r9, [rsp+148h+varHref]
0x1801511ae  xor     r8d, r8d
0x1801511b1  mov     rdx, r15
0x1801511b4  mov     rax, [rax+40h]
0x1801511b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801511bd  test    eax, eax
0x1801511bf  js      short loc_180151204
0x1801511c1  cmp     word ptr [rsp+148h+varHref.___u0], 8
0x1801511ca  jnz     short loc_180151204
0x1801511cc  mov     rsi, qword ptr [rsp+148h+varHref.___u0+8]
0x1801511d4  test    rsi, rsi
0x1801511d7  jz      short loc_180151204
0x1801511d9  mov     pSite, rsi; pbstr
0x1801511dc  call    cs:__imp_SysStringLen
0x1801511e2  mov     edx, eax; length
0x1801511e4  mov     pSite, rsi; c
0x1801511e7  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x1801511ec  mov     rdi, rax
0x1801511ef  lea     pSite, [rsp+148h+pResult]; ppref
0x1801511f7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801511fc  mov     [rsp+148h+pResult._p], rdi
0x180151204  mov     esi, [rsp+148h+lLength]
0x18015120b  jmp     short loc_18015122E
0x18015120d  mov     r8d, 4; count
0x180151213  lea     rdx, aBody; "BODY"
0x18015121a  mov     pSite, [rsp+148h+bstrTagName]; first
0x18015121f  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x180151224  test    eax, eax
0x180151226  cmovz   esi, [rsp+148h+lLength]
0x18015122e  mov     [rsp+148h+i], esi
0x180151232  mov     pSite, [rsp+148h+bstrTagName]; bstrString
0x180151237  call    cs:__imp_SysFreeString
0x18015123d  mov     [rsp+148h+bstrTagName], rbx
0x180151242  mov     pSite, [rsp+148h+e]
0x180151247  test    pSite, pSite
0x18015124a  jz      short loc_18015125D
0x18015124c  mov     rax, [pSite]
0x18015124f  mov     rax, [rax+10h]
0x180151253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151258  mov     [rsp+148h+e], rbx
0x18015125d  mov     pSite, [rsp+148h+pDisp]
0x180151262  test    pSite, pSite
0x180151265  jz      short loc_180151278
0x180151267  mov     rax, [pSite]
0x18015126a  mov     rax, [rax+10h]
0x18015126e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151273  mov     [rsp+148h+pDisp], rbx
0x180151278  inc     esi
0x18015127a  mov     [rsp+148h+i], esi
0x18015127e  jmp     loc_180151095
0x180151283  mov     pSite, [rsp+148h+pAll]
0x18015128b  test    pSite, pSite
0x18015128e  jz      short loc_1801512A4
0x180151290  mov     rax, [pSite]
0x180151293  mov     rax, [rax+10h]
0x180151297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015129c  mov     [rsp+148h+pAll], rbx
0x1801512a4  mov     pSite, [rsp+148h+pHtmlDoc]
0x1801512a9  mov     rax, [pSite]
0x1801512ac  lea     rdx, [rsp+148h+pDocURL]
0x1801512b1  mov     rax, [rax+140h]
0x1801512b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801512bd  test    eax, eax
0x1801512bf  js      $Cleanup_21
0x1801512c5  test    rdi, rdi
0x1801512c8  jz      short loc_180151330
0x1801512ca  mov     r8, [rsp+148h+pDocURL]; pszTargetUrl
0x1801512cf  test    r8, r8
0x1801512d2  jz      short loc_180151301
0x1801512d4  cmp     [r8], bx
0x1801512d8  jz      short loc_180151301
0x1801512da  mov     rdx, [rdi+18h]; pszBaseTagUrl
0x1801512de  mov     pSite, r14; pSite
0x1801512e1  call    ?AllowBaseTagUrl@@YA_NPEAUIUnknown@@PEBG1@Z; AllowBaseTagUrl(IUnknown *,ushort const *,ushort const *)
0x1801512e6  test    al, al
0x1801512e8  jnz     short loc_180151301
0x1801512ea  xor     edx, edx; pref
0x1801512ec  lea     pSite, [rsp+148h+pResult]; ppref
0x1801512f4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801512f9  mov     rdi, [rsp+148h+pResult._p]
0x180151301  test    rdi, rdi
0x180151304  jz      short loc_180151330
0x180151306  mov     rdx, [rsp+148h+pDocURL]; pszbaseURL
0x18015130b  mov     pSite, rdi; relativeURL
0x18015130e  call    ?resolveURL@URL@@SAPEAVString@@PEAV2@PEBG@Z; URL::resolveURL(String *,ushort const *)
0x180151313  mov     rdi, rax
0x180151316  lea     pSite, [rsp+148h+pResult]; ppref
0x18015131e  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180151323  mov     [rsp+148h+pResult._p], rdi
0x18015132b  test    rdi, rdi
0x18015132e  jnz     short loc_180151352
0x180151330  mov     pSite, [rsp+148h+pDocURL]; c
0x180151335  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
  ... truncated ...
```
