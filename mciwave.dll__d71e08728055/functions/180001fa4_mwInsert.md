# mwInsert

- ea: `0x180001fa4`
- end: `0x180002148`
- name: `mwInsert`
- size: `420`
- prototype: `__int64 __fastcall(int, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001860`

## callees

- `0x180001768`
- `0x18000180c`
- `0x180001fa4`
- `0x18000276c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800020ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800020ac`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002082`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002082`

## pseudocode

```c
_BOOL8 __fastcall mwInsert(__int64 a1, char *lpBuffer, DWORD nNumberOfBytesToWrite)
{
  DWORD v3; // esi
  int *DataNode; // rbx
  int v7; // edx
  int v8; // r8d
  int v9; // r14d
  unsigned int v10; // r14d
  DWORD v11; // r8d
  DWORD v12; // ebp
  void *v13; // rcx
  LONG v14; // edx
  __int64 v15; // rcx
  unsigned int v16; // eax
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  v3 = nNumberOfBytesToWrite;
  DataNode = (int *)(*(_QWORD *)(a1 + 104) + 16LL * *(unsigned int *)(a1 + 120));
  if ( nNumberOfBytesToWrite )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *DataNode < 0 )
        {
          v7 = DataNode[1];
          v8 = *(_DWORD *)(a1 + 124);
          v9 = *(_DWORD *)(a1 + 64);
          if ( v9 == v8 + v7 )
            break;
        }
        v16 = mwSplitCurrentDataNode(a1);
        if ( v16 == -1 )
          return v3 == 0;
        DataNode = (int *)(*(_QWORD *)(a1 + 104) + 16LL * v16);
      }
      v10 = v9 - v8;
      v11 = DataNode[2] - v7;
      if ( v3 > v11 )
      {
        if ( DataNode[2] + (*DataNode & 0x7FFFFFFF) != *(_DWORD *)(a1 + 132) )
        {
          v12 = GatherAdjacentFreeDataNodes(a1, DataNode, v10, v3);
          goto LABEL_8;
        }
        DataNode[2] = v3
                    + DataNode[2]
                    + *(_DWORD *)(a1 + 148)
                    - (v3 + *(_DWORD *)(a1 + 148) - v11 - 1) % *(_DWORD *)(a1 + 148)
                    - v11
                    - 1;
        *(_DWORD *)(a1 + 132) += v3
                               + *(_DWORD *)(a1 + 148)
                               - (v3 + *(_DWORD *)(a1 + 148) - v11 - 1) % *(_DWORD *)(a1 + 148)
                               - v11
                               - 1;
      }
      v12 = v3;
LABEL_8:
      if ( v12 )
      {
        v13 = *(void **)(a1 + 88);
        v14 = v10 + (*DataNode & 0x7FFFFFFF);
        NumberOfBytesWritten = 0;
        if ( SetFilePointer(v13, v14, 0, 0) == -1
          || (!WriteFile(*(HANDLE *)(a1 + 88), lpBuffer, v12, &NumberOfBytesWritten, 0)
           || (v15 = NumberOfBytesWritten, NumberOfBytesWritten != v12)
            ? (LODWORD(v15) = -1)
            : (DataNode[1] += NumberOfBytesWritten,
               lpBuffer += v15,
               *(_DWORD *)(a1 + 64) += v15,
               v3 -= v15,
               *(_DWORD *)(a1 + 76) += v15),
              (_DWORD)v15 != v12) )
        {
          *(_DWORD *)(a1 + 140) = 349;
          return v3 == 0;
        }
      }
      if ( v3 )
      {
        DataNode = (int *)NextDataNode(a1, v3);
        if ( DataNode )
          continue;
      }
      return v3 == 0;
    }
  }
  return v3 == 0;
}

```

## disassembly

```asm
0x180001fa4  push    rbx
0x180001fa6  push    rbp
0x180001fa7  push    rsi
0x180001fa8  push    rdi
0x180001fa9  push    r14
0x180001fab  push    r15
0x180001fad  sub     rsp, 38h
0x180001fb1  mov     ebx, [rcx+78h]
0x180001fb4  mov     esi, r8d
0x180001fb7  shl     rbx, 4
0x180001fbb  mov     r15, rdx
0x180001fbe  add     rbx, [rcx+68h]
0x180001fc2  mov     rdi, rcx
0x180001fc5  test    r8d, r8d
0x180001fc8  jz      loc_180002134
0x180001fce  mov     ecx, [rbx]
0x180001fd0  test    ecx, ecx
0x180001fd2  jns     loc_18000210C
0x180001fd8  mov     edx, [rbx+4]
0x180001fdb  mov     r8d, [rdi+7Ch]
0x180001fdf  mov     r14d, [rdi+40h]
0x180001fe3  lea     eax, [r8+rdx]
0x180001fe7  cmp     r14d, eax
0x180001fea  jnz     loc_18000210C
0x180001ff0  sub     r14d, r8d
0x180001ff3  mov     r8d, [rbx+8]
0x180001ff7  sub     r8d, edx
0x180001ffa  cmp     esi, r8d
0x180001ffd  jb      short loc_18000205A
0x180001fff  jz      short loc_18000205A
0x180002001  btr     ecx, 1Fh
0x180002005  add     ecx, [rbx+8]
0x180002008  cmp     ecx, [rdi+84h]
0x18000200e  jnz     loc_1800020D1
0x180002014  mov     ecx, [rdi+94h]
0x18000201a  xor     edx, edx
0x18000201c  mov     eax, ecx
0x18000201e  sub     eax, r8d
0x180002021  dec     eax
0x180002023  add     eax, esi
0x180002025  div     ecx
0x180002027  sub     ecx, edx
0x180002029  xor     edx, edx
0x18000202b  sub     ecx, r8d
0x18000202e  add     ecx, [rbx+8]
0x180002031  lea     eax, [rcx-1]
0x180002034  add     eax, esi
0x180002036  mov     [rbx+8], eax
0x180002039  mov     ecx, [rdi+94h]
0x18000203f  mov     eax, ecx
0x180002041  sub     eax, r8d
0x180002044  dec     eax
0x180002046  add     eax, esi
0x180002048  div     ecx
0x18000204a  sub     ecx, edx
0x18000204c  sub     ecx, r8d
0x18000204f  lea     eax, [rcx-1]
0x180002052  add     eax, esi
0x180002054  add     [rdi+84h], eax
0x18000205a  mov     ebp, esi
0x18000205c  test    ebp, ebp
0x18000205e  jz      loc_1800020F0
0x180002064  mov     edx, [rbx]
0x180002066  xor     r9d, r9d; dwMoveMethod
0x180002069  mov     rcx, [rdi+58h]; hFile
0x18000206d  btr     edx, 1Fh
0x180002071  add     edx, r14d; lDistanceToMove
0x180002074  mov     [rsp+68h+NumberOfBytesWritten], 0
0x18000207f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002082  call    cs:__imp_SetFilePointer
0x180002088  cmp     eax, 0FFFFFFFFh
0x18000208b  jz      loc_18000212A
0x180002091  mov     rcx, [rdi+58h]; hFile
0x180002095  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000209d  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800020a0  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800020a9  mov     rdx, r15; lpBuffer
0x1800020ac  call    cs:__imp_WriteFile
0x1800020b2  test    eax, eax
0x1800020b4  jz      short loc_1800020E9
0x1800020b6  mov     ecx, [rsp+68h+NumberOfBytesWritten]
0x1800020bd  cmp     ecx, ebp
0x1800020bf  jnz     short loc_1800020E9
0x1800020c1  add     [rbx+4], ecx
0x1800020c4  add     r15, rcx
0x1800020c7  add     [rdi+40h], ecx
0x1800020ca  sub     esi, ecx
0x1800020cc  add     [rdi+4Ch], ecx
0x1800020cf  jmp     short loc_1800020EC
0x1800020d1  mov     r9d, esi
0x1800020d4  mov     r8d, r14d
0x1800020d7  mov     rdx, rbx
0x1800020da  mov     rcx, rdi
0x1800020dd  call    GatherAdjacentFreeDataNodes
0x1800020e2  mov     ebp, eax
0x1800020e4  jmp     loc_18000205C
0x1800020e9  or      ecx, 0FFFFFFFFh
0x1800020ec  cmp     ecx, ebp
0x1800020ee  jnz     short loc_18000212A
0x1800020f0  test    esi, esi
0x1800020f2  jz      short loc_180002134
0x1800020f4  mov     edx, esi
0x1800020f6  mov     rcx, rdi
0x1800020f9  call    NextDataNode
0x1800020fe  mov     rbx, rax
0x180002101  test    rax, rax
0x180002104  jnz     loc_180001FCE
0x18000210a  jmp     short loc_180002134
0x18000210c  mov     edx, esi
0x18000210e  mov     rcx, rdi; int
0x180002111  call    mwSplitCurrentDataNode
0x180002116  cmp     eax, 0FFFFFFFFh
0x180002119  jz      short loc_180002134
0x18000211b  mov     ebx, eax
0x18000211d  shl     rbx, 4
0x180002121  add     rbx, [rdi+68h]
0x180002125  jmp     loc_180001FCE
0x18000212a  mov     dword ptr [rdi+8Ch], 15Dh
0x180002134  xor     eax, eax
0x180002136  test    esi, esi
0x180002138  setz    al
0x18000213b  add     rsp, 38h
0x18000213f  pop     r15
0x180002141  pop     r14
0x180002143  pop     rdi
0x180002144  pop     rsi
0x180002145  pop     rbp
0x180002146  pop     rbx
0x180002147  retn
```
