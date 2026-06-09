# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x1800054e4`
- end: `0x180005618`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005bf0`

## callees

- `0x1800037f4`
- `0x18000399c`
- `0x1800054e4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005603`
- `OLEAUT32!__imp_SysFreeString` at `0x180005603`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800055cc`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1800055cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_18001C710;
  for ( i = off_18001C718; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
      v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      i = off_18001C718;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18001C708, a2, &bstrString, &v10);
  if ( v7 >= 0 )
  {
    libID = 0;
    v7 = ((__int64 (__fastcall *)(struct ITypeLib *, GUID **))v10->lpVtbl->GetLibAttr)(v10, &libID);
    if ( v7 >= 0 )
    {
      v7 = UnRegisterTypeLib(
             libID,
             *(_WORD *)libID[1].Data4,
             *(_WORD *)&libID[1].Data4[2],
             libID[1].Data1,
             *(SYSKIND *)&libID[1].Data2);
      ((void (__fastcall *)(struct ITypeLib *, GUID *))v10->lpVtbl->ReleaseTLibAttr)(v10, libID);
    }
  }
  if ( v10 )
    ((void (__fastcall *)(struct ITypeLib *))v10->lpVtbl->Release)(v10);
  SysFreeString(bstrString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800054e4  mov     [rsp-18h+arg_8], rbx
0x1800054e9  mov     [rsp-18h+arg_10], r8
0x1800054ee  mov     [rsp-18h+libID], rcx
0x1800054f3  push    rbp
0x1800054f4  push    rsi
0x1800054f5  push    rdi
0x1800054f6  mov     rbp, rsp
0x1800054f9  sub     rsp, 30h
0x1800054fd  xor     ebx, ebx
0x1800054ff  mov     rdi, cs:off_18001C710
0x180005506  mov     rax, cs:off_18001C718
0x18000550d  cmp     rdi, rax
0x180005510  jnb     short loc_180005568
0x180005512  mov     rsi, [rdi]
0x180005515  test    rsi, rsi
0x180005518  jz      short loc_180005557
0x18000551a  mov     rax, [rsi+38h]
0x18000551e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005523  xor     r8d, r8d; int
0x180005526  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005529  mov     rcx, [rsi]; rguid
0x18000552c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005531  mov     ebx, eax
0x180005533  test    eax, eax
0x180005535  js      loc_180005609
0x18000553b  xor     ecx, ecx
0x18000553d  mov     rax, [rsi+8]
0x180005541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005546  mov     ebx, eax
0x180005548  test    eax, eax
0x18000554a  js      loc_180005609
0x180005550  mov     rax, cs:off_18001C718
0x180005557  add     rdi, 8
0x18000555b  cmp     rdi, rax
0x18000555e  jb      short loc_180005512
0x180005560  test    ebx, ebx
0x180005562  js      loc_180005609
0x180005568  mov     [rbp+bstrString], 0
0x180005570  mov     [rbp+arg_10], 0
0x180005578  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x18000557c  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180005580  mov     rcx, cs:off_18001C708; HINSTANCE
0x180005587  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x18000558c  mov     ebx, eax
0x18000558e  test    eax, eax
0x180005590  js      short loc_1800055E9
0x180005592  mov     [rbp+libID], 0
0x18000559a  mov     rcx, [rbp+arg_10]
0x18000559e  mov     rax, [rcx]
0x1800055a1  lea     rdx, [rbp+libID]
0x1800055a5  mov     rax, [rax+38h]
0x1800055a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ae  mov     ebx, eax
0x1800055b0  test    eax, eax
0x1800055b2  js      short loc_1800055E9
0x1800055b4  mov     rcx, [rbp+libID]; libID
0x1800055b8  mov     eax, [rcx+14h]
0x1800055bb  mov     [rsp+30h+syskind], eax; syskind
0x1800055bf  mov     r9d, [rcx+10h]; lcid
0x1800055c3  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x1800055c8  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x1800055cc  call    cs:__imp_UnRegisterTypeLib
0x1800055d2  mov     ebx, eax
0x1800055d4  mov     rcx, [rbp+arg_10]
0x1800055d8  mov     rax, [rcx]
0x1800055db  mov     rdx, [rbp+libID]
0x1800055df  mov     rax, [rax+60h]
0x1800055e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055e8  nop
0x1800055e9  mov     rcx, [rbp+arg_10]
0x1800055ed  test    rcx, rcx
0x1800055f0  jz      short loc_1800055FF
0x1800055f2  mov     rax, [rcx]
0x1800055f5  mov     rax, [rax+10h]
0x1800055f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fe  nop
0x1800055ff  mov     rcx, [rbp+bstrString]; bstrString
0x180005603  call    cs:__imp_SysFreeString
0x180005609  mov     eax, ebx
0x18000560b  mov     rbx, [rsp+30h+arg_8]
0x180005610  add     rsp, 30h
0x180005614  pop     rdi
0x180005615  pop     rsi
0x180005616  pop     rbp
0x180005617  retn
```
