# CopyBlockData

- ea: `0x180001424`
- end: `0x180001552`
- name: `CopyBlockData`
- size: `302`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _DWORD *, int, int, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001288`
- `0x180001aa8`
- `0x18000276c`

## callees

- `0x180001424`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001503`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001503`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800014a9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800014a9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180001472`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800014d3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180001472`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800014d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001529`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001529`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001448`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001448`

## pseudocode

```c
__int64 __fastcall CopyBlockData(__int64 a1, _DWORD *a2, _DWORD *a3, int a4, int a5, SIZE_T dwBytes)
{
  DWORD v6; // ebx
  HGLOBAL v11; // rsi
  void *v12; // rcx
  void *v13; // rcx
  int v14; // ebx

  v6 = dwBytes;
  v11 = GlobalAlloc(0, (unsigned int)dwBytes);
  if ( v11 )
  {
    if ( SetFilePointer(*(HANDLE *)(a1 + 88), a4 + (*a2 & 0x7FFFFFFF), 0, 0) == -1
      || (v12 = *(void **)(a1 + 88), LODWORD(dwBytes) = 0, !ReadFile(v12, v11, v6, (LPDWORD)&dwBytes, 0))
      || (_DWORD)dwBytes != v6
      || SetFilePointer(*(HANDLE *)(a1 + 88), a5 + (*a3 & 0x7FFFFFFF), 0, 0) == -1 )
    {
      v14 = 348;
    }
    else
    {
      v13 = *(void **)(a1 + 88);
      LODWORD(dwBytes) = 0;
      if ( WriteFile(v13, v11, v6, (LPDWORD)&dwBytes, 0) && (_DWORD)dwBytes == v6 )
        v14 = 0;
      else
        v14 = 349;
    }
    GlobalFree(v11);
    if ( !v14 )
      return 1;
  }
  else
  {
    v14 = 264;
  }
  *(_DWORD *)(a1 + 140) = v14;
  return 0;
}

```

## disassembly

```asm
0x180001424  push    rbx
0x180001426  push    rbp
0x180001427  push    rsi
0x180001428  push    rdi
0x180001429  push    r14
0x18000142b  push    r15
0x18000142d  sub     rsp, 38h
0x180001431  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x180001438  mov     r14, rdx
0x18000143b  mov     rdi, rcx
0x18000143e  mov     edx, ebx; dwBytes
0x180001440  xor     ecx, ecx; uFlags
0x180001442  mov     ebp, r9d
0x180001445  mov     r15, r8
0x180001448  call    cs:__imp_GlobalAlloc
0x18000144e  mov     rsi, rax
0x180001451  test    rax, rax
0x180001454  jz      loc_180001538
0x18000145a  mov     edx, [r14]
0x18000145d  xor     r9d, r9d; dwMoveMethod
0x180001460  mov     rcx, [rdi+58h]; hFile
0x180001464  mov     r14d, 7FFFFFFFh
0x18000146a  and     edx, r14d
0x18000146d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180001470  add     edx, ebp; lDistanceToMove
0x180001472  call    cs:__imp_SetFilePointer
0x180001478  or      ebp, 0FFFFFFFFh
0x18000147b  cmp     eax, ebp
0x18000147d  jz      loc_180001521
0x180001483  mov     rcx, [rdi+58h]; hFile
0x180001487  lea     r9, [rsp+68h+dwBytes]; lpNumberOfBytesRead
0x18000148f  mov     r8d, ebx; nNumberOfBytesToRead
0x180001492  mov     dword ptr [rsp+68h+dwBytes], 0
0x18000149d  mov     rdx, rsi; lpBuffer
0x1800014a0  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800014a9  call    cs:__imp_ReadFile
0x1800014af  test    eax, eax
0x1800014b1  jz      short loc_180001521
0x1800014b3  cmp     dword ptr [rsp+68h+dwBytes], ebx
0x1800014ba  jnz     short loc_180001521
0x1800014bc  mov     edx, [r15]
0x1800014bf  xor     r9d, r9d; dwMoveMethod
0x1800014c2  mov     rcx, [rdi+58h]; hFile
0x1800014c6  and     edx, r14d
0x1800014c9  add     edx, [rsp+68h+arg_20]; lDistanceToMove
0x1800014d0  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800014d3  call    cs:__imp_SetFilePointer
0x1800014d9  cmp     eax, ebp
0x1800014db  jz      short loc_180001521
0x1800014dd  mov     rcx, [rdi+58h]; hFile
0x1800014e1  lea     r9, [rsp+68h+dwBytes]; lpNumberOfBytesWritten
0x1800014e9  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800014ec  mov     dword ptr [rsp+68h+dwBytes], 0
0x1800014f7  mov     rdx, rsi; lpBuffer
0x1800014fa  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180001503  call    cs:__imp_WriteFile
0x180001509  test    eax, eax
0x18000150b  jz      short loc_18000151A
0x18000150d  cmp     dword ptr [rsp+68h+dwBytes], ebx
0x180001514  jnz     short loc_18000151A
0x180001516  xor     ebx, ebx
0x180001518  jmp     short loc_180001526
0x18000151a  mov     ebx, 15Dh
0x18000151f  jmp     short loc_180001526
0x180001521  mov     ebx, 15Ch
0x180001526  mov     rcx, rsi; hMem
0x180001529  call    cs:__imp_GlobalFree
0x18000152f  test    ebx, ebx
0x180001531  jnz     short loc_18000153D
0x180001533  lea     eax, [rbx+1]
0x180001536  jmp     short loc_180001545
0x180001538  mov     ebx, 108h
0x18000153d  mov     [rdi+8Ch], ebx
0x180001543  xor     eax, eax
0x180001545  add     rsp, 38h
0x180001549  pop     r15
0x18000154b  pop     r14
0x18000154d  pop     rdi
0x18000154e  pop     rsi
0x18000154f  pop     rbp
0x180001550  pop     rbx
0x180001551  retn
```
