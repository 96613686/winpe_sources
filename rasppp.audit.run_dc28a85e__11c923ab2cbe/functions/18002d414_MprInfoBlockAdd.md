# MprInfoBlockAdd

- ea: `0x18002d414`
- end: `0x18002d685`
- name: `MprInfoBlockAdd`
- size: `625`
- prototype: `DWORD __stdcall(LPVOID lpHeader, DWORD dwInfoType, DWORD dwItemSize, DWORD dwItemCount, LPBYTE lpItemData, LPVOID *lplpNewHeader)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180019098`
- `0x18001928c`
- `0x18001973c`

## callees

- `0x180001d3e`
- `0x18002d3ec`
- `0x18002d414`
- `0x18002d7d4`
- `0x180033a80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d539`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d54d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d54d`

## pseudocode

```c
DWORD __stdcall MprInfoBlockAdd(
        LPVOID lpHeader,
        DWORD dwInfoType,
        DWORD dwItemSize,
        DWORD dwItemCount,
        LPBYTE lpItemData,
        LPVOID *lplpNewHeader)
{
  __int64 v6; // rsi
  __int64 v8; // rbp
  LPVOID *v10; // rdi
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  unsigned int v13; // r14d
  DWORD result; // eax
  unsigned int v15; // ecx
  size_t v16; // r15
  HANDLE ProcessHeap; // rax
  void *v18; // rax
  unsigned int v19; // r15d
  void *i; // rbp
  __int64 v21; // rsi
  __int64 v22; // rax
  char *v23; // rdx

  v6 = dwItemCount;
  v8 = dwItemSize;
  if ( !lpHeader )
    return 87;
  v10 = lplpNewHeader;
  if ( !lplpNewHeader )
    return 87;
  v11 = *((_DWORD *)lpHeader + 2);
  v12 = 0;
  if ( v11 )
  {
    while ( *((_DWORD *)lpHeader + 4 * v12 + 3) != dwInfoType )
    {
      if ( ++v12 >= v11 )
        goto LABEL_6;
    }
    return 87;
  }
LABEL_6:
  if ( v12 < v11 )
    return 87;
  v13 = dwItemCount * v8;
  if ( dwItemCount * (_DWORD)v8 )
  {
    if ( !lpItemData )
      return 87;
  }
  *lplpNewHeader = 0;
  if ( !(unsigned int)ValidateRTRInfoBlockHeader(lpHeader) )
    return 87;
  LODWORD(lplpNewHeader) = *((_DWORD *)lpHeader + 1);
  result = AlignLength(&lplpNewHeader);
  if ( (result & 0x80000000) != 0 )
    return (unsigned __int16)result;
  if ( (int)lplpNewHeader + 16 < (unsigned int)lplpNewHeader )
    return 534;
  LODWORD(lplpNewHeader) = (_DWORD)lplpNewHeader + 16;
  result = AlignLength(&lplpNewHeader);
  if ( (result & 0x80000000) != 0 )
    return (unsigned __int16)result;
  v15 = v6 * v8;
  if ( (unsigned __int64)(v6 * v8) > 0xFFFFFFFF || v15 + (unsigned int)lplpNewHeader < v15 )
    return 534;
  LODWORD(lplpNewHeader) = v15 + (_DWORD)lplpNewHeader;
  result = AlignLength(&lplpNewHeader);
  if ( (result & 0x80000000) != 0 )
    return (unsigned __int16)result;
  v16 = (unsigned int)lplpNewHeader;
  ProcessHeap = GetProcessHeap();
  v18 = HeapAlloc(ProcessHeap, 0, (unsigned int)v16);
  *v10 = v18;
  if ( !v18 )
    return 8;
  memset_0(v18, 0, v16);
  memcpy_0(*v10, lpHeader, 16LL * *((unsigned int *)lpHeader + 2) + 12);
  v19 = 0;
  *((_DWORD *)*v10 + 4 * *((unsigned int *)lpHeader + 2) + 3) = dwInfoType;
  *((_DWORD *)*v10 + 4 * *((unsigned int *)lpHeader + 2) + 4) = v8;
  *((_DWORD *)*v10 + 4 * *((unsigned int *)lpHeader + 2) + 5) = v6;
  for ( i = (void *)(((unsigned __int64)*v10 + 16 * (unsigned int)++*((_DWORD *)*v10 + 2) + 19) & 0xFFFFFFFFFFFFFFF8uLL);
        v19 < *((_DWORD *)lpHeader + 2);
        i = (void *)(((unsigned __int64)i
                    + (unsigned int)(*(_DWORD *)((char *)lpHeader + v21 + 16) * *(_DWORD *)((char *)lpHeader + v21 + 20))
                    + 7)
                   & 0xFFFFFFFFFFFFFFF8uLL) )
  {
    v21 = 16LL * v19;
    v22 = *(unsigned int *)((char *)lpHeader + v21 + 24);
    if ( (unsigned int)v22 >= *((_DWORD *)lpHeader + 1) )
      v23 = 0;
    else
      v23 = (char *)lpHeader + v22;
    memcpy_0(
      i,
      v23,
      (unsigned int)(*(_DWORD *)((char *)lpHeader + v21 + 16) * *(_DWORD *)((char *)lpHeader + v21 + 20)));
    ++v19;
    *(_DWORD *)((char *)*v10 + v21 + 24) = (_DWORD)i - *(_DWORD *)v10;
  }
  memcpy_0(i, lpItemData, v13);
  *((_DWORD *)*v10 + 4 * v19 + 6) = (_DWORD)i - *(_DWORD *)v10;
  *((_DWORD *)*v10 + 1) = (((_DWORD)i + v13 + 7) & 0xFFFFFFF8) - *(_DWORD *)v10;
  return 0;
}

```

## disassembly

```asm
0x18002d414  push    rbx
0x18002d416  push    rbp
0x18002d417  push    rsi
0x18002d418  push    rdi
0x18002d419  push    r13
0x18002d41b  push    r14
0x18002d41d  push    r15
0x18002d41f  sub     rsp, 20h
0x18002d423  mov     esi, r9d
0x18002d426  mov     r13d, edx
0x18002d429  mov     ebp, r8d
0x18002d42c  mov     rbx, rcx
0x18002d42f  test    rcx, rcx
0x18002d432  jz      loc_18002D670
0x18002d438  mov     rdi, [rsp+58h+lplpNewHeader]
0x18002d440  test    rdi, rdi
0x18002d443  jz      loc_18002D670
0x18002d449  mov     r8d, [rbx+8]
0x18002d44d  xor     ecx, ecx
0x18002d44f  test    r8d, r8d
0x18002d452  jz      short loc_18002D46B
0x18002d454  mov     eax, ecx
0x18002d456  add     rax, rax
0x18002d459  cmp     [rbx+rax*8+0Ch], r13d
0x18002d45e  jz      loc_18002D670
0x18002d464  inc     ecx
0x18002d466  cmp     ecx, r8d
0x18002d469  jb      short loc_18002D454
0x18002d46b  cmp     ecx, r8d
0x18002d46e  jb      loc_18002D670
0x18002d474  mov     r14d, ebp
0x18002d477  imul    r14d, esi
0x18002d47b  test    r14d, r14d
0x18002d47e  jz      short loc_18002D48F
0x18002d480  cmp     [rsp+58h+lpItemData], 0
0x18002d489  jz      loc_18002D670
0x18002d48f  mov     qword ptr [rdi], 0
0x18002d496  mov     rcx, rbx
0x18002d499  call    ValidateRTRInfoBlockHeader
0x18002d49e  test    eax, eax
0x18002d4a0  jz      loc_18002D670
0x18002d4a6  mov     eax, [rbx+4]
0x18002d4a9  mov     dword ptr [rsp+58h+lplpNewHeader], eax
0x18002d4b0  lea     rcx, [rsp+58h+lplpNewHeader]
0x18002d4b8  call    AlignLength
0x18002d4bd  test    eax, eax
0x18002d4bf  jns     short loc_18002D4C9
0x18002d4c1  movzx   eax, ax
0x18002d4c4  jmp     loc_18002D675
0x18002d4c9  mov     eax, dword ptr [rsp+58h+lplpNewHeader]
0x18002d4d0  lea     ecx, [rax+10h]
0x18002d4d3  cmp     ecx, eax
0x18002d4d5  jb      loc_18002D669
0x18002d4db  mov     dword ptr [rsp+58h+lplpNewHeader], ecx
0x18002d4e2  lea     rcx, [rsp+58h+lplpNewHeader]
0x18002d4ea  call    AlignLength
0x18002d4ef  test    eax, eax
0x18002d4f1  js      short loc_18002D4C1
0x18002d4f3  mov     rcx, rbp
0x18002d4f6  mov     eax, 0FFFFFFFFh
0x18002d4fb  imul    rcx, rsi
0x18002d4ff  cmp     rcx, rax
0x18002d502  ja      loc_18002D669
0x18002d508  mov     edx, dword ptr [rsp+58h+lplpNewHeader]
0x18002d50f  add     edx, ecx
0x18002d511  cmp     edx, ecx
0x18002d513  jb      loc_18002D669
0x18002d519  mov     dword ptr [rsp+58h+lplpNewHeader], edx
0x18002d520  lea     rcx, [rsp+58h+lplpNewHeader]
0x18002d528  call    AlignLength
0x18002d52d  test    eax, eax
0x18002d52f  js      short loc_18002D4C1
0x18002d531  mov     r15d, dword ptr [rsp+58h+lplpNewHeader]
0x18002d539  call    cs:__imp_GetProcessHeap
0x18002d540  nop     dword ptr [rax+rax+00h]
0x18002d545  mov     r8d, r15d; dwBytes
0x18002d548  xor     edx, edx; dwFlags
0x18002d54a  mov     rcx, rax; hHeap
0x18002d54d  call    cs:__imp_HeapAlloc
0x18002d554  nop     dword ptr [rax+rax+00h]
0x18002d559  mov     [rdi], rax
0x18002d55c  test    rax, rax
0x18002d55f  jnz     short loc_18002D56B
0x18002d561  mov     eax, 8
0x18002d566  jmp     loc_18002D675
0x18002d56b  mov     r8, r15; Size
0x18002d56e  xor     edx, edx; Val
0x18002d570  mov     rcx, rax; void *
0x18002d573  call    memset_0
0x18002d578  mov     r8d, [rbx+8]
0x18002d57c  mov     rdx, rbx; Src
0x18002d57f  mov     rcx, [rdi]; void *
0x18002d582  shl     r8, 4
0x18002d586  add     r8, 0Ch; Size
0x18002d58a  call    memcpy_0
0x18002d58f  mov     ecx, [rbx+8]
0x18002d592  xor     r15d, r15d
0x18002d595  mov     rax, [rdi]
0x18002d598  add     rcx, rcx
0x18002d59b  mov     [rax+rcx*8+0Ch], r13d
0x18002d5a0  mov     ecx, [rbx+8]
0x18002d5a3  mov     rax, [rdi]
0x18002d5a6  inc     rcx
0x18002d5a9  add     rcx, rcx
0x18002d5ac  mov     [rax+rcx*8], ebp
0x18002d5af  mov     ecx, [rbx+8]
0x18002d5b2  mov     rax, [rdi]
0x18002d5b5  add     rcx, rcx
0x18002d5b8  mov     [rax+rcx*8+14h], esi
0x18002d5bc  mov     rax, [rdi]
0x18002d5bf  inc     dword ptr [rax+8]
0x18002d5c2  mov     rcx, [rdi]
0x18002d5c5  mov     eax, [rcx+8]
0x18002d5c8  lea     rbp, [rcx+13h]
0x18002d5cc  shl     rax, 4
0x18002d5d0  add     rbp, rax
0x18002d5d3  and     rbp, 0FFFFFFFFFFFFFFF8h
0x18002d5d7  cmp     [rbx+8], r15d
0x18002d5db  jbe     short loc_18002D630
0x18002d5dd  mov     esi, r15d
0x18002d5e0  shl     rsi, 4
0x18002d5e4  mov     eax, [rsi+rbx+18h]
0x18002d5e8  cmp     eax, [rbx+4]
0x18002d5eb  jnb     short loc_18002D5F3
0x18002d5ed  lea     rdx, [rbx+rax]
0x18002d5f1  jmp     short loc_18002D5F5
0x18002d5f3  xor     edx, edx; Src
0x18002d5f5  mov     r8d, [rsi+rbx+14h]
0x18002d5fa  mov     rcx, rbp; void *
0x18002d5fd  imul    r8d, [rsi+rbx+10h]; Size
0x18002d603  call    memcpy_0
0x18002d608  mov     rax, [rdi]
0x18002d60b  mov     ecx, ebp
0x18002d60d  sub     ecx, [rdi]
0x18002d60f  add     rbp, 7
0x18002d613  inc     r15d
0x18002d616  mov     [rsi+rax+18h], ecx
0x18002d61a  mov     eax, [rsi+rbx+14h]
0x18002d61e  imul    eax, [rsi+rbx+10h]
0x18002d623  add     rbp, rax
0x18002d626  and     rbp, 0FFFFFFFFFFFFFFF8h
0x18002d62a  cmp     r15d, [rbx+8]
0x18002d62e  jb      short loc_18002D5DD
0x18002d630  mov     rdx, [rsp+58h+lpItemData]; Src
0x18002d638  mov     rcx, rbp; void *
0x18002d63b  mov     r8d, r14d; Size
0x18002d63e  call    memcpy_0
0x18002d643  mov     rax, [rdi]
0x18002d646  mov     edx, ebp
0x18002d648  sub     edx, [rdi]
0x18002d64a  mov     ecx, r15d
0x18002d64d  add     rcx, rcx
0x18002d650  mov     [rax+rcx*8+18h], edx
0x18002d654  lea     ecx, [r14+7]
0x18002d658  mov     rax, [rdi]
0x18002d65b  add     ecx, ebp
0x18002d65d  and     ecx, 0FFFFFFF8h
0x18002d660  sub     ecx, [rdi]
0x18002d662  mov     [rax+4], ecx
0x18002d665  xor     eax, eax
0x18002d667  jmp     short loc_18002D675
0x18002d669  mov     eax, 216h
0x18002d66e  jmp     short loc_18002D675
0x18002d670  mov     eax, 57h ; 'W'
0x18002d675  add     rsp, 20h
0x18002d679  pop     r15
0x18002d67b  pop     r14
0x18002d67d  pop     r13
0x18002d67f  pop     rdi
0x18002d680  pop     rsi
0x18002d681  pop     rbp
0x18002d682  pop     rbx
0x18002d683  retn
```
