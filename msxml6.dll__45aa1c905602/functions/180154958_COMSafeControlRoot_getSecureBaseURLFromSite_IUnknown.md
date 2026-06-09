# COMSafeControlRoot::getSecureBaseURLFromSite(IUnknown *)

- ea: `0x180154958`
- end: `0x180154cdc`
- name: `?getSecureBaseURLFromSite@COMSafeControlRoot@@SAPEAVString@@PEAUIUnknown@@@Z`
- size: `900`
- prototype: `String *__fastcall(IUnknown *pSite)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180154f9c`

## callees

- `0x180015a80`
- `0x180019cd0`
- `0x180019e20`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800bda08`
- `0x1800bda58`
- `0x180154958`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180154c86`
- `OLEAUT32!__imp_SysFreeString` at `0x180154c86`

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
    goto $Cleanup_23;
  }
  if ( pSite->QueryInterface(pSite, &IID_IOleClientSite, (void **)&pClientSite) < 0 )
  {
    if ( pSite->QueryInterface(pSite, &IID_IServiceProvider, (void **)&pSP) < 0 )
      goto $Cleanup_23;
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
$Cleanup_23:
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
0x180154958  mov     rax, rsp
0x18015495b  push    rsi
0x18015495c  push    rdi
0x18015495d  push    r14
0x18015495f  sub     rsp, 60h
0x180154963  mov     rsi, pSite
0x180154966  mov     qword ptr [rax-38h], 0
0x18015496e  mov     qword ptr [rax-30h], 0
0x180154976  mov     qword ptr [rax+20h], 0
0x18015497e  mov     qword ptr [rax-40h], 0
0x180154986  mov     qword ptr [rax-48h], 0
0x18015498e  mov     qword ptr [rax+18h], 0
0x180154996  mov     qword ptr [rax-28h], 0
0x18015499e  xor     r14d, r14d
0x1801549a1  xor     edi, edi
0x1801549a3  mov     [rax+10h], rdi
0x1801549a7  mov     rax, [pSite]
0x1801549aa  lea     r8, [rsp+78h+pXmlDoc]
0x1801549af  lea     rdx, IID_IXMLDOMDocument
0x1801549b6  mov     rax, [rax]
0x1801549b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801549be  test    eax, eax
0x1801549c0  js      short loc_1801549EB
0x1801549c2  mov     pSite, [rsp+78h+pXmlDoc]
0x1801549c7  mov     rax, [pSite]
0x1801549ca  lea     rdx, [rsp+78h+pDocURL]
0x1801549d2  mov     rax, [rax+1E8h]
0x1801549d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801549de  test    eax, eax
0x1801549e0  js      loc_180154CBD
0x1801549e6  jmp     loc_180154B5C
0x1801549eb  mov     rax, [rsi]
0x1801549ee  lea     r8, [rsp+78h+pClientSite]
0x1801549f3  lea     rdx, IID_IOleClientSite
0x1801549fa  mov     pSite, rsi
0x1801549fd  mov     rax, [rax]
0x180154a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a05  test    eax, eax
0x180154a07  js      short loc_180154A68
0x180154a09  mov     pSite, [rsp+78h+pClientSite]
0x180154a0e  mov     rax, [pSite]
0x180154a11  lea     r9, [rsp+78h+pMk]
0x180154a16  mov     edx, 1
0x180154a1b  mov     r8d, edx
0x180154a1e  mov     rax, [rax+20h]
0x180154a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a27  test    eax, eax
0x180154a29  js      $Cleanup_23
0x180154a2f  mov     pSite, [rsp+78h+pMk]
0x180154a34  mov     rax, [pSite]
0x180154a37  lea     r9, [rsp+78h+pOleStr]
0x180154a3c  xor     r8d, r8d
0x180154a3f  xor     edx, edx
0x180154a41  mov     rax, [rax+0A0h]
0x180154a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a4d  test    eax, eax
0x180154a4f  js      $Cleanup_23
0x180154a55  mov     pSite, [rsp+78h+pOleStr]
0x180154a5a  test    pSite, pSite
0x180154a5d  jz      loc_180154B81
0x180154a63  jmp     loc_180154B64
0x180154a68  mov     rax, [rsi]
0x180154a6b  lea     r8, [rsp+78h+pSP]
0x180154a73  lea     rdx, IID_IServiceProvider
0x180154a7a  mov     pSite, rsi
0x180154a7d  mov     rax, [rax]
0x180154a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a85  test    eax, eax
0x180154a87  js      $Cleanup_23
0x180154a8d  mov     pSite, [rsp+78h+pSP]
0x180154a95  mov     rax, [pSite]
0x180154a98  lea     r9, [rsp+78h+pXmlDoc]
0x180154a9d  lea     r8, IID_IXMLDOMDocument
0x180154aa4  lea     rdx, IID_IInternetHostSecurityManager
0x180154aab  mov     rax, [rax+18h]
0x180154aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154ab4  test    eax, eax
0x180154ab6  js      short loc_180154ADE
0x180154ab8  mov     pSite, [rsp+78h+pXmlDoc]
0x180154abd  mov     rax, [pSite]
0x180154ac0  lea     rdx, [rsp+78h+pDocURL]
0x180154ac8  mov     rax, [rax+1E8h]
0x180154acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154ad4  test    eax, eax
0x180154ad6  js      loc_180154CC4
0x180154adc  jmp     short loc_180154B5C
0x180154ade  mov     pSite, [rsp+78h+pSP]
0x180154ae6  mov     rax, [pSite]
0x180154ae9  lea     r9, [rsp+78h+pHtmlDoc]
0x180154aee  lea     r8, IID_IHTMLDocument2
0x180154af5  lea     rdx, SID_SContainerDispatch
0x180154afc  mov     rax, [rax+18h]
0x180154b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b05  test    eax, eax
0x180154b07  jns     short loc_180154B38
0x180154b09  mov     pSite, [rsp+78h+pSP]
0x180154b11  mov     rax, [pSite]
0x180154b14  lea     r9, [rsp+78h+pHtmlDoc]
0x180154b19  lea     r8, IID_IHTMLDocument2
0x180154b20  lea     rdx, IID_IInternetHostSecurityManager
0x180154b27  mov     rax, [rax+18h]
0x180154b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b30  test    eax, eax
0x180154b32  js      $Cleanup_23
0x180154b38  mov     pSite, [rsp+78h+pHtmlDoc]
0x180154b3d  mov     rax, [pSite]
0x180154b40  lea     rdx, [rsp+78h+pDocURL]
0x180154b48  mov     rax, [rax+140h]
0x180154b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b54  test    eax, eax
0x180154b56  js      loc_180154CCB
0x180154b5c  mov     pSite, [rsp+78h+pDocURL]; c
0x180154b64  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180154b69  mov     rdi, rax
0x180154b6c  lea     pSite, [rsp+78h+pResult]; ppref
0x180154b74  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154b79  mov     [rsp+78h+pResult._p], rdi
0x180154b81  jmp     short $Cleanup_23
0x180154b83  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180154b88  mov     rdi, [rsp+78h+pResult._p]
0x180154b90  test    rdi, rdi
0x180154b93  jz      short loc_180154BAC
0x180154b95  xor     edx, edx; pref
0x180154b97  lea     pSite, [rsp+78h+pResult]; ppref
0x180154b9f  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180154ba4  mov     rdi, [rsp+78h+pResult._p]
0x180154bac  mov     ecx, cs:_tls_index
0x180154bb2  mov     rax, gs:58h
0x180154bbb  mov     edx, 8
0x180154bc0  mov     rax, [rax+pSite*8]
0x180154bc4  mov     pSite, [rax+rdx]
0x180154bc8  mov     r14, [pSite+8]
0x180154bcc  mov     pSite, [rsp+78h+pClientSite]
0x180154bd1  test    pSite, pSite
0x180154bd4  jz      short loc_180154BEB
0x180154bd6  mov     rax, [pSite]
0x180154bd9  mov     rax, [rax+10h]
0x180154bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154be2  mov     [rsp+78h+pClientSite], 0
0x180154beb  mov     pSite, [rsp+78h+pMk]
0x180154bf0  test    pSite, pSite
0x180154bf3  jz      short loc_180154C0A
0x180154bf5  mov     rax, [pSite]
0x180154bf8  mov     rax, [rax+10h]
0x180154bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154c01  mov     [rsp+78h+pMk], 0
0x180154c0a  mov     pSite, [rsp+78h+pSP]
0x180154c12  test    pSite, pSite
0x180154c15  jz      short loc_180154C2F
0x180154c17  mov     rax, [pSite]
0x180154c1a  mov     rax, [rax+10h]
0x180154c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154c23  mov     [rsp+78h+pSP], 0
0x180154c2f  mov     pSite, [rsp+78h+pHtmlDoc]
0x180154c34  test    pSite, pSite
0x180154c37  jz      short loc_180154C4E
0x180154c39  mov     rax, [pSite]
0x180154c3c  mov     rax, [rax+10h]
0x180154c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154c45  mov     [rsp+78h+pHtmlDoc], 0
0x180154c4e  mov     pSite, [rsp+78h+pXmlDoc]
0x180154c53  test    pSite, pSite
0x180154c56  jz      short loc_180154C6D
0x180154c58  mov     rax, [pSite]
0x180154c5b  mov     rax, [rax+10h]
0x180154c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154c64  mov     [rsp+78h+pXmlDoc], 0
0x180154c6d  mov     pSite, [rsp+78h+pOleStr]; pv
0x180154c72  call    cs:__imp_CoTaskMemFree
0x180154c79  nop     dword ptr [rax+rax+00h]
0x180154c7e  mov     pSite, [rsp+78h+pDocURL]; bstrString
0x180154c86  call    cs:__imp_SysFreeString
0x180154c8d  nop     dword ptr [rax+rax+00h]
0x180154c92  test    r14, r14
0x180154c95  jnz     short loc_180154CD3
0x180154c97  mov     [rsp+78h+pResult._p], 0
0x180154ca3  lea     pSite, [rsp+78h+pResult]; ppref
0x180154cab  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154cb0  mov     rax, rdi
0x180154cb3  add     rsp, 60h
0x180154cb7  pop     r14
0x180154cb9  pop     rdi
0x180154cba  pop     rsi
0x180154cbb  retn
0x180154cbd  mov     ecx, eax; hr
0x180154cbf  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180154cc4  mov     ecx, eax; hr
0x180154cc6  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180154ccb  mov     ecx, eax; hr
0x180154ccd  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180154cd3  mov     pSite, r14; this
0x180154cd6  call    ?throwThis@Exception@@QEAAXXZ; Exception::throwThis(void)
0x18018212e  push    rbp
0x180182130  sub     rsp, 30h
0x180182134  mov     rbp, rdx
0x180182137  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18018213c  nop
0x18018213d  add     rsp, 30h
0x180182141  pop     rbp
0x180182142  retn
```
