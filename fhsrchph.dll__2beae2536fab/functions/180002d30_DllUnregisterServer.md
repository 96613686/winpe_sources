# DllUnregisterServer

- ea: `0x180002d30`
- end: `0x180002ddd`
- name: `DllUnregisterServer`
- size: `173`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ac0`

## callees

- `0x1800022c4`
- `0x180002d30`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180002d3f`
- `KERNEL32!GetThreadLocale` at `0x180002d3f`
- `KERNEL32!SetThreadLocale` at `0x180002d4c`
- `KERNEL32!SetThreadLocale` at `0x180002dc5`
- `KERNEL32!SetThreadLocale` at `0x180002d4c`
- `KERNEL32!SetThreadLocale` at `0x180002dc5`

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
    v1 = 0;
    v2 = off_1800110B0;
    v3 = off_1800110B8;
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
        v3 = off_1800110B8;
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
0x180002d30  mov     [rsp+arg_0], rbx
0x180002d35  mov     [rsp+arg_8], rsi
0x180002d3a  push    rdi
0x180002d3b  sub     rsp, 20h
0x180002d3f  call    cs:__imp_GetThreadLocale
0x180002d45  mov     esi, eax
0x180002d47  mov     ecx, 800h; Locale
0x180002d4c  call    cs:__imp_SetThreadLocale
0x180002d52  nop
0x180002d53  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180002d5a  test    rax, rax
0x180002d5d  jz      short loc_180002D68
0x180002d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d64  test    eax, eax
0x180002d66  js      short loc_180002DBC
0x180002d68  xor     eax, eax
0x180002d6a  mov     rbx, cs:off_1800110B0
0x180002d71  mov     rcx, cs:off_1800110B8
0x180002d78  jmp     short loc_180002DB7
0x180002d7a  mov     rdi, [rbx]
0x180002d7d  test    rdi, rdi
0x180002d80  jz      short loc_180002DB3
0x180002d82  mov     rax, [rdi+38h]
0x180002d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8b  xor     r8d, r8d; int
0x180002d8e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180002d91  mov     rcx, [rdi]; rguid
0x180002d94  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180002d99  test    eax, eax
0x180002d9b  js      short loc_180002DBC
0x180002d9d  xor     ecx, ecx
0x180002d9f  mov     rax, [rdi+8]
0x180002da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da8  test    eax, eax
0x180002daa  js      short loc_180002DBC
0x180002dac  mov     rcx, cs:off_1800110B8
0x180002db3  add     rbx, 8
0x180002db7  cmp     rbx, rcx
0x180002dba  jb      short loc_180002D7A
0x180002dbc  xor     ebx, ebx
0x180002dbe  test    eax, eax
0x180002dc0  cmovs   ebx, eax
0x180002dc3  mov     ecx, esi; Locale
0x180002dc5  call    cs:__imp_SetThreadLocale
0x180002dcb  mov     eax, ebx
0x180002dcd  mov     rbx, [rsp+28h+arg_0]
0x180002dd2  mov     rsi, [rsp+28h+arg_8]
0x180002dd7  add     rsp, 20h
0x180002ddb  pop     rdi
0x180002ddc  retn
```
