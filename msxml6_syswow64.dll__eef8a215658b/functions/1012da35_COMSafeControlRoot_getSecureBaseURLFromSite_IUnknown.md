# COMSafeControlRoot::getSecureBaseURLFromSite(IUnknown *)

- ea: `0x1012da35`
- end: `0x1012dcf2`
- name: `?getSecureBaseURLFromSite@COMSafeControlRoot@@SGPAVString@@PAUIUnknown@@@Z`
- size: `701`
- prototype: `String *__userpurge@<eax>(IUnknown *pSite@<ecx>)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1012df64`

## callees

- `0x1003fb13`
- `0x10040b56`
- `0x10040bb4`
- `0x10064c51`
- `0x10064d6d`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x1012da35`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012dcaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1012dcaa`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012dcb3`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012dcb3`

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
          JUMPOUT(0x1012DCEB);
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
0x1012da35  push    30h
0x1012da37  push    offset stru_1017C938
0x1012da3c  call    __SEH_prolog4
0x1012da41  mov     [ebp+var_3C], pSite
0x1012da44  xor     edi, edi
0x1012da46  mov     [ebp+pClientSite], edi
0x1012da49  mov     [ebp+pMk], edi
0x1012da4c  mov     [ebp+pSP], edi
0x1012da4f  mov     [ebp+pHtmlDoc], edi
0x1012da52  mov     [ebp+pXmlDoc], edi
0x1012da55  mov     [ebp+pDocURL], edi
0x1012da58  mov     [ebp+pOleStr], edi
0x1012da5b  mov     [ebp+var_40], edi
0x1012da5e  mov     ebx, edi
0x1012da60  mov     [ebp+pResult._p], ebx
0x1012da63  mov     [ebp+ms_exc.registration.TryLevel], edi
0x1012da66  mov     eax, [pSite]
0x1012da68  mov     esi, [eax]
0x1012da6a  lea     eax, [ebp+pXmlDoc]
0x1012da6d  push    eax
0x1012da6e  push    offset _IID_IXMLDOMDocument
0x1012da73  push    pSite
0x1012da74  mov     pSite, esi; this
0x1012da76  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012da7c  call    esi
0x1012da7e  test    eax, eax
0x1012da80  js      short loc_1012DAA9
0x1012da82  mov     pSite, [ebp+pXmlDoc]
0x1012da85  mov     eax, [pSite]
0x1012da87  mov     esi, [eax+0F4h]
0x1012da8d  lea     eax, [ebp+pDocURL]
0x1012da90  push    eax
0x1012da91  push    pSite
0x1012da92  mov     pSite, esi; this
0x1012da94  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012da9a  call    esi
0x1012da9c  test    eax, eax
0x1012da9e  js      loc_1012DCDD
0x1012daa4  jmp     loc_1012DBC2
0x1012daa9  mov     pSite, [ebp+var_3C]
0x1012daac  mov     eax, [pSite]
0x1012daae  mov     esi, [eax]
0x1012dab0  lea     eax, [ebp+pClientSite]
0x1012dab3  push    eax
0x1012dab4  push    offset _IID_IOleClientSite
0x1012dab9  push    pSite
0x1012daba  mov     pSite, esi; this
0x1012dabc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dac2  call    esi
0x1012dac4  test    eax, eax
0x1012dac6  js      short loc_1012DB1C
0x1012dac8  mov     pSite, [ebp+pClientSite]
0x1012dacb  mov     eax, [pSite]
0x1012dacd  mov     esi, [eax+10h]
0x1012dad0  lea     eax, [ebp+pMk]
0x1012dad3  push    eax
0x1012dad4  push    1
0x1012dad6  push    1
0x1012dad8  push    pSite
0x1012dad9  mov     pSite, esi; this
0x1012dadb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dae1  call    esi
0x1012dae3  test    eax, eax
0x1012dae5  jns     short loc_1012DAF3
0x1012dae7  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012daee  jmp     Cleanup_22
0x1012daf3  mov     pSite, [ebp+pMk]
0x1012daf6  mov     eax, [pSite]
0x1012daf8  mov     esi, [eax+50h]
0x1012dafb  lea     eax, [ebp+pOleStr]
0x1012dafe  push    eax
0x1012daff  push    edi
0x1012db00  push    edi
0x1012db01  push    pSite
0x1012db02  mov     pSite, esi; this
0x1012db04  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db0a  call    esi
0x1012db0c  test    eax, eax
0x1012db0e  js      short loc_1012DAE7
0x1012db10  mov     pSite, [ebp+pOleStr]
0x1012db13  test    pSite, pSite
0x1012db15  jz      short loc_1012DAE7
0x1012db17  jmp     loc_1012DBC5
0x1012db1c  mov     pSite, [ebp+var_3C]
0x1012db1f  mov     eax, [pSite]
0x1012db21  mov     esi, [eax]
0x1012db23  lea     eax, [ebp+pSP]
0x1012db26  push    eax
0x1012db27  push    offset _IID_IServiceProvider
0x1012db2c  push    pSite
0x1012db2d  mov     pSite, esi; this
0x1012db2f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db35  call    esi
0x1012db37  test    eax, eax
0x1012db39  js      short loc_1012DAE7
0x1012db3b  mov     pSite, [ebp+pSP]
0x1012db3e  mov     eax, [pSite]
0x1012db40  mov     esi, [eax+0Ch]
0x1012db43  lea     eax, [ebp+pXmlDoc]
0x1012db46  push    eax
0x1012db47  push    offset _IID_IXMLDOMDocument
0x1012db4c  push    offset _IID_IInternetHostSecurityManager
0x1012db51  push    pSite
0x1012db52  mov     pSite, esi; this
0x1012db54  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db5a  call    esi
0x1012db5c  test    eax, eax
0x1012db5e  jns     loc_1012DA82
0x1012db64  mov     pSite, [ebp+pSP]
0x1012db67  mov     eax, [pSite]
0x1012db69  mov     esi, [eax+0Ch]
0x1012db6c  lea     eax, [ebp+pHtmlDoc]
0x1012db6f  push    eax
0x1012db70  push    offset _IID_IHTMLDocument2
0x1012db75  push    offset _SID_SContainerDispatch
0x1012db7a  push    pSite
0x1012db7b  mov     pSite, esi; this
0x1012db7d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012db83  call    esi
0x1012db85  test    eax, eax
0x1012db87  jns     short loc_1012DBB2
0x1012db89  mov     pSite, [ebp+pSP]
0x1012db8c  mov     eax, [pSite]
0x1012db8e  mov     esi, [eax+0Ch]
0x1012db91  lea     eax, [ebp+pHtmlDoc]
0x1012db94  push    eax
0x1012db95  push    offset _IID_IHTMLDocument2
0x1012db9a  push    offset _IID_IInternetHostSecurityManager
0x1012db9f  push    pSite
0x1012dba0  mov     pSite, esi; this
0x1012dba2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dba8  call    esi
0x1012dbaa  test    eax, eax
0x1012dbac  js      loc_1012DAE7
0x1012dbb2  mov     pSite, [ebp+pHtmlDoc]
0x1012dbb5  mov     eax, [pSite]
0x1012dbb7  mov     esi, [eax+0A0h]
0x1012dbbd  jmp     loc_1012DA8D
0x1012dbc2  mov     pSite, [ebp+pDocURL]; c
0x1012dbc5  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x1012dbca  mov     ebx, eax
0x1012dbcc  lea     pSite, [ebp+pResult]; ppref
0x1012dbcf  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dbd4  mov     [ebp+pResult._p], ebx
0x1012dbd7  jmp     loc_1012DAE7
0x1012dbdc  mov     pSite, [ebp+ms_exc.exc_ptr]; ep
0x1012dbdf  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1012dbe4  retn
0x1012dbe5  mov     esp, [ebp+ms_exc.old_esp]
0x1012dbe8  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1012dbed  mov     ebx, [ebp+pResult._p]
0x1012dbf0  test    ebx, ebx
0x1012dbf2  jz      short loc_1012DC01
0x1012dbf4  xor     edx, edx; pref
0x1012dbf6  lea     pSite, [ebp+pResult]; ppref
0x1012dbf9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1012dbfe  mov     ebx, [ebp+pResult._p]
0x1012dc01  mov     pSite, __tls_index
0x1012dc07  mov     eax, large fs:2Ch
0x1012dc0d  mov     eax, [eax+pSite*4]
0x1012dc10  mov     eax, [eax+4]
0x1012dc16  mov     eax, [eax+8]
0x1012dc19  mov     [ebp+var_40], eax
0x1012dc1c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1012dc23  xor     edi, edi
0x1012dc25  mov     pSite, [ebp+pClientSite]
0x1012dc28  test    pSite, pSite
0x1012dc2a  jz      short loc_1012DC3F
0x1012dc2c  mov     eax, [pSite]
0x1012dc2e  push    pSite
0x1012dc2f  mov     esi, [eax+8]
0x1012dc32  mov     pSite, esi; this
0x1012dc34  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dc3a  call    esi
0x1012dc3c  mov     [ebp+pClientSite], edi
0x1012dc3f  mov     pSite, [ebp+pMk]
0x1012dc42  test    pSite, pSite
0x1012dc44  jz      short loc_1012DC59
0x1012dc46  mov     eax, [pSite]
0x1012dc48  push    pSite
0x1012dc49  mov     esi, [eax+8]
0x1012dc4c  mov     pSite, esi; this
0x1012dc4e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dc54  call    esi
0x1012dc56  mov     [ebp+pMk], edi
0x1012dc59  mov     pSite, [ebp+pSP]
0x1012dc5c  test    pSite, pSite
0x1012dc5e  jz      short loc_1012DC73
0x1012dc60  mov     eax, [pSite]
0x1012dc62  push    pSite
0x1012dc63  mov     esi, [eax+8]
0x1012dc66  mov     pSite, esi; this
0x1012dc68  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dc6e  call    esi
0x1012dc70  mov     [ebp+pSP], edi
0x1012dc73  mov     pSite, [ebp+pHtmlDoc]
0x1012dc76  test    pSite, pSite
0x1012dc78  jz      short loc_1012DC8D
0x1012dc7a  mov     eax, [pSite]
0x1012dc7c  push    pSite
0x1012dc7d  mov     esi, [eax+8]
0x1012dc80  mov     pSite, esi; this
0x1012dc82  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dc88  call    esi
0x1012dc8a  mov     [ebp+pHtmlDoc], edi
0x1012dc8d  mov     pSite, [ebp+pXmlDoc]
0x1012dc90  test    pSite, pSite
0x1012dc92  jz      short loc_1012DCA7
0x1012dc94  mov     eax, [pSite]
0x1012dc96  push    pSite
0x1012dc97  mov     esi, [eax+8]
0x1012dc9a  mov     pSite, esi; this
0x1012dc9c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dca2  call    esi
0x1012dca4  mov     [ebp+pXmlDoc], edi
0x1012dca7  push    [ebp+pOleStr]; pv
0x1012dcaa  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1012dcb0  push    [ebp+pDocURL]; bstrString
0x1012dcb3  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1012dcb9  mov     eax, [ebp+var_40]
0x1012dcbc  test    eax, eax
0x1012dcbe  jnz     short loc_1012DCE4
0x1012dcc0  mov     [ebp+pResult._p], edi
0x1012dcc3  lea     pSite, [ebp+pResult]; ppref
0x1012dcc6  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dccb  mov     eax, ebx
0x1012dccd  mov     pSite, [ebp+ms_exc.registration.Next]
0x1012dcd0  mov     large fs:0, pSite
0x1012dcd7  pop     pSite
0x1012dcd8  pop     edi
0x1012dcd9  pop     esi
0x1012dcda  pop     ebx
0x1012dcdb  leave
0x1012dcdc  retn
0x1012dcdd  mov     pSite, eax; hr
0x1012dcdf  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x1012dce4  mov     pSite, eax; this
0x1012dce6  call    ?throwThis@Exception@@QAEXXZ; Exception::throwThis(void)
```
