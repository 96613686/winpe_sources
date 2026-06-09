# Dynamo::StateEntry::SetValue(tagVARIANT const &)

- ea: `0x1800f6a20`
- end: `0x1800f6b2b`
- name: `?SetValue@StateEntry@Dynamo@@UEAAXAEBUtagVARIANT@@@Z`
- size: `267`
- prototype: `void(Dynamo::StateEntry *__hidden this, const struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180023874`
- `0x1800f6a20`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f6a70`
- `OLEAUT32!__imp_VariantInit` at `0x1800f6a70`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6b13`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6b13`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800f6a93`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800f6a93`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800f6ac2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800f6ac2`
- `DMCmnUtils!OmaDmRegistrySetBinary` at `0x1800f6ae4`
- `DMCmnUtils!OmaDmRegistrySetBinary` at `0x1800f6ae4`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800f6a41`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800f6a41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dynamo::StateEntry::SetValue(HKEY *this, const struct tagVARIANT *a2)
{
  int v4; // eax
  HRESULT v5; // eax
  UINT v6; // eax
  int v7; // eax
  int vt; // [rsp+20h] [rbp-38h]
  int vta; // [rsp+20h] [rbp-38h]
  int vtb; // [rsp+20h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = OmaDmRegistrySetDWORD(this[1], 0, L"VarType", a2->vt);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v4,
      vt);
  VariantInit(&pvarg);
  v5 = VariantChangeTypeEx(&pvarg, a2, 0x7Fu, 0, 8u);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v5,
      vta);
  v6 = SysStringByteLen(pvarg.bstrVal);
  v7 = OmaDmRegistrySetBinary(this[1], 0, L"Data", pvarg.bstrVal, v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
      (const char *)(unsigned int)v7,
      vtb);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x1800f6a20  mov     [rsp+arg_0], rbx
0x1800f6a25  push    rdi
0x1800f6a26  sub     rsp, 50h
0x1800f6a2a  mov     rbx, rdx
0x1800f6a2d  mov     rdi, rcx
0x1800f6a30  movzx   r9d, word ptr [rdx]
0x1800f6a34  lea     r8, aVartype; "VarType"
0x1800f6a3b  xor     edx, edx
0x1800f6a3d  mov     rcx, [rcx+8]
0x1800f6a41  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800f6a48  nop     dword ptr [rax+rax+00h]
0x1800f6a4d  mov     rcx, [rsp+58h]; this
0x1800f6a52  test    eax, eax
0x1800f6a54  jns     short loc_1800F6A6B
0x1800f6a56  mov     r9d, eax; char *
0x1800f6a59  lea     r8, aOnecoreuapAdmi_112; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f6a60  mov     edx, 32h ; '2'; void *
0x1800f6a65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6a6b  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800f6a70  call    cs:__imp_VariantInit
0x1800f6a77  nop     dword ptr [rax+rax+00h]
0x1800f6a7c  nop
0x1800f6a7d  xor     r9d, r9d; wFlags
0x1800f6a80  mov     [rsp+58h+vt], 8; int
0x1800f6a87  lea     r8d, [r9+7Fh]; lcid
0x1800f6a8b  mov     rdx, rbx; pvarSrc
0x1800f6a8e  lea     rcx, [rsp+58h+pvarg]; pvargDest
0x1800f6a93  call    cs:__imp_VariantChangeTypeEx
0x1800f6a9a  nop     dword ptr [rax+rax+00h]
0x1800f6a9f  mov     rcx, [rsp+58h]; this
0x1800f6aa4  test    eax, eax
0x1800f6aa6  jns     short loc_1800F6ABD
0x1800f6aa8  mov     r9d, eax; char *
0x1800f6aab  lea     r8, aOnecoreuapAdmi_112; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f6ab2  mov     edx, 35h ; '5'; void *
0x1800f6ab7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6abd  mov     rcx, qword ptr [rsp+58h+pvarg+8]; bstr
0x1800f6ac2  call    cs:__imp_SysStringByteLen
0x1800f6ac9  nop     dword ptr [rax+rax+00h]
0x1800f6ace  mov     dword ptr [rsp+58h+vt], eax; int
0x1800f6ad2  mov     r9, qword ptr [rsp+58h+pvarg+8]
0x1800f6ad7  lea     r8, aData; "Data"
0x1800f6ade  xor     edx, edx
0x1800f6ae0  mov     rcx, [rdi+8]
0x1800f6ae4  call    cs:__imp_?OmaDmRegistrySetBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z; OmaDmRegistrySetBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x1800f6aeb  nop     dword ptr [rax+rax+00h]
0x1800f6af0  mov     rcx, [rsp+58h]; this
0x1800f6af5  test    eax, eax
0x1800f6af7  jns     short loc_1800F6B0E
0x1800f6af9  mov     r9d, eax; char *
0x1800f6afc  lea     r8, aOnecoreuapAdmi_112; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f6b03  mov     edx, 3Ah ; ':'; void *
0x1800f6b08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6b0e  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800f6b13  call    cs:__imp_VariantClear
0x1800f6b1a  nop     dword ptr [rax+rax+00h]
0x1800f6b1f  mov     rbx, [rsp+58h+arg_0]
0x1800f6b24  add     rsp, 50h
0x1800f6b28  pop     rdi
0x1800f6b29  retn
```
