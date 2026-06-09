# FillDirectoryCacheDataBlockV1

- ea: `0x14000bfe0`
- end: `0x14000c400`
- name: `FillDirectoryCacheDataBlockV1`
- size: `1056`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bf20`

## callees

- `0x14000bfe0`
- `0x1400372c0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c264`
- `ntoskrnl!ExAllocatePool2` at `0x14000c2c8`
- `ntoskrnl!ExAllocatePool2` at `0x14000c264`
- `ntoskrnl!ExAllocatePool2` at `0x14000c2c8`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c00c`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c033`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c0d5`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c2f7`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c381`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c00c`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c033`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c0d5`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c2f7`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000c381`

## pseudocode

```c
__int64 __fastcall FillDirectoryCacheDataBlockV1(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  unsigned int v5; // ebp
  CCHAR MostSignificantBit; // al
  __int64 v7; // r14
  CCHAR v8; // al
  __int64 v9; // rbx
  __int64 v10; // r15
  unsigned int *v11; // r15
  unsigned int *v12; // rcx
  unsigned int v13; // ebx
  CCHAR v14; // al
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rbx
  int v19; // eax
  int v20; // eax
  __int16 v21; // cx
  __int16 v22; // cx
  __int64 Pool2; // rax
  __int64 v25; // r13
  __int64 v26; // rax
  unsigned int v27; // ebx
  CCHAR v28; // al
  __int64 v29; // rdx
  unsigned int v30; // ecx
  __int64 v31; // rdx
  _WORD *v32; // rbx
  unsigned int v33; // eax
  CCHAR v34; // al
  unsigned int v35; // eax

  v3 = (unsigned int)(*(char *)(a2 + 68) + 87 + *(_DWORD *)(a2 + 60)) >> 7;
  v5 = v3 + 1;
  MostSignificantBit = RtlFindMostSignificantBit(*(unsigned int *)(a1 + 220));
  if ( MostSignificantBit <= 4 )
    v7 = 0;
  else
    v7 = (unsigned int)(MostSignificantBit - 3) >> 1;
  v8 = RtlFindMostSignificantBit(v3 + *(_DWORD *)(a1 + 220));
  if ( v8 <= 4 )
    v9 = 0;
  else
    v9 = (unsigned int)(v8 - 3) >> 1;
  if ( (unsigned int)v9 >= 8
    || (unsigned int)v7 >= 8
    || v5 + *(_DWORD *)(a1 + 220) >= dbgDirCacheBlockCountLimit
    || v5 > 8 )
  {
    return 3221227780LL;
  }
  v10 = a1 + 8 * v7;
  if ( *(_QWORD *)(v10 + 152) )
  {
    v11 = (unsigned int *)(a1 + 216);
    goto LABEL_11;
  }
  Pool2 = ExAllocatePool2(258, *((unsigned int *)qword_14003EDA8 + v7), 1834181444);
  *(_QWORD *)(v10 + 152) = Pool2;
  if ( !Pool2 )
    return 3221227780LL;
  v11 = (unsigned int *)(a1 + 216);
  *(_DWORD *)(a1 + 216) = 32 << (2 * v7);
LABEL_11:
  if ( (_DWORD)v7 == (_DWORD)v9 )
  {
    v12 = v11;
    goto LABEL_13;
  }
  v25 = a1 + 8 * v9;
  if ( *(_QWORD *)(v25 + 152) )
    goto LABEL_37;
  v26 = ExAllocatePool2(258, *((unsigned int *)qword_14003EDA8 + v9), 1834181444);
  *(_QWORD *)(v25 + 152) = v26;
  if ( !v26 )
    return 3221227780LL;
  *v11 = 32 << (2 * v9);
  do
  {
LABEL_37:
    v27 = *(_DWORD *)(a1 + 220);
    v28 = RtlFindMostSignificantBit(v27);
    if ( v28 <= 4 )
    {
      v29 = 0;
    }
    else
    {
      v29 = (unsigned int)(v28 - 3) >> 1;
      if ( (unsigned int)v29 >= 8 )
        goto LABEL_54;
    }
    _mm_lfence();
    if ( (_DWORD)v29 )
      v30 = v27 - (32 << (2 * v29 - 2));
    else
      v30 = v27;
    v31 = *(_QWORD *)(a1 + 8 * v29 + 152);
    if ( v31 && v27 < *(_DWORD *)(a1 + 216) )
    {
      v32 = (_WORD *)(v31 + (v30 << 7));
      goto LABEL_44;
    }
LABEL_54:
    __int2c();
    v32 = 0;
LABEL_44:
    memset(v32, 0, 0x80u);
    v32[42] |= 8u;
    v33 = *(_DWORD *)(a1 + 220) + 1;
    *(_DWORD *)(a1 + 220) = v33;
    v34 = RtlFindMostSignificantBit(v33);
    if ( v34 <= 4 )
      v35 = 0;
    else
      v35 = (unsigned int)(v34 - 3) >> 1;
  }
  while ( v35 == (_DWORD)v7 );
  v12 = (unsigned int *)(a1 + 216);
LABEL_13:
  v13 = *(_DWORD *)(a1 + 220);
  if ( v13 + v5 > *v12 )
    return 3221227780LL;
  v14 = RtlFindMostSignificantBit(v13);
  if ( v14 > 4 )
  {
    v15 = (unsigned int)(v14 - 3) >> 1;
    if ( (unsigned int)v15 < 8 )
      goto LABEL_16;
    goto LABEL_55;
  }
  v15 = 0;
LABEL_16:
  _mm_lfence();
  v16 = (_DWORD)v15 ? v13 - (32 << (2 * v15 - 2)) : v13;
  v17 = *(_QWORD *)(a1 + 8 * v15 + 152);
  if ( v17 && v13 < *v11 )
  {
    v18 = v17 + (unsigned int)(v16 << 7);
  }
  else
  {
LABEL_55:
    __int2c();
    v18 = 0;
  }
  *(_DWORD *)(a1 + 220) += v5;
  if ( !v18 )
    return 3221227780LL;
  *(_QWORD *)v18 = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(v18 + 8) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(v18 + 16) = *(_QWORD *)(a2 + 24);
  *(_QWORD *)(v18 + 24) = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(v18 + 32) = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(v18 + 40) = *(_QWORD *)(a2 + 48);
  *(_QWORD *)(v18 + 48) = *(_QWORD *)(a2 + 96);
  v19 = *(_DWORD *)(a2 + 56);
  *(_DWORD *)(v18 + 72) = v19;
  *(_QWORD *)(v18 + 56) = -1;
  *(_QWORD *)(v18 + 64) = -1;
  if ( (v19 & 0x400) != 0 )
  {
    *(_DWORD *)(v18 + 80) = *(_DWORD *)(a2 + 64);
    v20 = 0;
  }
  else
  {
    *(_DWORD *)(v18 + 80) = 0;
    v20 = *(_DWORD *)(a2 + 64);
  }
  *(_DWORD *)(v18 + 76) = v20;
  v21 = *(_WORD *)(v18 + 86) & 0xFFF0 | (*(_BYTE *)(a2 + 68) >> 1) & 0xF;
  *(_WORD *)(v18 + 86) = v21;
  v22 = v21 & 0xF;
  *(_WORD *)(v18 + 86) = v22 | (8 * (*(_WORD *)(a2 + 60) & 0xFFFE));
  *(_WORD *)(v18 + 84) = 0;
  if ( v22 )
    memmove((void *)(v18 + 88), (const void *)(a2 + 70), *(char *)(a2 + 68));
  memmove(
    (void *)(v18 + 2 * ((*(_WORD *)(v18 + 86) & 0xF) + 44LL)),
    (const void *)(a2 + 104),
    *(unsigned int *)(a2 + 60));
  return 0;
}

```

## disassembly

```asm
0x14000bfe0  push    rbx
0x14000bfe2  push    rbp
0x14000bfe3  push    rsi
0x14000bfe4  push    rdi
0x14000bfe5  push    r14
0x14000bfe7  sub     rsp, 20h
0x14000bfeb  movsx   r8d, byte ptr [rdx+44h]
0x14000bff0  mov     rsi, rcx
0x14000bff3  mov     ebx, [rdx+3Ch]
0x14000bff6  add     r8d, 57h ; 'W'
0x14000bffa  mov     ecx, [rcx+0DCh]; Set
0x14000c000  add     ebx, r8d
0x14000c003  shr     ebx, 7
0x14000c006  mov     rdi, rdx
0x14000c009  lea     ebp, [rbx+1]
0x14000c00c  call    cs:__imp_RtlFindMostSignificantBit
0x14000c013  nop     dword ptr [rax+rax+00h]
0x14000c018  cmp     al, 4
0x14000c01a  jle     loc_14000C238
0x14000c020  movsx   r14d, al
0x14000c024  sub     r14d, 3
0x14000c028  shr     r14d, 1
0x14000c02b  mov     ecx, [rsi+0DCh]
0x14000c031  add     ecx, ebx; Set
0x14000c033  call    cs:__imp_RtlFindMostSignificantBit
0x14000c03a  nop     dword ptr [rax+rax+00h]
0x14000c03f  cmp     al, 4
0x14000c041  jle     loc_14000C240
0x14000c047  movsx   ebx, al
0x14000c04a  sub     ebx, 3
0x14000c04d  shr     ebx, 1
0x14000c04f  mov     ecx, [rsi+0DCh]
0x14000c055  mov     eax, cs:dbgDirCacheBlockCountLimit
0x14000c05b  add     ecx, ebp
0x14000c05d  mov     [rsp+48h+arg_0], r12
0x14000c062  mov     [rsp+48h+arg_8], r13
0x14000c067  mov     [rsp+48h+arg_10], r15
0x14000c06c  cmp     ebx, 8
0x14000c06f  jnb     loc_14000C3AE
0x14000c075  cmp     r14d, 8
0x14000c079  jnb     loc_14000C3AE
0x14000c07f  cmp     ecx, eax
0x14000c081  jnb     loc_14000C3AE
0x14000c087  cmp     ebp, 8
0x14000c08a  ja      loc_14000C3AE
0x14000c090  lea     r15, [rsi+r14*8]
0x14000c094  mov     r12d, 20h ; ' '
0x14000c09a  cmp     qword ptr [r15+98h], 0
0x14000c0a2  lea     rcx, qword_14003EDA8
0x14000c0a9  jz      loc_14000C255
0x14000c0af  lea     r15, [rsi+0D8h]
0x14000c0b6  cmp     r14d, ebx
0x14000c0b9  jnz     loc_14000C2AC
0x14000c0bf  mov     rcx, r15
0x14000c0c2  mov     ebx, [rsi+0DCh]
0x14000c0c8  lea     eax, [rbx+rbp]
0x14000c0cb  cmp     eax, [rcx]
0x14000c0cd  ja      loc_14000C3AE
0x14000c0d3  mov     ecx, ebx; Set
0x14000c0d5  call    cs:__imp_RtlFindMostSignificantBit
0x14000c0dc  nop     dword ptr [rax+rax+00h]
0x14000c0e1  cmp     al, 4
0x14000c0e3  jle     loc_14000C247
0x14000c0e9  movsx   eax, al
0x14000c0ec  sub     eax, 3
0x14000c0ef  shr     eax, 1
0x14000c0f1  cmp     eax, 8
0x14000c0f4  jnb     loc_14000C3F7
0x14000c0fa  lfence
0x14000c0fd  test    eax, eax
0x14000c0ff  jz      loc_14000C24E
0x14000c105  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x14000c10c  shl     r12d, cl
0x14000c10f  mov     ecx, ebx
0x14000c111  sub     ecx, r12d
0x14000c114  mov     rdx, [rsi+rax*8+98h]
0x14000c11c  test    rdx, rdx
0x14000c11f  jz      loc_14000C3CA
0x14000c125  cmp     ebx, [r15]
0x14000c128  jnb     loc_14000C3D3
0x14000c12e  shl     ecx, 7
0x14000c131  mov     ebx, ecx
0x14000c133  add     rbx, rdx
0x14000c136  add     [rsi+0DCh], ebp
0x14000c13c  test    rbx, rbx
0x14000c13f  jz      loc_14000C3AE
0x14000c145  mov     rax, [rdi+8]
0x14000c149  mov     [rbx], rax
0x14000c14c  mov     rax, [rdi+10h]
0x14000c150  mov     [rbx+8], rax
0x14000c154  mov     rax, [rdi+18h]
0x14000c158  mov     [rbx+10h], rax
0x14000c15c  mov     rax, [rdi+20h]
0x14000c160  mov     [rbx+18h], rax
0x14000c164  mov     rax, [rdi+28h]
0x14000c168  mov     [rbx+20h], rax
0x14000c16c  mov     rax, [rdi+30h]
0x14000c170  mov     [rbx+28h], rax
0x14000c174  mov     rax, [rdi+60h]
0x14000c178  mov     [rbx+30h], rax
0x14000c17c  mov     eax, [rdi+38h]
0x14000c17f  mov     [rbx+48h], eax
0x14000c182  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x14000c18a  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x14000c192  bt      eax, 0Ah
0x14000c196  jb      loc_14000C29F
0x14000c19c  mov     dword ptr [rbx+50h], 0
0x14000c1a3  mov     eax, [rdi+40h]
0x14000c1a6  mov     [rbx+4Ch], eax
0x14000c1a9  mov     edx, 0FFF0h
0x14000c1ae  movzx   eax, byte ptr [rdi+44h]
0x14000c1b2  shr     al, 1
0x14000c1b4  and     al, 0Fh
0x14000c1b6  movzx   ecx, al
0x14000c1b9  movzx   eax, word ptr [rbx+56h]
0x14000c1bd  and     ax, dx
0x14000c1c0  mov     edx, 0FFFEh
0x14000c1c5  or      cx, ax
0x14000c1c8  mov     [rbx+56h], cx
0x14000c1cc  and     cx, 0Fh
0x14000c1d0  movzx   eax, word ptr [rdi+3Ch]
0x14000c1d4  and     ax, dx
0x14000c1d7  shl     ax, 3
0x14000c1db  or      ax, cx
0x14000c1de  mov     [rbx+56h], ax
0x14000c1e2  xor     eax, eax
0x14000c1e4  mov     [rbx+54h], ax
0x14000c1e8  test    cx, cx
0x14000c1eb  jz      short loc_14000C1FF
0x14000c1ed  movsx   r8, byte ptr [rdi+44h]; Size
0x14000c1f2  lea     rdx, [rdi+46h]; Src
0x14000c1f6  lea     rcx, [rbx+58h]; void *
0x14000c1fa  call    memmove
0x14000c1ff  movzx   eax, word ptr [rbx+56h]
0x14000c203  lea     rdx, [rdi+68h]; Src
0x14000c207  mov     r8d, [rdi+3Ch]; Size
0x14000c20b  and     eax, 0Fh
0x14000c20e  lea     rax, [rax+2Ch]
0x14000c212  lea     rcx, [rbx+rax*2]; void *
0x14000c216  call    memmove
0x14000c21b  xor     eax, eax
0x14000c21d  mov     r15, [rsp+48h+arg_10]
0x14000c222  mov     r13, [rsp+48h+arg_8]
0x14000c227  mov     r12, [rsp+48h+arg_0]
0x14000c22c  add     rsp, 20h
0x14000c230  pop     r14
0x14000c232  pop     rdi
0x14000c233  pop     rsi
0x14000c234  pop     rbp
0x14000c235  pop     rbx
0x14000c236  retn
0x14000c238  xor     r14d, r14d
0x14000c23b  jmp     loc_14000C02B
0x14000c240  xor     ebx, ebx
0x14000c242  jmp     loc_14000C04F
0x14000c247  xor     eax, eax
0x14000c249  jmp     loc_14000C0FA
0x14000c24e  mov     ecx, ebx
0x14000c250  jmp     loc_14000C114
0x14000c255  mov     edx, [rcx+r14*4]
0x14000c259  mov     r8d, 6D536344h
0x14000c25f  mov     ecx, 102h
0x14000c264  call    cs:__imp_ExAllocatePool2
0x14000c26b  nop     dword ptr [rax+rax+00h]
0x14000c270  mov     [r15+98h], rax
0x14000c277  test    rax, rax
0x14000c27a  jz      loc_14000C3AE
0x14000c280  lea     ecx, [r14+r14]
0x14000c284  mov     eax, r12d
0x14000c287  shl     eax, cl
0x14000c289  lea     r15, [rsi+0D8h]
0x14000c290  mov     [r15], eax
0x14000c293  lea     rcx, qword_14003EDA8
0x14000c29a  jmp     loc_14000C0B6
0x14000c29f  mov     eax, [rdi+40h]
0x14000c2a2  mov     [rbx+50h], eax
0x14000c2a5  xor     eax, eax
0x14000c2a7  jmp     loc_14000C1A6
0x14000c2ac  lea     r13, [rsi+rbx*8]
0x14000c2b0  cmp     qword ptr [r13+98h], 0
0x14000c2b8  jnz     short loc_14000C2EF
0x14000c2ba  mov     edx, [rcx+rbx*4]
0x14000c2bd  mov     r8d, 6D536344h
0x14000c2c3  mov     ecx, 102h
0x14000c2c8  call    cs:__imp_ExAllocatePool2
0x14000c2cf  nop     dword ptr [rax+rax+00h]
0x14000c2d4  mov     [r13+98h], rax
0x14000c2db  test    rax, rax
0x14000c2de  jz      loc_14000C3AE
0x14000c2e4  lea     ecx, [rbx+rbx]
0x14000c2e7  mov     eax, r12d
0x14000c2ea  shl     eax, cl
0x14000c2ec  mov     [r15], eax
0x14000c2ef  mov     ebx, [rsi+0DCh]
0x14000c2f5  mov     ecx, ebx; Set
0x14000c2f7  call    cs:__imp_RtlFindMostSignificantBit
0x14000c2fe  nop     dword ptr [rax+rax+00h]
0x14000c303  cmp     al, 4
0x14000c305  jle     loc_14000C3BC
0x14000c30b  movsx   edx, al
0x14000c30e  sub     edx, 3
0x14000c311  shr     edx, 1
0x14000c313  cmp     edx, 8
0x14000c316  jnb     loc_14000C3EE
0x14000c31c  lfence
0x14000c31f  test    edx, edx
0x14000c321  jz      loc_14000C3C3
0x14000c327  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000c32e  mov     eax, r12d
0x14000c331  shl     eax, cl
0x14000c333  mov     ecx, ebx
0x14000c335  sub     ecx, eax
0x14000c337  mov     rdx, [rsi+rdx*8+98h]
0x14000c33f  test    rdx, rdx
0x14000c342  jz      loc_14000C3DC
0x14000c348  cmp     ebx, [rsi+0D8h]
0x14000c34e  jnb     loc_14000C3E5
0x14000c354  shl     ecx, 7
0x14000c357  mov     ebx, ecx
0x14000c359  add     rbx, rdx
0x14000c35c  xor     edx, edx; Val
0x14000c35e  mov     r8d, 80h; Size
0x14000c364  mov     rcx, rbx; void *
0x14000c367  call    memset
0x14000c36c  or      word ptr [rbx+54h], 8
0x14000c371  mov     eax, [rsi+0DCh]
0x14000c377  inc     eax
0x14000c379  mov     ecx, eax; Set
0x14000c37b  mov     [rsi+0DCh], eax
0x14000c381  call    cs:__imp_RtlFindMostSignificantBit
0x14000c388  nop     dword ptr [rax+rax+00h]
0x14000c38d  cmp     al, 4
0x14000c38f  jle     short loc_14000C3B8
0x14000c391  movsx   eax, al
0x14000c394  sub     eax, 3
0x14000c397  shr     eax, 1
0x14000c399  cmp     eax, r14d
0x14000c39c  jz      loc_14000C2EF
0x14000c3a2  lea     rcx, [rsi+0D8h]
0x14000c3a9  jmp     loc_14000C0C2
0x14000c3ae  mov     eax, 0C0000904h
0x14000c3b3  jmp     loc_14000C21D
0x14000c3b8  xor     eax, eax
0x14000c3ba  jmp     short loc_14000C399
0x14000c3bc  xor     edx, edx
0x14000c3be  jmp     loc_14000C31C
0x14000c3c3  mov     ecx, ebx
0x14000c3c5  jmp     loc_14000C337
0x14000c3ca  int     2Ch; Windows NT - assertion failure
0x14000c3cc  xor     ebx, ebx
0x14000c3ce  jmp     loc_14000C136
0x14000c3d3  int     2Ch; Windows NT - assertion failure
0x14000c3d5  xor     ebx, ebx
0x14000c3d7  jmp     loc_14000C136
0x14000c3dc  int     2Ch; Windows NT - assertion failure
0x14000c3de  xor     ebx, ebx
0x14000c3e0  jmp     loc_14000C35C
0x14000c3e5  int     2Ch; Windows NT - assertion failure
0x14000c3e7  xor     ebx, ebx
0x14000c3e9  jmp     loc_14000C35C
0x14000c3ee  int     2Ch; Windows NT - assertion failure
0x14000c3f0  xor     ebx, ebx
0x14000c3f2  jmp     loc_14000C35C
0x14000c3f7  int     2Ch; Windows NT - assertion failure
0x14000c3f9  xor     ebx, ebx
0x14000c3fb  jmp     loc_14000C136
```
