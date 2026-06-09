# PuZeroSector(void *,ulong,unsigned __int64)

- ea: `0x1801a4888`
- end: `0x1801a492f`
- name: `?PuZeroSector@@YAHPEAXK_K@Z`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD nNumberOfBytesToWrite, LARGE_INTEGER liDistanceToMove)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180196f6c`
- `0x1801a481c`

## callees

- `0x1801a4888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a491c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a491c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a490f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a490f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a48a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a48fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a48a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a48fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a48b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a48b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a48f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a48f4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801a48d1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801a48d1`

## pseudocode

```c
__int64 __fastcall PuZeroSector(HANDLE hFile, DWORD nNumberOfBytesToWrite, LARGE_INTEGER liDistanceToMove)
{
  HANDLE ProcessHeap; // rax
  void *v7; // rdi
  unsigned int v8; // ebx
  HANDLE v9; // rax
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  ProcessHeap = GetProcessHeap();
  if ( ProcessHeap && (v7 = HeapAlloc(ProcessHeap, 8u, nNumberOfBytesToWrite)) != 0 )
  {
    v8 = SetFilePointerEx(hFile, liDistanceToMove, 0, 0);
    if ( v8 )
      v8 = WriteFile(hFile, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
    v9 = GetProcessHeap();
    if ( v9 )
      HeapFree(v9, 0, v7);
  }
  else
  {
    SetLastError(8u);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1801a4888  push    rbx
0x1801a488a  push    rbp
0x1801a488b  push    rsi
0x1801a488c  push    rdi
0x1801a488d  sub     rsp, 38h
0x1801a4891  mov     rbx, r8
0x1801a4894  mov     esi, edx
0x1801a4896  mov     rbp, rcx
0x1801a4899  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1801a48a1  call    cs:__imp_GetProcessHeap
0x1801a48a7  test    rax, rax
0x1801a48aa  jz      short loc_1801A4917
0x1801a48ac  mov     r8d, esi; dwBytes
0x1801a48af  mov     edx, 8; dwFlags
0x1801a48b4  mov     rcx, rax; hHeap
0x1801a48b7  call    cs:__imp_HeapAlloc
0x1801a48bd  mov     rdi, rax
0x1801a48c0  test    rax, rax
0x1801a48c3  jz      short loc_1801A4917
0x1801a48c5  xor     r9d, r9d; dwMoveMethod
0x1801a48c8  xor     r8d, r8d; lpNewFilePointer
0x1801a48cb  mov     rdx, rbx; liDistanceToMove
0x1801a48ce  mov     rcx, rbp; hFile
0x1801a48d1  call    cs:__imp_SetFilePointerEx
0x1801a48d7  mov     ebx, eax
0x1801a48d9  test    eax, eax
0x1801a48db  jz      short loc_1801A48FC
0x1801a48dd  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801a48e2  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1801a48eb  mov     r8d, esi; nNumberOfBytesToWrite
0x1801a48ee  mov     rdx, rdi; lpBuffer
0x1801a48f1  mov     rcx, rbp; hFile
0x1801a48f4  call    cs:__imp_WriteFile
0x1801a48fa  mov     ebx, eax
0x1801a48fc  call    cs:__imp_GetProcessHeap
0x1801a4902  test    rax, rax
0x1801a4905  jz      short loc_1801A4924
0x1801a4907  mov     r8, rdi; lpMem
0x1801a490a  xor     edx, edx; dwFlags
0x1801a490c  mov     rcx, rax; hHeap
0x1801a490f  call    cs:__imp_HeapFree
0x1801a4915  jmp     short loc_1801A4924
0x1801a4917  mov     ecx, 8; dwErrCode
0x1801a491c  call    cs:__imp_SetLastError
0x1801a4922  xor     ebx, ebx
0x1801a4924  mov     eax, ebx
0x1801a4926  add     rsp, 38h
0x1801a492a  pop     rdi
0x1801a492b  pop     rsi
0x1801a492c  pop     rbp
0x1801a492d  pop     rbx
0x1801a492e  retn
```
