# GetUriInfo(ushort const *,ulong,ulong,UriInfo *)

- ea: `0x180018e00`
- end: `0x180019634`
- name: `?GetUriInfo@@YAJPEBGKKPEAVUriInfo@@@Z`
- size: `2100`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned int, struct UriInfo *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010420`
- `0x180016c10`
- `0x180017620`
- `0x180048948`

## callees

- `0x180003c80`
- `0x180018e00`
- `0x18001a5a8`
- `0x18001a614`
- `0x18001a660`
- `0x18005911c`

## import_xrefs

- `msvcrt!iswascii` at `0x1800193ce`
- `msvcrt!iswascii` at `0x1800193ce`
- `msvcrt!iswalpha` at `0x1800193dd`
- `msvcrt!iswalpha` at `0x1800193dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180018f40`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180018f40`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001956d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001956d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x1800191b1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180019621`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x1800191b1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180019621`

## pseudocode

```c
__int64 __fastcall GetUriInfo(const unsigned __int16 *a1, unsigned int a2, int a3, __m128i *a4)
{
  unsigned int v8; // r13d
  __m128i v9; // xmm6
  __m128i v10; // xmm8
  __m128i v11; // xmm7
  __m128i v12; // xmm9
  __m128i v13; // xmm10
  unsigned int v14; // ebx
  __int64 v15; // r11
  int v16; // ecx
  unsigned int v17; // r9d
  const unsigned __int16 *i; // r10
  int v19; // edx
  unsigned int v20; // ecx
  int v21; // edx
  int v22; // eax
  int v23; // r15d
  double v24; // xmm1_8
  __int64 result; // rax
  __m128i v26; // xmm0
  unsigned int v27; // ebx
  __int64 *v28; // rcx
  __m128i v29; // xmm1
  __m128i v30; // xmm2
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int64 v33; // xmm0_8
  int v34; // eax
  __int64 *v35; // rax
  char v36; // si
  int v37; // eax
  __int64 (__fastcall *v38)(PCWSTR, unsigned int, unsigned int, struct UriComponents *); // rcx
  int v39; // ebx
  int v40; // r8d
  int v41; // edx
  int v42; // ecx
  unsigned int v43; // eax
  enum URL_SCHEME v44; // ecx
  const struct UriSchemeInfo *UriSchemeInfo; // rax
  __m128i v46; // xmm1
  __int128 v47; // xmm0
  __int64 v48; // rax
  unsigned int v49; // edi
  unsigned __int16 v50; // ax
  unsigned __int16 v51; // ax
  unsigned __int16 v52; // ax
  __int64 v53; // r10
  __int64 v54; // r10
  __int16 v55; // ax
  __int16 v56; // r8
  __int16 *v57; // rsi
  __m128i v58; // [rsp+38h] [rbp-99h] BYREF
  __int128 v59; // [rsp+48h] [rbp-89h]
  __m128i v60; // [rsp+58h] [rbp-79h]
  __int128 v61; // [rsp+68h] [rbp-69h]
  __int128 v62; // [rsp+78h] [rbp-59h]
  __int64 v63; // [rsp+88h] [rbp-49h]
  unsigned __int64 v64; // [rsp+90h] [rbp-41h]
  __int64 v65; // [rsp+98h] [rbp-39h]
  int v66; // [rsp+140h] [rbp+6Fh]
  int v67; // [rsp+150h] [rbp+7Fh]

  v66 = 0;
  v63 = 0;
  v8 = 0;
  v67 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0x7FFFFFE03FFLL;
  while ( 1 )
  {
    if ( v14 == a2 )
      goto LABEL_23;
    if ( v14 > a2 )
      goto LABEL_11;
    if ( !v14 && *a1 == 58 )
    {
LABEL_23:
      if ( PathIsUNCW(a1) || (unsigned __int16)(*a1 - 1) <= 0x7Eu && isalpha_0((unsigned __int8)*a1) && a1[1] == 58 )
      {
        if ( (a3 & 4) != 0 )
          goto LABEL_70;
        goto LABEL_30;
      }
      if ( a2 && (a3 & 2) != 0 )
      {
        v44 = URL_SCHEME_WILDCARD;
LABEL_71:
        v66 = 1;
        UriSchemeInfo = GetUriSchemeInfo(v44);
        v46 = *((__m128i *)UriSchemeInfo + 2);
        v30 = *(__m128i *)UriSchemeInfo;
        v59 = *((_OWORD *)UriSchemeInfo + 1);
        v47 = *((_OWORD *)UriSchemeInfo + 3);
        v60 = v46;
        v32 = *((_OWORD *)UriSchemeInfo + 4);
        v61 = v47;
        v33 = *((_QWORD *)UriSchemeInfo + 10);
      }
      else
      {
        if ( (a3 & 1) == 0 )
          goto LABEL_30;
        v30 = (__m128i)xmmword_180108930;
        v59 = xmmword_180108940;
        v61 = xmmword_180108960;
        v33 = 2;
        v60 = *(__m128i *)&off_180108950;
        v32 = xmmword_180108970;
        v67 = 1;
        v66 = 1;
      }
LABEL_36:
      v34 = _mm_cvtsi128_si32(v30);
      v58 = v30;
      v62 = v32;
      v63 = v33;
      if ( v34 == 9 )
      {
        if ( (a3 & 0x20) != 0 )
        {
          v35 = &qword_1800E5900;
LABEL_40:
          v9 = *(__m128i *)v35;
          v58 = *(__m128i *)v35;
          v10 = *((__m128i *)v35 + 1);
          v59 = (__int128)v10;
          v11 = *((__m128i *)v35 + 2);
          v60 = v11;
          v12 = *((__m128i *)v35 + 3);
          v61 = (__int128)v12;
          v13 = *((__m128i *)v35 + 4);
          v62 = (__int128)v13;
          v63 = v35[10];
          if ( (a3 & 0x10) != 0 )
          {
            v36 = ~v60.m128i_i8[12] & v60.m128i_i8[8];
            v60.m128i_i32[2] &= ~v60.m128i_i32[3];
            v11 = v60;
          }
          else
          {
            v36 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
          }
          if ( (_DWORD)v63 != 1 && (a3 & 0x4000) == 0 && !GetIDNSettingsForIE() )
            LODWORD(v63) = 1;
          if ( (a3 & 0xA000000) != 0 )
          {
            LODWORD(v62) = v62 & 0xFFFC0FFF | 0x12000;
            v13 = (__m128i)v62;
          }
          if ( (a3 & 0x80u) == 0 )
          {
LABEL_47:
            v37 = _mm_cvtsi128_si32(v9);
            if ( v37 )
            {
              v39 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 12));
            }
            else
            {
              v38 = (__int64 (__fastcall *)(PCWSTR, unsigned int, unsigned int, struct UriComponents *))v60.m128i_i64[0];
              v39 = _mm_cvtsi128_si32(_mm_srli_si128(v10, 12));
              if ( v8 )
              {
                v48 = v8 + 1;
                if ( (unsigned int)v48 < a2 && a1[v48] != 47 )
                {
                  v39 = 1;
                  v38 = RelativeCrack;
                }
              }
              v37 = 0;
              v58.m128i_i64[1] = (__int64)a1;
              v58.m128i_i32[0] = 0;
              v9 = v58;
              LODWORD(v59) = v8;
              HIDWORD(v59) = v39;
              v10 = (__m128i)v59;
              v60.m128i_i64[0] = (__int64)v38;
              v11 = v60;
            }
            v23 = v66;
            v20 = 0;
            v21 = v67;
            if ( v66 || v67 || v39 == 1 )
            {
              v22 = 0;
              goto LABEL_31;
            }
            if ( v37 == 9 )
            {
              v49 = a2 - v8;
              if ( v49 < 3
                || a1[v8] != 58
                || (v50 = a1[v8 + 1], v50 != 47) && v50 != 92
                || (v51 = a1[v8 + 2], v51 != 47) && v51 != 92 )
              {
                if ( v49 < 5
                  || a1[v8] != 58
                  || a1[v8 + 1] != 47
                  || (v52 = a1[v8 + 3], v52 != 58) && v52 != 124
                  || a1[v8 + 4] != 47
                  || !iswascii(a1[2])
                  || !iswalpha(a1[2]) )
                {
LABEL_99:
                  v22 = 0;
                  if ( !v39 )
                  {
                    v21 = 1;
                    v20 = 0;
                    goto LABEL_31;
                  }
                  goto LABEL_57;
                }
              }
            }
            else if ( StrCmpNW(&a1[v8], L"://", 3) && ((v36 & 2) == 0 || StrCmpNW(&a1[v8], L":\\\\", 3)) )
            {
              goto LABEL_99;
            }
            v22 = 1;
LABEL_57:
            v20 = 0;
            v21 = 0;
            goto LABEL_31;
          }
          v40 = _mm_cvtsi128_si32(_mm_srli_si128(v12, 12));
          v41 = _mm_cvtsi128_si32(_mm_srli_si128(v12, 4));
          if ( (a3 & 0xA000000) != 0 )
          {
            v42 = _mm_cvtsi128_si32(v12);
          }
          else
          {
            if ( (v41 & 0x10000) != 0 )
            {
              v42 = v61 & 0xFFFC7FFF | 0x10000;
              LODWORD(v61) = v42;
              v12 = (__m128i)v61;
            }
            else
            {
              v42 = _mm_cvtsi128_si32(v12);
            }
            if ( (v40 & 0x10000) != 0 )
            {
              v43 = DWORD2(v61) & 0xFFFC7FFF | 0x10000;
              DWORD2(v61) = v43;
              v12 = (__m128i)v61;
LABEL_63:
              if ( (v41 & 0x80000) != 0 )
              {
                LODWORD(v61) = v42 & 0xFFE3FFFF | 0x80000;
                v12 = (__m128i)v61;
              }
              if ( (v40 & 0x80000) != 0 )
              {
                DWORD2(v61) = v43 & 0xFFE3FFFF | 0x80000;
                v12 = (__m128i)v61;
              }
              goto LABEL_47;
            }
          }
          v43 = _mm_cvtsi128_si32(_mm_srli_si128(v12, 8));
          goto LABEL_63;
        }
      }
      else if ( !v34 && (a3 & 0x400) != 0 )
      {
        v35 = qword_180086840;
        goto LABEL_40;
      }
      v35 = (__int64 *)&v58;
      goto LABEL_40;
    }
    v16 = a1[v14];
    if ( v16 == 58 )
      break;
    if ( v16 != 43
      && (unsigned int)(v16 - 45) >= 2
      && ((unsigned __int16)v16 >= 0x80u
       || ((unsigned __int8)(v16 - 48) > 0x2Au || !_bittest64(&v15, (unsigned __int8)(v16 - 48)))
       && (unsigned __int8)(v16 - 97) > 0x19u)
      && (v14 || a2 <= 1 || *a1 != 42 || a1[1] != 58 || (a3 & 1) != 0) )
    {
      goto LABEL_23;
    }
    ++v14;
  }
  if ( (unsigned __int16)(*a1 - 1) > 0x7Eu )
  {
LABEL_10:
    v8 = v14;
LABEL_11:
    if ( v8 == 1 && *a1 == 42 )
    {
LABEL_33:
      _mm_lfence();
      v27 = dword_180284BB0[v8];
      if ( v27 != -1 )
      {
        while ( v27 < 0x17 )
        {
          v57 = &_ImageBase[4 * v27 + 701120];
          if ( *(_DWORD *)(*(_QWORD *)v57 + 16LL) != v8 )
            break;
          if ( !StrCmpNICW(a1, *(LPCWSTR *)(*(_QWORD *)v57 + 8LL), v8) )
          {
            if ( **(_DWORD **)v57 != 28 || (a3 & 0x1000000) != 0 )
            {
              v28 = (&off_180156580)[v27];
              goto LABEL_35;
            }
            break;
          }
          ++v27;
        }
      }
LABEL_34:
      v28 = qword_180086000;
LABEL_35:
      v29 = *((__m128i *)v28 + 2);
      v30 = *(__m128i *)v28;
      v59 = *((_OWORD *)v28 + 1);
      v31 = *((_OWORD *)v28 + 3);
      v60 = v29;
      v32 = *((_OWORD *)v28 + 4);
      v61 = v31;
      v33 = v28[10];
      goto LABEL_36;
    }
    v17 = v8;
    for ( i = a1; ; ++i )
    {
      if ( !v17 )
      {
        if ( v8 >= 0x10 )
          goto LABEL_34;
        goto LABEL_33;
      }
      v19 = *i;
      if ( v19 != 37 )
        break;
      if ( !(unsigned int)IsPercentEncodedOctetW(i, v17) )
        goto LABEL_102;
      HexToWord(*(unsigned __int16 *)(v53 + 4));
      v55 = HexToWord(*(unsigned __int16 *)(v54 + 2));
      v19 = (unsigned __int16)(16 * v55 + v56);
      if ( v19 != 43 && (unsigned int)(v19 - 45) >= 2 )
      {
        if ( (unsigned __int16)v19 >= 0x80u )
        {
LABEL_102:
          v21 = 0;
          v20 = -2147024809;
          v22 = 0;
          v23 = 0;
          goto LABEL_31;
        }
        if ( (unsigned __int8)(16 * v55 + v56 - 48) > 0x2Au || !_bittest64(&v15, (unsigned __int8)(16 * v55 + v56 - 48)) )
          goto LABEL_101;
      }
LABEL_21:
      --v17;
    }
    if ( v19 == 43 || (unsigned int)(v19 - 45) < 2 )
      goto LABEL_21;
    if ( (unsigned __int16)v19 >= 0x80u )
      goto LABEL_102;
    if ( (unsigned __int8)(v19 - 48) <= 0x2Au && _bittest64(&v15, (unsigned __int8)(v19 - 48)) )
      goto LABEL_21;
LABEL_101:
    if ( (unsigned __int8)(v19 - 97) > 0x19u )
      goto LABEL_102;
    goto LABEL_21;
  }
  if ( !isalpha_0((unsigned __int8)*a1) || a1[1] != 58 )
  {
    v15 = 0x7FFFFFE03FFLL;
    goto LABEL_10;
  }
  if ( (a3 & 4) != 0 )
  {
LABEL_70:
    v44 = URL_SCHEME_FILE;
    goto LABEL_71;
  }
LABEL_30:
  v20 = -2146697214;
  v21 = 0;
  v22 = 0;
  v23 = 0;
LABEL_31:
  v24 = *(double *)&v63;
  *a4 = v9;
  a4[1] = v10;
  a4[2] = v11;
  a4[3] = v12;
  a4[4] = v13;
  LODWORD(v65) = v22;
  result = v20;
  v64 = __PAIR64__(v21, v23);
  v26.m128i_i64[1] = __PAIR64__(v21, v23);
  *(double *)v26.m128i_i64 = v24;
  a4[5] = v26;
  a4[6].m128i_i64[0] = v65;
  return result;
}

```

## disassembly

```asm
0x180018e00  mov     rax, rsp
0x180018e03  mov     [rax+8], rbx
0x180018e07  push    rbp
0x180018e08  push    rsi
0x180018e09  push    rdi
0x180018e0a  push    r12
0x180018e0c  push    r13
0x180018e0e  push    r14
0x180018e10  push    r15
0x180018e12  lea     rbp, [rax-5Fh]
0x180018e16  sub     rsp, 0F0h
0x180018e1d  movaps  xmmword ptr [rax-48h], xmm6
0x180018e21  mov     r14, rcx
0x180018e24  movaps  xmmword ptr [rax-58h], xmm7
0x180018e28  xor     ecx, ecx
0x180018e2a  movaps  xmmword ptr [rax-68h], xmm8
0x180018e2f  mov     r12, r9
0x180018e32  movaps  xmmword ptr [rax-78h], xmm9
0x180018e37  mov     r15d, r8d
0x180018e3a  movaps  xmmword ptr [rax-88h], xmm10
0x180018e42  mov     edi, edx
0x180018e44  xor     eax, eax
0x180018e46  mov     [rbp+57h+arg_8], ecx
0x180018e49  mov     qword ptr [rbp+57h+var_A0], rax
0x180018e4d  mov     r13d, ecx
0x180018e50  mov     [rbp+57h+arg_18], ecx
0x180018e53  xorps   xmm6, xmm6
0x180018e56  xorps   xmm8, xmm8
0x180018e5a  xorps   xmm7, xmm7
0x180018e5d  xorps   xmm9, xmm9
0x180018e61  xorps   xmm10, xmm10
0x180018e65  mov     ebx, ecx
0x180018e67  mov     esi, 80h
0x180018e6c  mov     r11, 7FFFFFE03FFh
0x180018e76  cmp     ebx, edi
0x180018e78  jz      loc_180018F3D
0x180018e7e  ja      short loc_180018ECA
0x180018e80  test    ebx, ebx
0x180018e82  jz      loc_180018F32
0x180018e88  mov     eax, ebx
0x180018e8a  movzx   ecx, word ptr [r14+rax*2]
0x180018e8f  cmp     ecx, 3Ah ; ':'
0x180018e92  jnz     loc_18001950C
0x180018e98  movzx   ecx, word ptr [r14]
0x180018e9c  lea     eax, [rcx-1]
0x180018e9f  cmp     ax, 7Eh ; '~'
0x180018ea3  ja      short loc_180018EC7
0x180018ea5  movzx   ecx, cl; C
0x180018ea8  call    isalpha_0
0x180018ead  test    eax, eax
0x180018eaf  jz      short loc_180018EBD
0x180018eb1  cmp     word ptr [r14+2], 3Ah ; ':'
0x180018eb7  jz      loc_1800193EC
0x180018ebd  mov     r11, 7FFFFFE03FFh
0x180018ec7  mov     r13d, ebx
0x180018eca  cmp     r13d, 1
0x180018ece  jnz     short loc_180018EDB
0x180018ed0  cmp     word ptr [r14], 2Ah ; '*'
0x180018ed5  jz      loc_18001901B
0x180018edb  mov     r9d, r13d
0x180018ede  mov     r10, r14
0x180018ee1  test    r9d, r9d
0x180018ee4  jz      loc_180019015
0x180018eea  movzx   edx, word ptr [r10]
0x180018eee  cmp     edx, 25h ; '%'
0x180018ef1  jz      loc_180019459
0x180018ef7  mov     ecx, edx
0x180018ef9  sub     ecx, 2Bh ; '+'
0x180018efc  jz      short loc_180018F29
0x180018efe  sub     ecx, 2
0x180018f01  jz      short loc_180018F29
0x180018f03  cmp     ecx, 1
0x180018f06  jz      short loc_180018F29
0x180018f08  cmp     dx, si
0x180018f0b  jnb     loc_180019447
0x180018f11  lea     eax, [rdx-30h]
0x180018f14  cmp     al, 2Ah ; '*'
0x180018f16  ja      loc_18001943B
0x180018f1c  movzx   eax, al
0x180018f1f  bt      r11, rax
0x180018f23  jnb     loc_18001943B
0x180018f29  add     r10, 2
0x180018f2d  dec     r9d
0x180018f30  jmp     short loc_180018EE1
0x180018f32  cmp     word ptr [r14], 3Ah ; ':'
0x180018f37  jnz     loc_180018E88
0x180018f3d  mov     rcx, r14; pszPath
0x180018f40  call    cs:__imp_PathIsUNCW
0x180018f46  test    eax, eax
0x180018f48  jnz     loc_180019297
0x180018f4e  movzx   ecx, word ptr [r14]
0x180018f52  lea     eax, [rcx-1]
0x180018f55  cmp     ax, 7Eh ; '~'
0x180018f59  ja      short loc_180018F73
0x180018f5b  movzx   ecx, cl; C
0x180018f5e  call    isalpha_0
0x180018f63  test    eax, eax
0x180018f65  jz      short loc_180018F73
0x180018f67  cmp     word ptr [r14+2], 3Ah ; ':'
0x180018f6d  jz      loc_180019297
0x180018f73  test    edi, edi
0x180018f75  jz      short loc_180018F81
0x180018f77  test    r15b, 2
0x180018f7b  jnz     loc_1800195AD
0x180018f81  test    r15b, 1
0x180018f85  jnz     loc_1800195B7
0x180018f8b  mov     ecx, 800C0002h
0x180018f90  mov     edx, r13d
0x180018f93  mov     eax, r13d
0x180018f96  mov     r15d, r13d
0x180018f99  movsd   xmm1, qword ptr [rbp+57h+var_A0]
0x180018f9e  lea     r11, [rsp+120h+var_30]
0x180018fa6  mov     rbx, [r11+40h]
0x180018faa  movaps  xmmword ptr [r12], xmm6
0x180018faf  movaps  xmm6, xmmword ptr [r11-10h]
0x180018fb4  movaps  xmmword ptr [r12+10h], xmm8
0x180018fba  movaps  xmm8, xmmword ptr [r11-30h]
0x180018fbf  movaps  xmmword ptr [r12+20h], xmm7
0x180018fc5  movaps  xmm7, xmmword ptr [r11-20h]
0x180018fca  movaps  xmmword ptr [r12+30h], xmm9
0x180018fd0  movaps  xmm9, xmmword ptr [r11-40h]
0x180018fd5  movaps  xmmword ptr [r12+40h], xmm10
0x180018fdb  movaps  xmm10, xmmword ptr [r11-50h]
0x180018fe0  mov     dword ptr [rbp+57h+var_90], eax
0x180018fe3  mov     eax, ecx
0x180018fe5  mov     dword ptr [rbp+57h+var_A0+8], r15d
0x180018fe9  mov     dword ptr [rbp+57h+var_A0+0Ch], edx
0x180018fec  movups  xmm0, [rbp+57h+var_A0]
0x180018ff0  movsd   xmm0, xmm1
0x180018ff4  movaps  xmmword ptr [r12+50h], xmm0
0x180018ffa  movsd   xmm0, [rbp+57h+var_90]
0x180018fff  movsd   qword ptr [r12+60h], xmm0
0x180019006  mov     rsp, r11
0x180019009  pop     r15
0x18001900b  pop     r14
0x18001900d  pop     r13
0x18001900f  pop     r12
0x180019011  pop     rdi
0x180019012  pop     rsi
0x180019013  pop     rbp
0x180019014  retn
0x180019015  cmp     r13d, 10h
0x180019019  jnb     short loc_180019038
0x18001901b  lfence
0x18001901e  mov     eax, r13d
0x180019021  lea     rcx, __ImageBase
0x180019028  mov     ebx, ds:rva dword_180284BB0[rcx+rax*4]
0x18001902f  cmp     ebx, 0FFFFFFFFh
0x180019032  jnz     loc_180019540
0x180019038  lea     rcx, qword_180086000
0x18001903f  movups  xmm0, xmmword ptr [rcx+10h]
0x180019043  movups  xmm1, xmmword ptr [rcx+20h]
0x180019047  movups  xmm2, xmmword ptr [rcx]
0x18001904a  movaps  [rsp+120h+var_E8+8], xmm0
0x18001904f  movups  xmm0, xmmword ptr [rcx+30h]
0x180019053  movaps  [rbp+57h+var_D0], xmm1
0x180019057  movups  xmm1, xmmword ptr [rcx+40h]
0x18001905b  movaps  [rbp+57h+var_C0], xmm0
0x18001905f  movsd   xmm0, qword ptr [rcx+50h]
0x180019064  movd    eax, xmm2
0x180019068  movaps  [rsp+120h+var_F8+8], xmm2
0x18001906d  movaps  [rbp+57h+var_B0], xmm1
0x180019071  movsd   qword ptr [rbp+57h+var_A0], xmm0
0x180019076  cmp     eax, 9
0x180019079  jz      loc_180019283
0x18001907f  test    eax, eax
0x180019081  jnz     loc_18001928D
0x180019087  bt      r15d, 0Ah
0x18001908c  jnb     loc_18001928D
0x180019092  lea     rax, qword_180086840
0x180019099  movups  xmm6, xmmword ptr [rax]
0x18001909c  movaps  [rsp+120h+var_F8+8], xmm6
0x1800190a1  movups  xmm8, xmmword ptr [rax+10h]
0x1800190a6  movaps  [rsp+120h+var_E8+8], xmm8
0x1800190ac  movups  xmm7, xmmword ptr [rax+20h]
0x1800190b0  movaps  [rbp+57h+var_D0], xmm7
0x1800190b4  movups  xmm9, xmmword ptr [rax+30h]
0x1800190b9  movaps  [rbp+57h+var_C0], xmm9
0x1800190be  movups  xmm10, xmmword ptr [rax+40h]
0x1800190c3  movaps  [rbp+57h+var_B0], xmm10
0x1800190c8  movsd   xmm0, qword ptr [rax+50h]
0x1800190cd  movsd   qword ptr [rbp+57h+var_A0], xmm0
0x1800190d2  test    r15b, 10h
0x1800190d6  jnz     loc_1800193FB
0x1800190dc  movdqa  xmm0, xmm7
0x1800190e0  psrldq  xmm0, 8
0x1800190e5  movd    esi, xmm0
0x1800190e9  cmp     dword ptr [rbp+57h+var_A0], 1
0x1800190ed  jz      short loc_1800190FA
0x1800190ef  bt      r15d, 0Eh
0x1800190f4  jnb     loc_1800192DC
0x1800190fa  mov     ecx, r15d
0x1800190fd  and     ecx, 0A000000h
0x180019103  jnz     loc_1800191CD
0x180019109  test    r15b, r15b
0x18001910c  js      loc_1800191E7
0x180019112  movd    eax, xmm6
0x180019116  mov     r8d, 2Fh ; '/'
0x18001911c  test    eax, eax
0x18001911e  jnz     short loc_180019160
0x180019120  mov     rcx, qword ptr [rbp+57h+var_D0]
0x180019124  psrldq  xmm8, 0Ch
0x18001912a  movd    ebx, xmm8
0x18001912f  test    r13d, r13d
0x180019132  jnz     loc_1800192F5
0x180019138  xor     eax, eax
0x18001913a  mov     qword ptr [rsp+120h+var_E8], r14
0x18001913f  mov     dword ptr [rsp+120h+var_F8+8], eax
0x180019143  movaps  xmm6, [rsp+120h+var_F8+8]
0x180019148  mov     dword ptr [rsp+120h+var_E8+8], r13d
0x18001914d  mov     [rbp+57h+var_D4], ebx
0x180019150  movaps  xmm8, [rsp+120h+var_E8+8]
0x180019156  mov     qword ptr [rbp+57h+var_D0], rcx
0x18001915a  movaps  xmm7, [rbp+57h+var_D0]
0x18001915e  jmp     short loc_18001916E
0x180019160  movdqa  xmm0, xmm8
0x180019165  psrldq  xmm0, 0Ch
0x18001916a  movd    ebx, xmm0
0x18001916e  mov     r15d, [rbp+57h+arg_8]
0x180019172  xor     ecx, ecx
0x180019174  mov     edx, [rbp+57h+arg_18]
0x180019177  test    r15d, r15d
0x18001917a  jnz     loc_180019335
0x180019180  test    edx, edx
0x180019182  jnz     loc_180019335
0x180019188  cmp     ebx, 1
0x18001918b  jz      loc_180019335
0x180019191  cmp     eax, 9
0x180019194  jz      loc_18001933C
0x18001919a  mov     eax, r13d
0x18001919d  lea     rdx, asc_180158888; "://"
0x1800191a4  mov     r8d, 3; nChar
0x1800191aa  lea     rdi, [r14+rax*2]
0x1800191ae  mov     rcx, rdi; psz1
0x1800191b1  call    cs:__imp_StrCmpNW
0x1800191b7  test    eax, eax
0x1800191b9  jnz     loc_18001941B
0x1800191bf  mov     eax, 1
0x1800191c4  xor     ecx, ecx
0x1800191c6  mov     edx, ecx
0x1800191c8  jmp     loc_180018F99
0x1800191cd  mov     eax, dword ptr [rbp+57h+var_B0]
0x1800191d0  and     eax, 0FFFD2FFFh
0x1800191d5  or      eax, 12000h
0x1800191da  mov     dword ptr [rbp+57h+var_B0], eax
0x1800191dd  movaps  xmm10, [rbp+57h+var_B0]
0x1800191e2  jmp     loc_180019109
0x1800191e7  movdqa  xmm0, xmm9
0x1800191ec  movdqa  xmm1, xmm9
0x1800191f1  psrldq  xmm0, 0Ch
0x1800191f6  psrldq  xmm1, 4
0x1800191fb  movd    r8d, xmm0
0x180019200  movd    edx, xmm1
0x180019204  test    ecx, ecx
0x180019206  jnz     loc_18001931D
0x18001920c  bt      edx, 10h
0x180019210  jnb     loc_180019411
0x180019216  mov     ecx, dword ptr [rbp+57h+var_C0]
0x180019219  and     ecx, 0FFFD7FFFh
0x18001921f  bts     ecx, 10h
0x180019223  mov     dword ptr [rbp+57h+var_C0], ecx
0x180019226  movaps  xmm9, [rbp+57h+var_C0]
0x18001922b  bt      r8d, 10h
0x180019230  jnb     loc_180019322
0x180019236  mov     eax, dword ptr [rbp+57h+var_C0+8]
0x180019239  and     eax, 0FFFD7FFFh
0x18001923e  bts     eax, 10h
0x180019242  mov     dword ptr [rbp+57h+var_C0+8], eax
0x180019245  movaps  xmm9, [rbp+57h+var_C0]
0x18001924a  bt      edx, 13h
0x18001924e  jnb     short loc_180019262
0x180019250  and     ecx, 0FFEBFFFFh
0x180019256  bts     ecx, 13h
0x18001925a  mov     dword ptr [rbp+57h+var_C0], ecx
0x18001925d  movaps  xmm9, [rbp+57h+var_C0]
0x180019262  bt      r8d, 13h
0x180019267  jnb     loc_180019112
0x18001926d  and     eax, 0FFEBFFFFh
0x180019272  bts     eax, 13h
0x180019276  mov     dword ptr [rbp+57h+var_C0+8], eax
0x180019279  movaps  xmm9, [rbp+57h+var_C0]
0x18001927e  jmp     loc_180019112
0x180019283  test    r15b, 20h
0x180019287  jnz     loc_1800194C7
0x18001928d  lea     rax, [rsp+120h+var_F8+8]
0x180019292  jmp     loc_180019099
0x180019297  test    r15b, 4
0x18001929b  jz      loc_180018F8B
0x1800192a1  mov     ecx, 9; enum URL_SCHEME
0x1800192a6  mov     [rbp+57h+arg_8], 1
0x1800192ad  call    ?GetUriSchemeInfo@@YAAEBUUriSchemeInfo@@W4URL_SCHEME@@@Z; GetUriSchemeInfo(URL_SCHEME)
0x1800192b2  movups  xmm0, xmmword ptr [rax+10h]
0x1800192b6  movups  xmm1, xmmword ptr [rax+20h]
0x1800192ba  movups  xmm2, xmmword ptr [rax]
0x1800192bd  movaps  [rsp+120h+var_E8+8], xmm0
0x1800192c2  movups  xmm0, xmmword ptr [rax+30h]
0x1800192c6  movaps  [rbp+57h+var_D0], xmm1
0x1800192ca  movups  xmm1, xmmword ptr [rax+40h]
0x1800192ce  movaps  [rbp+57h+var_C0], xmm0
0x1800192d2  movsd   xmm0, qword ptr [rax+50h]
  ... truncated ...
```
