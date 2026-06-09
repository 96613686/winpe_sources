# ProcessSimpleTypeElement::GetAttributeValue(IXMLDOMNode *,ushort const *,ushort,tagVARIANT *)

- ea: `0x180022b30`
- end: `0x180022c24`
- name: `?GetAttributeValue@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@PEBGGPEAUtagVARIANT@@@Z`
- size: `244`
- prototype: `int(ProcessSimpleTypeElement *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058ab0`
- `0x180058ce4`
- `0x180059e04`

## callees

- `0x180022b30`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022b6b`
- `OLEAUT32!__imp_SysAllocString` at `0x180022b6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180022bfa`
- `OLEAUT32!__imp_SysFreeString` at `0x180022bfa`
- `OLEAUT32!__imp_VariantInit` at `0x180022b62`
- `OLEAUT32!__imp_VariantInit` at `0x180022b62`
- `OLEAUT32!__imp_VariantClear` at `0x180022bea`
- `OLEAUT32!__imp_VariantClear` at `0x180022bea`
- `OLEAUT32!__imp_VariantCopy` at `0x180022bde`
- `OLEAUT32!__imp_VariantCopy` at `0x180022bde`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180022bd6`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180022bd6`

## pseudocode

```c
__int64 __fastcall ProcessSimpleTypeElement::GetAttributeValue(
        ProcessSimpleTypeElement *this,
        const OLECHAR *a2,
        const unsigned __int16 *a3,
        VARIANTARG *a4)
{
  VARTYPE vt; // di
  OLECHAR *v8; // rsi
  int v9; // ebx
  HRESULT v10; // eax
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF

  v12 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  vt = (unsigned __int16)a3;
  VariantInit(&pvarg);
  v8 = SysAllocString(a2);
  if ( v8 )
  {
    v9 = (**(__int64 (__fastcall ***)(ProcessSimpleTypeElement *, GUID *, __int64 *))this)(
           this,
           &IID_IXMLDOMElement,
           &v12);
    if ( v9 >= 0 && v12 )
      v9 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v12 + 352LL))(v12, v8, &pvarg);
    if ( !v9 )
    {
      if ( pvarg.vt == vt )
        v10 = VariantCopy(a4, &pvarg);
      else
        v10 = VariantChangeTypeEx(a4, &pvarg, 0x7Fu, 0, vt);
      v9 = v10;
      VariantClear(&pvarg);
    }
  }
  else
  {
    v9 = -2147024882;
  }
  SysFreeString(v8);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180022b30  push    rbp
0x180022b32  push    rbx
0x180022b33  push    rsi
0x180022b34  push    rdi
0x180022b35  push    r14
0x180022b37  push    r15
0x180022b39  mov     rbp, rsp
0x180022b3c  sub     rsp, 58h
0x180022b40  xor     eax, eax
0x180022b42  mov     r15, rcx
0x180022b45  xorps   xmm0, xmm0
0x180022b48  mov     qword ptr [rbp+pvarg+10h], rax
0x180022b4c  lea     rcx, [rbp+pvarg]; pvarg
0x180022b50  mov     [rbp+var_28], rax
0x180022b54  movups  xmmword ptr [rbp+pvarg], xmm0
0x180022b58  mov     r14, r9
0x180022b5b  movzx   edi, r8w
0x180022b5f  mov     rbx, rdx
0x180022b62  call    cs:__imp_VariantInit
0x180022b68  mov     rcx, rbx; psz
0x180022b6b  call    cs:__imp_SysAllocString
0x180022b71  mov     rsi, rax
0x180022b74  test    rax, rax
0x180022b77  jz      short loc_180022BF2
0x180022b79  mov     rcx, [r15]
0x180022b7c  lea     r8, [rbp+var_28]
0x180022b80  lea     rdx, IID_IXMLDOMElement
0x180022b87  mov     rax, [rcx]
0x180022b8a  mov     rcx, r15
0x180022b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b92  mov     ebx, eax
0x180022b94  test    eax, eax
0x180022b96  js      short loc_180022BB9
0x180022b98  mov     rcx, [rbp+var_28]
0x180022b9c  test    rcx, rcx
0x180022b9f  jz      short loc_180022BB9
0x180022ba1  mov     rax, [rcx]
0x180022ba4  lea     r8, [rbp+pvarg]
0x180022ba8  mov     rdx, rsi
0x180022bab  mov     rax, [rax+160h]
0x180022bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bb7  mov     ebx, eax
0x180022bb9  test    ebx, ebx
0x180022bbb  jnz     short loc_180022BF7
0x180022bbd  lea     rdx, [rbp+pvarg]; pvargSrc
0x180022bc1  mov     rcx, r14; pvargDest
0x180022bc4  cmp     word ptr [rbp+pvarg], di
0x180022bc8  jz      short loc_180022BDE
0x180022bca  xor     r9d, r9d; wFlags
0x180022bcd  mov     [rsp+58h+vt], di; vt
0x180022bd2  lea     r8d, [rbx+7Fh]; lcid
0x180022bd6  call    cs:__imp_VariantChangeTypeEx
0x180022bdc  jmp     short loc_180022BE4
0x180022bde  call    cs:__imp_VariantCopy
0x180022be4  lea     rcx, [rbp+pvarg]; pvarg
0x180022be8  mov     ebx, eax
0x180022bea  call    cs:__imp_VariantClear
0x180022bf0  jmp     short loc_180022BF7
0x180022bf2  mov     ebx, 8007000Eh
0x180022bf7  mov     rcx, rsi; bstrString
0x180022bfa  call    cs:__imp_SysFreeString
0x180022c00  mov     rcx, [rbp+var_28]
0x180022c04  test    rcx, rcx
0x180022c07  jz      short loc_180022C15
0x180022c09  mov     rax, [rcx]
0x180022c0c  mov     rax, [rax+10h]
0x180022c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c15  mov     eax, ebx
0x180022c17  add     rsp, 58h
0x180022c1b  pop     r15
0x180022c1d  pop     r14
0x180022c1f  pop     rdi
0x180022c20  pop     rsi
0x180022c21  pop     rbx
0x180022c22  pop     rbp
0x180022c23  retn
```
