# CreateNewEventEntry

- ea: `0x18002f7a0`
- end: `0x18002f9a2`
- name: `CreateNewEventEntry`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002fda0`

## callees

- `0x18002f700`
- `0x18002f7a0`
- `0x18003098c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f843`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f843`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f82f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f82f`

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
0x18002f7a0  mov     [rsp+arg_8], rbx
0x18002f7a5  mov     [rsp+arg_18], r9b
0x18002f7aa  mov     [rsp+arg_0], rcx
0x18002f7af  push    rbp
0x18002f7b0  push    rsi
0x18002f7b1  push    rdi
0x18002f7b2  push    r12
0x18002f7b4  push    r13
0x18002f7b6  push    r14
0x18002f7b8  push    r15
0x18002f7ba  sub     rsp, 30h
0x18002f7be  mov     r14, [rsp+68h+arg_28]
0x18002f7c6  xor     edx, edx
0x18002f7c8  xor     r11d, r11d
0x18002f7cb  mov     dil, r9b
0x18002f7ce  mov     r15, r8
0x18002f7d1  xor     r10b, r10b
0x18002f7d4  mov     r13b, 2
0x18002f7d7  mov     [r14], rdx
0x18002f7da  movzx   eax, r10b
0x18002f7de  add     rax, rax
0x18002f7e1  cmp     r10b, r13b
0x18002f7e4  mov     ecx, [r8+rax*8+8]
0x18002f7e9  lea     rax, [rcx+rdx]
0x18002f7ed  cmovnb  rdx, rax
0x18002f7f1  lea     rax, [rcx+r11]
0x18002f7f5  cmovnb  rax, r11
0x18002f7f9  inc     r10b
0x18002f7fc  mov     r11, rax
0x18002f7ff  cmp     r10b, 6
0x18002f803  jb      short loc_18002F7DA
0x18002f805  add     rax, rdx
0x18002f808  cmp     rax, 0FFFFh
0x18002f80e  jbe     short loc_18002F81A
0x18002f810  mov     eax, 216h
0x18002f815  jmp     loc_18002F98C
0x18002f81a  lea     rbx, [rdx+8Eh]
0x18002f821  mov     esi, 8
0x18002f826  test    rbx, rbx
0x18002f829  jz      loc_18002F98A
0x18002f82f  call    cs:__imp_GetProcessHeap
0x18002f836  nop     dword ptr [rax+rax+00h]
0x18002f83b  mov     r8, rbx; dwBytes
0x18002f83e  mov     edx, esi; dwFlags
0x18002f840  mov     rcx, rax; hHeap
0x18002f843  call    cs:__imp_HeapAlloc
0x18002f84a  nop     dword ptr [rax+rax+00h]
0x18002f84f  mov     [rsp+68h+var_48], rax
0x18002f854  test    rax, rax
0x18002f857  jz      loc_18002F98A
0x18002f85d  lea     edx, [rsi+58h]
0x18002f860  mov     [rsp+68h+var_40], rbx
0x18002f865  lea     rcx, [rsp+68h+var_48]
0x18002f86a  call    CBufferGetNextOffset
0x18002f86f  xor     sil, sil
0x18002f872  mov     bpl, dil
0x18002f875  add     bpl, r13b
0x18002f878  mov     r12, rax
0x18002f87b  mov     r13b, bpl
0x18002f87e  jz      short loc_18002F8F0
0x18002f880  xor     r14d, r14d
0x18002f883  mov     rdi, r14
0x18002f886  add     rdi, rdi
0x18002f889  cmp     sil, 2
0x18002f88d  jnb     short loc_18002F89C
0x18002f88f  movups  xmm0, xmmword ptr [r15+rdi*8]
0x18002f894  movdqu  xmmword ptr [r12+rdi*8], xmm0
0x18002f89a  jmp     short loc_18002F8D5
0x18002f89c  mov     edx, [r15+rdi*8+8]
0x18002f8a1  lea     rcx, [rsp+68h+var_48]
0x18002f8a6  call    CBufferGetNextOffset
0x18002f8ab  mov     r8d, edx; Size
0x18002f8ae  mov     rcx, rax; void *
0x18002f8b1  mov     rdx, [r15+rdi*8]; Src
0x18002f8b5  mov     rbx, rax
0x18002f8b8  call    memcpy_0
0x18002f8bd  mov     [r12+rdi*8], rbx
0x18002f8c1  mov     eax, [r15+rdi*8+0Ch]
0x18002f8c6  mov     [r12+rdi*8+0Ch], eax
0x18002f8cb  mov     eax, [r15+rdi*8+8]
0x18002f8d0  mov     [r12+rdi*8+8], eax
0x18002f8d5  inc     sil
0x18002f8d8  inc     r14
0x18002f8db  cmp     sil, bpl
0x18002f8de  jb      short loc_18002F883
0x18002f8e0  mov     r14, [rsp+68h+arg_28]
0x18002f8e8  mov     dil, [rsp+68h+arg_18]
0x18002f8f0  mov     edx, 2Eh ; '.'
0x18002f8f5  lea     rcx, [rsp+68h+var_48]
0x18002f8fa  call    CBufferGetNextOffset
0x18002f8ff  mov     rsi, rax
0x18002f902  mov     [rax+10h], r12
0x18002f906  mov     rax, [rsp+68h+arg_0]
0x18002f90b  movups  xmm0, xmmword ptr [rax]
0x18002f90e  mov     eax, [rsp+68h+arg_20]
0x18002f915  mov     byte ptr [rsi+2Ch], 6
0x18002f919  mov     [rsi+2Dh], dil
0x18002f91d  mov     [rsi+28h], eax
0x18002f920  movdqu  xmmword ptr [rsi], xmm0
0x18002f924  cmp     bpl, 6
0x18002f928  jnb     short loc_18002F983
0x18002f92a  movzx   ebp, bpl
0x18002f92e  mov     rdi, rbp
0x18002f931  lea     rcx, [rsp+68h+var_48]
0x18002f936  add     rdi, rdi
0x18002f939  mov     edx, [r15+rdi*8+8]
0x18002f93e  call    CBufferGetNextOffset
0x18002f943  mov     r8d, edx; Size
0x18002f946  mov     rcx, rax; void *
0x18002f949  mov     rdx, [r15+rdi*8]; Src
0x18002f94d  mov     rbx, rax
0x18002f950  call    memcpy_0
0x18002f955  mov     rax, [rsi+10h]
0x18002f959  inc     r13b
0x18002f95c  inc     rbp
0x18002f95f  mov     [rax+rdi*8], rbx
0x18002f963  mov     rcx, [rsi+10h]
0x18002f967  mov     eax, [r15+rdi*8+0Ch]
0x18002f96c  mov     [rcx+rdi*8+0Ch], eax
0x18002f970  mov     rcx, [rsi+10h]
0x18002f974  mov     eax, [r15+rdi*8+8]
0x18002f979  mov     [rcx+rdi*8+8], eax
0x18002f97d  cmp     r13b, 6
0x18002f981  jb      short loc_18002F92E
0x18002f983  mov     [r14], rsi
0x18002f986  xor     eax, eax
0x18002f988  jmp     short loc_18002F98C
0x18002f98a  mov     eax, esi
0x18002f98c  mov     rbx, [rsp+68h+arg_8]
0x18002f991  add     rsp, 30h
0x18002f995  pop     r15
0x18002f997  pop     r14
0x18002f999  pop     r13
0x18002f99b  pop     r12
0x18002f99d  pop     rdi
0x18002f99e  pop     rsi
0x18002f99f  pop     rbp
0x18002f9a0  retn
```
