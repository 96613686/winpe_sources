# RtlImageDirectoryEntryToData

- ea: `0x180066020`
- end: `0x1800661d0`
- name: `RtlImageDirectoryEntryToData`
- size: `432`
- prototype: ``
- caller_count: `26`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180028620`
- `0x180057760`
- `0x180060fc8`
- `0x18006596c`
- `0x180065ab0`
- `0x180065c60`
- `0x180065e70`
- `0x1800668e0`
- `0x180068f24`
- `0x180069678`
- `0x1800ac3d0`
- `0x1800bdfb0`
- `0x1800c5394`
- `0x1800d0504`
- `0x1800d0a5c`
- `0x1800d6508`
- `0x1800fc74c`
- `0x1800fca24`
- `0x1800fe050`
- `0x180104fe0`
- `0x1801097c0`
- `0x18010c520`
- `0x180136ed4`
- `0x18013ab40`
- `0x18015bb68`
- `0x18015bc68`

## callees

- `0x18001f070`
- `0x180066020`
- `0x1800680b0`

## pseudocode

```c
__int64 __fastcall RtlImageDirectoryEntryToData(__int64 a1, char a2, unsigned __int16 a3, _DWORD *a4)
{
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // r9
  __int16 v12; // ax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // r10
  unsigned int v17; // r11d
  unsigned int *v18; // rdx
  unsigned int i; // r8d
  __int64 v20; // r9
  char v21; // cl
  int v22; // ecx
  __int64 v23; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v6 = a3;
  v7 = a1 & 1;
  v23 = 0;
  v9 = a1;
  if ( (a1 & 2) != 0 || (a1 & 1) != 0 )
  {
    v21 = 0;
    v9 &= 0xFFFFFFFFFFFFFFFCuLL;
    if ( !v7 )
      v21 = a2;
    a2 = v21;
  }
  v10 = RtlImageNtHeaderEx(1, v9, 0, &v23);
  v11 = v23;
  if ( !v23 )
    goto LABEL_11;
  v12 = *(_WORD *)(v23 + 24);
  if ( v12 == 267 )
  {
    if ( (unsigned int)v6 < *(_DWORD *)(v23 + 116) )
    {
      v16 = *(unsigned int *)(v23 + 8 * v6 + 120);
      if ( !(_DWORD)v16 )
        goto LABEL_28;
      *a4 = *(_DWORD *)(v23 + 8 * v6 + 124);
      if ( a2 || (unsigned int)v16 < *(_DWORD *)(v11 + 84) )
      {
        v5 = v9 + v16;
        v10 = 0;
        goto LABEL_11;
      }
      v17 = *(unsigned __int16 *)(v11 + 6);
      v18 = (unsigned int *)(v11 + *(unsigned __int16 *)(v11 + 20) + 24LL);
      for ( i = 0; i < v17; ++i )
      {
        v20 = v18[3];
        if ( (unsigned int)v16 >= (unsigned int)v20 && (unsigned int)v16 < (unsigned int)v20 + v18[4] )
        {
          v5 = v9 + v18[5] - v20 + v16;
          if ( v5 )
            goto LABEL_10;
          break;
        }
        v18 += 10;
      }
    }
LABEL_24:
    v10 = -1073741811;
    goto LABEL_11;
  }
  if ( v12 != 523 || (unsigned int)v6 >= *(_DWORD *)(v23 + 132) )
    goto LABEL_24;
  v13 = *(unsigned int *)(v23 + 8 * v6 + 136);
  if ( !(_DWORD)v13 )
  {
LABEL_28:
    v10 = -1073741822;
    goto LABEL_11;
  }
  *a4 = *(_DWORD *)(v23 + 8 * v6 + 140);
  if ( a2 || (unsigned int)v13 < *(_DWORD *)(v11 + 84) )
  {
    v5 = v9 + v13;
LABEL_10:
    v10 = 0;
  }
  else
  {
    v5 = RtlAddressInSectionTable(v11, v9, (unsigned int)v13);
    v22 = 0;
    if ( !v5 )
      v22 = -1073741811;
    v10 = v22;
  }
LABEL_11:
  v14 = 0;
  if ( v10 >= 0 )
    return v5;
  return v14;
}

```

## disassembly

```asm
0x180066020  mov     [rsp+arg_8], rbx
0x180066025  mov     [rsp+arg_10], rbp
0x18006602a  push    rsi
0x18006602b  push    rdi
0x18006602c  push    r14
0x18006602e  sub     rsp, 20h
0x180066032  movzx   ebp, dl
0x180066035  xor     ebx, ebx
0x180066037  mov     rdx, rcx
0x18006603a  movzx   esi, r8w
0x18006603e  and     edx, 1
0x180066041  mov     [rsp+38h+arg_0], 0
0x18006604a  mov     r14, r9
0x18006604d  mov     rdi, rcx
0x180066050  test    cl, 2
0x180066053  jnz     loc_180066178
0x180066059  test    rdx, rdx
0x18006605c  jnz     loc_180066178
0x180066062  lea     r9, [rsp+38h+arg_0]
0x180066067  xor     r8d, r8d
0x18006606a  mov     rdx, rdi
0x18006606d  mov     ecx, 1
0x180066072  call    RtlImageNtHeaderEx
0x180066077  mov     r9, [rsp+38h+arg_0]
0x18006607c  test    r9, r9
0x18006607f  jz      short loc_1800660D5
0x180066081  movzx   eax, word ptr [r9+18h]
0x180066086  mov     ecx, 10Bh
0x18006608b  cmp     ax, cx
0x18006608e  jz      short loc_1800660F4
0x180066090  mov     ecx, 20Bh
0x180066095  cmp     ax, cx
0x180066098  jnz     loc_18006616E
0x18006609e  cmp     esi, [r9+84h]
0x1800660a5  jnb     loc_18006616E
0x1800660ab  mov     ecx, [r9+rsi*8+88h]
0x1800660b3  test    ecx, ecx
0x1800660b5  jz      loc_18006618C
0x1800660bb  mov     eax, [r9+rsi*8+8Ch]
0x1800660c3  mov     [r14], eax
0x1800660c6  test    bpl, bpl
0x1800660c9  jz      loc_180066196
0x1800660cf  lea     rbx, [rdi+rcx]
0x1800660d3  xor     eax, eax
0x1800660d5  mov     rbp, [rsp+38h+arg_10]
0x1800660da  xor     ecx, ecx
0x1800660dc  test    eax, eax
0x1800660de  cmovns  rcx, rbx
0x1800660e2  mov     rbx, [rsp+38h+arg_8]
0x1800660e7  mov     rax, rcx
0x1800660ea  add     rsp, 20h
0x1800660ee  pop     r14
0x1800660f0  pop     rdi
0x1800660f1  pop     rsi
0x1800660f2  retn
0x1800660f4  cmp     esi, [r9+74h]
0x1800660f8  jnb     short loc_18006616E
0x1800660fa  mov     r10d, [r9+rsi*8+78h]
0x1800660ff  test    r10d, r10d
0x180066102  jz      loc_18006618C
0x180066108  mov     eax, [r9+rsi*8+7Ch]
0x18006610d  mov     [r14], eax
0x180066110  test    bpl, bpl
0x180066113  jnz     loc_1800661C5
0x180066119  cmp     r10d, [r9+54h]
0x18006611d  jb      loc_1800661C5
0x180066123  movzx   edx, word ptr [r9+14h]
0x180066128  movzx   r11d, word ptr [r9+6]
0x18006612d  add     rdx, 18h
0x180066131  add     rdx, r9
0x180066134  xor     r8d, r8d
0x180066137  cmp     r8d, r11d
0x18006613a  jnb     short loc_18006616E
0x18006613c  mov     r9d, [rdx+0Ch]
0x180066140  cmp     r10d, r9d
0x180066143  jb      short loc_180066150
0x180066145  mov     ecx, [rdx+10h]
0x180066148  add     ecx, r9d
0x18006614b  cmp     r10d, ecx
0x18006614e  jb      short loc_180066159
0x180066150  add     rdx, 28h ; '('
0x180066154  inc     r8d
0x180066157  jmp     short loc_180066137
0x180066159  mov     eax, [rdx+14h]
0x18006615c  mov     rbx, r10
0x18006615f  sub     rax, r9
0x180066162  add     rax, rdi
0x180066165  add     rbx, rax
0x180066168  jnz     loc_1800660D3
0x18006616e  mov     eax, 0C000000Dh
0x180066173  jmp     loc_1800660D5
0x180066178  xor     ecx, ecx
0x18006617a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18006617e  test    rdx, rdx
0x180066181  cmovz   ecx, ebp
0x180066184  movzx   ebp, cl
0x180066187  jmp     loc_180066062
0x18006618c  mov     eax, 0C0000002h
0x180066191  jmp     loc_1800660D5
0x180066196  cmp     ecx, [r9+54h]
0x18006619a  jb      loc_1800660CF
0x1800661a0  mov     r8d, ecx
0x1800661a3  mov     rdx, rdi
0x1800661a6  mov     rcx, r9
0x1800661a9  call    RtlAddressInSectionTable
0x1800661ae  mov     rbx, rax
0x1800661b1  xor     ecx, ecx
0x1800661b3  mov     eax, 0C000000Dh
0x1800661b8  test    rbx, rbx
0x1800661bb  cmovz   ecx, eax
0x1800661be  mov     eax, ecx
0x1800661c0  jmp     loc_1800660D5
0x1800661c5  lea     rbx, [rdi+r10]
0x1800661c9  xor     eax, eax
0x1800661cb  jmp     loc_1800660D5
```
