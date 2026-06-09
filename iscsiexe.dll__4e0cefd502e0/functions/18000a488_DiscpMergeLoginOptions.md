# DiscpMergeLoginOptions

- ea: `0x18000a488`
- end: `0x18000a740`
- name: `DiscpMergeLoginOptions`
- size: `696`
- prototype: `__int64 __fastcall(__int64, _BYTE *, _BYTE *, _BYTE *, char)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fb8`
- `0x180006c30`
- `0x180009898`

## callees

- `0x180001cfe`
- `0x18000a488`

## pseudocode

```c
__int64 __fastcall DiscpMergeLoginOptions(__int64 a1, _BYTE *a2, _BYTE *a3, _BYTE *a4, char a5)
{
  _BYTE *v9; // rdx
  _BYTE *v10; // rcx
  _BYTE *v11; // r8
  int v12; // r10d
  unsigned int v13; // r9d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 result; // rax
  int v20; // eax
  _BYTE v21[104]; // [rsp+20h] [rbp-68h] BYREF

  memset_0((void *)a1, 0, 0x40u);
  memset_0(v21, 0, 0x40u);
  v9 = v21;
  v10 = v21;
  if ( a2 )
    v9 = a2;
  v11 = v21;
  if ( a3 )
    v10 = a3;
  if ( a4 )
    v11 = a4;
  v12 = *((_DWORD *)v10 + 1) | *((_DWORD *)v11 + 1) | *((_DWORD *)v9 + 1);
  v13 = v12 & 0xFFFFFF1F;
  *(_DWORD *)(a1 + 4) = v12 & 0xFFFFFF1F;
  *(_DWORD *)(a1 + 8) = *((_DWORD *)v9 + 2) | *((_DWORD *)v10 + 2) | *((_DWORD *)v11 + 2);
  if ( (v12 & 0xFFFFFF1F) != 0 )
  {
    if ( (v12 & 1) != 0 )
    {
      if ( (v9[4] & 1) != 0 )
      {
        v14 = *((_DWORD *)v9 + 4);
      }
      else if ( (v10[4] & 1) != 0 )
      {
        v14 = *((_DWORD *)v10 + 4);
      }
      else
      {
        v14 = *((_DWORD *)v11 + 4);
      }
      *(_DWORD *)(a1 + 16) = v14;
    }
    if ( (v12 & 2) != 0 )
    {
      if ( (v9[4] & 2) != 0 )
      {
        v15 = *((_DWORD *)v9 + 5);
      }
      else if ( (v10[4] & 2) != 0 )
      {
        v15 = *((_DWORD *)v10 + 5);
      }
      else
      {
        v15 = *((_DWORD *)v11 + 5);
      }
      *(_DWORD *)(a1 + 20) = v15;
    }
    if ( (v12 & 4) != 0 )
    {
      if ( (v9[4] & 4) != 0 )
      {
        v16 = *((_DWORD *)v9 + 6);
      }
      else if ( (v10[4] & 4) != 0 )
      {
        v16 = *((_DWORD *)v10 + 6);
      }
      else
      {
        v16 = *((_DWORD *)v11 + 6);
      }
      *(_DWORD *)(a1 + 24) = v16;
    }
    if ( (v12 & 8) != 0 )
    {
      if ( (v9[4] & 8) != 0 )
      {
        v17 = *((_DWORD *)v9 + 7);
      }
      else if ( (v10[4] & 8) != 0 )
      {
        v17 = *((_DWORD *)v10 + 7);
      }
      else
      {
        v17 = *((_DWORD *)v11 + 7);
      }
      *(_DWORD *)(a1 + 28) = v17;
    }
    if ( (v12 & 0x10) != 0 )
    {
      if ( (v9[4] & 0x10) != 0 )
      {
        v18 = *((_DWORD *)v9 + 8);
      }
      else if ( (v10[4] & 0x10) != 0 )
      {
        v18 = *((_DWORD *)v10 + 8);
      }
      else
      {
        v18 = *((_DWORD *)v11 + 8);
      }
      *(_DWORD *)(a1 + 32) = v18;
    }
  }
  result = *((_DWORD *)v9 + 1) & 0x80;
  if ( !a5 )
  {
    if ( (_DWORD)result )
    {
      *(_DWORD *)(a1 + 4) = v13 | 0x80;
      v20 = *((_DWORD *)v9 + 3);
    }
    else if ( (v10[4] & 0x80) != 0 )
    {
      *(_DWORD *)(a1 + 4) = v13 | 0x80;
      v20 = *((_DWORD *)v10 + 3);
    }
    else
    {
      if ( (v11[4] & 0x80) == 0 )
        goto LABEL_59;
      *(_DWORD *)(a1 + 4) = v13 | 0x80;
      v20 = *((_DWORD *)v11 + 3);
    }
    *(_DWORD *)(a1 + 12) = v20;
LABEL_59:
    result = 32;
    if ( (v9[4] & 0x20) != 0 )
    {
      *(_DWORD *)(a1 + 4) |= 0x20u;
      *(_QWORD *)(a1 + 48) = *((_QWORD *)v9 + 6);
      result = *((unsigned int *)v9 + 9);
    }
    else if ( (v10[4] & 0x20) != 0 )
    {
      *(_DWORD *)(a1 + 4) |= 0x20u;
      *(_QWORD *)(a1 + 48) = *((_QWORD *)v10 + 6);
      result = *((unsigned int *)v10 + 9);
    }
    else
    {
      if ( (v11[4] & 0x20) == 0 )
      {
LABEL_66:
        if ( (v9[4] & 0x40) != 0 )
        {
          *(_DWORD *)(a1 + 4) |= 0x40u;
          goto LABEL_46;
        }
        if ( (v10[4] & 0x40) != 0 )
        {
          *(_DWORD *)(a1 + 4) |= 0x40u;
          goto LABEL_49;
        }
        if ( (v11[4] & 0x40) == 0 )
          return result;
        *(_DWORD *)(a1 + 4) |= 0x40u;
LABEL_72:
        *(_QWORD *)(a1 + 56) = *((_QWORD *)v11 + 7);
        result = *((unsigned int *)v11 + 10);
        goto LABEL_73;
      }
      *(_DWORD *)(a1 + 4) |= 0x20u;
      *(_QWORD *)(a1 + 48) = *((_QWORD *)v11 + 6);
      result = *((unsigned int *)v11 + 9);
    }
    *(_DWORD *)(a1 + 36) = result;
    goto LABEL_66;
  }
  if ( !(_DWORD)result )
  {
    if ( (v10[4] & 0x80) != 0 )
    {
      *(_DWORD *)(a1 + 4) = v12 ^ (*((_DWORD *)v10 + 1) ^ v12) & 0xE0;
      *(_DWORD *)(a1 + 12) = *((_DWORD *)v10 + 3);
      *(_QWORD *)(a1 + 48) = *((_QWORD *)v10 + 6);
      *(_DWORD *)(a1 + 36) = *((_DWORD *)v10 + 9);
LABEL_49:
      *(_QWORD *)(a1 + 56) = *((_QWORD *)v10 + 7);
      result = *((unsigned int *)v10 + 10);
      goto LABEL_73;
    }
    if ( (v11[4] & 0x80) == 0 )
      return result;
    *(_DWORD *)(a1 + 4) = v12 ^ (*((_DWORD *)v11 + 1) ^ v12) & 0xE0;
    *(_DWORD *)(a1 + 12) = *((_DWORD *)v11 + 3);
    *(_QWORD *)(a1 + 48) = *((_QWORD *)v11 + 6);
    *(_DWORD *)(a1 + 36) = *((_DWORD *)v11 + 9);
    goto LABEL_72;
  }
  *(_DWORD *)(a1 + 4) = v12 ^ (*((_DWORD *)v9 + 1) ^ v12) & 0xE0;
  *(_DWORD *)(a1 + 12) = *((_DWORD *)v9 + 3);
  *(_QWORD *)(a1 + 48) = *((_QWORD *)v9 + 6);
  *(_DWORD *)(a1 + 36) = *((_DWORD *)v9 + 9);
LABEL_46:
  *(_QWORD *)(a1 + 56) = *((_QWORD *)v9 + 7);
  result = *((unsigned int *)v9 + 10);
LABEL_73:
  *(_DWORD *)(a1 + 40) = result;
  return result;
}

```

## disassembly

```asm
0x18000a488  push    rbx
0x18000a48a  push    rbp
0x18000a48b  push    rsi
0x18000a48c  push    rdi
0x18000a48d  push    r14
0x18000a48f  sub     rsp, 60h
0x18000a493  mov     rdi, r8
0x18000a496  mov     rbx, rdx
0x18000a499  mov     r14d, 40h ; '@'
0x18000a49f  xor     edx, edx; Val
0x18000a4a1  mov     r8d, r14d; Size
0x18000a4a4  mov     rsi, r9
0x18000a4a7  mov     rbp, rcx
0x18000a4aa  call    memset_0
0x18000a4af  mov     r8d, r14d; Size
0x18000a4b2  lea     rcx, [rsp+88h+var_68]; void *
0x18000a4b7  xor     edx, edx; Val
0x18000a4b9  call    memset_0
0x18000a4be  test    rbx, rbx
0x18000a4c1  lea     rdx, [rsp+88h+var_68]
0x18000a4c6  lea     rcx, [rsp+88h+var_68]
0x18000a4cb  cmovnz  rdx, rbx
0x18000a4cf  lea     r8, [rsp+88h+var_68]
0x18000a4d4  test    rdi, rdi
0x18000a4d7  cmovnz  rcx, rdi
0x18000a4db  test    rsi, rsi
0x18000a4de  mov     r10d, [rdx+4]
0x18000a4e2  cmovnz  r8, rsi
0x18000a4e6  or      r10d, [r8+4]
0x18000a4ea  or      r10d, [rcx+4]
0x18000a4ee  mov     r9d, r10d
0x18000a4f1  and     r9d, 0FFFFFF1Fh
0x18000a4f8  mov     [rbp+4], r9d
0x18000a4fc  mov     eax, [r8+8]
0x18000a500  or      eax, [rcx+8]
0x18000a503  or      eax, [rdx+8]
0x18000a506  mov     [rbp+8], eax
0x18000a509  test    r9d, r9d
0x18000a50c  jz      loc_18000A5BC
0x18000a512  mov     al, 1
0x18000a514  test    al, r9b
0x18000a517  jz      short loc_18000A534
0x18000a519  test    [rdx+4], al
0x18000a51c  jz      short loc_18000A523
0x18000a51e  mov     eax, [rdx+10h]
0x18000a521  jmp     short loc_18000A531
0x18000a523  test    [rcx+4], al
0x18000a526  jz      short loc_18000A52D
0x18000a528  mov     eax, [rcx+10h]
0x18000a52b  jmp     short loc_18000A531
0x18000a52d  mov     eax, [r8+10h]
0x18000a531  mov     [rbp+10h], eax
0x18000a534  mov     al, 2
0x18000a536  test    al, r9b
0x18000a539  jz      short loc_18000A556
0x18000a53b  test    [rdx+4], al
0x18000a53e  jz      short loc_18000A545
0x18000a540  mov     eax, [rdx+14h]
0x18000a543  jmp     short loc_18000A553
0x18000a545  test    [rcx+4], al
0x18000a548  jz      short loc_18000A54F
0x18000a54a  mov     eax, [rcx+14h]
0x18000a54d  jmp     short loc_18000A553
0x18000a54f  mov     eax, [r8+14h]
0x18000a553  mov     [rbp+14h], eax
0x18000a556  mov     al, 4
0x18000a558  test    al, r9b
0x18000a55b  jz      short loc_18000A578
0x18000a55d  test    [rdx+4], al
0x18000a560  jz      short loc_18000A567
0x18000a562  mov     eax, [rdx+18h]
0x18000a565  jmp     short loc_18000A575
0x18000a567  test    [rcx+4], al
0x18000a56a  jz      short loc_18000A571
0x18000a56c  mov     eax, [rcx+18h]
0x18000a56f  jmp     short loc_18000A575
0x18000a571  mov     eax, [r8+18h]
0x18000a575  mov     [rbp+18h], eax
0x18000a578  mov     al, 8
0x18000a57a  test    al, r9b
0x18000a57d  jz      short loc_18000A59A
0x18000a57f  test    [rdx+4], al
0x18000a582  jz      short loc_18000A589
0x18000a584  mov     eax, [rdx+1Ch]
0x18000a587  jmp     short loc_18000A597
0x18000a589  test    [rcx+4], al
0x18000a58c  jz      short loc_18000A593
0x18000a58e  mov     eax, [rcx+1Ch]
0x18000a591  jmp     short loc_18000A597
0x18000a593  mov     eax, [r8+1Ch]
0x18000a597  mov     [rbp+1Ch], eax
0x18000a59a  mov     al, 10h
0x18000a59c  test    al, r9b
0x18000a59f  jz      short loc_18000A5BC
0x18000a5a1  test    [rdx+4], al
0x18000a5a4  jz      short loc_18000A5AB
0x18000a5a6  mov     eax, [rdx+20h]
0x18000a5a9  jmp     short loc_18000A5B9
0x18000a5ab  test    [rcx+4], al
0x18000a5ae  jz      short loc_18000A5B5
0x18000a5b0  mov     eax, [rcx+20h]
0x18000a5b3  jmp     short loc_18000A5B9
0x18000a5b5  mov     eax, [r8+20h]
0x18000a5b9  mov     [rbp+20h], eax
0x18000a5bc  mov     eax, [rdx+4]
0x18000a5bf  mov     r11d, 80h
0x18000a5c5  and     eax, r11d
0x18000a5c8  cmp     [rsp+88h+arg_20], 0
0x18000a5d0  jz      loc_18000A681
0x18000a5d6  test    eax, eax
0x18000a5d8  jz      short loc_18000A60F
0x18000a5da  mov     eax, r10d
0x18000a5dd  xor     eax, [rdx+4]
0x18000a5e0  and     eax, 0E0h
0x18000a5e5  xor     eax, r10d
0x18000a5e8  mov     [rbp+4], eax
0x18000a5eb  mov     eax, [rdx+0Ch]
0x18000a5ee  mov     [rbp+0Ch], eax
0x18000a5f1  mov     rax, [rdx+30h]
0x18000a5f5  mov     [rbp+30h], rax
0x18000a5f9  mov     eax, [rdx+24h]
0x18000a5fc  mov     [rbp+24h], eax
0x18000a5ff  mov     rax, [rdx+38h]
0x18000a603  mov     [rbp+38h], rax
0x18000a607  mov     eax, [rdx+28h]
0x18000a60a  jmp     loc_18000A732
0x18000a60f  test    [rcx+4], r11b
0x18000a613  jz      short loc_18000A64A
0x18000a615  mov     eax, r10d
0x18000a618  xor     eax, [rcx+4]
0x18000a61b  and     eax, 0E0h
0x18000a620  xor     eax, r10d
0x18000a623  mov     [rbp+4], eax
0x18000a626  mov     eax, [rcx+0Ch]
0x18000a629  mov     [rbp+0Ch], eax
0x18000a62c  mov     rax, [rcx+30h]
0x18000a630  mov     [rbp+30h], rax
0x18000a634  mov     eax, [rcx+24h]
0x18000a637  mov     [rbp+24h], eax
0x18000a63a  mov     rax, [rcx+38h]
0x18000a63e  mov     [rbp+38h], rax
0x18000a642  mov     eax, [rcx+28h]
0x18000a645  jmp     loc_18000A732
0x18000a64a  test    [r8+4], r11b
0x18000a64e  jz      loc_18000A735
0x18000a654  mov     eax, r10d
0x18000a657  xor     eax, [r8+4]
0x18000a65b  and     eax, 0E0h
0x18000a660  xor     eax, r10d
0x18000a663  mov     [rbp+4], eax
0x18000a666  mov     eax, [r8+0Ch]
0x18000a66a  mov     [rbp+0Ch], eax
0x18000a66d  mov     rax, [r8+30h]
0x18000a671  mov     [rbp+30h], rax
0x18000a675  mov     eax, [r8+24h]
0x18000a679  mov     [rbp+24h], eax
0x18000a67c  jmp     loc_18000A726
0x18000a681  test    eax, eax
0x18000a683  jz      short loc_18000A691
0x18000a685  or      r9d, r11d
0x18000a688  mov     [rbp+4], r9d
0x18000a68c  mov     eax, [rdx+0Ch]
0x18000a68f  jmp     short loc_18000A6B4
0x18000a691  test    [rcx+4], r11b
0x18000a695  jz      short loc_18000A6A3
0x18000a697  or      r9d, r11d
0x18000a69a  mov     [rbp+4], r9d
0x18000a69e  mov     eax, [rcx+0Ch]
0x18000a6a1  jmp     short loc_18000A6B4
0x18000a6a3  test    [r8+4], r11b
0x18000a6a7  jz      short loc_18000A6B7
0x18000a6a9  or      r9d, r11d
0x18000a6ac  mov     [rbp+4], r9d
0x18000a6b0  mov     eax, [r8+0Ch]
0x18000a6b4  mov     [rbp+0Ch], eax
0x18000a6b7  mov     eax, 20h ; ' '
0x18000a6bc  test    [rdx+4], al
0x18000a6bf  jz      short loc_18000A6D1
0x18000a6c1  or      [rbp+4], eax
0x18000a6c4  mov     rax, [rdx+30h]
0x18000a6c8  mov     [rbp+30h], rax
0x18000a6cc  mov     eax, [rdx+24h]
0x18000a6cf  jmp     short loc_18000A6FB
0x18000a6d1  test    [rcx+4], al
0x18000a6d4  jz      short loc_18000A6E6
0x18000a6d6  or      [rbp+4], eax
0x18000a6d9  mov     rax, [rcx+30h]
0x18000a6dd  mov     [rbp+30h], rax
0x18000a6e1  mov     eax, [rcx+24h]
0x18000a6e4  jmp     short loc_18000A6FB
0x18000a6e6  test    [r8+4], al
0x18000a6ea  jz      short loc_18000A6FE
0x18000a6ec  or      [rbp+4], eax
0x18000a6ef  mov     rax, [r8+30h]
0x18000a6f3  mov     [rbp+30h], rax
0x18000a6f7  mov     eax, [r8+24h]
0x18000a6fb  mov     [rbp+24h], eax
0x18000a6fe  test    [rdx+4], r14b
0x18000a702  jz      short loc_18000A70D
0x18000a704  or      [rbp+4], r14d
0x18000a708  jmp     loc_18000A5FF
0x18000a70d  test    [rcx+4], r14b
0x18000a711  jz      short loc_18000A71C
0x18000a713  or      [rbp+4], r14d
0x18000a717  jmp     loc_18000A63A
0x18000a71c  test    [r8+4], r14b
0x18000a720  jz      short loc_18000A735
0x18000a722  or      [rbp+4], r14d
0x18000a726  mov     rax, [r8+38h]
0x18000a72a  mov     [rbp+38h], rax
0x18000a72e  mov     eax, [r8+28h]
0x18000a732  mov     [rbp+28h], eax
0x18000a735  add     rsp, 60h
0x18000a739  pop     r14
0x18000a73b  pop     rdi
0x18000a73c  pop     rsi
0x18000a73d  pop     rbp
0x18000a73e  pop     rbx
0x18000a73f  retn
```
