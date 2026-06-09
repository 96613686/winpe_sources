# ATL::CAtlModuleT<ATL::CComModule>::UnregisterServer(int,_GUID const *)

- ea: `0x18000bee4`
- end: `0x18000bf76`
- name: `?UnregisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `146`
- prototype: `int __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c780`

## callees

- `0x1800099a8`
- `0x180009ea0`
- `0x18000bee4`
- `0x18001c010`

## pseudocode

```c
int __fastcall ATL::CAtlModuleT<ATL::CComModule>::UnregisterServer(__int64 a1, const unsigned __int16 *a2)
{
  int result; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rbx
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  if ( !ATL::_pPerfUnRegFunc || (result = ATL::_pPerfUnRegFunc(), result >= 0) )
  {
    v3 = off_180027590;
    for ( i = off_180027598; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
        result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( result < 0 )
          return result;
        result = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
        if ( result < 0 )
          return result;
        i = off_180027598;
      }
    }
    return ATL::AtlUnRegisterTypeLib(off_180027588, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000bee4  mov     [rsp+arg_0], rbx
0x18000bee9  push    rdi
0x18000beea  sub     rsp, 20h
0x18000beee  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000bef5  test    rax, rax
0x18000bef8  jz      short loc_18000BF03
0x18000befa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beff  test    eax, eax
0x18000bf01  js      short loc_18000BF6B
0x18000bf03  xor     eax, eax
0x18000bf05  mov     rbx, cs:off_180027590
0x18000bf0c  mov     rcx, cs:off_180027598
0x18000bf13  cmp     rbx, rcx
0x18000bf16  jnb     short loc_18000BF5E
0x18000bf18  mov     rdi, [rbx]
0x18000bf1b  test    rdi, rdi
0x18000bf1e  jz      short loc_18000BF51
0x18000bf20  mov     rax, [rdi+38h]
0x18000bf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf29  xor     r8d, r8d; int
0x18000bf2c  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000bf2f  mov     rcx, [rdi]; rguid
0x18000bf32  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000bf37  test    eax, eax
0x18000bf39  js      short loc_18000BF6B
0x18000bf3b  xor     ecx, ecx
0x18000bf3d  mov     rax, [rdi+8]
0x18000bf41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf46  test    eax, eax
0x18000bf48  js      short loc_18000BF6B
0x18000bf4a  mov     rcx, cs:off_180027598
0x18000bf51  add     rbx, 8
0x18000bf55  cmp     rbx, rcx
0x18000bf58  jb      short loc_18000BF18
0x18000bf5a  test    eax, eax
0x18000bf5c  js      short loc_18000BF6B
0x18000bf5e  mov     rcx, cs:off_180027588; HINSTANCE
0x18000bf65  call    ?AtlUnRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlUnRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18000bf6a  nop
0x18000bf6b  mov     rbx, [rsp+28h+arg_0]
0x18000bf70  add     rsp, 20h
0x18000bf74  pop     rdi
0x18000bf75  retn
```
