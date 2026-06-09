# ASN1BERDecChar16String

- ea: `0x180001010`
- end: `0x1800014a4`
- name: `ASN1BERDecChar16String`
- size: `1172`
- prototype: `__int64 __fastcall(_DWORD *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180001010`
- `0x180001b30`
- `0x180001f50`
- `0x1800020a0`
- `0x180002200`
- `0x180004310`
- `0x1800062ec`
- `0x18000aadd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000113d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000113d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000125a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000139e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000125a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000139e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001404`

## pseudocode

```c
__int64 __fastcall ASN1BERDecChar16String(_DWORD *a1, int a2, unsigned int *a3)
{
  _DWORD *v5; // rbx
  int v6; // eax
  unsigned __int8 *v7; // rax
  int v8; // ebp
  unsigned __int8 *v9; // r8
  char v10; // si
  int v11; // esi
  int v12; // r9d
  _DWORD *v13; // rax
  int v15; // ecx
  int v16; // edx
  unsigned int v17; // esi
  unsigned __int8 *v18; // r8
  int v19; // r14d
  int v20; // eax
  __int64 v21; // rsi
  char *v22; // rbp
  unsigned int v23; // ecx
  unsigned int v24; // r8d
  __int64 v25; // rcx
  unsigned int v26; // r9d
  __int64 v27; // r8
  __int64 v28; // rax
  unsigned int v29; // r9d
  unsigned int v30; // r9d
  __int64 v31; // rdx
  int v32; // r15d
  _BYTE *v33; // rax
  char v34; // cl
  unsigned int v35; // edx
  unsigned int v36; // ecx
  __int64 v37; // rax
  __int64 v38; // rbp
  __int64 v39; // r14
  __int64 v40; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-30h]
  __int64 v42; // [rsp+70h] [rbp+8h] BYREF
  __int64 v43; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(hMem) = 0;
  v40 = 0;
  v5 = a1;
  v6 = a1[4] + a1[6] - a1[10];
  v42 = 0;
  v43 = 0;
  if ( !v6 )
    goto LABEL_44;
  v7 = (unsigned __int8 *)*((_QWORD *)a1 + 5);
  v8 = *v7;
  v9 = v7 + 1;
  v10 = *v7;
  *((_QWORD *)a1 + 5) = v7 + 1;
  v11 = v10 & 0x1F;
  if ( v11 == 31 )
  {
    v11 = 0;
    v32 = 0;
    while ( (unsigned int)ASN1BERDecCheck(v5, 1) )
    {
      v33 = (_BYTE *)*((_QWORD *)v5 + 5);
      v34 = *v33;
      v9 = v33 + 1;
      *((_QWORD *)v5 + 5) = v33 + 1;
      if ( (v11 & 0xE0000000) == 0 )
      {
        v12 = (_DWORD)v33 + 1;
        v11 = (v11 << 7) | v34 & 0x7F;
        if ( v34 >= 0 )
          goto LABEL_4;
        if ( (unsigned int)++v32 < 4 )
          continue;
      }
      ASN1DecSetError(v5, 4294966285LL);
      return 0;
    }
    return 0;
  }
  v12 = (_DWORD)v7 + 1;
LABEL_4:
  if ( a2 != (v11 | ((v8 & 0xFFFFFFC0) << 24)) )
  {
    do
    {
      v13 = (_DWORD *)*((_QWORD *)v5 + 7);
      v5[8] = -1011;
      if ( v5 == v13 )
        break;
      v5 = v13;
    }
    while ( v13 );
    return 0;
  }
  v15 = v5[4];
  v16 = v5[6];
  if ( !(v16 + v15 - v12) )
    goto LABEL_44;
  v17 = *v9;
  v18 = v9 + 1;
  *((_QWORD *)v5 + 5) = v18;
  if ( v17 < 0x80 )
    goto LABEL_10;
  if ( v17 == 128 )
  {
    v17 = 0;
    v19 = 1;
    goto LABEL_13;
  }
  if ( v17 > 0x84 )
  {
    v31 = 4294966293LL;
    goto LABEL_45;
  }
  v26 = v17 - 128;
  if ( v17 - 128 > v16 + v15 - (int)v18 )
  {
LABEL_44:
    v31 = 4294966294LL;
LABEL_45:
    ASN1DecSetError(v5, v31);
    return 0;
  }
  v17 = 0;
  if ( v26 == 2 )
  {
LABEL_28:
    v17 |= *v18++ << 8;
    *((_QWORD *)v5 + 5) = v18;
LABEL_29:
    v17 |= *v18;
    *((_QWORD *)v5 + 5) = v18 + 1;
    LODWORD(v18) = (_DWORD)v18 + 1;
    goto LABEL_10;
  }
  v29 = v26 - 1;
  if ( !v29 )
    goto LABEL_29;
  v30 = v29 - 2;
  if ( !v30 )
  {
LABEL_42:
    v17 |= *v18++ << 16;
    *((_QWORD *)v5 + 5) = v18;
    goto LABEL_28;
  }
  if ( v30 == 1 )
  {
    v17 = *v18++ << 24;
    *((_QWORD *)v5 + 5) = v18;
    goto LABEL_42;
  }
LABEL_10:
  v19 = 0;
  if ( v17 > v16 + v15 - (int)v18 )
  {
    ASN1DecSetError(v5, 4294966294LL);
    v20 = 0;
  }
  else
  {
    v20 = 1;
  }
  if ( !v20 )
    return 0;
LABEL_13:
  if ( (v8 & 0x20) != 0 )
  {
    *a3 = 0;
    *((_QWORD *)a3 + 1) = 0;
    if ( (unsigned int)BERDecConstructed((_DWORD)v5, v17, v19, (unsigned int)&v42, (__int64)&v43) )
    {
      v38 = v42;
      v39 = v43;
      while ( 1 )
      {
        do
        {
          if ( !(unsigned int)ASN1BERDecNotEndOfContents(v38, v39) )
            return ASN1BERDecEndOfContents(v5, v38, v39);
          if ( !(unsigned int)ASN1BERDecChar16String(v38, 4, &v40) )
            return 0;
        }
        while ( !(_DWORD)v40 );
        v36 = *a3 + v40;
        if ( v36 < *a3 )
          break;
        if ( v36 + 1 < v36 )
          break;
        if ( 2 * (unsigned __int64)(v36 + 1) > 0xFFFFFFFF )
          break;
        v37 = DecMemReAlloc(v38, *((_QWORD *)a3 + 1));
        *((_QWORD *)a3 + 1) = v37;
        if ( !v37 )
          break;
        memcpy_0((void *)(v37 + 2LL * *a3), hMem, 2LL * (unsigned int)v40);
        *a3 += v40;
        *(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * *a3) = 0;
        if ( !v5[19] )
          LocalFree(hMem);
        hMem = 0;
      }
      if ( !v5[19] )
        LocalFree(hMem);
    }
    return 0;
  }
  LODWORD(v21) = v17 >> 1;
  *a3 = v21;
  if ( (_DWORD)v21 )
  {
    v22 = 0;
    v23 = (2 * v21 + 5) & 0xFFFFFFFC;
    if ( 2 * (int)v21 + 2 <= v23 )
    {
      if ( !v5[19] )
      {
        v22 = (char *)LocalAlloc(0x40u, v23);
        goto LABEL_18;
      }
      v35 = v5[26];
      if ( v35 >= v23 )
      {
        v22 = (char *)*((_QWORD *)v5 + 12);
        *((_QWORD *)v5 + 12) = &v22[v23];
        v5[26] = v35 - v23;
LABEL_18:
        if ( v22 )
          goto LABEL_19;
      }
    }
    ASN1DecSetError(v5, 4294966290LL);
LABEL_19:
    *((_QWORD *)a3 + 1) = v22;
    if ( v22 )
    {
      v24 = 0;
      do
      {
        v25 = v24++;
        *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v25) = _byteswap_ushort(**((_WORD **)v5 + 5));
        *((_QWORD *)v5 + 5) += 2LL;
      }
      while ( v24 < (unsigned int)v21 );
      *(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * (unsigned int)v21) = 0;
      if ( (g_dwDecodingRules & 2) == 0 )
      {
        v27 = *((_QWORD *)a3 + 1);
        while ( 1 )
        {
          LODWORD(v28) = v21;
          v21 = (unsigned int)(v21 - 1);
          if ( *(_WORD *)(v27 + 2 * v21) )
            break;
          if ( !(_DWORD)v21 )
            return 1;
        }
        while ( (_DWORD)v28 )
        {
          v28 = (unsigned int)(v28 - 1);
          if ( !*(_WORD *)(v27 + 2 * v28) )
          {
            if ( !v5[19] )
              LocalFree(*((HLOCAL *)a3 + 1));
            *((_QWORD *)a3 + 1) = 0;
            *a3 = 0;
            ASN1DecSetError(v5, 4294966283LL);
            return 0;
          }
        }
      }
      return 1;
    }
    return 0;
  }
  *((_QWORD *)a3 + 1) = 0;
  return 1;
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  mov     [r11+10h], rbx
0x180001017  mov     [r11+18h], rbp
0x18000101b  push    rsi
0x18000101c  push    rdi
0x18000101d  push    r12
0x18000101f  push    r14
0x180001021  push    r15
0x180001023  sub     rsp, 40h
0x180001027  xor     eax, eax
0x180001029  xor     r12d, r12d
0x18000102c  mov     [r11-34h], rax
0x180001030  mov     rdi, r8
0x180001033  mov     [r11-38h], rax
0x180001037  mov     r14d, edx
0x18000103a  mov     eax, [rcx+18h]
0x18000103d  mov     rbx, rcx
0x180001040  sub     eax, [rcx+28h]
0x180001043  add     eax, [rcx+10h]
0x180001046  mov     [r11+8], r12
0x18000104a  mov     [r11+20h], r12
0x18000104e  cmp     eax, 1
0x180001051  jb      loc_1800012AB
0x180001057  mov     rax, [rcx+28h]
0x18000105b  movzx   ebp, byte ptr [rax]
0x18000105e  lea     r8, [rax+1]
0x180001062  mov     esi, ebp
0x180001064  mov     [rcx+28h], r8
0x180001068  and     esi, 1Fh
0x18000106b  cmp     esi, 1Fh
0x18000106e  jz      loc_1800012E4
0x180001074  mov     r9d, r8d
0x180001077  mov     eax, ebp
0x180001079  and     eax, 0FFFFFFC0h
0x18000107c  shl     eax, 18h
0x18000107f  or      eax, esi
0x180001081  cmp     r14d, eax
0x180001084  jz      short loc_1800010BA
0x180001086  mov     rax, [rbx+38h]
0x18000108a  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x180001091  cmp     rbx, rax
0x180001094  jz      short loc_18000109E
0x180001096  mov     rbx, rax
0x180001099  test    rax, rax
0x18000109c  jnz     short loc_180001086
0x18000109e  xor     eax, eax
0x1800010a0  mov     rbx, [rsp+68h+arg_8]
0x1800010a5  mov     rbp, [rsp+68h+arg_10]
0x1800010ad  add     rsp, 40h
0x1800010b1  pop     r15
0x1800010b3  pop     r14
0x1800010b5  pop     r12
0x1800010b7  pop     rdi
0x1800010b8  pop     rsi
0x1800010b9  retn
0x1800010ba  mov     ecx, [rbx+10h]
0x1800010bd  mov     eax, ecx
0x1800010bf  mov     edx, [rbx+18h]
0x1800010c2  sub     eax, r9d
0x1800010c5  add     eax, edx
0x1800010c7  cmp     eax, 1
0x1800010ca  jb      loc_1800012AB
0x1800010d0  movzx   esi, byte ptr [r8]
0x1800010d4  inc     r8
0x1800010d7  mov     [rbx+28h], r8
0x1800010db  cmp     esi, 80h
0x1800010e1  jnb     loc_1800011B7
0x1800010e7  sub     ecx, r8d
0x1800010ea  mov     r14d, r12d
0x1800010ed  add     ecx, edx
0x1800010ef  cmp     esi, ecx
0x1800010f1  ja      loc_1800012BD
0x1800010f7  mov     eax, 1
0x1800010fc  test    eax, eax
0x1800010fe  jz      short loc_18000109E
0x180001100  test    bpl, 20h
0x180001104  jnz     loc_180001411
0x18000110a  shr     esi, 1
0x18000110c  mov     [rdi], esi
0x18000110e  jz      loc_1800012A2
0x180001114  lea     eax, ds:2[rsi*2]
0x18000111b  mov     rbp, r12
0x18000111e  lea     ecx, [rax+3]
0x180001121  and     ecx, 0FFFFFFFCh
0x180001124  cmp     eax, ecx
0x180001126  ja      loc_1800012D2
0x18000112c  cmp     [rbx+4Ch], r12d
0x180001130  jnz     loc_180001367
0x180001136  mov     edx, ecx; uBytes
0x180001138  mov     ecx, 40h ; '@'; uFlags
0x18000113d  call    cs:__imp_LocalAlloc
0x180001143  mov     rbp, rax
0x180001146  test    rbp, rbp
0x180001149  jz      loc_1800012D2
0x18000114f  mov     [rdi+8], rbp
0x180001153  test    rbp, rbp
0x180001156  jz      loc_18000109E
0x18000115c  mov     r8d, r12d
0x18000115f  test    esi, esi
0x180001161  jz      short loc_18000119A
0x180001163  nop     dword ptr [rax+00h]
0x180001167  nop     word ptr [rax+rax+00000000h]
0x180001170  mov     rax, [rbx+28h]
0x180001174  movzx   ecx, byte ptr [rax]
0x180001177  movzx   edx, byte ptr [rax+1]
0x18000117b  mov     rax, [rdi+8]
0x18000117f  shl     cx, 8
0x180001183  or      dx, cx
0x180001186  mov     ecx, r8d
0x180001189  inc     r8d
0x18000118c  mov     [rax+rcx*2], dx
0x180001190  add     qword ptr [rbx+28h], 2
0x180001195  cmp     r8d, esi
0x180001198  jb      short loc_180001170
0x18000119a  mov     rcx, [rdi+8]
0x18000119e  mov     [rcx+rsi*2], r12w
0x1800011a3  mov     eax, cs:g_dwDecodingRules
0x1800011a9  test    al, 2
0x1800011ab  jz      short loc_18000121A
0x1800011ad  mov     eax, 1
0x1800011b2  jmp     loc_1800010A0
0x1800011b7  jz      short loc_18000120C
0x1800011b9  cmp     esi, 84h
0x1800011bf  ja      loc_18000149A
0x1800011c5  mov     eax, ecx
0x1800011c7  lea     r9d, [rsi-80h]
0x1800011cb  sub     eax, r8d
0x1800011ce  add     eax, edx
0x1800011d0  cmp     r9d, eax
0x1800011d3  ja      loc_1800012AB
0x1800011d9  mov     esi, r12d
0x1800011dc  cmp     r9d, 2
0x1800011e0  jnz     loc_180001279
0x1800011e6  movzx   eax, byte ptr [r8]
0x1800011ea  shl     eax, 8
0x1800011ed  or      esi, eax
0x1800011ef  inc     r8
0x1800011f2  mov     [rbx+28h], r8
0x1800011f6  movzx   eax, byte ptr [r8]
0x1800011fa  or      esi, eax
0x1800011fc  lea     rax, [r8+1]
0x180001200  mov     [rbx+28h], rax
0x180001204  mov     r8d, eax
0x180001207  jmp     loc_1800010E7
0x18000120c  mov     esi, r12d
0x18000120f  mov     r14d, 1
0x180001215  jmp     loc_180001100
0x18000121a  mov     r8, [rdi+8]
0x18000121e  xchg    ax, ax
0x180001220  mov     eax, esi
0x180001222  dec     esi
0x180001224  cmp     r12w, [r8+rsi*2]
0x180001229  jnz     short loc_180001234
0x18000122b  test    esi, esi
0x18000122d  jnz     short loc_180001220
0x18000122f  jmp     loc_1800011AD
0x180001234  mov     esi, 0FFFFFFFFh
0x180001239  nop     dword ptr [rax+00000000h]
0x180001240  test    eax, eax
0x180001242  jz      loc_1800011AD
0x180001248  add     eax, esi
0x18000124a  mov     rcx, r8; hMem
0x18000124d  cmp     r12w, [r8+rax*2]
0x180001252  jnz     short loc_180001240
0x180001254  cmp     [rbx+4Ch], r12d
0x180001258  jnz     short loc_180001260
0x18000125a  call    cs:__imp_LocalFree
0x180001260  mov     [rdi+8], r12
0x180001264  mov     edx, 0FFFFFC0Bh
0x180001269  mov     rcx, rbx
0x18000126c  mov     [rdi], r12d
0x18000126f  call    ASN1DecSetError
0x180001274  jmp     loc_18000109E
0x180001279  sub     r9d, 1
0x18000127d  jz      loc_1800011F6
0x180001283  sub     r9d, 2
0x180001287  jnz     loc_18000134A
0x18000128d  movzx   eax, byte ptr [r8]
0x180001291  shl     eax, 10h
0x180001294  or      esi, eax
0x180001296  inc     r8
0x180001299  mov     [rbx+28h], r8
0x18000129d  jmp     loc_1800011E6
0x1800012a2  mov     [rdi+8], r12
0x1800012a6  jmp     loc_1800011AD
0x1800012ab  mov     edx, 0FFFFFC16h
0x1800012b0  mov     rcx, rbx
0x1800012b3  call    ASN1DecSetError
0x1800012b8  jmp     loc_18000109E
0x1800012bd  mov     edx, 0FFFFFC16h
0x1800012c2  mov     rcx, rbx
0x1800012c5  call    ASN1DecSetError
0x1800012ca  mov     eax, r12d
0x1800012cd  jmp     loc_1800010FC
0x1800012d2  mov     edx, 0FFFFFC12h
0x1800012d7  mov     rcx, rbx
0x1800012da  call    ASN1DecSetError
0x1800012df  jmp     loc_18000114F
0x1800012e4  mov     esi, r12d
0x1800012e7  mov     r15d, r12d
0x1800012ea  mov     edx, 1
0x1800012ef  mov     rcx, rbx
0x1800012f2  call    ASN1BERDecCheck
0x1800012f7  test    eax, eax
0x1800012f9  jz      loc_18000109E
0x1800012ff  mov     rax, [rbx+28h]
0x180001303  movzx   ecx, byte ptr [rax]
0x180001306  lea     r8, [rax+1]
0x18000130a  mov     [rbx+28h], r8
0x18000130e  test    esi, 0E0000000h
0x180001314  jnz     short loc_180001338
0x180001316  mov     eax, esi
0x180001318  mov     edx, ecx
0x18000131a  and     ecx, 7Fh
0x18000131d  shl     eax, 7
0x180001320  mov     esi, ecx
0x180001322  mov     r9d, r8d
0x180001325  or      esi, eax
0x180001327  test    dl, dl
0x180001329  jns     loc_180001077
0x18000132f  inc     r15d
0x180001332  cmp     r15d, 4
0x180001336  jb      short loc_1800012EA
0x180001338  mov     edx, 0FFFFFC0Dh
0x18000133d  mov     rcx, rbx
0x180001340  call    ASN1DecSetError
0x180001345  jmp     loc_18000109E
0x18000134a  cmp     r9d, 1
0x18000134e  jnz     loc_1800010E7
0x180001354  movzx   esi, byte ptr [r8]
0x180001358  shl     esi, 18h
0x18000135b  inc     r8
0x18000135e  mov     [rbx+28h], r8
0x180001362  jmp     loc_18000128D
0x180001367  mov     edx, [rbx+68h]
0x18000136a  cmp     edx, ecx
0x18000136c  jb      loc_1800012D2
0x180001372  mov     rbp, [rbx+60h]
0x180001376  mov     eax, ecx
0x180001378  add     rax, rbp
0x18000137b  sub     edx, ecx
0x18000137d  mov     [rbx+60h], rax
0x180001381  mov     [rbx+68h], edx
0x180001384  jmp     loc_180001146
0x180001389  add     ecx, [rdi]
0x18000138b  cmp     ecx, [rdi]
0x18000138d  jnb     short loc_1800013A9
0x18000138f  cmp     [rbx+4Ch], r12d
0x180001393  jnz     loc_18000109E
0x180001399  mov     rcx, [rsp+68h+hMem]; hMem
0x18000139e  call    cs:__imp_LocalFree
0x1800013a4  jmp     loc_18000109E
0x1800013a9  lea     eax, [rcx+1]
0x1800013ac  cmp     eax, ecx
0x1800013ae  jb      short loc_18000138F
0x1800013b0  mov     r8d, eax
0x1800013b3  add     r8, r8
0x1800013b6  cmp     r8, rsi
0x1800013b9  ja      short loc_18000138F
0x1800013bb  mov     rdx, [rdi+8]
0x1800013bf  mov     rcx, rbp
0x1800013c2  call    DecMemReAlloc
0x1800013c7  mov     [rdi+8], rax
0x1800013cb  test    rax, rax
0x1800013ce  jz      short loc_18000138F
0x1800013d0  mov     ecx, [rdi]
0x1800013d2  mov     r8d, dword ptr [rsp+68h+var_38]
0x1800013d7  mov     rdx, [rsp+68h+hMem]; Src
0x1800013dc  add     r8, r8; Size
0x1800013df  lea     rcx, [rax+rcx*2]; void *
0x1800013e3  call    memcpy_0
0x1800013e8  mov     eax, dword ptr [rsp+68h+var_38]
0x1800013ec  add     [rdi], eax
0x1800013ee  mov     edx, [rdi]
0x1800013f0  mov     rcx, [rdi+8]
0x1800013f4  mov     [rcx+rdx*2], r12w
0x1800013f9  cmp     [rbx+4Ch], r12d
0x1800013fd  jnz     short loc_18000140A
0x1800013ff  mov     rcx, [rsp+68h+hMem]; hMem
0x180001404  call    cs:__imp_LocalFree
0x18000140a  mov     [rsp+68h+hMem], r12
0x18000140f  jmp     short loc_180001451
0x180001411  lea     rax, [rsp+68h+arg_18]
0x180001419  mov     [rdi], r12d
0x18000141c  lea     r9, [rsp+68h+arg_0]
0x180001421  mov     [rsp+68h+var_48], rax
0x180001426  mov     r8d, r14d
0x180001429  mov     [rdi+8], r12
0x18000142d  mov     edx, esi
0x18000142f  mov     rcx, rbx
0x180001432  call    _BERDecConstructed
0x180001437  test    eax, eax
0x180001439  jz      loc_18000109E
0x18000143f  mov     rbp, [rsp+68h+arg_0]
0x180001444  mov     esi, 0FFFFFFFFh
0x180001449  mov     r14, [rsp+68h+arg_18]
0x180001451  mov     rdx, r14
0x180001454  mov     rcx, rbp
0x180001457  call    ASN1BERDecNotEndOfContents
0x18000145c  test    eax, eax
  ... truncated ...
```
