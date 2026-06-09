# DllRegisterServer

- ea: `0x180006840`
- end: `0x1800068f7`
- name: `DllRegisterServer`
- size: `183`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800038f0`
- `0x180005dbc`
- `0x180006840`
- `0x18000b010`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rbx
  HRESULT v1; // edi
  __int64 (*v2)(void); // rax
  int v3; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax

  v0 = qword_180012EE0;
  v1 = 0;
  if ( !qword_180012EE0 )
    goto LABEL_14;
  if ( *(_QWORD *)qword_180012EE0 )
  {
    do
    {
      v2 = *(__int64 (**)(void))(v0 + 48);
      if ( !v2 || !v2() )
      {
        v1 = (*(__int64 (__fastcall **)(__int64))(v0 + 8))(1);
        if ( v1 < 0 )
          break;
        v3 = _Module;
        if ( _Module != 248 )
          goto LABEL_9;
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
        v1 = ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v0, v4, 1);
        if ( v1 < 0 )
          break;
      }
      v3 = _Module;
LABEL_9:
      if ( v3 == 176 )
        v0 += 56;
      else
        v0 += 72;
    }
    while ( *(_QWORD *)v0 );
  }
  if ( !v1 )
  {
LABEL_14:
    RemovePathFromInProcServerEntry(&CLSID_ExtractIcon);
    RemovePathFromInProcServerEntry(&CLSID_HHCollectionWrapper);
  }
  return v1;
}

```

## disassembly

```asm
0x180006840  mov     [rsp+arg_0], rbx
0x180006845  push    rdi
0x180006846  sub     rsp, 20h
0x18000684a  mov     rbx, cs:qword_180012EE0
0x180006851  xor     edi, edi
0x180006853  test    rbx, rbx
0x180006856  jz      short loc_1800068D2
0x180006858  cmp     [rbx], rdi
0x18000685b  jz      short loc_1800068CE
0x18000685d  mov     rax, [rbx+30h]
0x180006861  test    rax, rax
0x180006864  jz      short loc_180006870
0x180006866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000686b  test    rax, rax
0x18000686e  jnz     short loc_1800068B1
0x180006870  mov     rax, [rbx+8]
0x180006874  mov     ecx, 1
0x180006879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000687e  mov     edi, eax
0x180006880  test    eax, eax
0x180006882  js      short loc_1800068CE
0x180006884  mov     eax, cs:?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000688a  cmp     eax, 0F8h
0x18000688f  jnz     short loc_1800068B7
0x180006891  mov     rax, [rbx+38h]
0x180006895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000689a  mov     rcx, [rbx]; struct _GUID *
0x18000689d  mov     r8d, 1; int
0x1800068a3  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800068a6  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800068ab  mov     edi, eax
0x1800068ad  test    eax, eax
0x1800068af  js      short loc_1800068CE
0x1800068b1  mov     eax, cs:?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x1800068b7  cmp     eax, 0B0h
0x1800068bc  jnz     short loc_1800068C4
0x1800068be  add     rbx, 38h ; '8'
0x1800068c2  jmp     short loc_1800068C8
0x1800068c4  add     rbx, 48h ; 'H'
0x1800068c8  cmp     qword ptr [rbx], 0
0x1800068cc  jnz     short loc_18000685D
0x1800068ce  test    edi, edi
0x1800068d0  jnz     short loc_1800068EA
0x1800068d2  lea     rcx, ?CLSID_ExtractIcon@@3U_GUID@@A; _GUID CLSID_ExtractIcon
0x1800068d9  call    RemovePathFromInProcServerEntry
0x1800068de  lea     rcx, CLSID_HHCollectionWrapper
0x1800068e5  call    RemovePathFromInProcServerEntry
0x1800068ea  mov     rbx, [rsp+28h+arg_0]
0x1800068ef  mov     eax, edi
0x1800068f1  add     rsp, 20h
0x1800068f5  pop     rdi
0x1800068f6  retn
```
