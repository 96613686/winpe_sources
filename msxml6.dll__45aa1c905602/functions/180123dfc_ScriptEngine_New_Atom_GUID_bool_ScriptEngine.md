# ScriptEngine::New(Atom *,_GUID,bool,ScriptEngine * *)

- ea: `0x180123dfc`
- end: `0x180123fa4`
- name: `?New@ScriptEngine@@SAXPEAVAtom@@U_GUID@@_NPEAPEAV1@@Z`
- size: `424`
- prototype: `void __fastcall(Atom *funcNamespace, _GUID clsid, bool fSecure, ScriptEngine **pp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c99cc`

## callees

- `0x18000e120`
- `0x1800101e4`
- `0x180096fb8`
- `0x1800bda08`
- `0x1800c6594`
- `0x1800d6c90`
- `0x1800dfe18`
- `0x180123dfc`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180123f24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180123f24`
- `urlmon!CompatFlagsFromClsid` at `0x180123e8a`
- `urlmon!CompatFlagsFromClsid` at `0x180123e8a`

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
0x180123dfc  mov     [rsp+arg_10], rbx
0x180123e01  push    rbp
0x180123e02  push    rsi
0x180123e03  push    rdi
0x180123e04  push    r14
0x180123e06  push    r15
0x180123e08  sub     rsp, 60h
0x180123e0c  movaps  [rsp+88h+var_38], xmm6
0x180123e11  mov     rsi, pp
0x180123e14  mov     bl, fSecure
0x180123e17  mov     rdi, clsid
0x180123e1a  mov     rbp, funcNamespace
0x180123e1d  call    ?CreateCatalogInformation@@YAJPEAPEAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x180123e22  test    eax, eax
0x180123e24  jnz     short loc_180123E69
0x180123e26  mov     funcNamespace, cs:?g_pCatInfo@@3PEAUICatInformation@@EA; ICatInformation * g_pCatInfo
0x180123e2d  lea     pp, CATID_ActiveScriptParse
0x180123e34  mov     [rsp+88h+var_60], 0
0x180123e3d  mov     r8d, 1
0x180123e43  mov     clsid, rdi
0x180123e46  mov     dword ptr [rsp+88h+ppv], 0
0x180123e4e  mov     rax, [funcNamespace]
0x180123e51  mov     rax, [rax+30h]
0x180123e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123e5a  test    eax, eax
0x180123e5c  jz      short loc_180123E69
0x180123e5e  mov     ecx, 80004002h; hr
0x180123e63  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180123e69  test    bl, bl
0x180123e6b  jz      short loc_180123EBF
0x180123e6d  lea     r8, [rsp+88h+dwMiscStatus]; pdwMiscStatusFlags
0x180123e72  mov     [rsp+88h+dwCompat], 0
0x180123e7a  lea     clsid, [rsp+88h+dwCompat]; pdwCompatFlags
0x180123e7f  mov     [rsp+88h+dwMiscStatus], 0
0x180123e87  mov     funcNamespace, rdi; pclsid
0x180123e8a  call    cs:__imp_CompatFlagsFromClsid
0x180123e91  nop     dword ptr [rax+rax+00h]
0x180123e96  mov     ecx, eax; hr
0x180123e98  call    ?succeeded@@YAJJ@Z; succeeded(long)
0x180123e9d  test    [rsp+88h+dwCompat], 400h
0x180123ea5  jz      short loc_180123EBF
0x180123ea7  xor     r9d, r9d; o3
0x180123eaa  xor     r8d, r8d; o2
0x180123ead  xor     edx, edx; o1
0x180123eaf  mov     ecx, 0C00CE33Ch; resid
0x180123eb4  call    ?storeError@XUtility@@SAXJPEAVObject@@00@Z; XUtility::storeError(long,Object *,Object *,Object *)
0x180123eb9  call    ?throwStored@Exception@@SAXXZ; Exception::throwStored(void)
0x180123ebe  int     3; Trap to Debugger
0x180123ebf  mov     edx, 4; dwFlags
0x180123ec4  lea     ecx, [clsid+64h]; cb
0x180123ec7  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180123ecc  movaps  xmm6, xmmword ptr [rdi]
0x180123ecf  mov     r8, rbp; funcNamespace
0x180123ed2  xor     edx, edx; host
0x180123ed4  mov     funcNamespace, rax; this
0x180123ed7  mov     rbx, rax
0x180123eda  call    ??0DispatchFunctions@@IEAA@PEAVExecutionHost@@PEAVAtom@@@Z; DispatchFunctions::DispatchFunctions(ExecutionHost *,Atom *)
0x180123edf  lea     rax, ??_7ObjectParam@@6BObject@@@; const ObjectParam::`vftable'{for `Object'}
0x180123ee6  xor     edx, edx; pUnkOuter
0x180123ee8  mov     [rbx], rax
0x180123eeb  lea     r15, [rbx+48h]
0x180123eef  lea     rax, ??_7ScriptEngine@@6B_xunknown@@@; const ScriptEngine::`vftable'{for `_xunknown'}
0x180123ef6  mov     [rsp+88h+ppv], r15; ppv
0x180123efb  mov     [rbx+8], rax
0x180123eff  lea     r14, [rbx+50h]
0x180123f03  mov     qword ptr [r15], 0
0x180123f0a  lea     pp, IID_IActiveScript; riid
0x180123f11  mov     qword ptr [r14], 0
0x180123f18  lea     r8d, [clsid+1]; dwClsContext
0x180123f1c  mov     funcNamespace, rdi; rclsid
0x180123f1f  movdqu  xmmword ptr [rbx+58h], xmm6
0x180123f24  call    cs:__imp_CoCreateInstance
0x180123f2b  nop     dword ptr [rax+rax+00h]
0x180123f30  mov     edi, eax
0x180123f32  test    eax, eax
0x180123f34  js      short loc_180123F86
0x180123f36  mov     funcNamespace, [r15]
0x180123f39  lea     clsid, IID_IActiveScriptParse64
0x180123f40  mov     r8, r14
0x180123f43  mov     rax, [funcNamespace]
0x180123f46  mov     rax, [rax]
0x180123f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123f4e  mov     edi, eax
0x180123f50  test    eax, eax
0x180123f52  js      short loc_180123F86
0x180123f54  mov     funcNamespace, [r14]
0x180123f57  mov     rax, [funcNamespace]
0x180123f5a  mov     rax, [rax+18h]
0x180123f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123f63  mov     edi, eax
0x180123f65  test    eax, eax
0x180123f67  js      short loc_180123F86
0x180123f69  movaps  xmm6, [rsp+88h+var_38]
0x180123f6e  mov     [rsi], rbx
0x180123f71  mov     rbx, [rsp+88h+arg_10]
0x180123f79  add     rsp, 60h
0x180123f7d  pop     r15
0x180123f7f  pop     r14
0x180123f81  pop     rdi
0x180123f82  pop     rsi
0x180123f83  pop     rbp
0x180123f84  retn
0x180123f86  mov     rax, [rbx]
0x180123f89  mov     funcNamespace, rbx
0x180123f8c  mov     rax, [rax+10h]
0x180123f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123f95  mov     ecx, edi; hr
0x180123f97  mov     qword ptr [rsi], 0
0x180123f9e  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
```
