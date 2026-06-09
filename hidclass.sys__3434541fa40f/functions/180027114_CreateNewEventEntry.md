# CreateNewEventEntry

- ea: `0x180027114`
- end: `0x180027335`
- name: `CreateNewEventEntry`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027588`

## callees

- `0x1800270e0`
- `0x180027114`
- `0x180027d00`
- `0x180028000`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800271ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800271ba`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(char a1, __int128 *a2, __int64 a3, __int64 a4, char a5, int a6, __int64 *a7)
{
  __int64 v7; // rbp
  __int64 v9; // r11
  __int64 v11; // r8
  unsigned __int8 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rax
  SIZE_T v16; // rdi
  PVOID PoolWithTag; // rax
  PVOID v18; // rbx
  __int64 NextOffset; // r12
  unsigned __int8 v20; // r14
  unsigned __int8 v21; // si
  unsigned int v22; // edx
  void *v23; // rbx
  __int64 v24; // rsi
  unsigned __int8 v25; // r12
  __int128 v26; // xmm0
  __int64 v27; // rbp
  __int64 v28; // rdi
  unsigned int v29; // edx
  void *v30; // rbx
  _QWORD v31[9]; // [rsp+20h] [rbp-48h] BYREF

  v7 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  *a7 = 0;
  do
  {
    v13 = *(unsigned int *)(a4 + 16LL * v12 + 8);
    if ( v12 >= 2u )
      v11 += v13;
    v14 = v13 + v9;
    if ( v12 >= 2u )
      v14 = v9;
    ++v12;
    v9 = v14;
  }
  while ( v12 < 7u );
  if ( (unsigned __int64)(v11 + v14) > 0xFFFF )
    return 3221225621LL;
  v16 = v11 + 158;
  if ( v11 == -158 )
    return 3221225495LL;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : NonPagedPoolNx), v16, 0x47417254u);
  v18 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225495LL;
  memset(PoolWithTag, 0, v16);
  v31[0] = v18;
  v31[1] = v16;
  NextOffset = CBufferGetNextOffset(v31, 112);
  v20 = a5 + 2;
  v21 = 0;
  if ( a5 != -2 )
  {
    do
    {
      if ( v21 >= 2u )
      {
        v23 = (void *)CBufferGetNextOffset(v31, *(unsigned int *)(a4 + 16 * v7 + 8));
        memmove(v23, *(const void **)(a4 + 16 * v7), v22);
        *(_QWORD *)(NextOffset + 16 * v7) = v23;
        *(_DWORD *)(NextOffset + 16 * v7 + 12) = *(_DWORD *)(a4 + 16 * v7 + 12);
        *(_DWORD *)(NextOffset + 16 * v7 + 8) = *(_DWORD *)(a4 + 16 * v7 + 8);
      }
      else
      {
        *(_OWORD *)(NextOffset + 16 * v7) = *(_OWORD *)(a4 + 16 * v7);
      }
      ++v21;
      ++v7;
    }
    while ( v21 < v20 );
  }
  v24 = CBufferGetNextOffset(v31, 46);
  *(_QWORD *)(v24 + 16) = NextOffset;
  v25 = a5 + 2;
  v26 = *a2;
  *(_BYTE *)(v24 + 44) = 7;
  *(_BYTE *)(v24 + 45) = a5;
  *(_DWORD *)(v24 + 40) = a6;
  *(_OWORD *)v24 = v26;
  if ( (unsigned __int8)(a5 + 2) < 7u )
  {
    v27 = v20;
    do
    {
      v28 = 2 * v27;
      v30 = (void *)CBufferGetNextOffset(v31, *(unsigned int *)(a4 + 16 * v27 + 8));
      memmove(v30, *(const void **)(a4 + 16 * v27), v29);
      ++v25;
      ++v27;
      *(_QWORD *)(*(_QWORD *)(v24 + 16) + 8 * v28) = v30;
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 8 * v28 + 12) = *(_DWORD *)(a4 + 8 * v28 + 12);
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 8 * v28 + 8) = *(_DWORD *)(a4 + 8 * v28 + 8);
    }
    while ( v25 < 7u );
  }
  *a7 = v24;
  return 0;
}

```

## disassembly

```asm
0x180027114  mov     [rsp+arg_0], rbx
0x180027119  mov     byte ptr [rsp+arg_10], r8b
0x18002711e  mov     [rsp+arg_8], rdx
0x180027123  push    rbp
0x180027124  push    rsi
0x180027125  push    rdi
0x180027126  push    r12
0x180027128  push    r13
0x18002712a  push    r14
0x18002712c  push    r15
0x18002712e  sub     rsp, 30h
0x180027132  mov     r13, [rsp+68h+arg_30]
0x18002713a  xor     ebp, ebp
0x18002713c  mov     r15, r9
0x18002713f  mov     r11d, ebp
0x180027142  mov     r9b, cl
0x180027145  mov     r8d, ebp
0x180027148  mov     r10b, bpl
0x18002714b  mov     [r13+0], rbp
0x18002714f  movzx   eax, r10b
0x180027153  add     rax, rax
0x180027156  cmp     r10b, 2
0x18002715a  mov     ecx, [r15+rax*8+8]
0x18002715f  lea     rax, [rcx+r8]
0x180027163  cmovnb  r8, rax
0x180027167  lea     rax, [rcx+r11]
0x18002716b  cmovnb  rax, r11
0x18002716f  inc     r10b
0x180027172  mov     r11, rax
0x180027175  cmp     r10b, 7
0x180027179  jb      short loc_18002714F
0x18002717b  add     rax, r8
0x18002717e  cmp     rax, 0FFFFh
0x180027184  jbe     short loc_180027190
0x180027186  mov     eax, 0C0000095h
0x18002718b  jmp     loc_18002731F
0x180027190  lea     rdi, [r8+9Eh]
0x180027197  test    rdi, rdi
0x18002719a  jz      loc_18002731A
0x1800271a0  neg     r9b
0x1800271a3  mov     r8d, 47417254h; Tag
0x1800271a9  mov     rdx, rdi; NumberOfBytes
0x1800271ac  sbb     ecx, ecx
0x1800271ae  and     ecx, 0FFFFFE01h
0x1800271b4  add     ecx, 200h; PoolType
0x1800271ba  call    cs:__imp_ExAllocatePoolWithTag
0x1800271c1  nop     dword ptr [rax+rax+00h]
0x1800271c6  mov     rbx, rax
0x1800271c9  test    rax, rax
0x1800271cc  jz      loc_18002731A
0x1800271d2  mov     r8, rdi; Size
0x1800271d5  xor     edx, edx; Val
0x1800271d7  mov     rcx, rax; void *
0x1800271da  call    memset
0x1800271df  mov     edx, 70h ; 'p'
0x1800271e4  mov     [rsp+68h+var_48], rbx
0x1800271e9  lea     rcx, [rsp+68h+var_48]
0x1800271ee  mov     [rsp+68h+var_40], rdi
0x1800271f3  call    CBufferGetNextOffset
0x1800271f8  mov     r14b, [rsp+68h+arg_20]
0x180027200  mov     r12, rax
0x180027203  add     r14b, 2
0x180027207  mov     sil, bpl
0x18002720a  mov     byte ptr [rsp+68h+arg_10], r14b
0x180027212  jz      short loc_180027271
0x180027214  mov     rdi, rbp
0x180027217  add     rdi, rdi
0x18002721a  cmp     sil, 2
0x18002721e  jnb     short loc_18002722D
0x180027220  movups  xmm0, xmmword ptr [r15+rdi*8]
0x180027225  movdqu  xmmword ptr [r12+rdi*8], xmm0
0x18002722b  jmp     short loc_180027266
0x18002722d  mov     edx, [r15+rdi*8+8]
0x180027232  lea     rcx, [rsp+68h+var_48]
0x180027237  call    CBufferGetNextOffset
0x18002723c  mov     r8d, edx; Size
0x18002723f  mov     rcx, rax; void *
0x180027242  mov     rdx, [r15+rdi*8]; Src
0x180027246  mov     rbx, rax
0x180027249  call    memmove
0x18002724e  mov     [r12+rdi*8], rbx
0x180027252  mov     eax, [r15+rdi*8+0Ch]
0x180027257  mov     [r12+rdi*8+0Ch], eax
0x18002725c  mov     eax, [r15+rdi*8+8]
0x180027261  mov     [r12+rdi*8+8], eax
0x180027266  inc     sil
0x180027269  inc     rbp
0x18002726c  cmp     sil, r14b
0x18002726f  jb      short loc_180027214
0x180027271  mov     edx, 2Eh ; '.'
0x180027276  lea     rcx, [rsp+68h+var_48]
0x18002727b  call    CBufferGetNextOffset
0x180027280  mov     ecx, [rsp+68h+arg_28]
0x180027287  mov     rsi, rax
0x18002728a  mov     [rax+10h], r12
0x18002728e  mov     rax, [rsp+68h+arg_8]
0x180027293  mov     r12d, [rsp+68h+arg_10]
0x18002729b  movups  xmm0, xmmword ptr [rax]
0x18002729e  mov     al, [rsp+68h+arg_20]
0x1800272a5  mov     byte ptr [rsi+2Ch], 7
0x1800272a9  mov     [rsi+2Dh], al
0x1800272ac  mov     [rsi+28h], ecx
0x1800272af  movdqu  xmmword ptr [rsi], xmm0
0x1800272b3  cmp     r12b, 7
0x1800272b7  jnb     short loc_180027312
0x1800272b9  movzx   ebp, r14b
0x1800272bd  mov     rdi, rbp
0x1800272c0  lea     rcx, [rsp+68h+var_48]
0x1800272c5  add     rdi, rdi
0x1800272c8  mov     edx, [r15+rdi*8+8]
0x1800272cd  call    CBufferGetNextOffset
0x1800272d2  mov     r8d, edx; Size
0x1800272d5  mov     rcx, rax; void *
0x1800272d8  mov     rdx, [r15+rdi*8]; Src
0x1800272dc  mov     rbx, rax
0x1800272df  call    memmove
0x1800272e4  mov     rcx, [rsi+10h]
0x1800272e8  inc     r12b
0x1800272eb  inc     rbp
0x1800272ee  mov     [rcx+rdi*8], rbx
0x1800272f2  mov     rcx, [rsi+10h]
0x1800272f6  mov     eax, [r15+rdi*8+0Ch]
0x1800272fb  mov     [rcx+rdi*8+0Ch], eax
0x1800272ff  mov     rcx, [rsi+10h]
0x180027303  mov     eax, [r15+rdi*8+8]
0x180027308  mov     [rcx+rdi*8+8], eax
0x18002730c  cmp     r12b, 7
0x180027310  jb      short loc_1800272BD
0x180027312  mov     [r13+0], rsi
0x180027316  xor     eax, eax
0x180027318  jmp     short loc_18002731F
0x18002731a  mov     eax, 0C0000017h
0x18002731f  mov     rbx, [rsp+68h+arg_0]
0x180027324  add     rsp, 30h
0x180027328  pop     r15
0x18002732a  pop     r14
0x18002732c  pop     r13
0x18002732e  pop     r12
0x180027330  pop     rdi
0x180027331  pop     rsi
0x180027332  pop     rbp
0x180027333  retn
```
