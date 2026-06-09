# CreateNewEventEntry

- ea: `0x18000a880`
- end: `0x18000aa89`
- name: `CreateNewEventEntry`
- size: `521`
- prototype: `__int64 __fastcall(__int128 *, unsigned __int8, __int64, char, int, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000acc0`

## callees

- `0x18000a7f0`
- `0x18000a880`
- `0x18000b3c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a91b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a91b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a929`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a929`

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
0x18000a880  mov     [rsp+arg_10], rbx
0x18000a885  mov     [rsp+arg_18], r9b
0x18000a88a  mov     [rsp+arg_0], rcx
0x18000a88f  push    rbp
0x18000a890  push    rsi
0x18000a891  push    rdi
0x18000a892  push    r12
0x18000a894  push    r13
0x18000a896  push    r14
0x18000a898  push    r15
0x18000a89a  sub     rsp, 30h
0x18000a89e  mov     rax, [rsp+68h+arg_28]
0x18000a8a6  xor     r10d, r10d
0x18000a8a9  movzx   r14d, dl
0x18000a8ad  xor     r11b, r11b
0x18000a8b0  xor     edx, edx
0x18000a8b2  mov     bpl, r9b
0x18000a8b5  mov     r12, r8
0x18000a8b8  mov     r15b, 2
0x18000a8bb  mov     [rax], rdx
0x18000a8be  test    r14b, r14b
0x18000a8c1  jz      short loc_18000A902
0x18000a8c3  movzx   eax, r11b
0x18000a8c7  add     rax, rax
0x18000a8ca  cmp     r11b, r15b
0x18000a8cd  mov     ecx, [r8+rax*8+8]
0x18000a8d2  lea     rax, [rcx+r10]
0x18000a8d6  cmovnb  r10, rax
0x18000a8da  lea     rax, [rcx+rdx]
0x18000a8de  cmovnb  rax, rdx
0x18000a8e2  inc     r11b
0x18000a8e5  mov     rdx, rax
0x18000a8e8  cmp     r11b, r14b
0x18000a8eb  jb      short loc_18000A8C3
0x18000a8ed  add     rax, r10
0x18000a8f0  cmp     rax, 0FFFFh
0x18000a8f6  jbe     short loc_18000A902
0x18000a8f8  mov     eax, 216h
0x18000a8fd  jmp     loc_18000AA71
0x18000a902  mov     rbx, r14
0x18000a905  mov     esi, 8
0x18000a90a  shl     rbx, 4
0x18000a90e  lea     rdi, [rbx+2Eh]
0x18000a912  add     rdi, r10
0x18000a915  jz      loc_18000AA6F
0x18000a91b  call    cs:__imp_GetProcessHeap
0x18000a921  mov     r8, rdi; dwBytes
0x18000a924  mov     edx, esi; dwFlags
0x18000a926  mov     rcx, rax; hHeap
0x18000a929  call    cs:__imp_HeapAlloc
0x18000a92f  mov     [rsp+68h+var_48], rax
0x18000a934  test    rax, rax
0x18000a937  jz      loc_18000AA6F
0x18000a93d  mov     rdx, rbx
0x18000a940  mov     [rsp+68h+var_40], rdi
0x18000a945  lea     rcx, [rsp+68h+var_48]
0x18000a94a  call    CBufferGetNextOffset
0x18000a94f  xor     sil, sil
0x18000a952  mov     r13, rax
0x18000a955  add     bpl, r15b
0x18000a958  mov     r15b, bpl
0x18000a95b  mov     [rsp+68h+arg_8], r15d
0x18000a960  jz      short loc_18000A9C9
0x18000a962  xor     r15d, r15d
0x18000a965  mov     rdi, r15
0x18000a968  add     rdi, rdi
0x18000a96b  cmp     sil, 2
0x18000a96f  jnb     short loc_18000A97F
0x18000a971  movups  xmm0, xmmword ptr [r12+rdi*8]
0x18000a976  movdqu  xmmword ptr [r13+rdi*8+0], xmm0
0x18000a97d  jmp     short loc_18000A9B9
0x18000a97f  mov     edx, [r12+rdi*8+8]
0x18000a984  lea     rcx, [rsp+68h+var_48]
0x18000a989  call    CBufferGetNextOffset
0x18000a98e  mov     r8d, edx; Size
0x18000a991  mov     rcx, rax; void *
0x18000a994  mov     rdx, [r12+rdi*8]; Src
0x18000a998  mov     rbx, rax
0x18000a99b  call    memcpy_0
0x18000a9a0  mov     [r13+rdi*8+0], rbx
0x18000a9a5  mov     eax, [r12+rdi*8+0Ch]
0x18000a9aa  mov     [r13+rdi*8+0Ch], eax
0x18000a9af  mov     eax, [r12+rdi*8+8]
0x18000a9b4  mov     [r13+rdi*8+8], eax
0x18000a9b9  inc     sil
0x18000a9bc  inc     r15
0x18000a9bf  cmp     sil, bpl
0x18000a9c2  jb      short loc_18000A965
0x18000a9c4  mov     r15d, [rsp+68h+arg_8]
0x18000a9c9  mov     edx, 2Eh ; '.'
0x18000a9ce  lea     rcx, [rsp+68h+var_48]
0x18000a9d3  call    CBufferGetNextOffset
0x18000a9d8  mov     rsi, rax
0x18000a9db  mov     [rax+10h], r13
0x18000a9df  mov     rax, [rsp+68h+arg_0]
0x18000a9e4  movups  xmm0, xmmword ptr [rax]
0x18000a9e7  mov     al, [rsp+68h+arg_18]
0x18000a9ee  mov     [rsi+2Dh], al
0x18000a9f1  mov     eax, [rsp+68h+arg_20]
0x18000a9f8  mov     [rsi+28h], eax
0x18000a9fb  mov     [rsi+2Ch], r14b
0x18000a9ff  movdqu  xmmword ptr [rsi], xmm0
0x18000aa03  cmp     r15b, r14b
0x18000aa06  jnb     short loc_18000AA60
0x18000aa08  movzx   ebp, bpl
0x18000aa0c  mov     rdi, rbp
0x18000aa0f  lea     rcx, [rsp+68h+var_48]
0x18000aa14  add     rdi, rdi
0x18000aa17  mov     edx, [r12+rdi*8+8]
0x18000aa1c  call    CBufferGetNextOffset
0x18000aa21  mov     r8d, edx; Size
0x18000aa24  mov     rcx, rax; void *
0x18000aa27  mov     rdx, [r12+rdi*8]; Src
0x18000aa2b  mov     rbx, rax
0x18000aa2e  call    memcpy_0
0x18000aa33  mov     rax, [rsi+10h]
0x18000aa37  inc     r15b
0x18000aa3a  inc     rbp
0x18000aa3d  mov     [rax+rdi*8], rbx
0x18000aa41  mov     rcx, [rsi+10h]
0x18000aa45  mov     eax, [r12+rdi*8+0Ch]
0x18000aa4a  mov     [rcx+rdi*8+0Ch], eax
0x18000aa4e  mov     rcx, [rsi+10h]
0x18000aa52  mov     eax, [r12+rdi*8+8]
0x18000aa57  mov     [rcx+rdi*8+8], eax
0x18000aa5b  cmp     r15b, r14b
0x18000aa5e  jb      short loc_18000AA0C
0x18000aa60  mov     rax, [rsp+68h+arg_28]
0x18000aa68  mov     [rax], rsi
0x18000aa6b  xor     eax, eax
0x18000aa6d  jmp     short loc_18000AA71
0x18000aa6f  mov     eax, esi
0x18000aa71  mov     rbx, [rsp+68h+arg_10]
0x18000aa79  add     rsp, 30h
0x18000aa7d  pop     r15
0x18000aa7f  pop     r14
0x18000aa81  pop     r13
0x18000aa83  pop     r12
0x18000aa85  pop     rdi
0x18000aa86  pop     rsi
0x18000aa87  pop     rbp
0x18000aa88  retn
```
