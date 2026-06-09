# mwOverWrite

- ea: `0x180002150`
- end: `0x180002317`
- name: `mwOverWrite`
- size: `455`
- prototype: `__int64 __fastcall(int, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001860`

## callees

- `0x180001288`
- `0x180001768`
- `0x18000180c`
- `0x180002150`
- `0x18000276c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002260`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002260`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002236`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002236`

## pseudocode

```c
_BOOL8 __fastcall mwOverWrite(__int64 a1, char *lpBuffer, DWORD nNumberOfBytesToWrite)
{
  unsigned int v3; // esi
  int *DataNode; // rbx
  unsigned int v7; // r8d
  unsigned int v8; // r14d
  DWORD v9; // ebp
  void *v10; // rcx
  LONG v11; // edx
  __int64 v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // eax
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  v3 = nNumberOfBytesToWrite;
  DataNode = (int *)(*(_QWORD *)(a1 + 104) + 16LL * *(unsigned int *)(a1 + 120));
  if ( nNumberOfBytesToWrite )
  {
    while ( 1 )
    {
      while ( *DataNode >= 0 )
      {
        v14 = mwSplitCurrentDataNode(a1);
        if ( v14 == -1 )
          return v3 == 0;
        DataNode = (int *)(*(_QWORD *)(a1 + 104) + 16LL * v14);
      }
      v7 = v3;
      v8 = *(_DWORD *)(a1 + 64) - *(_DWORD *)(a1 + 124);
      if ( v3 >= DataNode[2] - v8 )
        v7 = DataNode[2] - v8;
      if ( v7 == v3 )
      {
        v9 = v3;
      }
      else if ( DataNode[2] + (*DataNode & 0x7FFFFFFF) == *(_DWORD *)(a1 + 132) )
      {
        v9 = v3;
        DataNode[2] = v3
                    + DataNode[2]
                    + *(_DWORD *)(a1 + 148)
                    - (v3 + *(_DWORD *)(a1 + 148) - v7 - 1) % *(_DWORD *)(a1 + 148)
                    - v7
                    - 1;
        *(_DWORD *)(a1 + 132) += v3
                               + *(_DWORD *)(a1 + 148)
                               - (v3 + *(_DWORD *)(a1 + 148) - v7 - 1) % *(_DWORD *)(a1 + 148)
                               - v7
                               - 1;
      }
      else
      {
        v9 = GatherAdjacentFreeDataNodes(a1, DataNode, v8, v3);
      }
      if ( v9 )
      {
        v10 = *(void **)(a1 + 88);
        v11 = v8 + (*DataNode & 0x7FFFFFFF);
        NumberOfBytesWritten = 0;
        if ( SetFilePointer(v10, v11, 0, 0) == -1 )
          break;
        if ( WriteFile(*(HANDLE *)(a1 + 88), lpBuffer, v9, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v9 )
        {
          if ( !(unsigned int)AdjustLastTempData(a1) )
            return v3 == 0;
          v12 = NumberOfBytesWritten;
          if ( DataNode[1] < v8 + NumberOfBytesWritten )
            DataNode[1] = v8 + NumberOfBytesWritten;
          *(_DWORD *)(a1 + 64) += v12;
          lpBuffer += v12;
          v3 -= v12;
          v13 = DataNode[1] + *(_DWORD *)(a1 + 124);
          if ( v13 > *(_DWORD *)(a1 + 76) )
            *(_DWORD *)(a1 + 76) = v13;
        }
        else
        {
          LODWORD(v12) = -1;
        }
        if ( (_DWORD)v12 != v9 )
          break;
      }
      if ( v3 )
      {
        DataNode = (int *)NextDataNode(a1, v3);
        if ( DataNode )
          continue;
      }
      return v3 == 0;
    }
    *(_DWORD *)(a1 + 140) = 349;
  }
  return v3 == 0;
}

```

## disassembly

```asm
0x180002150  push    rbx
0x180002152  push    rbp
0x180002153  push    rsi
0x180002154  push    rdi
0x180002155  push    r14
0x180002157  push    r15
0x180002159  sub     rsp, 38h
0x18000215d  mov     ebx, [rcx+78h]
0x180002160  mov     esi, r8d
0x180002163  shl     rbx, 4
0x180002167  mov     r15, rdx
0x18000216a  add     rbx, [rcx+68h]
0x18000216e  mov     rdi, rcx
0x180002171  test    r8d, r8d
0x180002174  jz      loc_180002303
0x18000217a  mov     ecx, [rbx]
0x18000217c  test    ecx, ecx
0x18000217e  jns     loc_1800022DB
0x180002184  mov     r14d, [rdi+40h]
0x180002188  mov     r8d, esi
0x18000218b  sub     r14d, [rdi+7Ch]
0x18000218f  mov     eax, [rbx+8]
0x180002192  sub     eax, r14d
0x180002195  cmp     esi, eax
0x180002197  cmovnb  r8d, eax
0x18000219b  cmp     r8d, esi
0x18000219e  jnz     short loc_1800021A4
0x1800021a0  mov     ebp, esi
0x1800021a2  jmp     short loc_180002210
0x1800021a4  btr     ecx, 1Fh
0x1800021a8  add     ecx, [rbx+8]
0x1800021ab  cmp     ecx, [rdi+84h]
0x1800021b1  jnz     short loc_1800021FD
0x1800021b3  mov     ecx, [rdi+94h]
0x1800021b9  xor     edx, edx
0x1800021bb  mov     eax, ecx
0x1800021bd  mov     ebp, esi
0x1800021bf  sub     eax, r8d
0x1800021c2  dec     eax
0x1800021c4  add     eax, esi
0x1800021c6  div     ecx
0x1800021c8  sub     ecx, edx
0x1800021ca  xor     edx, edx
0x1800021cc  sub     ecx, r8d
0x1800021cf  add     ecx, [rbx+8]
0x1800021d2  lea     eax, [rcx-1]
0x1800021d5  add     eax, esi
0x1800021d7  mov     [rbx+8], eax
0x1800021da  mov     ecx, [rdi+94h]
0x1800021e0  mov     eax, ecx
0x1800021e2  sub     eax, r8d
0x1800021e5  dec     eax
0x1800021e7  add     eax, esi
0x1800021e9  div     ecx
0x1800021eb  sub     ecx, edx
0x1800021ed  sub     ecx, r8d
0x1800021f0  lea     eax, [rcx-1]
0x1800021f3  add     eax, esi
0x1800021f5  add     [rdi+84h], eax
0x1800021fb  jmp     short loc_180002210
0x1800021fd  mov     r9d, esi
0x180002200  mov     r8d, r14d
0x180002203  mov     rdx, rbx
0x180002206  mov     rcx, rdi
0x180002209  call    GatherAdjacentFreeDataNodes
0x18000220e  mov     ebp, eax
0x180002210  test    ebp, ebp
0x180002212  jz      loc_1800022BF
0x180002218  mov     edx, [rbx]
0x18000221a  xor     r9d, r9d; dwMoveMethod
0x18000221d  mov     rcx, [rdi+58h]; hFile
0x180002221  btr     edx, 1Fh
0x180002225  add     edx, r14d; lDistanceToMove
0x180002228  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180002233  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002236  call    cs:__imp_SetFilePointer
0x18000223c  cmp     eax, 0FFFFFFFFh
0x18000223f  jz      loc_1800022F9
0x180002245  mov     rcx, [rdi+58h]; hFile
0x180002249  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002251  mov     r8d, ebp; nNumberOfBytesToWrite
0x180002254  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000225d  mov     rdx, r15; lpBuffer
0x180002260  call    cs:__imp_WriteFile
0x180002266  test    eax, eax
0x180002268  jz      short loc_1800022B8
0x18000226a  mov     r9d, [rsp+68h+NumberOfBytesWritten]
0x180002272  cmp     r9d, ebp
0x180002275  jnz     short loc_1800022B8
0x180002277  mov     r8d, r14d
0x18000227a  mov     rdx, rbx
0x18000227d  mov     rcx, rdi; int
0x180002280  call    AdjustLastTempData
0x180002285  test    eax, eax
0x180002287  jz      short loc_180002303
0x180002289  mov     edx, [rsp+68h+NumberOfBytesWritten]
0x180002290  lea     eax, [r14+rdx]
0x180002294  cmp     [rbx+4], eax
0x180002297  jnb     short loc_18000229C
0x180002299  mov     [rbx+4], eax
0x18000229c  add     [rdi+40h], edx
0x18000229f  add     r15, rdx
0x1800022a2  mov     r8d, [rdi+7Ch]
0x1800022a6  sub     esi, edx
0x1800022a8  add     r8d, [rbx+4]
0x1800022ac  cmp     r8d, [rdi+4Ch]
0x1800022b0  jbe     short loc_1800022BB
0x1800022b2  mov     [rdi+4Ch], r8d
0x1800022b6  jmp     short loc_1800022BB
0x1800022b8  or      edx, 0FFFFFFFFh
0x1800022bb  cmp     edx, ebp
0x1800022bd  jnz     short loc_1800022F9
0x1800022bf  test    esi, esi
0x1800022c1  jz      short loc_180002303
0x1800022c3  mov     edx, esi
0x1800022c5  mov     rcx, rdi
0x1800022c8  call    NextDataNode
0x1800022cd  mov     rbx, rax
0x1800022d0  test    rax, rax
0x1800022d3  jnz     loc_18000217A
0x1800022d9  jmp     short loc_180002303
0x1800022db  mov     edx, esi
0x1800022dd  mov     rcx, rdi; int
0x1800022e0  call    mwSplitCurrentDataNode
0x1800022e5  cmp     eax, 0FFFFFFFFh
0x1800022e8  jz      short loc_180002303
0x1800022ea  mov     ebx, eax
0x1800022ec  shl     rbx, 4
0x1800022f0  add     rbx, [rdi+68h]
0x1800022f4  jmp     loc_18000217A
0x1800022f9  mov     dword ptr [rdi+8Ch], 15Dh
0x180002303  xor     eax, eax
0x180002305  test    esi, esi
0x180002307  setz    al
0x18000230a  add     rsp, 38h
0x18000230e  pop     r15
0x180002310  pop     r14
0x180002312  pop     rdi
0x180002313  pop     rsi
0x180002314  pop     rbp
0x180002315  pop     rbx
0x180002316  retn
```
