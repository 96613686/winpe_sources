# DllRegisterServer

- ea: `0x180005d30`
- end: `0x180005ddc`
- name: `DllRegisterServer`
- size: `172`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005b80`

## callees

- `0x1800054a0`
- `0x180005d30`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180005d39`
- `KERNEL32!GetThreadLocale` at `0x180005d39`
- `KERNEL32!SetThreadLocale` at `0x180005d46`
- `KERNEL32!SetThreadLocale` at `0x180005dcb`
- `KERNEL32!SetThreadLocale` at `0x180005d46`
- `KERNEL32!SetThreadLocale` at `0x180005dcb`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  HRESULT v1; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v2; // rdi
  __int64 *v3; // rcx
  __int64 v4; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = 0;
  v2 = off_180010160;
  v3 = (__int64 *)off_180010168;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v3 )
  {
    v4 = *(_QWORD *)v2;
    if ( *(_QWORD *)v2 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64))(v4 + 8))(1);
      if ( v1 < 0 )
        break;
      v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
      v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 1);
      if ( v1 < 0 )
        break;
      v3 = (__int64 *)off_180010168;
    }
    v2 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v2 + 8);
  }
  if ( v1 >= 0 && ATL::_pPerfRegFunc )
    v1 = ATL::_pPerfRegFunc(hInstance);
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x180005d30  push    rbx
0x180005d32  push    rbp
0x180005d33  push    rsi
0x180005d34  push    rdi
0x180005d35  sub     rsp, 28h
0x180005d39  call    cs:__imp_GetThreadLocale
0x180005d3f  mov     ebp, eax
0x180005d41  mov     ecx, 800h; Locale
0x180005d46  call    cs:__imp_SetThreadLocale
0x180005d4c  nop
0x180005d4d  xor     ebx, ebx
0x180005d4f  mov     rdi, cs:off_180010160
0x180005d56  mov     rcx, cs:off_180010168
0x180005d5d  jmp     short loc_180005DA6
0x180005d5f  mov     rsi, [rdi]
0x180005d62  test    rsi, rsi
0x180005d65  jz      short loc_180005DA2
0x180005d67  mov     ecx, 1
0x180005d6c  mov     rax, [rsi+8]
0x180005d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d75  mov     ebx, eax
0x180005d77  test    eax, eax
0x180005d79  js      short loc_180005DAB
0x180005d7b  mov     rax, [rsi+38h]
0x180005d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d84  mov     r8d, 1; int
0x180005d8a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005d8d  mov     rcx, [rsi]; rguid
0x180005d90  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005d95  mov     ebx, eax
0x180005d97  test    eax, eax
0x180005d99  js      short loc_180005DAB
0x180005d9b  mov     rcx, cs:off_180010168
0x180005da2  add     rdi, 8
0x180005da6  cmp     rdi, rcx
0x180005da9  jb      short loc_180005D5F
0x180005dab  test    ebx, ebx
0x180005dad  js      short loc_180005DC9
0x180005daf  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180005db6  test    rax, rax
0x180005db9  jz      short loc_180005DC9
0x180005dbb  mov     rcx, cs:hInstance
0x180005dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dc7  mov     ebx, eax
0x180005dc9  mov     ecx, ebp; Locale
0x180005dcb  call    cs:__imp_SetThreadLocale
0x180005dd1  mov     eax, ebx
0x180005dd3  add     rsp, 28h
0x180005dd7  pop     rdi
0x180005dd8  pop     rsi
0x180005dd9  pop     rbp
0x180005dda  pop     rbx
0x180005ddb  retn
```
