# DllUnregisterServer

- ea: `0x1800128a0`
- end: `0x180012952`
- name: `DllUnregisterServer`
- size: `178`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f054`
- `0x18000f150`
- `0x1800128a0`
- `0x180014010`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800128cf`
- `RPCRT4!NdrDllUnregisterProxy` at `0x1800128cf`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8
  const unsigned __int16 *v2; // rdx
  struct ATL::_ATL_MODULE *v3; // rcx
  __int64 v4; // rbx
  __int64 (*v5)(void); // rax
  __int64 (*v6)(void); // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  v4 = qword_180024B20;
  if ( qword_180024B20 )
  {
    while ( 1 )
    {
      if ( !*(_QWORD *)v4 )
      {
        ATL::AtlModuleUnRegisterTypeLib(v3, v2);
        return 0;
      }
      v5 = *(__int64 (**)(void))(v4 + 48);
      if ( !v5 || !v5() )
      {
        (*(void (__fastcall **)(_QWORD))(v4 + 8))(0);
        if ( _Module == 248 )
        {
          v6 = *(__int64 (**)(void))(v4 + 56);
          if ( !v6 )
            goto LABEL_13;
          v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)v6();
          ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v4, v7, 0);
        }
      }
      if ( _Module == 176 )
        v4 += 56;
      else
LABEL_13:
        v4 += 72;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800128a0  push    rbx
0x1800128a2  sub     rsp, 20h
0x1800128a6  mov     rax, cs:aProxyFileList
0x1800128ad  mov     rcx, [rax+8]
0x1800128b1  mov     rax, [rcx]
0x1800128b4  test    rax, rax
0x1800128b7  jz      short loc_1800128BE
0x1800128b9  mov     r8, [rax]
0x1800128bc  jmp     short loc_1800128C1
0x1800128be  xor     r8d, r8d; pclsid
0x1800128c1  mov     rcx, cs:hProxyDll; hDll
0x1800128c8  lea     rdx, aProxyFileList; pProxyFileList
0x1800128cf  call    cs:__imp_NdrDllUnregisterProxy
0x1800128d5  mov     rbx, cs:qword_180024B20
0x1800128dc  test    rbx, rbx
0x1800128df  jz      short loc_18001294A
0x1800128e1  jmp     short loc_18001293F
0x1800128e3  mov     rax, [rbx+30h]
0x1800128e7  test    rax, rax
0x1800128ea  jz      short loc_1800128F6
0x1800128ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128f1  test    rax, rax
0x1800128f4  jnz     short loc_180012929
0x1800128f6  mov     rax, [rbx+8]
0x1800128fa  xor     ecx, ecx
0x1800128fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012901  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18001290b  jnz     short loc_180012929
0x18001290d  mov     rax, [rbx+38h]
0x180012911  test    rax, rax
0x180012914  jz      short loc_18001293B
0x180012916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001291b  mov     rcx, [rbx]; struct _GUID *
0x18001291e  xor     r8d, r8d; int
0x180012921  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180012924  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180012929  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180012933  jnz     short loc_18001293B
0x180012935  add     rbx, 38h ; '8'
0x180012939  jmp     short loc_18001293F
0x18001293b  add     rbx, 48h ; 'H'
0x18001293f  cmp     qword ptr [rbx], 0
0x180012943  jnz     short loc_1800128E3
0x180012945  call    ?AtlModuleUnRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z; ATL::AtlModuleUnRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)
0x18001294a  xor     eax, eax
0x18001294c  add     rsp, 20h
0x180012950  pop     rbx
0x180012951  retn
```
