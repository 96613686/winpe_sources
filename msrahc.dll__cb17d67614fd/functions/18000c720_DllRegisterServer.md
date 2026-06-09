# DllRegisterServer

- ea: `0x18000c720`
- end: `0x18000c77a`
- name: `DllRegisterServer`
- size: `90`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800099a8`
- `0x18000b3a4`
- `0x18000c720`
- `0x18001c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax

  v2 = qword_1800280C8;
  if ( qword_1800280C8 )
  {
    while ( *(_QWORD *)v2 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v2 + 8))(1);
      if ( result < 0 )
        return result;
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v2 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v2, v4, 1);
      if ( result < 0 )
        return result;
      v2 += 72;
    }
  }
  return ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(v1, v0);
}

```

## disassembly

```asm
0x18000c720  push    rbx
0x18000c722  sub     rsp, 20h
0x18000c726  mov     rbx, cs:qword_1800280C8
0x18000c72d  test    rbx, rbx
0x18000c730  jz      short loc_18000C76E
0x18000c732  jmp     short loc_18000C768
0x18000c734  mov     ecx, 1
0x18000c739  mov     rax, [rbx+8]
0x18000c73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c742  test    eax, eax
0x18000c744  js      short loc_18000C774
0x18000c746  mov     rax, [rbx+38h]
0x18000c74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c74f  mov     r8d, 1; int
0x18000c755  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000c758  mov     rcx, [rbx]; rguid
0x18000c75b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000c760  test    eax, eax
0x18000c762  js      short loc_18000C774
0x18000c764  add     rbx, 48h ; 'H'
0x18000c768  cmp     qword ptr [rbx], 0
0x18000c76c  jnz     short loc_18000C734
0x18000c76e  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x18000c773  nop
0x18000c774  add     rsp, 20h
0x18000c778  pop     rbx
0x18000c779  retn
```
