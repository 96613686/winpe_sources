# DllUnregisterServer

- ea: `0x1800093e0`
- end: `0x1800094a4`
- name: `DllUnregisterServer`
- size: `196`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800062a8`
- `0x1800093e0`
- `0x180014010`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v1; // rax
  HRESULT result; // eax
  __int64 *v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  v0 = qword_18001AC68;
  if ( qword_18001AC68 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0);
      if ( result < 0 )
        return result;
      result = (*(__int64 (__fastcall **)(_QWORD))(v0 + 8))(0);
      if ( result < 0 )
        return result;
      v0 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
  {
    v3 = off_18001A200[0];
    result = 0;
    v4 = off_18001A208;
    while ( v3 < v4 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( result < 0 )
          return result;
        result = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
        if ( result < 0 )
          return result;
        v4 = off_18001A208;
      }
      ++v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800093e0  mov     [rsp+arg_0], rbx
0x1800093e5  push    rdi
0x1800093e6  sub     rsp, 20h
0x1800093ea  mov     rbx, cs:qword_18001AC68
0x1800093f1  test    rbx, rbx
0x1800093f4  jz      short loc_180009430
0x1800093f6  jmp     short loc_18000942A
0x1800093f8  mov     rax, [rbx+38h]
0x1800093fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009401  mov     rcx, [rbx]; rguid
0x180009404  xor     r8d, r8d; int
0x180009407  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000940a  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000940f  test    eax, eax
0x180009411  js      loc_180009499
0x180009417  mov     rax, [rbx+8]
0x18000941b  xor     ecx, ecx
0x18000941d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009422  test    eax, eax
0x180009424  js      short loc_180009499
0x180009426  add     rbx, 48h ; 'H'
0x18000942a  cmp     qword ptr [rbx], 0
0x18000942e  jnz     short loc_1800093F8
0x180009430  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180009437  test    rax, rax
0x18000943a  jz      short loc_180009445
0x18000943c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009441  test    eax, eax
0x180009443  js      short loc_180009499
0x180009445  mov     rbx, cs:off_18001A200
0x18000944c  xor     eax, eax
0x18000944e  mov     rcx, cs:off_18001A208
0x180009455  jmp     short loc_180009494
0x180009457  mov     rdi, [rbx]
0x18000945a  test    rdi, rdi
0x18000945d  jz      short loc_180009490
0x18000945f  mov     rax, [rdi+38h]
0x180009463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009468  mov     rcx, [rdi]; rguid
0x18000946b  xor     r8d, r8d; int
0x18000946e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009471  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009476  test    eax, eax
0x180009478  js      short loc_180009499
0x18000947a  mov     rax, [rdi+8]
0x18000947e  xor     ecx, ecx
0x180009480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009485  test    eax, eax
0x180009487  js      short loc_180009499
0x180009489  mov     rcx, cs:off_18001A208
0x180009490  add     rbx, 8
0x180009494  cmp     rbx, rcx
0x180009497  jb      short loc_180009457
0x180009499  mov     rbx, [rsp+28h+arg_0]
0x18000949e  add     rsp, 20h
0x1800094a2  pop     rdi
0x1800094a3  retn
```
