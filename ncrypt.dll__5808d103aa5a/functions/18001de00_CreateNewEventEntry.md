# CreateNewEventEntry

- ea: `0x18001de00`
- end: `0x18001e009`
- name: `CreateNewEventEntry`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800184c8`

## callees

- `0x18001dcdc`
- `0x18001de00`
- `0x18001f15d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dea9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de9b`

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
0x18001de00  mov     [rsp+arg_10], rbx
0x18001de05  mov     [rsp+arg_18], r9b
0x18001de0a  mov     [rsp+arg_0], rcx
0x18001de0f  push    rbp
0x18001de10  push    rsi
0x18001de11  push    rdi
0x18001de12  push    r12
0x18001de14  push    r13
0x18001de16  push    r14
0x18001de18  push    r15
0x18001de1a  sub     rsp, 30h
0x18001de1e  mov     rax, [rsp+68h+arg_28]
0x18001de26  xor     r10d, r10d
0x18001de29  movzx   r14d, dl
0x18001de2d  xor     r11b, r11b
0x18001de30  xor     edx, edx
0x18001de32  mov     bpl, r9b
0x18001de35  mov     r12, r8
0x18001de38  mov     r15b, 2
0x18001de3b  mov     [rax], rdx
0x18001de3e  test    r14b, r14b
0x18001de41  jz      short loc_18001DE82
0x18001de43  movzx   eax, r11b
0x18001de47  add     rax, rax
0x18001de4a  cmp     r11b, r15b
0x18001de4d  mov     ecx, [r8+rax*8+8]
0x18001de52  lea     rax, [rcx+r10]
0x18001de56  cmovnb  r10, rax
0x18001de5a  lea     rax, [rcx+rdx]
0x18001de5e  cmovnb  rax, rdx
0x18001de62  inc     r11b
0x18001de65  mov     rdx, rax
0x18001de68  cmp     r11b, r14b
0x18001de6b  jb      short loc_18001DE43
0x18001de6d  add     rax, r10
0x18001de70  cmp     rax, 0FFFFh
0x18001de76  jbe     short loc_18001DE82
0x18001de78  mov     eax, 216h
0x18001de7d  jmp     loc_18001DFF1
0x18001de82  mov     rbx, r14
0x18001de85  mov     esi, 8
0x18001de8a  shl     rbx, 4
0x18001de8e  lea     rdi, [rbx+2Eh]
0x18001de92  add     rdi, r10
0x18001de95  jz      loc_18001DFEF
0x18001de9b  call    cs:__imp_GetProcessHeap
0x18001dea1  mov     r8, rdi; dwBytes
0x18001dea4  mov     edx, esi; dwFlags
0x18001dea6  mov     rcx, rax; hHeap
0x18001dea9  call    cs:__imp_HeapAlloc
0x18001deaf  mov     [rsp+68h+var_48], rax
0x18001deb4  test    rax, rax
0x18001deb7  jz      loc_18001DFEF
0x18001debd  mov     rdx, rbx
0x18001dec0  mov     [rsp+68h+var_40], rdi
0x18001dec5  lea     rcx, [rsp+68h+var_48]
0x18001deca  call    CBufferGetNextOffset
0x18001decf  xor     sil, sil
0x18001ded2  mov     r13, rax
0x18001ded5  add     bpl, r15b
0x18001ded8  mov     r15b, bpl
0x18001dedb  mov     [rsp+68h+arg_8], r15d
0x18001dee0  jz      short loc_18001DF49
0x18001dee2  xor     r15d, r15d
0x18001dee5  mov     rdi, r15
0x18001dee8  add     rdi, rdi
0x18001deeb  cmp     sil, 2
0x18001deef  jnb     short loc_18001DEFF
0x18001def1  movups  xmm0, xmmword ptr [r12+rdi*8]
0x18001def6  movdqu  xmmword ptr [r13+rdi*8+0], xmm0
0x18001defd  jmp     short loc_18001DF39
0x18001deff  mov     edx, [r12+rdi*8+8]
0x18001df04  lea     rcx, [rsp+68h+var_48]
0x18001df09  call    CBufferGetNextOffset
0x18001df0e  mov     r8d, edx; Size
0x18001df11  mov     rcx, rax; void *
0x18001df14  mov     rdx, [r12+rdi*8]; Src
0x18001df18  mov     rbx, rax
0x18001df1b  call    memcpy_0
0x18001df20  mov     [r13+rdi*8+0], rbx
0x18001df25  mov     eax, [r12+rdi*8+0Ch]
0x18001df2a  mov     [r13+rdi*8+0Ch], eax
0x18001df2f  mov     eax, [r12+rdi*8+8]
0x18001df34  mov     [r13+rdi*8+8], eax
0x18001df39  inc     sil
0x18001df3c  inc     r15
0x18001df3f  cmp     sil, bpl
0x18001df42  jb      short loc_18001DEE5
0x18001df44  mov     r15d, [rsp+68h+arg_8]
0x18001df49  mov     edx, 2Eh ; '.'
0x18001df4e  lea     rcx, [rsp+68h+var_48]
0x18001df53  call    CBufferGetNextOffset
0x18001df58  mov     rsi, rax
0x18001df5b  mov     [rax+10h], r13
0x18001df5f  mov     rax, [rsp+68h+arg_0]
0x18001df64  movups  xmm0, xmmword ptr [rax]
0x18001df67  mov     al, [rsp+68h+arg_18]
0x18001df6e  mov     [rsi+2Dh], al
0x18001df71  mov     eax, [rsp+68h+arg_20]
0x18001df78  mov     [rsi+28h], eax
0x18001df7b  mov     [rsi+2Ch], r14b
0x18001df7f  movdqu  xmmword ptr [rsi], xmm0
0x18001df83  cmp     r15b, r14b
0x18001df86  jnb     short loc_18001DFE0
0x18001df88  movzx   ebp, bpl
0x18001df8c  mov     rdi, rbp
0x18001df8f  lea     rcx, [rsp+68h+var_48]
0x18001df94  add     rdi, rdi
0x18001df97  mov     edx, [r12+rdi*8+8]
0x18001df9c  call    CBufferGetNextOffset
0x18001dfa1  mov     r8d, edx; Size
0x18001dfa4  mov     rcx, rax; void *
0x18001dfa7  mov     rdx, [r12+rdi*8]; Src
0x18001dfab  mov     rbx, rax
0x18001dfae  call    memcpy_0
0x18001dfb3  mov     rax, [rsi+10h]
0x18001dfb7  inc     r15b
0x18001dfba  inc     rbp
0x18001dfbd  mov     [rax+rdi*8], rbx
0x18001dfc1  mov     rcx, [rsi+10h]
0x18001dfc5  mov     eax, [r12+rdi*8+0Ch]
0x18001dfca  mov     [rcx+rdi*8+0Ch], eax
0x18001dfce  mov     rcx, [rsi+10h]
0x18001dfd2  mov     eax, [r12+rdi*8+8]
0x18001dfd7  mov     [rcx+rdi*8+8], eax
0x18001dfdb  cmp     r15b, r14b
0x18001dfde  jb      short loc_18001DF8C
0x18001dfe0  mov     rax, [rsp+68h+arg_28]
0x18001dfe8  mov     [rax], rsi
0x18001dfeb  xor     eax, eax
0x18001dfed  jmp     short loc_18001DFF1
0x18001dfef  mov     eax, esi
0x18001dff1  mov     rbx, [rsp+68h+arg_10]
0x18001dff9  add     rsp, 30h
0x18001dffd  pop     r15
0x18001dfff  pop     r14
0x18001e001  pop     r13
0x18001e003  pop     r12
0x18001e005  pop     rdi
0x18001e006  pop     rsi
0x18001e007  pop     rbp
0x18001e008  retn
```
