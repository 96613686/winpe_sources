# WriteCell

- ea: `0x10016b00`
- end: `0x10016dee`
- name: `WriteCell`
- size: `750`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10018430`
- `0x10018550`

## callees

- `0x10016950`
- `0x10016b00`
- `0x1002611f`
- `0x10035f40`

## pseudocode

```c
int __fastcall WriteCell(int a1, __int16 a2, int a3)
{
  __int16 v4; // ax
  int v5; // ecx
  int *v6; // ebx
  int v7; // eax
  unsigned int v8; // esi
  int v9; // ecx
  int result; // eax
  int v11; // ecx
  int *v12; // ebx
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  int v16; // eax
  char v17; // bl
  int v18; // ecx
  unsigned int v19; // esi
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  __int64 v23; // [esp+10h] [ebp-1Ch]
  int v24; // [esp+14h] [ebp-18h]
  int v25; // [esp+14h] [ebp-18h]
  int v26; // [esp+14h] [ebp-18h]
  void *v27; // [esp+1Ch] [ebp-10h]
  void *v28; // [esp+1Ch] [ebp-10h]
  int *v29; // [esp+1Ch] [ebp-10h]
  void *v30; // [esp+1Ch] [ebp-10h]
  int v31; // [esp+20h] [ebp-Ch] BYREF
  int v32; // [esp+24h] [ebp-8h]

  LOWORD(v32) = a2;
  HIWORD(v32) = *(unsigned __int8 *)(a3 + 4);
  v4 = *(_WORD *)(a3 + 8);
  if ( (v4 & 1) != 0 )
  {
    v5 = *(_DWORD *)(a1 + 20);
    v6 = (int *)pExcelRecordBuffer;
    v27 = *(void **)(a3 + 12);
    v31 = 393729;
    v7 = BFWriteFile(v5, (char *)&v31, 4u);
    if ( v7 )
      goto LABEL_9;
    v8 = SHIWORD(v31);
    memset(v6, 0, SHIWORD(v31));
LABEL_7:
    *v6 = v32;
    *((_WORD *)v6 + 2) = (_WORD)v27;
LABEL_8:
    v7 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)v6, v8);
LABEL_9:
    result = dword_10001970[abs32(v7)];
    if ( result == -10 )
      return -10;
    return result;
  }
  if ( (v4 & 2) != 0 )
  {
    v9 = *(_DWORD *)(a1 + 20);
    v6 = (int *)pExcelRecordBuffer;
    v23 = *(_QWORD *)(a3 + 24);
    v27 = *(void **)(a3 + 12);
    v31 = 918019;
    v7 = BFWriteFile(v9, (char *)&v31, 4u);
    if ( v7 )
      goto LABEL_9;
    v8 = SHIWORD(v31);
    memset(v6, 0, SHIWORD(v31));
    *(_QWORD *)((char *)v6 + 6) = v23;
    goto LABEL_7;
  }
  if ( (v4 & 4) != 0 )
  {
    v11 = *(_DWORD *)(a1 + 20);
    v12 = (int *)pExcelRecordBuffer;
    v24 = *(_DWORD *)(a3 + 24);
    v28 = *(void **)(a3 + 12);
    v31 = 524805;
    v13 = BFWriteFile(v11, (char *)&v31, 4u);
    if ( !v13 )
    {
      v14 = SHIWORD(v31);
      memset(v12, 0, SHIWORD(v31));
      *v12 = v32;
      *((_WORD *)v12 + 2) = (_WORD)v28;
      *((_BYTE *)v12 + 6) = v24 != 0;
      *((_BYTE *)v12 + 7) = 0;
      v15 = dword_10001970[abs32(BFWriteFile(*(_DWORD *)(a1 + 20), (char *)v12, v14))];
      if ( v15 == -10 )
        v15 = -10;
      result = dword_10001970[abs32(v15)];
      if ( result == -10 )
        return -10;
      return result;
    }
    goto LABEL_34;
  }
  if ( (v4 & 8) != 0 )
  {
    v16 = *(_DWORD *)(a3 + 24);
    v25 = *(_DWORD *)(a3 + 12);
    if ( v16 )
    {
      switch ( v16 )
      {
        case 1:
          v17 = 7;
          break;
        case 2:
          v17 = 15;
          break;
        case 3:
          v17 = 23;
          break;
        case 4:
          v17 = 29;
          break;
        default:
          v17 = 42;
          if ( v16 == 5 )
            v17 = 36;
          break;
      }
    }
    else
    {
      v17 = 0;
    }
    v18 = *(_DWORD *)(a1 + 20);
    v29 = (int *)pExcelRecordBuffer;
    v31 = 524805;
    v13 = BFWriteFile(v18, (char *)&v31, 4u);
    if ( !v13 )
    {
      v19 = SHIWORD(v31);
      memset(v29, 0, SHIWORD(v31));
      *v29 = v32;
      *((_WORD *)v29 + 2) = v25;
      *((_BYTE *)v29 + 6) = v17;
      *((_BYTE *)v29 + 7) = 1;
      v13 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)v29, v19);
    }
LABEL_34:
    v20 = dword_10001970[abs32(v13)];
    if ( v20 == -10 )
      v20 = -10;
    result = dword_10001970[abs32(v20)];
    if ( result == -10 )
      return -10;
    return result;
  }
  if ( (v4 & 0x10) == 0 )
  {
    if ( (*(_WORD *)(a3 + 8) & 0x2000) == 0 )
      return 0;
    v22 = *(_DWORD *)(a1 + 20);
    v6 = (int *)pExcelRecordBuffer;
    v30 = *(void **)(a3 + 16);
    v26 = *(_DWORD *)(a3 + 12);
    v31 = 655998;
    v7 = BFWriteFile(v22, (char *)&v31, 4u);
    if ( v7 )
      goto LABEL_9;
    v8 = SHIWORD(v31);
    memset(v6, 0, SHIWORD(v31));
    *v6 = v32;
    *((_WORD *)v6 + 2) = v26;
    *(int *)((char *)v6 + 6) = (int)v30;
    goto LABEL_8;
  }
  v21 = *(_DWORD *)(a3 + 24);
  if ( !v21 || v21 == -1 )
    return WriteTextCell(v32, *(_DWORD *)(a3 + 12), &WideCharStr);
  else
    return WriteTextCell(v32, *(_DWORD *)(a3 + 12), (LPCWCH)(v21 + 14));
}

```

## disassembly

```asm
0x10016b00  mov     edi, edi
0x10016b02  push    ebp
0x10016b03  mov     ebp, esp
0x10016b05  sub     esp, 20h
0x10016b08  mov     word ptr [ebp+var_8], dx
0x10016b0c  mov     edx, [ebp+arg_0]
0x10016b0f  push    ebx
0x10016b10  push    esi
0x10016b11  push    edi
0x10016b12  movzx   eax, byte ptr [edx+4]
0x10016b16  mov     edi, ecx
0x10016b18  mov     word ptr [ebp+var_8+2], ax
0x10016b1c  movzx   eax, word ptr [edx+8]
0x10016b20  test    al, 1
0x10016b22  jz      short loc_10016B56
0x10016b24  mov     eax, [edx+0Ch]
0x10016b27  lea     edx, [ebp+var_C]
0x10016b2a  mov     ecx, [edi+14h]
0x10016b2d  mov     ebx, _pExcelRecordBuffer
0x10016b33  push    4
0x10016b35  mov     [ebp+var_10], eax
0x10016b38  mov     [ebp+var_C], 60201h
0x10016b3f  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016b44  test    eax, eax
0x10016b46  jnz     short loc_10016BB8
0x10016b48  movsx   esi, word ptr [ebp+var_C+2]
0x10016b4c  push    esi; Size
0x10016b4d  push    eax; Val
0x10016b4e  push    ebx; void *
0x10016b4f  call    _memset
0x10016b54  jmp     short loc_10016B9E
0x10016b56  test    al, 2
0x10016b58  jz      short loc_10016BD8
0x10016b5a  movsd   xmm0, qword ptr [edx+18h]
0x10016b5f  mov     eax, [edx+0Ch]
0x10016b62  lea     edx, [ebp+var_C]
0x10016b65  mov     ecx, [edi+14h]
0x10016b68  mov     ebx, _pExcelRecordBuffer
0x10016b6e  push    4
0x10016b70  movsd   [ebp+var_1C], xmm0
0x10016b75  mov     [ebp+var_10], eax
0x10016b78  mov     [ebp+var_C], 0E0203h
0x10016b7f  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016b84  test    eax, eax
0x10016b86  jnz     short loc_10016BB8
0x10016b88  movsx   esi, word ptr [ebp+var_C+2]
0x10016b8c  push    esi; Size
0x10016b8d  push    eax; Val
0x10016b8e  push    ebx; void *
0x10016b8f  call    _memset
0x10016b94  movsd   xmm0, [ebp+var_1C]
0x10016b99  movsd   qword ptr [ebx+6], xmm0
0x10016b9e  mov     eax, [ebp+var_8]
0x10016ba1  mov     [ebx], eax
0x10016ba3  mov     eax, [ebp+var_10]
0x10016ba6  mov     [ebx+4], ax
0x10016baa  mov     ecx, [edi+14h]
0x10016bad  add     esp, 0Ch
0x10016bb0  mov     edx, ebx
0x10016bb2  push    esi
0x10016bb3  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016bb8  cdq
0x10016bb9  mov     ecx, 0FFFFFFF6h
0x10016bbe  xor     eax, edx
0x10016bc0  sub     eax, edx
0x10016bc2  mov     eax, ds:dword_10001970[eax*4]
0x10016bc9  cmp     eax, 0FFFFFFF6h
0x10016bcc  cmovz   eax, ecx
0x10016bcf  pop     edi
0x10016bd0  pop     esi
0x10016bd1  pop     ebx
0x10016bd2  mov     esp, ebp
0x10016bd4  pop     ebp
0x10016bd5  retn    4
0x10016bd8  test    al, 4
0x10016bda  jz      loc_10016C73
0x10016be0  mov     eax, [edx+18h]
0x10016be3  mov     ecx, [edi+14h]
0x10016be6  mov     ebx, _pExcelRecordBuffer
0x10016bec  mov     dword ptr [ebp+var_1C+4], eax
0x10016bef  mov     eax, [edx+0Ch]
0x10016bf2  lea     edx, [ebp+var_C]
0x10016bf5  push    4
0x10016bf7  mov     [ebp+var_10], eax
0x10016bfa  mov     [ebp+var_C], 80205h
0x10016c01  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016c06  test    eax, eax
0x10016c08  jnz     loc_10016D12
0x10016c0e  movsx   esi, word ptr [ebp+var_C+2]
0x10016c12  push    esi; Size
0x10016c13  push    eax; Val
0x10016c14  push    ebx; void *
0x10016c15  call    _memset
0x10016c1a  mov     eax, [ebp+var_8]
0x10016c1d  add     esp, 0Ch
0x10016c20  cmp     dword ptr [ebp+var_1C+4], 0
0x10016c24  mov     edx, ebx
0x10016c26  mov     [ebx], eax
0x10016c28  mov     eax, [ebp+var_10]
0x10016c2b  mov     [ebx+4], ax
0x10016c2f  setnz   al
0x10016c32  mov     [ebx+6], al
0x10016c35  mov     byte ptr [ebx+7], 0
0x10016c39  mov     ecx, [edi+14h]
0x10016c3c  push    esi
0x10016c3d  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016c42  cdq
0x10016c43  mov     ecx, 0FFFFFFF6h
0x10016c48  xor     eax, edx
0x10016c4a  sub     eax, edx
0x10016c4c  mov     eax, ds:dword_10001970[eax*4]
0x10016c53  cmp     eax, 0FFFFFFF6h
0x10016c56  cmovz   eax, ecx
0x10016c59  cdq
0x10016c5a  xor     eax, edx
0x10016c5c  sub     eax, edx
0x10016c5e  mov     eax, ds:dword_10001970[eax*4]
0x10016c65  cmp     eax, ecx
0x10016c67  cmovz   eax, ecx
0x10016c6a  pop     edi
0x10016c6b  pop     esi
0x10016c6c  pop     ebx
0x10016c6d  mov     esp, ebp
0x10016c6f  pop     ebp
0x10016c70  retn    4
0x10016c73  test    al, 8
0x10016c75  jz      loc_10016D43
0x10016c7b  mov     eax, [edx+18h]
0x10016c7e  mov     ecx, [edx+0Ch]
0x10016c81  mov     dword ptr [ebp+var_1C+4], ecx
0x10016c84  test    eax, eax
0x10016c86  jnz     short loc_10016C8C
0x10016c88  xor     bl, bl
0x10016c8a  jmp     short loc_10016CC0
0x10016c8c  cmp     eax, 1
0x10016c8f  jnz     short loc_10016C95
0x10016c91  mov     bl, 7
0x10016c93  jmp     short loc_10016CC0
0x10016c95  cmp     eax, 2
0x10016c98  jnz     short loc_10016C9E
0x10016c9a  mov     bl, 0Fh
0x10016c9c  jmp     short loc_10016CC0
0x10016c9e  cmp     eax, 3
0x10016ca1  jnz     short loc_10016CA7
0x10016ca3  mov     bl, 17h
0x10016ca5  jmp     short loc_10016CC0
0x10016ca7  cmp     eax, 4
0x10016caa  jnz     short loc_10016CB0
0x10016cac  mov     bl, 1Dh
0x10016cae  jmp     short loc_10016CC0
0x10016cb0  cmp     eax, 5
0x10016cb3  mov     ebx, 2Ah ; '*'
0x10016cb8  mov     ecx, 24h ; '$'
0x10016cbd  cmovz   ebx, ecx
0x10016cc0  mov     eax, _pExcelRecordBuffer
0x10016cc5  lea     edx, [ebp+var_C]
0x10016cc8  mov     ecx, [edi+14h]
0x10016ccb  push    4
0x10016ccd  mov     [ebp+var_10], eax
0x10016cd0  mov     [ebp+var_C], 80205h
0x10016cd7  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016cdc  test    eax, eax
0x10016cde  jnz     short loc_10016D12
0x10016ce0  movsx   esi, word ptr [ebp+var_C+2]
0x10016ce4  push    esi; Size
0x10016ce5  push    eax; Val
0x10016ce6  push    [ebp+var_10]; void *
0x10016ce9  call    _memset
0x10016cee  mov     ecx, [ebp+var_10]
0x10016cf1  add     esp, 0Ch
0x10016cf4  mov     eax, [ebp+var_8]
0x10016cf7  mov     edx, ecx
0x10016cf9  mov     [ecx], eax
0x10016cfb  mov     eax, dword ptr [ebp+var_1C+4]
0x10016cfe  mov     [ecx+4], ax
0x10016d02  mov     [ecx+6], bl
0x10016d05  mov     byte ptr [ecx+7], 1
0x10016d09  mov     ecx, [edi+14h]
0x10016d0c  push    esi
0x10016d0d  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016d12  cdq
0x10016d13  mov     ecx, 0FFFFFFF6h
0x10016d18  xor     eax, edx
0x10016d1a  sub     eax, edx
0x10016d1c  mov     eax, ds:dword_10001970[eax*4]
0x10016d23  cmp     eax, 0FFFFFFF6h
0x10016d26  cmovz   eax, ecx
0x10016d29  cdq
0x10016d2a  xor     eax, edx
0x10016d2c  sub     eax, edx
0x10016d2e  mov     eax, ds:dword_10001970[eax*4]
0x10016d35  cmp     eax, ecx
0x10016d37  cmovz   eax, ecx
0x10016d3a  pop     edi
0x10016d3b  pop     esi
0x10016d3c  pop     ebx
0x10016d3d  mov     esp, ebp
0x10016d3f  pop     ebp
0x10016d40  retn    4
0x10016d43  test    al, 10h
0x10016d45  jz      short loc_10016D8B
0x10016d47  mov     eax, [edx+18h]
0x10016d4a  test    eax, eax
0x10016d4c  jz      short loc_10016D6E
0x10016d4e  cmp     eax, 0FFFFFFFFh
0x10016d51  jz      short loc_10016D6E
0x10016d53  add     eax, 0Eh
0x10016d56  push    eax; lpWideCharStr
0x10016d57  push    dword ptr [edx+0Ch]; __int16
0x10016d5a  mov     edx, [edi+18h]
0x10016d5d  push    [ebp+var_8]; int
0x10016d60  call    WriteTextCell
0x10016d65  pop     edi
0x10016d66  pop     esi
0x10016d67  pop     ebx
0x10016d68  mov     esp, ebp
0x10016d6a  pop     ebp
0x10016d6b  retn    4
0x10016d6e  mov     eax, offset WideCharStr
0x10016d73  push    eax; lpWideCharStr
0x10016d74  push    dword ptr [edx+0Ch]; __int16
0x10016d77  mov     edx, [edi+18h]
0x10016d7a  push    [ebp+var_8]; int
0x10016d7d  call    WriteTextCell
0x10016d82  pop     edi
0x10016d83  pop     esi
0x10016d84  pop     ebx
0x10016d85  mov     esp, ebp
0x10016d87  pop     ebp
0x10016d88  retn    4
0x10016d8b  test    eax, 2000h
0x10016d90  jz      short loc_10016DE3
0x10016d92  mov     eax, [edx+10h]
0x10016d95  mov     ecx, [edi+14h]
0x10016d98  mov     ebx, _pExcelRecordBuffer
0x10016d9e  mov     [ebp+var_10], eax
0x10016da1  mov     eax, [edx+0Ch]
0x10016da4  lea     edx, [ebp+var_C]
0x10016da7  push    4
0x10016da9  mov     dword ptr [ebp+var_1C+4], eax
0x10016dac  mov     [ebp+var_C], 0A027Eh
0x10016db3  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10016db8  test    eax, eax
0x10016dba  jnz     loc_10016BB8
0x10016dc0  movsx   esi, word ptr [ebp+var_C+2]
0x10016dc4  push    esi; Size
0x10016dc5  push    eax; Val
0x10016dc6  push    ebx; void *
0x10016dc7  call    _memset
0x10016dcc  mov     eax, [ebp+var_8]
0x10016dcf  mov     [ebx], eax
0x10016dd1  mov     eax, dword ptr [ebp+var_1C+4]
0x10016dd4  mov     [ebx+4], ax
0x10016dd8  mov     eax, [ebp+var_10]
0x10016ddb  mov     [ebx+6], eax
0x10016dde  jmp     loc_10016BAA
0x10016de3  pop     edi
0x10016de4  pop     esi
0x10016de5  xor     eax, eax
0x10016de7  pop     ebx
0x10016de8  mov     esp, ebp
0x10016dea  pop     ebp
0x10016deb  retn    4
```
