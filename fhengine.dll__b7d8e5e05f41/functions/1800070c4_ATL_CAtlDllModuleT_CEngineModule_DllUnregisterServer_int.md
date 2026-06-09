# ATL::CAtlDllModuleT<CEngineModule>::DllUnregisterServer(int)

- ea: `0x1800070c4`
- end: `0x180007171`
- name: `?DllUnregisterServer@?$CAtlDllModuleT@VCEngineModule@@@ATL@@QEAAJH@Z`
- size: `173`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800075f0`

## callees

- `0x180006b44`
- `0x1800070c4`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800070d3`
- `KERNEL32!GetThreadLocale` at `0x1800070d3`
- `KERNEL32!SetThreadLocale` at `0x1800070e0`
- `KERNEL32!SetThreadLocale` at `0x180007159`
- `KERNEL32!SetThreadLocale` at `0x1800070e0`
- `KERNEL32!SetThreadLocale` at `0x180007159`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 ATL::CAtlDllModuleT<CEngineModule>::DllUnregisterServer()
{
  LCID ThreadLocale; // esi
  int v1; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  unsigned int v6; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v1 = ATL::_pPerfUnRegFunc(), v1 >= 0) )
  {
    v1 = 0;
    v2 = off_1800401C0;
    v3 = off_1800401C8;
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
        v3 = off_1800401C8;
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
0x1800070c4  mov     [rsp+arg_0], rbx
0x1800070c9  mov     [rsp+arg_8], rsi
0x1800070ce  push    rdi
0x1800070cf  sub     rsp, 20h
0x1800070d3  call    cs:__imp_GetThreadLocale
0x1800070d9  mov     esi, eax
0x1800070db  mov     ecx, 800h; Locale
0x1800070e0  call    cs:__imp_SetThreadLocale
0x1800070e6  nop
0x1800070e7  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x1800070ee  test    rax, rax
0x1800070f1  jz      short loc_1800070FC
0x1800070f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f8  test    eax, eax
0x1800070fa  js      short loc_180007150
0x1800070fc  xor     eax, eax
0x1800070fe  mov     rbx, cs:off_1800401C0
0x180007105  mov     rcx, cs:off_1800401C8
0x18000710c  jmp     short loc_18000714B
0x18000710e  mov     rdi, [rbx]
0x180007111  test    rdi, rdi
0x180007114  jz      short loc_180007147
0x180007116  mov     rax, [rdi+38h]
0x18000711a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000711f  xor     r8d, r8d; int
0x180007122  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180007125  mov     rcx, [rdi]; rguid
0x180007128  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000712d  test    eax, eax
0x18000712f  js      short loc_180007150
0x180007131  xor     ecx, ecx
0x180007133  mov     rax, [rdi+8]
0x180007137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000713c  test    eax, eax
0x18000713e  js      short loc_180007150
0x180007140  mov     rcx, cs:off_1800401C8
0x180007147  add     rbx, 8
0x18000714b  cmp     rbx, rcx
0x18000714e  jb      short loc_18000710E
0x180007150  xor     ebx, ebx
0x180007152  test    eax, eax
0x180007154  cmovs   ebx, eax
0x180007157  mov     ecx, esi; Locale
0x180007159  call    cs:__imp_SetThreadLocale
0x18000715f  mov     eax, ebx
0x180007161  mov     rbx, [rsp+28h+arg_0]
0x180007166  mov     rsi, [rsp+28h+arg_8]
0x18000716b  add     rsp, 20h
0x18000716f  pop     rdi
0x180007170  retn
```
