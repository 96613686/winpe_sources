# InterCodeBook(x,x,x,x)

- ea: `0x10010735`
- end: `0x10010a0c`
- name: `_InterCodeBook@16`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10004b3b`

## callees

- `0x100041c0`
- `0x10010735`
- `0x10010a12`
- `0x10010ef2`
- `0x10011341`
- `0x10011ce4`

## pseudocode

```c
int __thiscall InterCodeBook(int this, int *a2, int *a3)
{
  int v3; // esi
  __int16 v4; // cx
  int v5; // eax
  int result; // eax
  int v7; // edx
  int v8; // eax
  int v9; // ecx
  char v10; // bl
  int v11; // edi
  int v12; // edx
  int v13; // ecx
  int v14; // esi
  int v15; // edi
  int v17; // esi
  int v18; // ecx
  int v19; // eax
  int v20; // edi
  int v21; // eax
  int v22; // edi
  int v23; // eax
  int v24; // ecx
  int v25; // edi
  int v26; // edi
  int v27; // ecx
  unsigned int v28; // edx
  int v29; // eax
  int v30; // esi
  int v31; // edx
  int i; // esi
  int v33; // eax
  int v34; // esi
  int v35; // [esp+Ch] [ebp-1Ch]
  int v36; // [esp+10h] [ebp-18h]
  int v38; // [esp+18h] [ebp-10h]
  __int16 v39; // [esp+1Ch] [ebp-Ch]
  int v40; // [esp+1Ch] [ebp-Ch]
  int v41; // [esp+20h] [ebp-8h] BYREF
  int v42; // [esp+24h] [ebp-4h]

  v3 = *((__int16 *)a2 + 5);
  v4 = a2[3];
  if ( a2[3] >= v3 )
    v4 = *((_WORD *)a2 + 5);
  v5 = v4 + *((__int16 *)a3 + 2);
  if ( v5 > 256 )
    v5 = 256;
  v35 = v5;
  if ( v5 <= v3 )
    return KeyCodeBook(a2);
  v7 = *a3;
  v8 = 0;
  v9 = *a2;
  v41 = 0;
  do
  {
    if ( *(_WORD *)(v7 + 6) == 0xFFFF )
    {
      *(_DWORD *)(v9 + 12) = 0;
      v10 = 1;
    }
    else
    {
      v10 = 0;
      *(_DWORD *)v9 = *(_DWORD *)v7;
      *(_WORD *)(v9 + 4) = *(_WORD *)(v7 + 4);
      v8 = v41;
      *(_BYTE *)(v9 + 6) = v41;
    }
    *(_BYTE *)(v9 + 7) = v10;
    v7 += 8;
    v9 += 460;
    v41 = ++v8;
  }
  while ( v8 < 256 );
  *((_WORD *)a2 + 4) = *((_WORD *)a3 + 2);
  MatchAndRefine((int *)this, 2, 255, 0);
  v11 = v35;
  v12 = 0;
  v13 = *a2;
  v14 = v35;
  v42 = (unsigned __int16)v35;
  *((_WORD *)a2 + 4) = v35;
  v36 = 0;
  v39 = 0;
  if ( v35 )
  {
    v15 = 0;
    do
    {
      --v14;
      if ( v12 >= *((__int16 *)a2 + 5) )
        break;
      if ( (*(_BYTE *)(v13 + 7) & 1) != 0 )
      {
        if ( v12++ )
          *(_DWORD *)(v15 + 8) = v13;
        else
          v41 = v13;
        v15 = v13;
      }
      v13 += 460;
    }
    while ( v14 );
    v36 = v15;
    v11 = v35;
    v39 = v12;
  }
  v17 = 0;
  v38 = 0;
  do
  {
    if ( v12 >= *((__int16 *)a2 + 5) )
      break;
    v18 = *a2;
    v19 = v11;
    if ( !v11 )
      goto LABEL_35;
    v20 = v38;
    do
    {
      v40 = --v19;
      if ( (*(_BYTE *)(v18 + 7) & 1) != 0 || *(_DWORD *)(v18 + 12) != v17 )
        goto LABEL_33;
      v20 |= v17;
      v21 = v12++;
      v38 = v20;
      if ( v21 )
        *(_DWORD *)(v36 + 8) = v18;
      else
        v41 = v18;
      *(_BYTE *)(v18 + 7) = 1;
      v36 = v18;
      if ( v12 == *((__int16 *)a2 + 5) )
        break;
      v19 = v40;
LABEL_33:
      v18 += 460;
    }
    while ( v19 );
    v11 = v35;
    v39 = v12;
LABEL_35:
    ++v17;
  }
  while ( v17 <= 1 );
  if ( v38 )
  {
    v22 = a2[3];
    v17 = a2[1];
    if ( v22 )
    {
      do
      {
        --v22;
        if ( (*(_BYTE *)(460 * *(unsigned __int8 *)(v17 + 6) + *a2 + 7) & 1) != 0 )
        {
          v23 = Match(v42, *(_WORD *)(this + 104), 0);
          v24 = *a2 + 460 * *(unsigned __int8 *)(v17 + 6);
          ++*(_DWORD *)(v24 + 12);
          *(_DWORD *)(v24 + 40) += v23;
        }
        v17 += 8;
      }
      while ( v22 );
      LOWORD(v12) = v39;
    }
  }
  v25 = (unsigned __int16)v12;
  LOWORD(v17) = SplitCodeBook(0, 0, &v41, (unsigned __int16)v12, 3);
  v26 = (__int16)v17 + (__int16)SplitCodeBook(0, 0, &v41, v25 - v17, 1);
  while ( v26 < *((__int16 *)a2 + 5) )
  {
    v27 = v35;
    v28 = 0;
    v29 = *a2;
    ++v26;
    v30 = 0;
    if ( !v35 )
      break;
    do
    {
      --v27;
      if ( (*(_BYTE *)(v29 + 7) & 3) == 0 && *(_DWORD *)(v29 + 40) >= v28 )
      {
        v28 = *(_DWORD *)(v29 + 40);
        v30 = v29;
      }
      v29 += 460;
    }
    while ( v27 );
    if ( !v28 )
      break;
    *(_BYTE *)(v30 + 7) |= 2u;
  }
  if ( (*(_BYTE *)(this + 106) & 1) != 0 )
  {
    v31 = a2[3];
    for ( i = a2[1]; v31; --v31 )
    {
      v33 = *(unsigned __int8 *)(i + 6);
      i += 8;
      *(_BYTE *)(i - 1) = *(_BYTE *)(460 * v33 + *a2 + 7) & 2;
    }
    result = ConvergeCodeBook(2, 2);
    if ( result )
      result = MatchAndRefine((int *)this, 2, 255, 0);
    a2[5] += result;
  }
  else
  {
    v34 = a2[5];
    result = v34 + ConvergeCodeBook(255, 0);
    a2[5] = result;
  }
  return result;
}

```

## disassembly

```asm
0x10010735  mov     edi, edi
0x10010737  push    ebp
0x10010738  mov     ebp, esp
0x1001073a  and     esp, 0FFFFFFF8h
0x1001073d  sub     esp, 1Ch
0x10010740  push    ebx
0x10010741  mov     ebx, [ebp+arg_0]
0x10010744  push    esi
0x10010745  mov     [esp+24h+Buf], ecx
0x10010749  push    edi
0x1001074a  movsx   esi, word ptr [ebx+0Ah]
0x1001074e  mov     edx, [ebx+0Ch]
0x10010751  cmp     edx, esi
0x10010753  mov     edi, [ebp+arg_4]
0x10010756  movzx   eax, si
0x10010759  movzx   ecx, dx
0x1001075c  cmovge  ecx, eax
0x1001075f  movsx   eax, word ptr [edi+4]
0x10010763  movsx   ecx, cx
0x10010766  add     eax, ecx
0x10010768  mov     ecx, 100h
0x1001076d  cmp     eax, ecx
0x1001076f  cmovg   eax, ecx
0x10010772  mov     [esp+28h+var_1C], eax
0x10010776  cmp     eax, esi
0x10010778  jg      short loc_10010789
0x1001077a  mov     ecx, [esp+28h+Buf]
0x1001077e  push    ebx
0x1001077f  call    _KeyCodeBook@12; KeyCodeBook(x,x,x)
0x10010784  jmp     loc_10010A03
0x10010789  mov     edx, [edi]
0x1001078b  xor     eax, eax
0x1001078d  mov     ecx, [ebx]
0x1001078f  mov     [esp+28h+var_8], eax
0x10010793  mov     esi, 0FFFFh
0x10010798  cmp     [edx+6], si
0x1001079c  jnz     short loc_100107A9
0x1001079e  mov     dword ptr [ecx+0Ch], 0
0x100107a5  mov     bl, 1
0x100107a7  jmp     short loc_100107BE
0x100107a9  mov     eax, [edx]
0x100107ab  xor     bl, bl
0x100107ad  mov     [ecx], eax
0x100107af  mov     ax, [edx+4]
0x100107b3  mov     [ecx+4], ax
0x100107b7  mov     eax, [esp+28h+var_8]
0x100107bb  mov     [ecx+6], al
0x100107be  mov     [ecx+7], bl
0x100107c1  add     edx, 8
0x100107c4  add     ecx, 1CCh
0x100107ca  inc     eax
0x100107cb  mov     [esp+28h+var_8], eax
0x100107cf  cmp     eax, 100h
0x100107d4  jl      short loc_10010793
0x100107d6  mov     ebx, [ebp+arg_0]
0x100107d9  mov     edx, ebx
0x100107db  mov     ax, [edi+4]
0x100107df  mov     ecx, [esp+28h+Buf]; Buf
0x100107e3  push    0; int
0x100107e5  push    0FFh; char
0x100107ea  push    2; int
0x100107ec  mov     [ebx+8], ax
0x100107f0  call    _MatchAndRefine@20; MatchAndRefine(x,x,x,x,x)
0x100107f5  mov     edi, [esp+28h+var_1C]
0x100107f9  xor     edx, edx
0x100107fb  mov     ecx, [ebx]
0x100107fd  mov     esi, edi
0x100107ff  movzx   eax, di
0x10010802  mov     [esp+28h+var_4], eax
0x10010806  mov     [ebx+8], ax
0x1001080a  mov     [esp+28h+var_18], 0
0x10010812  mov     [esp+28h+var_C], edx
0x10010816  test    edi, edi
0x10010818  jz      short loc_10010853
0x1001081a  mov     edi, edx
0x1001081c  movsx   eax, word ptr [ebx+0Ah]
0x10010820  dec     esi
0x10010821  cmp     edx, eax
0x10010823  jge     short loc_10010847
0x10010825  test    byte ptr [ecx+7], 1
0x10010829  jz      short loc_1001083D
0x1001082b  mov     eax, edx
0x1001082d  inc     edx
0x1001082e  test    eax, eax
0x10010830  jnz     short loc_10010838
0x10010832  mov     [esp+28h+var_8], ecx
0x10010836  jmp     short loc_1001083B
0x10010838  mov     [edi+8], ecx
0x1001083b  mov     edi, ecx
0x1001083d  add     ecx, 1CCh
0x10010843  test    esi, esi
0x10010845  jnz     short loc_1001081C
0x10010847  mov     [esp+28h+var_18], edi
0x1001084b  mov     edi, [esp+28h+var_1C]
0x1001084f  mov     [esp+28h+var_C], edx
0x10010853  xor     esi, esi
0x10010855  xor     eax, eax
0x10010857  mov     [esp+28h+var_10], eax
0x1001085b  movsx   eax, word ptr [ebx+0Ah]
0x1001085f  cmp     edx, eax
0x10010861  jge     short loc_100108C5
0x10010863  mov     ecx, [ebx]
0x10010865  mov     eax, edi
0x10010867  test    edi, edi
0x10010869  jz      short loc_100108BF
0x1001086b  mov     edi, [esp+28h+var_10]
0x1001086f  dec     eax
0x10010870  test    byte ptr [ecx+7], 1
0x10010874  mov     [esp+28h+var_C], eax
0x10010878  jnz     short loc_100108AD
0x1001087a  cmp     [ecx+0Ch], esi
0x1001087d  jnz     short loc_100108AD
0x1001087f  or      edi, esi
0x10010881  mov     eax, edx
0x10010883  inc     edx
0x10010884  mov     [esp+28h+var_10], edi
0x10010888  test    eax, eax
0x1001088a  jnz     short loc_10010892
0x1001088c  mov     [esp+28h+var_8], ecx
0x10010890  jmp     short loc_10010899
0x10010892  mov     eax, [esp+28h+var_18]
0x10010896  mov     [eax+8], ecx
0x10010899  mov     byte ptr [ecx+7], 1
0x1001089d  movsx   eax, word ptr [ebx+0Ah]
0x100108a1  mov     [esp+28h+var_18], ecx
0x100108a5  cmp     edx, eax
0x100108a7  jz      short loc_100108B7
0x100108a9  mov     eax, [esp+28h+var_C]
0x100108ad  add     ecx, 1CCh
0x100108b3  test    eax, eax
0x100108b5  jnz     short loc_1001086F
0x100108b7  mov     edi, [esp+28h+var_1C]
0x100108bb  mov     [esp+28h+var_C], edx
0x100108bf  inc     esi
0x100108c0  cmp     esi, 1
0x100108c3  jle     short loc_1001085B
0x100108c5  cmp     [esp+28h+var_10], 0
0x100108ca  jz      short loc_1001091D
0x100108cc  mov     edi, [ebx+0Ch]
0x100108cf  mov     esi, [ebx+4]
0x100108d2  test    edi, edi
0x100108d4  jz      short loc_1001091D
0x100108d6  movzx   eax, byte ptr [esi+6]
0x100108da  dec     edi
0x100108db  mov     edx, [ebx]
0x100108dd  imul    eax, 1CCh
0x100108e3  test    byte ptr [eax+edx+7], 1
0x100108e8  jz      short loc_10010912
0x100108ea  mov     eax, [esp+28h+Buf]
0x100108ee  mov     ecx, esi
0x100108f0  push    0
0x100108f2  movzx   eax, word ptr [eax+68h]
0x100108f6  push    eax
0x100108f7  push    [esp+30h+var_4]
0x100108fb  call    _Match@20; Match(x,x,x,x,x)
0x10010900  movzx   ecx, byte ptr [esi+6]
0x10010904  imul    ecx, 1CCh
0x1001090a  add     ecx, [ebx]
0x1001090c  inc     dword ptr [ecx+0Ch]
0x1001090f  add     [ecx+28h], eax
0x10010912  add     esi, 8
0x10010915  test    edi, edi
0x10010917  jnz     short loc_100108D6
0x10010919  mov     edx, [esp+28h+var_C]
0x1001091d  push    3
0x1001091f  movzx   edi, dx
0x10010922  lea     eax, [esp+2Ch+var_8]
0x10010926  push    edi
0x10010927  push    eax
0x10010928  push    0
0x1001092a  push    0
0x1001092c  xor     edx, edx
0x1001092e  mov     ecx, ebx
0x10010930  call    _SplitCodeBook@28; SplitCodeBook(x,x,x,x,x,x,x)
0x10010935  mov     si, ax
0x10010938  xor     edx, edx
0x1001093a  push    1
0x1001093c  sub     edi, esi
0x1001093e  lea     eax, [esp+2Ch+var_8]
0x10010942  push    edi
0x10010943  push    eax
0x10010944  push    0
0x10010946  push    0
0x10010948  mov     ecx, ebx
0x1001094a  call    _SplitCodeBook@28; SplitCodeBook(x,x,x,x,x,x,x)
0x1001094f  movsx   edi, ax
0x10010952  movsx   eax, si
0x10010955  add     edi, eax
0x10010957  jmp     short loc_1001098A
0x10010959  mov     ecx, [esp+28h+var_1C]
0x1001095d  xor     edx, edx
0x1001095f  mov     eax, [ebx]
0x10010961  inc     edi
0x10010962  xor     esi, esi
0x10010964  cmp     ecx, edx
0x10010966  jz      short loc_10010992
0x10010968  dec     ecx
0x10010969  test    byte ptr [eax+7], 3
0x1001096d  jnz     short loc_10010979
0x1001096f  cmp     [eax+28h], edx
0x10010972  jb      short loc_10010979
0x10010974  mov     edx, [eax+28h]
0x10010977  mov     esi, eax
0x10010979  add     eax, 1CCh
0x1001097e  test    ecx, ecx
0x10010980  jnz     short loc_10010968
0x10010982  test    edx, edx
0x10010984  jz      short loc_10010992
0x10010986  or      byte ptr [esi+7], 2
0x1001098a  movsx   eax, word ptr [ebx+0Ah]
0x1001098e  cmp     edi, eax
0x10010990  jl      short loc_10010959
0x10010992  mov     edi, [esp+28h+Buf]
0x10010996  test    byte ptr [edi+6Ah], 1
0x1001099a  jz      short loc_100109EB
0x1001099c  mov     edx, [ebx+0Ch]
0x1001099f  mov     esi, [ebx+4]
0x100109a2  test    edx, edx
0x100109a4  jz      short loc_100109C3
0x100109a6  movzx   eax, byte ptr [esi+6]
0x100109aa  lea     esi, [esi+8]
0x100109ad  imul    ecx, eax, 1CCh
0x100109b3  mov     eax, [ebx]
0x100109b5  mov     al, [ecx+eax+7]
0x100109b9  and     al, 2
0x100109bb  mov     [esi-1], al
0x100109be  sub     edx, 1
0x100109c1  jnz     short loc_100109A6
0x100109c3  push    2
0x100109c5  push    2
0x100109c7  mov     edx, ebx
0x100109c9  mov     ecx, edi
0x100109cb  call    _ConvergeCodeBook@16; ConvergeCodeBook(x,x,x,x)
0x100109d0  test    eax, eax
0x100109d2  jz      short loc_100109E6
0x100109d4  push    0; int
0x100109d6  push    0FFh; char
0x100109db  push    2; int
0x100109dd  mov     edx, ebx
0x100109df  mov     ecx, edi; Buf
0x100109e1  call    _MatchAndRefine@20; MatchAndRefine(x,x,x,x,x)
0x100109e6  add     [ebx+14h], eax
0x100109e9  jmp     short loc_10010A03
0x100109eb  mov     esi, [ebx+14h]
0x100109ee  mov     edx, ebx
0x100109f0  push    0
0x100109f2  push    0FFh
0x100109f7  mov     ecx, edi
0x100109f9  call    _ConvergeCodeBook@16; ConvergeCodeBook(x,x,x,x)
0x100109fe  add     eax, esi
0x10010a00  mov     [ebx+14h], eax
0x10010a03  pop     edi
0x10010a04  pop     esi
0x10010a05  pop     ebx
0x10010a06  mov     esp, ebp
0x10010a08  pop     ebp
0x10010a09  retn    8
```
