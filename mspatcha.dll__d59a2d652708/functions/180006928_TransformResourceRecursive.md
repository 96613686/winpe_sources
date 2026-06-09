# TransformResourceRecursive

- ea: `0x180006928`
- end: `0x180006a57`
- name: `TransformResourceRecursive`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000677c`
- `0x180006928`

## callees

- `0x180004cc4`
- `0x180006928`

## pseudocode

```c
void __fastcall TransformResourceRecursive(__int64 a1, unsigned __int64 a2)
{
  int *v3; // rdi
  unsigned int v4; // eax
  int v5; // eax
  int i; // esi
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  unsigned int *v10; // r11
  int NewRvaFromRiftTable; // eax
  _DWORD *v12; // r11
  int v13; // eax
  int v14; // r11d
  int v15; // eax
  int v16; // r11d

  if ( a2 < *(_QWORD *)(a1 + 8)
    || (v3 = (int *)(a2 + 16), a2 + 16 > *(_QWORD *)(a1 + 16))
    || (v4 = *(_DWORD *)(a1 + 28) + 16, *(_DWORD *)(a1 + 28) = v4, v4 > *(_DWORD *)(a1 + 24)) )
  {
LABEL_13:
    *(_DWORD *)(a1 + 56) = 1;
  }
  else
  {
    v5 = *(_DWORD *)(a1 + 32);
    if ( *(_DWORD *)(a2 + 4) != v5 )
      *(_DWORD *)(a2 + 4) = v5;
    for ( i = *(unsigned __int16 *)(a2 + 12) + *(unsigned __int16 *)(a2 + 14); i; --i )
    {
      if ( (unsigned __int64)(v3 + 2) > *(_QWORD *)(a1 + 16) )
        goto LABEL_13;
      *(_DWORD *)(a1 + 28) += 8;
      v7 = *(unsigned int *)(a1 + 24);
      if ( *(_DWORD *)(a1 + 28) > (unsigned int)v7 )
        goto LABEL_13;
      v8 = (unsigned int)v3[1];
      if ( (int)v8 >= 0 )
      {
        v10 = (unsigned int *)(*(_QWORD *)(a1 + 8) + v8);
        if ( (unsigned __int64)v10 >= *(_QWORD *)(a1 + 8) && (unsigned __int64)(v10 + 4) <= *(_QWORD *)(a1 + 16) )
        {
          NewRvaFromRiftTable = GetNewRvaFromRiftTable(*(int **)a1, *v10);
          if ( *v12 != NewRvaFromRiftTable )
            *v12 = NewRvaFromRiftTable;
          goto LABEL_20;
        }
      }
      else if ( (unsigned int)v7 >= 0x10 )
      {
        v9 = v8 & 0x7FFFFFFF;
        if ( v9 <= v7 - 16 )
        {
          TransformResourceRecursive(a1, *(_QWORD *)(a1 + 8) + v9);
          if ( *(_DWORD *)(a1 + 28) > *(_DWORD *)(a1 + 24) )
            goto LABEL_13;
          goto LABEL_20;
        }
      }
      *(_DWORD *)(a1 + 56) = 1;
LABEL_20:
      v13 = GetNewRvaFromRiftTable(*(int **)a1, (v3[1] & 0x7FFFFFFFu) + *(_DWORD *)(a1 + 48)) - *(_DWORD *)(a1 + 52);
      if ( v14 != v13 )
        v3[1] ^= (v3[1] ^ v13) & 0x7FFFFFFF;
      if ( *v3 < 0 )
      {
        v15 = GetNewRvaFromRiftTable(*(int **)a1, (*v3 & 0x7FFFFFFFu) + *(_DWORD *)(a1 + 48)) - *(_DWORD *)(a1 + 52);
        if ( v16 != v15 )
          *v3 ^= (*v3 ^ v15) & 0x7FFFFFFF;
      }
      v3 += 2;
    }
  }
}

```

## disassembly

```asm
0x180006928  push    rbx
0x18000692a  push    rbp
0x18000692b  push    rsi
0x18000692c  push    rdi
0x18000692d  push    r14
0x18000692f  sub     rsp, 20h
0x180006933  mov     rbx, rcx
0x180006936  cmp     rdx, [rcx+8]
0x18000693a  jb      short loc_1800069B3
0x18000693c  lea     rdi, [rdx+10h]
0x180006940  cmp     rdi, [rcx+10h]
0x180006944  ja      short loc_1800069B3
0x180006946  mov     eax, [rcx+1Ch]
0x180006949  add     eax, 10h
0x18000694c  mov     [rcx+1Ch], eax
0x18000694f  cmp     eax, [rcx+18h]
0x180006952  ja      short loc_1800069B3
0x180006954  mov     eax, [rcx+20h]
0x180006957  cmp     [rdx+4], eax
0x18000695a  jz      short loc_18000695F
0x18000695c  mov     [rdx+4], eax
0x18000695f  movzx   esi, word ptr [rdx+0Eh]
0x180006963  movzx   eax, word ptr [rdx+0Ch]
0x180006967  add     esi, eax
0x180006969  jz      short loc_1800069BA
0x18000696b  mov     r14d, 7FFFFFFFh
0x180006971  lea     rbp, [rdi+8]
0x180006975  cmp     rbp, [rbx+10h]
0x180006979  ja      short loc_1800069B3
0x18000697b  add     dword ptr [rbx+1Ch], 8
0x18000697f  mov     eax, [rbx+18h]
0x180006982  cmp     [rbx+1Ch], eax
0x180006985  ja      short loc_1800069B3
0x180006987  mov     edx, [rdi+4]
0x18000698a  test    edx, edx
0x18000698c  jns     short loc_1800069C5
0x18000698e  cmp     eax, 10h
0x180006991  jb      short loc_1800069F1
0x180006993  and     rdx, r14
0x180006996  sub     rax, 10h
0x18000699a  cmp     rdx, rax
0x18000699d  ja      short loc_1800069F1
0x18000699f  add     rdx, [rbx+8]
0x1800069a3  mov     rcx, rbx
0x1800069a6  call    TransformResourceRecursive
0x1800069ab  mov     eax, [rbx+18h]
0x1800069ae  cmp     [rbx+1Ch], eax
0x1800069b1  jbe     short loc_1800069F8
0x1800069b3  mov     dword ptr [rbx+38h], 1
0x1800069ba  add     rsp, 20h
0x1800069be  pop     r14
0x1800069c0  pop     rdi
0x1800069c1  pop     rsi
0x1800069c2  pop     rbp
0x1800069c3  pop     rbx
0x1800069c4  retn
0x1800069c5  mov     r11, rdx
0x1800069c8  add     r11, [rbx+8]
0x1800069cc  cmp     r11, [rbx+8]
0x1800069d0  jb      short loc_1800069F1
0x1800069d2  lea     rax, [r11+10h]
0x1800069d6  cmp     rax, [rbx+10h]
0x1800069da  ja      short loc_1800069F1
0x1800069dc  mov     edx, [r11]
0x1800069df  mov     rcx, [rbx]
0x1800069e2  call    GetNewRvaFromRiftTable
0x1800069e7  cmp     [r11], eax
0x1800069ea  jz      short loc_1800069F8
0x1800069ec  mov     [r11], eax
0x1800069ef  jmp     short loc_1800069F8
0x1800069f1  mov     dword ptr [rbx+38h], 1
0x1800069f8  mov     edx, [rbx+30h]
0x1800069fb  mov     r11d, [rdi+4]
0x1800069ff  mov     rcx, [rbx]
0x180006a02  and     r11d, r14d
0x180006a05  add     edx, r11d
0x180006a08  call    GetNewRvaFromRiftTable
0x180006a0d  sub     eax, [rbx+34h]
0x180006a10  cmp     r11d, eax
0x180006a13  jz      short loc_180006A1E
0x180006a15  xor     eax, [rdi+4]
0x180006a18  and     eax, r14d
0x180006a1b  xor     [rdi+4], eax
0x180006a1e  cmp     dword ptr [rdi], 0
0x180006a21  jge     short loc_180006A46
0x180006a23  mov     edx, [rbx+30h]
0x180006a26  mov     r11d, [rdi]
0x180006a29  mov     rcx, [rbx]
0x180006a2c  and     r11d, r14d
0x180006a2f  add     edx, r11d
0x180006a32  call    GetNewRvaFromRiftTable
0x180006a37  sub     eax, [rbx+34h]
0x180006a3a  cmp     r11d, eax
0x180006a3d  jz      short loc_180006A46
0x180006a3f  xor     eax, [rdi]
0x180006a41  and     eax, r14d
0x180006a44  xor     [rdi], eax
0x180006a46  mov     rdi, rbp
0x180006a49  add     esi, 0FFFFFFFFh
0x180006a4c  jnz     loc_180006971
0x180006a52  jmp     loc_1800069BA
```
