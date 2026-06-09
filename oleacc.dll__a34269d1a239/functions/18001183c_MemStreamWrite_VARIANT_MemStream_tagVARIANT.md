# MemStreamWrite_VARIANT(MemStream &,tagVARIANT &)

- ea: `0x18001183c`
- end: `0x180011bad`
- name: `?MemStreamWrite_VARIANT@@YAHAEAVMemStream@@AEAUtagVARIANT@@@Z`
- size: `881`
- prototype: `__int64 __fastcall(struct MemStream *this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011340`

## callees

- `0x180010300`
- `0x18001183c`
- `0x180017324`
- `0x180047ff8`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180011902`
- `OLEAUT32!__imp_SysStringLen` at `0x180011902`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180011ad6`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180011ad6`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180011b46`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180011b46`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180011b0e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180011b0e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180011af6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180011af6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180011b2e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180011b2e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180011a8b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180011a8b`

## pseudocode

```c
__int64 __fastcall MemStreamWrite_VARIANT(struct MemStream *this, struct tagVARIANT *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned int v9; // esi
  VARTYPE vt; // ax
  __int64 v11; // rdx
  UINT v12; // r8d
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  int v15; // ebx
  BSTR bstrVal; // r14
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  int iVal; // eax
  MemStream *v21; // rcx
  int v22; // r8d
  void *v23; // r15
  __int64 v24; // rbx
  LONG lVal; // ebx
  SAFEARRAY *parray; // rcx
  SAFEARRAY *v27; // rcx
  int v28; // ebx
  SAFEARRAY *v29; // rcx
  unsigned int v30; // ebx
  UINT Elemsize; // eax
  double dblVal; // xmm0_8
  __int64 plUbound; // [rsp+60h] [rbp+40h] BYREF
  LONG plLbound; // [rsp+68h] [rbp+48h] BYREF
  unsigned __int64 v35; // [rsp+70h] [rbp+50h] BYREF
  void *Src; // [rsp+78h] [rbp+58h] BYREF

  v4 = *(_QWORD *)this;
  v5 = -1;
  v6 = *(_QWORD *)this & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v6 == v4 )
  {
    v7 = v4;
  }
  else
  {
    v7 = -1;
    if ( v6 + 2 >= v6 )
      v7 = v6 + 2;
  }
  v8 = v4 + *((_QWORD *)this + 1) - v7;
  if ( v8 > *((_QWORD *)this + 1) )
    return 0;
  plUbound = 0;
  v9 = 1;
  if ( !is_mul_ok(2u, 1u) )
    return 0;
  if ( v8 < 2 )
    goto LABEL_33;
  vt = a2->vt;
  *(_QWORD *)this = v7;
  *((_QWORD *)this + 1) = v8;
  *(_WORD *)v7 = vt;
  *(_QWORD *)this += 2LL;
  *((_QWORD *)this + 1) -= 2LL;
  v11 = *(_QWORD *)this;
  switch ( a2->vt )
  {
    case 0u:
      return v9;
    case 3u:
      lVal = a2->lVal;
      if ( !(unsigned int)MemStream::Check(this, 4u, 1) )
        return 0;
      **(_DWORD **)this = lVal;
LABEL_31:
      *(_QWORD *)this += 4LL;
      *((_QWORD *)this + 1) -= 4LL;
      return v9;
    case 5u:
      dblVal = a2->dblVal;
      if ( (unsigned int)MemStream::Check(this, 8u, 1) )
      {
        **(double **)this = (double)(int)dblVal;
        *(_QWORD *)this += 8LL;
        *((_QWORD *)this + 1) -= 8LL;
        return v9;
      }
      return 0;
  }
  if ( a2->vt != 8 )
  {
    if ( a2->vt != 11 )
    {
      if ( a2->vt != 27 && a2->vt != 31 )
        return v9;
      if ( SafeArrayGetDim(a2->parray) == 1 )
      {
        parray = a2->parray;
        plLbound = 0;
        LODWORD(plUbound) = 0;
        if ( SafeArrayGetLBound(parray, 1u, &plLbound) >= 0
          && SafeArrayGetUBound(a2->parray, 1u, (LONG *)&plUbound) >= 0 )
        {
          v27 = a2->parray;
          v28 = plUbound - plLbound;
          Src = 0;
          if ( SafeArrayAccessData(v27, &Src) >= 0 )
          {
            v29 = a2->parray;
            v30 = v28 + 1;
            v35 = 0;
            Elemsize = SafeArrayGetElemsize(v29);
            if ( (int)ULongLongMult(v30, Elemsize, &v35) >= 0 )
            {
              if ( (unsigned int)MemStream::Check(this, 4u, 1)
                && (v22 = v35,
                    **(_DWORD **)this = v30,
                    *(_QWORD *)this += 4LL,
                    v23 = Src,
                    *((_QWORD *)this + 1) -= 4LL,
                    (unsigned int)MemStream::Check(v21, 1u, v22)) )
              {
                v24 = (int)v35;
                memcpy_0(*(void **)this, v23, (int)v35);
                *(_QWORD *)this += v24;
                *((_QWORD *)this + 1) -= v24;
              }
              else
              {
                v9 = 0;
              }
              SafeArrayUnaccessData(a2->parray);
              return v9;
            }
          }
        }
      }
      return 0;
    }
    v18 = v11 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (v11 & 0xFFFFFFFFFFFFFFFCuLL) == v11 )
    {
      v5 = *(_QWORD *)this;
    }
    else if ( v18 + 4 >= v18 )
    {
      v5 = v18 + 4;
    }
    v19 = v11 + *((_QWORD *)this + 1) - v5;
    if ( v19 > *((_QWORD *)this + 1) || !is_mul_ok(4u, 1u) )
      return 0;
    if ( v19 >= 4 )
    {
      iVal = a2->iVal;
      *((_QWORD *)this + 1) = v19;
      *(_QWORD *)this = v5;
      *(_DWORD *)v5 = iVal;
      goto LABEL_31;
    }
LABEL_33:
    *((_QWORD *)this + 1) = 0;
    return 0;
  }
  v12 = SysStringLen(a2->bstrVal);
  v13 = *(_QWORD *)this & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v13 == *(_QWORD *)this )
  {
    v5 = *(_QWORD *)this;
  }
  else if ( v13 + 4 >= v13 )
  {
    v5 = v13 + 4;
  }
  v14 = *(_QWORD *)this + *((_QWORD *)this + 1) - v5;
  if ( v14 > *((_QWORD *)this + 1) || !is_mul_ok(4u, 1u) )
    return 0;
  if ( v14 < 4 )
    goto LABEL_33;
  *((_QWORD *)this + 1) = v14;
  *(_QWORD *)this = v5;
  *(_DWORD *)v5 = v12;
  v15 = 2 * v12;
  *(_QWORD *)this += 4LL;
  *((_QWORD *)this + 1) -= 4LL;
  bstrVal = a2->bstrVal;
  if ( (unsigned int)MemStream::Check(this, 1u, 2 * v12) )
  {
    memcpy_0(*(void **)this, bstrVal, v15);
    *(_QWORD *)this += v15;
    *((_QWORD *)this + 1) -= v15;
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x18001183c  push    rbp
0x18001183e  push    rbx
0x18001183f  push    rsi
0x180011840  push    rdi
0x180011841  push    r12
0x180011843  push    r14
0x180011845  push    r15
0x180011847  mov     rbp, rsp
0x18001184a  sub     rsp, 20h
0x18001184e  mov     rdi, rcx
0x180011851  mov     r14, rdx
0x180011854  mov     rdx, [rcx]
0x180011857  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001185b  mov     rcx, rdx
0x18001185e  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180011862  cmp     rcx, rdx
0x180011865  jz      loc_1800119AC
0x18001186b  lea     rax, [rcx+2]
0x18001186f  mov     r8, rbx
0x180011872  cmp     rax, rcx
0x180011875  cmovnb  r8, rax
0x180011879  mov     rcx, [rdi+8]
0x18001187d  sub     rcx, r8
0x180011880  add     rcx, rdx
0x180011883  cmp     rcx, [rdi+8]
0x180011887  ja      loc_18001199B
0x18001188d  xor     r12d, r12d
0x180011890  mov     [rbp+plUbound], r12
0x180011894  lea     esi, [r12+1]
0x180011899  mov     eax, esi
0x18001189b  lea     r9d, [r12+2]
0x1800118a0  mul     r9
0x1800118a3  test    rdx, rdx
0x1800118a6  jnz     loc_18001199B
0x1800118ac  cmp     rax, rcx
0x1800118af  ja      loc_180011A24
0x1800118b5  movzx   eax, word ptr [r14]
0x1800118b9  mov     [rdi], r8
0x1800118bc  mov     [rdi+8], rcx
0x1800118c0  mov     [r8], ax
0x1800118c4  add     [rdi], r9
0x1800118c7  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFEh
0x1800118cc  mov     rdx, [rdi]
0x1800118cf  cmp     [r14], r12w
0x1800118d3  jz      loc_180011997
0x1800118d9  cmp     word ptr [r14], 3
0x1800118de  jz      loc_180011A96
0x1800118e4  cmp     word ptr [r14], 5
0x1800118e9  lea     r15d, [r12+8]
0x1800118ee  jz      loc_180011B6E
0x1800118f4  cmp     [r14], r15w
0x1800118f8  jnz     loc_1800119BC
0x1800118fe  mov     rcx, [r14+8]; pbstr
0x180011902  call    cs:__imp_SysStringLen
0x180011908  mov     rdx, [rdi]
0x18001190b  mov     r8d, eax
0x18001190e  mov     rcx, rdx
0x180011911  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180011915  cmp     rcx, rdx
0x180011918  jz      loc_1800119B4
0x18001191e  lea     rax, [rcx+4]
0x180011922  cmp     rax, rcx
0x180011925  cmovnb  rbx, rax
0x180011929  mov     rcx, [rdi+8]
0x18001192d  sub     rcx, rbx
0x180011930  add     rcx, rdx
0x180011933  cmp     rcx, [rdi+8]
0x180011937  ja      short loc_18001199B
0x180011939  mov     r15d, 4
0x18001193f  mov     rax, rsi
0x180011942  mul     r15
0x180011945  test    rdx, rdx
0x180011948  jnz     short loc_18001199B
0x18001194a  cmp     rax, rcx
0x18001194d  ja      loc_180011A24
0x180011953  mov     [rdi+8], rcx
0x180011957  mov     rdx, rsi; unsigned __int64
0x18001195a  mov     [rdi], rbx
0x18001195d  mov     rcx, rdi; this
0x180011960  mov     [rbx], r8d
0x180011963  lea     ebx, [r8+r8]
0x180011967  add     [rdi], r15
0x18001196a  mov     r8d, ebx; int
0x18001196d  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFCh
0x180011972  mov     r14, [r14+8]
0x180011976  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001197b  test    eax, eax
0x18001197d  jz      short loc_18001199B
0x18001197f  mov     rcx, [rdi]; void *
0x180011982  mov     rdx, r14; Src
0x180011985  movsxd  rbx, ebx
0x180011988  mov     r8, rbx; Size
0x18001198b  call    memcpy_0
0x180011990  add     [rdi], rbx
0x180011993  sub     [rdi+8], rbx
0x180011997  mov     eax, esi
0x180011999  jmp     short loc_18001199D
0x18001199b  xor     eax, eax
0x18001199d  add     rsp, 20h
0x1800119a1  pop     r15
0x1800119a3  pop     r14
0x1800119a5  pop     r12
0x1800119a7  pop     rdi
0x1800119a8  pop     rsi
0x1800119a9  pop     rbx
0x1800119aa  pop     rbp
0x1800119ab  retn
0x1800119ac  mov     r8, rdx
0x1800119af  jmp     loc_180011879
0x1800119b4  mov     rbx, rdx
0x1800119b7  jmp     loc_180011929
0x1800119bc  cmp     word ptr [r14], 0Bh
0x1800119c1  jnz     loc_180011AC0
0x1800119c7  mov     rcx, rdx
0x1800119ca  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800119ce  cmp     rcx, rdx
0x1800119d1  jz      short loc_180011A1F
0x1800119d3  lea     rax, [rcx+4]
0x1800119d7  cmp     rax, rcx
0x1800119da  cmovnb  rbx, rax
0x1800119de  mov     rcx, [rdi+8]
0x1800119e2  sub     rcx, rbx
0x1800119e5  add     rcx, rdx
0x1800119e8  cmp     rcx, [rdi+8]
0x1800119ec  ja      short loc_18001199B
0x1800119ee  mov     r15d, 4
0x1800119f4  mov     rax, rsi
0x1800119f7  mul     r15
0x1800119fa  test    rdx, rdx
0x1800119fd  jnz     short loc_18001199B
0x1800119ff  cmp     rax, rcx
0x180011a02  ja      short loc_180011A24
0x180011a04  movsx   eax, word ptr [r14+8]
0x180011a09  mov     [rdi+8], rcx
0x180011a0d  mov     [rdi], rbx
0x180011a10  mov     [rbx], eax
0x180011a12  add     [rdi], r15
0x180011a15  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFCh
0x180011a1a  jmp     loc_180011997
0x180011a1f  mov     rbx, rdx
0x180011a22  jmp     short loc_1800119DE
0x180011a24  mov     [rdi+8], r12
0x180011a28  jmp     loc_18001199B
0x180011a2d  mov     r15d, 4
0x180011a33  mov     r8d, esi; int
0x180011a36  mov     edx, r15d; unsigned __int64
0x180011a39  mov     rcx, rdi; this
0x180011a3c  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x180011a41  test    eax, eax
0x180011a43  jz      loc_180011B66
0x180011a49  mov     rax, [rdi]
0x180011a4c  mov     rdx, rsi; unsigned __int64
0x180011a4f  mov     r8d, dword ptr [rbp+arg_10]; int
0x180011a53  mov     [rax], ebx
0x180011a55  add     [rdi], r15
0x180011a58  mov     r15, [rbp+Src]
0x180011a5c  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFCh
0x180011a61  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x180011a66  test    eax, eax
0x180011a68  jz      loc_180011B66
0x180011a6e  movsxd  rbx, dword ptr [rbp+arg_10]
0x180011a72  mov     rdx, r15; Src
0x180011a75  mov     rcx, [rdi]; void *
0x180011a78  mov     r8, rbx; Size
0x180011a7b  call    memcpy_0
0x180011a80  add     [rdi], rbx
0x180011a83  sub     [rdi+8], rbx
0x180011a87  mov     rcx, [r14+8]; psa
0x180011a8b  call    cs:__imp_SafeArrayUnaccessData
0x180011a91  jmp     loc_180011997
0x180011a96  mov     ebx, [r14+8]
0x180011a9a  mov     r15d, 4
0x180011aa0  mov     edx, r15d; unsigned __int64
0x180011aa3  mov     r8d, esi; int
0x180011aa6  mov     rcx, rdi; this
0x180011aa9  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x180011aae  test    eax, eax
0x180011ab0  jz      loc_18001199B
0x180011ab6  mov     rcx, [rdi]
0x180011ab9  mov     [rcx], ebx
0x180011abb  jmp     loc_180011A12
0x180011ac0  cmp     word ptr [r14], 1Bh
0x180011ac5  jz      short loc_180011AD2
0x180011ac7  cmp     word ptr [r14], 1Fh
0x180011acc  jnz     loc_180011997
0x180011ad2  mov     rcx, [r14+8]; psa
0x180011ad6  call    cs:__imp_SafeArrayGetDim
0x180011adc  cmp     eax, esi
0x180011ade  jnz     loc_18001199B
0x180011ae4  mov     rcx, [r14+8]; psa
0x180011ae8  lea     r8, [rbp+plLbound]; plLbound
0x180011aec  mov     edx, esi; nDim
0x180011aee  mov     [rbp+plLbound], r12d
0x180011af2  mov     dword ptr [rbp+plUbound], r12d
0x180011af6  call    cs:__imp_SafeArrayGetLBound
0x180011afc  test    eax, eax
0x180011afe  js      loc_18001199B
0x180011b04  mov     rcx, [r14+8]; psa
0x180011b08  lea     r8, [rbp+plUbound]; plUbound
0x180011b0c  mov     edx, esi; nDim
0x180011b0e  call    cs:__imp_SafeArrayGetUBound
0x180011b14  test    eax, eax
0x180011b16  js      loc_18001199B
0x180011b1c  mov     ebx, dword ptr [rbp+plUbound]
0x180011b1f  lea     rdx, [rbp+Src]; ppvData
0x180011b23  mov     rcx, [r14+8]; psa
0x180011b27  sub     ebx, [rbp+plLbound]
0x180011b2a  mov     [rbp+Src], r12
0x180011b2e  call    cs:__imp_SafeArrayAccessData
0x180011b34  test    eax, eax
0x180011b36  js      loc_18001199B
0x180011b3c  mov     rcx, [r14+8]; psa
0x180011b40  inc     ebx
0x180011b42  mov     [rbp+arg_10], r12
0x180011b46  call    cs:__imp_SafeArrayGetElemsize
0x180011b4c  mov     ecx, ebx; unsigned __int64
0x180011b4e  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x180011b52  mov     edx, eax; unsigned __int64
0x180011b54  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180011b59  test    eax, eax
0x180011b5b  js      loc_18001199B
0x180011b61  jmp     loc_180011A2D
0x180011b66  mov     esi, r12d
0x180011b69  jmp     loc_180011A87
0x180011b6e  movsd   xmm0, qword ptr [r14+8]
0x180011b74  mov     r8d, esi; int
0x180011b77  mov     rdx, r15; unsigned __int64
0x180011b7a  mov     rcx, rdi; this
0x180011b7d  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x180011b82  test    eax, eax
0x180011b84  jz      loc_18001199B
0x180011b8a  mov     rax, [rdi]
0x180011b8d  cvttsd2si rcx, xmm0
0x180011b92  xorps   xmm0, xmm0
0x180011b95  mov     ecx, ecx
0x180011b97  cvtsi2sd xmm0, rcx
0x180011b9c  movsd   qword ptr [rax], xmm0
0x180011ba0  add     [rdi], r15
0x180011ba3  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFF8h
0x180011ba8  jmp     loc_180011997
```
