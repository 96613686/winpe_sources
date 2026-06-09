# WriteStringPool

- ea: `0x1000d590`
- end: `0x1000d753`
- name: `WriteStringPool`
- size: `451`
- prototype: `int __fastcall(int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1000d760`

## callees

- `0x1000bfc0`
- `0x1000cf40`
- `0x1000cfd0`
- `0x1000d030`
- `0x1000d590`
- `0x1002580a`
- `0x10025ab7`

## pseudocode

```c
int __fastcall WriteStringPool(int a1, int a2)
{
  int v2; // edi
  int i; // esi
  _DWORD *j; // eax
  int FirstTextCell; // edi
  int v6; // ecx
  int v7; // ebx
  int v8; // esi
  _DWORD *v9; // edx
  int v10; // eax
  int v11; // ecx
  int TextCell; // eax
  _DWORD *v13; // eax
  int v14; // esi
  _WORD *v15; // ebx
  bool v17; // cc
  int v18; // edi
  _DWORD *k; // ebx
  int v20; // esi
  int v21; // esi
  int v22; // edi
  int v23; // [esp-Ch] [ebp-3Ch]
  int v24; // [esp-8h] [ebp-38h]
  _BYTE v25[12]; // [esp+Ch] [ebp-24h] BYREF
  _DWORD *v26; // [esp+18h] [ebp-18h]
  int v27; // [esp+1Ch] [ebp-14h]
  _WORD *v28; // [esp+20h] [ebp-10h]
  int v29; // [esp+24h] [ebp-Ch]
  int v30; // [esp+28h] [ebp-8h]
  int v31; // [esp+2Ch] [ebp-4h] BYREF

  v27 = a1;
  v29 = a2;
  v2 = *(_DWORD *)(a2 + 40);
  if ( v2 )
  {
    for ( i = 2; i != 523; ++i )
    {
      for ( j = *(_DWORD **)(v2 + 4 * i); j; j = (_DWORD *)*j )
        j[2] = -1;
    }
  }
  FirstTextCell = FindFirstTextCell(a2, v25);
  v6 = 0;
  v7 = 0;
  v30 = 0;
  v8 = 0;
  if ( FirstTextCell )
  {
    v9 = v26;
    while ( 1 )
    {
      v10 = *(_DWORD *)(FirstTextCell + 8);
      if ( v10 && v10 != -1 )
      {
        v11 = *(_DWORD *)(v10 + 8);
        if ( v11 != -1 )
        {
          *(_DWORD *)(FirstTextCell + 12) = v11;
          v6 = v30;
          goto LABEL_17;
        }
        v6 = v30;
      }
      *(_DWORD *)(FirstTextCell + 12) = v8;
      if ( v10 && v10 != -1 )
        *(_DWORD *)(v10 + 8) = v8;
      ++v8;
      ++v7;
LABEL_17:
      v30 = ++v6;
      if ( !v9 )
        break;
      FirstTextCell = (int)v9;
      TextCell = NextTextCell(v25, *v9);
      v6 = v30;
      v9 = (_DWORD *)TextCell;
      v26 = (_DWORD *)TextCell;
    }
  }
  v13 = pExcelRecordBuffer;
  v14 = 8;
  v31 = 524540;
  *(_DWORD *)pExcelRecordBuffer = v6;
  v13[1] = v7;
  if ( v7 >= 1024 )
  {
    do
      v14 *= 2;
    while ( v7 / v14 >= 128 );
  }
  v15 = (_WORD *)MemAllocate(1026);
  v28 = v15;
  if ( !v15 )
    return -2;
  if ( v14 > 0x8000 )
    LOWORD(v14) = 0x8000;
  v17 = v30 <= 0;
  *v15 = v14;
  if ( !v17 )
  {
    v30 = -1;
    v18 = FindFirstTextCell(v29, v25);
    if ( v18 )
    {
      for ( k = v26; ; v26 = k )
      {
        v20 = *(_DWORD *)(v18 + 8);
        if ( !v20 || v20 == -1 )
          v21 = -1;
        else
          v21 = *(_DWORD *)(v20 + 8);
        if ( v21 > v30 )
        {
          v22 = AddToStringPool(v18, v21, &v31, v23, v24, v28);
          if ( v22 )
            goto LABEL_40;
          v30 = v21;
        }
        if ( !k )
          break;
        v18 = (int)k;
        k = (_DWORD *)NextTextCell(v25, *k);
      }
      v15 = v28;
    }
  }
  v22 = WriteRecord(&v31, pExcelRecordBuffer);
  if ( !v22 )
  {
    v31 = 67240191;
    v22 = WriteRecord(&v31, v15);
  }
LABEL_40:
  MemFree(v28);
  return v22;
}

```

## disassembly

```asm
0x1000d590  mov     edi, edi
0x1000d592  push    ebp
0x1000d593  mov     ebp, esp
0x1000d595  sub     esp, 24h
0x1000d598  push    ebx
0x1000d599  mov     ebx, edx
0x1000d59b  mov     [ebp+var_14], ecx
0x1000d59e  push    esi
0x1000d59f  push    edi
0x1000d5a0  mov     [ebp+var_C], ebx
0x1000d5a3  mov     edi, [ebx+28h]
0x1000d5a6  test    edi, edi
0x1000d5a8  jz      short loc_1000D5D6
0x1000d5aa  mov     esi, 2
0x1000d5af  nop
0x1000d5b0  mov     eax, [edi+esi*4]
0x1000d5b3  test    eax, eax
0x1000d5b5  jz      short loc_1000D5CD
0x1000d5b7  nop     word ptr [eax+eax+00000000h]
0x1000d5c0  mov     dword ptr [eax+8], 0FFFFFFFFh
0x1000d5c7  mov     eax, [eax]
0x1000d5c9  test    eax, eax
0x1000d5cb  jnz     short loc_1000D5C0
0x1000d5cd  inc     esi
0x1000d5ce  cmp     esi, 20Bh
0x1000d5d4  jnz     short loc_1000D5B0
0x1000d5d6  lea     edx, [ebp+var_24]
0x1000d5d9  mov     ecx, ebx
0x1000d5db  call    FindFirstTextCell
0x1000d5e0  mov     edi, eax
0x1000d5e2  xor     ecx, ecx
0x1000d5e4  xor     ebx, ebx
0x1000d5e6  mov     [ebp+var_8], ecx
0x1000d5e9  xor     esi, esi
0x1000d5eb  test    edi, edi
0x1000d5ed  jz      short loc_1000D642
0x1000d5ef  mov     edx, [ebp+var_18]
0x1000d5f2  mov     eax, [edi+8]
0x1000d5f5  test    eax, eax
0x1000d5f7  jz      short loc_1000D611
0x1000d5f9  cmp     eax, 0FFFFFFFFh
0x1000d5fc  jz      short loc_1000D611
0x1000d5fe  mov     ecx, [eax+8]
0x1000d601  cmp     ecx, 0FFFFFFFFh
0x1000d604  jz      short loc_1000D60E
0x1000d606  mov     [edi+0Ch], ecx
0x1000d609  mov     ecx, [ebp+var_8]
0x1000d60c  jmp     short loc_1000D622
0x1000d60e  mov     ecx, [ebp+var_8]
0x1000d611  mov     [edi+0Ch], esi
0x1000d614  test    eax, eax
0x1000d616  jz      short loc_1000D620
0x1000d618  cmp     eax, 0FFFFFFFFh
0x1000d61b  jz      short loc_1000D620
0x1000d61d  mov     [eax+8], esi
0x1000d620  inc     esi
0x1000d621  inc     ebx
0x1000d622  inc     ecx
0x1000d623  mov     [ebp+var_8], ecx
0x1000d626  test    edx, edx
0x1000d628  jz      short loc_1000D642
0x1000d62a  mov     edi, edx
0x1000d62c  lea     ecx, [ebp+var_24]
0x1000d62f  mov     edx, [edx]
0x1000d631  call    NextTextCell
0x1000d636  mov     ecx, [ebp+var_8]
0x1000d639  mov     edx, eax
0x1000d63b  mov     [ebp+var_18], edx
0x1000d63e  test    edi, edi
0x1000d640  jnz     short loc_1000D5F2
0x1000d642  mov     eax, _pExcelRecordBuffer
0x1000d647  mov     esi, 8
0x1000d64c  mov     [ebp+var_4], 800FCh
0x1000d653  mov     [eax], ecx
0x1000d655  mov     [eax+4], ebx
0x1000d658  cmp     ebx, 400h
0x1000d65e  jl      short loc_1000D66E
0x1000d660  mov     eax, ebx
0x1000d662  add     esi, esi
0x1000d664  cdq
0x1000d665  idiv    esi
0x1000d667  cmp     eax, 80h
0x1000d66c  jge     short loc_1000D660
0x1000d66e  mov     ecx, 402h
0x1000d673  call    _MemAllocate@4; MemAllocate(x)
0x1000d678  mov     ebx, eax
0x1000d67a  mov     [ebp+var_10], ebx
0x1000d67d  test    ebx, ebx
0x1000d67f  jnz     short loc_1000D68B
0x1000d681  lea     eax, [ebx-2]
0x1000d684  pop     edi
0x1000d685  pop     esi
0x1000d686  pop     ebx
0x1000d687  mov     esp, ebp
0x1000d689  pop     ebp
0x1000d68a  retn
0x1000d68b  mov     eax, 8000h
0x1000d690  cmp     esi, eax
0x1000d692  cmovg   esi, eax
0x1000d695  cmp     [ebp+var_8], 0
0x1000d699  mov     [ebx], si
0x1000d69c  jle     short loc_1000D70D
0x1000d69e  mov     ecx, [ebp+var_C]
0x1000d6a1  lea     edx, [ebp+var_24]
0x1000d6a4  or      esi, 0FFFFFFFFh
0x1000d6a7  mov     [ebp+var_8], esi
0x1000d6aa  call    FindFirstTextCell
0x1000d6af  mov     edi, eax
0x1000d6b1  test    edi, edi
0x1000d6b3  jz      short loc_1000D70D
0x1000d6b5  mov     ebx, [ebp+var_18]
0x1000d6b8  mov     esi, [edi+8]
0x1000d6bb  test    esi, esi
0x1000d6bd  jz      short loc_1000D6C9
0x1000d6bf  cmp     esi, 0FFFFFFFFh
0x1000d6c2  jz      short loc_1000D6C9
0x1000d6c4  mov     esi, [esi+8]
0x1000d6c7  jmp     short loc_1000D6CC
0x1000d6c9  or      esi, 0FFFFFFFFh
0x1000d6cc  cmp     esi, [ebp+var_8]
0x1000d6cf  jle     short loc_1000D6F1
0x1000d6d1  push    [ebp+var_10]
0x1000d6d4  mov     edx, [ebp+var_C]
0x1000d6d7  lea     eax, [ebp+var_4]
0x1000d6da  mov     ecx, [ebp+var_14]
0x1000d6dd  sub     esp, 8
0x1000d6e0  push    eax
0x1000d6e1  push    esi
0x1000d6e2  push    edi
0x1000d6e3  call    AddToStringPool
0x1000d6e8  mov     edi, eax
0x1000d6ea  test    edi, edi
0x1000d6ec  jnz     short loc_1000D742
0x1000d6ee  mov     [ebp+var_8], esi
0x1000d6f1  test    ebx, ebx
0x1000d6f3  jz      short loc_1000D70A
0x1000d6f5  mov     edx, [ebx]
0x1000d6f7  lea     ecx, [ebp+var_24]
0x1000d6fa  mov     edi, ebx
0x1000d6fc  call    NextTextCell
0x1000d701  mov     ebx, eax
0x1000d703  mov     [ebp+var_18], ebx
0x1000d706  test    edi, edi
0x1000d708  jnz     short loc_1000D6B8
0x1000d70a  mov     ebx, [ebp+var_10]
0x1000d70d  push    _pExcelRecordBuffer
0x1000d713  mov     esi, [ebp+var_14]
0x1000d716  lea     eax, [ebp+var_4]
0x1000d719  mov     edx, [ebp+var_C]
0x1000d71c  mov     ecx, esi
0x1000d71e  push    eax
0x1000d71f  call    WriteRecord
0x1000d724  mov     edi, eax
0x1000d726  test    edi, edi
0x1000d728  jnz     short loc_1000D742
0x1000d72a  mov     edx, [ebp+var_C]
0x1000d72d  lea     eax, [ebp+var_4]
0x1000d730  push    ebx
0x1000d731  push    eax
0x1000d732  mov     ecx, esi
0x1000d734  mov     [ebp+var_4], 40200FFh
0x1000d73b  call    WriteRecord
0x1000d740  mov     edi, eax
0x1000d742  mov     ecx, [ebp+var_10]
0x1000d745  call    _MemFree@4; MemFree(x)
0x1000d74a  mov     eax, edi
0x1000d74c  pop     edi
0x1000d74d  pop     esi
0x1000d74e  pop     ebx
0x1000d74f  mov     esp, ebp
0x1000d751  pop     ebp
0x1000d752  retn
```
