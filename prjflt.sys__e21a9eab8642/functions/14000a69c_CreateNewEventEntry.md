# CreateNewEventEntry

- ea: `0x14000a69c`
- end: `0x14000a905`
- name: `CreateNewEventEntry`
- size: `617`
- prototype: `__int64 __fastcall(char, __int128 *, unsigned __int8, __int64, char, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aad0`

## callees

- `0x14000a69c`
- `0x14000bb80`
- `0x14000be80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a747`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a747`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(
        char a1,
        __int128 *a2,
        unsigned __int8 a3,
        __int64 a4,
        char a5,
        int a6,
        _QWORD *a7)
{
  __int64 v7; // r10
  __int64 v8; // r11
  unsigned __int8 v9; // r13
  unsigned __int8 v10; // bl
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v16; // rdi
  SIZE_T v17; // rbx
  char *PoolWithTag; // rax
  char *v19; // rbp
  int v20; // r9d
  char *v21; // rsi
  char *v22; // r15
  char v23; // dl
  unsigned __int8 v24; // r14
  unsigned __int8 v25; // bp
  __int64 v26; // r13
  size_t v27; // r8
  char *v28; // rax
  unsigned __int64 v29; // rcx
  char *v30; // rdi
  __int128 v31; // xmm0
  __int64 v32; // r15
  __int64 v33; // r14
  size_t v34; // r8
  char *v35; // rbp
  int v36; // r9d
  int v37; // [rsp+20h] [rbp-48h]
  char *v38; // [rsp+28h] [rbp-40h]

  v7 = 0;
  v8 = 0;
  v9 = a3;
  v10 = 0;
  *a7 = 0;
  if ( a3 )
  {
    do
    {
      v13 = *(unsigned int *)(a4 + 16LL * v10 + 8);
      if ( v10 >= 2u )
        v7 += v13;
      v14 = v13 + v8;
      if ( v10 >= 2u )
        v14 = v8;
      ++v10;
      v8 = v14;
    }
    while ( v10 < a3 );
    if ( (unsigned __int64)(v7 + v14) > 0xFFFF )
      return 3221225621LL;
  }
  v16 = 16LL * a3;
  v17 = v7 + v16 + 46;
  if ( !v17 )
    return 3221225495LL;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : 512), v17, 0x47417254u);
  v19 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225495LL;
  memset(PoolWithTag, 0, v17);
  if ( v16 && v17 >= v16 )
  {
    v21 = &v19[v16];
    v17 -= v16;
    v22 = v19;
  }
  else
  {
    v22 = 0;
    v21 = v19;
  }
  v23 = a5;
  v24 = 0;
  v25 = a5 + 2;
  LOBYTE(v20) = a5 + 2;
  v37 = v20;
  if ( a5 != -2 )
  {
    v26 = 0;
    do
    {
      if ( v24 >= 2u )
      {
        v27 = *(unsigned int *)(a4 + 16 * v26 + 8);
        if ( *(_DWORD *)(a4 + 16 * v26 + 8) && v17 >= v27 )
        {
          v28 = v21;
          v21 += v27;
          v17 -= v27;
        }
        else
        {
          v28 = 0;
        }
        v38 = v28;
        memmove(v28, *(const void **)(a4 + 16 * v26), v27);
        *(_QWORD *)&v22[16 * v26] = v38;
        *(_DWORD *)&v22[16 * v26 + 12] = *(_DWORD *)(a4 + 16 * v26 + 12);
        *(_DWORD *)&v22[16 * v26 + 8] = *(_DWORD *)(a4 + 16 * v26 + 8);
      }
      else
      {
        *(_OWORD *)&v22[16 * v26] = *(_OWORD *)(a4 + 16 * v26);
      }
      ++v24;
      ++v26;
    }
    while ( v24 < v25 );
    v9 = a3;
    v23 = a5;
    LOBYTE(v20) = v37;
  }
  v29 = v17;
  v30 = v21;
  if ( v17 >= 0x2E )
  {
    v21 += 46;
    v17 -= 46LL;
  }
  if ( v29 < 0x2E )
    v30 = 0;
  *((_QWORD *)v30 + 2) = v22;
  v31 = *a2;
  v30[44] = v9;
  v30[45] = v23;
  *((_DWORD *)v30 + 10) = a6;
  *(_OWORD *)v30 = v31;
  if ( (unsigned __int8)v20 < v9 )
  {
    v32 = v25;
    do
    {
      v33 = 2 * v32;
      v34 = *(unsigned int *)(a4 + 16 * v32 + 8);
      if ( *(_DWORD *)(a4 + 16 * v32 + 8) && v17 >= v34 )
      {
        v35 = v21;
        v21 += v34;
        v17 -= v34;
      }
      else
      {
        v35 = 0;
      }
      memmove(v35, *(const void **)(a4 + 16 * v32++), v34);
      v36 = v37;
      LOBYTE(v36) = v37 + 1;
      v37 = v36;
      *(_QWORD *)(*((_QWORD *)v30 + 2) + 8 * v33) = v35;
      *(_DWORD *)(*((_QWORD *)v30 + 2) + 8 * v33 + 12) = *(_DWORD *)(a4 + 8 * v33 + 12);
      *(_DWORD *)(*((_QWORD *)v30 + 2) + 8 * v33 + 8) = *(_DWORD *)(a4 + 8 * v33 + 8);
    }
    while ( (unsigned __int8)v36 < v9 );
  }
  *a7 = v30;
  return 0;
}

```

## disassembly

```asm
0x14000a69c  mov     [rsp+arg_0], rbx
0x14000a6a1  mov     [rsp+arg_10], r8b
0x14000a6a6  mov     [rsp+arg_8], rdx
0x14000a6ab  push    rbp
0x14000a6ac  push    rsi
0x14000a6ad  push    rdi
0x14000a6ae  push    r12
0x14000a6b0  push    r13
0x14000a6b2  push    r14
0x14000a6b4  push    r15
0x14000a6b6  sub     rsp, 30h
0x14000a6ba  mov     rax, [rsp+68h+arg_30]
0x14000a6c2  xor     r10d, r10d
0x14000a6c5  xor     r11d, r11d
0x14000a6c8  movzx   r13d, r8b
0x14000a6cc  xor     bl, bl
0x14000a6ce  mov     r12, r9
0x14000a6d1  mov     r9b, cl
0x14000a6d4  mov     [rax], r10
0x14000a6d7  test    r8b, r8b
0x14000a6da  jz      short loc_14000A719
0x14000a6dc  movzx   eax, bl
0x14000a6df  add     rax, rax
0x14000a6e2  cmp     bl, 2
0x14000a6e5  mov     ecx, [r12+rax*8+8]
0x14000a6ea  lea     rax, [rcx+r10]
0x14000a6ee  cmovnb  r10, rax
0x14000a6f2  lea     rax, [rcx+r11]
0x14000a6f6  cmovnb  rax, r11
0x14000a6fa  inc     bl
0x14000a6fc  mov     r11, rax
0x14000a6ff  cmp     bl, r13b
0x14000a702  jb      short loc_14000A6DC
0x14000a704  add     rax, r10
0x14000a707  cmp     rax, 0FFFFh
0x14000a70d  jbe     short loc_14000A719
0x14000a70f  mov     eax, 0C0000095h
0x14000a714  jmp     loc_14000A8EF
0x14000a719  mov     rdi, r13
0x14000a71c  shl     rdi, 4
0x14000a720  lea     rbx, [rdi+2Eh]
0x14000a724  add     rbx, r10
0x14000a727  jz      loc_14000A8EA
0x14000a72d  neg     r9b
0x14000a730  mov     r8d, 47417254h; Tag
0x14000a736  mov     rdx, rbx; NumberOfBytes
0x14000a739  sbb     ecx, ecx
0x14000a73b  and     ecx, 0FFFFFE01h
0x14000a741  add     ecx, 200h; PoolType
0x14000a747  call    cs:__imp_ExAllocatePoolWithTag
0x14000a74e  nop     dword ptr [rax+rax+00h]
0x14000a753  mov     rbp, rax
0x14000a756  test    rax, rax
0x14000a759  jz      loc_14000A8EA
0x14000a75f  mov     r8, rbx; Size
0x14000a762  xor     edx, edx; Val
0x14000a764  mov     rcx, rax; void *
0x14000a767  call    memset
0x14000a76c  test    rdi, rdi
0x14000a76f  jz      short loc_14000A782
0x14000a771  cmp     rbx, rdi
0x14000a774  jb      short loc_14000A782
0x14000a776  lea     rsi, [rdi+rbp]
0x14000a77a  sub     rbx, rdi
0x14000a77d  mov     r15, rbp
0x14000a780  jmp     short loc_14000A788
0x14000a782  xor     r15d, r15d
0x14000a785  mov     rsi, rbp
0x14000a788  mov     dl, [rsp+68h+arg_20]
0x14000a78f  xor     r14b, r14b
0x14000a792  mov     bpl, dl
0x14000a795  add     bpl, 2
0x14000a799  mov     r9b, bpl
0x14000a79c  mov     [rsp+68h+var_48], r9d
0x14000a7a1  jz      loc_14000A82C
0x14000a7a7  xor     r13d, r13d
0x14000a7aa  mov     rdi, r13
0x14000a7ad  add     rdi, rdi
0x14000a7b0  cmp     r14b, 2
0x14000a7b4  jnb     short loc_14000A7C3
0x14000a7b6  movups  xmm0, xmmword ptr [r12+rdi*8]
0x14000a7bb  movdqu  xmmword ptr [r15+rdi*8], xmm0
0x14000a7c1  jmp     short loc_14000A80D
0x14000a7c3  mov     r8d, [r12+rdi*8+8]; Size
0x14000a7c8  test    r8, r8
0x14000a7cb  jz      short loc_14000A7DD
0x14000a7cd  cmp     rbx, r8
0x14000a7d0  jb      short loc_14000A7DD
0x14000a7d2  mov     rax, rsi
0x14000a7d5  add     rsi, r8
0x14000a7d8  sub     rbx, r8
0x14000a7db  jmp     short loc_14000A7DF
0x14000a7dd  xor     eax, eax
0x14000a7df  mov     rdx, [r12+rdi*8]; Src
0x14000a7e3  mov     rcx, rax; void *
0x14000a7e6  mov     [rsp+68h+var_40], rax
0x14000a7eb  call    memmove
0x14000a7f0  mov     rax, [rsp+68h+var_40]
0x14000a7f5  mov     [r15+rdi*8], rax
0x14000a7f9  mov     eax, [r12+rdi*8+0Ch]
0x14000a7fe  mov     [r15+rdi*8+0Ch], eax
0x14000a803  mov     eax, [r12+rdi*8+8]
0x14000a808  mov     [r15+rdi*8+8], eax
0x14000a80d  inc     r14b
0x14000a810  inc     r13
0x14000a813  cmp     r14b, bpl
0x14000a816  jb      short loc_14000A7AA
0x14000a818  mov     r13b, [rsp+68h+arg_10]
0x14000a820  mov     dl, [rsp+68h+arg_20]
0x14000a827  mov     r9d, [rsp+68h+var_48]
0x14000a82c  mov     rcx, rbx
0x14000a82f  mov     rdi, rsi
0x14000a832  cmp     rbx, 2Eh ; '.'
0x14000a836  jb      short loc_14000A840
0x14000a838  add     rsi, 2Eh ; '.'
0x14000a83c  sub     rbx, 2Eh ; '.'
0x14000a840  xor     eax, eax
0x14000a842  cmp     rcx, 2Eh ; '.'
0x14000a846  cmovb   rdi, rax
0x14000a84a  mov     rax, [rsp+68h+arg_8]
0x14000a84f  mov     [rdi+10h], r15
0x14000a853  movups  xmm0, xmmword ptr [rax]
0x14000a856  mov     eax, [rsp+68h+arg_28]
0x14000a85d  mov     [rdi+2Ch], r13b
0x14000a861  mov     [rdi+2Dh], dl
0x14000a864  mov     [rdi+28h], eax
0x14000a867  movdqu  xmmword ptr [rdi], xmm0
0x14000a86b  cmp     r9b, r13b
0x14000a86e  jnb     short loc_14000A8DB
0x14000a870  movzx   r15d, bpl
0x14000a874  mov     r14, r15
0x14000a877  add     r14, r14
0x14000a87a  mov     r8d, [r12+r14*8+8]; Size
0x14000a87f  test    r8, r8
0x14000a882  jz      short loc_14000A894
0x14000a884  cmp     rbx, r8
0x14000a887  jb      short loc_14000A894
0x14000a889  mov     rbp, rsi
0x14000a88c  add     rsi, r8
0x14000a88f  sub     rbx, r8
0x14000a892  jmp     short loc_14000A896
0x14000a894  xor     ebp, ebp
0x14000a896  mov     rdx, [r12+r14*8]; Src
0x14000a89a  mov     rcx, rbp; void *
0x14000a89d  call    memmove
0x14000a8a2  mov     rax, [rdi+10h]
0x14000a8a6  inc     r15
0x14000a8a9  mov     r9d, [rsp+68h+var_48]
0x14000a8ae  inc     r9b
0x14000a8b1  mov     [rsp+68h+var_48], r9d
0x14000a8b6  mov     [rax+r14*8], rbp
0x14000a8ba  mov     rcx, [rdi+10h]
0x14000a8be  mov     eax, [r12+r14*8+0Ch]
0x14000a8c3  mov     [rcx+r14*8+0Ch], eax
0x14000a8c8  mov     rcx, [rdi+10h]
0x14000a8cc  mov     eax, [r12+r14*8+8]
0x14000a8d1  mov     [rcx+r14*8+8], eax
0x14000a8d6  cmp     r9b, r13b
0x14000a8d9  jb      short loc_14000A874
0x14000a8db  mov     rax, [rsp+68h+arg_30]
0x14000a8e3  mov     [rax], rdi
0x14000a8e6  xor     eax, eax
0x14000a8e8  jmp     short loc_14000A8EF
0x14000a8ea  mov     eax, 0C0000017h
0x14000a8ef  mov     rbx, [rsp+68h+arg_0]
0x14000a8f4  add     rsp, 30h
0x14000a8f8  pop     r15
0x14000a8fa  pop     r14
0x14000a8fc  pop     r13
0x14000a8fe  pop     r12
0x14000a900  pop     rdi
0x14000a901  pop     rsi
0x14000a902  pop     rbp
0x14000a903  retn
```
