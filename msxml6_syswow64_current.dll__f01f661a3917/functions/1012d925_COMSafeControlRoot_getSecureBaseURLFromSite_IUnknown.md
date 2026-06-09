# COMSafeControlRoot::getSecureBaseURLFromSite(IUnknown *)

- ea: `0x1012d925`
- end: `0x1012dbe2`
- name: `?getSecureBaseURLFromSite@COMSafeControlRoot@@SGPAVString@@PAUIUnknown@@@Z`
- size: `701`
- prototype: `String *__userpurge@<eax>(IUnknown *pSite@<ecx>)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1012de54`

## callees

- `0x1003fba3`
- `0x10040be6`
- `0x10040c44`
- `0x10064cf1`
- `0x10064e0d`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x1012d925`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012db9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012db9a`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012dba3`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012dba3`

## pseudocode

```c
String *__thiscall COMSafeControlRoot::getSecureBaseURLFromSite(IUnknown *pSite)
{
  String *v1; // ebx
  HRESULT v2; // eax
  wchar_t *v3; // ecx
  Exception *v5; // eax
  wchar_t *pOleStr; // [esp+18h] [ebp-38h] BYREF
  IMoniker *pMk; // [esp+1Ch] [ebp-34h] BYREF
  IOleClientSite *pClientSite; // [esp+20h] [ebp-30h] BYREF
  IHTMLDocument2 *pHtmlDoc; // [esp+24h] [ebp-2Ch] BYREF
  IXMLDOMDocument *pXmlDoc; // [esp+28h] [ebp-28h] BYREF
  IServiceProvider *pSP; // [esp+2Ch] [ebp-24h] BYREF
  wchar_t *pDocURL; // [esp+30h] [ebp-20h] BYREF
  _reference<String> pResult; // [esp+34h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+38h] [ebp-18h]

  pClientSite = 0;
  pMk = 0;
  pSP = 0;
  pHtmlDoc = 0;
  pXmlDoc = 0;
  pDocURL = 0;
  pOleStr = 0;
  v1 = 0;
  pResult._p = 0;
  ms_exc.registration.TryLevel = 0;
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IXMLDOMDocument **))pSite->QueryInterface)(
         pSite->QueryInterface,
         pSite,
         &IID_IXMLDOMDocument,
         &pXmlDoc) >= 0 )
    goto LABEL_2;
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IOleClientSite **))pSite->QueryInterface)(
         pSite->QueryInterface,
         pSite,
         &IID_IOleClientSite,
         &pClientSite) < 0 )
  {
    if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IServiceProvider **))pSite->QueryInterface)(
           pSite->QueryInterface,
           pSite,
           &IID_IServiceProvider,
           &pSP) >= 0 )
    {
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, GUID *, GUID *, IXMLDOMDocument **))pSP->QueryService)(
             pSP->QueryService,
             pSP,
             &IID_IInternetHostSecurityManager,
             &IID_IXMLDOMDocument,
             &pXmlDoc) >= 0 )
      {
LABEL_2:
        v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMDocument *, wchar_t **), IXMLDOMDocument *, wchar_t **))pXmlDoc->get_url)(
               pXmlDoc->get_url,
               pXmlDoc,
               &pDocURL);
LABEL_3:
        if ( v2 < 0 )
        {
          Exception::throwHR(v2);
          Exception::throwThis(v5);
          JUMPOUT(0x1012DBDB);
        }
        v3 = pDocURL;
        goto LABEL_16;
      }
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, SID *, GUID *, IHTMLDocument2 **))pSP->QueryService)(
             pSP->QueryService,
             pSP,
             &SID_SContainerDispatch,
             &IID_IHTMLDocument2,
             &pHtmlDoc) >= 0
        || ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, GUID *, GUID *, IHTMLDocument2 **))pSP->QueryService)(
             pSP->QueryService,
             pSP,
             &IID_IInternetHostSecurityManager,
             &IID_IHTMLDocument2,
             &pHtmlDoc) >= 0 )
      {
        v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IHTMLDocument2 *, wchar_t **), IHTMLDocument2 *, wchar_t **))pHtmlDoc->get_URL)(
               pHtmlDoc->get_URL,
               pHtmlDoc,
               &pDocURL);
        goto LABEL_3;
      }
    }
  }
  else if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IOleClientSite *, unsigned int, unsigned int, IMoniker **), IOleClientSite *, int, int, IMoniker **))pClientSite->GetMoniker)(
              pClientSite->GetMoniker,
              pClientSite,
              1,
              1,
              &pMk) >= 0
         && ((int (__thiscall *)(HRESULT (__stdcall *)(IMoniker *, IBindCtx *, IMoniker *, wchar_t **), IMoniker *, _DWORD, _DWORD, wchar_t **))pMk->GetDisplayName)(
              pMk->GetDisplayName,
              pMk,
              0,
              0,
              &pOleStr) >= 0 )
  {
    v3 = pOleStr;
    if ( pOleStr )
    {
LABEL_16:
      v1 = String::newString(v3);
      release(&pResult._p);
      pResult._p = v1;
    }
  }
  ms_exc.registration.TryLevel = -2;
  if ( pClientSite )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IOleClientSite *))pClientSite->Release)(
      pClientSite->Release,
      pClientSite);
    pClientSite = 0;
  }
  if ( pMk )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pMk->Release)(pMk->Release, pMk);
    pMk = 0;
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
  CoTaskMemFree(pOleStr);
  SysFreeString(pDocURL);
  pResult._p = 0;
  release(&pResult._p);
  return v1;
}

```

## disassembly

```asm
0x1012d925  push    30h
0x1012d927  push    offset stru_1017C848
0x1012d92c  call    __SEH_prolog4
0x1012d931  mov     [ebp+var_3C], pSite
0x1012d934  xor     edi, edi
0x1012d936  mov     [ebp+pClientSite], edi
0x1012d939  mov     [ebp+pMk], edi
0x1012d93c  mov     [ebp+pSP], edi
0x1012d93f  mov     [ebp+pHtmlDoc], edi
0x1012d942  mov     [ebp+pXmlDoc], edi
0x1012d945  mov     [ebp+pDocURL], edi
0x1012d948  mov     [ebp+pOleStr], edi
0x1012d94b  mov     [ebp+var_40], edi
0x1012d94e  mov     ebx, edi
0x1012d950  mov     [ebp+pResult._p], ebx
0x1012d953  mov     [ebp+ms_exc.registration.TryLevel], edi
0x1012d956  mov     eax, [pSite]
0x1012d958  mov     esi, [eax]
0x1012d95a  lea     eax, [ebp+pXmlDoc]
0x1012d95d  push    eax
0x1012d95e  push    offset _IID_IXMLDOMDocument
0x1012d963  push    pSite
0x1012d964  mov     pSite, esi; this
0x1012d966  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d96c  call    esi
0x1012d96e  test    eax, eax
0x1012d970  js      short loc_1012D999
0x1012d972  mov     pSite, [ebp+pXmlDoc]
0x1012d975  mov     eax, [pSite]
0x1012d977  mov     esi, [eax+0F4h]
0x1012d97d  lea     eax, [ebp+pDocURL]
0x1012d980  push    eax
0x1012d981  push    pSite
0x1012d982  mov     pSite, esi; this
0x1012d984  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d98a  call    esi
0x1012d98c  test    eax, eax
0x1012d98e  js      loc_1012DBCD
0x1012d994  jmp     loc_1012DAB2
0x1012d999  mov     pSite, [ebp+var_3C]
0x1012d99c  mov     eax, [pSite]
0x1012d99e  mov     esi, [eax]
0x1012d9a0  lea     eax, [ebp+pClientSite]
0x1012d9a3  push    eax
0x1012d9a4  push    offset _IID_IOleClientSite
0x1012d9a9  push    pSite
0x1012d9aa  mov     pSite, esi; this
0x1012d9ac  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d9b2  call    esi
0x1012d9b4  test    eax, eax
0x1012d9b6  js      short loc_1012DA0C
0x1012d9b8  mov     pSite, [ebp+pClientSite]
0x1012d9bb  mov     eax, [pSite]
0x1012d9bd  mov     esi, [eax+10h]
0x1012d9c0  lea     eax, [ebp+pMk]
0x1012d9c3  push    eax
0x1012d9c4  push    1
0x1012d9c6  push    1
0x1012d9c8  push    pSite
0x1012d9c9  mov     pSite, esi; this
0x1012d9cb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d9d1  call    esi
0x1012d9d3  test    eax, eax
0x1012d9d5  jns     short loc_1012D9E3
0x1012d9d7  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012d9de  jmp     Cleanup_22
0x1012d9e3  mov     pSite, [ebp+pMk]
0x1012d9e6  mov     eax, [pSite]
0x1012d9e8  mov     esi, [eax+50h]
0x1012d9eb  lea     eax, [ebp+pOleStr]
0x1012d9ee  push    eax
0x1012d9ef  push    edi
0x1012d9f0  push    edi
0x1012d9f1  push    pSite
0x1012d9f2  mov     pSite, esi; this
0x1012d9f4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012d9fa  call    esi
0x1012d9fc  test    eax, eax
0x1012d9fe  js      short loc_1012D9D7
0x1012da00  mov     pSite, [ebp+pOleStr]
0x1012da03  test    pSite, pSite
0x1012da05  jz      short loc_1012D9D7
0x1012da07  jmp     loc_1012DAB5
0x1012da0c  mov     pSite, [ebp+var_3C]
0x1012da0f  mov     eax, [pSite]
0x1012da11  mov     esi, [eax]
0x1012da13  lea     eax, [ebp+pSP]
0x1012da16  push    eax
0x1012da17  push    offset _IID_IServiceProvider
0x1012da1c  push    pSite
0x1012da1d  mov     pSite, esi; this
0x1012da1f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012da25  call    esi
0x1012da27  test    eax, eax
0x1012da29  js      short loc_1012D9D7
0x1012da2b  mov     pSite, [ebp+pSP]
0x1012da2e  mov     eax, [pSite]
0x1012da30  mov     esi, [eax+0Ch]
0x1012da33  lea     eax, [ebp+pXmlDoc]
0x1012da36  push    eax
0x1012da37  push    offset _IID_IXMLDOMDocument
0x1012da3c  push    offset _IID_IInternetHostSecurityManager
0x1012da41  push    pSite
0x1012da42  mov     pSite, esi; this
0x1012da44  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012da4a  call    esi
0x1012da4c  test    eax, eax
0x1012da4e  jns     loc_1012D972
0x1012da54  mov     pSite, [ebp+pSP]
0x1012da57  mov     eax, [pSite]
0x1012da59  mov     esi, [eax+0Ch]
0x1012da5c  lea     eax, [ebp+pHtmlDoc]
0x1012da5f  push    eax
0x1012da60  push    offset _IID_IHTMLDocument2
0x1012da65  push    offset _SID_SContainerDispatch
0x1012da6a  push    pSite
0x1012da6b  mov     pSite, esi; this
0x1012da6d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012da73  call    esi
0x1012da75  test    eax, eax
0x1012da77  jns     short loc_1012DAA2
0x1012da79  mov     pSite, [ebp+pSP]
0x1012da7c  mov     eax, [pSite]
0x1012da7e  mov     esi, [eax+0Ch]
0x1012da81  lea     eax, [ebp+pHtmlDoc]
0x1012da84  push    eax
0x1012da85  push    offset _IID_IHTMLDocument2
0x1012da8a  push    offset _IID_IInternetHostSecurityManager
0x1012da8f  push    pSite
0x1012da90  mov     pSite, esi; this
0x1012da92  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012da98  call    esi
0x1012da9a  test    eax, eax
0x1012da9c  js      loc_1012D9D7
0x1012daa2  mov     pSite, [ebp+pHtmlDoc]
0x1012daa5  mov     eax, [pSite]
0x1012daa7  mov     esi, [eax+0A0h]
0x1012daad  jmp     loc_1012D97D
0x1012dab2  mov     pSite, [ebp+pDocURL]; c
0x1012dab5  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1012daba  mov     ebx, eax
0x1012dabc  lea     pSite, [ebp+pResult]; ppref
0x1012dabf  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dac4  mov     [ebp+pResult._p], ebx
0x1012dac7  jmp     loc_1012D9D7
0x1012dacc  mov     pSite, [ebp+ms_exc.exc_ptr]; ep
0x1012dacf  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1012dad4  retn
0x1012dad5  mov     esp, [ebp+ms_exc.old_esp]
0x1012dad8  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1012dadd  mov     ebx, [ebp+pResult._p]
0x1012dae0  test    ebx, ebx
0x1012dae2  jz      short loc_1012DAF1
0x1012dae4  xor     edx, edx; pref
0x1012dae6  lea     pSite, [ebp+pResult]; ppref
0x1012dae9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1012daee  mov     ebx, [ebp+pResult._p]
0x1012daf1  mov     pSite, __tls_index
0x1012daf7  mov     eax, large fs:2Ch
0x1012dafd  mov     eax, [eax+pSite*4]
0x1012db00  mov     eax, [eax+4]
0x1012db06  mov     eax, [eax+8]
0x1012db09  mov     [ebp+var_40], eax
0x1012db0c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012db13  xor     edi, edi
0x1012db15  mov     pSite, [ebp+pClientSite]
0x1012db18  test    pSite, pSite
0x1012db1a  jz      short loc_1012DB2F
0x1012db1c  mov     eax, [pSite]
0x1012db1e  push    pSite
0x1012db1f  mov     esi, [eax+8]
0x1012db22  mov     pSite, esi; this
0x1012db24  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db2a  call    esi
0x1012db2c  mov     [ebp+pClientSite], edi
0x1012db2f  mov     pSite, [ebp+pMk]
0x1012db32  test    pSite, pSite
0x1012db34  jz      short loc_1012DB49
0x1012db36  mov     eax, [pSite]
0x1012db38  push    pSite
0x1012db39  mov     esi, [eax+8]
0x1012db3c  mov     pSite, esi; this
0x1012db3e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db44  call    esi
0x1012db46  mov     [ebp+pMk], edi
0x1012db49  mov     pSite, [ebp+pSP]
0x1012db4c  test    pSite, pSite
0x1012db4e  jz      short loc_1012DB63
0x1012db50  mov     eax, [pSite]
0x1012db52  push    pSite
0x1012db53  mov     esi, [eax+8]
0x1012db56  mov     pSite, esi; this
0x1012db58  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db5e  call    esi
0x1012db60  mov     [ebp+pSP], edi
0x1012db63  mov     pSite, [ebp+pHtmlDoc]
0x1012db66  test    pSite, pSite
0x1012db68  jz      short loc_1012DB7D
0x1012db6a  mov     eax, [pSite]
0x1012db6c  push    pSite
0x1012db6d  mov     esi, [eax+8]
0x1012db70  mov     pSite, esi; this
0x1012db72  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db78  call    esi
0x1012db7a  mov     [ebp+pHtmlDoc], edi
0x1012db7d  mov     pSite, [ebp+pXmlDoc]
0x1012db80  test    pSite, pSite
0x1012db82  jz      short loc_1012DB97
0x1012db84  mov     eax, [pSite]
0x1012db86  push    pSite
0x1012db87  mov     esi, [eax+8]
0x1012db8a  mov     pSite, esi; this
0x1012db8c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db92  call    esi
0x1012db94  mov     [ebp+pXmlDoc], edi
0x1012db97  push    [ebp+pOleStr]; pv
0x1012db9a  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1012dba0  push    [ebp+pDocURL]; bstrString
0x1012dba3  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1012dba9  mov     eax, [ebp+var_40]
0x1012dbac  test    eax, eax
0x1012dbae  jnz     short loc_1012DBD4
0x1012dbb0  mov     [ebp+pResult._p], edi
0x1012dbb3  lea     pSite, [ebp+pResult]; ppref
0x1012dbb6  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dbbb  mov     eax, ebx
0x1012dbbd  mov     pSite, [ebp+ms_exc.registration.Next]
0x1012dbc0  mov     large fs:0, pSite
0x1012dbc7  pop     pSite
0x1012dbc8  pop     edi
0x1012dbc9  pop     esi
0x1012dbca  pop     ebx
0x1012dbcb  leave
0x1012dbcc  retn
0x1012dbcd  mov     pSite, eax; hr
0x1012dbcf  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x1012dbd4  mov     pSite, eax; this
0x1012dbd6  call    ?throwThis@Exception@@QAEXXZ; Exception::throwThis(void)
```
