# ErrOldOpenTempTable(x,x,x,x,x,x)

- ea: `0x10088599`
- end: `0x10088772`
- name: `_ErrOldOpenTempTable@24`
- size: `473`
- prototype: `int __thiscall(int, int, int, int, int)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x1008934e`
- `0x1008d0af`
- `0x10098400`
- `0x1009b1a2`
- `0x1009cc3b`
- `0x100a12a0`
- `0x100a2042`
- `0x100a4a22`
- `0x100c1680`
- `0x100db08a`
- `0x100f8e4a`
- `0x100f9190`
- `0x100fa58e`
- `0x10108750`
- `0x1010a0d2`
- `0x1010ac6e`

## callees

- `0x10045f7b`
- `0x1004c9a0`
- `0x10088599`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10088760`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10088760`

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
0x10088599  mov     edi, edi
0x1008859b  push    ebp
0x1008859c  mov     ebp, esp
0x1008859e  and     esp, 0FFFFFFF8h
0x100885a1  sub     esp, 24h
0x100885a4  push    ebx
0x100885a5  push    esi
0x100885a6  xor     esi, esi
0x100885a8  mov     [esp+2Ch+var_4], ecx
0x100885ac  cmp     [ebp+arg_8], 0FFFEFFh
0x100885b3  mov     eax, 409h
0x100885b8  push    edi
0x100885b9  cmovnz  eax, [ebp+arg_8]
0x100885bd  mov     edi, [ebp+arg_0]
0x100885c0  push    ecx; int
0x100885c1  imul    ecx, edi, 1Ch; Size
0x100885c4  mov     [esp+34h+var_8], edx
0x100885c8  lea     edx, [esp+34h+Block]
0x100885cc  mov     [esp+34h+var_14], esi
0x100885d0  mov     [esp+34h+var_18], eax
0x100885d4  call    _ErrUtilAllocSeg@12; ErrUtilAllocSeg(x,x,x)
0x100885d9  test    eax, eax
0x100885db  js      loc_10088769
0x100885e1  mov     eax, [esp+30h+Block]
0x100885e5  xor     ecx, ecx
0x100885e7  mov     edx, [ebp+arg_C]
0x100885ea  or      edx, 10h
0x100885ed  mov     [esp+30h+var_10], ecx
0x100885f1  lea     ebx, [eax+edi*4]
0x100885f4  test    edi, edi
0x100885f6  jz      loc_10088718
0x100885fc  mov     [esp+30h+var_C], 9
0x10088604  mov     esi, [ebp+arg_4]
0x10088607  mov     edi, ecx
0x10088609  shl     edi, 4
0x1008860c  mov     [esp+30h+var_1C], edi
0x10088610  mov     eax, [edi+esi]
0x10088613  test    eax, eax
0x10088615  cmovz   eax, [esp+30h+var_C]
0x1008861a  mov     [edi+esi], eax
0x1008861d  imul    ecx, 18h
0x10088620  mov     [esp+30h+var_24], ecx
0x10088624  mov     dword ptr [ecx+ebx], 18h
0x1008862b  mov     eax, [edi+esi+4]
0x1008862f  mov     [ecx+ebx+10h], eax
0x10088633  mov     eax, [esp+30h+var_24]
0x10088637  mov     ecx, [edi+esi+8]
0x1008863b  mov     [eax+ebx+14h], ecx
0x1008863f  mov     esi, [edi+esi]
0x10088642  mov     edi, [esp+30h+var_18]
0x10088646  mov     [eax+ebx+0Ch], edi
0x1008864a  mov     edi, [ebp+arg_4]
0x1008864d  mov     [eax+ebx+8], esi
0x10088651  mov     eax, [esp+30h+var_1C]
0x10088655  cmp     dword ptr [eax+edi], 9
0x10088659  mov     edi, [ebp+arg_0]
0x1008865c  mov     eax, [esp+30h+var_24]
0x10088660  jnb     short loc_10088669
0x10088662  or      ecx, 1
0x10088665  mov     [eax+ebx+14h], ecx
0x10088669  cmp     esi, 0Ah
0x1008866c  jz      short loc_100886B4
0x1008866e  cmp     esi, 0Ch
0x10088671  jz      short loc_100886B4
0x10088673  cmp     esi, 10h
0x10088676  jnz     short loc_100886E8
0x10088678  mov     esi, [ebp+arg_4]
0x1008867b  mov     ecx, [esp+30h+var_1C]
0x1008867f  push    10h
0x10088681  movzx   ecx, word ptr [ecx+esi+4]
0x10088686  mov     [eax+ebx+0Ch], cx
0x1008868b  mov     eax, [esp+34h+var_1C]
0x1008868f  mov     ax, [eax+esi+6]
0x10088694  mov     esi, [esp+34h+var_24]
0x10088698  mov     [esi+ebx+0Eh], ax
0x1008869d  xor     eax, eax
0x1008869f  pop     esi
0x100886a0  cmp     ax, cx
0x100886a3  jnz     short loc_100886E8
0x100886a5  mov     eax, [esp+30h+var_24]
0x100886a9  push    12h
0x100886ab  pop     ecx
0x100886ac  push    esi
0x100886ad  mov     [eax+ebx+0Ch], cx
0x100886b2  jmp     short loc_100886E7
0x100886b4  cmp     [esp+30h+var_18], 0
0x100886b9  mov     eax, esi
0x100886bb  jnz     short loc_100886D1
0x100886bd  push    0Bh
0x100886bf  pop     eax
0x100886c0  cmp     esi, 0Ah
0x100886c3  push    9
0x100886c5  pop     esi
0x100886c6  cmovz   eax, esi
0x100886c9  mov     esi, [esp+30h+var_24]
0x100886cd  mov     [esi+ebx+8], eax
0x100886d1  mov     esi, eax
0x100886d3  cmp     eax, 0Ah
0x100886d6  jnz     short loc_100886E8
0x100886d8  mov     eax, [esp+30h+var_24]
0x100886dc  or      ecx, 10000h
0x100886e2  push    esi
0x100886e3  mov     [eax+ebx+14h], ecx
0x100886e7  pop     esi
0x100886e8  mov     ecx, [esp+30h+var_14]
0x100886ec  mov     eax, edx
0x100886ee  and     eax, 0FFFFFFEFh
0x100886f1  cmp     esi, 4
0x100886f4  cmovnz  edx, eax
0x100886f7  lea     eax, [ecx+4]
0x100886fa  cmovnz  eax, ecx
0x100886fd  mov     ecx, [esp+30h+var_10]
0x10088701  inc     ecx
0x10088702  mov     [esp+30h+var_14], eax
0x10088706  mov     [esp+30h+var_10], ecx
0x1008870a  mov     esi, eax
0x1008870c  cmp     ecx, edi
0x1008870e  jb      loc_10088604
0x10088714  mov     eax, [esp+30h+Block]
0x10088718  push    eax
0x10088719  push    [esp+34h+var_8]
0x1008871d  mov     eax, edx
0x1008871f  and     eax, 0FFFFFFEFh
0x10088722  cmp     esi, 8
0x10088725  cmovbe  eax, edx
0x10088728  push    eax
0x10088729  push    edi
0x1008872a  push    ebx
0x1008872b  push    [esp+44h+var_4]
0x1008872f  call    _ErrIsamOpenTempTable@24; ErrIsamOpenTempTable(x,x,x,x,x,x)
0x10088734  mov     ebx, eax
0x10088736  xor     esi, esi
0x10088738  mov     eax, [esp+30h+Block]
0x1008873c  mov     [esp+30h+var_4], ebx
0x10088740  test    edi, edi
0x10088742  jz      short loc_1008875B
0x10088744  mov     ebx, [ebp+arg_4]
0x10088747  mov     ecx, [eax+esi*4]
0x1008874a  mov     edx, esi
0x1008874c  add     edx, edx
0x1008874e  inc     esi
0x1008874f  mov     [ebx+edx*8+0Ch], ecx
0x10088753  cmp     esi, edi
0x10088755  jb      short loc_10088747
0x10088757  mov     ebx, [esp+30h+var_4]
0x1008875b  test    eax, eax
0x1008875d  jz      short loc_10088767
0x1008875f  push    eax; Block
0x10088760  call    ds:__imp__free
0x10088766  pop     ecx
0x10088767  mov     eax, ebx
0x10088769  pop     edi
0x1008876a  pop     esi
0x1008876b  pop     ebx
0x1008876c  mov     esp, ebp
0x1008876e  pop     ebp
0x1008876f  retn    10h
```
