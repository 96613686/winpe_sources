# DllUnregisterServer

- ea: `0x1800134c0`
- end: `0x1800135a5`
- name: `DllUnregisterServer`
- size: `229`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000eb5c`
- `0x1800134c0`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180013594`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180013594`

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

  v0 = qword_180024F98;
  if ( qword_180024F98 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0);
      if ( result < 0 )
        goto LABEL_16;
      result = (*(__int64 (__fastcall **)(_QWORD))(v0 + 8))(0);
      if ( result < 0 )
        goto LABEL_16;
      v0 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
  {
    result = 0;
    v3 = off_1800243F0[0];
    v4 = off_1800243F8;
    while ( v3 < v4 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( result < 0 )
          break;
        result = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
        if ( result < 0 )
          break;
        v4 = off_1800243F8;
      }
      ++v3;
    }
  }
LABEL_16:
  if ( result >= 0 )
    return UnRegisterTypeLib(&GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d, 1u, 0, 0, SYS_WIN32);
  return result;
}

```

## disassembly

```asm
0x1800134c0  mov     [rsp+arg_0], rbx
0x1800134c5  push    rdi
0x1800134c6  sub     rsp, 30h
0x1800134ca  mov     rbx, cs:qword_180024F98
0x1800134d1  test    rbx, rbx
0x1800134d4  jz      short loc_180013510
0x1800134d6  jmp     short loc_18001350A
0x1800134d8  mov     rax, [rbx+38h]
0x1800134dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134e1  xor     r8d, r8d; int
0x1800134e4  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800134e7  mov     rcx, [rbx]; rguid
0x1800134ea  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800134ef  test    eax, eax
0x1800134f1  js      loc_180013579
0x1800134f7  xor     ecx, ecx
0x1800134f9  mov     rax, [rbx+8]
0x1800134fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013502  test    eax, eax
0x180013504  js      short loc_180013579
0x180013506  add     rbx, 48h ; 'H'
0x18001350a  cmp     qword ptr [rbx], 0
0x18001350e  jnz     short loc_1800134D8
0x180013510  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180013517  test    rax, rax
0x18001351a  jz      short loc_180013525
0x18001351c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013521  test    eax, eax
0x180013523  js      short loc_180013579
0x180013525  xor     eax, eax
0x180013527  mov     rbx, cs:off_1800243F0
0x18001352e  mov     rcx, cs:off_1800243F8
0x180013535  jmp     short loc_180013574
0x180013537  mov     rdi, [rbx]
0x18001353a  test    rdi, rdi
0x18001353d  jz      short loc_180013570
0x18001353f  mov     rax, [rdi+38h]
0x180013543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013548  xor     r8d, r8d; int
0x18001354b  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001354e  mov     rcx, [rdi]; rguid
0x180013551  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180013556  test    eax, eax
0x180013558  js      short loc_180013579
0x18001355a  xor     ecx, ecx
0x18001355c  mov     rax, [rdi+8]
0x180013560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013565  test    eax, eax
0x180013567  js      short loc_180013579
0x180013569  mov     rcx, cs:off_1800243F8
0x180013570  add     rbx, 8
0x180013574  cmp     rbx, rcx
0x180013577  jb      short loc_180013537
0x180013579  test    eax, eax
0x18001357b  js      short loc_18001359A
0x18001357d  xor     r8d, r8d; wVerMinor
0x180013580  lea     eax, [r8+1]
0x180013584  mov     edx, eax; wVerMajor
0x180013586  mov     [rsp+38h+syskind], eax; syskind
0x18001358a  xor     r9d, r9d; lcid
0x18001358d  lea     rcx, _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d; libID
0x180013594  call    cs:__imp_UnRegisterTypeLib
0x18001359a  mov     rbx, [rsp+38h+arg_0]
0x18001359f  add     rsp, 30h
0x1800135a3  pop     rdi
0x1800135a4  retn
```
