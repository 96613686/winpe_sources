# DllUnregisterServer

- ea: `0x180006900`
- end: `0x18000697e`
- name: `DllUnregisterServer`
- size: `126`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800038f0`
- `0x180006900`
- `0x18000b010`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  __int64 (*v1)(void); // rax
  __int64 (*v2)(void); // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v3; // rax

  v0 = qword_180012EE0;
  if ( qword_180012EE0 )
  {
    while ( 1 )
    {
      if ( !*(_QWORD *)v0 )
        return 0;
      v1 = *(__int64 (**)(void))(v0 + 48);
      if ( !v1 || !v1() )
      {
        (*(void (__fastcall **)(_QWORD))(v0 + 8))(0);
        if ( _Module == 248 )
        {
          v2 = *(__int64 (**)(void))(v0 + 56);
          if ( !v2 )
            goto LABEL_10;
          v3 = (const struct ATL::_ATL_CATMAP_ENTRY *)v2();
          ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v0, v3, 0);
        }
      }
      if ( _Module == 176 )
        v0 += 56;
      else
LABEL_10:
        v0 += 72;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006900  push    rbx
0x180006902  sub     rsp, 20h
0x180006906  mov     rbx, cs:qword_180012EE0
0x18000690d  test    rbx, rbx
0x180006910  jz      short loc_180006976
0x180006912  jmp     short loc_180006970
0x180006914  mov     rax, [rbx+30h]
0x180006918  test    rax, rax
0x18000691b  jz      short loc_180006927
0x18000691d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006922  test    rax, rax
0x180006925  jnz     short loc_18000695A
0x180006927  mov     rax, [rbx+8]
0x18000692b  xor     ecx, ecx
0x18000692d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006932  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18000693c  jnz     short loc_18000695A
0x18000693e  mov     rax, [rbx+38h]
0x180006942  test    rax, rax
0x180006945  jz      short loc_18000696C
0x180006947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694c  mov     rcx, [rbx]; struct _GUID *
0x18000694f  xor     r8d, r8d; int
0x180006952  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006955  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000695a  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180006964  jnz     short loc_18000696C
0x180006966  add     rbx, 38h ; '8'
0x18000696a  jmp     short loc_180006970
0x18000696c  add     rbx, 48h ; 'H'
0x180006970  cmp     qword ptr [rbx], 0
0x180006974  jnz     short loc_180006914
0x180006976  xor     eax, eax
0x180006978  add     rsp, 20h
0x18000697c  pop     rbx
0x18000697d  retn
```
