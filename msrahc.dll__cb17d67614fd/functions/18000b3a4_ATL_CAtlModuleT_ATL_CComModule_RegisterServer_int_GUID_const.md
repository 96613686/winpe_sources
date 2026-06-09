# ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)

- ea: `0x18000b3a4`
- end: `0x18000b446`
- name: `?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c720`

## callees

- `0x1800099a8`
- `0x180009cec`
- `0x18000b3a4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(__int64 a1, const unsigned __int16 *a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rdi
  __int64 result; // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  v2 = off_180027590;
  for ( i = off_180027598; v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v2 )
  {
    v4 = *v2;
    if ( *v2 )
    {
      result = (*((__int64 (__fastcall **)(__int64))v4 + 1))(1);
      if ( (int)result < 0 )
        return result;
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v6, 1);
      if ( (int)result < 0 )
        return result;
      i = off_180027598;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_180027588, a2);
  if ( (int)result >= 0 )
  {
    if ( ATL::_pPerfRegFunc )
      return ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hModule);
  }
  return result;
}

```

## disassembly

```asm
0x18000b3a4  mov     [rsp+arg_0], rbx
0x18000b3a9  push    rdi
0x18000b3aa  sub     rsp, 20h
0x18000b3ae  xor     eax, eax
0x18000b3b0  mov     rbx, cs:off_180027590
0x18000b3b7  mov     rcx, cs:off_180027598
0x18000b3be  cmp     rbx, rcx
0x18000b3c1  jnb     short loc_18000B40F
0x18000b3c3  mov     rdi, [rbx]
0x18000b3c6  test    rdi, rdi
0x18000b3c9  jz      short loc_18000B402
0x18000b3cb  mov     ecx, 1
0x18000b3d0  mov     rax, [rdi+8]
0x18000b3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3d9  test    eax, eax
0x18000b3db  js      short loc_18000B43B
0x18000b3dd  mov     rax, [rdi+38h]
0x18000b3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e6  mov     r8d, 1; int
0x18000b3ec  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000b3ef  mov     rcx, [rdi]; rguid
0x18000b3f2  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000b3f7  test    eax, eax
0x18000b3f9  js      short loc_18000B43B
0x18000b3fb  mov     rcx, cs:off_180027598
0x18000b402  add     rbx, 8
0x18000b406  cmp     rbx, rcx
0x18000b409  jb      short loc_18000B3C3
0x18000b40b  test    eax, eax
0x18000b40d  js      short loc_18000B43B
0x18000b40f  mov     rcx, cs:off_180027588; HINSTANCE
0x18000b416  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18000b41b  test    eax, eax
0x18000b41d  js      short loc_18000B43B
0x18000b41f  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000b426  test    rdx, rdx
0x18000b429  jz      short loc_18000B43B
0x18000b42b  mov     rcx, cs:hModule
0x18000b432  mov     rax, rdx
0x18000b435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b43a  nop
0x18000b43b  mov     rbx, [rsp+28h+arg_0]
0x18000b440  add     rsp, 20h
0x18000b444  pop     rdi
0x18000b445  retn
```
