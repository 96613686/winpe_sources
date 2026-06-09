# CreateNewEventEntry

- ea: `0x1800176f8`
- end: `0x1800178ea`
- name: `CreateNewEventEntry`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017cb0`

## callees

- `0x1800175d4`
- `0x1800176f8`
- `0x180018928`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017784`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017784`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017792`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017792`

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
  while ( v11 < 5u );
  if ( (unsigned __int64)(v7 + v13) > 0xFFFF )
    return 534;
  v15 = v7 + 126;
  if ( v7 == -126 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v29[0] = HeapAlloc(ProcessHeap, 8u, v15);
  if ( !v29[0] )
    return 8;
  v29[1] = v15;
  v17 = 0;
  LOBYTE(v18) = v9 + 2;
  NextOffset = CBufferGetNextOffset(v29, 80);
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
  *(_BYTE *)(v24 + 44) = 5;
  *(_BYTE *)(v24 + 45) = v9;
  *(_DWORD *)(v24 + 40) = a5;
  *(_OWORD *)v24 = v25;
  if ( (unsigned __int8)v18 < 5u )
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
    while ( v20 < 5u );
  }
  *v6 = v24;
  return 0;
}

```

## disassembly

```asm
0x1800176f8  mov     [rsp+arg_8], rbx
0x1800176fd  mov     [rsp+arg_18], r9b
0x180017702  mov     [rsp+arg_0], rcx
0x180017707  push    rbp
0x180017708  push    rsi
0x180017709  push    rdi
0x18001770a  push    r12
0x18001770c  push    r13
0x18001770e  push    r14
0x180017710  push    r15
0x180017712  sub     rsp, 30h
0x180017716  mov     r14, [rsp+68h+arg_28]
0x18001771e  xor     edx, edx
0x180017720  xor     r11d, r11d
0x180017723  mov     dil, r9b
0x180017726  mov     r15, r8
0x180017729  xor     r10b, r10b
0x18001772c  mov     r13b, 2
0x18001772f  mov     [r14], rdx
0x180017732  movzx   eax, r10b
0x180017736  add     rax, rax
0x180017739  cmp     r10b, r13b
0x18001773c  mov     ecx, [r8+rax*8+8]
0x180017741  lea     rax, [rcx+rdx]
0x180017745  cmovnb  rdx, rax
0x180017749  lea     rax, [rcx+r11]
0x18001774d  cmovnb  rax, r11
0x180017751  inc     r10b
0x180017754  mov     r11, rax
0x180017757  cmp     r10b, 5
0x18001775b  jb      short loc_180017732
0x18001775d  add     rax, rdx
0x180017760  cmp     rax, 0FFFFh
0x180017766  jbe     short loc_180017772
0x180017768  mov     eax, 216h
0x18001776d  jmp     loc_1800178D5
0x180017772  lea     rbx, [rdx+7Eh]
0x180017776  mov     esi, 8
0x18001777b  test    rbx, rbx
0x18001777e  jz      loc_1800178D3
0x180017784  call    cs:__imp_GetProcessHeap
0x18001778a  mov     r8, rbx; dwBytes
0x18001778d  mov     edx, esi; dwFlags
0x18001778f  mov     rcx, rax; hHeap
0x180017792  call    cs:__imp_HeapAlloc
0x180017798  mov     [rsp+68h+var_48], rax
0x18001779d  test    rax, rax
0x1800177a0  jz      loc_1800178D3
0x1800177a6  lea     edx, [rsi+48h]
0x1800177a9  mov     [rsp+68h+var_40], rbx
0x1800177ae  lea     rcx, [rsp+68h+var_48]
0x1800177b3  call    CBufferGetNextOffset
0x1800177b8  xor     sil, sil
0x1800177bb  mov     bpl, dil
0x1800177be  add     bpl, r13b
0x1800177c1  mov     r12, rax
0x1800177c4  mov     r13b, bpl
0x1800177c7  jz      short loc_180017839
0x1800177c9  xor     r14d, r14d
0x1800177cc  mov     rdi, r14
0x1800177cf  add     rdi, rdi
0x1800177d2  cmp     sil, 2
0x1800177d6  jnb     short loc_1800177E5
0x1800177d8  movups  xmm0, xmmword ptr [r15+rdi*8]
0x1800177dd  movdqu  xmmword ptr [r12+rdi*8], xmm0
0x1800177e3  jmp     short loc_18001781E
0x1800177e5  mov     edx, [r15+rdi*8+8]
0x1800177ea  lea     rcx, [rsp+68h+var_48]
0x1800177ef  call    CBufferGetNextOffset
0x1800177f4  mov     r8d, edx; Size
0x1800177f7  mov     rcx, rax; void *
0x1800177fa  mov     rdx, [r15+rdi*8]; Src
0x1800177fe  mov     rbx, rax
0x180017801  call    memcpy_0
0x180017806  mov     [r12+rdi*8], rbx
0x18001780a  mov     eax, [r15+rdi*8+0Ch]
0x18001780f  mov     [r12+rdi*8+0Ch], eax
0x180017814  mov     eax, [r15+rdi*8+8]
0x180017819  mov     [r12+rdi*8+8], eax
0x18001781e  inc     sil
0x180017821  inc     r14
0x180017824  cmp     sil, bpl
0x180017827  jb      short loc_1800177CC
0x180017829  mov     r14, [rsp+68h+arg_28]
0x180017831  mov     dil, [rsp+68h+arg_18]
0x180017839  mov     edx, 2Eh ; '.'
0x18001783e  lea     rcx, [rsp+68h+var_48]
0x180017843  call    CBufferGetNextOffset
0x180017848  mov     rsi, rax
0x18001784b  mov     [rax+10h], r12
0x18001784f  mov     rax, [rsp+68h+arg_0]
0x180017854  movups  xmm0, xmmword ptr [rax]
0x180017857  mov     eax, [rsp+68h+arg_20]
0x18001785e  mov     byte ptr [rsi+2Ch], 5
0x180017862  mov     [rsi+2Dh], dil
0x180017866  mov     [rsi+28h], eax
0x180017869  movdqu  xmmword ptr [rsi], xmm0
0x18001786d  cmp     bpl, 5
0x180017871  jnb     short loc_1800178CC
0x180017873  movzx   ebp, bpl
0x180017877  mov     rdi, rbp
0x18001787a  lea     rcx, [rsp+68h+var_48]
0x18001787f  add     rdi, rdi
0x180017882  mov     edx, [r15+rdi*8+8]
0x180017887  call    CBufferGetNextOffset
0x18001788c  mov     r8d, edx; Size
0x18001788f  mov     rcx, rax; void *
0x180017892  mov     rdx, [r15+rdi*8]; Src
0x180017896  mov     rbx, rax
0x180017899  call    memcpy_0
0x18001789e  mov     rax, [rsi+10h]
0x1800178a2  inc     r13b
0x1800178a5  inc     rbp
0x1800178a8  mov     [rax+rdi*8], rbx
0x1800178ac  mov     rcx, [rsi+10h]
0x1800178b0  mov     eax, [r15+rdi*8+0Ch]
0x1800178b5  mov     [rcx+rdi*8+0Ch], eax
0x1800178b9  mov     rcx, [rsi+10h]
0x1800178bd  mov     eax, [r15+rdi*8+8]
0x1800178c2  mov     [rcx+rdi*8+8], eax
0x1800178c6  cmp     r13b, 5
0x1800178ca  jb      short loc_180017877
0x1800178cc  mov     [r14], rsi
0x1800178cf  xor     eax, eax
0x1800178d1  jmp     short loc_1800178D5
0x1800178d3  mov     eax, esi
0x1800178d5  mov     rbx, [rsp+68h+arg_8]
0x1800178da  add     rsp, 30h
0x1800178de  pop     r15
0x1800178e0  pop     r14
0x1800178e2  pop     r13
0x1800178e4  pop     r12
0x1800178e6  pop     rdi
0x1800178e7  pop     rsi
0x1800178e8  pop     rbp
0x1800178e9  retn
```
