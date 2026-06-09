# OpenWorkbookStream

- ea: `0x10011010`
- end: `0x1001126e`
- name: `OpenWorkbookStream`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10011280`

## callees

- `0x1000dcc0`
- `0x10011010`
- `0x10025f86`
- `0x10026030`
- `0x100260bc`

## pseudocode

```c
int __fastcall OpenWorkbookStream(int a1, int a2)
{
  int result; // eax
  int v5; // ecx
  int v6; // ecx
  int *v7; // ecx
  __int16 v8; // [esp+Ch] [ebp-4h] BYREF
  __int16 v9; // [esp+Eh] [ebp-2h]

  result = BFOpenStream(a2);
  if ( result )
  {
    if ( result == -9 )
      return BFOpenStream(a2);
  }
  else
  {
    BFCloseStream(*(_DWORD *)(a1 + 20));
    result = BFOpenStream(a2);
    if ( result )
    {
      if ( result == -9 )
      {
        *(_DWORD *)(a1 + 48) = 0;
        return BFOpenStream(a2);
      }
    }
    else
    {
      if ( ExcelReadRecordHeader(a1, &v8) || v8 != 9 && v8 != 521 && v8 != 1033 && v8 != 2057 )
        goto LABEL_36;
      v5 = *(_DWORD *)(a1 + 40);
      if ( v5 )
        *(_DWORD *)(v5 + 8) = **(_DWORD **)(v5 + 8);
      else
        BFSetFilePosition(*(int **)(a1 + 20), 1, v9);
      if ( !ExcelReadRecordHeader(a1, &v8) )
      {
        while ( v8 != 354 )
        {
          if ( v8 == 10
            || v8 == 516
            || v8 == 638
            || v8 == 515
            || v8 == 189
            || v8 == 190
            || v8 == 513
            || v8 == 517
            || v8 == 214
            || v8 == 253
            || v8 == 518
            || v8 == 1030
            || v8 == 6
            || v8 == 519
            || v8 == 545
            || v8 == 1212 )
          {
            v7 = *(int **)(a1 + 20);
            *(_DWORD *)(a1 + 48) = 0;
            BFSetFilePosition(v7, 0, 0);
            return 0;
          }
          v6 = *(_DWORD *)(a1 + 40);
          if ( v6 )
            *(_DWORD *)(v6 + 8) = **(_DWORD **)(v6 + 8);
          else
            BFSetFilePosition(*(int **)(a1 + 20), 1, v9);
          if ( ExcelReadRecordHeader(a1, &v8) )
            goto LABEL_36;
        }
        BFCloseStream(*(_DWORD *)(a1 + 20));
        *(_DWORD *)(a1 + 48) = 1;
        return BFOpenStream(a2);
      }
      else
      {
LABEL_36:
        BFCloseStream(*(_DWORD *)(a1 + 20));
        return -10;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10011010  mov     edi, edi
0x10011012  push    ebp
0x10011013  mov     ebp, esp
0x10011015  push    ecx
0x10011016  push    ebx
0x10011017  push    esi
0x10011018  mov     esi, ecx
0x1001101a  push    edi
0x1001101b  mov     edi, edx
0x1001101d  mov     edx, offset aWorkbook; "Workbook"
0x10011022  push    edi
0x10011023  mov     ecx, [esi+14h]
0x10011026  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x1001102b  test    eax, eax
0x1001102d  jnz     loc_10011254
0x10011033  mov     ecx, [esi+14h]
0x10011036  call    _BFCloseStream@4; BFCloseStream(x)
0x1001103b  mov     ecx, [esi+14h]
0x1001103e  mov     edx, offset aBook; "Book"
0x10011043  push    edi
0x10011044  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x10011049  test    eax, eax
0x1001104b  jz      short loc_10011070
0x1001104d  cmp     eax, 0FFFFFFF7h
0x10011050  jnz     loc_10011267
0x10011056  xor     eax, eax
0x10011058  mov     edx, offset aWorkbook; "Workbook"
0x1001105d  mov     [esi+30h], eax
0x10011060  mov     ecx, [esi+14h]
0x10011063  push    edi
0x10011064  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x10011069  pop     edi
0x1001106a  pop     esi
0x1001106b  pop     ebx
0x1001106c  mov     esp, ebp
0x1001106e  pop     ebp
0x1001106f  retn
0x10011070  lea     edx, [ebp+var_4]
0x10011073  mov     ecx, esi
0x10011075  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x1001107a  test    eax, eax
0x1001107c  jz      short loc_10011092
0x1001107e  mov     ecx, [esi+14h]
0x10011081  call    _BFCloseStream@4; BFCloseStream(x)
0x10011086  mov     eax, 0FFFFFFF6h
0x1001108b  pop     edi
0x1001108c  pop     esi
0x1001108d  pop     ebx
0x1001108e  mov     esp, ebp
0x10011090  pop     ebp
0x10011091  retn
0x10011092  mov     eax, [ebp+var_4]
0x10011095  cmp     ax, 9
0x10011099  jz      short loc_100110B9
0x1001109b  mov     ecx, 209h
0x100110a0  cmp     ax, cx
0x100110a3  jz      short loc_100110B9
0x100110a5  mov     ecx, 409h
0x100110aa  cmp     ax, cx
0x100110ad  jz      short loc_100110B9
0x100110af  mov     ecx, 809h
0x100110b4  cmp     ax, cx
0x100110b7  jnz     short loc_1001107E
0x100110b9  mov     ecx, [esi+28h]
0x100110bc  test    ecx, ecx
0x100110be  jz      short loc_100110CA
0x100110c0  mov     eax, [ecx+8]
0x100110c3  mov     eax, [eax]
0x100110c5  mov     [ecx+8], eax
0x100110c8  jmp     short loc_100110DC
0x100110ca  movsx   eax, word ptr [ebp+var_4+2]
0x100110ce  mov     edx, 1
0x100110d3  mov     ecx, [esi+14h]
0x100110d6  push    eax
0x100110d7  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x100110dc  lea     edx, [ebp+var_4]
0x100110df  mov     ecx, esi
0x100110e1  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x100110e6  test    eax, eax
0x100110e8  jnz     short loc_1001107E
0x100110ea  mov     ecx, 204h
0x100110ef  mov     ebx, 162h
0x100110f4  lea     edx, [ecx+7Ah]
0x100110f7  nop     word ptr [eax+eax+00000000h]
0x10011100  mov     eax, [ebp+var_4]
0x10011103  cmp     ax, bx
0x10011106  jz      loc_1001122F
0x1001110c  cmp     ax, 0Ah
0x10011110  jz      loc_10011213
0x10011116  cmp     ax, cx
0x10011119  jz      loc_10011213
0x1001111f  cmp     ax, dx
0x10011122  jz      loc_10011213
0x10011128  mov     ecx, 203h
0x1001112d  cmp     ax, cx
0x10011130  jz      loc_10011213
0x10011136  mov     ecx, 0BDh
0x1001113b  cmp     ax, cx
0x1001113e  jz      loc_10011213
0x10011144  mov     ecx, 0BEh
0x10011149  cmp     ax, cx
0x1001114c  jz      loc_10011213
0x10011152  mov     ecx, 201h
0x10011157  cmp     ax, cx
0x1001115a  jz      loc_10011213
0x10011160  mov     ecx, 205h
0x10011165  cmp     ax, cx
0x10011168  jz      loc_10011213
0x1001116e  mov     ecx, 0D6h
0x10011173  cmp     ax, cx
0x10011176  jz      loc_10011213
0x1001117c  mov     ecx, 0FDh
0x10011181  cmp     ax, cx
0x10011184  jz      loc_10011213
0x1001118a  mov     ecx, 206h
0x1001118f  cmp     ax, cx
0x10011192  jz      short loc_10011213
0x10011194  mov     ecx, 406h
0x10011199  cmp     ax, cx
0x1001119c  jz      short loc_10011213
0x1001119e  cmp     ax, 6
0x100111a2  jz      short loc_10011213
0x100111a4  mov     ecx, 207h
0x100111a9  cmp     ax, cx
0x100111ac  jz      short loc_10011213
0x100111ae  mov     ecx, 221h
0x100111b3  cmp     ax, cx
0x100111b6  jz      short loc_10011213
0x100111b8  mov     ecx, 4BCh
0x100111bd  cmp     ax, cx
0x100111c0  jz      short loc_10011213
0x100111c2  mov     ecx, [esi+28h]
0x100111c5  test    ecx, ecx
0x100111c7  jz      short loc_100111D3
0x100111c9  mov     eax, [ecx+8]
0x100111cc  mov     eax, [eax]
0x100111ce  mov     [ecx+8], eax
0x100111d1  jmp     short loc_100111E5
0x100111d3  movsx   eax, word ptr [ebp+var_4+2]
0x100111d7  mov     edx, 1
0x100111dc  mov     ecx, [esi+14h]
0x100111df  push    eax
0x100111e0  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x100111e5  lea     edx, [ebp+var_4]
0x100111e8  mov     ecx, esi
0x100111ea  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x100111ef  mov     ecx, 204h
0x100111f4  lea     edx, [ecx+7Ah]
0x100111f7  test    eax, eax
0x100111f9  jz      loc_10011100
0x100111ff  mov     ecx, [esi+14h]
0x10011202  call    _BFCloseStream@4; BFCloseStream(x)
0x10011207  mov     eax, 0FFFFFFF6h
0x1001120c  pop     edi
0x1001120d  pop     esi
0x1001120e  pop     ebx
0x1001120f  mov     esp, ebp
0x10011211  pop     ebp
0x10011212  retn
0x10011213  mov     ecx, [esi+14h]
0x10011216  xor     edx, edx
0x10011218  push    0
0x1001121a  mov     dword ptr [esi+30h], 0
0x10011221  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10011226  xor     eax, eax
0x10011228  pop     edi
0x10011229  pop     esi
0x1001122a  pop     ebx
0x1001122b  mov     esp, ebp
0x1001122d  pop     ebp
0x1001122e  retn
0x1001122f  mov     ecx, [esi+14h]
0x10011232  call    _BFCloseStream@4; BFCloseStream(x)
0x10011237  mov     eax, 1
0x1001123c  mov     edx, offset aWorkbook; "Workbook"
0x10011241  mov     [esi+30h], eax
0x10011244  mov     ecx, [esi+14h]
0x10011247  push    edi
0x10011248  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x1001124d  pop     edi
0x1001124e  pop     esi
0x1001124f  pop     ebx
0x10011250  mov     esp, ebp
0x10011252  pop     ebp
0x10011253  retn
0x10011254  cmp     eax, 0FFFFFFF7h
0x10011257  jnz     short loc_10011267
0x10011259  mov     ecx, [esi+14h]
0x1001125c  mov     edx, offset aBook; "Book"
0x10011261  push    edi
0x10011262  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x10011267  pop     edi
0x10011268  pop     esi
0x10011269  pop     ebx
0x1001126a  mov     esp, ebp
0x1001126c  pop     ebp
0x1001126d  retn
```
