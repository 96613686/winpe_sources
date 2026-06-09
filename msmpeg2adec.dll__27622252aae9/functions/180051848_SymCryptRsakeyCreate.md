# SymCryptRsakeyCreate

- ea: `0x180051848`
- end: `0x1800519ee`
- name: `SymCryptRsakeyCreate`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180051538`

## callees

- `0x180009170`
- `0x180051848`
- `0x180052444`
- `0x1800550b8`
- `0x18005796c`

## pseudocode

```c
__int64 __fastcall SymCryptRsakeyCreate(__int64 a1, unsigned __int64 a2, _DWORD *a3)
{
  __int64 v6; // r14
  unsigned __int64 v7; // rbp
  int v8; // r8d
  unsigned int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // r9d
  unsigned int v19; // eax
  __int64 i; // r8
  int v21; // ecx
  unsigned int v22; // ecx
  __int64 v23; // r8
  int v24; // ecx
  __int64 v25; // rcx

  v6 = 0;
  v7 = (unsigned int)SymCryptSizeofRsakeyFromParams(a3);
  if ( a2 >= v7 && (unsigned int)(a3[1] - 256) <= 0xFF00 && a3[3] == 1 && (a3[2] & 0xFFFFFFFD) == 0 )
  {
    v6 = a1;
    SymCryptWipeAsm(a1, a2);
    *(_DWORD *)(a1 + 12) = a3[1];
    *(_DWORD *)(a1 + 4) = v7;
    *(_BYTE *)(a1 + 8) = 0;
    v8 = SymCryptDigitsFromBits();
    *(_DWORD *)(a1 + 20) = v8;
    *(_DWORD *)(a1 + 28) = a3[2];
    *(_DWORD *)(a1 + 24) = a3[3];
    if ( (unsigned int)(v8 - 1) > 0x7FF )
      v9 = 0;
    else
      v9 = 192 * v8 + 128;
    v10 = v9;
    v11 = SymCryptFdefModulusCreate(a1 + 192, v9);
    v12 = 0;
    *(_QWORD *)(a1 + 120) = v11;
    v13 = v10 + a1 + 192;
    if ( *(_DWORD *)(a1 + 28) )
    {
      do
      {
        *(_QWORD *)(a1 + 8 * v12 + 64) = v13;
        v14 = *(_DWORD *)(a1 + 20);
        if ( (unsigned int)(v14 - 1) > 0x7FF )
          v15 = 0;
        else
          v15 = (unsigned int)(192 * v14 + 128);
        v13 += v15;
        v12 = (unsigned int)(v12 + 1);
        v16 = *(_DWORD *)(a1 + 28);
      }
      while ( (unsigned int)v12 < v16 );
      if ( v16 )
      {
        v17 = 0;
        v18 = ((a3[1] >> 9) + (((a3[1] & 0x1FFu) + 511) >> 9)) << 6;
        do
        {
          *(_QWORD *)(a1 + 8 * v17 + 80) = v13;
          v13 += v18;
          v17 = (unsigned int)(v17 + 1);
        }
        while ( (unsigned int)v17 < *(_DWORD *)(a1 + 28) );
      }
    }
    v19 = *(_DWORD *)(a1 + 24);
    for ( i = 0; (unsigned int)i < v19; v19 = *(_DWORD *)(a1 + 24) )
    {
      *(_QWORD *)(a1 + 8 * i + 96) = v13;
      v21 = *(_DWORD *)(a1 + 20);
      if ( (unsigned int)(v21 - 1) > 0x7FF )
        v22 = 0;
      else
        v22 = (v21 << 6) + 32;
      i = (unsigned int)(i + 1);
      v13 += v22;
    }
    v23 = 0;
    if ( *(_DWORD *)(a1 + 28) * v19 )
    {
      do
      {
        *(_QWORD *)(a1 + 8 * v23 + 104) = v13;
        v24 = *(_DWORD *)(a1 + 20);
        if ( (unsigned int)(v24 - 1) > 0x7FF )
          v25 = 0;
        else
          v25 = (unsigned int)((v24 << 6) + 32);
        v13 += v25;
        v23 = (unsigned int)(v23 + 1);
      }
      while ( (unsigned int)v23 < *(_DWORD *)(a1 + 28) * *(_DWORD *)(a1 + 24) );
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180051848  push    rbx
0x18005184a  push    rbp
0x18005184b  push    rsi
0x18005184c  push    rdi
0x18005184d  push    r12
0x18005184f  push    r14
0x180051851  sub     rsp, 28h
0x180051855  mov     rdi, rcx
0x180051858  mov     rsi, r8
0x18005185b  mov     rcx, r8
0x18005185e  mov     rbx, rdx
0x180051861  xor     r14d, r14d
0x180051864  call    SymCryptSizeofRsakeyFromParams
0x180051869  mov     ebp, eax
0x18005186b  cmp     rbx, rbp
0x18005186e  jb      loc_1800519DD
0x180051874  mov     eax, [rsi+4]
0x180051877  sub     eax, 100h
0x18005187c  cmp     eax, 0FF00h
0x180051881  ja      loc_1800519DD
0x180051887  cmp     dword ptr [rsi+0Ch], 1
0x18005188b  jnz     loc_1800519DD
0x180051891  test    dword ptr [rsi+8], 0FFFFFFFDh
0x180051898  jnz     loc_1800519DD
0x18005189e  mov     rdx, rbx
0x1800518a1  mov     rcx, rdi
0x1800518a4  mov     r14, rdi
0x1800518a7  call    SymCryptWipeAsm
0x1800518ac  mov     ecx, [rsi+4]
0x1800518af  mov     [rdi+0Ch], ecx
0x1800518b2  mov     [rdi+4], ebp
0x1800518b5  mov     byte ptr [rdi+8], 0
0x1800518b9  call    SymCryptDigitsFromBits
0x1800518be  mov     r8d, eax
0x1800518c1  mov     [rdi+14h], eax
0x1800518c4  mov     eax, [rsi+8]
0x1800518c7  lea     rbp, [rdi+0C0h]
0x1800518ce  mov     [rdi+1Ch], eax
0x1800518d1  mov     r12d, 7FFh
0x1800518d7  mov     eax, [rsi+0Ch]
0x1800518da  mov     [rdi+18h], eax
0x1800518dd  lea     eax, [r8-1]
0x1800518e1  cmp     eax, r12d
0x1800518e4  ja      short loc_1800518F2
0x1800518e6  lea     eax, [r8+r8*2]
0x1800518ea  shl     eax, 6
0x1800518ed  sub     eax, 0FFFFFF80h
0x1800518f0  jmp     short loc_1800518F4
0x1800518f2  xor     eax, eax
0x1800518f4  mov     edx, eax
0x1800518f6  mov     rcx, rbp
0x1800518f9  mov     ebx, eax
0x1800518fb  call    SymCryptFdefModulusCreate
0x180051900  xor     ecx, ecx
0x180051902  mov     [rdi+78h], rax
0x180051906  lea     rdx, [rbx+rbp]
0x18005190a  cmp     [rdi+1Ch], ecx
0x18005190d  jbe     short loc_180051972
0x18005190f  mov     [rdi+rcx*8+40h], rdx
0x180051914  mov     r8d, [rdi+14h]
0x180051918  lea     eax, [r8-1]
0x18005191c  cmp     eax, r12d
0x18005191f  ja      short loc_18005192D
0x180051921  lea     eax, [r8+r8*2]
0x180051925  shl     eax, 6
0x180051928  sub     eax, 0FFFFFF80h
0x18005192b  jmp     short loc_18005192F
0x18005192d  xor     eax, eax
0x18005192f  add     rdx, rax
0x180051932  inc     ecx
0x180051934  mov     eax, [rdi+1Ch]
0x180051937  cmp     ecx, eax
0x180051939  jb      short loc_18005190F
0x18005193b  test    eax, eax
0x18005193d  jz      short loc_180051972
0x18005193f  mov     eax, [rsi+4]
0x180051942  mov     r9d, 1FFh
0x180051948  mov     ecx, eax
0x18005194a  xor     r8d, r8d
0x18005194d  and     ecx, r9d
0x180051950  shr     eax, 9
0x180051953  add     r9d, ecx
0x180051956  shr     r9d, 9
0x18005195a  add     r9d, eax
0x18005195d  shl     r9d, 6
0x180051961  mov     [rdi+r8*8+50h], rdx
0x180051966  add     rdx, r9
0x180051969  inc     r8d
0x18005196c  cmp     r8d, [rdi+1Ch]
0x180051970  jb      short loc_180051961
0x180051972  mov     eax, [rdi+18h]
0x180051975  xor     r8d, r8d
0x180051978  test    eax, eax
0x18005197a  jz      short loc_1800519A6
0x18005197c  mov     [rdi+r8*8+60h], rdx
0x180051981  mov     ecx, [rdi+14h]
0x180051984  lea     eax, [rcx-1]
0x180051987  cmp     eax, r12d
0x18005198a  ja      short loc_180051994
0x18005198c  shl     ecx, 6
0x18005198f  add     ecx, 20h ; ' '
0x180051992  jmp     short loc_180051996
0x180051994  xor     ecx, ecx
0x180051996  mov     eax, ecx
0x180051998  inc     r8d
0x18005199b  add     rdx, rax
0x18005199e  mov     eax, [rdi+18h]
0x1800519a1  cmp     r8d, eax
0x1800519a4  jb      short loc_18005197C
0x1800519a6  imul    eax, [rdi+1Ch]
0x1800519aa  xor     r8d, r8d
0x1800519ad  test    eax, eax
0x1800519af  jz      short loc_1800519DD
0x1800519b1  mov     [rdi+r8*8+68h], rdx
0x1800519b6  mov     ecx, [rdi+14h]
0x1800519b9  lea     eax, [rcx-1]
0x1800519bc  cmp     eax, r12d
0x1800519bf  ja      short loc_1800519C9
0x1800519c1  shl     ecx, 6
0x1800519c4  add     ecx, 20h ; ' '
0x1800519c7  jmp     short loc_1800519CB
0x1800519c9  xor     ecx, ecx
0x1800519cb  add     rdx, rcx
0x1800519ce  inc     r8d
0x1800519d1  mov     ecx, [rdi+18h]
0x1800519d4  imul    ecx, [rdi+1Ch]
0x1800519d8  cmp     r8d, ecx
0x1800519db  jb      short loc_1800519B1
0x1800519dd  mov     rax, r14
0x1800519e0  add     rsp, 28h
0x1800519e4  pop     r14
0x1800519e6  pop     r12
0x1800519e8  pop     rdi
0x1800519e9  pop     rsi
0x1800519ea  pop     rbp
0x1800519eb  pop     rbx
0x1800519ec  retn
```
