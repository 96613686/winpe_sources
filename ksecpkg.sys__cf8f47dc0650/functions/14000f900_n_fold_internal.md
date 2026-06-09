# n_fold_internal

- ea: `0x14000f900`
- end: `0x14000fa26`
- name: `n_fold_internal`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e7b0`
- `0x14000f844`
- `0x14000f88c`

## callees

- `0x14000f778`
- `0x14000f7a0`
- `0x14000f900`
- `0x14000fa2c`
- `0x1400102c0`

## pseudocode

```c
char __fastcall n_fold_internal(_OWORD *a1, unsigned int a2, const void *a3, __int64 a4, _OWORD *a5)
{
  size_t v6; // rsi
  signed int v8; // edi
  __int64 v9; // rcx
  unsigned int v10; // ebp
  unsigned int v11; // eax
  _BYTE *v12; // rbx
  __int64 v13; // r8
  char v14; // r10
  __int64 v15; // r9
  __int64 v16; // rdx
  char v17; // r9
  __int64 v18; // rdx
  _OWORD *v19; // r9
  int v20; // ebx
  unsigned int v21; // ebp

  v6 = a2;
  v8 = 0;
  v10 = 16 * a2 / (unsigned int)GCD_l(a2);
  v11 = v10 / (unsigned int)v6;
  if ( (int)(v10 / (unsigned int)v6) > 0 )
  {
    do
    {
      v12 = (char *)a1 + (unsigned int)(v6 * v8);
      if ( v8 )
      {
        memmove(v12, (char *)a1 + (unsigned int)(v6 * (v8 - 1)), v6);
        rotate_right_1((unsigned int)v6, (char *)a1 + (unsigned int)(v6 * v8));
        v13 = (unsigned int)(v6 - 1);
        v14 = v12[v13];
        LODWORD(v15) = v6 - 1;
        if ( (_DWORD)v6 != 1 )
        {
          do
          {
            v16 = (unsigned int)v15;
            v15 = (unsigned int)(v15 - 1);
            LOBYTE(v9) = (v12[v16] >> 4) | (16 * v12[v15]);
            v12[v16] = v9;
          }
          while ( (_DWORD)v15 );
        }
        LOBYTE(v11) = (16 * v14) | (*v12 >> 4);
        *v12 = v11;
        v17 = v12[v13];
        if ( (_DWORD)v6 != 1 )
        {
          do
          {
            v18 = (unsigned int)(v13 - 1);
            v9 = (unsigned int)v13;
            LOBYTE(v11) = v12[v18];
            LODWORD(v13) = v13 - 1;
            v12[v9] = v11;
          }
          while ( (_DWORD)v18 );
        }
        *v12 = v17;
      }
      else
      {
        LOBYTE(v11) = (unsigned __int8)memmove(v12, a3, v6);
      }
      ++v8;
    }
    while ( v8 < (int)(v10 / (unsigned int)v6) );
  }
  v19 = a5;
  v20 = 1;
  v21 = v10 >> 4;
  *a5 = *a1;
  if ( v21 > 1 )
  {
    do
      LOBYTE(v11) = OCA_add(v9, v19, (char *)a1 + (unsigned int)(16 * v20++));
    while ( v20 < (int)v21 );
  }
  return v11;
}

```

## disassembly

```asm
0x14000f900  push    rbx
0x14000f902  push    rbp
0x14000f903  push    rsi
0x14000f904  push    rdi
0x14000f905  push    r12
0x14000f907  push    r13
0x14000f909  push    r14
0x14000f90b  push    r15
0x14000f90d  sub     rsp, 28h
0x14000f911  mov     r14, rcx
0x14000f914  mov     esi, edx
0x14000f916  mov     ecx, edx
0x14000f918  mov     r13, r8
0x14000f91b  call    GCD_l
0x14000f920  mov     r10d, eax
0x14000f923  xor     edx, edx
0x14000f925  mov     eax, esi
0x14000f927  xor     edi, edi
0x14000f929  shl     eax, 4
0x14000f92c  div     r10d
0x14000f92f  xor     edx, edx
0x14000f931  mov     ebp, eax
0x14000f933  div     esi
0x14000f935  mov     r12d, eax
0x14000f938  test    eax, eax
0x14000f93a  jle     loc_14000F9DF
0x14000f940  mov     ebx, edi
0x14000f942  mov     r8, rsi; Size
0x14000f945  imul    ebx, esi
0x14000f948  add     rbx, r14
0x14000f94b  mov     rcx, rbx; void *
0x14000f94e  test    edi, edi
0x14000f950  jnz     short loc_14000F95C
0x14000f952  mov     rdx, r13; Src
0x14000f955  call    memmove
0x14000f95a  jmp     short loc_14000F9D4
0x14000f95c  lea     edx, [rdi-1]
0x14000f95f  imul    edx, esi
0x14000f962  add     rdx, r14; Src
0x14000f965  call    memmove
0x14000f96a  mov     rdx, rbx
0x14000f96d  mov     ecx, esi
0x14000f96f  call    rotate_right_1
0x14000f974  cmp     esi, 1
0x14000f977  jb      short loc_14000F9D4
0x14000f979  lea     r8d, [rsi-1]
0x14000f97d  mov     r10b, [r8+rbx]
0x14000f981  mov     r9d, r8d
0x14000f984  test    r8d, r8d
0x14000f987  jz      short loc_14000F9A6
0x14000f989  mov     edx, r9d
0x14000f98c  dec     r9d
0x14000f98f  mov     al, [rdx+rbx]
0x14000f992  mov     cl, [r9+rbx]
0x14000f996  shl     cl, 4
0x14000f999  shr     al, 4
0x14000f99c  or      cl, al
0x14000f99e  mov     [rdx+rbx], cl
0x14000f9a1  test    r9d, r9d
0x14000f9a4  jnz     short loc_14000F989
0x14000f9a6  mov     al, [rbx]
0x14000f9a8  shr     al, 4
0x14000f9ab  shl     r10b, 4
0x14000f9af  or      al, r10b
0x14000f9b2  mov     [rbx], al
0x14000f9b4  mov     r9b, [r8+rbx]
0x14000f9b8  test    r8d, r8d
0x14000f9bb  jz      short loc_14000F9D1
0x14000f9bd  lea     edx, [r8-1]
0x14000f9c1  mov     ecx, r8d
0x14000f9c4  mov     al, [rdx+rbx]
0x14000f9c7  mov     r8d, edx
0x14000f9ca  mov     [rcx+rbx], al
0x14000f9cd  test    edx, edx
0x14000f9cf  jnz     short loc_14000F9BD
0x14000f9d1  mov     [rbx], r9b
0x14000f9d4  inc     edi
0x14000f9d6  cmp     edi, r12d
0x14000f9d9  jl      loc_14000F940
0x14000f9df  mov     r9, [rsp+68h+arg_20]
0x14000f9e7  mov     ebx, 1
0x14000f9ec  movups  xmm0, xmmword ptr [r14]
0x14000f9f0  shr     ebp, 4
0x14000f9f3  movdqu  xmmword ptr [r9], xmm0
0x14000f9f8  cmp     ebp, ebx
0x14000f9fa  jbe     short loc_14000FA14
0x14000f9fc  mov     r8d, ebx
0x14000f9ff  mov     rdx, r9
0x14000fa02  shl     r8d, 4
0x14000fa06  add     r8, r14
0x14000fa09  call    OCA_add
0x14000fa0e  inc     ebx
0x14000fa10  cmp     ebx, ebp
0x14000fa12  jl      short loc_14000F9FC
0x14000fa14  add     rsp, 28h
0x14000fa18  pop     r15
0x14000fa1a  pop     r14
0x14000fa1c  pop     r13
0x14000fa1e  pop     r12
0x14000fa20  pop     rdi
0x14000fa21  pop     rsi
0x14000fa22  pop     rbp
0x14000fa23  pop     rbx
0x14000fa24  retn
```
