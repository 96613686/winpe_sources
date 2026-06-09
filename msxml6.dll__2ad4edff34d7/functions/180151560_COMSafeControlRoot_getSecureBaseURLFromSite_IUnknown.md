# COMSafeControlRoot::getSecureBaseURLFromSite(IUnknown *)

- ea: `0x180151560`
- end: `0x1801518d7`
- name: `?getSecureBaseURLFromSite@COMSafeControlRoot@@SAPEAVString@@PEAUIUnknown@@@Z`
- size: `887`
- prototype: `String *__fastcall(IUnknown *pSite)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180151b8c`

## callees

- `0x180009490`
- `0x18000d688`
- `0x18000d7d0`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800bc3b0`
- `0x1800bc400`
- `0x180151560`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015187a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015187a`
- `OLEAUT32!__imp_SysFreeString` at `0x180151888`
- `OLEAUT32!__imp_SysFreeString` at `0x180151888`

## pseudocode

```c
String *__fastcall COMSafeControlRoot::getSecureBaseURLFromSite(IUnknown *pSite)
{
  String *v2; // rdi
  HRESULT v3; // eax
  wchar_t *v4; // rcx
  HRESULT v5; // eax
  HRESULT v6; // eax
  IXMLDOMDocument *pXmlDoc; // [rsp+30h] [rbp-48h] BYREF
  IHTMLDocument2 *pHtmlDoc; // [rsp+38h] [rbp-40h] BYREF
  IOleClientSite *pClientSite; // [rsp+40h] [rbp-38h] BYREF
  IMoniker *pMk; // [rsp+48h] [rbp-30h] BYREF
  wchar_t *pOleStr; // [rsp+50h] [rbp-28h] BYREF
  _reference<String> pResult; // [rsp+88h] [rbp+10h] BYREF
  wchar_t *pDocURL; // [rsp+90h] [rbp+18h] BYREF
  IServiceProvider *pSP; // [rsp+98h] [rbp+20h] BYREF

  pClientSite = 0;
  pMk = 0;
  pSP = 0;
  pHtmlDoc = 0;
  pXmlDoc = 0;
  pDocURL = 0;
  pOleStr = 0;
  v2 = 0;
  pResult._p = 0;
  if ( pSite->QueryInterface(pSite, &IID_IXMLDOMDocument, (void **)&pXmlDoc) >= 0 )
  {
    v3 = pXmlDoc->get_url(pXmlDoc, &pDocURL);
    if ( v3 < 0 )
      Exception::throwHR(v3);
LABEL_16:
    v4 = pDocURL;
LABEL_17:
    v2 = String::newString(v4);
    release(&pResult._p);
    pResult._p = v2;
    goto $Cleanup_22;
  }
  if ( pSite->QueryInterface(pSite, &IID_IOleClientSite, (void **)&pClientSite) < 0 )
  {
    if ( pSite->QueryInterface(pSite, &IID_IServiceProvider, (void **)&pSP) < 0 )
      goto $Cleanup_22;
    if ( pSP->QueryService(pSP, &IID_IInternetHostSecurityManager, &IID_IXMLDOMDocument, (void **)&pXmlDoc) >= 0 )
    {
      v5 = pXmlDoc->get_url(pXmlDoc, &pDocURL);
      if ( v5 < 0 )
        Exception::throwHR(v5);
      goto LABEL_16;
    }
    if ( pSP->QueryService(pSP, (const _GUID *)&SID_SContainerDispatch, &IID_IHTMLDocument2, (void **)&pHtmlDoc) >= 0
      || pSP->QueryService(pSP, &IID_IInternetHostSecurityManager, &IID_IHTMLDocument2, (void **)&pHtmlDoc) >= 0 )
    {
      v6 = pHtmlDoc->get_URL(pHtmlDoc, &pDocURL);
      if ( v6 < 0 )
        Exception::throwHR(v6);
      goto LABEL_16;
    }
  }
  else if ( pClientSite->GetMoniker(pClientSite, 1u, 1u, &pMk) >= 0 && pMk->GetDisplayName(pMk, 0, 0, &pOleStr) >= 0 )
  {
    v4 = pOleStr;
    if ( pOleStr )
      goto LABEL_17;
  }
$Cleanup_22:
  if ( pClientSite )
  {
    pClientSite->Release(pClientSite);
    pClientSite = 0;
  }
  if ( pMk )
  {
    pMk->Release(pMk);
    pMk = 0;
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
  CoTaskMemFree(pOleStr);
  SysFreeString(pDocURL);
  pResult._p = 0;
  release(&pResult._p);
  return v2;
}

```

## disassembly

```asm
0x180151560  mov     rax, rsp
0x180151563  push    rsi
0x180151564  push    rdi
0x180151565  push    r14
0x180151567  sub     rsp, 60h
0x18015156b  mov     rsi, pSite
0x18015156e  mov     qword ptr [rax-38h], 0
0x180151576  mov     qword ptr [rax-30h], 0
0x18015157e  mov     qword ptr [rax+20h], 0
0x180151586  mov     qword ptr [rax-40h], 0
0x18015158e  mov     qword ptr [rax-48h], 0
0x180151596  mov     qword ptr [rax+18h], 0
0x18015159e  mov     qword ptr [rax-28h], 0
0x1801515a6  xor     r14d, r14d
0x1801515a9  xor     edi, edi
0x1801515ab  mov     [rax+10h], rdi
0x1801515af  mov     rax, [pSite]
0x1801515b2  lea     r8, [rsp+78h+pXmlDoc]
0x1801515b7  lea     rdx, IID_IXMLDOMDocument
0x1801515be  mov     rax, [rax]
0x1801515c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801515c6  test    eax, eax
0x1801515c8  js      short loc_1801515F3
0x1801515ca  mov     pSite, [rsp+78h+pXmlDoc]
0x1801515cf  mov     rax, [pSite]
0x1801515d2  lea     rdx, [rsp+78h+pDocURL]
0x1801515da  mov     rax, [rax+1E8h]
0x1801515e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801515e6  test    eax, eax
0x1801515e8  js      loc_1801518B8
0x1801515ee  jmp     loc_180151764
0x1801515f3  mov     rax, [rsi]
0x1801515f6  lea     r8, [rsp+78h+pClientSite]
0x1801515fb  lea     rdx, IID_IOleClientSite
0x180151602  mov     pSite, rsi
0x180151605  mov     rax, [rax]
0x180151608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015160d  test    eax, eax
0x18015160f  js      short loc_180151670
0x180151611  mov     pSite, [rsp+78h+pClientSite]
0x180151616  mov     rax, [pSite]
0x180151619  lea     r9, [rsp+78h+pMk]
0x18015161e  mov     edx, 1
0x180151623  mov     r8d, edx
0x180151626  mov     rax, [rax+20h]
0x18015162a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015162f  test    eax, eax
0x180151631  js      $Cleanup_22
0x180151637  mov     pSite, [rsp+78h+pMk]
0x18015163c  mov     rax, [pSite]
0x18015163f  lea     r9, [rsp+78h+pOleStr]
0x180151644  xor     r8d, r8d
0x180151647  xor     edx, edx
0x180151649  mov     rax, [rax+0A0h]
0x180151650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151655  test    eax, eax
0x180151657  js      $Cleanup_22
0x18015165d  mov     pSite, [rsp+78h+pOleStr]
0x180151662  test    pSite, pSite
0x180151665  jz      loc_180151789
0x18015166b  jmp     loc_18015176C
0x180151670  mov     rax, [rsi]
0x180151673  lea     r8, [rsp+78h+pSP]
0x18015167b  lea     rdx, IID_IServiceProvider
0x180151682  mov     pSite, rsi
0x180151685  mov     rax, [rax]
0x180151688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015168d  test    eax, eax
0x18015168f  js      $Cleanup_22
0x180151695  mov     pSite, [rsp+78h+pSP]
0x18015169d  mov     rax, [pSite]
0x1801516a0  lea     r9, [rsp+78h+pXmlDoc]
0x1801516a5  lea     r8, IID_IXMLDOMDocument
0x1801516ac  lea     rdx, IID_IInternetHostSecurityManager
0x1801516b3  mov     rax, [rax+18h]
0x1801516b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801516bc  test    eax, eax
0x1801516be  js      short loc_1801516E6
0x1801516c0  mov     pSite, [rsp+78h+pXmlDoc]
0x1801516c5  mov     rax, [pSite]
0x1801516c8  lea     rdx, [rsp+78h+pDocURL]
0x1801516d0  mov     rax, [rax+1E8h]
0x1801516d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801516dc  test    eax, eax
0x1801516de  js      loc_1801518BF
0x1801516e4  jmp     short loc_180151764
0x1801516e6  mov     pSite, [rsp+78h+pSP]
0x1801516ee  mov     rax, [pSite]
0x1801516f1  lea     r9, [rsp+78h+pHtmlDoc]
0x1801516f6  lea     r8, IID_IHTMLDocument2
0x1801516fd  lea     rdx, SID_SContainerDispatch
0x180151704  mov     rax, [rax+18h]
0x180151708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015170d  test    eax, eax
0x18015170f  jns     short loc_180151740
0x180151711  mov     pSite, [rsp+78h+pSP]
0x180151719  mov     rax, [pSite]
0x18015171c  lea     r9, [rsp+78h+pHtmlDoc]
0x180151721  lea     r8, IID_IHTMLDocument2
0x180151728  lea     rdx, IID_IInternetHostSecurityManager
0x18015172f  mov     rax, [rax+18h]
0x180151733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151738  test    eax, eax
0x18015173a  js      $Cleanup_22
0x180151740  mov     pSite, [rsp+78h+pHtmlDoc]
0x180151745  mov     rax, [pSite]
0x180151748  lea     rdx, [rsp+78h+pDocURL]
0x180151750  mov     rax, [rax+140h]
0x180151757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015175c  test    eax, eax
0x18015175e  js      loc_1801518C6
0x180151764  mov     pSite, [rsp+78h+pDocURL]; c
0x18015176c  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180151771  mov     rdi, rax
0x180151774  lea     pSite, [rsp+78h+pResult]; ppref
0x18015177c  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180151781  mov     [rsp+78h+pResult._p], rdi
0x180151789  jmp     short $Cleanup_22
0x18015178b  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180151790  mov     rdi, [rsp+78h+pResult._p]
0x180151798  test    rdi, rdi
0x18015179b  jz      short loc_1801517B4
0x18015179d  xor     edx, edx; pref
0x18015179f  lea     pSite, [rsp+78h+pResult]; ppref
0x1801517a7  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801517ac  mov     rdi, [rsp+78h+pResult._p]
0x1801517b4  mov     ecx, cs:_tls_index
0x1801517ba  mov     rax, gs:58h
0x1801517c3  mov     edx, 8
0x1801517c8  mov     rax, [rax+pSite*8]
0x1801517cc  mov     pSite, [rax+rdx]
0x1801517d0  mov     r14, [pSite+8]
0x1801517d4  mov     pSite, [rsp+78h+pClientSite]
0x1801517d9  test    pSite, pSite
0x1801517dc  jz      short loc_1801517F3
0x1801517de  mov     rax, [pSite]
0x1801517e1  mov     rax, [rax+10h]
0x1801517e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801517ea  mov     [rsp+78h+pClientSite], 0
0x1801517f3  mov     pSite, [rsp+78h+pMk]
0x1801517f8  test    pSite, pSite
0x1801517fb  jz      short loc_180151812
0x1801517fd  mov     rax, [pSite]
0x180151800  mov     rax, [rax+10h]
0x180151804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151809  mov     [rsp+78h+pMk], 0
0x180151812  mov     pSite, [rsp+78h+pSP]
0x18015181a  test    pSite, pSite
0x18015181d  jz      short loc_180151837
0x18015181f  mov     rax, [pSite]
0x180151822  mov     rax, [rax+10h]
0x180151826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015182b  mov     [rsp+78h+pSP], 0
0x180151837  mov     pSite, [rsp+78h+pHtmlDoc]
0x18015183c  test    pSite, pSite
0x18015183f  jz      short loc_180151856
0x180151841  mov     rax, [pSite]
0x180151844  mov     rax, [rax+10h]
0x180151848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015184d  mov     [rsp+78h+pHtmlDoc], 0
0x180151856  mov     pSite, [rsp+78h+pXmlDoc]
0x18015185b  test    pSite, pSite
0x18015185e  jz      short loc_180151875
0x180151860  mov     rax, [pSite]
0x180151863  mov     rax, [rax+10h]
0x180151867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015186c  mov     [rsp+78h+pXmlDoc], 0
0x180151875  mov     pSite, [rsp+78h+pOleStr]; pv
0x18015187a  call    cs:__imp_CoTaskMemFree
0x180151880  mov     pSite, [rsp+78h+pDocURL]; bstrString
0x180151888  call    cs:__imp_SysFreeString
0x18015188e  test    r14, r14
0x180151891  jnz     short loc_1801518CE
0x180151893  mov     [rsp+78h+pResult._p], 0
0x18015189f  lea     pSite, [rsp+78h+pResult]; ppref
0x1801518a7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1801518ac  mov     rax, rdi
0x1801518af  add     rsp, 60h
0x1801518b3  pop     r14
0x1801518b5  pop     rdi
0x1801518b6  pop     rsi
0x1801518b7  retn
0x1801518b8  mov     ecx, eax; hr
0x1801518ba  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1801518bf  mov     ecx, eax; hr
0x1801518c1  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1801518c6  mov     ecx, eax; hr
0x1801518c8  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x1801518ce  mov     pSite, r14; this
0x1801518d1  call    ?throwThis@Exception@@QEAAXXZ; Exception::throwThis(void)
0x18017e470  push    rbp
0x18017e472  sub     rsp, 30h
0x18017e476  mov     rbp, rdx
0x18017e479  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017e47e  nop
0x18017e47f  add     rsp, 30h
0x18017e483  pop     rbp
0x18017e484  retn
```
