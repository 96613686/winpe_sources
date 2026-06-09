# cComputeGlyphSet

- ea: `0x14005b59c`
- end: `0x14005b6c0`
- name: `cComputeGlyphSet`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004d57c`

## callees

- `0x14005b59c`

## pseudocode

```c
__int64 __fastcall cComputeGlyphSet(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, _DWORD *a5)
{
  _DWORD *v5; // r10
  _DWORD *v6; // rsi
  unsigned int v11; // edi
  unsigned int v12; // r9d
  __int64 i; // r8
  __int64 v15; // rsi
  int v16; // eax
  __int64 v17; // r14
  __int64 v18; // rdi
  unsigned __int16 v19; // ax
  _DWORD *v20; // rdx
  unsigned __int8 *v21; // rcx
  int v22; // eax

  v5 = 0;
  v6 = 0;
  if ( a5 )
  {
    a5[2] = 0;
    a5[3] = a4;
    v15 = a3 + 4 + 4 * a4;
    v16 = 2;
    *a5 = v15 * 4;
    v6 = &a5[v15];
    if ( a3 == 256 )
      v16 = 4;
    v5 = &a5[4 * a4 + 4];
    a5[1] = v16;
  }
  v11 = 0;
  v12 = 0;
  if ( a3 )
  {
    do
    {
      for ( i = v11 + 1;
            (unsigned int)i < a3
         && *(unsigned __int16 *)(a1 + 2 * i) - *(unsigned __int16 *)(a1 + 2LL * (unsigned int)(i - 1)) <= 1;
            i = (unsigned int)(i + 1) )
      {
        ;
      }
      if ( a5 )
      {
        if ( v12 < a4 )
        {
          v17 = v11;
          v18 = 2LL * v12;
          LOWORD(a5[2 * v18 + 4]) = *(_WORD *)(a1 + 2 * v17);
          v19 = *(_WORD *)(a1 + 2LL * (unsigned int)(i - 1)) - *(_WORD *)(a1 + 2 * v17) + 1;
          *(_QWORD *)&a5[2 * v18 + 6] = v5;
          HIWORD(a5[2 * v18 + 4]) = v19;
          v20 = &v5[v19];
          if ( v20 <= v6 )
          {
            v21 = (unsigned __int8 *)(v17 + a2);
            while ( v5 < v20 )
            {
              v22 = *v21++;
              *v5++ = v22;
            }
            a5[2] += HIWORD(a5[4 * v12 + 4]);
          }
        }
      }
      ++v12;
      v11 = i;
    }
    while ( (unsigned int)i < a3 );
  }
  return v12;
}

```

## disassembly

```asm
0x14005b59c  push    rbx
0x14005b59e  push    rbp
0x14005b59f  push    rsi
0x14005b5a0  push    rdi
0x14005b5a1  push    r12
0x14005b5a3  push    r13
0x14005b5a5  push    r14
0x14005b5a7  push    r15
0x14005b5a9  mov     r11, [rsp+40h+arg_20]
0x14005b5ae  xor     r10d, r10d
0x14005b5b1  xor     esi, esi
0x14005b5b3  mov     ebp, r9d
0x14005b5b6  mov     r15, rcx
0x14005b5b9  mov     ebx, r8d
0x14005b5bc  mov     r12, rdx
0x14005b5bf  lea     r13d, [r10+1]
0x14005b5c3  lea     ecx, [rsi+4]
0x14005b5c6  test    r11, r11
0x14005b5c9  jnz     short loc_14005B61C
0x14005b5cb  xor     edi, edi
0x14005b5cd  xor     r9d, r9d
0x14005b5d0  test    ebx, ebx
0x14005b5d2  jz      short loc_14005B60C
0x14005b5d4  lea     r8d, [rdi+1]
0x14005b5d8  jmp     short loc_14005B5F2
0x14005b5da  movzx   ecx, word ptr [r15+r8*2]
0x14005b5df  lea     eax, [r8-1]
0x14005b5e3  movzx   edx, word ptr [r15+rax*2]
0x14005b5e8  sub     ecx, edx
0x14005b5ea  cmp     ecx, r13d
0x14005b5ed  jg      short loc_14005B5F7
0x14005b5ef  add     r8d, r13d
0x14005b5f2  cmp     r8d, ebx
0x14005b5f5  jb      short loc_14005B5DA
0x14005b5f7  test    r11, r11
0x14005b5fa  jz      short loc_14005B601
0x14005b5fc  cmp     r9d, ebp
0x14005b5ff  jb      short loc_14005B658
0x14005b601  add     r9d, r13d
0x14005b604  mov     edi, r8d
0x14005b607  cmp     r8d, ebx
0x14005b60a  jb      short loc_14005B5D4
0x14005b60c  mov     eax, r9d
0x14005b60f  pop     r15
0x14005b611  pop     r14
0x14005b613  pop     r13
0x14005b615  pop     r12
0x14005b617  pop     rdi
0x14005b618  pop     rsi
0x14005b619  pop     rbp
0x14005b61a  pop     rbx
0x14005b61b  retn
0x14005b61c  mov     [r11+8], r10d
0x14005b620  lea     esi, [r8+4]
0x14005b624  lea     esi, [rsi+rbp*4]
0x14005b627  mov     [r11+0Ch], ebp
0x14005b62b  shl     esi, 2
0x14005b62e  mov     eax, 2
0x14005b633  mov     [r11], esi
0x14005b636  mov     r10, rbp
0x14005b639  add     rsi, r11
0x14005b63c  cmp     ebx, 100h
0x14005b642  cmovz   eax, ecx
0x14005b645  add     r10, r13
0x14005b648  shl     r10, 4
0x14005b64c  add     r10, r11
0x14005b64f  mov     [r11+4], eax
0x14005b653  jmp     loc_14005B5CB
0x14005b658  mov     r14d, edi
0x14005b65b  mov     edi, r9d
0x14005b65e  add     rdi, rdi
0x14005b661  movzx   eax, word ptr [r15+r14*2]
0x14005b666  mov     [r11+rdi*8+10h], ax
0x14005b66c  lea     eax, [r8-1]
0x14005b670  movzx   eax, word ptr [r15+rax*2]
0x14005b675  sub     ax, [r15+r14*2]
0x14005b67a  add     ax, r13w
0x14005b67e  mov     [r11+rdi*8+18h], r10
0x14005b683  movzx   ecx, ax
0x14005b686  mov     [r11+rdi*8+12h], cx
0x14005b68c  lea     rdx, [r10+rcx*4]
0x14005b690  cmp     rdx, rsi
0x14005b693  ja      loc_14005B601
0x14005b699  lea     rcx, [r14+r12]
0x14005b69d  jmp     short loc_14005B6AC
0x14005b69f  movzx   eax, byte ptr [rcx]
0x14005b6a2  add     rcx, r13
0x14005b6a5  mov     [r10], eax
0x14005b6a8  add     r10, 4
0x14005b6ac  cmp     r10, rdx
0x14005b6af  jb      short loc_14005B69F
0x14005b6b1  movzx   ecx, word ptr [r11+rdi*8+12h]
0x14005b6b7  add     [r11+8], ecx
0x14005b6bb  jmp     loc_14005B601
```
