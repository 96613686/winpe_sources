# CreateNewEventEntry

- ea: `0x180023c24`
- end: `0x180023e2d`
- name: `CreateNewEventEntry`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024160`

## callees

- `0x180011135`
- `0x180023b94`
- `0x180023c24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ccd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023ccd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023cbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023cbf`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, __int64 *a6)
{
  __int64 v6; // r10
  __int64 v7; // r14
  unsigned __int8 v8; // r11
  __int64 v9; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  SIZE_T v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int8 v17; // si
  __int64 NextOffset; // r13
  bool v19; // zf
  __int64 v20; // rbp
  unsigned __int8 v21; // r15
  __int64 v22; // r15
  unsigned int v23; // edx
  void *v24; // rbx
  __int64 v25; // rsi
  __int128 v26; // xmm0
  __int64 v27; // rdi
  unsigned int v28; // edx
  void *v29; // rbx
  _QWORD v30[9]; // [rsp+20h] [rbp-48h] BYREF

  v6 = 0;
  v7 = a2;
  v8 = 0;
  v9 = 0;
  *a6 = 0;
  if ( (_BYTE)v7 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v8 + 8);
      if ( v8 >= 2u )
        v6 += v12;
      v13 = v12 + v9;
      if ( v8 >= 2u )
        v13 = v9;
      ++v8;
      v9 = v13;
    }
    while ( v8 < (unsigned __int8)v7 );
    if ( (unsigned __int64)(v6 + v13) > 0xFFFF )
      return 534;
  }
  v15 = v6 + 16 * v7 + 46;
  if ( !v15 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v30[0] = HeapAlloc(ProcessHeap, 8u, v15);
  if ( !v30[0] )
    return 8;
  v30[1] = v15;
  v17 = 0;
  NextOffset = CBufferGetNextOffset(v30, 16 * v7);
  v19 = a4 == -2;
  LOBYTE(v20) = a4 + 2;
  v21 = v20;
  if ( !v19 )
  {
    v22 = 0;
    do
    {
      if ( v17 >= 2u )
      {
        v24 = (void *)CBufferGetNextOffset(v30, *(unsigned int *)(a3 + 16 * v22 + 8));
        memcpy_0(v24, *(const void **)(a3 + 16 * v22), v23);
        *(_QWORD *)(NextOffset + 16 * v22) = v24;
        *(_DWORD *)(NextOffset + 16 * v22 + 12) = *(_DWORD *)(a3 + 16 * v22 + 12);
        *(_DWORD *)(NextOffset + 16 * v22 + 8) = *(_DWORD *)(a3 + 16 * v22 + 8);
      }
      else
      {
        *(_OWORD *)(NextOffset + 16 * v22) = *(_OWORD *)(a3 + 16 * v22);
      }
      ++v17;
      ++v22;
    }
    while ( v17 < (unsigned __int8)v20 );
    v21 = v20;
  }
  v25 = CBufferGetNextOffset(v30, 46);
  *(_QWORD *)(v25 + 16) = NextOffset;
  v26 = *a1;
  *(_BYTE *)(v25 + 45) = a4;
  *(_DWORD *)(v25 + 40) = a5;
  *(_BYTE *)(v25 + 44) = v7;
  *(_OWORD *)v25 = v26;
  if ( v21 < (unsigned __int8)v7 )
  {
    v20 = (unsigned __int8)v20;
    do
    {
      v27 = 2 * v20;
      v29 = (void *)CBufferGetNextOffset(v30, *(unsigned int *)(a3 + 16 * v20 + 8));
      memcpy_0(v29, *(const void **)(a3 + 16 * v20), v28);
      ++v21;
      ++v20;
      *(_QWORD *)(*(_QWORD *)(v25 + 16) + 8 * v27) = v29;
      *(_DWORD *)(*(_QWORD *)(v25 + 16) + 8 * v27 + 12) = *(_DWORD *)(a3 + 8 * v27 + 12);
      *(_DWORD *)(*(_QWORD *)(v25 + 16) + 8 * v27 + 8) = *(_DWORD *)(a3 + 8 * v27 + 8);
    }
    while ( v21 < (unsigned __int8)v7 );
  }
  *a6 = v25;
  return 0;
}

```

## disassembly

```asm
0x180023c24  mov     [rsp+arg_10], rbx
0x180023c29  mov     [rsp+arg_18], r9b
0x180023c2e  mov     [rsp+arg_0], rcx
0x180023c33  push    rbp
0x180023c34  push    rsi
0x180023c35  push    rdi
0x180023c36  push    r12
0x180023c38  push    r13
0x180023c3a  push    r14
0x180023c3c  push    r15
0x180023c3e  sub     rsp, 30h
0x180023c42  mov     rax, [rsp+68h+arg_28]
0x180023c4a  xor     r10d, r10d
0x180023c4d  movzx   r14d, dl
0x180023c51  xor     r11b, r11b
0x180023c54  xor     edx, edx
0x180023c56  mov     bpl, r9b
0x180023c59  mov     r12, r8
0x180023c5c  mov     r15b, 2
0x180023c5f  mov     [rax], rdx
0x180023c62  test    r14b, r14b
0x180023c65  jz      short loc_180023CA6
0x180023c67  movzx   eax, r11b
0x180023c6b  add     rax, rax
0x180023c6e  cmp     r11b, r15b
0x180023c71  mov     ecx, [r8+rax*8+8]
0x180023c76  lea     rax, [rcx+r10]
0x180023c7a  cmovnb  r10, rax
0x180023c7e  lea     rax, [rcx+rdx]
0x180023c82  cmovnb  rax, rdx
0x180023c86  inc     r11b
0x180023c89  mov     rdx, rax
0x180023c8c  cmp     r11b, r14b
0x180023c8f  jb      short loc_180023C67
0x180023c91  add     rax, r10
0x180023c94  cmp     rax, 0FFFFh
0x180023c9a  jbe     short loc_180023CA6
0x180023c9c  mov     eax, 216h
0x180023ca1  jmp     loc_180023E15
0x180023ca6  mov     rbx, r14
0x180023ca9  mov     esi, 8
0x180023cae  shl     rbx, 4
0x180023cb2  lea     rdi, [rbx+2Eh]
0x180023cb6  add     rdi, r10
0x180023cb9  jz      loc_180023E13
0x180023cbf  call    cs:__imp_GetProcessHeap
0x180023cc5  mov     r8, rdi; dwBytes
0x180023cc8  mov     edx, esi; dwFlags
0x180023cca  mov     rcx, rax; hHeap
0x180023ccd  call    cs:__imp_HeapAlloc
0x180023cd3  mov     [rsp+68h+var_48], rax
0x180023cd8  test    rax, rax
0x180023cdb  jz      loc_180023E13
0x180023ce1  mov     rdx, rbx
0x180023ce4  mov     [rsp+68h+var_40], rdi
0x180023ce9  lea     rcx, [rsp+68h+var_48]
0x180023cee  call    CBufferGetNextOffset
0x180023cf3  xor     sil, sil
0x180023cf6  mov     r13, rax
0x180023cf9  add     bpl, r15b
0x180023cfc  mov     r15b, bpl
0x180023cff  mov     [rsp+68h+arg_8], r15d
0x180023d04  jz      short loc_180023D6D
0x180023d06  xor     r15d, r15d
0x180023d09  mov     rdi, r15
0x180023d0c  add     rdi, rdi
0x180023d0f  cmp     sil, 2
0x180023d13  jnb     short loc_180023D23
0x180023d15  movups  xmm0, xmmword ptr [r12+rdi*8]
0x180023d1a  movdqu  xmmword ptr [r13+rdi*8+0], xmm0
0x180023d21  jmp     short loc_180023D5D
0x180023d23  mov     edx, [r12+rdi*8+8]
0x180023d28  lea     rcx, [rsp+68h+var_48]
0x180023d2d  call    CBufferGetNextOffset
0x180023d32  mov     r8d, edx; Size
0x180023d35  mov     rcx, rax; void *
0x180023d38  mov     rdx, [r12+rdi*8]; Src
0x180023d3c  mov     rbx, rax
0x180023d3f  call    memcpy_0
0x180023d44  mov     [r13+rdi*8+0], rbx
0x180023d49  mov     eax, [r12+rdi*8+0Ch]
0x180023d4e  mov     [r13+rdi*8+0Ch], eax
0x180023d53  mov     eax, [r12+rdi*8+8]
0x180023d58  mov     [r13+rdi*8+8], eax
0x180023d5d  inc     sil
0x180023d60  inc     r15
0x180023d63  cmp     sil, bpl
0x180023d66  jb      short loc_180023D09
0x180023d68  mov     r15d, [rsp+68h+arg_8]
0x180023d6d  mov     edx, 2Eh ; '.'
0x180023d72  lea     rcx, [rsp+68h+var_48]
0x180023d77  call    CBufferGetNextOffset
0x180023d7c  mov     rsi, rax
0x180023d7f  mov     [rax+10h], r13
0x180023d83  mov     rax, [rsp+68h+arg_0]
0x180023d88  movups  xmm0, xmmword ptr [rax]
0x180023d8b  mov     al, [rsp+68h+arg_18]
0x180023d92  mov     [rsi+2Dh], al
0x180023d95  mov     eax, [rsp+68h+arg_20]
0x180023d9c  mov     [rsi+28h], eax
0x180023d9f  mov     [rsi+2Ch], r14b
0x180023da3  movdqu  xmmword ptr [rsi], xmm0
0x180023da7  cmp     r15b, r14b
0x180023daa  jnb     short loc_180023E04
0x180023dac  movzx   ebp, bpl
0x180023db0  mov     rdi, rbp
0x180023db3  lea     rcx, [rsp+68h+var_48]
0x180023db8  add     rdi, rdi
0x180023dbb  mov     edx, [r12+rdi*8+8]
0x180023dc0  call    CBufferGetNextOffset
0x180023dc5  mov     r8d, edx; Size
0x180023dc8  mov     rcx, rax; void *
0x180023dcb  mov     rdx, [r12+rdi*8]; Src
0x180023dcf  mov     rbx, rax
0x180023dd2  call    memcpy_0
0x180023dd7  mov     rax, [rsi+10h]
0x180023ddb  inc     r15b
0x180023dde  inc     rbp
0x180023de1  mov     [rax+rdi*8], rbx
0x180023de5  mov     rcx, [rsi+10h]
0x180023de9  mov     eax, [r12+rdi*8+0Ch]
0x180023dee  mov     [rcx+rdi*8+0Ch], eax
0x180023df2  mov     rcx, [rsi+10h]
0x180023df6  mov     eax, [r12+rdi*8+8]
0x180023dfb  mov     [rcx+rdi*8+8], eax
0x180023dff  cmp     r15b, r14b
0x180023e02  jb      short loc_180023DB0
0x180023e04  mov     rax, [rsp+68h+arg_28]
0x180023e0c  mov     [rax], rsi
0x180023e0f  xor     eax, eax
0x180023e11  jmp     short loc_180023E15
0x180023e13  mov     eax, esi
0x180023e15  mov     rbx, [rsp+68h+arg_10]
0x180023e1d  add     rsp, 30h
0x180023e21  pop     r15
0x180023e23  pop     r14
0x180023e25  pop     r13
0x180023e27  pop     r12
0x180023e29  pop     rdi
0x180023e2a  pop     rsi
0x180023e2b  pop     rbp
0x180023e2c  retn
```
