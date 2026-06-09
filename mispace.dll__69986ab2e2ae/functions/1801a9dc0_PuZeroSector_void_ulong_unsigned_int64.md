# PuZeroSector(void *,ulong,unsigned __int64)

- ea: `0x1801a9dc0`
- end: `0x1801a9e84`
- name: `?PuZeroSector@@YAHPEAXK_K@Z`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD nNumberOfBytesToWrite, LARGE_INTEGER liDistanceToMove)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18019ba98`
- `0x1801a9d4c`

## callees

- `0x1800298d0`
- `0x1801a9dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a9e6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a9e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9dd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9e4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9dd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9e4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a9df5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a9df5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a9e3e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a9e3e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801a9e15`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801a9e15`

## pseudocode

```c
__int64 __fastcall PuZeroSector(HANDLE hFile, DWORD nNumberOfBytesToWrite, LARGE_INTEGER liDistanceToMove)
{
  HANDLE ProcessHeap; // rax
  void *v7; // rdi
  unsigned int v8; // ebx
  HANDLE v9; // rax
  unsigned int v10; // edx
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  ProcessHeap = GetProcessHeap();
  if ( ProcessHeap && (v7 = HeapAlloc(ProcessHeap, 8u, nNumberOfBytesToWrite)) != 0 )
  {
    v8 = SetFilePointerEx(hFile, liDistanceToMove, 0, 0);
    if ( v8 )
      v8 = WriteFile(hFile, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
    v9 = GetProcessHeap();
    PmHeapFree(v9, v10, v7);
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
0x1801a9dc0  push    rbx
0x1801a9dc2  push    rbp
0x1801a9dc3  push    rsi
0x1801a9dc4  push    rdi
0x1801a9dc5  sub     rsp, 38h
0x1801a9dc9  mov     rbx, r8
0x1801a9dcc  mov     esi, edx
0x1801a9dce  mov     rbp, rcx
0x1801a9dd1  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1801a9dd9  call    cs:__imp_GetProcessHeap
0x1801a9de0  nop     dword ptr [rax+rax+00h]
0x1801a9de5  test    rax, rax
0x1801a9de8  jz      short loc_1801A9E65
0x1801a9dea  mov     r8d, esi; dwBytes
0x1801a9ded  mov     edx, 8; dwFlags
0x1801a9df2  mov     rcx, rax; hHeap
0x1801a9df5  call    cs:__imp_HeapAlloc
0x1801a9dfc  nop     dword ptr [rax+rax+00h]
0x1801a9e01  mov     rdi, rax
0x1801a9e04  test    rax, rax
0x1801a9e07  jz      short loc_1801A9E65
0x1801a9e09  xor     r9d, r9d; dwMoveMethod
0x1801a9e0c  xor     r8d, r8d; lpNewFilePointer
0x1801a9e0f  mov     rdx, rbx; liDistanceToMove
0x1801a9e12  mov     rcx, rbp; hFile
0x1801a9e15  call    cs:__imp_SetFilePointerEx
0x1801a9e1c  nop     dword ptr [rax+rax+00h]
0x1801a9e21  mov     ebx, eax
0x1801a9e23  test    eax, eax
0x1801a9e25  jz      short loc_1801A9E4C
0x1801a9e27  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801a9e2c  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1801a9e35  mov     r8d, esi; nNumberOfBytesToWrite
0x1801a9e38  mov     rdx, rdi; lpBuffer
0x1801a9e3b  mov     rcx, rbp; hFile
0x1801a9e3e  call    cs:__imp_WriteFile
0x1801a9e45  nop     dword ptr [rax+rax+00h]
0x1801a9e4a  mov     ebx, eax
0x1801a9e4c  call    cs:__imp_GetProcessHeap
0x1801a9e53  nop     dword ptr [rax+rax+00h]
0x1801a9e58  mov     rcx, rax; void *
0x1801a9e5b  mov     r8, rdi; void *
0x1801a9e5e  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a9e63  jmp     short loc_1801A9E78
0x1801a9e65  mov     ecx, 8; dwErrCode
0x1801a9e6a  call    cs:__imp_SetLastError
0x1801a9e71  nop     dword ptr [rax+rax+00h]
0x1801a9e76  xor     ebx, ebx
0x1801a9e78  mov     eax, ebx
0x1801a9e7a  add     rsp, 38h
0x1801a9e7e  pop     rdi
0x1801a9e7f  pop     rsi
0x1801a9e80  pop     rbp
0x1801a9e81  pop     rbx
0x1801a9e82  retn
```
