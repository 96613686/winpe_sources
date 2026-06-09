# ScriptEngine::New(Atom *,_GUID,bool,ScriptEngine * *)

- ea: `0x100e9b88`
- end: `0x100e9cfa`
- name: `?New@ScriptEngine@@SGXPAVAtom@@U_GUID@@_NPAPAV1@@Z`
- size: `370`
- prototype: `void __userpurge(Atom *funcNamespace@<ecx>, _GUID clsid, bool fSecure@<dl>, ScriptEngine **pp)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x100e4055`

## callees

- `0x1003f548`
- `0x100648dc`
- `0x10064ce0`
- `0x10064cf1`
- `0x10064eb7`
- `0x10067bc0`
- `0x1006b510`
- `0x1007615e`
- `0x1008d538`
- `0x100e9b88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100e9c7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100e9c7e`
- `urlmon!CompatFlagsFromClsid` at `0x100e9c04`
- `urlmon!CompatFlagsFromClsid` at `0x100e9c04`

## pseudocode

```c
void __fastcall ScriptEngine::New(Atom *funcNamespace, bool fSecure, _GUID clsid, ScriptEngine **pp)
{
  ScriptEngine *v4; // ebx
  Object *v5; // edi
  HRESULT v6; // ecx
  HRESULT v7; // eax
  ICatInformation **v8; // [esp+0h] [ebp-40h]
  _GUID v9; // [esp+Ch] [ebp-34h]
  unsigned int dwMiscStatus; // [esp+20h] [ebp-20h] BYREF
  ScriptEngine **v12; // [esp+24h] [ebp-1Ch]
  unsigned int dwCompat; // [esp+28h] [ebp-18h] BYREF
  _GUID clsida; // [esp+2Ch] [ebp-14h] BYREF

  v12 = pp;
  clsida = clsid;
  LOBYTE(v4) = fSecure;
  v5 = 0;
  if ( CreateCatalogInformation(v8)
    || !((int (__thiscall *)(HRESULT (__stdcall *)(ICatInformation *, const _GUID *, unsigned int, const _GUID *, unsigned int, const _GUID *), ICatInformation *, _GUID *, int, _GUID *, _DWORD, _DWORD))g_pCatInfo->IsClassOfCategories)(
          g_pCatInfo->IsClassOfCategories,
          g_pCatInfo,
          &clsida,
          1,
          &CATID_ActiveScriptParse,
          0,
          0) )
  {
    goto LABEL_5;
  }
  v6 = -2147467262;
  while ( 1 )
  {
    Exception::throwHR(v6);
LABEL_5:
    if ( (_BYTE)v4 )
    {
      dwCompat = (unsigned int)v5;
      dwMiscStatus = (unsigned int)v5;
      v7 = CompatFlagsFromClsid(&clsida, &dwCompat, &dwMiscStatus);
      succeeded(v7);
      if ( (dwCompat & 0x400) != 0 )
      {
        XUtility::storeError(-1072897220, 0, v5, v5);
        Exception::throwStored();
      }
    }
    v4 = (ScriptEngine *)_MemAlloc(0x40u, 4);
    v9 = clsida;
    DispatchFunctions::DispatchFunctions(v4, 0, funcNamespace);
    v4->DispatchFunctions::ExtensionFunctions::xobject<Object,&IID_IUnknown>::xunknown<Object,&IID_IUnknown>::Object::IUnknown::__vftable = (ScriptEngine_vtbl *)ObjectParam::`vftable'{for `Object'};
    v4->DispatchFunctions::ExtensionFunctions::xobject<Object,&IID_IUnknown>::xunknown<Object,&IID_IUnknown>::_xunknown::__vftable = (_xunknown_vtbl *)ScriptEngine::`vftable'{for `_xunknown'};
    v4->_as._p = 0;
    v4->_asp._p = 0;
    v4->_clsid = v9;
    v5 = (Object *)CoCreateInstance(&clsida, 0, 1u, &IID_IActiveScript, (LPVOID *)&v4->_as._p);
    if ( (int)v5 >= 0 )
    {
      v5 = (Object *)((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IActiveScript *, GUID *, _reference<IActiveScriptParse32> *))v4->_as._p->QueryInterface)(
                       v4->_as._p->QueryInterface,
                       v4->_as._p,
                       &IID_IActiveScriptParse32,
                       &v4->_asp);
      if ( (int)v5 >= 0 )
      {
        v5 = (Object *)((int (__thiscall *)(HRESULT (__stdcall *)(IActiveScriptParse32 *), IActiveScriptParse32 *))v4->_asp._p->InitNew)(
                         v4->_asp._p->InitNew,
                         v4->_asp._p);
        if ( (int)v5 >= 0 )
          break;
      }
    }
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ScriptEngine *))v4->Release)(v4->Release, v4);
    v6 = (HRESULT)v5;
    *v12 = 0;
  }
  *v12 = v4;
}

```

## disassembly

```asm
0x100e9b88  mov     edi, edi
0x100e9b8a  push    ebp
0x100e9b8b  mov     ebp, esp
0x100e9b8d  sub     esp, 34h
0x100e9b90  mov     eax, ___security_cookie
0x100e9b95  xor     eax, ebp
0x100e9b97  mov     [ebp+var_4], eax
0x100e9b9a  mov     eax, [ebp+pp]
0x100e9b9d  push    ebx
0x100e9b9e  push    esi
0x100e9b9f  push    edi; ppUnk
0x100e9ba0  lea     esi, [ebp+arg_0]
0x100e9ba3  mov     [ebp+var_24], funcNamespace
0x100e9ba6  lea     edi, [ebp+clsid]
0x100e9ba9  mov     [ebp+var_1C], eax
0x100e9bac  movsd
0x100e9bad  mov     bl, fSecure
0x100e9baf  movsd
0x100e9bb0  movsd
0x100e9bb1  movsd
0x100e9bb2  call    ?CreateCatalogInformation@@YGJPAPAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x100e9bb7  xor     edi, edi
0x100e9bb9  test    eax, eax
0x100e9bbb  jnz     short loc_100E9BEE
0x100e9bbd  mov     funcNamespace, ?g_pCatInfo@@3PAUICatInformation@@A; ICatInformation * g_pCatInfo
0x100e9bc3  push    edi
0x100e9bc4  push    edi
0x100e9bc5  push    offset _CATID_ActiveScriptParse
0x100e9bca  mov     eax, [funcNamespace]
0x100e9bcc  push    1
0x100e9bce  mov     esi, [eax+18h]
0x100e9bd1  lea     eax, [ebp+clsid]
0x100e9bd4  push    eax
0x100e9bd5  push    funcNamespace
0x100e9bd6  mov     funcNamespace, esi; this
0x100e9bd8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9bde  call    esi
0x100e9be0  test    eax, eax
0x100e9be2  jz      short loc_100E9BEE
0x100e9be4  mov     funcNamespace, 80004002h; hr
0x100e9be9  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x100e9bee  test    bl, bl
0x100e9bf0  jz      short loc_100E9C2D
0x100e9bf2  lea     eax, [ebp+dwMiscStatus]
0x100e9bf5  mov     [ebp+dwCompat], edi
0x100e9bf8  push    eax; pdwMiscStatusFlags
0x100e9bf9  lea     eax, [ebp+dwCompat]
0x100e9bfc  mov     [ebp+dwMiscStatus], edi
0x100e9bff  push    eax; pdwCompatFlags
0x100e9c00  lea     eax, [ebp+clsid]
0x100e9c03  push    eax; pclsid
0x100e9c04  call    ds:__imp__CompatFlagsFromClsid@12; CompatFlagsFromClsid(x,x,x)
0x100e9c0a  mov     funcNamespace, eax; hr
0x100e9c0c  call    ?succeeded@@YGJJ@Z; succeeded(long)
0x100e9c11  test    [ebp+dwCompat], 400h
0x100e9c18  jz      short loc_100E9C2D
0x100e9c1a  push    edi; o3
0x100e9c1b  push    edi; o2
0x100e9c1c  xor     edx, edx; o1
0x100e9c1e  mov     funcNamespace, 0C00CE33Ch; resid
0x100e9c23  call    ?storeError@XUtility@@SGXJPAVObject@@00@Z; XUtility::storeError(long,Object *,Object *,Object *)
0x100e9c28  call    ?throwStored@Exception@@SGXXZ; Exception::throwStored(void)
0x100e9c2d  push    4
0x100e9c2f  pop     edx; dwFlags
0x100e9c30  push    40h ; '@'
0x100e9c32  pop     funcNamespace; cb
0x100e9c33  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x100e9c38  push    [ebp+var_24]; funcNamespace
0x100e9c3b  lea     esi, [ebp+clsid]
0x100e9c3e  mov     ebx, eax
0x100e9c40  lea     edi, [ebp+var_34]
0x100e9c43  mov     funcNamespace, ebx; this
0x100e9c45  movsd
0x100e9c46  push    0; host
0x100e9c48  movsd
0x100e9c49  movsd
0x100e9c4a  movsd
0x100e9c4b  call    ??0DispatchFunctions@@IAE@PAVExecutionHost@@PAVAtom@@@Z; DispatchFunctions::DispatchFunctions(ExecutionHost *,Atom *)
0x100e9c50  xor     funcNamespace, funcNamespace
0x100e9c52  mov     dword ptr [ebx], offset ??_7ObjectParam@@6BObject@@@; const ObjectParam::`vftable'{for `Object'}
0x100e9c58  lea     eax, [ebx+28h]
0x100e9c5b  mov     dword ptr [ebx+4], offset ??_7ScriptEngine@@6B_xunknown@@@; const ScriptEngine::`vftable'{for `_xunknown'}
0x100e9c62  mov     [eax], funcNamespace
0x100e9c64  lea     edi, [ebx+30h]
0x100e9c67  mov     [ebx+2Ch], funcNamespace
0x100e9c6a  lea     esi, [ebp+var_34]
0x100e9c6d  movsd
0x100e9c6e  push    eax; ppv
0x100e9c6f  push    offset _IID_IActiveScript; riid
0x100e9c74  push    1; dwClsContext
0x100e9c76  movsd
0x100e9c77  lea     eax, [ebp+clsid]
0x100e9c7a  push    funcNamespace; pUnkOuter
0x100e9c7b  push    eax; rclsid
0x100e9c7c  movsd
0x100e9c7d  movsd
0x100e9c7e  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100e9c84  mov     edi, eax
0x100e9c86  test    edi, edi
0x100e9c88  js      short loc_100E9CDA
0x100e9c8a  mov     funcNamespace, [ebx+28h]
0x100e9c8d  mov     eax, [funcNamespace]
0x100e9c8f  mov     esi, [eax]
0x100e9c91  lea     eax, [ebx+2Ch]
0x100e9c94  push    eax
0x100e9c95  push    offset _IID_IActiveScriptParse32
0x100e9c9a  push    funcNamespace
0x100e9c9b  mov     funcNamespace, esi; this
0x100e9c9d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9ca3  call    esi
0x100e9ca5  mov     edi, eax
0x100e9ca7  test    edi, edi
0x100e9ca9  js      short loc_100E9CDA
0x100e9cab  mov     eax, [ebx+2Ch]
0x100e9cae  push    eax
0x100e9caf  mov     funcNamespace, [eax]
0x100e9cb1  mov     esi, [funcNamespace+0Ch]
0x100e9cb4  mov     funcNamespace, esi; this
0x100e9cb6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9cbc  call    esi
0x100e9cbe  mov     edi, eax
0x100e9cc0  test    edi, edi
0x100e9cc2  js      short loc_100E9CDA
0x100e9cc4  mov     eax, [ebp+var_1C]
0x100e9cc7  mov     funcNamespace, [ebp+var_4]
0x100e9cca  pop     edi
0x100e9ccb  pop     esi
0x100e9ccc  mov     [eax], ebx
0x100e9cce  xor     funcNamespace, ebp; cookie
0x100e9cd0  pop     ebx
0x100e9cd1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100e9cd6  leave
0x100e9cd7  retn    14h
0x100e9cda  mov     eax, [ebx]
0x100e9cdc  push    ebx
0x100e9cdd  mov     esi, [eax+8]
0x100e9ce0  mov     funcNamespace, esi; this
0x100e9ce2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9ce8  call    esi
0x100e9cea  mov     eax, [ebp+var_1C]
0x100e9ced  mov     funcNamespace, edi
0x100e9cef  mov     dword ptr [eax], 0
0x100e9cf5  jmp     loc_100E9BE9
```
