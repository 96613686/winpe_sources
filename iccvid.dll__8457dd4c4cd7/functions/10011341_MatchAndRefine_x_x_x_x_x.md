# MatchAndRefine(x,x,x,x,x)

- ea: `0x10011341`
- end: `0x100115e8`
- name: `_MatchAndRefine@20`
- size: `679`
- prototype: `int __thiscall(jmp_buf Buf, int, char, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100041c0`
- `0x10010735`

## callees

- `0x10010c96`
- `0x10010ef2`
- `0x10011341`
- `0x100130b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100115d8`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100115d8`

## pseudocode

```c
int __fastcall MatchAndRefine(jmp_buf Buf, int *a2, int a3, char a4, unsigned __int8 a5)
{
  int *v5; // ebx
  int v7; // esi
  int v8; // edx
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  __int16 v12; // ax
  __int16 Neighbors; // ax
  int v14; // eax
  unsigned int *v15; // esi
  char v16; // cl
  unsigned int v17; // eax
  _DWORD *v18; // ecx
  int v19; // ecx
  unsigned __int8 *v20; // esi
  int v21; // edi
  unsigned __int8 v22; // bl
  int v23; // ecx
  unsigned __int8 v24; // cl
  unsigned __int8 v25; // al
  int (__thiscall *v26)(_DWORD, int, int, int); // esi
  __int16 v27; // ax
  int v28; // eax
  int *v30; // [esp+10h] [ebp-Ch]
  int v32; // [esp+18h] [ebp-4h]
  int v33; // [esp+18h] [ebp-4h]

  v5 = a2;
  v7 = *((__int16 *)a2 + 4);
  v8 = 0;
  v9 = *a2;
  v30 = Buf;
  if ( v7 )
  {
    do
    {
      *(_DWORD *)(v9 + 12) = 0;
      v9 += 460;
      *(_DWORD *)(v9 - 420) = 0;
      *(_DWORD *)(v9 - 444) = 0;
      *(_DWORD *)(v9 - 440) = 0;
      *(_DWORD *)(v9 - 436) = 0;
      *(_DWORD *)(v9 - 432) = 0;
      *(_DWORD *)(v9 - 428) = 0;
      *(_DWORD *)(v9 - 424) = 0;
      v10 = v8 + 1;
      if ( ((unsigned __int8)(a5 ^ *(_BYTE *)(v9 - 453)) & (a5 | 1)) != 0 )
        v10 = v8;
      v8 = v10;
      --v7;
    }
    while ( v7 );
    v5 = a2;
  }
  if ( a3 )
  {
    if ( a3 == 2 && *((_WORD *)Buf + 94) == 1 )
    {
      v11 = 8;
      while ( 1 )
      {
        --v11;
        if ( v8 >= dword_10014004[4 * v11] )
          break;
        if ( !v11 )
        {
          v11 = -1;
          break;
        }
      }
      *((_WORD *)Buf + 51) = *((_WORD *)Buf + v11 + 86);
    }
    v12 = *((_WORD *)Buf + 51);
    if ( v12 )
      Neighbors = MakeNeighbors(v12, a5);
    else
      Neighbors = 0;
    *((_WORD *)Buf + 52) = Neighbors;
  }
  v14 = v5[3];
  v15 = (unsigned int *)v5[1];
  if ( v14 )
  {
    v16 = a4;
    do
    {
      v32 = --v14;
      if ( v16 == -1 || v16 == *((_BYTE *)v15 + 7) )
      {
        v17 = Match(v15, (unsigned __int8 *)*v5, *((_WORD *)v5 + 4), *((_WORD *)Buf + 52), a5);
        v18 = (_DWORD *)(*v5 + 460 * *((unsigned __int8 *)v15 + 6));
        v18[10] += v17;
        ++v18[3];
        v18[4] += *(unsigned __int8 *)v15;
        v18[5] += *((unsigned __int8 *)v15 + 1);
        v18[6] += *((unsigned __int8 *)v15 + 2);
        v18[7] += *((unsigned __int8 *)v15 + 3);
        v18[8] += *((unsigned __int8 *)v15 + 4);
        v18[9] += *((unsigned __int8 *)v15 + 5);
        v14 = v32;
        v16 = a4;
      }
      v15 += 2;
    }
    while ( v14 );
  }
  v19 = 0;
  v20 = (unsigned __int8 *)*v5;
  v33 = 0;
  if ( *((_WORD *)v5 + 4) )
  {
    v21 = *((__int16 *)v5 + 4);
    do
    {
      v22 = v20[7];
      --v21;
      if ( (v22 & 1) == 0 )
      {
        if ( *((_DWORD *)v20 + 3) )
        {
          v19 += *((_DWORD *)v20 + 10);
          v33 = v19;
          if ( (v22 & 2) != 0 )
          {
            v23 = *((int *)v20 + 3) >> 1;
            *((_DWORD *)v20 + 4) = (unsigned int)(v23 + *((_DWORD *)v20 + 4)) / *((_DWORD *)v20 + 3);
            *((_DWORD *)v20 + 5) = (unsigned int)(v23 + *((_DWORD *)v20 + 5)) / *((_DWORD *)v20 + 3);
            *((_DWORD *)v20 + 6) = (unsigned int)(v23 + *((_DWORD *)v20 + 6)) / *((_DWORD *)v20 + 3);
            *((_DWORD *)v20 + 7) = (unsigned int)(v23 + *((_DWORD *)v20 + 7)) / *((_DWORD *)v20 + 3);
            *((_DWORD *)v20 + 8) = (unsigned int)(v23 + *((_DWORD *)v20 + 8)) / *((_DWORD *)v20 + 3);
            *((_DWORD *)v20 + 9) = (unsigned int)(v23 + *((_DWORD *)v20 + 9)) / *((_DWORD *)v20 + 3);
            v24 = v20[16];
            if ( *v20 != v24
              || v20[1] != v20[20]
              || v20[2] != v20[24]
              || v20[3] != v20[28]
              || v20[4] != v20[32]
              || v20[5] != v20[36] )
            {
              v20[1] = v20[20];
              v20[2] = v20[24];
              v20[3] = v20[28];
              v20[4] = v20[32];
              v25 = v20[36];
              *v20 = v24;
              v20[5] = v25;
              v20[7] = v22 | 4;
            }
            v19 = v33;
          }
        }
      }
      v20 += 460;
    }
    while ( v21 );
    Buf = v30;
  }
  v26 = (int (__thiscall *)(_DWORD, int, int, int))Buf[261];
  v27 = *((_WORD *)Buf + 524) + 1;
  *((_WORD *)Buf + 524) = v27;
  if ( v26 )
  {
    v28 = 100 * v27 / *((__int16 *)Buf + 525);
    if ( v28 > 100 )
      v28 = 100;
    if ( v26(v26, Buf[260], 1, v28) )
      _longjmp(Buf, 1);
  }
  return v33;
}

```

## disassembly

```asm
0x10011341  mov     edi, edi
0x10011343  push    ebp
0x10011344  mov     ebp, esp
0x10011346  sub     esp, 10h
0x10011349  push    ebx
0x1001134a  mov     ebx, edx
0x1001134c  xor     eax, eax
0x1001134e  push    esi
0x1001134f  push    edi
0x10011350  mov     edi, ecx
0x10011352  mov     [ebp+var_4], ebx
0x10011355  movsx   esi, word ptr [ebx+8]
0x10011359  mov     edx, eax
0x1001135b  mov     ecx, [ebx]
0x1001135d  mov     [ebp+var_C], edi
0x10011360  test    esi, esi
0x10011362  jz      short loc_100113BB
0x10011364  mov     bl, byte ptr [ebp+arg_8]
0x10011367  or      bl, 1
0x1001136a  mov     [ecx+0Ch], eax
0x1001136d  lea     ecx, [ecx+1CCh]
0x10011373  mov     [ecx-1A4h], eax
0x10011379  mov     [ecx-1BCh], eax
0x1001137f  mov     [ecx-1B8h], eax
0x10011385  mov     [ecx-1B4h], eax
0x1001138b  mov     [ecx-1B0h], eax
0x10011391  mov     [ecx-1ACh], eax
0x10011397  mov     [ecx-1A8h], eax
0x1001139d  mov     al, [ecx-1C5h]
0x100113a3  xor     al, byte ptr [ebp+arg_8]
0x100113a6  test    bl, al
0x100113a8  lea     eax, [edx+1]
0x100113ab  push    0
0x100113ad  cmovnz  eax, edx
0x100113b0  mov     edx, eax
0x100113b2  pop     eax
0x100113b3  sub     esi, 1
0x100113b6  jnz     short loc_1001136A
0x100113b8  mov     ebx, [ebp+var_4]
0x100113bb  xor     eax, eax
0x100113bd  inc     eax
0x100113be  cmp     [ebp+arg_0], 0
0x100113c2  jz      short loc_10011418
0x100113c4  cmp     [ebp+arg_0], 2
0x100113c8  jnz     short loc_100113F5
0x100113ca  cmp     [edi+0BCh], ax
0x100113d1  jnz     short loc_100113F5
0x100113d3  push    8
0x100113d5  pop     ecx
0x100113d6  dec     ecx
0x100113d7  mov     eax, ecx
0x100113d9  shl     eax, 4
0x100113dc  cmp     edx, dword_10014004[eax]
0x100113e2  jge     short loc_100113E9
0x100113e4  test    ecx, ecx
0x100113e6  jnz     short loc_100113D6
0x100113e8  dec     ecx
0x100113e9  mov     ax, [edi+ecx*2+0ACh]
0x100113f1  mov     [edi+66h], ax
0x100113f5  movzx   eax, word ptr [edi+66h]
0x100113f9  test    ax, ax
0x100113fc  jz      short loc_10011412
0x100113fe  push    [ebp+arg_8]
0x10011401  movsx   edx, word ptr [ebx+8]
0x10011405  mov     ecx, [ebx]
0x10011407  push    eax
0x10011408  call    _MakeNeighbors@16; MakeNeighbors(x,x,x,x)
0x1001140d  movzx   eax, ax
0x10011410  jmp     short loc_10011414
0x10011412  xor     eax, eax
0x10011414  mov     [edi+68h], ax
0x10011418  mov     eax, [ebx+0Ch]
0x1001141b  mov     esi, [ebx+4]
0x1001141e  test    eax, eax
0x10011420  jz      short loc_10011491
0x10011422  mov     cl, [ebp+arg_4]
0x10011425  dec     eax
0x10011426  mov     [ebp+var_4], eax
0x10011429  cmp     cl, 0FFh
0x1001142c  jz      short loc_10011433
0x1001142e  cmp     cl, [esi+7]
0x10011431  jnz     short loc_1001148A
0x10011433  push    [ebp+arg_8]
0x10011436  movzx   eax, word ptr [edi+68h]
0x1001143a  mov     ecx, esi
0x1001143c  mov     edx, [ebx]
0x1001143e  push    eax
0x1001143f  movzx   eax, word ptr [ebx+8]
0x10011443  push    eax
0x10011444  call    _Match@20; Match(x,x,x,x,x)
0x10011449  movzx   ecx, byte ptr [esi+6]
0x1001144d  imul    ecx, 1CCh
0x10011453  add     ecx, [ebx]
0x10011455  add     [ecx+28h], eax
0x10011458  inc     dword ptr [ecx+0Ch]
0x1001145b  movzx   eax, byte ptr [esi]
0x1001145e  add     [ecx+10h], eax
0x10011461  movzx   eax, byte ptr [esi+1]
0x10011465  add     [ecx+14h], eax
0x10011468  movzx   eax, byte ptr [esi+2]
0x1001146c  add     [ecx+18h], eax
0x1001146f  movzx   eax, byte ptr [esi+3]
0x10011473  add     [ecx+1Ch], eax
0x10011476  movzx   eax, byte ptr [esi+4]
0x1001147a  add     [ecx+20h], eax
0x1001147d  movzx   eax, byte ptr [esi+5]
0x10011481  add     [ecx+24h], eax
0x10011484  mov     eax, [ebp+var_4]
0x10011487  mov     cl, [ebp+arg_4]
0x1001148a  add     esi, 8
0x1001148d  test    eax, eax
0x1001148f  jnz     short loc_10011425
0x10011491  movsx   eax, word ptr [ebx+8]
0x10011495  xor     ecx, ecx
0x10011497  mov     esi, [ebx]
0x10011499  mov     [ebp+var_4], ecx
0x1001149c  mov     [ebp+var_8], eax
0x1001149f  test    eax, eax
0x100114a1  jz      loc_1001158B
0x100114a7  mov     edi, eax
0x100114a9  mov     bl, [esi+7]
0x100114ac  dec     edi
0x100114ad  test    bl, 1
0x100114b0  jnz     loc_1001157A
0x100114b6  cmp     dword ptr [esi+0Ch], 0
0x100114ba  jz      loc_1001157A
0x100114c0  add     ecx, [esi+28h]
0x100114c3  mov     [ebp+var_4], ecx
0x100114c6  test    bl, 2
0x100114c9  jz      loc_1001157A
0x100114cf  mov     ecx, [esi+0Ch]
0x100114d2  xor     edx, edx
0x100114d4  mov     eax, [esi+10h]
0x100114d7  sar     ecx, 1
0x100114d9  add     eax, ecx
0x100114db  div     dword ptr [esi+0Ch]
0x100114de  xor     edx, edx
0x100114e0  mov     [esi+10h], eax
0x100114e3  mov     eax, [esi+14h]
0x100114e6  add     eax, ecx
0x100114e8  div     dword ptr [esi+0Ch]
0x100114eb  xor     edx, edx
0x100114ed  mov     [esi+14h], eax
0x100114f0  mov     eax, [esi+18h]
0x100114f3  add     eax, ecx
0x100114f5  div     dword ptr [esi+0Ch]
0x100114f8  xor     edx, edx
0x100114fa  mov     [esi+18h], eax
0x100114fd  mov     eax, [esi+1Ch]
0x10011500  add     eax, ecx
0x10011502  div     dword ptr [esi+0Ch]
0x10011505  xor     edx, edx
0x10011507  mov     [esi+1Ch], eax
0x1001150a  mov     eax, [esi+20h]
0x1001150d  add     eax, ecx
0x1001150f  div     dword ptr [esi+0Ch]
0x10011512  xor     edx, edx
0x10011514  mov     [esi+20h], eax
0x10011517  mov     eax, [esi+24h]
0x1001151a  add     eax, ecx
0x1001151c  div     dword ptr [esi+0Ch]
0x1001151f  mov     [esi+24h], eax
0x10011522  mov     cl, [esi+10h]
0x10011525  cmp     [esi], cl
0x10011527  jnz     short loc_10011551
0x10011529  mov     al, [esi+1]
0x1001152c  cmp     al, [esi+14h]
0x1001152f  jnz     short loc_10011551
0x10011531  mov     al, [esi+2]
0x10011534  cmp     al, [esi+18h]
0x10011537  jnz     short loc_10011551
0x10011539  mov     al, [esi+3]
0x1001153c  cmp     al, [esi+1Ch]
0x1001153f  jnz     short loc_10011551
0x10011541  mov     al, [esi+4]
0x10011544  cmp     al, [esi+20h]
0x10011547  jnz     short loc_10011551
0x10011549  mov     al, [esi+5]
0x1001154c  cmp     al, [esi+24h]
0x1001154f  jz      short loc_10011577
0x10011551  mov     al, [esi+14h]
0x10011554  or      bl, 4
0x10011557  mov     [esi+1], al
0x1001155a  mov     al, [esi+18h]
0x1001155d  mov     [esi+2], al
0x10011560  mov     al, [esi+1Ch]
0x10011563  mov     [esi+3], al
0x10011566  mov     al, [esi+20h]
0x10011569  mov     [esi+4], al
0x1001156c  mov     al, [esi+24h]
0x1001156f  mov     [esi], cl
0x10011571  mov     [esi+5], al
0x10011574  mov     [esi+7], bl
0x10011577  mov     ecx, [ebp+var_4]
0x1001157a  add     esi, 1CCh
0x10011580  test    edi, edi
0x10011582  jnz     loc_100114A9
0x10011588  mov     edi, [ebp+var_C]
0x1001158b  mov     ax, [edi+418h]
0x10011592  mov     esi, [edi+414h]
0x10011598  inc     ax
0x1001159a  movzx   eax, ax
0x1001159d  mov     [edi+418h], ax
0x100115a4  test    esi, esi
0x100115a6  jz      short loc_100115DE
0x100115a8  movsx   ecx, word ptr [edi+41Ah]
0x100115af  cwde
0x100115b0  imul    eax, 64h ; 'd'
0x100115b3  push    64h ; 'd'
0x100115b5  cdq
0x100115b6  idiv    ecx
0x100115b8  pop     ecx
0x100115b9  cmp     eax, ecx
0x100115bb  cmovg   eax, ecx
0x100115be  mov     ecx, esi
0x100115c0  push    eax
0x100115c1  push    1
0x100115c3  push    dword ptr [edi+410h]
0x100115c9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100115cf  call    esi
0x100115d1  test    eax, eax
0x100115d3  jz      short loc_100115DE
0x100115d5  push    1; Value
0x100115d7  push    edi; Buf
0x100115d8  call    ds:__imp__longjmp
0x100115de  mov     eax, [ebp+var_4]
0x100115e1  pop     edi
0x100115e2  pop     esi
0x100115e3  pop     ebx
0x100115e4  leave
0x100115e5  retn    0Ch
```
