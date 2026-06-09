# optimal_find_match

- ea: `0x180006384`
- end: `0x18000650b`
- name: `optimal_find_match`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x180006384`

## pseudocode

```c
__int64 __fastcall optimal_find_match(__int64 a1, int a2)
{
  __int64 v2; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // rdi
  __int64 v7; // r11
  __int64 result; // rax
  int v9; // ebx
  int v10; // edx
  int v11; // r13d
  int v12; // r12d
  int v13; // r8d
  __int64 v14; // rbp
  __int64 v15; // r14
  int v16; // eax
  unsigned __int16 v17; // ax

  v2 = *(_QWORD *)(a1 + 88);
  v4 = *(unsigned __int16 *)(a2 + v2);
  v5 = (unsigned __int16 *)(v2 + 213484 + 2LL * a2);
  v6 = (unsigned __int16 *)(v2 + 82412 + 2LL * a2);
  v7 = *(unsigned __int16 *)(v2 + 2 * v4 + 344556);
  *(_WORD *)(v2 + 2 * v4 + 344556) = a2;
  if ( (unsigned int)v7 <= a2 - 32764 )
  {
    *v5 = 0;
    result = 0;
    *v6 = 0;
    return result;
  }
  v9 = 2;
  v10 = 2;
  v11 = 2;
  v12 = 2;
  while ( 2 )
  {
    v13 = v9;
    v14 = (unsigned int)(v9 + v7);
    v15 = (unsigned int)(v9 + a2);
    while ( 1 )
    {
      v16 = *(unsigned __int8 *)(v14 + v2) - *(unsigned __int8 *)(v15 + v2);
      if ( v16 )
        break;
      v15 = (unsigned int)(v15 + 1);
      v14 = (unsigned int)(v14 + 1);
      if ( ++v13 >= 258 )
        goto LABEL_11;
    }
    if ( v16 < 0 )
    {
      if ( v13 <= v12 )
      {
LABEL_15:
        *v5 = v7;
        v5 = (unsigned __int16 *)(v2 + 2 * ((unsigned int)v7 + 41206LL));
        v17 = *v5;
        goto LABEL_23;
      }
      if ( v13 <= v10 )
      {
LABEL_13:
        v9 = v13;
        v12 = v13;
        if ( v11 < v13 )
          v9 = v11;
        goto LABEL_15;
      }
      do
LABEL_11:
        *(_DWORD *)(v2 + 4LL * ++v10 + 81376) = a2 - v7 - 1;
      while ( v10 < v13 );
      if ( v13 < 50 )
        goto LABEL_13;
LABEL_28:
      *v6 = *(_WORD *)(v2 + 2 * v7 + 82412);
      *v5 = *(_WORD *)(v2 + 2 * v7 + 213484);
      goto LABEL_25;
    }
    if ( v13 > v11 )
    {
      if ( v13 > v10 )
      {
        do
          *(_DWORD *)(v2 + 4LL * ++v10 + 81376) = a2 - v7 - 1;
        while ( v10 < v13 );
        if ( v13 >= 50 )
          goto LABEL_28;
      }
      v9 = v12;
      v11 = v13;
      if ( v13 < v12 )
        v9 = v13;
    }
    *v6 = v7;
    v6 = (unsigned __int16 *)(v2 + 2 * ((unsigned int)v7 + 106742LL));
    v17 = *v6;
LABEL_23:
    v7 = v17;
    if ( v17 > (unsigned int)(a2 - 32764) )
      continue;
    break;
  }
  *v6 = 0;
  *v5 = 0;
LABEL_25:
  if ( v10 < 3 )
    return 0;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006384  push    rbx
0x180006386  push    rbp
0x180006387  push    rsi
0x180006388  push    rdi
0x180006389  push    r12
0x18000638b  push    r13
0x18000638d  push    r14
0x18000638f  push    r15
0x180006391  mov     r9, [rcx+58h]
0x180006395  xor     r10d, r10d
0x180006398  movsxd  r15, edx
0x18000639b  lea     rsi, [r9+341ECh]
0x1800063a2  movzx   eax, word ptr [r15+r9]
0x1800063a7  lea     rdi, [r9+141ECh]
0x1800063ae  lea     rsi, [rsi+r15*2]
0x1800063b2  lea     rdi, [rdi+r15*2]
0x1800063b6  movzx   r11d, word ptr [r9+rax*2+541ECh]
0x1800063bf  mov     [r9+rax*2+541ECh], r15w
0x1800063c8  lea     eax, [r15-7FFCh]
0x1800063cf  cmp     r11d, eax
0x1800063d2  ja      short loc_1800063E3
0x1800063d4  mov     [rsi], r10w
0x1800063d8  xor     eax, eax
0x1800063da  mov     [rdi], r10w
0x1800063de  jmp     loc_1800064E4
0x1800063e3  mov     ebx, 2
0x1800063e8  mov     edx, ebx
0x1800063ea  mov     r13d, ebx
0x1800063ed  mov     r12d, ebx
0x1800063f0  mov     r8d, ebx
0x1800063f3  lea     ebp, [rbx+r11]
0x1800063f7  lea     r14d, [rbx+r15]
0x1800063fb  movzx   ecx, byte ptr [r14+r9]
0x180006400  movzx   eax, byte ptr [rbp+r9+0]
0x180006406  sub     eax, ecx
0x180006408  jnz     short loc_18000641D
0x18000640a  inc     r14d
0x18000640d  inc     ebp
0x18000640f  inc     r8d
0x180006412  cmp     r8d, 102h
0x180006419  jl      short loc_1800063FB
0x18000641b  jmp     short loc_18000642B
0x18000641d  test    eax, eax
0x18000641f  jns     short loc_180006473
0x180006421  cmp     r8d, r12d
0x180006424  jle     short loc_18000645C
0x180006426  cmp     r8d, edx
0x180006429  jle     short loc_18000644F
0x18000642b  mov     ecx, r15d
0x18000642e  sub     ecx, r11d
0x180006431  dec     ecx
0x180006433  inc     edx
0x180006435  movsxd  rax, edx
0x180006438  mov     [r9+rax*4+13DE0h], ecx
0x180006440  cmp     edx, r8d
0x180006443  jl      short loc_180006433
0x180006445  cmp     r8d, 32h ; '2'
0x180006449  jge     loc_1800064F1
0x18000644f  cmp     r13d, r8d
0x180006452  mov     ebx, r8d
0x180006455  mov     r12d, r8d
0x180006458  cmovl   ebx, r13d
0x18000645c  mov     [rsi], r11w
0x180006460  mov     esi, r11d
0x180006463  add     rsi, 0A0F6h
0x18000646a  lea     rsi, [r9+rsi*2]
0x18000646e  movzx   eax, word ptr [rsi]
0x180006471  jmp     short loc_1800064BF
0x180006473  cmp     r8d, r13d
0x180006476  jle     short loc_1800064AA
0x180006478  cmp     r8d, edx
0x18000647b  jle     short loc_18000649D
0x18000647d  mov     ecx, r15d
0x180006480  sub     ecx, r11d
0x180006483  dec     ecx
0x180006485  inc     edx
0x180006487  movsxd  rax, edx
0x18000648a  mov     [r9+rax*4+13DE0h], ecx
0x180006492  cmp     edx, r8d
0x180006495  jl      short loc_180006485
0x180006497  cmp     r8d, 32h ; '2'
0x18000649b  jge     short loc_1800064F1
0x18000649d  cmp     r8d, r12d
0x1800064a0  mov     ebx, r12d
0x1800064a3  mov     r13d, r8d
0x1800064a6  cmovl   ebx, r8d
0x1800064aa  mov     [rdi], r11w
0x1800064ae  mov     edi, r11d
0x1800064b1  add     rdi, 1A0F6h
0x1800064b8  lea     rdi, [r9+rdi*2]
0x1800064bc  movzx   eax, word ptr [rdi]
0x1800064bf  movzx   r11d, ax
0x1800064c3  lea     eax, [r15-7FFCh]
0x1800064ca  cmp     r11d, eax
0x1800064cd  ja      loc_1800063F0
0x1800064d3  mov     [rdi], r10w
0x1800064d7  mov     [rsi], r10w
0x1800064db  cmp     edx, 3
0x1800064de  cmovl   edx, r10d
0x1800064e2  mov     eax, edx
0x1800064e4  pop     r15
0x1800064e6  pop     r14
0x1800064e8  pop     r13
0x1800064ea  pop     r12
0x1800064ec  pop     rdi
0x1800064ed  pop     rsi
0x1800064ee  pop     rbp
0x1800064ef  pop     rbx
0x1800064f0  retn
0x1800064f1  movzx   eax, word ptr [r9+r11*2+141ECh]
0x1800064fa  mov     [rdi], ax
0x1800064fd  movzx   eax, word ptr [r9+r11*2+341ECh]
0x180006506  mov     [rsi], ax
0x180006509  jmp     short loc_1800064DB
```
