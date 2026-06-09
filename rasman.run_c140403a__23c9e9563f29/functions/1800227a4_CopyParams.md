# CopyParams

- ea: `0x1800227a4`
- end: `0x18002287b`
- name: `CopyParams`
- size: `215`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f80`

## callees

- `0x1800227a4`
- `0x1800263b6`

## pseudocode

```c
__int64 __fastcall CopyParams(char *Src, char *a2, unsigned int a3)
{
  size_t v6; // rbx
  __int64 result; // rax
  unsigned __int16 v8; // si
  char *i; // r14
  __int64 v10; // rbx
  int v11; // eax

  v6 = 56LL * a3;
  result = (__int64)memcpy_0(a2, Src, v6);
  v8 = 0;
  for ( i = &a2[v6]; v8 < a3; result = v8 )
  {
    v10 = 56LL * v8;
    v11 = *(_DWORD *)&Src[v10 + 32];
    if ( v11 == 1 )
    {
      *(_DWORD *)&a2[v10 + 40] = *(_DWORD *)&Src[v10 + 40];
      *(_QWORD *)&a2[v10 + 48] = i;
      memcpy_0(i, *(const void **)&Src[v10 + 48], *(unsigned int *)&Src[v10 + 40]);
      i += *(unsigned int *)&Src[v10 + 40];
    }
    else if ( v11 )
    {
      if ( v11 == 2 )
      {
        *(_DWORD *)&a2[v10 + 40] = (_DWORD)i - 56 * v8 - (_DWORD)a2;
        memcpy_0(i, &Src[v10 + *(unsigned int *)&Src[v10 + 40]], *(unsigned int *)&Src[v10 + 44]);
        *(_DWORD *)&a2[v10 + 44] = *(_DWORD *)&Src[v10 + 44];
      }
    }
    else
    {
      *(_DWORD *)&a2[v10 + 40] = *(_DWORD *)&Src[v10 + 40];
    }
    ++v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800227a4  push    rbx
0x1800227a6  push    rbp
0x1800227a7  push    rsi
0x1800227a8  push    rdi
0x1800227a9  push    r12
0x1800227ab  push    r14
0x1800227ad  push    r15
0x1800227af  sub     rsp, 20h
0x1800227b3  mov     r15d, r8d
0x1800227b6  mov     rbp, rdx
0x1800227b9  mov     rdi, rcx
0x1800227bc  mov     rdx, rcx; Src
0x1800227bf  imul    rbx, r15, 38h ; '8'
0x1800227c3  mov     rcx, rbp; void *
0x1800227c6  mov     r8, rbx; Size
0x1800227c9  call    memcpy_0
0x1800227ce  xor     esi, esi
0x1800227d0  lea     r14, [rbx+rbp]
0x1800227d4  test    r15d, r15d
0x1800227d7  jz      loc_18002286C
0x1800227dd  lea     r12d, [rsi+1]
0x1800227e1  movzx   eax, si
0x1800227e4  imul    rbx, rax, 38h ; '8'
0x1800227e8  mov     eax, [rbx+rdi+20h]
0x1800227ec  cmp     eax, r12d
0x1800227ef  jnz     short loc_180022819
0x1800227f1  mov     eax, [rbx+rdi+28h]
0x1800227f5  mov     rcx, r14; void *
0x1800227f8  mov     [rbx+rbp+28h], eax
0x1800227fc  mov     [rbx+rbp+30h], r14
0x180022801  mov     r8d, [rbx+rdi+28h]; Size
0x180022806  mov     rdx, [rbx+rdi+30h]; Src
0x18002280b  call    memcpy_0
0x180022810  mov     eax, [rbx+rdi+28h]
0x180022814  add     r14, rax
0x180022817  jmp     short loc_18002285C
0x180022819  test    eax, eax
0x18002281b  jnz     short loc_180022827
0x18002281d  mov     eax, [rbx+rdi+28h]
0x180022821  mov     [rbx+rbp+28h], eax
0x180022825  jmp     short loc_18002285C
0x180022827  cmp     eax, 2
0x18002282a  jnz     short loc_18002285C
0x18002282c  movzx   eax, si
0x18002282f  imul    ecx, eax, 38h ; '8'
0x180022832  mov     eax, r14d
0x180022835  sub     eax, ecx
0x180022837  mov     rcx, r14; void *
0x18002283a  sub     eax, ebp
0x18002283c  mov     [rbx+rbp+28h], eax
0x180022840  mov     edx, [rbx+rdi+28h]
0x180022844  mov     r8d, [rbx+rdi+2Ch]; Size
0x180022849  add     rdx, rbx
0x18002284c  add     rdx, rdi; Src
0x18002284f  call    memcpy_0
0x180022854  mov     eax, [rbx+rdi+2Ch]
0x180022858  mov     [rbx+rbp+2Ch], eax
0x18002285c  add     si, r12w
0x180022860  movzx   eax, si
0x180022863  cmp     eax, r15d
0x180022866  jb      loc_1800227E1
0x18002286c  add     rsp, 20h
0x180022870  pop     r15
0x180022872  pop     r14
0x180022874  pop     r12
0x180022876  pop     rdi
0x180022877  pop     rsi
0x180022878  pop     rbp
0x180022879  pop     rbx
0x18002287a  retn
```
