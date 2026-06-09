# ErrOldOpenTempTable(x,x,x,x,x,x)

- ea: `0x10088729`
- end: `0x10088902`
- name: `_ErrOldOpenTempTable@24`
- size: `473`
- prototype: `int __thiscall(int, int, int, int, int)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x100894de`
- `0x1008d23f`
- `0x10098590`
- `0x1009b332`
- `0x1009cdcb`
- `0x100a1430`
- `0x100a21d2`
- `0x100a4bb2`
- `0x100c1810`
- `0x100db21a`
- `0x100f8fda`
- `0x100f9320`
- `0x100fa71e`
- `0x101088f0`
- `0x1010a272`
- `0x1010ae0e`

## callees

- `0x100460fb`
- `0x1004cb30`
- `0x10088729`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100888f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100888f0`

## pseudocode

```c
int __fastcall ErrOldOpenTempTable(int a1, int a2, unsigned int a3, int a4, int a5, int a6)
{
  unsigned int v6; // esi
  int v7; // eax
  unsigned int v8; // edi
  int result; // eax
  _DWORD *v10; // eax
  unsigned int v11; // ecx
  int v12; // edx
  char *v13; // ebx
  int v14; // edi
  int v15; // eax
  int v16; // eax
  int v17; // ecx
  int v18; // esi
  __int16 v19; // cx
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int i; // esi
  int v25; // ecx
  int v26; // edx
  int v27; // [esp-4h] [ebp-34h]
  _DWORD *v28; // [esp-4h] [ebp-34h]
  int v29; // [esp+Ch] [ebp-24h]
  _DWORD *Block; // [esp+10h] [ebp-20h]
  int v31; // [esp+14h] [ebp-1Ch]
  int v32; // [esp+18h] [ebp-18h]
  unsigned int v33; // [esp+1Ch] [ebp-14h]
  unsigned int v34; // [esp+20h] [ebp-10h]

  v6 = 0;
  v7 = 1033;
  if ( a5 != 16776959 )
    v7 = a5;
  v8 = a3;
  v33 = 0;
  v32 = v7;
  result = ErrUtilAllocSeg(28 * a3, a1);
  if ( result < 0 )
    return result;
  v10 = Block;
  v11 = 0;
  v12 = a6 | 0x10;
  v34 = 0;
  v13 = (char *)&Block[a3];
  if ( !a3 )
    goto LABEL_27;
  do
  {
    v14 = 16 * v11;
    v31 = 16 * v11;
    v15 = *(_DWORD *)(16 * v11 + a4);
    if ( !v15 )
      v15 = 9;
    *(_DWORD *)(v14 + a4) = v15;
    v29 = 24 * v11;
    *(_DWORD *)&v13[v29] = 24;
    *(_DWORD *)&v13[v29 + 16] = *(_DWORD *)(v14 + a4 + 4);
    v16 = 24 * v11;
    v17 = *(_DWORD *)(v14 + a4 + 8);
    *(_DWORD *)&v13[v29 + 20] = v17;
    v18 = *(_DWORD *)(v14 + a4);
    *(_DWORD *)&v13[v16 + 12] = v32;
    *(_DWORD *)&v13[v16 + 8] = v18;
    v8 = a3;
    if ( *(_DWORD *)(v31 + a4) < 9u )
    {
      v17 |= 1u;
      *(_DWORD *)&v13[v29 + 20] = v17;
    }
    if ( v18 == 10 || v18 == 12 )
    {
      v20 = v18;
      if ( !v32 )
      {
        v20 = 11;
        if ( v18 == 10 )
          v20 = 9;
        *(_DWORD *)&v13[v29 + 8] = v20;
      }
      v18 = v20;
      if ( v20 == 10 )
      {
        v27 = 10;
        *(_DWORD *)&v13[v29 + 20] = v17 | 0x10000;
        goto LABEL_20;
      }
    }
    else if ( v18 == 16 )
    {
      v19 = *(_WORD *)(v31 + a4 + 4);
      *(_WORD *)&v13[v29 + 12] = v19;
      *(_WORD *)&v13[v29 + 14] = *(_WORD *)(v31 + a4 + 6);
      v18 = 16;
      if ( !v19 )
      {
        v27 = 16;
        *(_WORD *)&v13[v29 + 12] = 18;
LABEL_20:
        v18 = v27;
      }
    }
    if ( v18 != 4 )
      v12 &= ~0x10u;
    v21 = v33 + 4;
    if ( v18 != 4 )
      v21 = v33;
    v11 = v34 + 1;
    v33 = v21;
    v34 = v11;
    v6 = v21;
  }
  while ( v11 < a3 );
  v10 = Block;
LABEL_27:
  v28 = v10;
  v22 = v12 & 0xFFFFFFEF;
  if ( v6 <= 8 )
    v22 = v12;
  v23 = ErrIsamOpenTempTable(a1, v13, v8, v22, a2, v28);
  for ( i = 0; i < v8; *(_DWORD *)(a4 + 8 * v26 + 12) = v25 )
  {
    v25 = Block[i];
    v26 = 2 * i++;
  }
  if ( Block )
    _free(Block);
  return v23;
}

```

## disassembly

```asm
0x10088729  mov     edi, edi
0x1008872b  push    ebp
0x1008872c  mov     ebp, esp
0x1008872e  and     esp, 0FFFFFFF8h
0x10088731  sub     esp, 24h
0x10088734  push    ebx
0x10088735  push    esi
0x10088736  xor     esi, esi
0x10088738  mov     [esp+2Ch+var_4], ecx
0x1008873c  cmp     [ebp+arg_8], 0FFFEFFh
0x10088743  mov     eax, 409h
0x10088748  push    edi
0x10088749  cmovnz  eax, [ebp+arg_8]
0x1008874d  mov     edi, [ebp+arg_0]
0x10088750  push    ecx; int
0x10088751  imul    ecx, edi, 1Ch; Size
0x10088754  mov     [esp+34h+var_8], edx
0x10088758  lea     edx, [esp+34h+Block]
0x1008875c  mov     [esp+34h+var_14], esi
0x10088760  mov     [esp+34h+var_18], eax
0x10088764  call    _ErrUtilAllocSeg@12; ErrUtilAllocSeg(x,x,x)
0x10088769  test    eax, eax
0x1008876b  js      loc_100888F9
0x10088771  mov     eax, [esp+30h+Block]
0x10088775  xor     ecx, ecx
0x10088777  mov     edx, [ebp+arg_C]
0x1008877a  or      edx, 10h
0x1008877d  mov     [esp+30h+var_10], ecx
0x10088781  lea     ebx, [eax+edi*4]
0x10088784  test    edi, edi
0x10088786  jz      loc_100888A8
0x1008878c  mov     [esp+30h+var_C], 9
0x10088794  mov     esi, [ebp+arg_4]
0x10088797  mov     edi, ecx
0x10088799  shl     edi, 4
0x1008879c  mov     [esp+30h+var_1C], edi
0x100887a0  mov     eax, [edi+esi]
0x100887a3  test    eax, eax
0x100887a5  cmovz   eax, [esp+30h+var_C]
0x100887aa  mov     [edi+esi], eax
0x100887ad  imul    ecx, 18h
0x100887b0  mov     [esp+30h+var_24], ecx
0x100887b4  mov     dword ptr [ecx+ebx], 18h
0x100887bb  mov     eax, [edi+esi+4]
0x100887bf  mov     [ecx+ebx+10h], eax
0x100887c3  mov     eax, [esp+30h+var_24]
0x100887c7  mov     ecx, [edi+esi+8]
0x100887cb  mov     [eax+ebx+14h], ecx
0x100887cf  mov     esi, [edi+esi]
0x100887d2  mov     edi, [esp+30h+var_18]
0x100887d6  mov     [eax+ebx+0Ch], edi
0x100887da  mov     edi, [ebp+arg_4]
0x100887dd  mov     [eax+ebx+8], esi
0x100887e1  mov     eax, [esp+30h+var_1C]
0x100887e5  cmp     dword ptr [eax+edi], 9
0x100887e9  mov     edi, [ebp+arg_0]
0x100887ec  mov     eax, [esp+30h+var_24]
0x100887f0  jnb     short loc_100887F9
0x100887f2  or      ecx, 1
0x100887f5  mov     [eax+ebx+14h], ecx
0x100887f9  cmp     esi, 0Ah
0x100887fc  jz      short loc_10088844
0x100887fe  cmp     esi, 0Ch
0x10088801  jz      short loc_10088844
0x10088803  cmp     esi, 10h
0x10088806  jnz     short loc_10088878
0x10088808  mov     esi, [ebp+arg_4]
0x1008880b  mov     ecx, [esp+30h+var_1C]
0x1008880f  push    10h
0x10088811  movzx   ecx, word ptr [ecx+esi+4]
0x10088816  mov     [eax+ebx+0Ch], cx
0x1008881b  mov     eax, [esp+34h+var_1C]
0x1008881f  mov     ax, [eax+esi+6]
0x10088824  mov     esi, [esp+34h+var_24]
0x10088828  mov     [esi+ebx+0Eh], ax
0x1008882d  xor     eax, eax
0x1008882f  pop     esi
0x10088830  cmp     ax, cx
0x10088833  jnz     short loc_10088878
0x10088835  mov     eax, [esp+30h+var_24]
0x10088839  push    12h
0x1008883b  pop     ecx
0x1008883c  push    esi
0x1008883d  mov     [eax+ebx+0Ch], cx
0x10088842  jmp     short loc_10088877
0x10088844  cmp     [esp+30h+var_18], 0
0x10088849  mov     eax, esi
0x1008884b  jnz     short loc_10088861
0x1008884d  push    0Bh
0x1008884f  pop     eax
0x10088850  cmp     esi, 0Ah
0x10088853  push    9
0x10088855  pop     esi
0x10088856  cmovz   eax, esi
0x10088859  mov     esi, [esp+30h+var_24]
0x1008885d  mov     [esi+ebx+8], eax
0x10088861  mov     esi, eax
0x10088863  cmp     eax, 0Ah
0x10088866  jnz     short loc_10088878
0x10088868  mov     eax, [esp+30h+var_24]
0x1008886c  or      ecx, 10000h
0x10088872  push    esi
0x10088873  mov     [eax+ebx+14h], ecx
0x10088877  pop     esi
0x10088878  mov     ecx, [esp+30h+var_14]
0x1008887c  mov     eax, edx
0x1008887e  and     eax, 0FFFFFFEFh
0x10088881  cmp     esi, 4
0x10088884  cmovnz  edx, eax
0x10088887  lea     eax, [ecx+4]
0x1008888a  cmovnz  eax, ecx
0x1008888d  mov     ecx, [esp+30h+var_10]
0x10088891  inc     ecx
0x10088892  mov     [esp+30h+var_14], eax
0x10088896  mov     [esp+30h+var_10], ecx
0x1008889a  mov     esi, eax
0x1008889c  cmp     ecx, edi
0x1008889e  jb      loc_10088794
0x100888a4  mov     eax, [esp+30h+Block]
0x100888a8  push    eax
0x100888a9  push    [esp+34h+var_8]
0x100888ad  mov     eax, edx
0x100888af  and     eax, 0FFFFFFEFh
0x100888b2  cmp     esi, 8
0x100888b5  cmovbe  eax, edx
0x100888b8  push    eax
0x100888b9  push    edi
0x100888ba  push    ebx
0x100888bb  push    [esp+44h+var_4]
0x100888bf  call    _ErrIsamOpenTempTable@24; ErrIsamOpenTempTable(x,x,x,x,x,x)
0x100888c4  mov     ebx, eax
0x100888c6  xor     esi, esi
0x100888c8  mov     eax, [esp+30h+Block]
0x100888cc  mov     [esp+30h+var_4], ebx
0x100888d0  test    edi, edi
0x100888d2  jz      short loc_100888EB
0x100888d4  mov     ebx, [ebp+arg_4]
0x100888d7  mov     ecx, [eax+esi*4]
0x100888da  mov     edx, esi
0x100888dc  add     edx, edx
0x100888de  inc     esi
0x100888df  mov     [ebx+edx*8+0Ch], ecx
0x100888e3  cmp     esi, edi
0x100888e5  jb      short loc_100888D7
0x100888e7  mov     ebx, [esp+30h+var_4]
0x100888eb  test    eax, eax
0x100888ed  jz      short loc_100888F7
0x100888ef  push    eax; Block
0x100888f0  call    ds:__imp__free
0x100888f6  pop     ecx
0x100888f7  mov     eax, ebx
0x100888f9  pop     edi
0x100888fa  pop     esi
0x100888fb  pop     ebx
0x100888fc  mov     esp, ebp
0x100888fe  pop     ebp
0x100888ff  retn    10h
```
