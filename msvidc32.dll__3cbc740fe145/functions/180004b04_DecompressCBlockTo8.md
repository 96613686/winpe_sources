# DecompressCBlockTo8

- ea: `0x180004b04`
- end: `0x180004db4`
- name: `DecompressCBlockTo8`
- size: `688`
- prototype: `unsigned __int8 *__fastcall(int *, unsigned __int8 *, int *, int, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005ad0`

## callees

- `0x180004b04`

## pseudocode

```c
unsigned __int8 *__fastcall DecompressCBlockTo8(int *a1, unsigned __int8 *a2, int *a3, int a4, _DWORD *a5)
{
  int v5; // eax
  unsigned __int8 v6; // r10
  __int64 v7; // r14
  int v9; // r11d
  unsigned __int8 *v10; // r9
  int v12; // r10d
  unsigned __int8 v13; // bp
  int v14; // eax
  unsigned __int8 v15; // cl
  int v16; // eax
  unsigned __int8 v17; // di
  int v18; // eax
  unsigned __int8 v19; // r9
  int v20; // r15d
  int v21; // esi
  int v22; // ecx
  int v23; // ebp
  __int64 v24; // rax
  unsigned __int8 v25; // bp
  int v26; // eax
  unsigned __int8 v27; // r9
  int v28; // eax
  unsigned __int8 v29; // si
  int v30; // eax
  int v31; // r9d
  __int64 v32; // rax
  unsigned __int8 v33; // di
  int v34; // eax
  int v35; // eax
  int v36; // r9d
  int v37; // r10d
  int v38; // r9d
  __int64 v39; // rax

  v5 = *a3;
  v6 = 0;
  v7 = a4;
  if ( (unsigned int)*a3 <= 1 )
  {
    LOWORD(v9) = 0;
LABEL_34:
    if ( v5 )
    {
      v33 = *a2++;
      v34 = v5 - 1;
      *a3 = v34;
      if ( v34 )
      {
        v6 = *a2++;
        *a3 = v34 - 1;
      }
    }
    else
    {
      v33 = 0;
    }
    v35 = v6;
    v36 = v6 << 8;
    v37 = 4;
    v38 = v35 | ((v35 | ((v35 | v36) << 8)) << 8);
    do
    {
      v39 = v9 & 0xF;
      LOWORD(v9) = (unsigned __int16)v9 >> 4;
      *a1 = v38 ^ (v38 ^ (v33 | ((v33 | ((v33 | (v33 << 8)) << 8)) << 8))) & ExpansionTable[v39];
      a1 = (int *)((char *)a1 + v7);
      --v37;
    }
    while ( v37 );
    return a2;
  }
  v9 = *(unsigned __int16 *)a2;
  v10 = a2 + 2;
  v5 -= 2;
  *a3 = v5;
  if ( (v9 & 0x8000u) == 0 )
  {
    a2 += 2;
    goto LABEL_34;
  }
  if ( (v9 & 0xFFFFFC00) == 0x8400 )
  {
    *a5 = (v9 & 0x3FF) - 1;
    return a2 + 2;
  }
  if ( (v9 & 0xFFFFFC00) == 0x8000 )
  {
    v12 = 4;
    do
    {
      *a1 = (unsigned __int8)v9
          | (((unsigned __int8)v9 | (((unsigned __int8)v9 | ((unsigned __int8)v9 << 8)) << 8)) << 8);
      a1 = (int *)((char *)a1 + v7);
      --v12;
    }
    while ( v12 );
    return a2 + 2;
  }
  if ( !v5 )
  {
    v13 = 0;
    a2 += 2;
LABEL_14:
    v15 = 0;
LABEL_16:
    v17 = 0;
    goto LABEL_18;
  }
  v13 = *v10;
  a2 += 3;
  v14 = v5 - 1;
  *a3 = v14;
  if ( !v14 )
    goto LABEL_14;
  v15 = *a2;
  a2 = v10 + 2;
  v16 = v14 - 1;
  *a3 = v16;
  if ( !v16 )
    goto LABEL_16;
  v17 = *a2;
  a2 = v10 + 3;
  v18 = v16 - 1;
  *a3 = v18;
  if ( v18 )
  {
    v19 = *a2++;
    *a3 = v18 - 1;
    goto LABEL_20;
  }
LABEL_18:
  v19 = 0;
LABEL_20:
  v20 = 2;
  v21 = v15 | ((v15 | ((v19 | (v19 << 8)) << 8)) << 8);
  v22 = v13;
  v23 = 2;
  do
  {
    v24 = v9 & 0xF;
    LOWORD(v9) = (unsigned __int16)v9 >> 4;
    *a1 = v21 ^ (v21 ^ (v22 | ((v22 | ((v17 | (v17 << 8)) << 8)) << 8))) & ExpansionTable[v24];
    a1 = (int *)((char *)a1 + v7);
    --v23;
  }
  while ( v23 );
  if ( !*a3 )
  {
    v25 = 0;
LABEL_25:
    v27 = 0;
    goto LABEL_27;
  }
  v25 = *a2++;
  v26 = *a3 - 1;
  *a3 = v26;
  if ( !v26 )
    goto LABEL_25;
  v27 = *a2++;
  v28 = v26 - 1;
  *a3 = v28;
  if ( v28 )
  {
    v29 = *a2++;
    v30 = v28 - 1;
    *a3 = v30;
    if ( v30 )
    {
      v6 = *a2++;
      *a3 = v30 - 1;
    }
    goto LABEL_30;
  }
LABEL_27:
  v29 = 0;
LABEL_30:
  v31 = v27 | ((v27 | ((v6 | (v6 << 8)) << 8)) << 8);
  do
  {
    v32 = v9 & 0xF;
    LOWORD(v9) = (unsigned __int16)v9 >> 4;
    *a1 = v31 ^ (v31 ^ (v25 | ((v25 | ((v29 | (v29 << 8)) << 8)) << 8))) & ExpansionTable[v32];
    a1 = (int *)((char *)a1 + v7);
    --v20;
  }
  while ( v20 );
  return a2;
}

```

## disassembly

```asm
0x180004b04  push    rbx
0x180004b06  push    rbp
0x180004b07  push    rsi
0x180004b08  push    rdi
0x180004b09  push    r12
0x180004b0b  push    r14
0x180004b0d  push    r15
0x180004b0f  mov     eax, [r8]
0x180004b12  xor     r10d, r10d
0x180004b15  movsxd  r14, r9d
0x180004b18  mov     rbx, rcx
0x180004b1b  cmp     eax, 1
0x180004b1e  ja      short loc_180004B29
0x180004b20  movzx   r11d, r10w
0x180004b24  jmp     loc_180004D16
0x180004b29  movzx   r11d, word ptr [rdx]
0x180004b2d  lea     r9, [rdx+2]
0x180004b31  add     eax, 0FFFFFFFEh
0x180004b34  mov     [r8], eax
0x180004b37  test    r11w, r11w
0x180004b3b  jns     loc_180004D13
0x180004b41  mov     edx, r11d
0x180004b44  mov     ecx, r11d
0x180004b47  and     edx, 0FFFFFC00h
0x180004b4d  cmp     edx, 8400h
0x180004b53  jnz     short loc_180004B6C
0x180004b55  mov     rax, [rsp+38h+arg_20]
0x180004b5a  and     ecx, 3FFh
0x180004b60  dec     ecx
0x180004b62  mov     [rax], ecx
0x180004b64  mov     rax, r9
0x180004b67  jmp     loc_180004DA9
0x180004b6c  cmp     edx, 8000h
0x180004b72  jnz     short loc_180004BA1
0x180004b74  movzx   eax, r11b
0x180004b78  mov     r10d, 4
0x180004b7e  mov     ecx, eax
0x180004b80  shl     ecx, 8
0x180004b83  or      ecx, eax
0x180004b85  shl     ecx, 8
0x180004b88  or      ecx, eax
0x180004b8a  shl     ecx, 8
0x180004b8d  or      ecx, eax
0x180004b8f  mov     rax, r14
0x180004b92  or      edi, 0FFFFFFFFh
0x180004b95  mov     [rbx], ecx
0x180004b97  add     rbx, rax
0x180004b9a  add     r10d, edi
0x180004b9d  jnz     short loc_180004B95
0x180004b9f  jmp     short loc_180004B64
0x180004ba1  test    eax, eax
0x180004ba3  jnz     short loc_180004BAD
0x180004ba5  mov     bpl, r10b
0x180004ba8  mov     rdx, r9
0x180004bab  jmp     short loc_180004BBC
0x180004bad  mov     bpl, [r9]
0x180004bb0  lea     rdx, [r9+1]
0x180004bb4  sub     eax, 1
0x180004bb7  mov     [r8], eax
0x180004bba  jnz     short loc_180004BC1
0x180004bbc  mov     cl, r10b
0x180004bbf  jmp     short loc_180004BCE
0x180004bc1  mov     cl, [rdx]
0x180004bc3  inc     rdx
0x180004bc6  sub     eax, 1
0x180004bc9  mov     [r8], eax
0x180004bcc  jnz     short loc_180004BD3
0x180004bce  mov     dil, r10b
0x180004bd1  jmp     short loc_180004BE1
0x180004bd3  mov     dil, [rdx]
0x180004bd6  inc     rdx
0x180004bd9  sub     eax, 1
0x180004bdc  mov     [r8], eax
0x180004bdf  jnz     short loc_180004BE6
0x180004be1  mov     r9b, r10b
0x180004be4  jmp     short loc_180004BF1
0x180004be6  mov     r9b, [rdx]
0x180004be9  inc     rdx
0x180004bec  dec     eax
0x180004bee  mov     [r8], eax
0x180004bf1  movzx   eax, r9b
0x180004bf5  mov     r15d, 2
0x180004bfb  movzx   ecx, cl
0x180004bfe  mov     esi, eax
0x180004c00  shl     esi, 8
0x180004c03  mov     r12, r14
0x180004c06  or      esi, eax
0x180004c08  lea     r14, ExpansionTable
0x180004c0f  shl     esi, 8
0x180004c12  or      esi, ecx
0x180004c14  movzx   eax, dil
0x180004c18  shl     esi, 8
0x180004c1b  mov     r9d, eax
0x180004c1e  shl     r9d, 8
0x180004c22  or      esi, ecx
0x180004c24  or      r9d, eax
0x180004c27  movzx   ecx, bpl
0x180004c2b  shl     r9d, 8
0x180004c2f  mov     ebp, r15d
0x180004c32  or      r9d, ecx
0x180004c35  shl     r9d, 8
0x180004c39  or      r9d, ecx
0x180004c3c  xor     r9d, esi
0x180004c3f  or      edi, 0FFFFFFFFh
0x180004c42  movzx   eax, r11w
0x180004c46  and     eax, 0Fh
0x180004c49  shr     r11w, 4
0x180004c4e  mov     ecx, [r14+rax*4]
0x180004c52  and     ecx, r9d
0x180004c55  xor     ecx, esi
0x180004c57  mov     [rbx], ecx
0x180004c59  add     rbx, r12
0x180004c5c  add     ebp, edi
0x180004c5e  jnz     short loc_180004C42
0x180004c60  mov     eax, [r8]
0x180004c63  test    eax, eax
0x180004c65  jnz     short loc_180004C6C
0x180004c67  mov     bpl, r10b
0x180004c6a  jmp     short loc_180004C7A
0x180004c6c  mov     bpl, [rdx]
0x180004c6f  inc     rdx
0x180004c72  sub     eax, 1
0x180004c75  mov     [r8], eax
0x180004c78  jnz     short loc_180004C7F
0x180004c7a  mov     r9b, r10b
0x180004c7d  jmp     short loc_180004C8D
0x180004c7f  mov     r9b, [rdx]
0x180004c82  inc     rdx
0x180004c85  sub     eax, 1
0x180004c88  mov     [r8], eax
0x180004c8b  jnz     short loc_180004C92
0x180004c8d  mov     sil, r10b
0x180004c90  jmp     short loc_180004CAB
0x180004c92  mov     sil, [rdx]
0x180004c95  inc     rdx
0x180004c98  sub     eax, 1
0x180004c9b  mov     [r8], eax
0x180004c9e  jz      short loc_180004CAB
0x180004ca0  mov     r10b, [rdx]
0x180004ca3  inc     rdx
0x180004ca6  dec     eax
0x180004ca8  mov     [r8], eax
0x180004cab  movzx   ecx, r9b
0x180004caf  movzx   eax, r10b
0x180004cb3  mov     r9d, eax
0x180004cb6  shl     r9d, 8
0x180004cba  or      r9d, eax
0x180004cbd  movzx   eax, sil
0x180004cc1  shl     r9d, 8
0x180004cc5  mov     r8d, eax
0x180004cc8  shl     r8d, 8
0x180004ccc  or      r9d, ecx
0x180004ccf  or      r8d, eax
0x180004cd2  shl     r9d, 8
0x180004cd6  shl     r8d, 8
0x180004cda  or      r9d, ecx
0x180004cdd  movzx   ecx, bpl
0x180004ce1  or      r8d, ecx
0x180004ce4  shl     r8d, 8
0x180004ce8  or      r8d, ecx
0x180004ceb  xor     r8d, r9d
0x180004cee  movzx   eax, r11w
0x180004cf2  and     eax, 0Fh
0x180004cf5  shr     r11w, 4
0x180004cfa  mov     ecx, [r14+rax*4]
0x180004cfe  and     ecx, r8d
0x180004d01  xor     ecx, r9d
0x180004d04  mov     [rbx], ecx
0x180004d06  add     rbx, r12
0x180004d09  add     r15d, edi
0x180004d0c  jnz     short loc_180004CEE
0x180004d0e  jmp     loc_180004DA6
0x180004d13  mov     rdx, r9
0x180004d16  test    eax, eax
0x180004d18  jnz     short loc_180004D1F
0x180004d1a  mov     dil, r10b
0x180004d1d  jmp     short loc_180004D38
0x180004d1f  mov     dil, [rdx]
0x180004d22  inc     rdx
0x180004d25  sub     eax, 1
0x180004d28  mov     [r8], eax
0x180004d2b  jz      short loc_180004D38
0x180004d2d  mov     r10b, [rdx]
0x180004d30  inc     rdx
0x180004d33  dec     eax
0x180004d35  mov     [r8], eax
0x180004d38  movzx   eax, r10b
0x180004d3c  mov     rsi, r14
0x180004d3f  mov     r9d, eax
0x180004d42  lea     r14, ExpansionTable
0x180004d49  shl     r9d, 8
0x180004d4d  mov     r10d, 4
0x180004d53  or      r9d, eax
0x180004d56  shl     r9d, 8
0x180004d5a  or      r9d, eax
0x180004d5d  shl     r9d, 8
0x180004d61  or      r9d, eax
0x180004d64  movzx   eax, dil
0x180004d68  mov     r8d, eax
0x180004d6b  shl     r8d, 8
0x180004d6f  or      r8d, eax
0x180004d72  shl     r8d, 8
0x180004d76  or      r8d, eax
0x180004d79  shl     r8d, 8
0x180004d7d  or      r8d, eax
0x180004d80  xor     r8d, r9d
0x180004d83  or      edi, 0FFFFFFFFh
0x180004d86  movzx   eax, r11w
0x180004d8a  and     eax, 0Fh
0x180004d8d  shr     r11w, 4
0x180004d92  mov     ecx, [r14+rax*4]
0x180004d96  and     ecx, r8d
0x180004d99  xor     ecx, r9d
0x180004d9c  mov     [rbx], ecx
0x180004d9e  add     rbx, rsi
0x180004da1  add     r10d, edi
0x180004da4  jnz     short loc_180004D86
0x180004da6  mov     rax, rdx
0x180004da9  pop     r15
0x180004dab  pop     r14
0x180004dad  pop     r12
0x180004daf  pop     rdi
0x180004db0  pop     rsi
0x180004db1  pop     rbp
0x180004db2  pop     rbx
0x180004db3  retn
```
