# DllUnregisterServer

- ea: `0x18000c780`
- end: `0x18000c7d4`
- name: `DllUnregisterServer`
- size: `84`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800099a8`
- `0x18000bee4`
- `0x18000c780`
- `0x18001c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  const unsigned __int16 *v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax
  HRESULT result; // eax

  v2 = qword_1800280C8;
  if ( qword_1800280C8 )
  {
    while ( *(_QWORD *)v2 )
    {
      v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v3, 0);
      if ( result < 0 )
        return result;
      result = (*(__int64 (__fastcall **)(_QWORD))(v2 + 8))(0);
      if ( result < 0 )
        return result;
      v2 += 72;
    }
  }
  return ATL::CAtlModuleT<ATL::CComModule>::UnregisterServer(v1, v0);
}

```

## disassembly

```asm
0x18000c780  push    rbx
0x18000c782  sub     rsp, 20h
0x18000c786  mov     rbx, cs:qword_1800280C8
0x18000c78d  test    rbx, rbx
0x18000c790  jz      short loc_18000C7C8
0x18000c792  jmp     short loc_18000C7C2
0x18000c794  mov     rax, [rbx+38h]
0x18000c798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c79d  xor     r8d, r8d; int
0x18000c7a0  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000c7a3  mov     rcx, [rbx]; rguid
0x18000c7a6  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000c7ab  test    eax, eax
0x18000c7ad  js      short loc_18000C7CE
0x18000c7af  xor     ecx, ecx
0x18000c7b1  mov     rax, [rbx+8]
0x18000c7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ba  test    eax, eax
0x18000c7bc  js      short loc_18000C7CE
0x18000c7be  add     rbx, 48h ; 'H'
0x18000c7c2  cmp     qword ptr [rbx], 0
0x18000c7c6  jnz     short loc_18000C794
0x18000c7c8  call    ?UnregisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::UnregisterServer(int,_GUID const *)
0x18000c7cd  nop
0x18000c7ce  add     rsp, 20h
0x18000c7d2  pop     rbx
0x18000c7d3  retn
```
