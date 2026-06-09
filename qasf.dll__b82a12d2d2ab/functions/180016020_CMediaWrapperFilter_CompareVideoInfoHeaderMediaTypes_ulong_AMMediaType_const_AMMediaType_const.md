# CMediaWrapperFilter::CompareVideoInfoHeaderMediaTypes(ulong,_AMMediaType const *,_AMMediaType const *)

- ea: `0x180016020`
- end: `0x18001630e`
- name: `?CompareVideoInfoHeaderMediaTypes@CMediaWrapperFilter@@KAJKPEBU_AMMediaType@@0@Z`
- size: `750`
- prototype: `__int64 __fastcall(char, const struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001588c`
- `0x180015a10`
- `0x1800174e4`

## callees

- `0x1800071e8`
- `0x180016020`
- `0x18001657c`
- `0x180016f7c`
- `0x18001e5b9`

## import_xrefs

- `USER32!EqualRect` at `0x1800161a0`
- `USER32!EqualRect` at `0x1800161b6`
- `USER32!EqualRect` at `0x1800161a0`
- `USER32!EqualRect` at `0x1800161b6`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::CompareVideoInfoHeaderMediaTypes(
        char a1,
        const struct _AMMediaType *a2,
        const struct _AMMediaType *a3)
{
  struct _AMMediaType *v4; // r12
  struct _AMMediaType *v5; // r15
  int IsValidVideoInfoHeaderMediaType; // ebx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  const struct _AMMediaType *v13; // rbx
  const struct _AMMediaType *v14; // rsi
  BYTE *pbFormat; // rdi
  BYTE *v16; // rsi
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  struct _AMMediaType *v20; // [rsp+20h] [rbp-58h] BYREF
  struct _AMMediaType *pv; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  pv = 0;
  v20 = 0;
  IsValidVideoInfoHeaderMediaType = CMediaWrapperFilter::IsValidVideoInfoHeaderMediaType(a2);
  if ( IsValidVideoInfoHeaderMediaType < 0 )
    return (unsigned int)IsValidVideoInfoHeaderMediaType;
  IsValidVideoInfoHeaderMediaType = CMediaWrapperFilter::IsValidVideoInfoHeaderMediaType(a3);
  if ( IsValidVideoInfoHeaderMediaType < 0 )
    return (unsigned int)IsValidVideoInfoHeaderMediaType;
  v9 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
  v10 = *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( *(_QWORD *)&a2->formattype.Data1 == *(_QWORD *)&FORMAT_VideoInfo.Data1
    && *(_QWORD *)a2->formattype.Data4 == *(_QWORD *)FORMAT_VideoInfo.Data4 )
  {
    v11 = CMediaWrapperFilter::CreateVideoInfoHeader2FromVideoInfoHeader1MediaType(a2, &pv);
    v4 = pv;
    IsValidVideoInfoHeaderMediaType = v11;
    if ( v11 < 0 )
      goto LABEL_59;
    v10 = *(_QWORD *)FORMAT_VideoInfo.Data4;
    v9 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
  }
  if ( *(_QWORD *)&a3->formattype.Data1 != v9
    || *(_QWORD *)a3->formattype.Data4 != v10
    || (v12 = CMediaWrapperFilter::CreateVideoInfoHeader2FromVideoInfoHeader1MediaType(a3, &v20),
        v5 = v20,
        IsValidVideoInfoHeaderMediaType = v12,
        v12 >= 0) )
  {
    v13 = v4;
    if ( !v4 )
      v13 = a2;
    v14 = v5;
    if ( !v5 )
      v14 = a3;
    if ( v13->pUnk
      || v14->pUnk
      || *(_QWORD *)&v13->majortype.Data1 != *(_QWORD *)&v14->majortype.Data1
      || *(_QWORD *)v13->majortype.Data4 != *(_QWORD *)v14->majortype.Data4
      || *(_QWORD *)&v13->subtype.Data1 != *(_QWORD *)&v14->subtype.Data1
      || *(_QWORD *)v13->subtype.Data4 != *(_QWORD *)v14->subtype.Data4
      || v13->bFixedSizeSamples != v14->bFixedSizeSamples
      || v13->bTemporalCompression != v14->bTemporalCompression
      || *(_QWORD *)&v13->formattype.Data1 != *(_QWORD *)&v14->formattype.Data1
      || *(_QWORD *)v13->formattype.Data4 != *(_QWORD *)v14->formattype.Data4
      || (a1 & 0x10) == 0 && v13->lSampleSize != v14->lSampleSize )
    {
      goto LABEL_58;
    }
    pbFormat = v13->pbFormat;
    v16 = v14->pbFormat;
    if ( (a1 & 1) == 0
      && (!EqualRect((const RECT *)v13->pbFormat, (const RECT *)v16)
       || !EqualRect((const RECT *)pbFormat + 1, (const RECT *)v16 + 1)) )
    {
      goto LABEL_58;
    }
    if ( *((_DWORD *)pbFormat + 17) != *((_DWORD *)v16 + 17)
      || (a1 & 2) == 0 && *((_DWORD *)pbFormat + 12) != *((_DWORD *)v16 + 12) )
    {
      goto LABEL_58;
    }
    if ( (a1 & 0x40) == 0 && *((_DWORD *)pbFormat + 13) != *((_DWORD *)v16 + 13) )
      goto LABEL_58;
    if ( (a1 & 4) == 0
      && (*((_DWORD *)pbFormat + 14) != *((_DWORD *)v16 + 14) || *((_DWORD *)pbFormat + 15) != *((_DWORD *)v16 + 15)) )
    {
      goto LABEL_58;
    }
    if ( (a1 & 0x20) == 0 && *((_DWORD *)pbFormat + 16) != *((_DWORD *)v16 + 16) )
      goto LABEL_58;
    v17 = *((_DWORD *)pbFormat + 18);
    if ( v17 != *((_DWORD *)v16 + 18)
      || *((_WORD *)pbFormat + 42) != *((_WORD *)v16 + 42)
      || *((_WORD *)pbFormat + 43) != *((_WORD *)v16 + 43)
      || *((_DWORD *)pbFormat + 22) != *((_DWORD *)v16 + 22)
      || *((_DWORD *)pbFormat + 24) != *((_DWORD *)v16 + 24)
      || *((_DWORD *)pbFormat + 25) != *((_DWORD *)v16 + 25)
      || *((_DWORD *)pbFormat + 26) != *((_DWORD *)v16 + 26)
      || *((_DWORD *)pbFormat + 27) != *((_DWORD *)v16 + 27)
      || (a1 & 8) == 0
      && (*((_DWORD *)pbFormat + 19) != *((_DWORD *)v16 + 19) || *((_DWORD *)pbFormat + 20) != *((_DWORD *)v16 + 20)) )
    {
      goto LABEL_58;
    }
    if ( (a1 & 0x10) == 0 && *((_DWORD *)pbFormat + 23) != *((_DWORD *)v16 + 23) )
      goto LABEL_58;
    if ( v17 < 0x28 )
    {
LABEL_53:
      IsValidVideoInfoHeaderMediaType = -2147418113;
      goto LABEL_59;
    }
    v18 = v17 - 40;
    if ( v18 >= 0xFFFFFF90 )
    {
      IsValidVideoInfoHeaderMediaType = -2147024362;
      goto LABEL_59;
    }
    if ( v18 + 112 > v13->cbFormat )
      goto LABEL_53;
    IsValidVideoInfoHeaderMediaType = 0;
    if ( memcmp_0(pbFormat + 112, v16 + 112, v18) )
LABEL_58:
      IsValidVideoInfoHeaderMediaType = 1;
  }
LABEL_59:
  if ( v4 )
    DeleteMediaType(v4);
  if ( v5 )
    DeleteMediaType(v5);
  if ( IsValidVideoInfoHeaderMediaType >= 0 )
    return IsValidVideoInfoHeaderMediaType == 1;
  return (unsigned int)IsValidVideoInfoHeaderMediaType;
}

```

## disassembly

```asm
0x180016020  mov     rax, rsp
0x180016023  push    rbx
0x180016024  push    rbp
0x180016025  push    rsi
0x180016026  push    rdi
0x180016027  push    r12
0x180016029  push    r13
0x18001602b  push    r14
0x18001602d  push    r15
0x18001602f  sub     rsp, 38h
0x180016033  mov     ebp, ecx
0x180016035  xor     r12d, r12d
0x180016038  xor     r15d, r15d
0x18001603b  mov     [rax+20h], r12
0x18001603f  mov     rcx, rdx; struct _AMMediaType *
0x180016042  mov     [rax-58h], r15
0x180016046  mov     rdi, r8
0x180016049  mov     rsi, rdx
0x18001604c  call    ?IsValidVideoInfoHeaderMediaType@CMediaWrapperFilter@@KAJPEBU_AMMediaType@@@Z; CMediaWrapperFilter::IsValidVideoInfoHeaderMediaType(_AMMediaType const *)
0x180016051  mov     ebx, eax
0x180016053  test    eax, eax
0x180016055  js      loc_1800162FB
0x18001605b  mov     rcx, rdi; struct _AMMediaType *
0x18001605e  call    ?IsValidVideoInfoHeaderMediaType@CMediaWrapperFilter@@KAJPEBU_AMMediaType@@@Z; CMediaWrapperFilter::IsValidVideoInfoHeaderMediaType(_AMMediaType const *)
0x180016063  mov     ebx, eax
0x180016065  test    eax, eax
0x180016067  js      loc_1800162FB
0x18001606d  mov     rcx, qword ptr cs:FORMAT_VideoInfo.Data1
0x180016074  lea     r13d, [r12+1]
0x180016079  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180016080  cmp     [rsi+2Ch], rcx
0x180016084  jnz     short loc_1800160BC
0x180016086  cmp     [rsi+34h], rax
0x18001608a  jnz     short loc_1800160BC
0x18001608c  lea     rdx, [rsp+78h+pv]; struct _AMMediaType **
0x180016094  mov     rcx, rsi; struct _AMMediaType *
0x180016097  call    ?CreateVideoInfoHeader2FromVideoInfoHeader1MediaType@CMediaWrapperFilter@@KAJPEBU_AMMediaType@@PEAPEAU2@@Z; CMediaWrapperFilter::CreateVideoInfoHeader2FromVideoInfoHeader1MediaType(_AMMediaType const *,_AMMediaType * *)
0x18001609c  mov     r12, [rsp+78h+pv]
0x1800160a4  mov     ebx, eax
0x1800160a6  test    eax, eax
0x1800160a8  js      loc_1800162D3
0x1800160ae  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800160b5  mov     rcx, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800160bc  cmp     [rdi+2Ch], rcx
0x1800160c0  jnz     short loc_1800160E4
0x1800160c2  cmp     [rdi+34h], rax
0x1800160c6  jnz     short loc_1800160E4
0x1800160c8  lea     rdx, [rsp+78h+var_58]; struct _AMMediaType **
0x1800160cd  mov     rcx, rdi; struct _AMMediaType *
0x1800160d0  call    ?CreateVideoInfoHeader2FromVideoInfoHeader1MediaType@CMediaWrapperFilter@@KAJPEBU_AMMediaType@@PEAPEAU2@@Z; CMediaWrapperFilter::CreateVideoInfoHeader2FromVideoInfoHeader1MediaType(_AMMediaType const *,_AMMediaType * *)
0x1800160d5  mov     r15, [rsp+78h+var_58]
0x1800160da  mov     ebx, eax
0x1800160dc  test    eax, eax
0x1800160de  js      loc_1800162D3
0x1800160e4  test    r12, r12
0x1800160e7  mov     rbx, r12
0x1800160ea  cmovz   rbx, rsi
0x1800160ee  test    r15, r15
0x1800160f1  mov     rsi, r15
0x1800160f4  cmovz   rsi, rdi
0x1800160f8  cmp     qword ptr [rbx+40h], 0
0x1800160fd  jnz     loc_1800162D0
0x180016103  cmp     qword ptr [rsi+40h], 0
0x180016108  jnz     loc_1800162D0
0x18001610e  mov     rax, [rbx]
0x180016111  cmp     rax, [rsi]
0x180016114  jnz     loc_1800162D0
0x18001611a  mov     rax, [rbx+8]
0x18001611e  cmp     rax, [rsi+8]
0x180016122  jnz     loc_1800162D0
0x180016128  mov     rax, [rbx+10h]
0x18001612c  cmp     rax, [rsi+10h]
0x180016130  jnz     loc_1800162D0
0x180016136  mov     rax, [rbx+18h]
0x18001613a  cmp     rax, [rsi+18h]
0x18001613e  jnz     loc_1800162D0
0x180016144  mov     eax, [rsi+20h]
0x180016147  cmp     [rbx+20h], eax
0x18001614a  jnz     loc_1800162D0
0x180016150  mov     eax, [rsi+24h]
0x180016153  cmp     [rbx+24h], eax
0x180016156  jnz     loc_1800162D0
0x18001615c  mov     rax, [rbx+2Ch]
0x180016160  cmp     rax, [rsi+2Ch]
0x180016164  jnz     loc_1800162D0
0x18001616a  mov     rax, [rbx+34h]
0x18001616e  cmp     rax, [rsi+34h]
0x180016172  jnz     loc_1800162D0
0x180016178  mov     r14d, ebp
0x18001617b  and     r14d, 10h
0x18001617f  jnz     short loc_18001618D
0x180016181  mov     eax, [rsi+28h]
0x180016184  cmp     [rbx+28h], eax
0x180016187  jnz     loc_1800162D0
0x18001618d  mov     rdi, [rbx+50h]
0x180016191  mov     rsi, [rsi+50h]
0x180016195  test    r13b, bpl
0x180016198  jnz     short loc_1800161C4
0x18001619a  mov     rdx, rsi; lprc2
0x18001619d  mov     rcx, rdi; lprc1
0x1800161a0  call    cs:__imp_EqualRect
0x1800161a6  test    eax, eax
0x1800161a8  jz      loc_1800162D0
0x1800161ae  lea     rdx, [rsi+10h]; lprc2
0x1800161b2  lea     rcx, [rdi+10h]; lprc1
0x1800161b6  call    cs:__imp_EqualRect
0x1800161bc  test    eax, eax
0x1800161be  jz      loc_1800162D0
0x1800161c4  mov     eax, [rsi+44h]
0x1800161c7  cmp     [rdi+44h], eax
0x1800161ca  jnz     loc_1800162D0
0x1800161d0  test    bpl, 2
0x1800161d4  jnz     short loc_1800161E2
0x1800161d6  mov     eax, [rsi+30h]
0x1800161d9  cmp     [rdi+30h], eax
0x1800161dc  jnz     loc_1800162D0
0x1800161e2  test    bpl, 40h
0x1800161e6  jnz     short loc_1800161F4
0x1800161e8  mov     eax, [rsi+34h]
0x1800161eb  cmp     [rdi+34h], eax
0x1800161ee  jnz     loc_1800162D0
0x1800161f4  test    bpl, 4
0x1800161f8  jnz     short loc_180016212
0x1800161fa  mov     eax, [rsi+38h]
0x1800161fd  cmp     [rdi+38h], eax
0x180016200  jnz     loc_1800162D0
0x180016206  mov     eax, [rsi+3Ch]
0x180016209  cmp     [rdi+3Ch], eax
0x18001620c  jnz     loc_1800162D0
0x180016212  test    bpl, 20h
0x180016216  jnz     short loc_180016224
0x180016218  mov     eax, [rsi+40h]
0x18001621b  cmp     [rdi+40h], eax
0x18001621e  jnz     loc_1800162D0
0x180016224  mov     ecx, [rdi+48h]
0x180016227  cmp     ecx, [rsi+48h]
0x18001622a  jnz     loc_1800162D0
0x180016230  movzx   eax, word ptr [rsi+54h]
0x180016234  cmp     [rdi+54h], ax
0x180016238  jnz     loc_1800162D0
0x18001623e  movzx   eax, word ptr [rsi+56h]
0x180016242  cmp     [rdi+56h], ax
0x180016246  jnz     loc_1800162D0
0x18001624c  mov     eax, [rsi+58h]
0x18001624f  cmp     [rdi+58h], eax
0x180016252  jnz     short loc_1800162D0
0x180016254  mov     eax, [rsi+60h]
0x180016257  cmp     [rdi+60h], eax
0x18001625a  jnz     short loc_1800162D0
0x18001625c  mov     eax, [rsi+64h]
0x18001625f  cmp     [rdi+64h], eax
0x180016262  jnz     short loc_1800162D0
0x180016264  mov     eax, [rsi+68h]
0x180016267  cmp     [rdi+68h], eax
0x18001626a  jnz     short loc_1800162D0
0x18001626c  mov     eax, [rsi+6Ch]
0x18001626f  cmp     [rdi+6Ch], eax
0x180016272  jnz     short loc_1800162D0
0x180016274  test    bpl, 8
0x180016278  jnz     short loc_18001628A
0x18001627a  mov     eax, [rsi+4Ch]
0x18001627d  cmp     [rdi+4Ch], eax
0x180016280  jnz     short loc_1800162D0
0x180016282  mov     eax, [rsi+50h]
0x180016285  cmp     [rdi+50h], eax
0x180016288  jnz     short loc_1800162D0
0x18001628a  test    r14d, r14d
0x18001628d  jnz     short loc_180016297
0x18001628f  mov     eax, [rsi+5Ch]
0x180016292  cmp     [rdi+5Ch], eax
0x180016295  jnz     short loc_1800162D0
0x180016297  cmp     ecx, 28h ; '('
0x18001629a  jnb     short loc_1800162A3
0x18001629c  mov     ebx, 8000FFFFh
0x1800162a1  jmp     short loc_1800162D3
0x1800162a3  add     ecx, 0FFFFFFD8h
0x1800162a6  lea     eax, [rcx+70h]
0x1800162a9  cmp     eax, 70h ; 'p'
0x1800162ac  jnb     short loc_1800162B5
0x1800162ae  mov     ebx, 80070216h
0x1800162b3  jmp     short loc_1800162D3
0x1800162b5  cmp     eax, [rbx+48h]
0x1800162b8  ja      short loc_18001629C
0x1800162ba  mov     r8d, ecx; Size
0x1800162bd  lea     rdx, [rsi+70h]; Buf2
0x1800162c1  lea     rcx, [rdi+70h]; Buf1
0x1800162c5  xor     ebx, ebx
0x1800162c7  call    memcmp_0
0x1800162cc  test    eax, eax
0x1800162ce  jz      short loc_1800162D3
0x1800162d0  mov     ebx, r13d
0x1800162d3  test    r12, r12
0x1800162d6  jz      short loc_1800162E0
0x1800162d8  mov     rcx, r12; pv
0x1800162db  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800162e0  test    r15, r15
0x1800162e3  jz      short loc_1800162ED
0x1800162e5  mov     rcx, r15; pv
0x1800162e8  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800162ed  test    ebx, ebx
0x1800162ef  js      short loc_1800162FB
0x1800162f1  xor     eax, eax
0x1800162f3  cmp     ebx, r13d
0x1800162f6  setz    al
0x1800162f9  jmp     short loc_1800162FD
0x1800162fb  mov     eax, ebx
0x1800162fd  add     rsp, 38h
0x180016301  pop     r15
0x180016303  pop     r14
0x180016305  pop     r13
0x180016307  pop     r12
0x180016309  pop     rdi
0x18001630a  pop     rsi
0x18001630b  pop     rbp
0x18001630c  pop     rbx
0x18001630d  retn
```
