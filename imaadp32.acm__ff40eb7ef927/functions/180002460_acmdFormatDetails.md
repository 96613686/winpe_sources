# acmdFormatDetails

- ea: `0x180002460`
- end: `0x1800025f0`
- name: `acmdFormatDetails`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800020b0`

## callees

- `0x180002460`
- `0x180002ccc`
- `0x180002d70`

## pseudocode

```c
__int64 __fastcall acmdFormatDetails(__int64 a1, __int64 a2, char a3)
{
  int v4; // r8d
  __int64 v6; // r9
  unsigned __int64 v7; // rcx
  int v8; // edx
  unsigned int v9; // r10d
  unsigned __int16 v10; // ax
  int v11; // ecx
  unsigned int v12; // edx
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  int v17; // r8d
  _WORD *v18; // rcx
  int IsValidFormat; // eax
  int v20; // eax
  bool v21; // cf

  v4 = a3 & 0xF;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 8;
  }
  else
  {
    v6 = *(_QWORD *)(a2 + 16);
    v7 = *(unsigned int *)(a2 + 4);
    v8 = *(_DWORD *)(a2 + 8) - 1;
    if ( v8 )
    {
      if ( v8 != 16 || (unsigned int)v7 >= 8 )
        return 512;
      *(_WORD *)v6 = 17;
      *(_WORD *)(v6 + 14) = 4;
      v9 = gauFormatIndexToSampleRate[(unsigned __int64)(unsigned int)v7 >> 1];
      v10 = (v7 & 1) + 1;
      *(_DWORD *)(v6 + 4) = v9;
      v11 = v10 >> 1;
      *(_WORD *)(v6 + 2) = v10;
      if ( v9 <= 0x2B11 )
        LOWORD(v12) = 256 << v11;
      else
        v12 = (256 << v11) * (v9 / 0x2AF8);
      *(_WORD *)(v6 + 12) = v12;
      *(_WORD *)(v6 + 16) = 2;
      v13 = (unsigned __int16)(8 * ((unsigned int)(unsigned __int16)v12 - (4 << v11)) / (4 << v11) + 1);
      *(_WORD *)(v6 + 18) = v13;
      v14 = v9 * (unsigned __int16)v12 / v13;
    }
    else
    {
      if ( (unsigned int)v7 >= 0x10 )
        return 512;
      *(_WORD *)v6 = 1;
      v15 = v7 >> 2;
      v16 = (v7 >> 1) & 1;
      LOWORD(v7) = (v7 & 1) + 1;
      *(_WORD *)(v6 + 2) = v7;
      v17 = gauFormatIndexToSampleRate[v15];
      LOWORD(v15) = gauFormatIndexToBitsPerSample[2 * v16];
      *(_WORD *)(v6 + 14) = v15;
      LODWORD(v15) = (unsigned __int16)((unsigned __int16)v15 >> 3 << ((unsigned int)v7 >> 1));
      *(_WORD *)(v6 + 12) = v15;
      v14 = v17 * v15;
      *(_DWORD *)(v6 + 4) = v17;
    }
    *(_DWORD *)(v6 + 8) = v14;
  }
  v18 = *(_WORD **)(a2 + 16);
  if ( *v18 != 1 )
  {
    if ( *v18 == 17 )
    {
      IsValidFormat = imaadpcmIsValidFormat(v18);
      goto LABEL_18;
    }
    return 512;
  }
  IsValidFormat = pcmIsValidFormat(v18);
LABEL_18:
  if ( !IsValidFormat )
    return 512;
  v20 = 284;
  *(_DWORD *)(a2 + 12) = 1;
  v21 = *(_DWORD *)a2 < 0x11Cu;
  *(_WORD *)(a2 + 28) = 0;
  if ( v21 )
    v20 = *(_DWORD *)a2;
  *(_DWORD *)a2 = v20;
  return 0;
}

```

## disassembly

```asm
0x180002460  mov     [rsp+arg_0], rbx
0x180002465  push    rdi
0x180002466  sub     rsp, 20h
0x18000246a  mov     rbx, rdx
0x18000246d  mov     edi, 1
0x180002472  and     r8d, 0Fh
0x180002476  jz      short loc_180002489
0x180002478  cmp     r8d, edi
0x18000247b  jz      loc_1800025A7
0x180002481  lea     eax, [rdi+7]
0x180002484  jmp     loc_1800025E5
0x180002489  mov     r9, [rdx+10h]
0x18000248d  mov     ecx, [rdx+4]
0x180002490  mov     edx, [rdx+8]
0x180002493  sub     edx, edi
0x180002495  jz      loc_180002545
0x18000249b  cmp     edx, 10h
0x18000249e  jnz     loc_1800025E0
0x1800024a4  cmp     ecx, 8
0x1800024a7  jnb     loc_1800025E0
0x1800024ad  mov     eax, ecx
0x1800024af  mov     word ptr [r9], 11h
0x1800024b5  and     cx, di
0x1800024b8  shr     rax, 1
0x1800024bb  add     cx, di
0x1800024be  lea     r10, __ImageBase
0x1800024c5  mov     r8d, 100h
0x1800024cb  lea     r11d, [rdx-0Ch]
0x1800024cf  mov     [r9+0Eh], r11w
0x1800024d4  mov     r10d, ds:rva gauFormatIndexToSampleRate[r10+rax*4]
0x1800024dc  movzx   eax, cx
0x1800024df  mov     ecx, eax
0x1800024e1  mov     [r9+4], r10d
0x1800024e5  shr     ecx, 1
0x1800024e7  shl     r8d, cl
0x1800024ea  mov     [r9+2], ax
0x1800024ef  cmp     r10d, 2B11h
0x1800024f6  jbe     short loc_180002509
0x1800024f8  mov     eax, 0BEA67251h
0x1800024fd  mul     r10d
0x180002500  shr     edx, 0Dh
0x180002503  imul    edx, r8d
0x180002507  jmp     short loc_18000250C
0x180002509  mov     edx, r8d
0x18000250c  movzx   r8d, dx
0x180002510  xor     edx, edx
0x180002512  shl     r11d, cl
0x180002515  mov     eax, r8d
0x180002518  sub     eax, r11d
0x18000251b  mov     [r9+0Ch], r8w
0x180002520  shl     eax, 3
0x180002523  div     r11d
0x180002526  imul    r8d, r10d
0x18000252a  xor     edx, edx
0x18000252c  add     ax, di
0x18000252f  mov     word ptr [r9+10h], 2
0x180002536  movzx   ecx, ax
0x180002539  mov     [r9+12h], cx
0x18000253e  mov     eax, r8d
0x180002541  div     ecx
0x180002543  jmp     short loc_1800025A3
0x180002545  cmp     ecx, 10h
0x180002548  jnb     loc_1800025E0
0x18000254e  mov     rdx, rcx
0x180002551  mov     [r9], di
0x180002555  mov     rax, rcx
0x180002558  shr     rdx, 1
0x18000255b  shr     rax, 2
0x18000255f  lea     r10, __ImageBase
0x180002566  and     cx, di
0x180002569  and     rdx, rdi
0x18000256c  add     cx, di
0x18000256f  mov     [r9+2], cx
0x180002574  mov     r8d, ds:rva gauFormatIndexToSampleRate[r10+rax*4]
0x18000257c  movzx   eax, ds:rva gauFormatIndexToBitsPerSample[r10+rdx*4]
0x180002585  mov     [r9+0Eh], ax
0x18000258a  shr     ax, 3
0x18000258e  shr     ecx, 1
0x180002590  shl     ax, cl
0x180002593  movzx   eax, ax
0x180002596  mov     [r9+0Ch], ax
0x18000259b  imul    eax, r8d
0x18000259f  mov     [r9+4], r8d
0x1800025a3  mov     [r9+8], eax
0x1800025a7  mov     rcx, [rbx+10h]
0x1800025ab  movzx   edx, word ptr [rcx]
0x1800025ae  sub     edx, edi
0x1800025b0  jz      short loc_1800025BE
0x1800025b2  cmp     edx, 10h
0x1800025b5  jnz     short loc_1800025E0
0x1800025b7  call    imaadpcmIsValidFormat
0x1800025bc  jmp     short loc_1800025C3
0x1800025be  call    pcmIsValidFormat
0x1800025c3  xor     ecx, ecx
0x1800025c5  test    eax, eax
0x1800025c7  jz      short loc_1800025E0
0x1800025c9  mov     eax, 11Ch
0x1800025ce  mov     [rbx+0Ch], edi
0x1800025d1  cmp     [rbx], eax
0x1800025d3  mov     [rbx+1Ch], cx
0x1800025d7  cmovb   eax, [rbx]
0x1800025da  mov     [rbx], eax
0x1800025dc  xor     eax, eax
0x1800025de  jmp     short loc_1800025E5
0x1800025e0  mov     eax, 200h
0x1800025e5  mov     rbx, [rsp+28h+arg_0]
0x1800025ea  add     rsp, 20h
0x1800025ee  pop     rdi
0x1800025ef  retn
```
