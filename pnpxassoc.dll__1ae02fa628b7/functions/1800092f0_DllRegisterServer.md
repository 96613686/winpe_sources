# DllRegisterServer

- ea: `0x1800092f0`
- end: `0x1800093ce`
- name: `DllRegisterServer`
- size: `222`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800062a8`
- `0x1800092f0`
- `0x180014010`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax
  __int64 *v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  v0 = qword_18001AC68;
  if ( qword_18001AC68 )
  {
    while ( *(_QWORD *)v0 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v0 + 8))(1);
      if ( result < 0 )
        return result;
      v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v2, 1);
      if ( result < 0 )
        return result;
      v0 += 72;
    }
  }
  v3 = off_18001A200[0];
  result = 0;
  v4 = off_18001A208;
  while ( v3 < v4 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v5 + 8))(1);
      if ( result < 0 )
        return result;
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 1);
      if ( result < 0 )
        return result;
      v4 = off_18001A208;
    }
    ++v3;
  }
  if ( ATL::_pPerfRegFunc )
    return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hInstance);
  return result;
}

```

## disassembly

```asm
0x1800092f0  mov     [rsp+arg_0], rbx
0x1800092f5  push    rdi
0x1800092f6  sub     rsp, 20h
0x1800092fa  mov     rbx, cs:qword_18001AC68
0x180009301  test    rbx, rbx
0x180009304  jz      short loc_18000934A
0x180009306  jmp     short loc_180009344
0x180009308  mov     rax, [rbx+8]
0x18000930c  mov     ecx, 1
0x180009311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009316  test    eax, eax
0x180009318  js      loc_1800093C3
0x18000931e  mov     rax, [rbx+38h]
0x180009322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009327  mov     rcx, [rbx]; rguid
0x18000932a  mov     r8d, 1; int
0x180009330  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009333  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009338  test    eax, eax
0x18000933a  js      loc_1800093C3
0x180009340  add     rbx, 48h ; 'H'
0x180009344  cmp     qword ptr [rbx], 0
0x180009348  jnz     short loc_180009308
0x18000934a  mov     rbx, cs:off_18001A200
0x180009351  xor     eax, eax
0x180009353  mov     rcx, cs:off_18001A208
0x18000935a  jmp     short loc_18000939F
0x18000935c  mov     rdi, [rbx]
0x18000935f  test    rdi, rdi
0x180009362  jz      short loc_18000939B
0x180009364  mov     rax, [rdi+8]
0x180009368  mov     ecx, 1
0x18000936d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009372  test    eax, eax
0x180009374  js      short loc_1800093C3
0x180009376  mov     rax, [rdi+38h]
0x18000937a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000937f  mov     rcx, [rdi]; rguid
0x180009382  mov     r8d, 1; int
0x180009388  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000938b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009390  test    eax, eax
0x180009392  js      short loc_1800093C3
0x180009394  mov     rcx, cs:off_18001A208
0x18000939b  add     rbx, 8
0x18000939f  cmp     rbx, rcx
0x1800093a2  jb      short loc_18000935C
0x1800093a4  test    eax, eax
0x1800093a6  js      short loc_1800093C3
0x1800093a8  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1800093af  test    rdx, rdx
0x1800093b2  jz      short loc_1800093C3
0x1800093b4  mov     rcx, cs:hInstance
0x1800093bb  mov     rax, rdx
0x1800093be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c3  mov     rbx, [rsp+28h+arg_0]
0x1800093c8  add     rsp, 20h
0x1800093cc  pop     rdi
0x1800093cd  retn
```
