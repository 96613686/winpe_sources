# HrPropVarVECTORToSAFEARRAY(tagPROPVARIANT *,tagPROPVARIANT const *,ulong,ushort)

- ea: `0x180052378`
- end: `0x1800524f8`
- name: `?HrPropVarVECTORToSAFEARRAY@@YAJPEAUtagPROPVARIANT@@PEBU1@KG@Z`
- size: `384`
- prototype: `int(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180052980`

## callees

- `0x180052378`
- `0x180052980`
- `0x180052a24`
- `0x180052c88`
- `0x180052d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052446`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052466`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800524b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052446`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052466`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800524b7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800523d2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800523d2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800524ce`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800524ce`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800524ab`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800524ab`

## pseudocode

```c
__int64 __fastcall HrPropVarVECTORToSAFEARRAY(
        struct tagPROPVARIANT *a1,
        const struct tagPROPVARIANT *a2,
        unsigned int a3,
        __int16 a4)
{
  VARTYPE vt; // r15
  LONG lVal; // eax
  SAFEARRAY *v10; // rsi
  HRESULT v11; // ebx
  __int64 v12; // rax
  unsigned int i; // ecx
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-48h] BYREF
  struct tagPROPVARIANT pv; // [rsp+38h] [rbp-40h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-28h] BYREF
  LONG rgIndices; // [rsp+C8h] [rbp+50h] BYREF

  vt = a2->vt;
  rgsabound.lLbound = 0;
  lVal = a2->lVal;
  rgIndices = 0;
  rgsabound.cElements = lVal;
  memset(&pvar, 0, sizeof(pvar));
  memset(&pv, 0, sizeof(pv));
  v10 = SafeArrayCreate(a4, 1u, &rgsabound);
  if ( v10 )
  {
    v11 = 0;
    v12 = 0;
    rgIndices = 0;
    if ( (vt & 0xFFF) == 0xC )
    {
      while ( (unsigned int)v12 < a2->lVal )
      {
        v11 = ImplicitPropVariantToVariantChangeType(
                &pv,
                (const struct tagPROPVARIANT *)&a2->bstrblobVal.pData[24 * v12],
                a3);
        if ( v11 < 0 || (v11 = SafeArrayPutElement(v10, &rgIndices, &pv), PropVariantClear((PROPVARIANT *)&pv), v11 < 0) )
        {
LABEL_14:
          SafeArrayDestroy(v10);
          return (unsigned int)v11;
        }
        v12 = (unsigned int)++rgIndices;
      }
    }
    else
    {
      for ( i = 0; i < a2->lVal; i = v12 )
      {
        v11 = LoadPropVariantFromVectorElem(&pvar, a2, v12);
        if ( v11 < 0 )
          goto LABEL_14;
        v11 = StgPropVariantChangeType(&pv, a4);
        PropVariantClear((PROPVARIANT *)&pvar);
        if ( v11 < 0 )
          goto LABEL_14;
        v11 = PutPropVariantDataIntoSafeArray(v10, &pv, rgIndices);
        PropVariantClear((PROPVARIANT *)&pv);
        if ( v11 < 0 )
          goto LABEL_14;
        LODWORD(v12) = rgIndices + 1;
        rgIndices = v12;
      }
    }
    a1->hVal.QuadPart = (LONGLONG)v10;
    a1->vt = a4 | 0x2000;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180052378  push    rbp
0x18005237a  push    rbx
0x18005237b  push    rsi
0x18005237c  push    rdi
0x18005237d  push    r12
0x18005237f  push    r13
0x180052381  push    r14
0x180052383  push    r15
0x180052385  mov     rbp, rsp
0x180052388  sub     rsp, 78h
0x18005238c  movzx   r15d, word ptr [rdx]
0x180052390  xor     eax, eax
0x180052392  mov     [rbp+var_18], rax
0x180052396  mov     r13d, r8d
0x180052399  mov     [rbp+var_30], rax
0x18005239d  lea     r8, [rbp+rgsabound]; rgsabound
0x1800523a1  mov     [rbp+rgsabound.lLbound], eax
0x1800523a4  mov     r14, rdx
0x1800523a7  mov     eax, [rdx+8]
0x1800523aa  mov     r12, rcx
0x1800523ad  xorps   xmm0, xmm0
0x1800523b0  mov     [rbp+rgIndices], 0
0x1800523b7  xorps   xmm1, xmm1
0x1800523ba  mov     [rbp+rgsabound.cElements], eax
0x1800523bd  mov     edx, 1; cDims
0x1800523c2  movzx   ecx, r9w; vt
0x1800523c6  movzx   edi, r9w
0x1800523ca  movups  xmmword ptr [rbp+pvar], xmm0
0x1800523ce  movups  xmmword ptr [rbp+pv], xmm1
0x1800523d2  call    cs:__imp_SafeArrayCreate
0x1800523d8  mov     rsi, rax
0x1800523db  test    rax, rax
0x1800523de  jnz     short loc_1800523EA
0x1800523e0  mov     ebx, 8007000Eh
0x1800523e5  jmp     loc_1800524E5
0x1800523ea  xor     ebx, ebx
0x1800523ec  mov     ecx, 0FFFh
0x1800523f1  and     r15w, cx
0x1800523f5  xor     eax, eax
0x1800523f7  mov     [rbp+rgIndices], eax
0x1800523fa  lea     ecx, [rbx+0Ch]
0x1800523fd  cmp     cx, r15w
0x180052401  jz      short loc_18005247C
0x180052403  xor     ecx, ecx
0x180052405  cmp     ecx, [r14+8]
0x180052409  jnb     loc_1800524D6
0x18005240f  mov     r8d, eax; int
0x180052412  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x180052416  mov     rdx, r14; struct tagPROPVARIANT *
0x180052419  call    ?LoadPropVariantFromVectorElem@@YAJPEAUtagPROPVARIANT@@PEBU1@H@Z; LoadPropVariantFromVectorElem(tagPROPVARIANT *,tagPROPVARIANT const *,int)
0x18005241e  mov     ebx, eax
0x180052420  test    eax, eax
0x180052422  js      loc_1800524CB
0x180052428  xor     r9d, r9d
0x18005242b  mov     [rsp+78h+var_58], di; __int16
0x180052430  mov     r8d, r13d
0x180052433  lea     rdx, [rbp+pvar]
0x180052437  lea     rcx, [rbp+pv]; struct tagPROPVARIANT *
0x18005243b  call    StgPropVariantChangeType
0x180052440  lea     rcx, [rbp+pvar]; pvar
0x180052444  mov     ebx, eax
0x180052446  call    cs:__imp_PropVariantClear
0x18005244c  test    ebx, ebx
0x18005244e  js      short loc_1800524CB
0x180052450  mov     r8d, [rbp+rgIndices]; int
0x180052454  lea     rdx, [rbp+pv]; struct tagPROPVARIANT *
0x180052458  mov     rcx, rsi; psa
0x18005245b  call    ?PutPropVariantDataIntoSafeArray@@YAJPEAUtagSAFEARRAY@@PEBUtagPROPVARIANT@@H@Z; PutPropVariantDataIntoSafeArray(tagSAFEARRAY *,tagPROPVARIANT const *,int)
0x180052460  lea     rcx, [rbp+pv]; pvar
0x180052464  mov     ebx, eax
0x180052466  call    cs:__imp_PropVariantClear
0x18005246c  test    ebx, ebx
0x18005246e  js      short loc_1800524CB
0x180052470  mov     eax, [rbp+rgIndices]
0x180052473  inc     eax
0x180052475  mov     [rbp+rgIndices], eax
0x180052478  mov     ecx, eax
0x18005247a  jmp     short loc_180052405
0x18005247c  cmp     eax, [r14+8]
0x180052480  jnb     short loc_1800524D6
0x180052482  lea     rcx, [rax+rax*2]
0x180052486  mov     r8d, r13d; unsigned int
0x180052489  mov     rax, [r14+10h]
0x18005248d  lea     rdx, [rax+rcx*8]; struct tagPROPVARIANT *
0x180052491  lea     rcx, [rbp+pv]; struct tagPROPVARIANT *
0x180052495  call    ?ImplicitPropVariantToVariantChangeType@@YAJPEAUtagPROPVARIANT@@PEBU1@K@Z; ImplicitPropVariantToVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const *,ulong)
0x18005249a  mov     ebx, eax
0x18005249c  test    eax, eax
0x18005249e  js      short loc_1800524CB
0x1800524a0  lea     r8, [rbp+pv]; pv
0x1800524a4  mov     rcx, rsi; psa
0x1800524a7  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800524ab  call    cs:__imp_SafeArrayPutElement
0x1800524b1  lea     rcx, [rbp+pv]; pvar
0x1800524b5  mov     ebx, eax
0x1800524b7  call    cs:__imp_PropVariantClear
0x1800524bd  test    ebx, ebx
0x1800524bf  js      short loc_1800524CB
0x1800524c1  mov     eax, [rbp+rgIndices]
0x1800524c4  inc     eax
0x1800524c6  mov     [rbp+rgIndices], eax
0x1800524c9  jmp     short loc_18005247C
0x1800524cb  mov     rcx, rsi; psa
0x1800524ce  call    cs:__imp_SafeArrayDestroy
0x1800524d4  jmp     short loc_1800524E5
0x1800524d6  or      di, 2000h
0x1800524db  mov     [r12+8], rsi
0x1800524e0  mov     [r12], di
0x1800524e5  mov     eax, ebx
0x1800524e7  add     rsp, 78h
0x1800524eb  pop     r15
0x1800524ed  pop     r14
0x1800524ef  pop     r13
0x1800524f1  pop     r12
0x1800524f3  pop     rdi
0x1800524f4  pop     rsi
0x1800524f5  pop     rbx
0x1800524f6  pop     rbp
0x1800524f7  retn
```
