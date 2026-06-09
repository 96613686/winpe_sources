# WBTMove(x,x,x,x)

- ea: `0x1002a530`
- end: `0x1002a7bf`
- name: `_WBTMove@16`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1001bc20`
- `0x1002a530`
- `0x1002acaf`
- `0x1002db68`
- `0x10031f44`

## pseudocode

```c
int __stdcall WBTMove(int a1, int a2, int a3, char a4)
{
  int v4; // eax
  int v5; // esi
  int result; // eax
  _DWORD *v7; // ecx
  int v8; // ebx
  int v9; // edi
  int v10; // edi
  unsigned __int8 v11; // al
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  char v16; // dl
  __int16 v17; // ax
  __int16 v18; // ax
  int v19; // edi
  int v20; // eax
  int v21; // ecx
  int v22; // edx
  __int16 v23; // ax
  bool v24; // zf
  __int16 v25; // ax
  int v26; // [esp-Ch] [ebp-20h]
  int v27; // [esp-Ch] [ebp-20h]
  int v28; // [esp+Ch] [ebp-8h]
  int v29; // [esp+10h] [ebp-4h]

  v4 = ISAMDBFindCursor(a1, a2);
  v5 = v4;
  if ( !v4 )
    return -1310;
  v29 = *(_DWORD *)(v4 + 4);
  *(_DWORD *)(v29 + 80) = 0;
  v7 = *(_DWORD **)(v4 + 4);
  if ( v7[14] == 1 )
  {
    result = CreateTableWithColumns(v7, v4);
    if ( result )
      return result;
  }
  v8 = a3;
  if ( a3 == 1 )
  {
    v9 = (a4 & 1) != 0 ? 6 : 0;
    goto LABEL_19;
  }
  if ( a3 != -1 )
  {
    if ( a3 == 0x80000000 )
    {
      v26 = 2;
    }
    else
    {
      if ( a3 != 0x7FFFFFFF )
      {
        v10 = 4 * (a4 & 1);
        if ( a3 >= 0 )
          v9 = v10 + 4;
        else
          v9 = v10 + 5;
        goto LABEL_19;
      }
      v26 = 3;
    }
    v9 = v26;
    goto LABEL_19;
  }
  v9 = 1;
  if ( (a4 & 1) != 0 )
    v9 = 7;
LABEL_19:
  if ( (a4 & 1) != 0 )
    return -1515;
  if ( *(_DWORD *)(v5 + 48) )
    CopyBufferClear((_DWORD *)v5);
  v11 = *(_BYTE *)(v5 + 29);
  if ( !a3 )
  {
    if ( v11 != 2 )
      return -1603;
    return 0;
  }
  v12 = (unsigned __int8)byte_100055D4[4 * v9 + v11] - 1;
  if ( !v12 )
  {
    v27 = 2;
    goto LABEL_43;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v27 = 3;
LABEL_43:
    v9 = v27;
LABEL_44:
    WorkbookRangeRange(v29 + 96);
    if ( v9 != 2 )
    {
      v16 = 2;
      *(_WORD *)(v5 + 30) = *(_WORD *)(v29 + 100) - *(_WORD *)(v29 + 96);
      if ( *(_DWORD *)(v29 + 44) == 1 )
        v16 = *(_WORD *)(v29 + 96) != *(_WORD *)(v29 + 100) ? 2 : 0;
      goto LABEL_48;
    }
    *(_WORD *)(v5 + 30) = 0;
    v16 = 2;
    if ( *(_DWORD *)(v29 + 44) != 1 )
    {
LABEL_48:
      *(_BYTE *)(v5 + 29) = v16;
      result = -1603;
      if ( v16 == 2 )
        return 0;
      return result;
    }
    if ( *(unsigned __int16 *)(v29 + 100) != *(unsigned __int16 *)(v29 + 96) )
    {
      *(_WORD *)(v5 + 30) = 1;
      goto LABEL_48;
    }
    goto LABEL_54;
  }
  v14 = v13 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 == 1 )
        return -1603;
    }
    else
    {
      v8 = a3 + 1;
    }
  }
  else
  {
    v8 = a3 - 1;
  }
  if ( v9 == 2 || v9 == 3 )
    goto LABEL_44;
  if ( v9 == 1 )
  {
    v16 = 2;
    v17 = *(_WORD *)(v5 + 30);
    if ( *(_DWORD *)(v29 + 44) == 1 )
    {
      if ( v17 != 1 )
      {
LABEL_40:
        v18 = v17 - 1;
LABEL_58:
        *(_WORD *)(v5 + 30) = v18;
        goto LABEL_48;
      }
    }
    else if ( v17 )
    {
      goto LABEL_40;
    }
LABEL_54:
    *(_BYTE *)(v5 + 29) = 0;
    return -1603;
  }
  if ( v9 )
  {
    v20 = abs32(v8);
    if ( !v20 )
      return 0;
    v21 = 0;
    v16 = 2;
    v28 = 0;
    if ( v20 > 0 )
    {
      v22 = v20;
      while ( 1 )
      {
        if ( v9 == 5 )
        {
          v23 = *(_WORD *)(v5 + 30);
          if ( *(_DWORD *)(v29 + 44) == 1 )
            v24 = v23 == 1;
          else
            v24 = v23 == 0;
          if ( v24 )
          {
            *(_BYTE *)(v5 + 29) = 0;
            return -1603;
          }
          v25 = v23 - 1;
        }
        else
        {
          if ( *(unsigned __int16 *)(v5 + 30) == *(unsigned __int16 *)(v29 + 100) - *(unsigned __int16 *)(v29 + 96) )
            goto LABEL_73;
          v21 = v28;
          v25 = *(_WORD *)(v5 + 30) + 1;
        }
        ++v21;
        *(_WORD *)(v5 + 30) = v25;
        v28 = v21;
        if ( v21 >= v22 )
        {
          *(_BYTE *)(v5 + 29) = 2;
          return 0;
        }
      }
    }
    goto LABEL_48;
  }
  v16 = 2;
  v19 = *(unsigned __int16 *)(v5 + 30);
  if ( v19 != *(unsigned __int16 *)(v29 + 100) - *(unsigned __int16 *)(v29 + 96) )
  {
    v18 = v19 + 1;
    goto LABEL_58;
  }
LABEL_73:
  *(_BYTE *)(v5 + 29) = 1;
  return -1603;
}

```

## disassembly

```asm
0x1002a530  mov     edi, edi
0x1002a532  push    ebp
0x1002a533  mov     ebp, esp
0x1002a535  mov     edx, [ebp+arg_4]
0x1002a538  sub     esp, 10h
0x1002a53b  mov     ecx, [ebp+arg_0]
0x1002a53e  push    esi
0x1002a53f  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002a544  mov     esi, eax
0x1002a546  test    esi, esi
0x1002a548  jnz     short loc_1002A554
0x1002a54a  mov     eax, 0FFFFFAE2h
0x1002a54f  jmp     loc_1002A605
0x1002a554  mov     eax, [esi+4]
0x1002a557  xor     edx, edx
0x1002a559  inc     edx
0x1002a55a  mov     [ebp+var_4], eax
0x1002a55d  mov     [ebp+var_10], edx
0x1002a560  mov     dword ptr [eax+50h], 0
0x1002a567  mov     ecx, [esi+4]
0x1002a56a  cmp     [ecx+38h], edx
0x1002a56d  jnz     short loc_1002A581
0x1002a56f  mov     edx, esi
0x1002a571  call    _CreateTableWithColumns@8; CreateTableWithColumns(x,x)
0x1002a576  test    eax, eax
0x1002a578  jnz     loc_1002A605
0x1002a57e  xor     edx, edx
0x1002a580  inc     edx
0x1002a581  mov     ecx, [ebp+arg_C]
0x1002a584  push    ebx
0x1002a585  mov     ebx, [ebp+arg_8]
0x1002a588  push    edi
0x1002a589  cmp     ebx, edx
0x1002a58b  jnz     short loc_1002A59D
0x1002a58d  mov     eax, ecx
0x1002a58f  and     al, dl
0x1002a591  movzx   edi, al
0x1002a594  neg     edi
0x1002a596  sbb     edi, edi
0x1002a598  and     edi, 6
0x1002a59b  jmp     short loc_1002A5DA
0x1002a59d  cmp     ebx, 0FFFFFFFFh
0x1002a5a0  jnz     short loc_1002A5AE
0x1002a5a2  push    7
0x1002a5a4  test    dl, cl
0x1002a5a6  mov     edi, edx
0x1002a5a8  pop     eax
0x1002a5a9  cmovnz  edi, eax
0x1002a5ac  jmp     short loc_1002A5DA
0x1002a5ae  cmp     ebx, 80000000h
0x1002a5b4  jnz     short loc_1002A5BA
0x1002a5b6  push    2
0x1002a5b8  jmp     short loc_1002A5C4
0x1002a5ba  cmp     ebx, 7FFFFFFFh
0x1002a5c0  jnz     short loc_1002A5C7
0x1002a5c2  push    3
0x1002a5c4  pop     edi
0x1002a5c5  jmp     short loc_1002A5DA
0x1002a5c7  mov     edi, ecx
0x1002a5c9  and     edi, edx
0x1002a5cb  shl     edi, 2
0x1002a5ce  test    ebx, ebx
0x1002a5d0  jns     short loc_1002A5D7
0x1002a5d2  add     edi, 5
0x1002a5d5  jmp     short loc_1002A5DA
0x1002a5d7  add     edi, 4
0x1002a5da  test    dl, cl
0x1002a5dc  jz      short loc_1002A5E5
0x1002a5de  mov     eax, 0FFFFFA15h
0x1002a5e3  jmp     short loc_1002A603
0x1002a5e5  cmp     dword ptr [esi+30h], 0
0x1002a5e9  jz      short loc_1002A5F2
0x1002a5eb  mov     ecx, esi
0x1002a5ed  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002a5f2  mov     al, [esi+1Dh]
0x1002a5f5  test    ebx, ebx
0x1002a5f7  jnz     short loc_1002A60A
0x1002a5f9  cmp     al, 2
0x1002a5fb  jnz     loc_1002A7B5
0x1002a601  xor     eax, eax
0x1002a603  pop     edi
0x1002a604  pop     ebx
0x1002a605  pop     esi
0x1002a606  leave
0x1002a607  retn    10h
0x1002a60a  movzx   eax, al
0x1002a60d  movzx   eax, ds:byte_100055D4[eax+edi*4]
0x1002a615  sub     eax, 1
0x1002a618  jz      short loc_1002A676
0x1002a61a  sub     eax, 1
0x1002a61d  jz      short loc_1002A672
0x1002a61f  sub     eax, 1
0x1002a622  jz      short loc_1002A637
0x1002a624  sub     eax, 1
0x1002a627  jz      short loc_1002A634
0x1002a629  sub     eax, 1
0x1002a62c  jz      loc_1002A7B5
0x1002a632  jmp     short loc_1002A638
0x1002a634  inc     ebx
0x1002a635  jmp     short loc_1002A638
0x1002a637  dec     ebx
0x1002a638  mov     ecx, ebx
0x1002a63a  mov     eax, edi
0x1002a63c  cmp     edi, 2
0x1002a63f  jz      short loc_1002A679
0x1002a641  cmp     eax, 3
0x1002a644  jz      short loc_1002A679
0x1002a646  xor     ecx, ecx
0x1002a648  inc     ecx
0x1002a649  cmp     edi, ecx
0x1002a64b  jnz     loc_1002A70D
0x1002a651  mov     ebx, [ebp+var_4]
0x1002a654  mov     dl, 2
0x1002a656  movzx   eax, word ptr [esi+1Eh]
0x1002a65a  cmp     [ebx+2Ch], ecx
0x1002a65d  jnz     loc_1002A6FA
0x1002a663  cmp     ax, cx
0x1002a666  jz      loc_1002A703
0x1002a66c  dec     eax
0x1002a66d  jmp     loc_1002A72F
0x1002a672  push    3
0x1002a674  jmp     short loc_1002A678
0x1002a676  push    2
0x1002a678  pop     edi
0x1002a679  mov     ecx, [ebp+var_4]
0x1002a67c  mov     edx, [ecx+10h]
0x1002a67f  lea     eax, [ecx+60h]
0x1002a682  mov     ecx, [ecx+0Ch]
0x1002a685  push    eax
0x1002a686  call    _WorkbookRangeRange@12; WorkbookRangeRange(x,x,x)
0x1002a68b  cmp     edi, 2
0x1002a68e  jnz     short loc_1002A6C8
0x1002a690  xor     eax, eax
0x1002a692  xor     ebx, ebx
0x1002a694  mov     [esi+1Eh], ax
0x1002a698  inc     ebx
0x1002a699  mov     eax, [ebp+var_4]
0x1002a69c  mov     dl, 2
0x1002a69e  cmp     [eax+2Ch], ebx
0x1002a6a1  jnz     short loc_1002A6B3
0x1002a6a3  movzx   ecx, word ptr [eax+64h]
0x1002a6a7  movzx   eax, word ptr [eax+60h]
0x1002a6ab  sub     ecx, eax
0x1002a6ad  jz      short loc_1002A703
0x1002a6af  mov     [esi+1Eh], bx
0x1002a6b3  xor     ecx, ecx
0x1002a6b5  mov     [esi+1Dh], dl
0x1002a6b8  cmp     dl, 2
0x1002a6bb  mov     eax, 0FFFFF9BDh
0x1002a6c0  cmovz   eax, ecx
0x1002a6c3  jmp     loc_1002A603
0x1002a6c8  cmp     edi, 3
0x1002a6cb  jnz     loc_1002A646
0x1002a6d1  mov     ecx, [ebp+var_4]
0x1002a6d4  mov     dl, 2
0x1002a6d6  mov     ax, [ecx+64h]
0x1002a6da  sub     ax, [ecx+60h]
0x1002a6de  mov     [esi+1Eh], ax
0x1002a6e2  cmp     dword ptr [ecx+2Ch], 1
0x1002a6e6  jnz     short loc_1002A6B3
0x1002a6e8  mov     dx, [ecx+64h]
0x1002a6ec  sub     dx, [ecx+60h]
0x1002a6f0  neg     dx
0x1002a6f3  sbb     dl, dl
0x1002a6f5  and     dl, 2
0x1002a6f8  jmp     short loc_1002A6B3
0x1002a6fa  test    ax, ax
0x1002a6fd  jnz     loc_1002A66C
0x1002a703  xor     al, al
0x1002a705  mov     [esi+1Dh], al
0x1002a708  jmp     loc_1002A7B5
0x1002a70d  test    edi, edi
0x1002a70f  jnz     short loc_1002A738
0x1002a711  mov     ebx, [ebp+var_4]
0x1002a714  mov     dl, 2
0x1002a716  movzx   edi, word ptr [esi+1Eh]
0x1002a71a  movzx   ecx, word ptr [ebx+64h]
0x1002a71e  movzx   eax, word ptr [ebx+60h]
0x1002a722  sub     ecx, eax
0x1002a724  cmp     edi, ecx
0x1002a726  jz      loc_1002A7B1
0x1002a72c  lea     eax, [edi+1]
0x1002a72f  mov     [esi+1Eh], ax
0x1002a733  jmp     loc_1002A6B3
0x1002a738  mov     eax, ebx
0x1002a73a  cdq
0x1002a73b  xor     eax, edx
0x1002a73d  sub     eax, edx
0x1002a73f  mov     [ebp+var_C], eax
0x1002a742  jz      loc_1002A601
0x1002a748  xor     ecx, ecx
0x1002a74a  mov     dl, 2
0x1002a74c  mov     [ebp+var_8], ecx
0x1002a74f  test    eax, eax
0x1002a751  jle     loc_1002A6B3
0x1002a757  mov     ebx, [ebp+var_4]
0x1002a75a  mov     edx, eax
0x1002a75c  cmp     edi, 5
0x1002a75f  jnz     short loc_1002A779
0x1002a761  cmp     dword ptr [ebx+2Ch], 1
0x1002a765  movzx   eax, word ptr [esi+1Eh]
0x1002a769  jnz     short loc_1002A771
0x1002a76b  cmp     ax, word ptr [ebp+var_10]
0x1002a76f  jmp     short loc_1002A774
0x1002a771  test    ax, ax
0x1002a774  jz      short loc_1002A7AB
0x1002a776  dec     eax
0x1002a777  jmp     short loc_1002A793
0x1002a779  movzx   eax, word ptr [ebx+60h]
0x1002a77d  movzx   ecx, word ptr [ebx+64h]
0x1002a781  sub     ecx, eax
0x1002a783  movzx   eax, word ptr [esi+1Eh]
0x1002a787  cmp     eax, ecx
0x1002a789  jz      short loc_1002A7B1
0x1002a78b  movzx   eax, word ptr [esi+1Eh]
0x1002a78f  mov     ecx, [ebp+var_8]
0x1002a792  inc     eax
0x1002a793  inc     ecx
0x1002a794  movzx   eax, ax
0x1002a797  mov     [esi+1Eh], ax
0x1002a79b  mov     [ebp+var_8], ecx
0x1002a79e  cmp     ecx, edx
0x1002a7a0  jl      short loc_1002A75C
0x1002a7a2  mov     byte ptr [esi+1Dh], 2
0x1002a7a6  jmp     loc_1002A601
0x1002a7ab  mov     byte ptr [esi+1Dh], 0
0x1002a7af  jmp     short loc_1002A7B5
0x1002a7b1  mov     byte ptr [esi+1Dh], 1
0x1002a7b5  mov     eax, 0FFFFF9BDh
0x1002a7ba  jmp     loc_1002A603
```
