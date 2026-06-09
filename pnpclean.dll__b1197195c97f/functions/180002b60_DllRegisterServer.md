# DllRegisterServer

- ea: `0x180002b60`
- end: `0x180002c0b`
- name: `DllRegisterServer`
- size: `171`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002304`
- `0x180002b60`
- `0x18000a010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180002b76`
- `KERNEL32!SetThreadLocale` at `0x180002bfa`
- `KERNEL32!SetThreadLocale` at `0x180002b76`
- `KERNEL32!SetThreadLocale` at `0x180002bfa`
- `KERNEL32!GetThreadLocale` at `0x180002b69`
- `KERNEL32!GetThreadLocale` at `0x180002b69`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  __int64 *v1; // rcx
  HRESULT v2; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rdi
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = off_1800100B8;
  v2 = 0;
  for ( i = off_1800100B0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v1; ++i )
  {
    v4 = *i;
    if ( *i )
    {
      v2 = (*((__int64 (__fastcall **)(__int64))v4 + 1))(1);
      if ( v2 < 0 )
        break;
      v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
      v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 1);
      if ( v2 < 0 )
        break;
      v1 = off_1800100B8;
    }
  }
  if ( v2 >= 0 && ATL::_pPerfRegFunc )
    v2 = ATL::_pPerfRegFunc(hInstance);
  SetThreadLocale(ThreadLocale);
  return v2;
}

```

## disassembly

```asm
0x180002b60  push    rbx
0x180002b62  push    rbp
0x180002b63  push    rsi
0x180002b64  push    rdi
0x180002b65  sub     rsp, 28h
0x180002b69  call    cs:__imp_GetThreadLocale
0x180002b6f  mov     ecx, 800h; Locale
0x180002b74  mov     ebp, eax
0x180002b76  call    cs:__imp_SetThreadLocale
0x180002b7c  mov     rcx, cs:off_1800100B8
0x180002b83  xor     ebx, ebx
0x180002b85  mov     rdi, cs:off_1800100B0
0x180002b8c  jmp     short loc_180002BD5
0x180002b8e  mov     rsi, [rdi]
0x180002b91  test    rsi, rsi
0x180002b94  jz      short loc_180002BD1
0x180002b96  mov     rax, [rsi+8]
0x180002b9a  mov     ecx, 1
0x180002b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba4  mov     ebx, eax
0x180002ba6  test    eax, eax
0x180002ba8  js      short loc_180002BDA
0x180002baa  mov     rax, [rsi+38h]
0x180002bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb3  mov     rcx, [rsi]; rguid
0x180002bb6  mov     r8d, 1; int
0x180002bbc  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180002bbf  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180002bc4  mov     ebx, eax
0x180002bc6  test    eax, eax
0x180002bc8  js      short loc_180002BDA
0x180002bca  mov     rcx, cs:off_1800100B8
0x180002bd1  add     rdi, 8
0x180002bd5  cmp     rdi, rcx
0x180002bd8  jb      short loc_180002B8E
0x180002bda  test    ebx, ebx
0x180002bdc  js      short loc_180002BF8
0x180002bde  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180002be5  test    rax, rax
0x180002be8  jz      short loc_180002BF8
0x180002bea  mov     rcx, cs:hInstance
0x180002bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf6  mov     ebx, eax
0x180002bf8  mov     ecx, ebp; Locale
0x180002bfa  call    cs:__imp_SetThreadLocale
0x180002c00  mov     eax, ebx
0x180002c02  add     rsp, 28h
0x180002c06  pop     rdi
0x180002c07  pop     rsi
0x180002c08  pop     rbp
0x180002c09  pop     rbx
0x180002c0a  retn
```
