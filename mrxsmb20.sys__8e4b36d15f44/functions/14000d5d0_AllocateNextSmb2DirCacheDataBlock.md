# AllocateNextSmb2DirCacheDataBlock

- ea: `0x14000d5d0`
- end: `0x14000d8e3`
- name: `AllocateNextSmb2DirCacheDataBlock`
- size: `787`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400351d0`

## callees

- `0x14000d5d0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d759`
- `ntoskrnl!ExAllocatePool2` at `0x14000d7a2`
- `ntoskrnl!ExAllocatePool2` at `0x14000d759`
- `ntoskrnl!ExAllocatePool2` at `0x14000d7a2`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d5eb`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d60f`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d6b4`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d7e8`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d872`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d5eb`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d60f`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d6b4`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d7e8`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000d872`

## pseudocode

```c
__int64 __fastcall AllocateNextSmb2DirCacheDataBlock(__int64 a1, int a2)
{
  unsigned int v3; // edi
  unsigned int v4; // ebp
  CCHAR MostSignificantBit; // al
  __int64 v6; // rsi
  CCHAR v7; // al
  __int64 v8; // rdi
  __int64 v9; // r14
  unsigned int *v10; // r14
  unsigned int *v11; // rcx
  unsigned int v12; // edi
  CCHAR v13; // al
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 result; // rax
  __int64 v18; // r12
  __int64 v19; // rax
  __int64 Pool2; // rax
  unsigned int v21; // edi
  CCHAR v22; // al
  __int64 v23; // rdx
  unsigned int v24; // ecx
  __int64 v25; // rdx
  _WORD *v26; // rdi
  unsigned int v27; // eax
  CCHAR v28; // al
  unsigned int v29; // eax

  v3 = (unsigned int)(a2 - 1) >> 7;
  v4 = v3 + 1;
  MostSignificantBit = RtlFindMostSignificantBit(*(unsigned int *)(a1 + 220));
  if ( MostSignificantBit <= 4 )
    v6 = 0;
  else
    v6 = (unsigned int)(MostSignificantBit - 3) >> 1;
  v7 = RtlFindMostSignificantBit(v3 + *(_DWORD *)(a1 + 220));
  if ( v7 <= 4 )
    v8 = 0;
  else
    v8 = (unsigned int)(v7 - 3) >> 1;
  if ( (unsigned int)v8 >= 8
    || (unsigned int)v6 >= 8
    || v4 + *(_DWORD *)(a1 + 220) >= dbgDirCacheBlockCountLimit
    || v4 > 8 )
  {
    return 0;
  }
  v9 = a1 + 8 * v6;
  if ( !*(_QWORD *)(v9 + 152) )
  {
    Pool2 = ExAllocatePool2(258, *((unsigned int *)qword_14003EDA8 + v6), 1834181444);
    *(_QWORD *)(v9 + 152) = Pool2;
    if ( Pool2 )
    {
      v10 = (unsigned int *)(a1 + 216);
      *(_DWORD *)(a1 + 216) = 32 << (2 * v6);
      goto LABEL_11;
    }
    return 0;
  }
  v10 = (unsigned int *)(a1 + 216);
LABEL_11:
  if ( (_DWORD)v6 == (_DWORD)v8 )
  {
    v11 = v10;
    goto LABEL_13;
  }
  v18 = a1 + 8 * v8;
  if ( *(_QWORD *)(v18 + 152) )
    goto LABEL_32;
  v19 = ExAllocatePool2(258, *((unsigned int *)qword_14003EDA8 + v8), 1834181444);
  *(_QWORD *)(v18 + 152) = v19;
  if ( !v19 )
    return 0;
  *v10 = 32 << (2 * v8);
  do
  {
LABEL_32:
    v21 = *(_DWORD *)(a1 + 220);
    v22 = RtlFindMostSignificantBit(v21);
    if ( v22 <= 4 )
    {
      v23 = 0;
    }
    else
    {
      v23 = (unsigned int)(v22 - 3) >> 1;
      if ( (unsigned int)v23 >= 8 )
        goto LABEL_48;
    }
    _mm_lfence();
    if ( (_DWORD)v23 )
      v24 = v21 - (32 << (2 * v23 - 2));
    else
      v24 = v21;
    v25 = *(_QWORD *)(a1 + 8 * v23 + 152);
    if ( v25 && v21 < *(_DWORD *)(a1 + 216) )
    {
      v26 = (_WORD *)(v25 + (v24 << 7));
      goto LABEL_39;
    }
LABEL_48:
    __int2c();
    v26 = 0;
LABEL_39:
    memset(v26, 0, 0x80u);
    v26[42] |= 8u;
    v27 = *(_DWORD *)(a1 + 220) + 1;
    *(_DWORD *)(a1 + 220) = v27;
    v28 = RtlFindMostSignificantBit(v27);
    if ( v28 <= 4 )
      v29 = 0;
    else
      v29 = (unsigned int)(v28 - 3) >> 1;
  }
  while ( v29 == (_DWORD)v6 );
  v11 = (unsigned int *)(a1 + 216);
LABEL_13:
  v12 = *(_DWORD *)(a1 + 220);
  if ( v12 + v4 > *v11 )
    return 0;
  v13 = RtlFindMostSignificantBit(v12);
  if ( v13 > 4 )
  {
    v14 = (unsigned int)(v13 - 3) >> 1;
    if ( (unsigned int)v14 < 8 )
      goto LABEL_16;
    goto LABEL_49;
  }
  v14 = 0;
LABEL_16:
  if ( (_DWORD)v14 )
    v15 = v12 - (32 << (2 * v14 - 2));
  else
    v15 = v12;
  v16 = *(_QWORD *)(a1 + 8 * v14 + 152);
  if ( v16 && v12 < *v10 )
  {
    result = v16 + (v15 << 7);
  }
  else
  {
LABEL_49:
    __int2c();
    result = 0;
  }
  *(_DWORD *)(a1 + 220) += v4;
  return result;
}

```

## disassembly

```asm
0x14000d5d0  push    rbx
0x14000d5d2  push    rbp
0x14000d5d3  push    rsi
0x14000d5d4  push    rdi
0x14000d5d5  sub     rsp, 28h
0x14000d5d9  lea     edi, [rdx-1]
0x14000d5dc  mov     rbx, rcx
0x14000d5df  mov     ecx, [rcx+0DCh]; Set
0x14000d5e5  shr     edi, 7
0x14000d5e8  lea     ebp, [rdi+1]
0x14000d5eb  call    cs:__imp_RtlFindMostSignificantBit
0x14000d5f2  nop     dword ptr [rax+rax+00h]
0x14000d5f7  cmp     al, 4
0x14000d5f9  jle     loc_14000D776
0x14000d5ff  movsx   esi, al
0x14000d602  sub     esi, 3
0x14000d605  shr     esi, 1
0x14000d607  mov     ecx, [rbx+0DCh]
0x14000d60d  add     ecx, edi; Set
0x14000d60f  call    cs:__imp_RtlFindMostSignificantBit
0x14000d616  nop     dword ptr [rax+rax+00h]
0x14000d61b  cmp     al, 4
0x14000d61d  jle     loc_14000D77D
0x14000d623  movsx   edi, al
0x14000d626  sub     edi, 3
0x14000d629  shr     edi, 1
0x14000d62b  mov     ecx, [rbx+0DCh]
0x14000d631  mov     eax, cs:dbgDirCacheBlockCountLimit
0x14000d637  add     ecx, ebp
0x14000d639  mov     [rsp+48h+arg_0], r12
0x14000d63e  mov     [rsp+48h+arg_8], r13
0x14000d643  mov     [rsp+48h+arg_10], r14
0x14000d648  mov     [rsp+48h+var_28], r15
0x14000d64d  cmp     edi, 8
0x14000d650  jnb     loc_14000D772
0x14000d656  cmp     esi, 8
0x14000d659  jnb     loc_14000D772
0x14000d65f  cmp     ecx, eax
0x14000d661  jnb     loc_14000D772
0x14000d667  cmp     ebp, 8
0x14000d66a  ja      loc_14000D772
0x14000d670  lea     r14, [rbx+rsi*8]
0x14000d674  mov     r15d, 20h ; ' '
0x14000d67a  cmp     qword ptr [r14+98h], 0
0x14000d682  lea     r13, qword_14003EDA8
0x14000d689  jz      loc_14000D792
0x14000d68f  lea     r14, [rbx+0D8h]
0x14000d696  cmp     esi, edi
0x14000d698  jnz     loc_14000D736
0x14000d69e  mov     rcx, r14
0x14000d6a1  mov     edi, [rbx+0DCh]
0x14000d6a7  lea     eax, [rdi+rbp]
0x14000d6aa  cmp     eax, [rcx]
0x14000d6ac  ja      loc_14000D772
0x14000d6b2  mov     ecx, edi; Set
0x14000d6b4  call    cs:__imp_RtlFindMostSignificantBit
0x14000d6bb  nop     dword ptr [rax+rax+00h]
0x14000d6c0  cmp     al, 4
0x14000d6c2  jle     loc_14000D784
0x14000d6c8  movsx   eax, al
0x14000d6cb  sub     eax, 3
0x14000d6ce  shr     eax, 1
0x14000d6d0  cmp     eax, 8
0x14000d6d3  jnb     loc_14000D8DA
0x14000d6d9  test    eax, eax
0x14000d6db  jz      loc_14000D78B
0x14000d6e1  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x14000d6e8  shl     r15d, cl
0x14000d6eb  mov     ecx, edi
0x14000d6ed  sub     ecx, r15d
0x14000d6f0  mov     rdx, [rbx+rax*8+98h]
0x14000d6f8  test    rdx, rdx
0x14000d6fb  jz      loc_14000D8B0
0x14000d701  cmp     edi, [r14]
0x14000d704  jnb     loc_14000D8B9
0x14000d70a  shl     ecx, 7
0x14000d70d  mov     eax, ecx
0x14000d70f  add     rax, rdx
0x14000d712  add     [rbx+0DCh], ebp
0x14000d718  mov     r15, [rsp+48h+var_28]
0x14000d71d  mov     r14, [rsp+48h+arg_10]
0x14000d722  mov     r13, [rsp+48h+arg_8]
0x14000d727  mov     r12, [rsp+48h+arg_0]
0x14000d72c  add     rsp, 28h
0x14000d730  pop     rdi
0x14000d731  pop     rsi
0x14000d732  pop     rbp
0x14000d733  pop     rbx
0x14000d734  retn
0x14000d736  lea     r12, [rbx+rdi*8]
0x14000d73a  cmp     qword ptr [r12+98h], 0
0x14000d743  jnz     loc_14000D7E0
0x14000d749  mov     edx, [r13+rdi*4+0]
0x14000d74e  mov     ecx, 102h
0x14000d753  mov     r8d, 6D536344h
0x14000d759  call    cs:__imp_ExAllocatePool2
0x14000d760  nop     dword ptr [rax+rax+00h]
0x14000d765  mov     [r12+98h], rax
0x14000d76d  test    rax, rax
0x14000d770  jnz     short loc_14000D7D1
0x14000d772  xor     eax, eax
0x14000d774  jmp     short loc_14000D718
0x14000d776  xor     esi, esi
0x14000d778  jmp     loc_14000D607
0x14000d77d  xor     edi, edi
0x14000d77f  jmp     loc_14000D62B
0x14000d784  xor     eax, eax
0x14000d786  jmp     loc_14000D6D9
0x14000d78b  mov     ecx, edi
0x14000d78d  jmp     loc_14000D6F0
0x14000d792  mov     edx, [r13+rsi*4+0]
0x14000d797  mov     ecx, 102h
0x14000d79c  mov     r8d, 6D536344h
0x14000d7a2  call    cs:__imp_ExAllocatePool2
0x14000d7a9  nop     dword ptr [rax+rax+00h]
0x14000d7ae  mov     [r14+98h], rax
0x14000d7b5  test    rax, rax
0x14000d7b8  jz      short loc_14000D772
0x14000d7ba  lea     ecx, [rsi+rsi]
0x14000d7bd  mov     eax, r15d
0x14000d7c0  shl     eax, cl
0x14000d7c2  lea     r14, [rbx+0D8h]
0x14000d7c9  mov     [r14], eax
0x14000d7cc  jmp     loc_14000D696
0x14000d7d1  lea     ecx, [rdi+rdi]
0x14000d7d4  mov     eax, r15d
0x14000d7d7  shl     eax, cl
0x14000d7d9  mov     [r14], eax
0x14000d7dc  nop     dword ptr [rax+00h]
0x14000d7e0  mov     edi, [rbx+0DCh]
0x14000d7e6  mov     ecx, edi; Set
0x14000d7e8  call    cs:__imp_RtlFindMostSignificantBit
0x14000d7ef  nop     dword ptr [rax+rax+00h]
0x14000d7f4  cmp     al, 4
0x14000d7f6  jle     loc_14000D89E
0x14000d7fc  movsx   edx, al
0x14000d7ff  sub     edx, 3
0x14000d802  shr     edx, 1
0x14000d804  cmp     edx, 8
0x14000d807  jnb     loc_14000D8D1
0x14000d80d  lfence
0x14000d810  test    edx, edx
0x14000d812  jz      loc_14000D8A9
0x14000d818  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000d81f  mov     eax, r15d
0x14000d822  shl     eax, cl
0x14000d824  mov     ecx, edi
0x14000d826  sub     ecx, eax
0x14000d828  mov     rdx, [rbx+rdx*8+98h]
0x14000d830  test    rdx, rdx
0x14000d833  jz      loc_14000D8C2
0x14000d839  cmp     edi, [rbx+0D8h]
0x14000d83f  jnb     loc_14000D8C8
0x14000d845  shl     ecx, 7
0x14000d848  mov     edi, ecx
0x14000d84a  add     rdi, rdx
0x14000d84d  xor     edx, edx; Val
0x14000d84f  mov     r8d, 80h; Size
0x14000d855  mov     rcx, rdi; void *
0x14000d858  call    memset
0x14000d85d  or      word ptr [rdi+54h], 8
0x14000d862  mov     eax, [rbx+0DCh]
0x14000d868  inc     eax
0x14000d86a  mov     ecx, eax; Set
0x14000d86c  mov     [rbx+0DCh], eax
0x14000d872  call    cs:__imp_RtlFindMostSignificantBit
0x14000d879  nop     dword ptr [rax+rax+00h]
0x14000d87e  cmp     al, 4
0x14000d880  jle     short loc_14000D8A5
0x14000d882  movsx   eax, al
0x14000d885  sub     eax, 3
0x14000d888  shr     eax, 1
0x14000d88a  cmp     eax, esi
0x14000d88c  jz      loc_14000D7E0
0x14000d892  lea     rcx, [rbx+0D8h]
0x14000d899  jmp     loc_14000D6A1
0x14000d89e  xor     edx, edx
0x14000d8a0  jmp     loc_14000D80D
0x14000d8a5  xor     eax, eax
0x14000d8a7  jmp     short loc_14000D88A
0x14000d8a9  mov     ecx, edi
0x14000d8ab  jmp     loc_14000D828
0x14000d8b0  int     2Ch; Windows NT - assertion failure
0x14000d8b2  xor     eax, eax
0x14000d8b4  jmp     loc_14000D712
0x14000d8b9  int     2Ch; Windows NT - assertion failure
0x14000d8bb  xor     eax, eax
0x14000d8bd  jmp     loc_14000D712
0x14000d8c2  int     2Ch; Windows NT - assertion failure
0x14000d8c4  xor     edi, edi
0x14000d8c6  jmp     short loc_14000D84D
0x14000d8c8  int     2Ch; Windows NT - assertion failure
0x14000d8ca  xor     edi, edi
0x14000d8cc  jmp     loc_14000D84D
0x14000d8d1  int     2Ch; Windows NT - assertion failure
0x14000d8d3  xor     edi, edi
0x14000d8d5  jmp     loc_14000D84D
0x14000d8da  int     2Ch; Windows NT - assertion failure
0x14000d8dc  xor     eax, eax
0x14000d8de  jmp     loc_14000D712
```
