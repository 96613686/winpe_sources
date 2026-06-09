# CreateNewEventEntry

- ea: `0x18001e3b8`
- end: `0x18001e5f0`
- name: `CreateNewEventEntry`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e8a0`

## callees

- `0x1800026a6`
- `0x18001e3b8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001e45e`
- `KERNEL32!HeapAlloc` at `0x18001e45e`
- `KERNEL32!GetProcessHeap` at `0x18001e450`
- `KERNEL32!GetProcessHeap` at `0x18001e450`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, char **a6)
{
  __int64 v6; // r10
  __int64 v7; // r11
  unsigned __int8 v8; // r12
  unsigned __int8 v9; // bl
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  char *v18; // rax
  int v19; // edx
  char *v20; // rbp
  char *v21; // rsi
  unsigned __int8 v22; // r15
  bool v23; // zf
  unsigned __int8 v24; // r14
  __int64 v25; // r12
  size_t v26; // r8
  char *v27; // rax
  unsigned __int64 v28; // rcx
  char *v29; // rdi
  __int128 v30; // xmm0
  __int64 v31; // r15
  __int64 v32; // r14
  size_t v33; // r8
  char *v34; // rbp
  int v35; // edx
  int v36; // [rsp+20h] [rbp-48h]
  char *v37; // [rsp+28h] [rbp-40h]

  v6 = 0;
  v7 = 0;
  v8 = a2;
  v9 = 0;
  *a6 = 0;
  if ( a2 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v6 += v12;
      v13 = v12 + v7;
      if ( v9 >= 2u )
        v13 = v7;
      ++v9;
      v7 = v13;
    }
    while ( v9 < a2 );
    if ( (unsigned __int64)(v6 + v13) > 0xFFFF )
      return 534;
  }
  v15 = 16LL * a2;
  v16 = v6 + v15 + 46;
  if ( !v16 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v18 = (char *)HeapAlloc(ProcessHeap, 8u, v16);
  v20 = v18;
  if ( !v18 )
    return 8;
  if ( v15 && v16 >= v15 )
  {
    v21 = &v18[v15];
    v16 -= v15;
  }
  else
  {
    v21 = v18;
    v20 = 0;
  }
  v22 = 0;
  v23 = a4 == -2;
  v24 = a4 + 2;
  LOBYTE(v19) = v24;
  v36 = v19;
  if ( !v23 )
  {
    v25 = 0;
    do
    {
      if ( v22 >= 2u )
      {
        v26 = *(unsigned int *)(a3 + 16 * v25 + 8);
        if ( *(_DWORD *)(a3 + 16 * v25 + 8) && v16 >= v26 )
        {
          v27 = v21;
          v21 += v26;
          v16 -= v26;
        }
        else
        {
          v27 = 0;
        }
        v37 = v27;
        memcpy_0(v27, *(const void **)(a3 + 16 * v25), v26);
        *(_QWORD *)&v20[16 * v25] = v37;
        *(_DWORD *)&v20[16 * v25 + 12] = *(_DWORD *)(a3 + 16 * v25 + 12);
        *(_DWORD *)&v20[16 * v25 + 8] = *(_DWORD *)(a3 + 16 * v25 + 8);
      }
      else
      {
        *(_OWORD *)&v20[16 * v25] = *(_OWORD *)(a3 + 16 * v25);
      }
      ++v22;
      ++v25;
    }
    while ( v22 < v24 );
    v8 = a2;
    LOBYTE(v19) = v36;
  }
  v28 = v16;
  v29 = v21;
  if ( v16 >= 0x2E )
  {
    v21 += 46;
    v16 -= 46LL;
  }
  if ( v28 < 0x2E )
    v29 = 0;
  *((_QWORD *)v29 + 2) = v20;
  v30 = *a1;
  v29[45] = a4;
  *((_DWORD *)v29 + 10) = a5;
  v29[44] = v8;
  *(_OWORD *)v29 = v30;
  if ( (unsigned __int8)v19 < v8 )
  {
    v31 = v24;
    do
    {
      v32 = 2 * v31;
      v33 = *(unsigned int *)(a3 + 16 * v31 + 8);
      if ( *(_DWORD *)(a3 + 16 * v31 + 8) && v16 >= v33 )
      {
        v34 = v21;
        v21 += v33;
        v16 -= v33;
      }
      else
      {
        v34 = 0;
      }
      memcpy_0(v34, *(const void **)(a3 + 16 * v31++), v33);
      v35 = v36;
      LOBYTE(v35) = v36 + 1;
      v36 = v35;
      *(_QWORD *)(*((_QWORD *)v29 + 2) + 8 * v32) = v34;
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 12) = *(_DWORD *)(a3 + 8 * v32 + 12);
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 8) = *(_DWORD *)(a3 + 8 * v32 + 8);
    }
    while ( (unsigned __int8)v35 < v8 );
  }
  *a6 = v29;
  return 0;
}

```

## disassembly

```asm
0x18001e3b8  mov     rax, rsp
0x18001e3bb  mov     [rax+18h], rbx
0x18001e3bf  mov     [rax+20h], r9b
0x18001e3c3  mov     [rax+10h], dl
0x18001e3c6  mov     [rax+8], rcx
0x18001e3ca  push    rbp
0x18001e3cb  push    rsi
0x18001e3cc  push    rdi
0x18001e3cd  push    r12
0x18001e3cf  push    r13
0x18001e3d1  push    r14
0x18001e3d3  push    r15
0x18001e3d5  sub     rsp, 30h
0x18001e3d9  mov     rax, [rsp+68h+arg_28]
0x18001e3e1  xor     r10d, r10d
0x18001e3e4  xor     r11d, r11d
0x18001e3e7  movzx   r12d, dl
0x18001e3eb  xor     bl, bl
0x18001e3ed  mov     r14b, r9b
0x18001e3f0  mov     r13, r8
0x18001e3f3  mov     [rax], r10
0x18001e3f6  test    dl, dl
0x18001e3f8  jz      short loc_18001E437
0x18001e3fa  movzx   eax, bl
0x18001e3fd  add     rax, rax
0x18001e400  cmp     bl, 2
0x18001e403  mov     ecx, [r8+rax*8+8]
0x18001e408  lea     rax, [rcx+r10]
0x18001e40c  cmovnb  r10, rax
0x18001e410  lea     rax, [rcx+r11]
0x18001e414  cmovnb  rax, r11
0x18001e418  inc     bl
0x18001e41a  mov     r11, rax
0x18001e41d  cmp     bl, r12b
0x18001e420  jb      short loc_18001E3FA
0x18001e422  add     rax, r10
0x18001e425  cmp     rax, 0FFFFh
0x18001e42b  jbe     short loc_18001E437
0x18001e42d  mov     eax, 216h
0x18001e432  jmp     loc_18001E5D8
0x18001e437  mov     rdi, r12
0x18001e43a  mov     esi, 8
0x18001e43f  shl     rdi, 4
0x18001e443  lea     rbx, [rdi+2Eh]
0x18001e447  add     rbx, r10
0x18001e44a  jz      loc_18001E5D6
0x18001e450  call    cs:__imp_GetProcessHeap
0x18001e456  mov     r8, rbx; dwBytes
0x18001e459  mov     edx, esi; dwFlags
0x18001e45b  mov     rcx, rax; hHeap
0x18001e45e  call    cs:__imp_HeapAlloc
0x18001e464  mov     rbp, rax
0x18001e467  test    rax, rax
0x18001e46a  jz      loc_18001E5D6
0x18001e470  test    rdi, rdi
0x18001e473  jz      short loc_18001E483
0x18001e475  cmp     rbx, rdi
0x18001e478  jb      short loc_18001E483
0x18001e47a  lea     rsi, [rdi+rax]
0x18001e47e  sub     rbx, rdi
0x18001e481  jmp     short loc_18001E488
0x18001e483  mov     rsi, rax
0x18001e486  xor     ebp, ebp
0x18001e488  xor     r15b, r15b
0x18001e48b  add     r14b, 2
0x18001e48f  mov     dl, r14b
0x18001e492  mov     [rsp+68h+var_48], edx
0x18001e496  jz      short loc_18001E513
0x18001e498  xor     r12d, r12d
0x18001e49b  mov     rdi, r12
0x18001e49e  add     rdi, rdi
0x18001e4a1  cmp     r15b, 2
0x18001e4a5  jnb     short loc_18001E4B5
0x18001e4a7  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x18001e4ad  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18001e4b3  jmp     short loc_18001E4FF
0x18001e4b5  mov     r8d, [r13+rdi*8+8]; Size
0x18001e4ba  test    r8, r8
0x18001e4bd  jz      short loc_18001E4CF
0x18001e4bf  cmp     rbx, r8
0x18001e4c2  jb      short loc_18001E4CF
0x18001e4c4  mov     rax, rsi
0x18001e4c7  add     rsi, r8
0x18001e4ca  sub     rbx, r8
0x18001e4cd  jmp     short loc_18001E4D1
0x18001e4cf  xor     eax, eax
0x18001e4d1  mov     rdx, [r13+rdi*8+0]; Src
0x18001e4d6  mov     rcx, rax; void *
0x18001e4d9  mov     [rsp+68h+var_40], rax
0x18001e4de  call    memcpy_0
0x18001e4e3  mov     rax, [rsp+68h+var_40]
0x18001e4e8  mov     [rbp+rdi*8+0], rax
0x18001e4ed  mov     eax, [r13+rdi*8+0Ch]
0x18001e4f2  mov     [rbp+rdi*8+0Ch], eax
0x18001e4f6  mov     eax, [r13+rdi*8+8]
0x18001e4fb  mov     [rbp+rdi*8+8], eax
0x18001e4ff  inc     r15b
0x18001e502  inc     r12
0x18001e505  cmp     r15b, r14b
0x18001e508  jb      short loc_18001E49B
0x18001e50a  mov     r12b, [rsp+68h+arg_8]
0x18001e50f  mov     edx, [rsp+68h+var_48]
0x18001e513  mov     rcx, rbx
0x18001e516  mov     rdi, rsi
0x18001e519  cmp     rbx, 2Eh ; '.'
0x18001e51d  jb      short loc_18001E527
0x18001e51f  add     rsi, 2Eh ; '.'
0x18001e523  sub     rbx, 2Eh ; '.'
0x18001e527  xor     eax, eax
0x18001e529  cmp     rcx, 2Eh ; '.'
0x18001e52d  cmovb   rdi, rax
0x18001e531  mov     rax, [rsp+68h+arg_0]
0x18001e536  mov     [rdi+10h], rbp
0x18001e53a  movups  xmm0, xmmword ptr [rax]
0x18001e53d  mov     al, [rsp+68h+arg_18]
0x18001e544  mov     [rdi+2Dh], al
0x18001e547  mov     eax, [rsp+68h+arg_20]
0x18001e54e  mov     [rdi+28h], eax
0x18001e551  mov     [rdi+2Ch], r12b
0x18001e555  movdqu  xmmword ptr [rdi], xmm0
0x18001e559  cmp     dl, r12b
0x18001e55c  jnb     short loc_18001E5C7
0x18001e55e  movzx   r15d, r14b
0x18001e562  mov     r14, r15
0x18001e565  add     r14, r14
0x18001e568  mov     r8d, [r13+r14*8+8]; Size
0x18001e56d  test    r8, r8
0x18001e570  jz      short loc_18001E582
0x18001e572  cmp     rbx, r8
0x18001e575  jb      short loc_18001E582
0x18001e577  mov     rbp, rsi
0x18001e57a  add     rsi, r8
0x18001e57d  sub     rbx, r8
0x18001e580  jmp     short loc_18001E584
0x18001e582  xor     ebp, ebp
0x18001e584  mov     rdx, [r13+r14*8+0]; Src
0x18001e589  mov     rcx, rbp; void *
0x18001e58c  call    memcpy_0
0x18001e591  mov     rax, [rdi+10h]
0x18001e595  inc     r15
0x18001e598  mov     edx, [rsp+68h+var_48]
0x18001e59c  inc     dl
0x18001e59e  mov     [rsp+68h+var_48], edx
0x18001e5a2  mov     [rax+r14*8], rbp
0x18001e5a6  mov     rcx, [rdi+10h]
0x18001e5aa  mov     eax, [r13+r14*8+0Ch]
0x18001e5af  mov     [rcx+r14*8+0Ch], eax
0x18001e5b4  mov     rcx, [rdi+10h]
0x18001e5b8  mov     eax, [r13+r14*8+8]
0x18001e5bd  mov     [rcx+r14*8+8], eax
0x18001e5c2  cmp     dl, r12b
0x18001e5c5  jb      short loc_18001E562
0x18001e5c7  mov     rax, [rsp+68h+arg_28]
0x18001e5cf  mov     [rax], rdi
0x18001e5d2  xor     eax, eax
0x18001e5d4  jmp     short loc_18001E5D8
0x18001e5d6  mov     eax, esi
0x18001e5d8  mov     rbx, [rsp+68h+arg_10]
0x18001e5e0  add     rsp, 30h
0x18001e5e4  pop     r15
0x18001e5e6  pop     r14
0x18001e5e8  pop     r13
0x18001e5ea  pop     r12
0x18001e5ec  pop     rdi
0x18001e5ed  pop     rsi
0x18001e5ee  pop     rbp
0x18001e5ef  retn
```
