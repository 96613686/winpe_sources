# CSlowLinkConfigInfo::_AddInfoToPathMap(CPathMap &,ushort const *,CSlowLinkConfigInfo::INFO const &)

- ea: `0x180060a3c`
- end: `0x180060b65`
- name: `?_AddInfoToPathMap@CSlowLinkConfigInfo@@AEAAJAEAVCPathMap@@PEBGAEBUINFO@1@@Z`
- size: `297`
- prototype: `int(CSlowLinkConfigInfo *__hidden this, struct CPathMap *, const unsigned __int16 *, const struct CSlowLinkConfigInfo::INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011070`
- `0x180011298`

## callees

- `0x180057ba0`
- `0x180060a3c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180060b19`
- `OLEAUT32!__imp_VariantInit` at `0x180060b19`
- `OLEAUT32!__imp_VariantClear` at `0x180060b41`
- `OLEAUT32!__imp_VariantClear` at `0x180060b41`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180060b4c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180060b4c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180060aa8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180060ad7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180060afc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180060aa8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180060ad7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180060afc`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180060a71`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180060a71`

## pseudocode

```c
__int64 __fastcall CSlowLinkConfigInfo::_AddInfoToPathMap(
        CSlowLinkConfigInfo *this,
        struct CPathMap *a2,
        const unsigned __int16 *a3,
        const struct CSlowLinkConfigInfo::INFO *a4)
{
  int v4; // ebx
  SAFEARRAY *Vector; // rsi
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  CSlowLinkConfigInfo *rgIndices; // [rsp+70h] [rbp+30h] BYREF
  __int64 pv; // [rsp+88h] [rbp+48h] BYREF

  rgIndices = this;
  v4 = 0;
  if ( *(_QWORD *)a4 )
  {
    Vector = SafeArrayCreateVector(0x15u, 0, 3u);
    if ( Vector )
    {
      if ( (*(_BYTE *)a4 & 1) != 0 )
      {
        pv = *((_QWORD *)a4 + 1);
        LODWORD(rgIndices) = 1;
        v4 = SafeArrayPutElement(Vector, (LONG *)&rgIndices, &pv);
        if ( v4 < 0 )
          goto LABEL_10;
      }
      if ( (*(_BYTE *)a4 & 2) != 0
        && (pv = *((_QWORD *)a4 + 2),
            LODWORD(rgIndices) = 2,
            v4 = SafeArrayPutElement(Vector, (LONG *)&rgIndices, &pv),
            v4 < 0)
        || (pv = *(_QWORD *)a4, LODWORD(rgIndices) = 0,
                                v4 = SafeArrayPutElement(Vector, (LONG *)&rgIndices, &pv),
                                v4 < 0) )
      {
LABEL_10:
        SafeArrayDestroy(Vector);
      }
      else
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.llVal = (LONGLONG)Vector;
        pvarg.vt = 8213;
        v4 = CPathMap::AddPath(a2, a3, &pvarg);
        VariantClear(&pvarg);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180060a3c  mov     [rsp-28h+arg_8], rbx
0x180060a41  mov     [rsp-28h+rgIndices], rcx
0x180060a46  push    rbp
0x180060a47  push    rsi
0x180060a48  push    rdi
0x180060a49  push    r14
0x180060a4b  push    r15
0x180060a4d  mov     rbp, rsp
0x180060a50  sub     rsp, 40h
0x180060a54  xor     ebx, ebx
0x180060a56  mov     rdi, r9
0x180060a59  mov     r14, r8
0x180060a5c  mov     r15, rdx
0x180060a5f  cmp     [r9], rbx
0x180060a62  jz      loc_180060B52
0x180060a68  lea     ecx, [rbx+15h]; vt
0x180060a6b  xor     edx, edx; lLbound
0x180060a6d  lea     r8d, [rbx+3]; cElements
0x180060a71  call    cs:__imp_SafeArrayCreateVector
0x180060a77  mov     rsi, rax
0x180060a7a  test    rax, rax
0x180060a7d  jnz     short loc_180060A89
0x180060a7f  mov     ebx, 8007000Eh
0x180060a84  jmp     loc_180060B52
0x180060a89  test    byte ptr [rdi], 1
0x180060a8c  jz      short loc_180060AB8
0x180060a8e  mov     rax, [rdi+8]
0x180060a92  lea     r8, [rbp+pv]; pv
0x180060a96  lea     rdx, [rbp+rgIndices]; rgIndices
0x180060a9a  mov     [rbp+pv], rax
0x180060a9e  mov     rcx, rsi; psa
0x180060aa1  mov     dword ptr [rbp+rgIndices], 1
0x180060aa8  call    cs:__imp_SafeArrayPutElement
0x180060aae  mov     ebx, eax
0x180060ab0  test    eax, eax
0x180060ab2  js      loc_180060B49
0x180060ab8  test    byte ptr [rdi], 2
0x180060abb  jz      short loc_180060AE3
0x180060abd  mov     rax, [rdi+10h]
0x180060ac1  lea     r8, [rbp+pv]; pv
0x180060ac5  lea     rdx, [rbp+rgIndices]; rgIndices
0x180060ac9  mov     [rbp+pv], rax
0x180060acd  mov     rcx, rsi; psa
0x180060ad0  mov     dword ptr [rbp+rgIndices], 2
0x180060ad7  call    cs:__imp_SafeArrayPutElement
0x180060add  mov     ebx, eax
0x180060adf  test    eax, eax
0x180060ae1  js      short loc_180060B49
0x180060ae3  mov     rax, [rdi]
0x180060ae6  lea     r8, [rbp+pv]; pv
0x180060aea  lea     rdx, [rbp+rgIndices]; rgIndices
0x180060aee  mov     [rbp+pv], rax
0x180060af2  mov     rcx, rsi; psa
0x180060af5  mov     dword ptr [rbp+rgIndices], 0
0x180060afc  call    cs:__imp_SafeArrayPutElement
0x180060b02  mov     ebx, eax
0x180060b04  test    eax, eax
0x180060b06  js      short loc_180060B49
0x180060b08  xorps   xmm0, xmm0
0x180060b0b  lea     rcx, [rbp+pvarg]; pvarg
0x180060b0f  xor     eax, eax
0x180060b11  movups  xmmword ptr [rbp+pvarg], xmm0
0x180060b15  mov     qword ptr [rbp+pvarg+10h], rax
0x180060b19  call    cs:__imp_VariantInit
0x180060b1f  mov     eax, 2015h
0x180060b24  mov     qword ptr [rbp+pvarg+8], rsi
0x180060b28  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180060b2c  mov     word ptr [rbp+pvarg], ax
0x180060b30  mov     rdx, r14; unsigned __int16 *
0x180060b33  mov     rcx, r15; this
0x180060b36  call    ?AddPath@CPathMap@@QEAAJPEBGAEBUtagVARIANT@@@Z; CPathMap::AddPath(ushort const *,tagVARIANT const &)
0x180060b3b  lea     rcx, [rbp+pvarg]; pvarg
0x180060b3f  mov     ebx, eax
0x180060b41  call    cs:__imp_VariantClear
0x180060b47  jmp     short loc_180060B52
0x180060b49  mov     rcx, rsi; psa
0x180060b4c  call    cs:__imp_SafeArrayDestroy
0x180060b52  mov     eax, ebx
0x180060b54  mov     rbx, [rsp+40h+arg_8]
0x180060b59  add     rsp, 40h
0x180060b5d  pop     r15
0x180060b5f  pop     r14
0x180060b61  pop     rdi
0x180060b62  pop     rsi
0x180060b63  pop     rbp
0x180060b64  retn
```
