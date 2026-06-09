# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x1400061fc`
- end: `0x14000632e`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005ce4`

## callees

- `0x140005384`
- `0x14000552c`
- `0x1400061fc`
- `0x140007010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140006319`
- `OLEAUT32!__imp_SysFreeString` at `0x140006319`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1400062e4`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x1400062e4`

## pseudocode

```c
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
  v3 = off_14000B100;
  for ( i = off_14000B108; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
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
      i = off_14000B108;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_14000B0F8, a2, &bstrString, &v10);
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
0x1400061fc  mov     [rsp-18h+arg_8], rbx
0x140006201  mov     [rsp-18h+arg_10], r8
0x140006206  mov     [rsp-18h+libID], rcx
0x14000620b  push    rbp
0x14000620c  push    rsi
0x14000620d  push    rdi
0x14000620e  mov     rbp, rsp
0x140006211  sub     rsp, 30h
0x140006215  mov     rdi, cs:off_14000B100
0x14000621c  xor     ebx, ebx
0x14000621e  mov     rax, cs:off_14000B108
0x140006225  cmp     rdi, rax
0x140006228  jnb     short loc_140006280
0x14000622a  mov     rsi, [rdi]
0x14000622d  test    rsi, rsi
0x140006230  jz      short loc_14000626F
0x140006232  mov     rax, [rsi+38h]
0x140006236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000623b  mov     rcx, [rsi]; rguid
0x14000623e  xor     r8d, r8d; int
0x140006241  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x140006244  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x140006249  mov     ebx, eax
0x14000624b  test    eax, eax
0x14000624d  js      loc_14000631F
0x140006253  mov     rax, [rsi+8]
0x140006257  xor     ecx, ecx
0x140006259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000625e  mov     ebx, eax
0x140006260  test    eax, eax
0x140006262  js      loc_14000631F
0x140006268  mov     rax, cs:off_14000B108
0x14000626f  add     rdi, 8
0x140006273  cmp     rdi, rax
0x140006276  jb      short loc_14000622A
0x140006278  test    ebx, ebx
0x14000627a  js      loc_14000631F
0x140006280  mov     rcx, cs:off_14000B0F8; HINSTANCE
0x140006287  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x14000628b  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14000628f  mov     [rbp+bstrString], 0
0x140006297  mov     [rbp+arg_10], 0
0x14000629f  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x1400062a4  mov     ebx, eax
0x1400062a6  test    eax, eax
0x1400062a8  js      short loc_140006300
0x1400062aa  mov     rcx, [rbp+arg_10]
0x1400062ae  lea     rdx, [rbp+libID]
0x1400062b2  mov     [rbp+libID], 0
0x1400062ba  mov     rax, [rcx]
0x1400062bd  mov     rax, [rax+38h]
0x1400062c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062c6  mov     ebx, eax
0x1400062c8  test    eax, eax
0x1400062ca  js      short loc_140006300
0x1400062cc  mov     rcx, [rbp+libID]; libID
0x1400062d0  mov     eax, [rcx+14h]
0x1400062d3  mov     r9d, [rcx+10h]; lcid
0x1400062d7  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x1400062dc  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x1400062e0  mov     [rsp+30h+syskind], eax; syskind
0x1400062e4  call    cs:__imp_UnRegisterTypeLib
0x1400062ea  mov     rcx, [rbp+arg_10]
0x1400062ee  mov     ebx, eax
0x1400062f0  mov     rdx, [rbp+libID]
0x1400062f4  mov     rax, [rcx]
0x1400062f7  mov     rax, [rax+60h]
0x1400062fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006300  mov     rcx, [rbp+arg_10]
0x140006304  test    rcx, rcx
0x140006307  jz      short loc_140006315
0x140006309  mov     rax, [rcx]
0x14000630c  mov     rax, [rax+10h]
0x140006310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006315  mov     rcx, [rbp+bstrString]; bstrString
0x140006319  call    cs:__imp_SysFreeString
0x14000631f  mov     eax, ebx
0x140006321  mov     rbx, [rsp+30h+arg_8]
0x140006326  add     rsp, 30h
0x14000632a  pop     rdi
0x14000632b  pop     rsi
0x14000632c  pop     rbp
0x14000632d  retn
```
