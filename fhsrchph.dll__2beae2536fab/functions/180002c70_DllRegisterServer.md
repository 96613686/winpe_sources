# DllRegisterServer

- ea: `0x180002c70`
- end: `0x180002d1c`
- name: `DllRegisterServer`
- size: `172`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ac0`

## callees

- `0x1800022c4`
- `0x180002c70`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180002c79`
- `KERNEL32!GetThreadLocale` at `0x180002c79`
- `KERNEL32!SetThreadLocale` at `0x180002c86`
- `KERNEL32!SetThreadLocale` at `0x180002d0b`
- `KERNEL32!SetThreadLocale` at `0x180002c86`
- `KERNEL32!SetThreadLocale` at `0x180002d0b`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  HRESULT v1; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rdi
  __int64 *v3; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = 0;
  v2 = off_1800110B0;
  v3 = off_1800110B8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    v4 = *v2;
    if ( *v2 )
    {
      v1 = (*((__int64 (__fastcall **)(__int64))v4 + 1))(1);
      if ( v1 < 0 )
        break;
      v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
      v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 1);
      if ( v1 < 0 )
        break;
      v3 = off_1800110B8;
    }
    ++v2;
  }
  if ( v1 >= 0 && ATL::_pPerfRegFunc )
    v1 = ATL::_pPerfRegFunc(hInstance);
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x180002c70  push    rbx
0x180002c72  push    rbp
0x180002c73  push    rsi
0x180002c74  push    rdi
0x180002c75  sub     rsp, 28h
0x180002c79  call    cs:__imp_GetThreadLocale
0x180002c7f  mov     ebp, eax
0x180002c81  mov     ecx, 800h; Locale
0x180002c86  call    cs:__imp_SetThreadLocale
0x180002c8c  nop
0x180002c8d  xor     ebx, ebx
0x180002c8f  mov     rdi, cs:off_1800110B0
0x180002c96  mov     rcx, cs:off_1800110B8
0x180002c9d  jmp     short loc_180002CE6
0x180002c9f  mov     rsi, [rdi]
0x180002ca2  test    rsi, rsi
0x180002ca5  jz      short loc_180002CE2
0x180002ca7  mov     ecx, 1
0x180002cac  mov     rax, [rsi+8]
0x180002cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb5  mov     ebx, eax
0x180002cb7  test    eax, eax
0x180002cb9  js      short loc_180002CEB
0x180002cbb  mov     rax, [rsi+38h]
0x180002cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc4  mov     r8d, 1; int
0x180002cca  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180002ccd  mov     rcx, [rsi]; rguid
0x180002cd0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180002cd5  mov     ebx, eax
0x180002cd7  test    eax, eax
0x180002cd9  js      short loc_180002CEB
0x180002cdb  mov     rcx, cs:off_1800110B8
0x180002ce2  add     rdi, 8
0x180002ce6  cmp     rdi, rcx
0x180002ce9  jb      short loc_180002C9F
0x180002ceb  test    ebx, ebx
0x180002ced  js      short loc_180002D09
0x180002cef  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180002cf6  test    rax, rax
0x180002cf9  jz      short loc_180002D09
0x180002cfb  mov     rcx, cs:hInstance
0x180002d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d07  mov     ebx, eax
0x180002d09  mov     ecx, ebp; Locale
0x180002d0b  call    cs:__imp_SetThreadLocale
0x180002d11  mov     eax, ebx
0x180002d13  add     rsp, 28h
0x180002d17  pop     rdi
0x180002d18  pop     rsi
0x180002d19  pop     rbp
0x180002d1a  pop     rbx
0x180002d1b  retn
```
