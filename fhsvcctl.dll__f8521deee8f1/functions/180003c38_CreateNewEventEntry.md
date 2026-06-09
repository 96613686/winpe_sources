# CreateNewEventEntry

- ea: `0x180003c38`
- end: `0x180003e70`
- name: `CreateNewEventEntry`
- size: `568`
- prototype: `__int64 __fastcall(__int128 *, unsigned __int8, __int64, char, int, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004120`

## callees

- `0x180003c38`
- `0x180004ee2`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003cde`
- `KERNEL32!HeapAlloc` at `0x180003cde`
- `KERNEL32!GetProcessHeap` at `0x180003cd0`
- `KERNEL32!GetProcessHeap` at `0x180003cd0`

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
0x180003c38  mov     rax, rsp
0x180003c3b  mov     [rax+18h], rbx
0x180003c3f  mov     [rax+20h], r9b
0x180003c43  mov     [rax+10h], dl
0x180003c46  mov     [rax+8], rcx
0x180003c4a  push    rbp
0x180003c4b  push    rsi
0x180003c4c  push    rdi
0x180003c4d  push    r12
0x180003c4f  push    r13
0x180003c51  push    r14
0x180003c53  push    r15
0x180003c55  sub     rsp, 30h
0x180003c59  mov     rax, [rsp+68h+arg_28]
0x180003c61  xor     r10d, r10d
0x180003c64  xor     r11d, r11d
0x180003c67  movzx   r12d, dl
0x180003c6b  xor     bl, bl
0x180003c6d  mov     r14b, r9b
0x180003c70  mov     r13, r8
0x180003c73  mov     [rax], r10
0x180003c76  test    dl, dl
0x180003c78  jz      short loc_180003CB7
0x180003c7a  movzx   eax, bl
0x180003c7d  add     rax, rax
0x180003c80  cmp     bl, 2
0x180003c83  mov     ecx, [r8+rax*8+8]
0x180003c88  lea     rax, [rcx+r10]
0x180003c8c  cmovnb  r10, rax
0x180003c90  lea     rax, [rcx+r11]
0x180003c94  cmovnb  rax, r11
0x180003c98  inc     bl
0x180003c9a  mov     r11, rax
0x180003c9d  cmp     bl, r12b
0x180003ca0  jb      short loc_180003C7A
0x180003ca2  add     rax, r10
0x180003ca5  cmp     rax, 0FFFFh
0x180003cab  jbe     short loc_180003CB7
0x180003cad  mov     eax, 216h
0x180003cb2  jmp     loc_180003E58
0x180003cb7  mov     rdi, r12
0x180003cba  mov     esi, 8
0x180003cbf  shl     rdi, 4
0x180003cc3  lea     rbx, [rdi+2Eh]
0x180003cc7  add     rbx, r10
0x180003cca  jz      loc_180003E56
0x180003cd0  call    cs:__imp_GetProcessHeap
0x180003cd6  mov     r8, rbx; dwBytes
0x180003cd9  mov     edx, esi; dwFlags
0x180003cdb  mov     rcx, rax; hHeap
0x180003cde  call    cs:__imp_HeapAlloc
0x180003ce4  mov     rbp, rax
0x180003ce7  test    rax, rax
0x180003cea  jz      loc_180003E56
0x180003cf0  test    rdi, rdi
0x180003cf3  jz      short loc_180003D03
0x180003cf5  cmp     rbx, rdi
0x180003cf8  jb      short loc_180003D03
0x180003cfa  lea     rsi, [rdi+rax]
0x180003cfe  sub     rbx, rdi
0x180003d01  jmp     short loc_180003D08
0x180003d03  mov     rsi, rax
0x180003d06  xor     ebp, ebp
0x180003d08  xor     r15b, r15b
0x180003d0b  add     r14b, 2
0x180003d0f  mov     dl, r14b
0x180003d12  mov     [rsp+68h+var_48], edx
0x180003d16  jz      short loc_180003D93
0x180003d18  xor     r12d, r12d
0x180003d1b  mov     rdi, r12
0x180003d1e  add     rdi, rdi
0x180003d21  cmp     r15b, 2
0x180003d25  jnb     short loc_180003D35
0x180003d27  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x180003d2d  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x180003d33  jmp     short loc_180003D7F
0x180003d35  mov     r8d, [r13+rdi*8+8]; Size
0x180003d3a  test    r8, r8
0x180003d3d  jz      short loc_180003D4F
0x180003d3f  cmp     rbx, r8
0x180003d42  jb      short loc_180003D4F
0x180003d44  mov     rax, rsi
0x180003d47  add     rsi, r8
0x180003d4a  sub     rbx, r8
0x180003d4d  jmp     short loc_180003D51
0x180003d4f  xor     eax, eax
0x180003d51  mov     rdx, [r13+rdi*8+0]; Src
0x180003d56  mov     rcx, rax; void *
0x180003d59  mov     [rsp+68h+var_40], rax
0x180003d5e  call    memcpy_0
0x180003d63  mov     rax, [rsp+68h+var_40]
0x180003d68  mov     [rbp+rdi*8+0], rax
0x180003d6d  mov     eax, [r13+rdi*8+0Ch]
0x180003d72  mov     [rbp+rdi*8+0Ch], eax
0x180003d76  mov     eax, [r13+rdi*8+8]
0x180003d7b  mov     [rbp+rdi*8+8], eax
0x180003d7f  inc     r15b
0x180003d82  inc     r12
0x180003d85  cmp     r15b, r14b
0x180003d88  jb      short loc_180003D1B
0x180003d8a  mov     r12b, [rsp+68h+arg_8]
0x180003d8f  mov     edx, [rsp+68h+var_48]
0x180003d93  mov     rcx, rbx
0x180003d96  mov     rdi, rsi
0x180003d99  cmp     rbx, 2Eh ; '.'
0x180003d9d  jb      short loc_180003DA7
0x180003d9f  add     rsi, 2Eh ; '.'
0x180003da3  sub     rbx, 2Eh ; '.'
0x180003da7  xor     eax, eax
0x180003da9  cmp     rcx, 2Eh ; '.'
0x180003dad  cmovb   rdi, rax
0x180003db1  mov     rax, [rsp+68h+arg_0]
0x180003db6  mov     [rdi+10h], rbp
0x180003dba  movups  xmm0, xmmword ptr [rax]
0x180003dbd  mov     al, [rsp+68h+arg_18]
0x180003dc4  mov     [rdi+2Dh], al
0x180003dc7  mov     eax, [rsp+68h+arg_20]
0x180003dce  mov     [rdi+28h], eax
0x180003dd1  mov     [rdi+2Ch], r12b
0x180003dd5  movdqu  xmmword ptr [rdi], xmm0
0x180003dd9  cmp     dl, r12b
0x180003ddc  jnb     short loc_180003E47
0x180003dde  movzx   r15d, r14b
0x180003de2  mov     r14, r15
0x180003de5  add     r14, r14
0x180003de8  mov     r8d, [r13+r14*8+8]; Size
0x180003ded  test    r8, r8
0x180003df0  jz      short loc_180003E02
0x180003df2  cmp     rbx, r8
0x180003df5  jb      short loc_180003E02
0x180003df7  mov     rbp, rsi
0x180003dfa  add     rsi, r8
0x180003dfd  sub     rbx, r8
0x180003e00  jmp     short loc_180003E04
0x180003e02  xor     ebp, ebp
0x180003e04  mov     rdx, [r13+r14*8+0]; Src
0x180003e09  mov     rcx, rbp; void *
0x180003e0c  call    memcpy_0
0x180003e11  mov     rax, [rdi+10h]
0x180003e15  inc     r15
0x180003e18  mov     edx, [rsp+68h+var_48]
0x180003e1c  inc     dl
0x180003e1e  mov     [rsp+68h+var_48], edx
0x180003e22  mov     [rax+r14*8], rbp
0x180003e26  mov     rcx, [rdi+10h]
0x180003e2a  mov     eax, [r13+r14*8+0Ch]
0x180003e2f  mov     [rcx+r14*8+0Ch], eax
0x180003e34  mov     rcx, [rdi+10h]
0x180003e38  mov     eax, [r13+r14*8+8]
0x180003e3d  mov     [rcx+r14*8+8], eax
0x180003e42  cmp     dl, r12b
0x180003e45  jb      short loc_180003DE2
0x180003e47  mov     rax, [rsp+68h+arg_28]
0x180003e4f  mov     [rax], rdi
0x180003e52  xor     eax, eax
0x180003e54  jmp     short loc_180003E58
0x180003e56  mov     eax, esi
0x180003e58  mov     rbx, [rsp+68h+arg_10]
0x180003e60  add     rsp, 30h
0x180003e64  pop     r15
0x180003e66  pop     r14
0x180003e68  pop     r13
0x180003e6a  pop     r12
0x180003e6c  pop     rdi
0x180003e6d  pop     rsi
0x180003e6e  pop     rbp
0x180003e6f  retn
```
