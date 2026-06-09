# DllUnregisterServer

- ea: `0x180005df0`
- end: `0x180005e9d`
- name: `DllUnregisterServer`
- size: `173`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005b80`

## callees

- `0x1800054a0`
- `0x180005df0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180005dff`
- `KERNEL32!GetThreadLocale` at `0x180005dff`
- `KERNEL32!SetThreadLocale` at `0x180005e0c`
- `KERNEL32!SetThreadLocale` at `0x180005e85`
- `KERNEL32!SetThreadLocale` at `0x180005e0c`
- `KERNEL32!SetThreadLocale` at `0x180005e85`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // esi
  int v1; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v2; // rbx
  __int64 *v3; // rcx
  __int64 v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  HRESULT v6; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v1 = ATL::_pPerfUnRegFunc(), v1 >= 0) )
  {
    v1 = 0;
    v2 = off_180010160;
    v3 = (__int64 *)off_180010168;
    while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v3 )
    {
      v4 = *(_QWORD *)v2;
      if ( *(_QWORD *)v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
        v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0);
        if ( v1 < 0 )
          break;
        v1 = (*(__int64 (__fastcall **)(_QWORD))(v4 + 8))(0);
        if ( v1 < 0 )
          break;
        v3 = (__int64 *)off_180010168;
      }
      v2 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v2 + 8);
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
0x180005df0  mov     [rsp+arg_0], rbx
0x180005df5  mov     [rsp+arg_8], rsi
0x180005dfa  push    rdi
0x180005dfb  sub     rsp, 20h
0x180005dff  call    cs:__imp_GetThreadLocale
0x180005e05  mov     esi, eax
0x180005e07  mov     ecx, 800h; Locale
0x180005e0c  call    cs:__imp_SetThreadLocale
0x180005e12  nop
0x180005e13  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180005e1a  test    rax, rax
0x180005e1d  jz      short loc_180005E28
0x180005e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e24  test    eax, eax
0x180005e26  js      short loc_180005E7C
0x180005e28  xor     eax, eax
0x180005e2a  mov     rbx, cs:off_180010160
0x180005e31  mov     rcx, cs:off_180010168
0x180005e38  jmp     short loc_180005E77
0x180005e3a  mov     rdi, [rbx]
0x180005e3d  test    rdi, rdi
0x180005e40  jz      short loc_180005E73
0x180005e42  mov     rax, [rdi+38h]
0x180005e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e4b  xor     r8d, r8d; int
0x180005e4e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005e51  mov     rcx, [rdi]; rguid
0x180005e54  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005e59  test    eax, eax
0x180005e5b  js      short loc_180005E7C
0x180005e5d  xor     ecx, ecx
0x180005e5f  mov     rax, [rdi+8]
0x180005e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e68  test    eax, eax
0x180005e6a  js      short loc_180005E7C
0x180005e6c  mov     rcx, cs:off_180010168
0x180005e73  add     rbx, 8
0x180005e77  cmp     rbx, rcx
0x180005e7a  jb      short loc_180005E3A
0x180005e7c  xor     ebx, ebx
0x180005e7e  test    eax, eax
0x180005e80  cmovs   ebx, eax
0x180005e83  mov     ecx, esi; Locale
0x180005e85  call    cs:__imp_SetThreadLocale
0x180005e8b  mov     eax, ebx
0x180005e8d  mov     rbx, [rsp+28h+arg_0]
0x180005e92  mov     rsi, [rsp+28h+arg_8]
0x180005e97  add     rsp, 20h
0x180005e9b  pop     rdi
0x180005e9c  retn
```
