# ScriptEngine::New(Atom *,_GUID,bool,ScriptEngine * *)

- ea: `0x100e9ca8`
- end: `0x100e9e1a`
- name: `?New@ScriptEngine@@SGXPAVAtom@@U_GUID@@_NPAPAV1@@Z`
- size: `370`
- prototype: `void __userpurge(Atom *funcNamespace@<ecx>, _GUID clsid, bool fSecure@<dl>, ScriptEngine **pp)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x100e4175`

## callees

- `0x1003f4b8`
- `0x1006483c`
- `0x10064c40`
- `0x10064c51`
- `0x10064e17`
- `0x10067b20`
- `0x1006b470`
- `0x1007618e`
- `0x1008d578`
- `0x100e9ca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100e9d9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x100e9d9e`
- `urlmon!CompatFlagsFromClsid` at `0x100e9d24`
- `urlmon!CompatFlagsFromClsid` at `0x100e9d24`

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
    v4 = (ScriptEngine *)_MemAlloc(0x40u, 4u);
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
0x100e9ca8  mov     edi, edi
0x100e9caa  push    ebp
0x100e9cab  mov     ebp, esp
0x100e9cad  sub     esp, 34h
0x100e9cb0  mov     eax, ___security_cookie
0x100e9cb5  xor     eax, ebp
0x100e9cb7  mov     [ebp+var_4], eax
0x100e9cba  mov     eax, [ebp+pp]
0x100e9cbd  push    ebx
0x100e9cbe  push    esi
0x100e9cbf  push    edi; ppUnk
0x100e9cc0  lea     esi, [ebp+arg_0]
0x100e9cc3  mov     [ebp+var_24], funcNamespace
0x100e9cc6  lea     edi, [ebp+clsid]
0x100e9cc9  mov     [ebp+var_1C], eax
0x100e9ccc  movsd
0x100e9ccd  mov     bl, fSecure
0x100e9ccf  movsd
0x100e9cd0  movsd
0x100e9cd1  movsd
0x100e9cd2  call    ?CreateCatalogInformation@@YGJPAPAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x100e9cd7  xor     edi, edi
0x100e9cd9  test    eax, eax
0x100e9cdb  jnz     short loc_100E9D0E
0x100e9cdd  mov     funcNamespace, ?g_pCatInfo@@3PAUICatInformation@@A; ICatInformation * g_pCatInfo
0x100e9ce3  push    edi
0x100e9ce4  push    edi
0x100e9ce5  push    offset _CATID_ActiveScriptParse
0x100e9cea  mov     eax, [funcNamespace]
0x100e9cec  push    1
0x100e9cee  mov     esi, [eax+18h]
0x100e9cf1  lea     eax, [ebp+clsid]
0x100e9cf4  push    eax
0x100e9cf5  push    funcNamespace
0x100e9cf6  mov     funcNamespace, esi; this
0x100e9cf8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9cfe  call    esi
0x100e9d00  test    eax, eax
0x100e9d02  jz      short loc_100E9D0E
0x100e9d04  mov     funcNamespace, 80004002h; hr
0x100e9d09  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x100e9d0e  test    bl, bl
0x100e9d10  jz      short loc_100E9D4D
0x100e9d12  lea     eax, [ebp+dwMiscStatus]
0x100e9d15  mov     [ebp+dwCompat], edi
0x100e9d18  push    eax; pdwMiscStatusFlags
0x100e9d19  lea     eax, [ebp+dwCompat]
0x100e9d1c  mov     [ebp+dwMiscStatus], edi
0x100e9d1f  push    eax; pdwCompatFlags
0x100e9d20  lea     eax, [ebp+clsid]
0x100e9d23  push    eax; pclsid
0x100e9d24  call    ds:__imp__CompatFlagsFromClsid@12; CompatFlagsFromClsid(x,x,x)
0x100e9d2a  mov     funcNamespace, eax; hr
0x100e9d2c  call    ?succeeded@@YGJJ@Z; succeeded(long)
0x100e9d31  test    [ebp+dwCompat], 400h
0x100e9d38  jz      short loc_100E9D4D
0x100e9d3a  push    edi; o3
0x100e9d3b  push    edi; o2
0x100e9d3c  xor     edx, edx; o1
0x100e9d3e  mov     funcNamespace, 0C00CE33Ch; resid
0x100e9d43  call    ?storeError@XUtility@@SGXJPAVObject@@00@Z; XUtility::storeError(long,Object *,Object *,Object *)
0x100e9d48  call    ?throwStored@Exception@@SGXXZ; Exception::throwStored(void)
0x100e9d4d  push    4
0x100e9d4f  pop     edx; dwFlags
0x100e9d50  push    40h ; '@'
0x100e9d52  pop     funcNamespace; cb
0x100e9d53  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x100e9d58  push    [ebp+var_24]; funcNamespace
0x100e9d5b  lea     esi, [ebp+clsid]
0x100e9d5e  mov     ebx, eax
0x100e9d60  lea     edi, [ebp+var_34]
0x100e9d63  mov     funcNamespace, ebx; this
0x100e9d65  movsd
0x100e9d66  push    0; host
0x100e9d68  movsd
0x100e9d69  movsd
0x100e9d6a  movsd
0x100e9d6b  call    ??0DispatchFunctions@@IAE@PAVExecutionHost@@PAVAtom@@@Z; DispatchFunctions::DispatchFunctions(ExecutionHost *,Atom *)
0x100e9d70  xor     funcNamespace, funcNamespace
0x100e9d72  mov     dword ptr [ebx], offset ??_7ObjectParam@@6BObject@@@; const ObjectParam::`vftable'{for `Object'}
0x100e9d78  lea     eax, [ebx+28h]
0x100e9d7b  mov     dword ptr [ebx+4], offset ??_7ScriptEngine@@6B_xunknown@@@; const ScriptEngine::`vftable'{for `_xunknown'}
0x100e9d82  mov     [eax], funcNamespace
0x100e9d84  lea     edi, [ebx+30h]
0x100e9d87  mov     [ebx+2Ch], funcNamespace
0x100e9d8a  lea     esi, [ebp+var_34]
0x100e9d8d  movsd
0x100e9d8e  push    eax; ppv
0x100e9d8f  push    offset _IID_IActiveScript; riid
0x100e9d94  push    1; dwClsContext
0x100e9d96  movsd
0x100e9d97  lea     eax, [ebp+clsid]
0x100e9d9a  push    funcNamespace; pUnkOuter
0x100e9d9b  push    eax; rclsid
0x100e9d9c  movsd
0x100e9d9d  movsd
0x100e9d9e  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x100e9da4  mov     edi, eax
0x100e9da6  test    edi, edi
0x100e9da8  js      short loc_100E9DFA
0x100e9daa  mov     funcNamespace, [ebx+28h]
0x100e9dad  mov     eax, [funcNamespace]
0x100e9daf  mov     esi, [eax]
0x100e9db1  lea     eax, [ebx+2Ch]
0x100e9db4  push    eax
0x100e9db5  push    offset _IID_IActiveScriptParse32
0x100e9dba  push    funcNamespace
0x100e9dbb  mov     funcNamespace, esi; this
0x100e9dbd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9dc3  call    esi
0x100e9dc5  mov     edi, eax
0x100e9dc7  test    edi, edi
0x100e9dc9  js      short loc_100E9DFA
0x100e9dcb  mov     eax, [ebx+2Ch]
0x100e9dce  push    eax
0x100e9dcf  mov     funcNamespace, [eax]
0x100e9dd1  mov     esi, [funcNamespace+0Ch]
0x100e9dd4  mov     funcNamespace, esi; this
0x100e9dd6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9ddc  call    esi
0x100e9dde  mov     edi, eax
0x100e9de0  test    edi, edi
0x100e9de2  js      short loc_100E9DFA
0x100e9de4  mov     eax, [ebp+var_1C]
0x100e9de7  mov     funcNamespace, [ebp+var_4]
0x100e9dea  pop     edi
0x100e9deb  pop     esi
0x100e9dec  mov     [eax], ebx
0x100e9dee  xor     funcNamespace, ebp; cookie
0x100e9df0  pop     ebx
0x100e9df1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100e9df6  leave
0x100e9df7  retn    14h
0x100e9dfa  mov     eax, [ebx]
0x100e9dfc  push    ebx
0x100e9dfd  mov     esi, [eax+8]
0x100e9e00  mov     funcNamespace, esi; this
0x100e9e02  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e9e08  call    esi
0x100e9e0a  mov     eax, [ebp+var_1C]
0x100e9e0d  mov     funcNamespace, edi
0x100e9e0f  mov     dword ptr [eax], 0
0x100e9e15  jmp     loc_100E9D09
```
