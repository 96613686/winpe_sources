# CdIsRemount

- ea: `0x1400140cc`
- end: `0x1400141d8`
- name: `CdIsRemount`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400142d8`

## callees

- `0x140002ee0`
- `0x1400140cc`

## pseudocode

```c
char __fastcall CdIsRemount(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // r14
  __int64 v4; // rbx
  char v7; // di
  __int64 v8; // rbp
  size_t v9; // rax
  const void *v10; // rdx
  const void *v11; // rcx
  unsigned int v12; // eax

  v3 = *(_QWORD *)(a2 + 8);
  v4 = qword_1400072F0;
  v7 = 0;
  while ( (__int64 *)v4 != &qword_1400072F0 )
  {
    *a3 = v4 - 32;
    if ( a2 == v4 - 32 )
      goto LABEL_18;
    v8 = *(_QWORD *)(v4 - 24);
    if ( v8 == v3 || *(_QWORD *)(v8 + 16) != *(_QWORD *)(v3 + 16) || *(_DWORD *)(v4 + 20) )
      goto LABEL_18;
    if ( (*(_DWORD *)(a2 + 48) & 0x80u) == 0 )
    {
      if ( *(_DWORD *)(v8 + 24) != *(_DWORD *)(v3 + 24) )
        goto LABEL_18;
      v12 = *(_DWORD *)(a2 + 528);
      if ( v12 != *(_DWORD *)(v4 + 496) || v12 && memcmp(*(const void **)(a2 + 520), *(const void **)(v4 + 488), v12) )
        goto LABEL_18;
      v9 = *(unsigned __int16 *)(v3 + 6);
      if ( (_WORD)v9 != *(_WORD *)(v8 + 6) )
        goto LABEL_18;
      v10 = (const void *)(v3 + 32);
      v11 = (const void *)(v8 + 32);
    }
    else
    {
      if ( (*(_DWORD *)(v4 + 16) & 0x80u) == 0 )
        goto LABEL_18;
      v9 = *(unsigned int *)(a2 + 528);
      if ( (_DWORD)v9 != *(_DWORD *)(v4 + 496) )
        goto LABEL_18;
      if ( !(_DWORD)v9 )
        return 1;
      v10 = *(const void **)(v4 + 488);
      v11 = *(const void **)(a2 + 520);
    }
    if ( !memcmp(v11, v10, v9) )
      return 1;
LABEL_18:
    v4 = *(_QWORD *)v4;
  }
  return v7;
}

```

## disassembly

```asm
0x1400140cc  push    rbx
0x1400140ce  push    rbp
0x1400140cf  push    rsi
0x1400140d0  push    rdi
0x1400140d1  push    r12
0x1400140d3  push    r14
0x1400140d5  push    r15
0x1400140d7  sub     rsp, 20h
0x1400140db  mov     r14, [rdx+8]
0x1400140df  lea     r12, qword_1400072F0
0x1400140e6  mov     rbx, cs:qword_1400072F0
0x1400140ed  mov     r15, r8
0x1400140f0  mov     rsi, rdx
0x1400140f3  xor     dil, dil
0x1400140f6  jmp     loc_1400141B7
0x1400140fb  lea     rax, [rbx-20h]
0x1400140ff  mov     [r15], rax
0x140014102  cmp     rsi, rax
0x140014105  jz      loc_1400141B4
0x14001410b  mov     rbp, [rbx-18h]
0x14001410f  cmp     rbp, r14
0x140014112  jz      loc_1400141B4
0x140014118  mov     rax, [r14+10h]
0x14001411c  cmp     [rbp+10h], rax
0x140014120  jnz     loc_1400141B4
0x140014126  cmp     dword ptr [rbx+14h], 0
0x14001412a  jnz     loc_1400141B4
0x140014130  mov     eax, [rsi+30h]
0x140014133  test    al, al
0x140014135  jns     short loc_140014160
0x140014137  mov     eax, [rbx+10h]
0x14001413a  test    al, al
0x14001413c  jns     short loc_1400141B4
0x14001413e  mov     eax, [rsi+210h]
0x140014144  cmp     eax, [rbx+1F0h]
0x14001414a  jnz     short loc_1400141B4
0x14001414c  test    eax, eax
0x14001414e  jz      short loc_1400141C2
0x140014150  mov     rdx, [rbx+1E8h]
0x140014157  mov     rcx, [rsi+208h]
0x14001415e  jmp     short loc_1400141A8
0x140014160  mov     eax, [r14+18h]
0x140014164  cmp     [rbp+18h], eax
0x140014167  jnz     short loc_1400141B4
0x140014169  mov     eax, [rsi+210h]
0x14001416f  cmp     eax, [rbx+1F0h]
0x140014175  jnz     short loc_1400141B4
0x140014177  test    eax, eax
0x140014179  jz      short loc_140014195
0x14001417b  mov     rdx, [rbx+1E8h]; Buf2
0x140014182  mov     r8d, eax; Size
0x140014185  mov     rcx, [rsi+208h]; Buf1
0x14001418c  call    memcmp
0x140014191  test    eax, eax
0x140014193  jnz     short loc_1400141B4
0x140014195  movzx   eax, word ptr [r14+6]
0x14001419a  cmp     ax, [rbp+6]
0x14001419e  jnz     short loc_1400141B4
0x1400141a0  lea     rdx, [r14+20h]; Buf2
0x1400141a4  lea     rcx, [rbp+20h]; Buf1
0x1400141a8  mov     r8, rax; Size
0x1400141ab  call    memcmp
0x1400141b0  test    eax, eax
0x1400141b2  jz      short loc_1400141C2
0x1400141b4  mov     rbx, [rbx]
0x1400141b7  cmp     rbx, r12
0x1400141ba  jnz     loc_1400140FB
0x1400141c0  jmp     short loc_1400141C5
0x1400141c2  mov     dil, 1
0x1400141c5  mov     al, dil
0x1400141c8  add     rsp, 20h
0x1400141cc  pop     r15
0x1400141ce  pop     r14
0x1400141d0  pop     r12
0x1400141d2  pop     rdi
0x1400141d3  pop     rsi
0x1400141d4  pop     rbp
0x1400141d5  pop     rbx
0x1400141d6  retn
```
