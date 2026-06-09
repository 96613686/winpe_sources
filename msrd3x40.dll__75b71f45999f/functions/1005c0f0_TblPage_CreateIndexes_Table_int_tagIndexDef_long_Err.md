# TblPage::CreateIndexes(Table *,int,tagIndexDef *,long,Err &)

- ea: `0x1005c0f0`
- end: `0x1005c649`
- name: `?CreateIndexes@TblPage@@AAEJPAVTable@@HPAUtagIndexDef@@JAAVErr@@@Z`
- size: `1369`
- prototype: `int __thiscall(TblPage *this, struct Table *, int, struct tagIndexDef *, int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1005ab70`

## callees

- `0x10012dd0`
- `0x10025ee0`
- `0x100319f0`
- `0x1005c0f0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1005c339`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1005c339`

## pseudocode

```c
int __thiscall TblPage::CreateIndexes(
        TblPage *this,
        struct Table *a2,
        int a3,
        struct tagIndexDef *a4,
        int a5,
        void **a6)
{
  int v6; // eax
  struct Table *v7; // ecx
  struct tagIndexDef *v8; // edx
  void **v9; // edi
  int v10; // ebx
  int result; // eax
  int v12; // esi
  _DWORD *v13; // edx
  int v14; // eax
  int v15; // edx
  void **v16; // ebx
  int v17; // eax
  _DWORD *v18; // edx
  unsigned int v19; // eax
  int v20; // eax
  size_t v21; // ecx
  unsigned int v22; // eax
  int i; // edi
  void **v24; // ebx
  int v25; // [esp-4h] [ebp-C8h]
  Index *Block; // [esp+10h] [ebp-B4h]
  unsigned int v28; // [esp+18h] [ebp-ACh]
  const CHAR *v29; // [esp+20h] [ebp-A4h]
  char *v30; // [esp+28h] [ebp-9Ch]
  _DWORD *v31; // [esp+28h] [ebp-9Ch]
  int v32; // [esp+28h] [ebp-9Ch]
  WCHAR WideCharStr[66]; // [esp+30h] [ebp-94h] BYREF
  int v34; // [esp+C0h] [ebp-4h]

  v6 = *((_DWORD *)this + 1);
  v7 = a2;
  v8 = a4;
  v9 = a6;
  v10 = *(_DWORD *)(v6 + 19);
  if ( v10 > 32 )
  {
    if ( (int)*a6 < 8 )
    {
      if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
      {
        if ( a6[3] )
          operator delete[](a6[3]);
        if ( a6[4] )
          operator delete[](a6[4]);
      }
      *a6 = (void *)8;
      result = 0;
      a6[1] = (void *)-1206;
      a6[2] = 0;
      a6[3] = 0;
      a6[4] = 0;
      return result;
    }
    return 0;
  }
  v12 = 0;
  if ( v10 > 0 )
  {
    while ( 1 )
    {
      v13 = (_DWORD *)((char *)v8 + 20 * v12);
      v14 = v13[1];
      v9 = a6;
      v7 = a2;
      if ( v14 >= *(_DWORD *)(*((_DWORD *)this + 1) + 23) || v14 < 0 || *v13 >= 0x100u )
        break;
      v8 = a4;
      if ( ++v12 >= v10 )
        goto LABEL_14;
    }
    if ( (int)*a6 >= 8 )
      goto LABEL_70;
    if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
    {
      if ( a6[3] )
        operator delete[](a6[3]);
      if ( a6[4] )
        operator delete[](a6[4]);
    }
    a6[1] = (void *)-1206;
    goto LABEL_68;
  }
LABEL_14:
  v12 = 0;
  v15 = (int)v8 + 20 * v10;
  v29 = (const CHAR *)v15;
  if ( v10 > 0 )
  {
    while ( 1 )
    {
      v30 = (char *)a4 + 20 * v12;
      Block = (Index *)operator new(0xC4u);
      v34 = 0;
      v16 = (void **)Index::Index(Block, (struct Err *)v9);
      v34 = -1;
      v17 = (int)*v9;
      if ( !v16 )
        break;
      if ( (v17 & 8) != 0 )
      {
        if ( v16[6] )
          operator delete[](v16[6]);
        goto LABEL_60;
      }
      v16[9] = *(void **)v30;
      *((_BYTE *)v16 + 40) ^= (*((_BYTE *)v16 + 40) ^ v30[19]) & 1;
      v16[15] = (void *)(((unsigned __int8)v30[19] >> 1) & 1);
      *((_BYTE *)v16 + 41) = v30[8];
      v16[11] = *(void **)(v30 + 9);
      v16[12] = *(void **)(v30 + 13);
      v16[13] = (void *)(unsigned __int8)v30[17];
      v16[14] = (void *)(unsigned __int8)v30[18];
      v18 = (_DWORD *)*((_DWORD *)a2 + *((_DWORD *)v30 + 1) + 413);
      v16[2] = v18;
      v31 = v18;
      v19 = v18[2];
      if ( v19 >= v18[1] )
      {
        Collection::Grow((Collection *)v18, v19 + 1, (struct Err *)v9);
        if ( (*(_BYTE *)v9 & 8) != 0 )
          goto LABEL_55;
        v18 = v31;
      }
      *(_DWORD *)(*v18 + 4 * v18[2]++) = v16;
      if ( (*(_BYTE *)v9 & 8) != 0 )
      {
LABEL_55:
        if ( v16[6] )
          operator delete[](v16[6]);
LABEL_60:
        operator delete(v16, 0xC4u);
        goto LABEL_69;
      }
      if ( v29 == (const CHAR *)-1 || !*v29 )
      {
        v21 = 0;
        WideCharStr[0] = 0;
        v32 = 0;
        v28 = 0;
      }
      else
      {
        v20 = MultiByteToWideChar(
                *(unsigned __int16 *)(*(_DWORD *)(*((_DWORD *)a2 + 9) + 60) + 100),
                0,
                v29 + 1,
                *(unsigned __int8 *)v29,
                WideCharStr,
                65);
        v9 = a6;
        if ( !v20 )
        {
          if ( (int)*a6 < 8 )
          {
            if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
            {
              if ( a6[3] )
                operator delete[](a6[3]);
              if ( a6[4] )
                operator delete[](a6[4]);
            }
            *a6 = (void *)8;
            a6[1] = (void *)-1002;
            a6[2] = 0;
            a6[3] = 0;
            a6[4] = 0;
          }
          if ( v16[6] )
            operator delete[](v16[6]);
          goto LABEL_60;
        }
        v21 = 2 * v20;
        v32 = 2 * v20;
        v28 = (unsigned int)(2 * v20) >> 1;
        if ( v28 > 0x40 )
        {
          if ( v16[6] )
            operator delete[](v16[6]);
LABEL_27:
          operator delete(v16, 0xC4u);
          Err::SetError(v9, -1206, v25);
          goto LABEL_69;
        }
      }
      memcpy(*v16, WideCharStr, v21);
      *((_WORD *)*v16 + v28) = 0;
      v16[1] = (void *)v32;
      v15 = (int)&v29[*(unsigned __int8 *)v29 + 1];
      v16[3] = 0;
      v22 = (unsigned int)v16[9];
      v29 = (const CHAR *)v15;
      v16[5] = 0;
      if ( v22 >= 0x20 || (v7 = a2, *((_DWORD *)a2 + v22 + 349)) )
      {
        if ( v16[6] )
          operator delete[](v16[6]);
        goto LABEL_27;
      }
      *((_DWORD *)a2 + v22 + 349) = v16;
      *((_DWORD *)a2 + v12++ + 381) = v16[9];
      if ( v12 >= *(_DWORD *)(*((_DWORD *)this + 1) + 19) )
      {
        if ( v12 >= 32 )
          return v15 - (_DWORD)a4;
        goto LABEL_40;
      }
    }
    if ( v17 >= 8 )
      goto LABEL_69;
    if ( (v17 & 0xFFFFFFFE) != 0 )
    {
      if ( v9[3] )
        operator delete[](v9[3]);
      if ( v9[4] )
        operator delete[](v9[4]);
    }
    v9[1] = (void *)-1011;
LABEL_68:
    v9[4] = 0;
    v9[3] = 0;
    v9[2] = 0;
    *v9 = (void *)8;
LABEL_69:
    v7 = a2;
LABEL_70:
    for ( i = 0; i < v12; ++i )
    {
      v24 = (void **)*((_DWORD *)v7 + i + 349);
      if ( v24 )
      {
        if ( v24[6] )
          operator delete[](v24[6]);
        operator delete(v24, 0xC4u);
        v7 = a2;
      }
      *((_DWORD *)v7 + i + 349) = 0;
    }
    return 0;
  }
  do
LABEL_40:
    *((_DWORD *)v7 + v12++ + 381) = -1;
  while ( v12 < 32 );
  return v15 - (_DWORD)a4;
}

```

## disassembly

```asm
0x1005c0f0  mov     edi, edi
0x1005c0f2  push    ebp
0x1005c0f3  mov     ebp, esp
0x1005c0f5  push    0FFFFFFFFh
0x1005c0f7  push    offset ?CreateIndexes@TblPage@@AAEJPAVTable@@HPAUtagIndexDef@@JAAVErr@@@Z_SEH
0x1005c0fc  mov     eax, large fs:0
0x1005c102  push    eax
0x1005c103  sub     esp, 0A8h
0x1005c109  mov     eax, ___security_cookie
0x1005c10e  xor     eax, ebp
0x1005c110  mov     [ebp+var_10], eax
0x1005c113  push    ebx
0x1005c114  push    esi
0x1005c115  push    edi
0x1005c116  push    eax
0x1005c117  lea     eax, [ebp+var_C]
0x1005c11a  mov     large fs:0, eax
0x1005c120  mov     eax, ecx
0x1005c122  mov     [ebp+var_B0], eax
0x1005c128  mov     eax, [eax+4]
0x1005c12b  mov     ecx, [ebp+arg_0]
0x1005c12e  mov     edx, [ebp+arg_8]
0x1005c131  mov     edi, [ebp+arg_10]
0x1005c134  mov     ebx, [eax+13h]
0x1005c137  mov     [ebp+var_98], ecx
0x1005c13d  mov     [ebp+var_A0], edx
0x1005c143  mov     [ebp+var_A8], edi
0x1005c149  cmp     ebx, 20h ; ' '
0x1005c14c  jle     short loc_1005C1A9
0x1005c14e  mov     eax, [edi]
0x1005c150  cmp     eax, 8
0x1005c153  jge     loc_1005C642
0x1005c159  test    eax, 0FFFFFFFEh
0x1005c15e  jz      short loc_1005C180
0x1005c160  mov     eax, [edi+0Ch]
0x1005c163  test    eax, eax
0x1005c165  jz      short loc_1005C170
0x1005c167  push    eax; Block
0x1005c168  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c16d  add     esp, 4
0x1005c170  mov     eax, [edi+10h]
0x1005c173  test    eax, eax
0x1005c175  jz      short loc_1005C180
0x1005c177  push    eax; Block
0x1005c178  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c17d  add     esp, 4
0x1005c180  mov     dword ptr [edi], 8
0x1005c186  xor     eax, eax
0x1005c188  mov     dword ptr [edi+4], 0FFFFFB4Ah
0x1005c18f  mov     dword ptr [edi+8], 0
0x1005c196  mov     dword ptr [edi+0Ch], 0
0x1005c19d  mov     dword ptr [edi+10h], 0
0x1005c1a4  jmp     loc_1005C4A9
0x1005c1a9  xor     esi, esi
0x1005c1ab  test    ebx, ebx
0x1005c1ad  jle     short loc_1005C1FF
0x1005c1af  nop
0x1005c1b0  mov     edi, [ebp+var_B0]
0x1005c1b6  lea     eax, [esi+esi*4]
0x1005c1b9  lea     edx, [edx+eax*4]
0x1005c1bc  mov     eax, [edx+4]
0x1005c1bf  mov     ecx, [edi+4]
0x1005c1c2  mov     edi, [ebp+var_A8]
0x1005c1c8  cmp     eax, [ecx+17h]
0x1005c1cb  mov     ecx, [ebp+var_98]
0x1005c1d1  jge     loc_1005C398
0x1005c1d7  test    eax, eax
0x1005c1d9  js      loc_1005C398
0x1005c1df  mov     eax, [edx]
0x1005c1e1  cmp     eax, 0FFh
0x1005c1e6  jg      loc_1005C398
0x1005c1ec  test    eax, eax
0x1005c1ee  js      loc_1005C398
0x1005c1f4  mov     edx, [ebp+var_A0]
0x1005c1fa  inc     esi
0x1005c1fb  cmp     esi, ebx
0x1005c1fd  jl      short loc_1005C1B0
0x1005c1ff  lea     eax, [ebx+ebx*4]
0x1005c202  xor     esi, esi
0x1005c204  lea     edx, [edx+eax*4]
0x1005c207  mov     [ebp+var_A4], edx
0x1005c20d  test    ebx, ebx
0x1005c20f  jle     loc_1005C490
0x1005c215  nop     word ptr [eax+eax+00000000h]
0x1005c220  mov     ecx, [ebp+var_A0]
0x1005c226  lea     eax, [esi+esi*4]
0x1005c229  push    0C4h; Size
0x1005c22e  lea     eax, [ecx+eax*4]
0x1005c231  mov     [ebp+var_9C], eax
0x1005c237  call    ??2@YAPAXI@Z; operator new(uint)
0x1005c23c  add     esp, 4
0x1005c23f  mov     [ebp+Block], eax
0x1005c245  push    edi; struct Err *
0x1005c246  mov     ecx, eax; this
0x1005c248  mov     [ebp+var_4], 0
0x1005c24f  call    ??0Index@@QAE@AAVErr@@@Z; Index::Index(Err &)
0x1005c254  mov     ebx, eax
0x1005c256  mov     [ebp+var_4], 0FFFFFFFFh
0x1005c25d  mov     eax, [edi]
0x1005c25f  test    ebx, ebx
0x1005c261  jz      loc_1005C5A9
0x1005c267  test    al, 8
0x1005c269  jnz     loc_1005C589
0x1005c26f  mov     edx, [ebp+var_9C]
0x1005c275  mov     eax, [edx]
0x1005c277  mov     [ebx+24h], eax
0x1005c27a  movzx   eax, byte ptr [edx+13h]
0x1005c27e  xor     al, [ebx+28h]
0x1005c281  and     al, 1
0x1005c283  xor     [ebx+28h], al
0x1005c286  movzx   eax, byte ptr [edx+13h]
0x1005c28a  shr     eax, 1
0x1005c28c  and     eax, 1
0x1005c28f  mov     [ebx+3Ch], eax
0x1005c292  movzx   eax, byte ptr [edx+8]
0x1005c296  mov     [ebx+29h], al
0x1005c299  mov     eax, [edx+9]
0x1005c29c  mov     [ebx+2Ch], eax
0x1005c29f  mov     eax, [edx+0Dh]
0x1005c2a2  mov     [ebx+30h], eax
0x1005c2a5  movzx   eax, byte ptr [edx+11h]
0x1005c2a9  mov     [ebx+34h], eax
0x1005c2ac  movzx   eax, byte ptr [edx+12h]
0x1005c2b0  mov     [ebx+38h], eax
0x1005c2b3  mov     eax, [edx+4]
0x1005c2b6  mov     edx, [ebp+var_98]
0x1005c2bc  mov     edx, [edx+eax*4+674h]
0x1005c2c3  mov     [ebx+8], edx
0x1005c2c6  mov     [ebp+var_9C], edx
0x1005c2cc  mov     eax, [edx+8]
0x1005c2cf  cmp     eax, [edx+4]
0x1005c2d2  jb      short loc_1005C2ED
0x1005c2d4  push    edi; struct Err *
0x1005c2d5  inc     eax
0x1005c2d6  mov     ecx, edx; this
0x1005c2d8  push    eax; unsigned int
0x1005c2d9  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x1005c2de  test    byte ptr [edi], 8
0x1005c2e1  jnz     loc_1005C569
0x1005c2e7  mov     edx, [ebp+var_9C]
0x1005c2ed  mov     ecx, [edx+8]
0x1005c2f0  mov     eax, [edx]
0x1005c2f2  mov     [eax+ecx*4], ebx
0x1005c2f5  inc     dword ptr [edx+8]
0x1005c2f8  test    byte ptr [edi], 8
0x1005c2fb  jnz     loc_1005C569
0x1005c301  mov     eax, [ebp+var_98]
0x1005c307  mov     eax, [eax+24h]
0x1005c30a  mov     eax, [eax+3Ch]
0x1005c30d  movzx   edx, word ptr [eax+64h]
0x1005c311  mov     eax, [ebp+var_A4]
0x1005c317  movzx   ecx, byte ptr [eax]
0x1005c31a  add     eax, 1
0x1005c31d  jz      loc_1005C3D6
0x1005c323  test    ecx, ecx
0x1005c325  jz      loc_1005C3D6
0x1005c32b  push    41h ; 'A'; cchWideChar
0x1005c32d  lea     edi, [ebp+WideCharStr]
0x1005c333  push    edi; lpWideCharStr
0x1005c334  push    ecx; cbMultiByte
0x1005c335  push    eax; lpMultiByteStr
0x1005c336  push    0; dwFlags
0x1005c338  push    edx; CodePage
0x1005c339  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1005c33f  mov     edi, [ebp+var_A8]
0x1005c345  test    eax, eax
0x1005c347  jz      loc_1005C4C7
0x1005c34d  lea     ecx, [eax+eax]
0x1005c350  mov     eax, ecx
0x1005c352  mov     [ebp+var_9C], ecx
0x1005c358  shr     eax, 1
0x1005c35a  mov     [ebp+var_AC], eax
0x1005c360  cmp     eax, 40h ; '@'
0x1005c363  jbe     loc_1005C3ED
0x1005c369  mov     eax, [ebx+18h]
0x1005c36c  test    eax, eax
0x1005c36e  jz      short loc_1005C379
0x1005c370  push    eax; Block
0x1005c371  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c376  add     esp, 4
0x1005c379  push    0C4h; unsigned int
0x1005c37e  push    ebx; Block
0x1005c37f  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005c384  add     esp, 4
0x1005c387  mov     ecx, edi
0x1005c389  push    0FFFFFB4Ah
0x1005c38e  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005c393  jmp     loc_1005C5F7
0x1005c398  mov     eax, [edi]
0x1005c39a  cmp     eax, 8
0x1005c39d  jge     loc_1005C5FD
0x1005c3a3  test    eax, 0FFFFFFFEh
0x1005c3a8  jz      short loc_1005C3CA
0x1005c3aa  mov     eax, [edi+0Ch]
0x1005c3ad  test    eax, eax
0x1005c3af  jz      short loc_1005C3BA
0x1005c3b1  push    eax; Block
0x1005c3b2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c3b7  add     esp, 4
0x1005c3ba  mov     eax, [edi+10h]
0x1005c3bd  test    eax, eax
0x1005c3bf  jz      short loc_1005C3CA
0x1005c3c1  push    eax; Block
0x1005c3c2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c3c7  add     esp, 4
0x1005c3ca  mov     dword ptr [edi+4], 0FFFFFB4Ah
0x1005c3d1  jmp     loc_1005C5DC
0x1005c3d6  xor     eax, eax
0x1005c3d8  xor     ecx, ecx
0x1005c3da  mov     [ebp+WideCharStr], ax
0x1005c3e1  mov     [ebp+var_9C], ecx
0x1005c3e7  mov     [ebp+var_AC], eax
0x1005c3ed  push    ecx; Size
0x1005c3ee  lea     eax, [ebp+WideCharStr]
0x1005c3f4  push    eax; Src
0x1005c3f5  push    dword ptr [ebx]; void *
0x1005c3f7  call    _memcpy
0x1005c3fc  mov     eax, [ebx]
0x1005c3fe  xor     edx, edx
0x1005c400  mov     ecx, [ebp+var_AC]
0x1005c406  add     esp, 0Ch
0x1005c409  mov     [eax+ecx*2], dx
0x1005c40d  mov     edx, [ebp+var_A4]
0x1005c413  mov     eax, [ebp+var_9C]
0x1005c419  mov     [ebx+4], eax
0x1005c41c  movzx   eax, byte ptr [edx]
0x1005c41f  inc     edx
0x1005c420  add     edx, eax
0x1005c422  mov     dword ptr [ebx+0Ch], 0
0x1005c429  mov     eax, [ebx+24h]
0x1005c42c  mov     [ebp+var_A4], edx
0x1005c432  mov     dword ptr [ebx+14h], 0
0x1005c439  test    eax, eax
0x1005c43b  js      loc_1005C53A
0x1005c441  cmp     eax, 20h ; ' '
0x1005c444  jnb     loc_1005C53A
0x1005c44a  mov     ecx, [ebp+var_98]
0x1005c450  cmp     dword ptr [ecx+eax*4+574h], 0
0x1005c458  jnz     loc_1005C53A
0x1005c45e  mov     [ecx+eax*4+574h], ebx
0x1005c465  mov     eax, [ebx+24h]
0x1005c468  mov     [ecx+esi*4+5F4h], eax
0x1005c46f  inc     esi
0x1005c470  mov     eax, [ebp+var_B0]
0x1005c476  mov     eax, [eax+4]
0x1005c479  cmp     esi, [eax+13h]
0x1005c47c  jl      loc_1005C220
0x1005c482  cmp     esi, 20h ; ' '
0x1005c485  jge     short loc_1005C4A1
0x1005c487  nop     word ptr [eax+eax+00000000h]
0x1005c490  mov     dword ptr [ecx+esi*4+5F4h], 0FFFFFFFFh
0x1005c49b  inc     esi
0x1005c49c  cmp     esi, 20h ; ' '
0x1005c49f  jl      short loc_1005C490
0x1005c4a1  sub     edx, [ebp+var_A0]
0x1005c4a7  mov     eax, edx
0x1005c4a9  mov     ecx, [ebp+var_C]
0x1005c4ac  mov     large fs:0, ecx
0x1005c4b3  pop     ecx
0x1005c4b4  pop     edi
0x1005c4b5  pop     esi
0x1005c4b6  pop     ebx
0x1005c4b7  mov     ecx, [ebp+var_10]
0x1005c4ba  xor     ecx, ebp; StackCookie
0x1005c4bc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005c4c1  mov     esp, ebp
0x1005c4c3  pop     ebp
0x1005c4c4  retn    14h
0x1005c4c7  mov     eax, [edi]
0x1005c4c9  cmp     eax, 8
0x1005c4cc  jge     short loc_1005C517
0x1005c4ce  test    eax, 0FFFFFFFEh
0x1005c4d3  jz      short loc_1005C4F5
0x1005c4d5  mov     eax, [edi+0Ch]
0x1005c4d8  test    eax, eax
0x1005c4da  jz      short loc_1005C4E5
0x1005c4dc  push    eax; Block
0x1005c4dd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c4e2  add     esp, 4
0x1005c4e5  mov     eax, [edi+10h]
0x1005c4e8  test    eax, eax
0x1005c4ea  jz      short loc_1005C4F5
0x1005c4ec  push    eax; Block
0x1005c4ed  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c4f2  add     esp, 4
0x1005c4f5  mov     dword ptr [edi], 8
0x1005c4fb  mov     dword ptr [edi+4], 0FFFFFC16h
0x1005c502  mov     dword ptr [edi+8], 0
0x1005c509  mov     dword ptr [edi+0Ch], 0
0x1005c510  mov     dword ptr [edi+10h], 0
0x1005c517  mov     eax, [ebx+18h]
0x1005c51a  test    eax, eax
0x1005c51c  jz      short loc_1005C527
0x1005c51e  push    eax; Block
0x1005c51f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c524  add     esp, 4
0x1005c527  push    0C4h; unsigned int
0x1005c52c  push    ebx; Block
0x1005c52d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005c532  add     esp, 8
  ... truncated ...
```
