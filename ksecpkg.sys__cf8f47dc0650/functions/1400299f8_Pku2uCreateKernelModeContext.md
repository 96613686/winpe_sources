# Pku2uCreateKernelModeContext

- ea: `0x1400299f8`
- end: `0x140029d8e`
- name: `Pku2uCreateKernelModeContext`
- size: `918`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140021db0`
- `0x140022010`

## callees

- `0x140007008`
- `0x14000dca8`
- `0x140010240`
- `0x1400102c0`
- `0x14002995c`
- `0x1400299f8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029ae3`
- `ntoskrnl!ExAllocatePool2` at `0x140029b60`
- `ntoskrnl!ExAllocatePool2` at `0x140029bf1`
- `ntoskrnl!ExAllocatePool2` at `0x140029c6e`
- `ntoskrnl!ExAllocatePool2` at `0x140029cf7`
- `ntoskrnl!ExAllocatePool2` at `0x140029ae3`
- `ntoskrnl!ExAllocatePool2` at `0x140029b60`
- `ntoskrnl!ExAllocatePool2` at `0x140029bf1`
- `ntoskrnl!ExAllocatePool2` at `0x140029c6e`
- `ntoskrnl!ExAllocatePool2` at `0x140029cf7`

## pseudocode

```c
__int64 __fastcall Pku2uCreateKernelModeContext(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, int a5)
{
  unsigned int v5; // r8d
  __int64 v6; // r12
  __int64 v8; // rsi
  enum _POOL_TYPE v9; // r14d
  int v10; // eax
  unsigned __int16 *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // ecx
  unsigned int v14; // ebp
  unsigned int v15; // ecx
  __int64 v16; // r15
  __int64 v17; // r8
  __int64 v18; // r13
  __int64 v19; // r12
  __int64 Pool2; // rax
  unsigned __int16 v21; // bp
  __int64 v22; // rax
  unsigned __int16 v23; // cx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int16 v26; // ax
  unsigned int v27; // eax
  __int64 v28; // rcx
  void *v29; // rax
  unsigned int v30; // eax
  void *v31; // rax
  void *v32; // rcx
  void (__fastcall *v33)(void *, unsigned __int16 *, __int64); // rax
  PVOID P; // [rsp+78h] [rbp+10h] BYREF
  _QWORD *v36; // [rsp+80h] [rbp+18h]
  __int64 v37; // [rsp+88h] [rbp+20h]

  v37 = a4;
  v36 = a3;
  v5 = *(_DWORD *)a2;
  v6 = a4;
  P = 0;
  if ( v5 < 0x48 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Invalid buffer size for marshalled context: was 0x%x, needed 0x%x\n", v5, 72);
    return 3221225485LL;
  }
  v8 = *(_QWORD *)(a2 + 8);
  v9 = Pku2uPoolType;
  v10 = Pku2uAllocateContext((unsigned int)Pku2uPoolType, &P);
  v11 = (unsigned __int16 *)P;
  v12 = v10;
  if ( v10 >= 0 )
  {
    *((_QWORD *)P + 14) = *(_QWORD *)(v8 + 56);
    v13 = *(_DWORD *)(v8 + 52);
    if ( v13 >= 0xFFFD )
    {
      v12 = -1073741637;
      goto LABEL_39;
    }
    v14 = 0;
    v15 = v13 >> 1;
    while ( 1 )
    {
      v16 = 256;
      v17 = 64;
      if ( v14 >= v15 )
        goto LABEL_18;
      v18 = 2LL * v14;
      if ( *(_WORD *)(v18 + *(unsigned int *)(v8 + 48) + v8) == 92 )
        break;
      ++v14;
    }
    v19 = 256;
    if ( v9 != PagedPool )
      v19 = 64;
    Pool2 = ExAllocatePool2(v19, v18 + 2, 1130525264);
    *((_QWORD *)v11 + 18) = Pool2;
    if ( Pool2 )
    {
      v21 = 2 * v14;
      v11[68] = v21;
      v11[69] = v21 + 2;
      memmove(*((void **)v11 + 18), (const void *)(v8 + *(unsigned int *)(v8 + 48)), v11[68]);
      *(_WORD *)(*((_QWORD *)v11 + 18) + 2 * ((unsigned __int64)v11[69] >> 1) - 2) = 0;
      v22 = ExAllocatePool2(v19, *(unsigned int *)(v8 + 52) - v18, 1130525264);
      *((_QWORD *)v11 + 16) = v22;
      if ( v22 )
      {
        v23 = *(_WORD *)(v8 + 52) - v21;
        v11[60] = v23 - 2;
        v11[61] = v23;
        memmove(*((void **)v11 + 16), (const void *)(v8 + v18 + *(unsigned int *)(v8 + 48) + 2LL), v11[60]);
        v6 = v37;
        *(_WORD *)(*((_QWORD *)v11 + 16) + 2 * ((unsigned __int64)v11[61] >> 1) - 2) = 0;
        v17 = 64;
LABEL_18:
        if ( !v11[61] )
        {
          v24 = 256;
          if ( v9 != PagedPool )
            v24 = 64;
          v25 = ExAllocatePool2(v24, *(unsigned int *)(v8 + 52) + 2LL, 1130525264);
          *((_QWORD *)v11 + 16) = v25;
          if ( !v25 )
            goto LABEL_15;
          v26 = *(_WORD *)(v8 + 52);
          v11[60] = v26;
          v11[61] = v26 + 2;
          memmove(*((void **)v11 + 16), (const void *)(v8 + *(unsigned int *)(v8 + 48)), v11[60]);
          *(_WORD *)(*((_QWORD *)v11 + 16) + 2 * ((unsigned __int64)v11[61] >> 1) - 2) = 0;
        }
        if ( *(_DWORD *)(v8 + 64) )
        {
          v27 = *(_DWORD *)(v8 + 68);
          v28 = 256;
          *((_DWORD *)v11 + 42) = v27;
          if ( v9 != PagedPool )
            v28 = 64;
          v29 = (void *)ExAllocatePool2(v28, v27, 1130525264);
          *((_QWORD *)v11 + 20) = v29;
          if ( !v29 )
          {
            v12 = -1073741670;
            goto LABEL_39;
          }
          memmove(v29, (const void *)(v8 + *(unsigned int *)(v8 + 64)), *((unsigned int *)v11 + 42));
        }
        *((_QWORD *)v11 + 7) = *(unsigned int *)(v8 + 8);
        if ( !v6 )
          v6 = *(int *)(v8 + 8);
        *((_QWORD *)v11 + 7) = v6;
        *((_DWORD *)v11 + 27) = *(_DWORD *)(v8 + 44);
        *((_DWORD *)v11 + 26) = *(_DWORD *)(v8 + 40) | a5;
        *((_QWORD *)v11 + 6) = a1;
        *((_DWORD *)v11 + 16) = *(_DWORD *)(v8 + 12);
        v30 = *(_DWORD *)(v8 + 20);
        *((_DWORD *)v11 + 18) = v30;
        if ( !v30 )
        {
LABEL_36:
          v32 = Pku2uNonPagedList;
          v33 = (void (__fastcall *)(void *, unsigned __int16 *, __int64))*((_QWORD *)&xmmword_140019060 + 1);
          if ( v9 == PagedPool )
            v32 = Pku2uPagedList;
          *((_QWORD *)v11 + 1) = 0;
          *(_QWORD *)v11 = 0;
          *((_DWORD *)v11 + 4) = 1;
          *((_DWORD *)v11 + 5) = 1112687947;
          *((_QWORD *)v11 + 3) = 0;
          *((_QWORD *)v11 + 4) = 0;
          v33(v32, v11, v17);
          v12 = 0;
          *v36 = v11;
          v11 = 0;
          goto LABEL_39;
        }
        if ( v9 != PagedPool )
          v16 = 64;
        v31 = (void *)ExAllocatePool2(v16, v30, 1130525264);
        *((_QWORD *)v11 + 10) = v31;
        if ( v31 )
        {
          memmove(v31, (const void *)(v8 + *(unsigned int *)(v8 + 16)), *((unsigned int *)v11 + 18));
          goto LABEL_36;
        }
      }
    }
LABEL_15:
    v12 = -1073741801;
  }
LABEL_39:
  if ( v11 )
    Pku2uFreeContext(v11);
  return v12;
}

```

## disassembly

```asm
0x1400299f8  mov     rax, rsp
0x1400299fb  mov     [rax+20h], r9
0x1400299ff  mov     [rax+18h], r8
0x140029a03  mov     [rax+8], rcx
0x140029a07  push    rbx
0x140029a08  push    rbp
0x140029a09  push    rsi
0x140029a0a  push    rdi
0x140029a0b  push    r12
0x140029a0d  push    r13
0x140029a0f  push    r14
0x140029a11  push    r15
0x140029a13  sub     rsp, 28h
0x140029a17  mov     r8d, [rdx]
0x140029a1a  xor     r13d, r13d
0x140029a1d  mov     r12, r9
0x140029a20  mov     [rax+10h], r13
0x140029a24  lea     r9d, [r13+48h]
0x140029a28  cmp     r8d, r9d
0x140029a2b  jnb     short loc_140029A50
0x140029a2d  cmp     cs:KsecInfoLevel, r13d
0x140029a34  jz      short loc_140029A46
0x140029a36  lea     rdx, aInvalidBufferS_0; "Invalid buffer size for marshalled cont"...
0x140029a3d  lea     ecx, [r13+1]
0x140029a41  call    KsecDebugOut
0x140029a46  mov     eax, 0C000000Dh
0x140029a4b  jmp     loc_140029D7C
0x140029a50  mov     rsi, [rdx+8]
0x140029a54  lea     rdx, [rsp+68h+P]
0x140029a59  mov     r14d, cs:?Pku2uPoolType@@3W4_POOL_TYPE@@A; _POOL_TYPE Pku2uPoolType
0x140029a60  mov     ecx, r14d
0x140029a63  call    Pku2uAllocateContext
0x140029a68  mov     rbx, [rsp+68h+P]
0x140029a6d  mov     edi, eax
0x140029a6f  test    eax, eax
0x140029a71  js      loc_140029D6D
0x140029a77  mov     rax, [rsi+38h]
0x140029a7b  mov     [rbx+70h], rax
0x140029a7f  mov     ecx, [rsi+34h]
0x140029a82  cmp     ecx, 0FFFDh
0x140029a88  jb      short loc_140029A94
0x140029a8a  mov     edi, 0C00000BBh
0x140029a8f  jmp     loc_140029D6D
0x140029a94  mov     ebp, r13d
0x140029a97  shr     ecx, 1
0x140029a99  mov     edi, 1
0x140029a9e  mov     eax, 2
0x140029aa3  mov     r15d, 100h
0x140029aa9  lea     r8d, [rax+3Eh]
0x140029aad  cmp     ebp, ecx
0x140029aaf  jnb     loc_140029BD1
0x140029ab5  mov     eax, ebp
0x140029ab7  lea     r13, [rax+rax]
0x140029abb  mov     eax, [rsi+30h]
0x140029abe  add     rax, r13
0x140029ac1  cmp     word ptr [rax+rsi], 5Ch ; '\'
0x140029ac6  jz      short loc_140029ACC
0x140029ac8  add     ebp, edi
0x140029aca  jmp     short loc_140029A9E
0x140029acc  cmp     r14d, edi
0x140029acf  lea     rdx, [r13+2]
0x140029ad3  mov     r12, r15
0x140029ad6  cmovnz  r12, r8
0x140029ada  mov     r8d, 43627250h
0x140029ae0  mov     rcx, r12
0x140029ae3  call    cs:__imp_ExAllocatePool2
0x140029aea  nop     dword ptr [rax+rax+00h]
0x140029aef  mov     [rbx+90h], rax
0x140029af6  test    rax, rax
0x140029af9  jnz     short loc_140029B05
0x140029afb  mov     edi, 0C0000017h
0x140029b00  jmp     loc_140029D6D
0x140029b05  add     bp, bp
0x140029b08  mov     eax, 2
0x140029b0d  mov     [rbx+88h], bp
0x140029b14  add     eax, ebp
0x140029b16  mov     [rbx+8Ah], ax
0x140029b1d  mov     edx, [rsi+30h]
0x140029b20  movzx   r8d, word ptr [rbx+88h]; Size
0x140029b28  add     rdx, rsi; Src
0x140029b2b  mov     rcx, [rbx+90h]; void *
0x140029b32  call    memmove
0x140029b37  movzx   r8d, word ptr [rbx+8Ah]
0x140029b3f  xor     eax, eax
0x140029b41  mov     rdx, [rbx+90h]
0x140029b48  mov     rcx, r12
0x140029b4b  shr     r8, 1
0x140029b4e  mov     [rdx+r8*2-2], ax
0x140029b54  mov     r8d, 43627250h
0x140029b5a  mov     edx, [rsi+34h]
0x140029b5d  sub     rdx, r13
0x140029b60  call    cs:__imp_ExAllocatePool2
0x140029b67  nop     dword ptr [rax+rax+00h]
0x140029b6c  mov     [rbx+80h], rax
0x140029b73  test    rax, rax
0x140029b76  jz      short loc_140029AFB
0x140029b78  movzx   ecx, word ptr [rsi+34h]
0x140029b7c  sub     cx, bp
0x140029b7f  lea     eax, [rcx-2]
0x140029b82  mov     [rbx+78h], ax
0x140029b86  mov     [rbx+7Ah], cx
0x140029b8a  mov     edx, [rsi+30h]
0x140029b8d  movzx   r8d, word ptr [rbx+78h]; Size
0x140029b92  add     rdx, 2
0x140029b96  mov     rcx, [rbx+80h]; void *
0x140029b9d  add     rdx, r13
0x140029ba0  add     rdx, rsi; Src
0x140029ba3  call    memmove
0x140029ba8  movzx   edx, word ptr [rbx+7Ah]
0x140029bac  mov     rcx, [rbx+80h]
0x140029bb3  mov     r12, [rsp+68h+arg_18]
0x140029bbb  shr     rdx, 1
0x140029bbe  xor     r13d, r13d
0x140029bc1  mov     [rcx+rdx*2-2], r13w
0x140029bc7  lea     eax, [r13+2]
0x140029bcb  lea     r8d, [r13+40h]
0x140029bcf  jmp     short loc_140029BD4
0x140029bd1  xor     r13d, r13d
0x140029bd4  cmp     [rbx+7Ah], r13w
0x140029bd9  jnz     short loc_140029C48
0x140029bdb  mov     edx, [rsi+34h]
0x140029bde  mov     rcx, r15
0x140029be1  add     rdx, rax
0x140029be4  cmp     r14d, edi
0x140029be7  cmovnz  rcx, r8
0x140029beb  mov     r8d, 43627250h
0x140029bf1  call    cs:__imp_ExAllocatePool2
0x140029bf8  nop     dword ptr [rax+rax+00h]
0x140029bfd  mov     [rbx+80h], rax
0x140029c04  test    rax, rax
0x140029c07  jz      loc_140029AFB
0x140029c0d  movzx   eax, word ptr [rsi+34h]
0x140029c11  mov     [rbx+78h], ax
0x140029c15  add     ax, 2
0x140029c19  mov     [rbx+7Ah], ax
0x140029c1d  mov     edx, [rsi+30h]
0x140029c20  movzx   r8d, word ptr [rbx+78h]; Size
0x140029c25  add     rdx, rsi; Src
0x140029c28  mov     rcx, [rbx+80h]; void *
0x140029c2f  call    memmove
0x140029c34  movzx   edx, word ptr [rbx+7Ah]
0x140029c38  mov     rcx, [rbx+80h]
0x140029c3f  shr     rdx, 1
0x140029c42  mov     [rcx+rdx*2-2], r13w
0x140029c48  mov     ebp, 40h ; '@'
0x140029c4d  cmp     [rsi+40h], r13d
0x140029c51  jz      short loc_140029CA5
0x140029c53  mov     eax, [rsi+44h]
0x140029c56  cmp     r14d, edi
0x140029c59  mov     rcx, r15
0x140029c5c  mov     [rbx+0A8h], eax
0x140029c62  cmovnz  rcx, rbp
0x140029c66  mov     edx, eax
0x140029c68  mov     r8d, 43627250h
0x140029c6e  call    cs:__imp_ExAllocatePool2
0x140029c75  nop     dword ptr [rax+rax+00h]
0x140029c7a  mov     [rbx+0A0h], rax
0x140029c81  test    rax, rax
0x140029c84  jnz     short loc_140029C90
0x140029c86  mov     edi, 0C000009Ah
0x140029c8b  jmp     loc_140029D6D
0x140029c90  mov     edx, [rsi+40h]
0x140029c93  mov     rcx, rax; void *
0x140029c96  mov     r8d, [rbx+0A8h]; Size
0x140029c9d  add     rdx, rsi; Src
0x140029ca0  call    memmove
0x140029ca5  mov     eax, [rsi+8]
0x140029ca8  mov     [rbx+38h], rax
0x140029cac  test    r12, r12
0x140029caf  jnz     short loc_140029CB5
0x140029cb1  movsxd  r12, dword ptr [rsi+8]
0x140029cb5  mov     [rbx+38h], r12
0x140029cb9  mov     eax, [rsi+2Ch]
0x140029cbc  mov     [rbx+6Ch], eax
0x140029cbf  mov     eax, [rsp+68h+arg_20]
0x140029cc6  or      eax, [rsi+28h]
0x140029cc9  mov     [rbx+68h], eax
0x140029ccc  mov     rax, [rsp+68h+arg_0]
0x140029cd1  mov     [rbx+30h], rax
0x140029cd5  mov     eax, [rsi+0Ch]
0x140029cd8  mov     [rbx+40h], eax
0x140029cdb  mov     eax, [rsi+14h]
0x140029cde  mov     [rbx+48h], eax
0x140029ce1  test    eax, eax
0x140029ce3  jz      short loc_140029D22
0x140029ce5  cmp     r14d, edi
0x140029ce8  mov     edx, eax
0x140029cea  mov     r8d, 43627250h
0x140029cf0  cmovnz  r15, rbp
0x140029cf4  mov     rcx, r15
0x140029cf7  call    cs:__imp_ExAllocatePool2
0x140029cfe  nop     dword ptr [rax+rax+00h]
0x140029d03  mov     [rbx+50h], rax
0x140029d07  test    rax, rax
0x140029d0a  jz      loc_140029AFB
0x140029d10  mov     edx, [rsi+10h]
0x140029d13  mov     rcx, rax; void *
0x140029d16  mov     r8d, [rbx+48h]; Size
0x140029d1a  add     rdx, rsi; Src
0x140029d1d  call    memmove
0x140029d22  mov     rcx, cs:?Pku2uNonPagedList@@3PEAXEA; void * Pku2uNonPagedList
0x140029d29  cmp     r14d, edi
0x140029d2c  mov     rax, qword ptr cs:xmmword_140019060+8
0x140029d33  mov     rdx, rbx
0x140029d36  cmovz   rcx, cs:?Pku2uPagedList@@3PEAXEA; void * Pku2uPagedList
0x140029d3e  mov     [rbx+8], r13
0x140029d42  mov     [rbx], r13
0x140029d45  mov     [rbx+10h], edi
0x140029d48  mov     dword ptr [rbx+14h], 4252454Bh
0x140029d4f  mov     [rbx+18h], r13
0x140029d53  mov     [rbx+20h], r13
0x140029d57  call    _guard_dispatch_icall
0x140029d5c  mov     rax, [rsp+68h+arg_10]
0x140029d64  mov     edi, r13d
0x140029d67  mov     [rax], rbx
0x140029d6a  mov     rbx, r13
0x140029d6d  test    rbx, rbx
0x140029d70  jz      short loc_140029D7A
0x140029d72  mov     rcx, rbx; P
0x140029d75  call    Pku2uFreeContext
0x140029d7a  mov     eax, edi
0x140029d7c  add     rsp, 28h
0x140029d80  pop     r15
0x140029d82  pop     r14
0x140029d84  pop     r13
0x140029d86  pop     r12
0x140029d88  pop     rdi
0x140029d89  pop     rsi
0x140029d8a  pop     rbp
0x140029d8b  pop     rbx
0x140029d8c  retn
```
