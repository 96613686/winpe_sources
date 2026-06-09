# ScriptEngine::New(Atom *,_GUID,bool,ScriptEngine * *)

- ea: `0x1801212bc`
- end: `0x180121457`
- name: `?New@ScriptEngine@@SAXPEAVAtom@@U_GUID@@_NPEAPEAV1@@Z`
- size: `411`
- prototype: `void __fastcall(ICatInformation **funcNamespace, _GUID *clsid, bool fSecure, ScriptEngine **pp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c80e4`

## callees

- `0x180034244`
- `0x18003617c`
- `0x1800966f8`
- `0x1800bc3b0`
- `0x1800c4e60`
- `0x1800d4ff0`
- `0x1800dddf8`
- `0x1801212bc`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801213de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801213de`
- `urlmon!CompatFlagsFromClsid` at `0x18012134a`
- `urlmon!CompatFlagsFromClsid` at `0x18012134a`

## pseudocode

```c
void __fastcall ScriptEngine::New(ICatInformation **funcNamespace, _GUID *clsid, bool fSecure, ScriptEngine **pp)
{
  HRESULT v8; // eax
  DispatchFunctions *v9; // rax
  CLSID v10; // xmm6
  ScriptEngine *v11; // rbx
  int Instance; // edi
  unsigned int dwCompat; // [rsp+40h] [rbp-48h] BYREF
  DWORD dwMiscStatus[3]; // [rsp+44h] [rbp-44h] BYREF

  if ( !CreateCatalogInformation(funcNamespace)
    && g_pCatInfo->IsClassOfCategories(g_pCatInfo, clsid, 1u, &CATID_ActiveScriptParse, 0, 0) )
  {
    Exception::throwHR(-2147467262);
  }
  if ( fSecure )
  {
    dwCompat = 0;
    dwMiscStatus[0] = 0;
    v8 = CompatFlagsFromClsid(clsid, &dwCompat, dwMiscStatus);
    succeeded(v8);
    if ( (dwCompat & 0x400) != 0 )
    {
      XUtility::storeError(-1072897220, 0, 0, 0);
      Exception::throwStored();
      __debugbreak();
    }
  }
  v9 = (DispatchFunctions *)_MemAlloc(0x68u, 4u);
  v10 = *clsid;
  v11 = (ScriptEngine *)v9;
  DispatchFunctions::DispatchFunctions(v9, 0, (Atom *)funcNamespace);
  v11->DispatchFunctions::ExtensionFunctions::xobject<Object,&IID_IUnknown>::xunknown<Object,&IID_IUnknown>::Object::IUnknown::__vftable = (ScriptEngine_vtbl *)ObjectParam::`vftable'{for `Object'};
  v11->DispatchFunctions::ExtensionFunctions::xobject<Object,&IID_IUnknown>::xunknown<Object,&IID_IUnknown>::_xunknown::__vftable = (_xunknown_vtbl *)ScriptEngine::`vftable'{for `_xunknown'};
  v11->_as._p = 0;
  v11->_asp._p = 0;
  v11->_clsid = v10;
  Instance = CoCreateInstance(clsid, 0, 1u, &IID_IActiveScript, (LPVOID *)&v11->_as._p);
  if ( Instance < 0
    || (Instance = v11->_as._p->QueryInterface(v11->_as._p, &IID_IActiveScriptParse64, (void **)&v11->_asp._p),
        Instance < 0)
    || (Instance = v11->_asp._p->InitNew(v11->_asp._p), Instance < 0) )
  {
    v11->Release(v11);
    *pp = 0;
    Exception::throwHR(Instance);
  }
  *pp = v11;
}

```

## disassembly

```asm
0x1801212bc  mov     [rsp+arg_10], rbx
0x1801212c1  push    rbp
0x1801212c2  push    rsi
0x1801212c3  push    rdi
0x1801212c4  push    r14
0x1801212c6  push    r15
0x1801212c8  sub     rsp, 60h
0x1801212cc  movaps  [rsp+88h+var_38], xmm6
0x1801212d1  mov     rsi, pp
0x1801212d4  mov     bl, fSecure
0x1801212d7  mov     rdi, clsid
0x1801212da  mov     rbp, funcNamespace
0x1801212dd  call    ?CreateCatalogInformation@@YAJPEAPEAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x1801212e2  test    eax, eax
0x1801212e4  jnz     short loc_180121329
0x1801212e6  mov     funcNamespace, cs:?g_pCatInfo@@3PEAUICatInformation@@EA; ICatInformation * g_pCatInfo
0x1801212ed  lea     pp, CATID_ActiveScriptParse
0x1801212f4  mov     [rsp+88h+var_60], 0
0x1801212fd  mov     r8d, 1
0x180121303  mov     clsid, rdi
0x180121306  mov     dword ptr [rsp+88h+ppv], 0
0x18012130e  mov     rax, [funcNamespace]
0x180121311  mov     rax, [rax+30h]
0x180121315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012131a  test    eax, eax
0x18012131c  jz      short loc_180121329
0x18012131e  mov     ecx, 80004002h; hr
0x180121323  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180121329  test    bl, bl
0x18012132b  jz      short loc_180121379
0x18012132d  lea     r8, [rsp+88h+dwMiscStatus]; pdwMiscStatusFlags
0x180121332  mov     [rsp+88h+dwCompat], 0
0x18012133a  lea     clsid, [rsp+88h+dwCompat]; pdwCompatFlags
0x18012133f  mov     [rsp+88h+dwMiscStatus], 0
0x180121347  mov     funcNamespace, rdi; pclsid
0x18012134a  call    cs:__imp_CompatFlagsFromClsid
0x180121350  mov     ecx, eax; hr
0x180121352  call    ?succeeded@@YAJJ@Z; succeeded(long)
0x180121357  test    [rsp+88h+dwCompat], 400h
0x18012135f  jz      short loc_180121379
0x180121361  xor     r9d, r9d; o3
0x180121364  xor     r8d, r8d; o2
0x180121367  xor     edx, edx; o1
0x180121369  mov     ecx, 0C00CE33Ch; resid
0x18012136e  call    ?storeError@XUtility@@SAXJPEAVObject@@00@Z; XUtility::storeError(long,Object *,Object *,Object *)
0x180121373  call    ?throwStored@Exception@@SAXXZ; Exception::throwStored(void)
0x180121378  int     3; Trap to Debugger
0x180121379  mov     edx, 4; dwFlags
0x18012137e  lea     ecx, [clsid+64h]; cb
0x180121381  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180121386  movaps  xmm6, xmmword ptr [rdi]
0x180121389  mov     r8, rbp; funcNamespace
0x18012138c  xor     edx, edx; host
0x18012138e  mov     funcNamespace, rax; this
0x180121391  mov     rbx, rax
0x180121394  call    ??0DispatchFunctions@@IEAA@PEAVExecutionHost@@PEAVAtom@@@Z; DispatchFunctions::DispatchFunctions(ExecutionHost *,Atom *)
0x180121399  lea     rax, ??_7ObjectParam@@6BObject@@@; const ObjectParam::`vftable'{for `Object'}
0x1801213a0  xor     edx, edx; pUnkOuter
0x1801213a2  mov     [rbx], rax
0x1801213a5  lea     r15, [rbx+48h]
0x1801213a9  lea     rax, ??_7ScriptEngine@@6B_xunknown@@@; const ScriptEngine::`vftable'{for `_xunknown'}
0x1801213b0  mov     [rsp+88h+ppv], r15; ppv
0x1801213b5  mov     [rbx+8], rax
0x1801213b9  lea     r14, [rbx+50h]
0x1801213bd  mov     qword ptr [r15], 0
0x1801213c4  lea     pp, IID_IActiveScript; riid
0x1801213cb  mov     qword ptr [r14], 0
0x1801213d2  lea     r8d, [clsid+1]; dwClsContext
0x1801213d6  mov     funcNamespace, rdi; rclsid
0x1801213d9  movdqu  xmmword ptr [rbx+58h], xmm6
0x1801213de  call    cs:__imp_CoCreateInstance
0x1801213e4  mov     edi, eax
0x1801213e6  test    eax, eax
0x1801213e8  js      short loc_180121439
0x1801213ea  mov     funcNamespace, [r15]
0x1801213ed  lea     clsid, IID_IActiveScriptParse64
0x1801213f4  mov     r8, r14
0x1801213f7  mov     rax, [funcNamespace]
0x1801213fa  mov     rax, [rax]
0x1801213fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121402  mov     edi, eax
0x180121404  test    eax, eax
0x180121406  js      short loc_180121439
0x180121408  mov     funcNamespace, [r14]
0x18012140b  mov     rax, [funcNamespace]
0x18012140e  mov     rax, [rax+18h]
0x180121412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121417  mov     edi, eax
0x180121419  test    eax, eax
0x18012141b  js      short loc_180121439
0x18012141d  movaps  xmm6, [rsp+88h+var_38]
0x180121422  mov     [rsi], rbx
0x180121425  mov     rbx, [rsp+88h+arg_10]
0x18012142d  add     rsp, 60h
0x180121431  pop     r15
0x180121433  pop     r14
0x180121435  pop     rdi
0x180121436  pop     rsi
0x180121437  pop     rbp
0x180121438  retn
0x180121439  mov     rax, [rbx]
0x18012143c  mov     funcNamespace, rbx
0x18012143f  mov     rax, [rax+10h]
0x180121443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121448  mov     ecx, edi; hr
0x18012144a  mov     qword ptr [rsi], 0
0x180121451  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
```
