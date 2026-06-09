# CopyParams

- ea: `0x18002333c`
- end: `0x180023414`
- name: `CopyParams`
- size: `216`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030d0`

## callees

- `0x18002333c`
- `0x180027386`

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
0x18002333c  push    rbx
0x18002333e  push    rbp
0x18002333f  push    rsi
0x180023340  push    rdi
0x180023341  push    r12
0x180023343  push    r14
0x180023345  push    r15
0x180023347  sub     rsp, 20h
0x18002334b  mov     r15d, r8d
0x18002334e  mov     rbp, rdx
0x180023351  mov     rdi, rcx
0x180023354  mov     rdx, rcx; Src
0x180023357  imul    rbx, r15, 38h ; '8'
0x18002335b  mov     rcx, rbp; void *
0x18002335e  mov     r8, rbx; Size
0x180023361  call    memcpy_0
0x180023366  xor     esi, esi
0x180023368  lea     r14, [rbx+rbp]
0x18002336c  test    r15d, r15d
0x18002336f  jz      loc_180023404
0x180023375  lea     r12d, [rsi+1]
0x180023379  movzx   eax, si
0x18002337c  imul    rbx, rax, 38h ; '8'
0x180023380  mov     eax, [rbx+rdi+20h]
0x180023384  cmp     eax, r12d
0x180023387  jnz     short loc_1800233B1
0x180023389  mov     eax, [rbx+rdi+28h]
0x18002338d  mov     rcx, r14; void *
0x180023390  mov     [rbx+rbp+28h], eax
0x180023394  mov     [rbx+rbp+30h], r14
0x180023399  mov     r8d, [rbx+rdi+28h]; Size
0x18002339e  mov     rdx, [rbx+rdi+30h]; Src
0x1800233a3  call    memcpy_0
0x1800233a8  mov     eax, [rbx+rdi+28h]
0x1800233ac  add     r14, rax
0x1800233af  jmp     short loc_1800233F4
0x1800233b1  test    eax, eax
0x1800233b3  jnz     short loc_1800233BF
0x1800233b5  mov     eax, [rbx+rdi+28h]
0x1800233b9  mov     [rbx+rbp+28h], eax
0x1800233bd  jmp     short loc_1800233F4
0x1800233bf  cmp     eax, 2
0x1800233c2  jnz     short loc_1800233F4
0x1800233c4  movzx   eax, si
0x1800233c7  imul    ecx, eax, 38h ; '8'
0x1800233ca  mov     eax, r14d
0x1800233cd  sub     eax, ecx
0x1800233cf  mov     rcx, r14; void *
0x1800233d2  sub     eax, ebp
0x1800233d4  mov     [rbx+rbp+28h], eax
0x1800233d8  mov     edx, [rbx+rdi+28h]
0x1800233dc  mov     r8d, [rbx+rdi+2Ch]; Size
0x1800233e1  add     rdx, rbx
0x1800233e4  add     rdx, rdi; Src
0x1800233e7  call    memcpy_0
0x1800233ec  mov     eax, [rbx+rdi+2Ch]
0x1800233f0  mov     [rbx+rbp+2Ch], eax
0x1800233f4  add     si, r12w
0x1800233f8  movzx   eax, si
0x1800233fb  cmp     eax, r15d
0x1800233fe  jb      loc_180023379
0x180023404  add     rsp, 20h
0x180023408  pop     r15
0x18002340a  pop     r14
0x18002340c  pop     r12
0x18002340e  pop     rdi
0x18002340f  pop     rsi
0x180023410  pop     rbp
0x180023411  pop     rbx
0x180023412  retn
```
