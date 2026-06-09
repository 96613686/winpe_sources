# MprInfoBlockAdd

- ea: `0x18002c328`
- end: `0x18002c58c`
- name: `MprInfoBlockAdd`
- size: `612`
- prototype: `DWORD __stdcall(LPVOID lpHeader, DWORD dwInfoType, DWORD dwItemSize, DWORD dwItemCount, LPBYTE lpItemData, LPVOID *lplpNewHeader)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800187f8`
- `0x1800189d8`
- `0x180018e1c`

## callees

- `0x180001d3e`
- `0x18002c304`
- `0x18002c328`
- `0x18002c6b8`
- `0x180032460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c44d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c44d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c45b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c45b`

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
0x18002c328  push    rbx
0x18002c32a  push    rbp
0x18002c32b  push    rsi
0x18002c32c  push    rdi
0x18002c32d  push    r13
0x18002c32f  push    r14
0x18002c331  push    r15
0x18002c333  sub     rsp, 20h
0x18002c337  mov     esi, r9d
0x18002c33a  mov     r13d, edx
0x18002c33d  mov     ebp, r8d
0x18002c340  mov     rbx, rcx
0x18002c343  test    rcx, rcx
0x18002c346  jz      loc_18002C578
0x18002c34c  mov     rdi, [rsp+58h+lplpNewHeader]
0x18002c354  test    rdi, rdi
0x18002c357  jz      loc_18002C578
0x18002c35d  mov     r8d, [rbx+8]
0x18002c361  xor     ecx, ecx
0x18002c363  test    r8d, r8d
0x18002c366  jz      short loc_18002C37F
0x18002c368  mov     eax, ecx
0x18002c36a  add     rax, rax
0x18002c36d  cmp     [rbx+rax*8+0Ch], r13d
0x18002c372  jz      loc_18002C578
0x18002c378  inc     ecx
0x18002c37a  cmp     ecx, r8d
0x18002c37d  jb      short loc_18002C368
0x18002c37f  cmp     ecx, r8d
0x18002c382  jb      loc_18002C578
0x18002c388  mov     r14d, ebp
0x18002c38b  imul    r14d, esi
0x18002c38f  test    r14d, r14d
0x18002c392  jz      short loc_18002C3A3
0x18002c394  cmp     [rsp+58h+lpItemData], 0
0x18002c39d  jz      loc_18002C578
0x18002c3a3  mov     qword ptr [rdi], 0
0x18002c3aa  mov     rcx, rbx
0x18002c3ad  call    ValidateRTRInfoBlockHeader
0x18002c3b2  test    eax, eax
0x18002c3b4  jz      loc_18002C578
0x18002c3ba  mov     eax, [rbx+4]
0x18002c3bd  mov     dword ptr [rsp+58h+lplpNewHeader], eax
0x18002c3c4  lea     rcx, [rsp+58h+lplpNewHeader]
0x18002c3cc  call    AlignLength
0x18002c3d1  test    eax, eax
0x18002c3d3  jns     short loc_18002C3DD
0x18002c3d5  movzx   eax, ax
0x18002c3d8  jmp     loc_18002C57D
0x18002c3dd  mov     eax, dword ptr [rsp+58h+lplpNewHeader]
0x18002c3e4  lea     ecx, [rax+10h]
0x18002c3e7  cmp     ecx, eax
0x18002c3e9  jb      loc_18002C571
0x18002c3ef  mov     dword ptr [rsp+58h+lplpNewHeader], ecx
0x18002c3f6  lea     rcx, [rsp+58h+lplpNewHeader]
0x18002c3fe  call    AlignLength
0x18002c403  test    eax, eax
0x18002c405  js      short loc_18002C3D5
0x18002c407  mov     rcx, rbp
0x18002c40a  mov     eax, 0FFFFFFFFh
0x18002c40f  imul    rcx, rsi
0x18002c413  cmp     rcx, rax
0x18002c416  ja      loc_18002C571
0x18002c41c  mov     edx, dword ptr [rsp+58h+lplpNewHeader]
0x18002c423  add     edx, ecx
0x18002c425  cmp     edx, ecx
0x18002c427  jb      loc_18002C571
0x18002c42d  mov     dword ptr [rsp+58h+lplpNewHeader], edx
0x18002c434  lea     rcx, [rsp+58h+lplpNewHeader]
0x18002c43c  call    AlignLength
0x18002c441  test    eax, eax
0x18002c443  js      short loc_18002C3D5
0x18002c445  mov     r15d, dword ptr [rsp+58h+lplpNewHeader]
0x18002c44d  call    cs:__imp_GetProcessHeap
0x18002c453  mov     r8d, r15d; dwBytes
0x18002c456  xor     edx, edx; dwFlags
0x18002c458  mov     rcx, rax; hHeap
0x18002c45b  call    cs:__imp_HeapAlloc
0x18002c461  mov     [rdi], rax
0x18002c464  test    rax, rax
0x18002c467  jnz     short loc_18002C473
0x18002c469  mov     eax, 8
0x18002c46e  jmp     loc_18002C57D
0x18002c473  mov     r8, r15; Size
0x18002c476  xor     edx, edx; Val
0x18002c478  mov     rcx, rax; void *
0x18002c47b  call    memset_0
0x18002c480  mov     r8d, [rbx+8]
0x18002c484  mov     rdx, rbx; Src
0x18002c487  mov     rcx, [rdi]; void *
0x18002c48a  shl     r8, 4
0x18002c48e  add     r8, 0Ch; Size
0x18002c492  call    memcpy_0
0x18002c497  mov     ecx, [rbx+8]
0x18002c49a  xor     r15d, r15d
0x18002c49d  mov     rax, [rdi]
0x18002c4a0  add     rcx, rcx
0x18002c4a3  mov     [rax+rcx*8+0Ch], r13d
0x18002c4a8  mov     ecx, [rbx+8]
0x18002c4ab  mov     rax, [rdi]
0x18002c4ae  inc     rcx
0x18002c4b1  add     rcx, rcx
0x18002c4b4  mov     [rax+rcx*8], ebp
0x18002c4b7  mov     ecx, [rbx+8]
0x18002c4ba  mov     rax, [rdi]
0x18002c4bd  add     rcx, rcx
0x18002c4c0  mov     [rax+rcx*8+14h], esi
0x18002c4c4  mov     rax, [rdi]
0x18002c4c7  inc     dword ptr [rax+8]
0x18002c4ca  mov     rcx, [rdi]
0x18002c4cd  mov     eax, [rcx+8]
0x18002c4d0  lea     rbp, [rcx+13h]
0x18002c4d4  shl     rax, 4
0x18002c4d8  add     rbp, rax
0x18002c4db  and     rbp, 0FFFFFFFFFFFFFFF8h
0x18002c4df  cmp     [rbx+8], r15d
0x18002c4e3  jbe     short loc_18002C538
0x18002c4e5  mov     esi, r15d
0x18002c4e8  shl     rsi, 4
0x18002c4ec  mov     eax, [rsi+rbx+18h]
0x18002c4f0  cmp     eax, [rbx+4]
0x18002c4f3  jnb     short loc_18002C4FB
0x18002c4f5  lea     rdx, [rbx+rax]
0x18002c4f9  jmp     short loc_18002C4FD
0x18002c4fb  xor     edx, edx; Src
0x18002c4fd  mov     r8d, [rsi+rbx+14h]
0x18002c502  mov     rcx, rbp; void *
0x18002c505  imul    r8d, [rsi+rbx+10h]; Size
0x18002c50b  call    memcpy_0
0x18002c510  mov     rax, [rdi]
0x18002c513  mov     ecx, ebp
0x18002c515  sub     ecx, [rdi]
0x18002c517  add     rbp, 7
0x18002c51b  inc     r15d
0x18002c51e  mov     [rsi+rax+18h], ecx
0x18002c522  mov     eax, [rsi+rbx+14h]
0x18002c526  imul    eax, [rsi+rbx+10h]
0x18002c52b  add     rbp, rax
0x18002c52e  and     rbp, 0FFFFFFFFFFFFFFF8h
0x18002c532  cmp     r15d, [rbx+8]
0x18002c536  jb      short loc_18002C4E5
0x18002c538  mov     rdx, [rsp+58h+lpItemData]; Src
0x18002c540  mov     rcx, rbp; void *
0x18002c543  mov     r8d, r14d; Size
0x18002c546  call    memcpy_0
0x18002c54b  mov     rax, [rdi]
0x18002c54e  mov     edx, ebp
0x18002c550  sub     edx, [rdi]
0x18002c552  mov     ecx, r15d
0x18002c555  add     rcx, rcx
0x18002c558  mov     [rax+rcx*8+18h], edx
0x18002c55c  lea     ecx, [r14+7]
0x18002c560  mov     rax, [rdi]
0x18002c563  add     ecx, ebp
0x18002c565  and     ecx, 0FFFFFFF8h
0x18002c568  sub     ecx, [rdi]
0x18002c56a  mov     [rax+4], ecx
0x18002c56d  xor     eax, eax
0x18002c56f  jmp     short loc_18002C57D
0x18002c571  mov     eax, 216h
0x18002c576  jmp     short loc_18002C57D
0x18002c578  mov     eax, 57h ; 'W'
0x18002c57d  add     rsp, 20h
0x18002c581  pop     r15
0x18002c583  pop     r14
0x18002c585  pop     r13
0x18002c587  pop     rdi
0x18002c588  pop     rsi
0x18002c589  pop     rbp
0x18002c58a  pop     rbx
0x18002c58b  retn
```
