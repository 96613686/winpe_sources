# ProcessSimpleTypeElement::GetNodeValue(IXMLDOMNode *,ushort,tagVARIANT *)

- ea: `0x180059d68`
- end: `0x180059dfe`
- name: `?GetNodeValue@ProcessSimpleTypeElement@@YAJPEAUIXMLDOMNode@@GPEAUtagVARIANT@@@Z`
- size: `150`
- prototype: `int(ProcessSimpleTypeElement *__hidden this, struct IXMLDOMNode *, unsigned __int16, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180059604`
- `0x180059f6c`
- `0x180059fd8`

## callees

- `0x180059d68`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180059d93`
- `OLEAUT32!__imp_VariantInit` at `0x180059d93`
- `OLEAUT32!__imp_VariantClear` at `0x180059de6`
- `OLEAUT32!__imp_VariantClear` at `0x180059de6`
- `OLEAUT32!__imp_VariantCopy` at `0x180059dd9`
- `OLEAUT32!__imp_VariantCopy` at `0x180059dd9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180059dd1`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180059dd1`

## pseudocode

```c
__int64 __fastcall ProcessSimpleTypeElement::GetNodeValue(
        ProcessSimpleTypeElement *this,
        struct IXMLDOMNode *a2,
        VARIANTARG *a3,
        struct tagVARIANT *a4)
{
  VARTYPE vt; // di
  int v7; // ebx
  HRESULT v8; // eax
  VARIANTARG pvarSrc; // [rsp+30h] [rbp-28h] BYREF

  memset(&pvarSrc, 0, sizeof(pvarSrc));
  vt = (unsigned __int16)a2;
  VariantInit(&pvarSrc);
  v7 = (*(__int64 (__fastcall **)(ProcessSimpleTypeElement *, VARIANTARG *))(*(_QWORD *)this + 240LL))(this, &pvarSrc);
  if ( v7 >= 0 )
  {
    if ( pvarSrc.vt == vt )
      v8 = VariantCopy(a3, &pvarSrc);
    else
      v8 = VariantChangeTypeEx(a3, &pvarSrc, 0x7Fu, 0, vt);
    v7 = v8;
    VariantClear(&pvarSrc);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180059d68  mov     r11, rsp
0x180059d6b  mov     [r11+8], rbx
0x180059d6f  mov     [r11+10h], rsi
0x180059d73  push    rdi
0x180059d74  sub     rsp, 50h
0x180059d78  xorps   xmm0, xmm0
0x180059d7b  mov     rbx, rcx
0x180059d7e  xor     eax, eax
0x180059d80  lea     rcx, [r11-28h]; pvarg
0x180059d84  movups  xmmword ptr [rsp+58h+pvarSrc], xmm0
0x180059d89  mov     [r11-18h], rax
0x180059d8d  mov     rsi, r8
0x180059d90  movzx   edi, dx
0x180059d93  call    cs:__imp_VariantInit
0x180059d99  mov     rax, [rbx]
0x180059d9c  lea     rdx, [rsp+58h+pvarSrc]
0x180059da1  mov     rcx, rbx
0x180059da4  mov     rax, [rax+0F0h]
0x180059dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059db0  mov     ebx, eax
0x180059db2  test    eax, eax
0x180059db4  js      short loc_180059DEC
0x180059db6  lea     rdx, [rsp+58h+pvarSrc]; pvargSrc
0x180059dbb  mov     rcx, rsi; pvargDest
0x180059dbe  cmp     word ptr [rsp+58h+pvarSrc], di
0x180059dc3  jz      short loc_180059DD9
0x180059dc5  xor     r9d, r9d; wFlags
0x180059dc8  mov     [rsp+58h+vt], di; vt
0x180059dcd  lea     r8d, [r9+7Fh]; lcid
0x180059dd1  call    cs:__imp_VariantChangeTypeEx
0x180059dd7  jmp     short loc_180059DDF
0x180059dd9  call    cs:__imp_VariantCopy
0x180059ddf  lea     rcx, [rsp+58h+pvarSrc]; pvarg
0x180059de4  mov     ebx, eax
0x180059de6  call    cs:__imp_VariantClear
0x180059dec  mov     rsi, [rsp+58h+arg_8]
0x180059df1  mov     eax, ebx
0x180059df3  mov     rbx, [rsp+58h+arg_0]
0x180059df8  add     rsp, 50h
0x180059dfc  pop     rdi
0x180059dfd  retn
```
