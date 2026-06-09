# optimal_insert

- ea: `0x180006514`
- end: `0x18000663b`
- name: `optimal_insert`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x180006514`

## pseudocode

```c
__int64 __fastcall optimal_insert(__int64 a1, int a2, int a3)
{
  __int64 v3; // r9
  __int64 result; // rax
  _WORD *v6; // rdi
  _WORD *v7; // rbx
  __int64 v8; // r10
  int v9; // r11d
  int v10; // r14d
  int v11; // r15d
  int v12; // edx
  __int64 v13; // rsi
  __int64 v14; // rbp
  int v15; // eax

  v3 = *(_QWORD *)(a1 + 88);
  result = *(unsigned __int16 *)(a2 + v3);
  v6 = (_WORD *)(v3 + 213484 + 2LL * a2);
  v7 = (_WORD *)(v3 + 82412 + 2LL * a2);
  v8 = *(unsigned __int16 *)(v3 + 2 * result + 344556);
  *(_WORD *)(v3 + 2 * result + 344556) = a2;
  if ( (int)v8 <= a3 )
  {
    *v6 = 0;
    *v7 = 0;
    return result;
  }
  v9 = 2;
  v10 = 2;
  v11 = 2;
  while ( 1 )
  {
    v12 = v9;
    v13 = (unsigned int)(v9 + v8);
    v14 = (unsigned int)(v9 + a2);
    do
    {
      v15 = *(unsigned __int8 *)(v13 + v3) - *(unsigned __int8 *)(v14 + v3);
      if ( v15 )
        break;
      v14 = (unsigned int)(v14 + 1);
      v13 = (unsigned int)(v13 + 1);
      ++v12;
    }
    while ( v12 < 50 );
    if ( v15 >= 0 )
      break;
    if ( v12 > v11 )
    {
      if ( v12 >= 50 )
        goto LABEL_20;
      v9 = v12;
      v11 = v12;
      if ( v10 < v12 )
        v9 = v10;
    }
    *v6 = v8;
    v6 = (_WORD *)(v3 + 2 * ((unsigned int)v8 + 41206LL));
    result = (unsigned __int16)*v6;
LABEL_18:
    v8 = (unsigned __int16)result;
    if ( (unsigned __int16)result <= a3 )
    {
      *v7 = 0;
      *v6 = 0;
      return result;
    }
  }
  if ( v12 <= v10 )
  {
LABEL_17:
    *v7 = v8;
    v7 = (_WORD *)(v3 + 2 * ((unsigned int)v8 + 106742LL));
    result = (unsigned __int16)*v7;
    goto LABEL_18;
  }
  if ( v12 < 50 )
  {
    v9 = v11;
    v10 = v12;
    if ( v12 < v11 )
      v9 = v12;
    goto LABEL_17;
  }
LABEL_20:
  *v7 = *(_WORD *)(v3 + 2 * v8 + 82412);
  result = *(unsigned __int16 *)(v3 + 2 * v8 + 213484);
  *v6 = result;
  return result;
}

```

## disassembly

```asm
0x180006514  push    rbx
0x180006516  push    rbp
0x180006517  push    rsi
0x180006518  push    rdi
0x180006519  push    r12
0x18000651b  push    r13
0x18000651d  push    r14
0x18000651f  push    r15
0x180006521  mov     r9, [rcx+58h]
0x180006525  mov     r13d, r8d
0x180006528  movsxd  r12, edx
0x18000652b  lea     rdi, [r9+341ECh]
0x180006532  movzx   eax, word ptr [r12+r9]
0x180006537  lea     rbx, [r9+141ECh]
0x18000653e  lea     rdi, [rdi+r12*2]
0x180006542  lea     rbx, [rbx+r12*2]
0x180006546  movzx   r10d, word ptr [r9+rax*2+541ECh]
0x18000654f  mov     [r9+rax*2+541ECh], r12w
0x180006558  cmp     r10d, r8d
0x18000655b  jg      short loc_18000656D
0x18000655d  xor     r8d, r8d
0x180006560  mov     [rdi], r8w
0x180006564  mov     [rbx], r8w
0x180006568  jmp     loc_180006614
0x18000656d  mov     r11d, 2
0x180006573  xor     r8d, r8d
0x180006576  mov     r14d, r11d
0x180006579  mov     r15d, r11d
0x18000657c  mov     edx, r11d
0x18000657f  lea     esi, [r11+r10]
0x180006583  lea     ebp, [r11+r12]
0x180006587  movzx   ecx, byte ptr [rbp+r9+0]
0x18000658d  movzx   eax, byte ptr [rsi+r9]
0x180006592  sub     eax, ecx
0x180006594  jnz     short loc_1800065A1
0x180006596  inc     ebp
0x180006598  inc     esi
0x18000659a  inc     edx
0x18000659c  cmp     edx, 32h ; '2'
0x18000659f  jl      short loc_180006587
0x1800065a1  test    eax, eax
0x1800065a3  jns     short loc_1800065D3
0x1800065a5  cmp     edx, r15d
0x1800065a8  jle     short loc_1800065BC
0x1800065aa  cmp     edx, 32h ; '2'
0x1800065ad  jge     short loc_180006621
0x1800065af  cmp     r14d, edx
0x1800065b2  mov     r11d, edx
0x1800065b5  mov     r15d, edx
0x1800065b8  cmovl   r11d, r14d
0x1800065bc  mov     [rdi], r10w
0x1800065c0  mov     edi, r10d
0x1800065c3  add     rdi, 0A0F6h
0x1800065ca  lea     rdi, [r9+rdi*2]
0x1800065ce  movzx   eax, word ptr [rdi]
0x1800065d1  jmp     short loc_1800065FF
0x1800065d3  cmp     edx, r14d
0x1800065d6  jle     short loc_1800065EA
0x1800065d8  cmp     edx, 32h ; '2'
0x1800065db  jge     short loc_180006621
0x1800065dd  cmp     edx, r15d
0x1800065e0  mov     r11d, r15d
0x1800065e3  mov     r14d, edx
0x1800065e6  cmovl   r11d, edx
0x1800065ea  mov     [rbx], r10w
0x1800065ee  mov     ebx, r10d
0x1800065f1  add     rbx, 1A0F6h
0x1800065f8  lea     rbx, [r9+rbx*2]
0x1800065fc  movzx   eax, word ptr [rbx]
0x1800065ff  movzx   r10d, ax
0x180006603  cmp     r10d, r13d
0x180006606  jg      loc_18000657C
0x18000660c  mov     [rbx], r8w
0x180006610  mov     [rdi], r8w
0x180006614  pop     r15
0x180006616  pop     r14
0x180006618  pop     r13
0x18000661a  pop     r12
0x18000661c  pop     rdi
0x18000661d  pop     rsi
0x18000661e  pop     rbp
0x18000661f  pop     rbx
0x180006620  retn
0x180006621  movzx   eax, word ptr [r9+r10*2+141ECh]
0x18000662a  mov     [rbx], ax
0x18000662d  movzx   eax, word ptr [r9+r10*2+341ECh]
0x180006636  mov     [rdi], ax
0x180006639  jmp     short loc_180006614
```
