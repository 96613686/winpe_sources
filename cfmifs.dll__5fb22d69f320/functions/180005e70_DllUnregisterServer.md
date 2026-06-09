# DllUnregisterServer

- ea: `0x180005e70`
- end: `0x180005f34`
- name: `DllUnregisterServer`
- size: `196`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800034c0`
- `0x180005e70`
- `0x180007010`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v1; // rax
  __int64 *v2; // rbx
  __int64 *v3; // rax
  __int64 v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  v0 = qword_18000B808;
  if ( qword_18000B808 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0) < 0
        || (*(int (__fastcall **)(_QWORD))(v0 + 8))(0) < 0 )
      {
        return 0;
      }
      v0 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || ATL::_pPerfUnRegFunc() >= 0 )
  {
    v2 = (__int64 *)off_18000B0A0[0];
    v3 = (__int64 *)off_18000B0A8;
    while ( v2 < v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
        if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0) < 0
          || (*(int (__fastcall **)(_QWORD))(v4 + 8))(0) < 0 )
        {
          return 0;
        }
        v3 = (__int64 *)off_18000B0A8;
      }
      ++v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005e70  mov     [rsp+arg_0], rbx
0x180005e75  push    rdi
0x180005e76  sub     rsp, 20h
0x180005e7a  mov     rbx, cs:qword_18000B808
0x180005e81  test    rbx, rbx
0x180005e84  jz      short loc_180005EC0
0x180005e86  jmp     short loc_180005EBA
0x180005e88  mov     rax, [rbx+38h]
0x180005e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e91  mov     rcx, [rbx]; rguid
0x180005e94  xor     r8d, r8d; int
0x180005e97  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005e9a  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005e9f  test    eax, eax
0x180005ea1  js      loc_180005F27
0x180005ea7  mov     rax, [rbx+8]
0x180005eab  xor     ecx, ecx
0x180005ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb2  test    eax, eax
0x180005eb4  js      short loc_180005F27
0x180005eb6  add     rbx, 48h ; 'H'
0x180005eba  cmp     qword ptr [rbx], 0
0x180005ebe  jnz     short loc_180005E88
0x180005ec0  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180005ec7  test    rax, rax
0x180005eca  jz      short loc_180005ED5
0x180005ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed1  test    eax, eax
0x180005ed3  js      short loc_180005F27
0x180005ed5  mov     rbx, cs:off_18000B0A0
0x180005edc  mov     rax, cs:off_18000B0A8
0x180005ee3  jmp     short loc_180005F22
0x180005ee5  mov     rdi, [rbx]
0x180005ee8  test    rdi, rdi
0x180005eeb  jz      short loc_180005F1E
0x180005eed  mov     rax, [rdi+38h]
0x180005ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef6  mov     rcx, [rdi]; rguid
0x180005ef9  xor     r8d, r8d; int
0x180005efc  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005eff  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005f04  test    eax, eax
0x180005f06  js      short loc_180005F27
0x180005f08  mov     rax, [rdi+8]
0x180005f0c  xor     ecx, ecx
0x180005f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f13  test    eax, eax
0x180005f15  js      short loc_180005F27
0x180005f17  mov     rax, cs:off_18000B0A8
0x180005f1e  add     rbx, 8
0x180005f22  cmp     rbx, rax
0x180005f25  jb      short loc_180005EE5
0x180005f27  mov     rbx, [rsp+28h+arg_0]
0x180005f2c  xor     eax, eax
0x180005f2e  add     rsp, 20h
0x180005f32  pop     rdi
0x180005f33  retn
```
