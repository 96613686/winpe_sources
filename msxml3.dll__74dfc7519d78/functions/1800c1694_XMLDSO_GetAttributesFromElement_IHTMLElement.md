# XMLDSO::GetAttributesFromElement(IHTMLElement *)

- ea: `0x1800c1694`
- end: `0x1800c1783`
- name: `?GetAttributesFromElement@XMLDSO@@QEAAXPEAUIHTMLElement@@@Z`
- size: `239`
- prototype: `void(XMLDSO *__hidden this, struct IHTMLElement *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180092ea0`

## callees

- `0x180094c8c`
- `0x1800c1694`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800c1715`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1772`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1715`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1772`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c16f1`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c1749`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c16f1`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800c1749`

## string_xrefs

- `0x1800c16b4`: `JavaDSOCompatible`

## pseudocode

```c
void __fastcall XMLDSO::GetAttributesFromElement(XMLDSO *this, struct IHTMLElement *a2)
{
  BOOL v4; // eax
  int v5; // ecx
  VARIANTARG pvargDest; // [rsp+30h] [rbp-20h] BYREF

  if ( a2 )
  {
    memset(&pvargDest, 0, sizeof(pvargDest));
    if ( GetExpandoProperty(a2, L"JavaDSOCompatible", &pvargDest) >= 0
      && VariantChangeTypeEx(&pvargDest, &pvargDest, 0x409u, 0, 0xBu) >= 0 )
    {
      v4 = pvargDest.iVal != 0;
      *((_DWORD *)this + 32) &= ~1u;
      *((_DWORD *)this + 32) |= v4;
    }
    VariantClear(&pvargDest);
    if ( GetExpandoProperty(a2, L"normalizeWhiteSpace", &pvargDest) >= 0
      && VariantChangeTypeEx(&pvargDest, &pvargDest, 0x409u, 0, 0xBu) >= 0 )
    {
      v5 = -(pvargDest.iVal != 0);
      *((_DWORD *)this + 32) &= ~2u;
      *((_DWORD *)this + 32) |= ~(_BYTE)v5 & 2;
    }
    VariantClear(&pvargDest);
  }
}

```

## disassembly

```asm
0x1800c1694  test    rdx, rdx
0x1800c1697  jz      locret_1800C1782
0x1800c169d  push    rbp
0x1800c169e  push    rbx
0x1800c169f  push    rsi
0x1800c16a0  push    rdi
0x1800c16a1  push    r15
0x1800c16a3  mov     rbp, rsp
0x1800c16a6  sub     rsp, 50h
0x1800c16aa  mov     rdi, rdx
0x1800c16ad  lea     r8, [rbp+pvargDest]; struct tagVARIANT *
0x1800c16b1  mov     rbx, rcx
0x1800c16b4  lea     rdx, aJavadsocompati; "JavaDSOCompatible"
0x1800c16bb  xorps   xmm0, xmm0
0x1800c16be  xor     eax, eax
0x1800c16c0  mov     rcx, rdi; struct IHTMLElement *
0x1800c16c3  mov     qword ptr [rbp+pvargDest+10h], rax
0x1800c16c7  xor     esi, esi
0x1800c16c9  movups  xmmword ptr [rbp+pvargDest], xmm0
0x1800c16cd  call    ?GetExpandoProperty@@YAJPEAUIHTMLElement@@PEBGPEAUtagVARIANT@@@Z; GetExpandoProperty(IHTMLElement *,ushort const *,tagVARIANT *)
0x1800c16d2  lea     r15d, [rsi+0Bh]
0x1800c16d6  test    eax, eax
0x1800c16d8  js      short loc_1800C1711
0x1800c16da  xor     r9d, r9d; wFlags
0x1800c16dd  mov     [rsp+50h+vt], r15w; vt
0x1800c16e3  mov     r8d, 409h; lcid
0x1800c16e9  lea     rdx, [rbp+pvargDest]; pvarSrc
0x1800c16ed  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800c16f1  call    cs:__imp_VariantChangeTypeEx
0x1800c16f7  test    eax, eax
0x1800c16f9  js      short loc_1800C1711
0x1800c16fb  cmp     word ptr [rbp+pvargDest+8], si
0x1800c16ff  mov     eax, esi
0x1800c1701  setnz   al
0x1800c1704  and     dword ptr [rbx+80h], 0FFFFFFFEh
0x1800c170b  or      [rbx+80h], eax
0x1800c1711  lea     rcx, [rbp+pvargDest]; pvarg
0x1800c1715  call    cs:__imp_VariantClear
0x1800c171b  lea     r8, [rbp+pvargDest]; struct tagVARIANT *
0x1800c171f  mov     rcx, rdi; struct IHTMLElement *
0x1800c1722  lea     rdx, aNormalizewhite; "normalizeWhiteSpace"
0x1800c1729  call    ?GetExpandoProperty@@YAJPEAUIHTMLElement@@PEBGPEAUtagVARIANT@@@Z; GetExpandoProperty(IHTMLElement *,ushort const *,tagVARIANT *)
0x1800c172e  test    eax, eax
0x1800c1730  js      short loc_1800C176E
0x1800c1732  xor     r9d, r9d; wFlags
0x1800c1735  mov     [rsp+50h+vt], r15w; vt
0x1800c173b  mov     r8d, 409h; lcid
0x1800c1741  lea     rdx, [rbp+pvargDest]; pvarSrc
0x1800c1745  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800c1749  call    cs:__imp_VariantChangeTypeEx
0x1800c174f  test    eax, eax
0x1800c1751  js      short loc_1800C176E
0x1800c1753  movzx   eax, word ptr [rbp+pvargDest+8]
0x1800c1757  neg     ax
0x1800c175a  sbb     ecx, ecx
0x1800c175c  and     dword ptr [rbx+80h], 0FFFFFFFDh
0x1800c1763  not     ecx
0x1800c1765  and     ecx, 2
0x1800c1768  or      [rbx+80h], ecx
0x1800c176e  lea     rcx, [rbp+pvargDest]; pvarg
0x1800c1772  call    cs:__imp_VariantClear
0x1800c1778  add     rsp, 50h
0x1800c177c  pop     r15
0x1800c177e  pop     rdi
0x1800c177f  pop     rsi
0x1800c1780  pop     rbx
0x1800c1781  pop     rbp
0x1800c1782  retn
```
