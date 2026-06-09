# DllRegisterServer

- ea: `0x180005d50`
- end: `0x180005e60`
- name: `DllRegisterServer`
- size: `272`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034c0`
- `0x180005d50`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005d6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180005d6a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005e4d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005e4d`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // ebp
  HRESULT v1; // eax
  HRESULT v2; // ebx
  __int64 v3; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax
  __int64 *v5; // rdi
  __int64 *v6; // rax
  __int64 v7; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax

  v0 = 1;
  v1 = CoInitializeEx(0, 6u);
  v2 = v1;
  if ( v1 >= 0 || (v0 = 0, v1 == -2147417850) )
  {
    v3 = qword_18000B808;
    if ( qword_18000B808 )
    {
      while ( *(_QWORD *)v3 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64))(v3 + 8))(1);
        if ( v2 < 0 )
          goto LABEL_19;
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
        v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 1);
        if ( v2 < 0 )
          goto LABEL_19;
        v3 += 72;
      }
    }
    v5 = (__int64 *)off_18000B0A0[0];
    v2 = 0;
    v6 = (__int64 *)off_18000B0A8;
    while ( v5 < v6 )
    {
      v7 = *v5;
      if ( *v5 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64))(v7 + 8))(1);
        if ( v2 < 0 )
          break;
        v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v7 + 56))();
        v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 1);
        if ( v2 < 0 )
          break;
        v6 = (__int64 *)off_18000B0A8;
      }
      ++v5;
    }
    if ( v2 >= 0 && ATL::_pPerfRegFunc )
      v2 = ATL::_pPerfRegFunc(hModule);
LABEL_19:
    if ( v0 )
      CoUninitialize();
  }
  return v2;
}

```

## disassembly

```asm
0x180005d50  push    rbx
0x180005d52  push    rbp
0x180005d53  push    rsi
0x180005d54  push    rdi
0x180005d55  push    r14
0x180005d57  sub     rsp, 20h
0x180005d5b  mov     r14d, 1
0x180005d61  xor     ecx, ecx; pvReserved
0x180005d63  mov     ebp, r14d
0x180005d66  lea     edx, [r14+5]; dwCoInit
0x180005d6a  call    cs:__imp_CoInitializeEx
0x180005d70  mov     ebx, eax
0x180005d72  test    eax, eax
0x180005d74  jns     short loc_180005D83
0x180005d76  xor     ebp, ebp
0x180005d78  cmp     eax, 80010106h
0x180005d7d  jnz     loc_180005E53
0x180005d83  mov     rdi, cs:qword_18000B808
0x180005d8a  test    rdi, rdi
0x180005d8d  jz      short loc_180005DD2
0x180005d8f  jmp     short loc_180005DCC
0x180005d91  mov     rax, [rdi+8]
0x180005d95  mov     ecx, r14d
0x180005d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9d  mov     ebx, eax
0x180005d9f  test    eax, eax
0x180005da1  js      loc_180005E49
0x180005da7  mov     rax, [rdi+38h]
0x180005dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db0  mov     rcx, [rdi]; rguid
0x180005db3  mov     r8d, r14d; int
0x180005db6  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005db9  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005dbe  mov     ebx, eax
0x180005dc0  test    eax, eax
0x180005dc2  js      loc_180005E49
0x180005dc8  add     rdi, 48h ; 'H'
0x180005dcc  cmp     qword ptr [rdi], 0
0x180005dd0  jnz     short loc_180005D91
0x180005dd2  mov     rdi, cs:off_18000B0A0
0x180005dd9  xor     ebx, ebx
0x180005ddb  mov     rax, cs:off_18000B0A8
0x180005de2  jmp     short loc_180005E26
0x180005de4  mov     rsi, [rdi]
0x180005de7  test    rsi, rsi
0x180005dea  jz      short loc_180005E22
0x180005dec  mov     rax, [rsi+8]
0x180005df0  mov     ecx, r14d
0x180005df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df8  mov     ebx, eax
0x180005dfa  test    eax, eax
0x180005dfc  js      short loc_180005E2B
0x180005dfe  mov     rax, [rsi+38h]
0x180005e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e07  mov     rcx, [rsi]; rguid
0x180005e0a  mov     r8d, r14d; int
0x180005e0d  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005e10  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005e15  mov     ebx, eax
0x180005e17  test    eax, eax
0x180005e19  js      short loc_180005E2B
0x180005e1b  mov     rax, cs:off_18000B0A8
0x180005e22  add     rdi, 8
0x180005e26  cmp     rdi, rax
0x180005e29  jb      short loc_180005DE4
0x180005e2b  test    ebx, ebx
0x180005e2d  js      short loc_180005E49
0x180005e2f  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180005e36  test    rax, rax
0x180005e39  jz      short loc_180005E49
0x180005e3b  mov     rcx, cs:hModule
0x180005e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e47  mov     ebx, eax
0x180005e49  test    ebp, ebp
0x180005e4b  jz      short loc_180005E53
0x180005e4d  call    cs:__imp_CoUninitialize
0x180005e53  mov     eax, ebx
0x180005e55  add     rsp, 20h
0x180005e59  pop     r14
0x180005e5b  pop     rdi
0x180005e5c  pop     rsi
0x180005e5d  pop     rbp
0x180005e5e  pop     rbx
0x180005e5f  retn
```
