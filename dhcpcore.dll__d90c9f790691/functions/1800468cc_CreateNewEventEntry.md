# CreateNewEventEntry

- ea: `0x1800468cc`
- end: `0x180046ac1`
- name: `CreateNewEventEntry`
- size: `501`
- prototype: `__int64 __fastcall(__int128 *, __int64, __int64, char, int, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046e70`

## callees

- `0x18004683c`
- `0x1800468cc`
- `0x180047e3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046969`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046969`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004695b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004695b`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, __int64 a2, __int64 a3, char a4, int a5, __int64 *a6)
{
  __int64 *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r11
  char v9; // di
  unsigned __int8 v11; // r10
  __int64 v12; // rcx
  __int64 v13; // rax
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int8 v17; // si
  __int64 v18; // rbp
  __int64 NextOffset; // r12
  unsigned __int8 v20; // r13
  __int64 v21; // r14
  unsigned int v22; // edx
  void *v23; // rbx
  __int64 v24; // rsi
  __int128 v25; // xmm0
  __int64 v26; // rdi
  unsigned int v27; // edx
  void *v28; // rbx
  _QWORD v29[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = a6;
  v7 = 0;
  v8 = 0;
  v9 = a4;
  v11 = 0;
  *a6 = 0;
  do
  {
    v12 = *(unsigned int *)(a3 + 16LL * v11 + 8);
    if ( v11 >= 2u )
      v7 += v12;
    v13 = v12 + v8;
    if ( v11 >= 2u )
      v13 = v8;
    ++v11;
    v8 = v13;
  }
  while ( v11 < 6u );
  if ( (unsigned __int64)(v7 + v13) > 0xFFFF )
    return 534;
  v15 = v7 + 142;
  if ( v7 == -142 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v29[0] = HeapAlloc(ProcessHeap, 8u, v15);
  if ( !v29[0] )
    return 8;
  v29[1] = v15;
  v17 = 0;
  LOBYTE(v18) = v9 + 2;
  NextOffset = CBufferGetNextOffset(v29, 96);
  v20 = v9 + 2;
  if ( v9 != -2 )
  {
    v21 = 0;
    do
    {
      if ( v17 >= 2u )
      {
        v23 = (void *)CBufferGetNextOffset(v29, *(unsigned int *)(a3 + 16 * v21 + 8));
        memcpy_0(v23, *(const void **)(a3 + 16 * v21), v22);
        *(_QWORD *)(NextOffset + 16 * v21) = v23;
        *(_DWORD *)(NextOffset + 16 * v21 + 12) = *(_DWORD *)(a3 + 16 * v21 + 12);
        *(_DWORD *)(NextOffset + 16 * v21 + 8) = *(_DWORD *)(a3 + 16 * v21 + 8);
      }
      else
      {
        *(_OWORD *)(NextOffset + 16 * v21) = *(_OWORD *)(a3 + 16 * v21);
      }
      ++v17;
      ++v21;
    }
    while ( v17 < (unsigned __int8)v18 );
    v6 = a6;
    v9 = a4;
  }
  v24 = CBufferGetNextOffset(v29, 46);
  *(_QWORD *)(v24 + 16) = NextOffset;
  v25 = *a1;
  *(_BYTE *)(v24 + 44) = 6;
  *(_BYTE *)(v24 + 45) = v9;
  *(_DWORD *)(v24 + 40) = a5;
  *(_OWORD *)v24 = v25;
  if ( (unsigned __int8)v18 < 6u )
  {
    v18 = (unsigned __int8)v18;
    do
    {
      v26 = 2 * v18;
      v28 = (void *)CBufferGetNextOffset(v29, *(unsigned int *)(a3 + 16 * v18 + 8));
      memcpy_0(v28, *(const void **)(a3 + 16 * v18), v27);
      ++v20;
      ++v18;
      *(_QWORD *)(*(_QWORD *)(v24 + 16) + 8 * v26) = v28;
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 8 * v26 + 12) = *(_DWORD *)(a3 + 8 * v26 + 12);
      *(_DWORD *)(*(_QWORD *)(v24 + 16) + 8 * v26 + 8) = *(_DWORD *)(a3 + 8 * v26 + 8);
    }
    while ( v20 < 6u );
  }
  *v6 = v24;
  return 0;
}

```

## disassembly

```asm
0x1800468cc  mov     [rsp+arg_8], rbx
0x1800468d1  mov     [rsp+arg_18], r9b
0x1800468d6  mov     [rsp+arg_0], rcx
0x1800468db  push    rbp
0x1800468dc  push    rsi
0x1800468dd  push    rdi
0x1800468de  push    r12
0x1800468e0  push    r13
0x1800468e2  push    r14
0x1800468e4  push    r15
0x1800468e6  sub     rsp, 30h
0x1800468ea  mov     r14, [rsp+68h+arg_28]
0x1800468f2  xor     edx, edx
0x1800468f4  xor     r11d, r11d
0x1800468f7  mov     dil, r9b
0x1800468fa  mov     r15, r8
0x1800468fd  xor     r10b, r10b
0x180046900  mov     r13b, 2
0x180046903  mov     [r14], rdx
0x180046906  movzx   eax, r10b
0x18004690a  add     rax, rax
0x18004690d  cmp     r10b, r13b
0x180046910  mov     ecx, [r8+rax*8+8]
0x180046915  lea     rax, [rcx+rdx]
0x180046919  cmovnb  rdx, rax
0x18004691d  lea     rax, [rcx+r11]
0x180046921  cmovnb  rax, r11
0x180046925  inc     r10b
0x180046928  mov     r11, rax
0x18004692b  cmp     r10b, 6
0x18004692f  jb      short loc_180046906
0x180046931  add     rax, rdx
0x180046934  cmp     rax, 0FFFFh
0x18004693a  jbe     short loc_180046946
0x18004693c  mov     eax, 216h
0x180046941  jmp     loc_180046AAC
0x180046946  lea     rbx, [rdx+8Eh]
0x18004694d  mov     esi, 8
0x180046952  test    rbx, rbx
0x180046955  jz      loc_180046AAA
0x18004695b  call    cs:__imp_GetProcessHeap
0x180046961  mov     r8, rbx; dwBytes
0x180046964  mov     edx, esi; dwFlags
0x180046966  mov     rcx, rax; hHeap
0x180046969  call    cs:__imp_HeapAlloc
0x18004696f  mov     [rsp+68h+var_48], rax
0x180046974  test    rax, rax
0x180046977  jz      loc_180046AAA
0x18004697d  lea     edx, [rsi+58h]
0x180046980  mov     [rsp+68h+var_40], rbx
0x180046985  lea     rcx, [rsp+68h+var_48]
0x18004698a  call    CBufferGetNextOffset
0x18004698f  xor     sil, sil
0x180046992  mov     bpl, dil
0x180046995  add     bpl, r13b
0x180046998  mov     r12, rax
0x18004699b  mov     r13b, bpl
0x18004699e  jz      short loc_180046A10
0x1800469a0  xor     r14d, r14d
0x1800469a3  mov     rdi, r14
0x1800469a6  add     rdi, rdi
0x1800469a9  cmp     sil, 2
0x1800469ad  jnb     short loc_1800469BC
0x1800469af  movups  xmm0, xmmword ptr [r15+rdi*8]
0x1800469b4  movdqu  xmmword ptr [r12+rdi*8], xmm0
0x1800469ba  jmp     short loc_1800469F5
0x1800469bc  mov     edx, [r15+rdi*8+8]
0x1800469c1  lea     rcx, [rsp+68h+var_48]
0x1800469c6  call    CBufferGetNextOffset
0x1800469cb  mov     r8d, edx; Size
0x1800469ce  mov     rcx, rax; void *
0x1800469d1  mov     rdx, [r15+rdi*8]; Src
0x1800469d5  mov     rbx, rax
0x1800469d8  call    memcpy_0
0x1800469dd  mov     [r12+rdi*8], rbx
0x1800469e1  mov     eax, [r15+rdi*8+0Ch]
0x1800469e6  mov     [r12+rdi*8+0Ch], eax
0x1800469eb  mov     eax, [r15+rdi*8+8]
0x1800469f0  mov     [r12+rdi*8+8], eax
0x1800469f5  inc     sil
0x1800469f8  inc     r14
0x1800469fb  cmp     sil, bpl
0x1800469fe  jb      short loc_1800469A3
0x180046a00  mov     r14, [rsp+68h+arg_28]
0x180046a08  mov     dil, [rsp+68h+arg_18]
0x180046a10  mov     edx, 2Eh ; '.'
0x180046a15  lea     rcx, [rsp+68h+var_48]
0x180046a1a  call    CBufferGetNextOffset
0x180046a1f  mov     rsi, rax
0x180046a22  mov     [rax+10h], r12
0x180046a26  mov     rax, [rsp+68h+arg_0]
0x180046a2b  movups  xmm0, xmmword ptr [rax]
0x180046a2e  mov     eax, [rsp+68h+arg_20]
0x180046a35  mov     byte ptr [rsi+2Ch], 6
0x180046a39  mov     [rsi+2Dh], dil
0x180046a3d  mov     [rsi+28h], eax
0x180046a40  movdqu  xmmword ptr [rsi], xmm0
0x180046a44  cmp     bpl, 6
0x180046a48  jnb     short loc_180046AA3
0x180046a4a  movzx   ebp, bpl
0x180046a4e  mov     rdi, rbp
0x180046a51  lea     rcx, [rsp+68h+var_48]
0x180046a56  add     rdi, rdi
0x180046a59  mov     edx, [r15+rdi*8+8]
0x180046a5e  call    CBufferGetNextOffset
0x180046a63  mov     r8d, edx; Size
0x180046a66  mov     rcx, rax; void *
0x180046a69  mov     rdx, [r15+rdi*8]; Src
0x180046a6d  mov     rbx, rax
0x180046a70  call    memcpy_0
0x180046a75  mov     rax, [rsi+10h]
0x180046a79  inc     r13b
0x180046a7c  inc     rbp
0x180046a7f  mov     [rax+rdi*8], rbx
0x180046a83  mov     rcx, [rsi+10h]
0x180046a87  mov     eax, [r15+rdi*8+0Ch]
0x180046a8c  mov     [rcx+rdi*8+0Ch], eax
0x180046a90  mov     rcx, [rsi+10h]
0x180046a94  mov     eax, [r15+rdi*8+8]
0x180046a99  mov     [rcx+rdi*8+8], eax
0x180046a9d  cmp     r13b, 6
0x180046aa1  jb      short loc_180046A4E
0x180046aa3  mov     [r14], rsi
0x180046aa6  xor     eax, eax
0x180046aa8  jmp     short loc_180046AAC
0x180046aaa  mov     eax, esi
0x180046aac  mov     rbx, [rsp+68h+arg_8]
0x180046ab1  add     rsp, 30h
0x180046ab5  pop     r15
0x180046ab7  pop     r14
0x180046ab9  pop     r13
0x180046abb  pop     r12
0x180046abd  pop     rdi
0x180046abe  pop     rsi
0x180046abf  pop     rbp
0x180046ac0  retn
```
