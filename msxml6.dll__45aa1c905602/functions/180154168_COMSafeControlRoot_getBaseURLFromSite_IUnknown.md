# COMSafeControlRoot::getBaseURLFromSite(IUnknown *)

- ea: `0x180154168`
- end: `0x18015491a`
- name: `?getBaseURLFromSite@COMSafeControlRoot@@SAPEAVString@@PEAUIUnknown@@@Z`
- size: `1970`
- prototype: `String *__fastcall(IUnknown *pSite)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180155080`

## callees

- `0x180015a80`
- `0x180019cd0`
- `0x180019e20`
- `0x180030768`
- `0x18006acec`
- `0x180083ee4`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800bda08`
- `0x1800bda40`
- `0x1800bda58`
- `0x180153540`
- `0x180154168`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154867`
- `OLEAUT32!__imp_SysAllocString` at `0x1801541bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1801541bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18015460b`
- `OLEAUT32!__imp_SysFreeString` at `0x180154876`
- `OLEAUT32!__imp_SysFreeString` at `0x180154887`
- `OLEAUT32!__imp_SysFreeString` at `0x180154898`
- `OLEAUT32!__imp_SysFreeString` at `0x18015460b`
- `OLEAUT32!__imp_SysFreeString` at `0x180154876`
- `OLEAUT32!__imp_SysFreeString` at `0x180154887`
- `OLEAUT32!__imp_SysFreeString` at `0x180154898`
- `OLEAUT32!__imp_SysStringLen` at `0x18015453f`
- `OLEAUT32!__imp_SysStringLen` at `0x1801545aa`
- `OLEAUT32!__imp_SysStringLen` at `0x18015453f`
- `OLEAUT32!__imp_SysStringLen` at `0x1801545aa`
- `OLEAUT32!__imp_VariantInit` at `0x180154202`
- `OLEAUT32!__imp_VariantInit` at `0x1801543ea`
- `OLEAUT32!__imp_VariantInit` at `0x180154420`
- `OLEAUT32!__imp_VariantInit` at `0x180154202`
- `OLEAUT32!__imp_VariantInit` at `0x1801543ea`
- `OLEAUT32!__imp_VariantInit` at `0x180154420`
- `OLEAUT32!__imp_VariantClear` at `0x1801548ac`
- `OLEAUT32!__imp_VariantClear` at `0x1801548ac`

## pseudocode

```c
String *__fastcall COMSafeControlRoot::getBaseURLFromSite(IUnknown *pSite)
{
  wchar_t *v2; // r15
  String *p; // rdi
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
    p = String::newString(pDocURL);
    release(&pResult._p);
    pResult._p = p;
    goto $Cleanup_22;
  }
  if ( pSite->QueryInterface(pSite, &IID_IServiceProvider, (void **)&pSP) >= 0 )
  {
    if ( pSP->QueryService(pSP, &IID_IBindHost, &IID_IBindHost, (void **)&pBH) >= 0 )
    {
      if ( pBH->CreateMoniker(pBH, (wchar_t *)L".", 0, &pMk, 0) < 0 || pMk->GetDisplayName(pMk, 0, 0, &pOleStr) < 0 )
        goto $Cleanup_22;
      v5 = pOleStr;
LABEL_50:
      p = String::newString(v5);
      release(&pResult._p);
      pResult._p = p;
      goto $Cleanup_22;
    }
    if ( pSP->QueryService(pSP, (const _GUID *)&SID_SContainerDispatch, &IID_IHTMLDocument2, (void **)&pHtmlDoc) < 0
      && pSP->QueryService(pSP, &IID_IInternetHostSecurityManager, &IID_IHTMLDocument2, (void **)&pHtmlDoc) < 0 )
    {
      goto $Cleanup_22;
    }
  }
  else if ( pSite->QueryInterface(pSite, &IID_IHTMLDocument2, (void **)&pHtmlDoc) < 0 )
  {
    goto $Cleanup_22;
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
      p = pResult._p;
    }
    if ( !p || (p = URL::resolveURL(p, pDocURL), release(&pResult._p), (pResult._p = p) == 0) )
    {
LABEL_49:
      v5 = pDocURL;
      goto LABEL_50;
    }
  }
$Cleanup_22:
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
0x180154168  mov     rax, rsp
0x18015416b  mov     [rax+8], rbx
0x18015416f  push    rsi
0x180154170  push    rdi
0x180154171  push    r12
0x180154173  push    r14
0x180154175  push    r15
0x180154177  sub     rsp, 120h
0x18015417e  mov     r14, pSite
0x180154181  xor     ebx, ebx
0x180154183  mov     [rsp+148h+pSP], rbx
0x180154188  mov     [rsp+148h+pBH], rbx
0x18015418d  mov     [rsp+148h+pMk], rbx
0x180154192  mov     [rsp+148h+pHtmlDoc], rbx
0x180154197  mov     [rsp+148h+pXmlDoc], rbx
0x18015419c  mov     [rax-0C8h], rbx
0x1801541a3  mov     [rax+20h], rbx
0x1801541a7  mov     [rsp+148h+pDisp], rbx
0x1801541ac  mov     [rsp+148h+e], rbx
0x1801541b1  mov     [rsp+148h+pDocURL], rbx
0x1801541b6  lea     pSite, aHref; "HREF"
0x1801541bd  call    cs:__imp_SysAllocString
0x1801541c4  nop     dword ptr [rax+rax+00h]
0x1801541c9  mov     r15, rax
0x1801541cc  mov     [rsp+148h+bstrHref], rax
0x1801541d4  mov     [rsp+148h+bstrTagName], rbx
0x1801541d9  test    rax, rax
0x1801541dc  jz      loc_1801548EE
0x1801541e2  mov     r12, rbx
0x1801541e5  xorps   xmm0, xmm0
0x1801541e8  xor     eax, eax
0x1801541ea  movups  xmmword ptr [rsp+148h+varHref.___u0], xmm0
0x1801541f2  mov     [rsp+148h+varHref.pRecInfo], rax
0x1801541fa  lea     pSite, [rsp+148h+varHref]; pvarg
0x180154202  call    cs:__imp_VariantInit
0x180154209  nop     dword ptr [rax+rax+00h]
0x18015420e  mov     rdi, rbx
0x180154211  mov     [rsp+148h+pResult._p], rbx
0x180154219  mov     rax, [r14]
0x18015421c  lea     r8, [rsp+148h+pXmlDoc]
0x180154221  lea     rdx, IID_IXMLDOMDocument
0x180154228  mov     pSite, r14
0x18015422b  mov     rax, [rax]
0x18015422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154233  test    eax, eax
0x180154235  js      short loc_18015427F
0x180154237  mov     pSite, [rsp+148h+pXmlDoc]
0x18015423c  mov     rax, [pSite]
0x18015423f  lea     rdx, [rsp+148h+pDocURL]
0x180154244  mov     rax, [rax+1E8h]
0x18015424b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154250  test    eax, eax
0x180154252  js      loc_1801548F4
0x180154258  mov     pSite, [rsp+148h+pDocURL]; c
0x18015425d  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180154262  mov     rdi, rax
0x180154265  lea     pSite, [rsp+148h+pResult]; ppref
0x18015426d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154272  mov     [rsp+148h+pResult._p], rdi
0x18015427a  jmp     $Cleanup_22
0x18015427f  mov     rax, [r14]
0x180154282  lea     r8, [rsp+148h+pSP]
0x180154287  lea     rdx, IID_IServiceProvider
0x18015428e  mov     pSite, r14
0x180154291  mov     rax, [rax]
0x180154294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154299  test    eax, eax
0x18015429b  jns     short loc_1801542C4
0x18015429d  mov     rax, [r14]
0x1801542a0  lea     r8, [rsp+148h+pHtmlDoc]
0x1801542a5  lea     rdx, IID_IHTMLDocument2
0x1801542ac  mov     pSite, r14
0x1801542af  mov     rax, [rax]
0x1801542b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801542b7  test    eax, eax
0x1801542b9  jns     $QueryHTMLDoc
0x1801542bf  jmp     $Cleanup_22
0x1801542c4  mov     pSite, [rsp+148h+pSP]
0x1801542c9  mov     rax, [pSite]
0x1801542cc  lea     r9, [rsp+148h+pBH]
0x1801542d1  lea     rdx, IID_IBindHost
0x1801542d8  mov     r8, rdx
0x1801542db  mov     rax, [rax+18h]
0x1801542df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801542e4  test    eax, eax
0x1801542e6  js      short loc_18015434A
0x1801542e8  mov     pSite, [rsp+148h+pBH]
0x1801542ed  mov     rax, [pSite]
0x1801542f0  mov     [rsp+148h+var_128], ebx
0x1801542f4  lea     r9, [rsp+148h+pMk]
0x1801542f9  xor     r8d, r8d
0x1801542fc  lea     rdx, asc_1801BF2F8; "."
0x180154303  mov     rax, [rax+18h]
0x180154307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015430c  test    eax, eax
0x18015430e  js      $Cleanup_22
0x180154314  mov     pSite, [rsp+148h+pMk]
0x180154319  mov     rax, [pSite]
0x18015431c  lea     r9, [rsp+148h+pOleStr]
0x180154324  xor     r8d, r8d
0x180154327  xor     edx, edx
0x180154329  mov     rax, [rax+0A0h]
0x180154330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154335  test    eax, eax
0x180154337  js      loc_18015472C
0x18015433d  mov     pSite, [rsp+148h+pOleStr]
0x180154345  jmp     loc_18015470F
0x18015434a  mov     pSite, [rsp+148h+pSP]
0x18015434f  mov     rax, [pSite]
0x180154352  lea     r9, [rsp+148h+pHtmlDoc]
0x180154357  lea     r8, IID_IHTMLDocument2
0x18015435e  lea     rdx, SID_SContainerDispatch
0x180154365  mov     rax, [rax+18h]
0x180154369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015436e  test    eax, eax
0x180154370  jns     short $QueryHTMLDoc
0x180154372  mov     pSite, [rsp+148h+pSP]
0x180154377  mov     rax, [pSite]
0x18015437a  lea     r9, [rsp+148h+pHtmlDoc]
0x18015437f  lea     r8, IID_IHTMLDocument2
0x180154386  lea     rdx, IID_IInternetHostSecurityManager
0x18015438d  mov     rax, [rax+18h]
0x180154391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154396  test    eax, eax
0x180154398  js      $Cleanup_22
0x18015439e  mov     pSite, [rsp+148h+pHtmlDoc]
0x1801543a3  mov     rax, [pSite]
0x1801543a6  lea     rdx, [rsp+148h+pAll]
0x1801543ae  mov     rax, [rax+40h]
0x1801543b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801543b7  test    eax, eax
0x1801543b9  js      loc_1801548FB
0x1801543bf  cmp     [rsp+148h+pAll], rbx
0x1801543c7  jz      loc_18015467E
0x1801543cd  xorps   xmm0, xmm0
0x1801543d0  xor     eax, eax
0x1801543d2  movups  xmmword ptr [rsp+148h+varIndex.___u0], xmm0
0x1801543da  mov     [rsp+148h+varIndex.pRecInfo], rax
0x1801543e2  lea     pSite, [rsp+148h+varIndex]; pvarg
0x1801543ea  call    cs:__imp_VariantInit
0x1801543f1  nop     dword ptr [rax+rax+00h]
0x1801543f6  mov     eax, 3
0x1801543fb  mov     word ptr [rsp+148h+varIndex.___u0], ax
0x180154403  xorps   xmm0, xmm0
0x180154406  xor     eax, eax
0x180154408  movups  xmmword ptr [rsp+148h+varEmpty.___u0], xmm0
0x180154410  mov     [rsp+148h+varEmpty.pRecInfo], rax
0x180154418  lea     pSite, [rsp+148h+varEmpty]; pvarg
0x180154420  call    cs:__imp_VariantInit
0x180154427  nop     dword ptr [rax+rax+00h]
0x18015442c  mov     [rsp+148h+lLength], ebx
0x180154433  mov     pSite, [rsp+148h+pAll]
0x18015443b  mov     rax, [pSite]
0x18015443e  lea     rdx, [rsp+148h+lLength]
0x180154446  mov     rax, [rax+48h]
0x18015444a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015444f  test    eax, eax
0x180154451  js      loc_180154902
0x180154457  mov     esi, ebx
0x180154459  mov     [rsp+148h+i], ebx
0x18015445d  cmp     esi, [rsp+148h+lLength]
0x180154464  jge     loc_18015465D
0x18015446a  mov     dword ptr [rsp+148h+varIndex.___u0+8], esi
0x180154471  mov     pSite, [rsp+148h+pAll]
0x180154479  mov     rax, [pSite]
0x18015447c  movups  xmm0, xmmword ptr [rsp+148h+varEmpty.___u0]
0x180154484  movaps  [rsp+148h+var_68], xmm0
0x18015448c  movsd   xmm1, [rsp+148h+varEmpty.pRecInfo]
0x180154495  movsd   [rsp+148h+var_58], xmm1
0x18015449e  movups  xmm0, xmmword ptr [rsp+148h+varIndex.___u0]
0x1801544a6  movaps  [rsp+148h+var_48], xmm0
0x1801544ae  movsd   xmm1, [rsp+148h+varIndex.pRecInfo]
0x1801544b7  movsd   [rsp+148h+var_38], xmm1
0x1801544c0  lea     r9, [rsp+148h+pDisp]
0x1801544c5  lea     r8, [rsp+148h+var_68]
0x1801544cd  lea     rdx, [rsp+148h+var_48]
0x1801544d5  mov     rax, [rax+58h]
0x1801544d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801544de  test    eax, eax
0x1801544e0  js      loc_180154909
0x1801544e6  mov     pSite, [rsp+148h+pDisp]
0x1801544eb  test    pSite, pSite
0x1801544ee  jz      loc_180154652
0x1801544f4  mov     rax, [pSite]
0x1801544f7  lea     r8, [rsp+148h+e]
0x1801544fc  lea     rdx, IID_IHTMLElement
0x180154503  mov     rax, [rax]
0x180154506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015450b  test    eax, eax
0x18015450d  js      loc_180154637
0x180154513  mov     pSite, [rsp+148h+e]
0x180154518  mov     rax, [pSite]
0x18015451b  lea     rdx, [rsp+148h+bstrTagName]
0x180154520  mov     rax, [rax+70h]
0x180154524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154529  test    eax, eax
0x18015452b  js      loc_18015461C
0x180154531  mov     pSite, [rsp+148h+bstrTagName]; pbstr
0x180154536  test    pSite, pSite
0x180154539  jz      loc_18015461C
0x18015453f  call    cs:__imp_SysStringLen
0x180154546  nop     dword ptr [rax+rax+00h]
0x18015454b  cmp     eax, 4
0x18015454e  jnz     loc_180154606
0x180154554  mov     r8d, eax; count
0x180154557  lea     rdx, aBase; "BASE"
0x18015455e  mov     pSite, [rsp+148h+bstrTagName]; first
0x180154563  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x180154568  test    eax, eax
0x18015456a  jnz     short loc_1801545E1
0x18015456c  mov     pSite, [rsp+148h+e]
0x180154571  mov     rax, [pSite]
0x180154574  lea     r9, [rsp+148h+varHref]
0x18015457c  xor     r8d, r8d
0x18015457f  mov     rdx, r15
0x180154582  mov     rax, [rax+40h]
0x180154586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015458b  test    eax, eax
0x18015458d  js      short loc_1801545D8
0x18015458f  cmp     word ptr [rsp+148h+varHref.___u0], 8
0x180154598  jnz     short loc_1801545D8
0x18015459a  mov     rsi, qword ptr [rsp+148h+varHref.___u0+8]
0x1801545a2  test    rsi, rsi
0x1801545a5  jz      short loc_1801545D8
0x1801545a7  mov     pSite, rsi; pbstr
0x1801545aa  call    cs:__imp_SysStringLen
0x1801545b1  nop     dword ptr [rax+rax+00h]
0x1801545b6  mov     edx, eax; length
0x1801545b8  mov     pSite, rsi; c
0x1801545bb  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x1801545c0  mov     rdi, rax
0x1801545c3  lea     pSite, [rsp+148h+pResult]; ppref
0x1801545cb  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801545d0  mov     [rsp+148h+pResult._p], rdi
0x1801545d8  mov     esi, [rsp+148h+lLength]
0x1801545df  jmp     short loc_180154602
0x1801545e1  mov     r8d, 4; count
0x1801545e7  lea     rdx, aBody; "BODY"
0x1801545ee  mov     pSite, [rsp+148h+bstrTagName]; first
0x1801545f3  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x1801545f8  test    eax, eax
0x1801545fa  cmovz   esi, [rsp+148h+lLength]
0x180154602  mov     [rsp+148h+i], esi
0x180154606  mov     pSite, [rsp+148h+bstrTagName]; bstrString
0x18015460b  call    cs:__imp_SysFreeString
0x180154612  nop     dword ptr [rax+rax+00h]
0x180154617  mov     [rsp+148h+bstrTagName], rbx
0x18015461c  mov     pSite, [rsp+148h+e]
0x180154621  test    pSite, pSite
0x180154624  jz      short loc_180154637
0x180154626  mov     rax, [pSite]
0x180154629  mov     rax, [rax+10h]
0x18015462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154632  mov     [rsp+148h+e], rbx
0x180154637  mov     pSite, [rsp+148h+pDisp]
0x18015463c  test    pSite, pSite
0x18015463f  jz      short loc_180154652
0x180154641  mov     rax, [pSite]
0x180154644  mov     rax, [rax+10h]
0x180154648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015464d  mov     [rsp+148h+pDisp], rbx
0x180154652  inc     esi
0x180154654  mov     [rsp+148h+i], esi
0x180154658  jmp     loc_18015445D
0x18015465d  mov     pSite, [rsp+148h+pAll]
0x180154665  test    pSite, pSite
0x180154668  jz      short loc_18015467E
0x18015466a  mov     rax, [pSite]
0x18015466d  mov     rax, [rax+10h]
0x180154671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154676  mov     [rsp+148h+pAll], rbx
0x18015467e  mov     pSite, [rsp+148h+pHtmlDoc]
0x180154683  mov     rax, [pSite]
0x180154686  lea     rdx, [rsp+148h+pDocURL]
0x18015468b  mov     rax, [rax+140h]
0x180154692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154697  test    eax, eax
0x180154699  js      $Cleanup_22
0x18015469f  test    rdi, rdi
0x1801546a2  jz      short loc_18015470A
0x1801546a4  mov     r8, [rsp+148h+pDocURL]; pszTargetUrl
0x1801546a9  test    r8, r8
0x1801546ac  jz      short loc_1801546DB
0x1801546ae  cmp     [r8], bx
0x1801546b2  jz      short loc_1801546DB
0x1801546b4  mov     rdx, [rdi+18h]; pszBaseTagUrl
0x1801546b8  mov     pSite, r14; pSite
0x1801546bb  call    ?AllowBaseTagUrl@@YA_NPEAUIUnknown@@PEBG1@Z; AllowBaseTagUrl(IUnknown *,ushort const *,ushort const *)
0x1801546c0  test    al, al
0x1801546c2  jnz     short loc_1801546DB
0x1801546c4  xor     edx, edx; pref
0x1801546c6  lea     pSite, [rsp+148h+pResult]; ppref
0x1801546ce  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801546d3  mov     rdi, [rsp+148h+pResult._p]
0x1801546db  test    rdi, rdi
0x1801546de  jz      short loc_18015470A
0x1801546e0  mov     rdx, [rsp+148h+pDocURL]; pszbaseURL
0x1801546e5  mov     pSite, rdi; relativeURL
0x1801546e8  call    ?resolveURL@URL@@SAPEAVString@@PEAV2@PEBG@Z; URL::resolveURL(String *,ushort const *)
0x1801546ed  mov     rdi, rax
  ... truncated ...
```
