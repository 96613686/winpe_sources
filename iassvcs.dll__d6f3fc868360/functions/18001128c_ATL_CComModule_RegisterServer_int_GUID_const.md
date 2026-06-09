# ATL::CComModule::RegisterServer(int,_GUID const *)

- ea: `0x18001128c`
- end: `0x18001137e`
- name: `?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(ATL::CComModule *this, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013280`

## callees

- `0x18000eb5c`
- `0x18000f024`
- `0x18001128c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::RegisterServer(
        ATL::CComModule *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  __int64 *v6; // rbx
  __int64 *i; // rcx
  __int64 v8; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v9; // rax

  v3 = qword_180024F98;
  if ( qword_180024F98 )
  {
    while ( *(_QWORD *)v3 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v3 + 8))(1);
      if ( (int)result < 0 )
        return result;
      v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v5, 1);
      if ( (int)result < 0 )
        return result;
      v3 += 72;
    }
  }
  v6 = off_1800243F0[0];
  for ( i = off_1800243F8; v6 < i; ++v6 )
  {
    v8 = *v6;
    if ( *v6 )
    {
      result = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const struct _GUID *))(v8 + 8))(1, a2, a3);
      if ( (int)result < 0 )
        return result;
      v9 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v8 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v8, v9, 1);
      if ( (int)result < 0 )
        return result;
      i = off_1800243F8;
    }
  }
  result = ATL::AtlRegisterTypeLib(off_1800243E8, a2);
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
0x18001128c  mov     [rsp+arg_0], rbx
0x180011291  push    rdi
0x180011292  sub     rsp, 20h
0x180011296  mov     rbx, cs:qword_180024F98
0x18001129d  test    rbx, rbx
0x1800112a0  jz      short loc_1800112E6
0x1800112a2  jmp     short loc_1800112E0
0x1800112a4  mov     ecx, 1
0x1800112a9  mov     rax, [rbx+8]
0x1800112ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b2  test    eax, eax
0x1800112b4  js      loc_180011373
0x1800112ba  mov     rax, [rbx+38h]
0x1800112be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c3  mov     r8d, 1; int
0x1800112c9  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800112cc  mov     rcx, [rbx]; rguid
0x1800112cf  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800112d4  test    eax, eax
0x1800112d6  js      loc_180011373
0x1800112dc  add     rbx, 48h ; 'H'
0x1800112e0  cmp     qword ptr [rbx], 0
0x1800112e4  jnz     short loc_1800112A4
0x1800112e6  xor     eax, eax
0x1800112e8  mov     rbx, cs:off_1800243F0
0x1800112ef  mov     rcx, cs:off_1800243F8
0x1800112f6  cmp     rbx, rcx
0x1800112f9  jnb     short loc_180011347
0x1800112fb  mov     rdi, [rbx]
0x1800112fe  test    rdi, rdi
0x180011301  jz      short loc_18001133A
0x180011303  mov     ecx, 1
0x180011308  mov     rax, [rdi+8]
0x18001130c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011311  test    eax, eax
0x180011313  js      short loc_180011373
0x180011315  mov     rax, [rdi+38h]
0x180011319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001131e  mov     r8d, 1; int
0x180011324  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180011327  mov     rcx, [rdi]; rguid
0x18001132a  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001132f  test    eax, eax
0x180011331  js      short loc_180011373
0x180011333  mov     rcx, cs:off_1800243F8
0x18001133a  add     rbx, 8
0x18001133e  cmp     rbx, rcx
0x180011341  jb      short loc_1800112FB
0x180011343  test    eax, eax
0x180011345  js      short loc_180011373
0x180011347  mov     rcx, cs:off_1800243E8; HINSTANCE
0x18001134e  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180011353  test    eax, eax
0x180011355  js      short loc_180011373
0x180011357  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18001135e  test    rdx, rdx
0x180011361  jz      short loc_180011373
0x180011363  mov     rcx, cs:hModule
0x18001136a  mov     rax, rdx
0x18001136d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011372  nop
0x180011373  mov     rbx, [rsp+28h+arg_0]
0x180011378  add     rsp, 20h
0x18001137c  pop     rdi
0x18001137d  retn
```
