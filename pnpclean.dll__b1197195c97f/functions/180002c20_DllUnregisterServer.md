# DllUnregisterServer

- ea: `0x180002c20`
- end: `0x180002ccc`
- name: `DllUnregisterServer`
- size: `172`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002304`
- `0x180002c20`
- `0x18000a010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180002c3c`
- `KERNEL32!SetThreadLocale` at `0x180002cb4`
- `KERNEL32!SetThreadLocale` at `0x180002c3c`
- `KERNEL32!SetThreadLocale` at `0x180002cb4`
- `KERNEL32!GetThreadLocale` at `0x180002c2f`
- `KERNEL32!GetThreadLocale` at `0x180002c2f`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // esi
  int v1; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  HRESULT v6; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v1 = ATL::_pPerfUnRegFunc(), v1 >= 0) )
  {
    v2 = off_1800100B0;
    v1 = 0;
    v3 = off_1800100B8;
    while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
        v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0);
        if ( v1 < 0 )
          break;
        v1 = (*((__int64 (__fastcall **)(_QWORD))v4 + 1))(0);
        if ( v1 < 0 )
          break;
        v3 = off_1800100B8;
      }
      ++v2;
    }
  }
  v6 = 0;
  if ( v1 < 0 )
    v6 = v1;
  SetThreadLocale(ThreadLocale);
  return v6;
}

```

## disassembly

```asm
0x180002c20  mov     [rsp+arg_0], rbx
0x180002c25  mov     [rsp+arg_8], rsi
0x180002c2a  push    rdi
0x180002c2b  sub     rsp, 20h
0x180002c2f  call    cs:__imp_GetThreadLocale
0x180002c35  mov     ecx, 800h; Locale
0x180002c3a  mov     esi, eax
0x180002c3c  call    cs:__imp_SetThreadLocale
0x180002c42  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180002c49  test    rax, rax
0x180002c4c  jz      short loc_180002C57
0x180002c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c53  test    eax, eax
0x180002c55  js      short loc_180002CAB
0x180002c57  mov     rbx, cs:off_1800100B0
0x180002c5e  xor     eax, eax
0x180002c60  mov     rcx, cs:off_1800100B8
0x180002c67  jmp     short loc_180002CA6
0x180002c69  mov     rdi, [rbx]
0x180002c6c  test    rdi, rdi
0x180002c6f  jz      short loc_180002CA2
0x180002c71  mov     rax, [rdi+38h]
0x180002c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7a  mov     rcx, [rdi]; rguid
0x180002c7d  xor     r8d, r8d; int
0x180002c80  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180002c83  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180002c88  test    eax, eax
0x180002c8a  js      short loc_180002CAB
0x180002c8c  mov     rax, [rdi+8]
0x180002c90  xor     ecx, ecx
0x180002c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c97  test    eax, eax
0x180002c99  js      short loc_180002CAB
0x180002c9b  mov     rcx, cs:off_1800100B8
0x180002ca2  add     rbx, 8
0x180002ca6  cmp     rbx, rcx
0x180002ca9  jb      short loc_180002C69
0x180002cab  xor     ebx, ebx
0x180002cad  mov     ecx, esi; Locale
0x180002caf  test    eax, eax
0x180002cb1  cmovs   ebx, eax
0x180002cb4  call    cs:__imp_SetThreadLocale
0x180002cba  mov     rsi, [rsp+28h+arg_8]
0x180002cbf  mov     eax, ebx
0x180002cc1  mov     rbx, [rsp+28h+arg_0]
0x180002cc6  add     rsp, 20h
0x180002cca  pop     rdi
0x180002ccb  retn
```
