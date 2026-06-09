# TextAppendRecord(x,x,x)

- ea: `0x1001e1e0`
- end: `0x1001eab6`
- name: `_TextAppendRecord@12`
- size: `2262`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops`

## callers

- `0x100154f0`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000bfb0`
- `0x1000c2f0`
- `0x1001d770`
- `0x1001d830`
- `0x1001dc10`
- `0x1001dde0`
- `0x1001de20`
- `0x1001e1e0`
- `0x1001f270`
- `0x10022400`
- `0x100232f0`
- `0x10023ac0`
- `0x10023b10`
- `0x10024170`
- `0x100241b0`
- `0x100241f0`
- `0x10024220`
- `0x10024250`
- `0x10024700`
- `0x10026500`
- `0x100268c0`
- `0x10026bf0`
- `0x10026c60`
- `0x10029520`
- `0x1002b81a`
- `0x1002c3dd`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1001e3e2`
- `KERNEL32!SetFilePointer` at `0x1001e3e2`
- `KERNEL32!GetStringTypeW` at `0x1001e839`
- `KERNEL32!GetStringTypeW` at `0x1001e839`
- `KERNEL32!GetStringTypeA` at `0x1001e860`
- `KERNEL32!GetStringTypeA` at `0x1001e860`

## pseudocode

```c
int __userpurge TextAppendRecord@<eax>(int a1@<ebx>, int a2, int *a3, __m128i *a4)
{
  int v4; // edx
  int v5; // ebx
  int v6; // edi
  bool v7; // zf
  wchar_t *v8; // esi
  int v9; // ebp
  int result; // eax
  _DWORD *v11; // esi
  _DWORD *v12; // ecx
  unsigned int v13; // eax
  int *v14; // edi
  int v15; // eax
  int v16; // ecx
  WCHAR *v17; // esi
  WCHAR *v18; // edx
  int v19; // ecx
  WCHAR *v20; // eax
  int v21; // eax
  int v22; // eax
  size_t v23; // edi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // ebx
  int v28; // ecx
  WCHAR *v29; // ebp
  WCHAR *v30; // edx
  WCHAR *v32; // eax
  int v33; // ecx
  int v34; // eax
  int Field; // eax
  const WCHAR *v36; // esi
  CHAR *v37; // eax
  LPCSTR i; // ebx
  WCHAR *v39; // edi
  int v40; // ebx
  BOOL v41; // edx
  int v42; // eax
  BOOL v43; // ecx
  int v44; // ebx
  int v45; // ebx
  int v46; // ecx
  int v47; // eax
  __m128i *v48; // eax
  __m128i v49; // [esp-2Ch] [ebp-4B0h]
  void *v50; // [esp-1Ch] [ebp-4A0h]
  WCHAR *Src; // [esp+4h] [ebp-480h]
  WCHAR *v53; // [esp+8h] [ebp-47Ch]
  _DWORD *v54; // [esp+Ch] [ebp-478h]
  int v55; // [esp+14h] [ebp-470h] BYREF
  int v56; // [esp+18h] [ebp-46Ch] BYREF
  int v57; // [esp+1Ch] [ebp-468h]
  int v58; // [esp+20h] [ebp-464h]
  int v59; // [esp+24h] [ebp-460h]
  int v60; // [esp+28h] [ebp-45Ch]
  WCHAR *v61; // [esp+2Ch] [ebp-458h] BYREF
  int *v62; // [esp+30h] [ebp-454h]
  int v63; // [esp+34h] [ebp-450h]
  LPCSTR lpSrcStr; // [esp+38h] [ebp-44Ch]
  int v65; // [esp+3Ch] [ebp-448h]
  WORD CharType[2]; // [esp+40h] [ebp-444h] BYREF
  int v67; // [esp+44h] [ebp-440h]
  int v68[2]; // [esp+48h] [ebp-43Ch] BYREF
  int v69[2]; // [esp+50h] [ebp-434h] BYREF
  int *v70; // [esp+58h] [ebp-42Ch]
  __m128i *v71; // [esp+5Ch] [ebp-428h]
  __m128i v72; // [esp+60h] [ebp-424h] BYREF
  __m128i v73; // [esp+70h] [ebp-414h] BYREF
  WCHAR SrcStr[256]; // [esp+80h] [ebp-404h] BYREF
  wchar_t Filename[256]; // [esp+280h] [ebp-204h] BYREF

  v4 = a2;
  v70 = a3;
  v5 = 0;
  v6 = *(_DWORD *)(a2 + 524);
  v71 = a4;
  v63 = 0;
  v58 = 0;
  v7 = *(_DWORD *)(v6 + 52) == 1;
  v8 = *(wchar_t **)(v6 + 8);
  lpSrcStr = 0;
  *(_DWORD *)CharType = 0;
  v55 = v7;
  v9 = 0;
  Src = (WCHAR *)v6;
  v57 = 1;
  v68[0] = 0;
  v56 = 0;
  v60 = 0;
  v59 = 0;
  v65 = 0;
  v68[1] = 0;
  v69[1] = 0;
  v72 = 0;
  v73 = 0;
  if ( !v7 && *(_WORD *)(v6 + 72) )
  {
    if ( *(_DWORD *)(v6 + 52) == 2 )
    {
      lpSrcStr = (LPCSTR)92;
      *(_DWORD *)CharType = 34;
    }
    else
    {
      lpSrcStr = (LPCSTR)*(unsigned __int16 *)(v6 + 72);
      *(_DWORD *)CharType = 0;
    }
  }
  if ( *(_DWORD *)(v6 + 52) != 3 )
  {
    if ( *(_DWORD *)(a2 + 8772) )
    {
      v11 = (_DWORD *)v6;
LABEL_24:
      v12 = (_DWORD *)v11[2];
      v54 = v12;
      if ( !v12 )
        return -5405;
      v13 = v12[4];
      if ( v13 > 1 )
        v56 = v13 - 1;
      while ( 1 )
      {
        v14 = v70;
        v62 = v70;
        if ( v70 )
        {
          v15 = v12[1];
          while ( v14[1] != v15 )
          {
            v14 = (int *)*v14;
            v62 = v14;
            if ( !v14 )
              goto LABEL_32;
          }
          v16 = v14[2];
          v17 = SrcStr;
          v18 = SrcStr;
          v53 = SrcStr;
          switch ( v16 )
          {
            case 1:
              rgpfnToWz[v16 - 1]((int)Src, (int)v54, SrcStr, 0xFFu, (int)(v14 + 6), 1);
              goto LABEL_37;
            case 2:
            case 3:
            case 4:
              rgpfnToWz[v16 - 1]((int)Src, (int)v54, SrcStr, 0xFFu, (int)(v14 + 6), 4);
              goto LABEL_37;
            case 5:
            case 7:
            case 8:
              rgpfnToWz[v16 - 1]((int)Src, (int)v54, SrcStr, 0xFFu, (int)(v14 + 6), 8);
              goto LABEL_37;
            case 6:
              *(float *)v69 = *((double *)v14 + 3);
              ((void (__stdcall *)(int, int, int, size_t, int, int))*(&off_1003E8F4 + v14[2]))(
                (int)Src,
                (int)v54,
                (int)SrcStr,
                0xFFu,
                (int)v69,
                4);
              goto LABEL_37;
            case 9:
              v23 = 6 * (v14[6] + 1);
              v24 = MemAllocate(v23);
              v63 = v24;
              if ( !v24 )
              {
                v5 = -1011;
                goto LABEL_156;
              }
              v17 = (WCHAR *)v24;
              v53 = (WCHAR *)v24;
              BytesToHexString(v24, v23 >> 1, v62[7], v62[6]);
              v14 = v62;
LABEL_37:
              v18 = Src;
LABEL_38:
              v19 = a2;
LABEL_39:
              v20 = (WCHAR *)a1;
LABEL_40:
              if ( *((_DWORD *)v20 + 13) == 3 )
              {
                v36 = v18;
                v60 = 0;
                if ( !IsUnicodeOS() && *Src )
                {
                  v68[0] = wcslen(Src);
                  v37 = (CHAR *)MemAllocate(8 * v68[0]);
                  v58 = (int)v37;
                  if ( !v37 )
                  {
                    v5 = -1011;
                    goto LABEL_154;
                  }
                  TextConvertFromUnicode(*(_DWORD *)(a1 + 36), Src, v68, v37, (int)v69);
                  lpSrcStr = (LPCSTR)v58;
                }
                for ( i = lpSrcStr; ; ++i )
                {
                  while ( IsUnicodeOS() )
                  {
                    if ( !*v36 )
                      goto LABEL_110;
                    GetStringTypeW(1u, v36, 1, CharType);
                    if ( (CharType[0] & 0x100) != 0 )
                      goto LABEL_110;
                    ++v36;
                  }
                  if ( !*i )
                    break;
                  GetStringTypeA(*(_DWORD *)(a1 + 36), 1u, i, 1, CharType);
                  if ( (CharType[0] & 0x100) != 0 )
                    break;
                }
LABEL_110:
                v39 = v61;
                lpSrcStr = i;
                v40 = v60;
                if ( v58 )
                {
                  MemFree(v58);
                  v58 = v40;
                }
                if ( v36 && *v36 )
                  v40 = IsCharBiDi(*v36);
                v11 = (_DWORD *)a1;
                v41 = v40 != 0;
                v42 = *(_DWORD *)(a1 + 824);
                if ( (v42 & 4) != 0 )
                  v43 = v40 != 0;
                else
                  v43 = (v42 & 2) != 0;
                v44 = v59;
                if ( v41 )
                  v44 = 64;
                if ( v43 )
                  v45 = v44 | 8;
                else
                  v45 = v44 | 4;
                v59 = v45;
                if ( *((_DWORD *)v53 + 7) )
                  v59 = v45 | 0x20;
                v46 = *((_DWORD *)v39 + 2);
                if ( v46 != 10 && v46 != 12 )
                  v9 = wcslen(Src);
                if ( !v9 || v46 == 11 )
                {
                  Field = HTMLWriteCell(v54[133], *(_DWORD *)(a1 + 36), 0, (wchar_t *)&dword_100010B4, 1);
                }
                else if ( v46 == 10 || v46 == 12 )
                {
                  Field = HTMLWriteCell(v54[133], *(_DWORD *)(a1 + 36), v59, Src, 1);
                }
                else
                {
                  Field = HTMLWriteCell(v54[133], *(_DWORD *)(a1 + 36), 8, Src, 1);
                }
                goto LABEL_135;
              }
              if ( v19 )
              {
                v27 = 0;
                v57 = 0;
                goto LABEL_80;
              }
              v22 = 0;
              if ( v20[36] )
              {
                v21 = v14[2];
                if ( v21 == 10
                  || v21 == 12
                  || v21 == 8
                  && (wcsrchr((const wchar_t *)(a1 + 210), *(_WORD *)(a1 + 56))
                   || wcsrchr((const wchar_t *)(a1 + 340), *(_WORD *)(a1 + 56))
                   || wcsrchr((const wchar_t *)(a1 + 80), *(_WORD *)(a1 + 56))) )
                {
                  v22 = 1;
                }
              }
              v18 = Src;
              v57 = v22;
              if ( Src == v17 )
              {
                v27 = v57;
LABEL_80:
                v28 = v14[2];
                if ( v28 != 10 )
                {
                  v29 = v18;
                  v30 = v18 + 1;
                  while ( *v29++ )
                    ;
                  v32 = v53;
                  v9 = v29 - v30;
                  if ( v28 == 9 )
                  {
                    v33 = *((_DWORD *)v53 + 3);
                    if ( v33 != -1 )
                    {
                      v18 = Src;
                      v32 = v53;
                      if ( v33 < v9 / 3 )
                        v9 = 3 * v33;
                      goto LABEL_92;
                    }
LABEL_95:
                    v18 = Src;
LABEL_92:
                    if ( v9 || v14[5] == 1 )
                      Field = TextPutNextField((int)v54, v18, *((_DWORD *)v32 + 3), v9, (int)&v55, v56, v27);
                    else
                      Field = TextPutNextField((int)v54, 0, *((_DWORD *)v32 + 3), 0, (int)&v55, v56, v27);
                    v11 = (_DWORD *)a1;
                    v56 = 0;
LABEL_135:
                    v5 = Field;
                    goto LABEL_136;
                  }
                  if ( !a2 )
                    goto LABEL_95;
                  v34 = *((_DWORD *)v53 + 3);
                  v18 = Src;
                  if ( v34 != -1 && v34 < v9 )
                    v9 = *((_DWORD *)v53 + 3);
                }
                v32 = v53;
                goto LABEL_92;
              }
              if ( v67 || v14[5] == 1 )
              {
                v5 = TextPutNextField((int)v54, v17, *((_DWORD *)v53 + 3), v67, (int)&v55, v56, v22);
                v56 = 0;
              }
              MemFree(v17);
              v11 = (_DWORD *)a1;
LABEL_136:
              if ( v5 )
                goto LABEL_154;
              break;
            case 10:
            case 12:
              if ( v16 == 10 )
              {
                v25 = v54[3];
                v17 = (WCHAR *)(v14 + 7);
                v9 = v14[6];
                v18 = (WCHAR *)(v14 + 7);
                v61 = (WCHAR *)(v14 + 7);
                v53 = (WCHAR *)(v14 + 7);
                if ( v25 < v9 )
                  v9 = v25;
              }
              else
              {
                v17 = (WCHAR *)v14[7];
                v18 = v17;
                v9 = v54[3];
                v61 = v17;
                v53 = v17;
                if ( v9 == -1 || v9 >= v14[6] )
                  v9 = v14[6];
              }
              v26 = 0;
              if ( v9 > 0 )
              {
                do
                {
                  if ( v17[v26] == 26 )
                    v17[v26] = 45;
                  ++v26;
                }
                while ( v26 < v9 );
                v14 = v62;
              }
              v19 = v55;
              if ( v55 )
                goto LABEL_39;
              v20 = Src;
              if ( !Src[36] )
                goto LABEL_40;
              v5 = QuoteString_0(v17, v9, (__int16)lpSrcStr, *(_DWORD *)CharType, &v61, v68);
              if ( v5 )
                goto LABEL_154;
              v17 = v61;
              goto LABEL_37;
            case 16:
              rgpfnToWz[v16 - 1]((int)Src, (int)v54, SrcStr, 0xFFu, (int)(v14 + 6), 16);
              goto LABEL_37;
            default:
              goto LABEL_38;
          }
        }
        else
        {
LABEL_32:
          if ( v11[13] == 3 )
          {
            v5 = HTMLWriteCell(*(_DWORD *)(v4 + 532), v11[9], 0, (wchar_t *)&dword_100010B4, 1);
          }
          else
          {
            v5 = TextPutNextField(v4, 0, v12[3], 0, (int)&v56, v57, v58);
            v57 = 0;
            if ( v5 )
              goto LABEL_154;
          }
        }
        if ( *v54 )
        {
          v47 = *(_DWORD *)(*v54 + 16) - v54[4] - v54[3];
          if ( v47 > 0 )
            v56 += v47;
        }
        v12 = (_DWORD *)*v54;
        v54 = (_DWORD *)*v54;
        if ( v63 )
        {
          MemFree(v63);
          v12 = v54;
          v63 = 0;
        }
        if ( !v12 )
          break;
        v4 = a2;
      }
      if ( v11[13] == 3 )
      {
        v5 = HTMLWriteRowEnd(*(_DWORD *)(a2 + 532), v11[9], 1);
        if ( !v5 )
          goto LABEL_153;
      }
      else
      {
        v5 = TextPutNextField(a2, 0, 0, 0, (int)&v56, 2, 0);
        if ( !v5 )
        {
          v48 = v71;
          *v71 = _mm_loadu_si128((const __m128i *)(a2 + 8856));
          v48[1] = _mm_loadu_si128((const __m128i *)(a2 + 8872));
          if ( !*(_DWORD *)(a2 + 8772) )
          {
            v49 = _mm_loadu_si128(&v72);
            v5 = TextGotoBookmark(
                   a2,
                   v49.m128i_i32[0],
                   v49.m128i_i32[1],
                   v49.m128i_i32[2],
                   v49.m128i_i32[3],
                   *(_OWORD *)&_mm_loadu_si128(&v73));
          }
LABEL_153:
          ++*(_DWORD *)(a2 + 560);
        }
      }
LABEL_154:
      if ( v63 )
        MemFree(v63);
LABEL_156:
      if ( v59 )
        MemFree(v59);
      return v5;
    }
    v72 = _mm_loadu_si128((const __m128i *)(a2 + 8856));
    v50 = *(void **)(a2 + 528);
    v73 = _mm_loadu_si128((const __m128i *)(a2 + 8872));
    if ( SetFilePointer(v50, 0, 0, 2u) == -1 )
      return -1022;
    goto LABEL_22;
  }
  if ( *(_DWORD *)(a2 + 560) )
  {
    v11 = (_DWORD *)v6;
    result = HTMLWriteRowBegin(*(_DWORD *)(a2 + 532), *(_DWORD *)(v6 + 36), 1);
    v5 = result;
    if ( result )
      return result;
    goto LABEL_23;
  }
  BFSetFilePosition(*(_DWORD *)(a2 + 532), 0, 0);
  BFTruncateFile(*(_DWORD *)(a2 + 532));
  SplitPath((wchar_t *)a2, 0, 0, 0, 0, Filename, 0xFFu, 0, 0);
  result = HTMLWriteFileBegin(*(_DWORD *)(a2 + 532), *(_DWORD *)(v6 + 36), Filename, 1, *(_DWORD *)(v6 + 824));
  if ( result )
    return result;
  result = HTMLWriteRowBegin(*(_DWORD *)(a2 + 532), *(_DWORD *)(v6 + 36), 1);
  v5 = result;
  if ( result )
    return result;
  if ( !*(_DWORD *)(v6 + 28) )
  {
LABEL_22:
    v11 = (_DWORD *)v6;
LABEL_23:
    v4 = a2;
    goto LABEL_24;
  }
  if ( !v8 )
  {
LABEL_14:
    v11 = (_DWORD *)v6;
    v5 = HTMLWriteRowEnd(*(_DWORD *)(a2 + 532), *(_DWORD *)(v6 + 36), 1);
    if ( v5 )
      return v5;
    goto LABEL_23;
  }
  while ( 1 )
  {
    result = HTMLWriteCell(*(_DWORD *)(a2 + 532), *(_DWORD *)(v6 + 36), 2, v8 + 18, 1);
    if ( result )
      return result;
    v8 = *(wchar_t **)v8;
    if ( !v8 )
      goto LABEL_14;
  }
}

```

## disassembly

```asm
0x1001e1e0  sub     esp, 480h
0x1001e1e6  mov     eax, ___security_cookie
0x1001e1eb  xor     eax, esp
0x1001e1ed  mov     [esp+480h+var_4], eax
0x1001e1f4  mov     edx, [esp+480h+arg_0]
0x1001e1fb  xorps   xmm0, xmm0
0x1001e1fe  mov     eax, [esp+480h+arg_4]
0x1001e205  push    ebx
0x1001e206  push    ebp
0x1001e207  push    esi
0x1001e208  mov     [esp+48Ch+var_42C], eax
0x1001e20c  xor     ebx, ebx
0x1001e20e  mov     eax, [esp+48Ch+arg_8]
0x1001e215  push    edi
0x1001e216  mov     edi, [edx+20Ch]
0x1001e21c  mov     [esp+490h+var_428], eax
0x1001e220  xor     eax, eax
0x1001e222  mov     [esp+490h+var_450], eax
0x1001e226  mov     [esp+490h+var_464], eax
0x1001e22a  cmp     dword ptr [edi+34h], 1
0x1001e22e  mov     esi, [edi+8]
0x1001e231  mov     [esp+490h+lpSrcStr], eax
0x1001e235  mov     dword ptr [esp+490h+CharType], eax
0x1001e239  setz    al
0x1001e23c  mov     [esp+490h+var_470], eax
0x1001e240  xor     ecx, ecx
0x1001e242  xor     eax, eax
0x1001e244  mov     [esp+490h+FullPath], edx
0x1001e248  xor     ebp, ebp
0x1001e24a  mov     [esp+490h+Src], edi
0x1001e24e  mov     [esp+490h+var_468], 1
0x1001e256  mov     [esp+490h+var_43C], ebx
0x1001e25a  mov     [esp+490h+var_46C], ebx
0x1001e25e  mov     [esp+490h+var_45C], eax
0x1001e262  mov     [esp+490h+var_460], ecx
0x1001e266  mov     [esp+490h+var_448], eax
0x1001e26a  mov     [esp+490h+var_438], eax
0x1001e26e  mov     [esp+490h+var_430], eax
0x1001e272  movdqu  [esp+490h+var_424], xmm0
0x1001e278  movdqu  [esp+490h+var_414], xmm0
0x1001e27e  cmp     [esp+490h+var_470], eax
0x1001e282  jnz     short loc_1001E2AD
0x1001e284  movzx   eax, word ptr [edi+48h]
0x1001e288  test    ax, ax
0x1001e28b  jz      short loc_1001E2AD
0x1001e28d  cmp     dword ptr [edi+34h], 2
0x1001e291  jnz     short loc_1001E2A5
0x1001e293  mov     [esp+490h+lpSrcStr], 5Ch ; '\'
0x1001e29b  mov     dword ptr [esp+490h+CharType], 22h ; '"'
0x1001e2a3  jmp     short loc_1001E2AD
0x1001e2a5  mov     [esp+490h+lpSrcStr], eax
0x1001e2a9  mov     dword ptr [esp+490h+CharType], ecx
0x1001e2ad  cmp     dword ptr [edi+34h], 3
0x1001e2b1  jnz     loc_1001E3AF
0x1001e2b7  cmp     [edx+230h], ecx
0x1001e2bd  jnz     loc_1001E392
0x1001e2c3  push    0; lDistanceToMove
0x1001e2c5  push    0; int
0x1001e2c7  push    dword ptr [edx+214h]; int
0x1001e2cd  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x1001e2d2  mov     ebx, [esp+490h+FullPath]
0x1001e2d6  push    dword ptr [ebx+214h]
0x1001e2dc  call    _BFTruncateFile@4; BFTruncateFile(x)
0x1001e2e1  push    0; ExtCount
0x1001e2e3  push    0; Ext
0x1001e2e5  push    0FFh; FilenameCount
0x1001e2ea  lea     eax, [esp+49Ch+Filename]
0x1001e2f1  push    eax; Filename
0x1001e2f2  push    0; DirCount
0x1001e2f4  push    0; Dir
0x1001e2f6  push    0; DriveCount
0x1001e2f8  push    0; lDistanceToMove
0x1001e2fa  push    ebx; FullPath
0x1001e2fb  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1001e300  push    dword ptr [edi+338h]
0x1001e306  lea     eax, [esp+494h+Filename]
0x1001e30d  push    1
0x1001e30f  push    eax
0x1001e310  push    dword ptr [edi+24h]
0x1001e313  push    dword ptr [ebx+214h]
0x1001e319  call    _HTMLWriteFileBegin@20; HTMLWriteFileBegin(x,x,x,x,x)
0x1001e31e  test    eax, eax
0x1001e320  jnz     loc_1001EA9B
0x1001e326  push    1
0x1001e328  push    dword ptr [edi+24h]
0x1001e32b  push    dword ptr [ebx+214h]
0x1001e331  call    _HTMLWriteRowBegin@12; HTMLWriteRowBegin(x,x,x)
0x1001e336  mov     ebx, eax
0x1001e338  test    ebx, ebx
0x1001e33a  jnz     loc_1001EA9B
0x1001e340  cmp     [edi+1Ch], ebp
0x1001e343  jz      loc_1001E3FB
0x1001e349  mov     ebx, [esp+490h+FullPath]
0x1001e34d  test    esi, esi
0x1001e34f  jz      short loc_1001E375
0x1001e351  push    1; int
0x1001e353  lea     eax, [esi+24h]
0x1001e356  push    eax; Str
0x1001e357  push    2; int
0x1001e359  push    dword ptr [edi+24h]; int
0x1001e35c  push    dword ptr [ebx+214h]; int
0x1001e362  call    _HTMLWriteCell@20; HTMLWriteCell(x,x,x,x,x)
0x1001e367  test    eax, eax
0x1001e369  jnz     loc_1001EA9B
0x1001e36f  mov     esi, [esi]
0x1001e371  test    esi, esi
0x1001e373  jnz     short loc_1001E351
0x1001e375  mov     esi, edi
0x1001e377  push    1
0x1001e379  push    dword ptr [esi+24h]
0x1001e37c  push    dword ptr [ebx+214h]
0x1001e382  call    _HTMLWriteRowEnd@12; HTMLWriteRowEnd(x,x,x)
0x1001e387  mov     ebx, eax
0x1001e389  test    ebx, ebx
0x1001e38b  jz      short loc_1001E3FD
0x1001e38d  jmp     loc_1001EA99
0x1001e392  mov     esi, edi
0x1001e394  push    1
0x1001e396  push    dword ptr [esi+24h]
0x1001e399  push    dword ptr [edx+214h]
0x1001e39f  call    _HTMLWriteRowBegin@12; HTMLWriteRowBegin(x,x,x)
0x1001e3a4  mov     ebx, eax
0x1001e3a6  test    ebx, ebx
0x1001e3a8  jz      short loc_1001E3FD
0x1001e3aa  jmp     loc_1001EA9B
0x1001e3af  cmp     [edx+2244h], ecx
0x1001e3b5  jnz     short loc_1001E3F7
0x1001e3b7  movdqu  xmm0, xmmword ptr [edx+2298h]
0x1001e3bf  push    2; dwMoveMethod
0x1001e3c1  push    0; lpDistanceToMoveHigh
0x1001e3c3  movdqu  [esp+498h+var_424], xmm0
0x1001e3c9  push    0; lDistanceToMove
0x1001e3cb  movdqu  xmm0, xmmword ptr [edx+22A8h]
0x1001e3d3  push    dword ptr [edx+210h]; hFile
0x1001e3d9  movdqu  [esp+4A0h+var_414], xmm0
0x1001e3e2  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1001e3e8  cmp     eax, 0FFFFFFFFh
0x1001e3eb  jnz     short loc_1001E3FB
0x1001e3ed  mov     eax, 0FFFFFC02h
0x1001e3f2  jmp     loc_1001EA9B
0x1001e3f7  mov     esi, edi
0x1001e3f9  jmp     short loc_1001E401
0x1001e3fb  mov     esi, edi
0x1001e3fd  mov     edx, [esp+490h+FullPath]
0x1001e401  mov     ecx, [esi+8]
0x1001e404  mov     [esp+490h+var_478], ecx
0x1001e408  test    ecx, ecx
0x1001e40a  jnz     short loc_1001E416
0x1001e40c  mov     eax, 0FFFFEAE3h
0x1001e411  jmp     loc_1001EA9B
0x1001e416  mov     eax, [ecx+10h]
0x1001e419  cmp     eax, 1
0x1001e41c  jbe     short loc_1001E423
0x1001e41e  dec     eax
0x1001e41f  mov     [esp+490h+var_46C], eax
0x1001e423  mov     eax, [esp+490h+var_42C]
0x1001e427  mov     edi, eax
0x1001e429  mov     [esp+490h+var_454], eax
0x1001e42d  test    eax, eax
0x1001e42f  jz      short loc_1001E443
0x1001e431  mov     eax, [ecx+4]
0x1001e434  cmp     [edi+4], eax
0x1001e437  jz      short loc_1001E47E
0x1001e439  mov     edi, [edi]
0x1001e43b  mov     [esp+490h+var_454], edi
0x1001e43f  test    edi, edi
0x1001e441  jnz     short loc_1001E434
0x1001e443  cmp     dword ptr [esi+34h], 3
0x1001e447  jz      loc_1001E97B
0x1001e44d  push    [esp+490h+var_464]; int
0x1001e451  lea     eax, [esp+494h+var_46C]
0x1001e455  push    [esp+494h+var_468]; int
0x1001e459  push    eax; int
0x1001e45a  push    0; int
0x1001e45c  push    dword ptr [ecx+0Ch]; int
0x1001e45f  push    0; Src
0x1001e461  push    edx; int
0x1001e462  call    _TextPutNextField@28; TextPutNextField(x,x,x,x,x,x,x)
0x1001e467  mov     ebx, eax
0x1001e469  mov     [esp+490h+var_468], 0
0x1001e471  test    ebx, ebx
0x1001e473  jnz     loc_1001EA7D
0x1001e479  jmp     loc_1001E994
0x1001e47e  mov     ecx, [edi+8]
0x1001e481  lea     esi, [esp+490h+SrcStr]
0x1001e488  mov     edx, esi
0x1001e48a  mov     [esp+490h+var_47C], edx
0x1001e48e  lea     eax, [ecx-1]; switch 16 cases
0x1001e491  cmp     eax, 0Fh
0x1001e494  ja      short def_1001E49D; jumptable 1001E49D default case, cases 11,13-15
0x1001e496  movzx   eax, ds:byte_1001EAD8[eax]
0x1001e49d  jmp     ds:jpt_1001E49D[eax*4]; switch jump
0x1001e4a4  push    1; jumptable 1001E49D case 1
0x1001e4a6  lea     eax, [edi+18h]
0x1001e4a9  push    eax; int
0x1001e4aa  lea     eax, [esp+498h+SrcStr]
0x1001e4b1  push    0FFh; pdecOut
0x1001e4b6  push    eax; strIn
0x1001e4b7  mov     eax, (_rgpfnToWz-4)[ecx*4]
0x1001e4be  push    [esp+4A0h+var_478]; int
0x1001e4c2  push    [esp+4A4h+Src]; int
0x1001e4c6  call    eax ; FWzToDecimal(x,x,x,x,x); FCurrencyToWz(x,x,x,x,x,x)
0x1001e4c8  mov     edx, [esp+494h+Src]
0x1001e4cc  mov     ecx, [esp+494h+FullPath]; jumptable 1001E49D default case, cases 11,13-15
0x1001e4d0  mov     eax, [esp+494h+var_484]
0x1001e4d4  cmp     dword ptr [eax+34h], 3
0x1001e4d8  jz      loc_1001E7A7
0x1001e4de  test    ecx, ecx
0x1001e4e0  jnz     loc_1001E6E1
0x1001e4e6  cmp     [eax+48h], cx
0x1001e4ea  jz      loc_1001E68F
0x1001e4f0  mov     eax, [edi+8]
0x1001e4f3  cmp     eax, 0Ah
0x1001e4f6  jz      short loc_1001E55E
0x1001e4f8  cmp     eax, 0Ch
0x1001e4fb  jz      short loc_1001E55E
0x1001e4fd  cmp     eax, 8
0x1001e500  jnz     loc_1001E68F
0x1001e506  mov     eax, [esp+494h+var_484]
0x1001e50a  movzx   eax, word ptr [eax+38h]
0x1001e50e  push    eax; Ch
0x1001e50f  mov     eax, [esp+498h+var_484]
0x1001e513  add     eax, 0D2h
0x1001e518  push    eax; Str
0x1001e519  call    _wcsrchr
0x1001e51e  add     esp, 8
0x1001e521  test    eax, eax
0x1001e523  jnz     short loc_1001E55E
0x1001e525  mov     ecx, [esp+494h+var_484]
0x1001e529  movzx   eax, word ptr [ecx+38h]
0x1001e52d  push    eax; Ch
0x1001e52e  lea     eax, [ecx+154h]
0x1001e534  push    eax; Str
0x1001e535  call    _wcsrchr
0x1001e53a  add     esp, 8
0x1001e53d  test    eax, eax
0x1001e53f  jnz     short loc_1001E55E
0x1001e541  mov     ecx, [esp+494h+var_484]
0x1001e545  movzx   eax, word ptr [ecx+38h]
0x1001e549  push    eax; Ch
0x1001e54a  lea     eax, [ecx+50h]
0x1001e54d  push    eax; Str
0x1001e54e  call    _wcsrchr
0x1001e553  add     esp, 8
0x1001e556  test    eax, eax
0x1001e558  jz      loc_1001E68F
0x1001e55e  mov     eax, 1
0x1001e563  jmp     loc_1001E691
0x1001e568  push    4; jumptable 1001E49D cases 2-4
0x1001e56a  jmp     loc_1001E4A6
0x1001e56f  push    8; jumptable 1001E49D cases 5,7,8
0x1001e571  jmp     loc_1001E4A6
0x1001e576  movsd   xmm0, qword ptr [edi+18h]; jumptable 1001E49D case 6
0x1001e57b  lea     ecx, [esp+490h+var_434]
0x1001e57f  cvtpd2ps xmm0, xmm0
0x1001e583  push    4
0x1001e585  push    ecx
0x1001e586  push    0FFh
0x1001e58b  lea     ecx, [esp+49Ch+SrcStr]
0x1001e592  push    ecx
0x1001e593  movss   [esp+4A0h+var_434], xmm0
0x1001e599  mov     eax, [edi+8]
0x1001e59c  mov     eax, off_1003E8F4[eax*4]
0x1001e5a3  jmp     loc_1001E4BE
0x1001e5a8  push    10h; jumptable 1001E49D case 16
0x1001e5aa  jmp     loc_1001E4A6
0x1001e5af  mov     eax, [edi+18h]; jumptable 1001E49D case 9
0x1001e5b2  inc     eax
0x1001e5b3  lea     edi, [eax+eax*2]
0x1001e5b6  add     edi, edi
0x1001e5b8  push    edi; Size
0x1001e5b9  call    _MemAllocate@4; MemAllocate(x)
0x1001e5be  mov     [esp+490h+var_450], eax
0x1001e5c2  test    eax, eax
0x1001e5c4  jz      loc_1001E9DC
0x1001e5ca  mov     ecx, [esp+490h+var_454]
0x1001e5ce  mov     esi, eax
0x1001e5d0  shr     edi, 1
0x1001e5d2  mov     [esp+490h+var_47C], eax
0x1001e5d6  push    dword ptr [ecx+18h]
0x1001e5d9  push    dword ptr [ecx+1Ch]
0x1001e5dc  push    edi
0x1001e5dd  push    eax
0x1001e5de  call    BytesToHexString
0x1001e5e3  mov     edi, [esp+490h+var_454]
0x1001e5e7  jmp     loc_1001E4C8
0x1001e5ec  mov     eax, [esp+490h+var_478]; jumptable 1001E49D cases 10,12
0x1001e5f0  cmp     ecx, 0Ah
0x1001e5f3  jnz     short loc_1001E60F
0x1001e5f5  mov     eax, [eax+0Ch]
0x1001e5f8  lea     esi, [edi+1Ch]
0x1001e5fb  mov     ebp, [edi+18h]
0x1001e5fe  mov     edx, esi
0x1001e600  cmp     eax, ebp
0x1001e602  mov     [esp+490h+var_458], esi
0x1001e606  mov     [esp+490h+var_47C], esi
0x1001e60a  cmovl   ebp, eax
0x1001e60d  jmp     short loc_1001E62C
0x1001e60f  mov     esi, [edi+1Ch]
0x1001e612  mov     edx, esi
  ... truncated ...
```
