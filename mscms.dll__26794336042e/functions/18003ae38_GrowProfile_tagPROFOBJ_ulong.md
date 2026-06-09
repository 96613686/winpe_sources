# GrowProfile(tagPROFOBJ *,ulong)

- ea: `0x18003ae38`
- end: `0x18003af03`
- name: `?GrowProfile@@YAHPEAUtagPROFOBJ@@K@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct tagPROFOBJ *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x18003a6fc`
- `0x18003c6b0`
- `0x18003c820`

## callees

- `0x18003ae38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aed1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aed1`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18003aee5`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18003aee5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003ae91`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003ae91`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003aeb7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003aeb7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003ae67`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003ae67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ae71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ae71`

## pseudocode

```c
__int64 __fastcall GrowProfile(struct tagPROFOBJ *a1, unsigned int a2)
{
  DWORD dwMaximumSizeLow; // esi
  void *v5; // rbp
  HANDLE FileMappingW; // rax
  LPVOID v7; // rax
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax

  if ( *((_DWORD *)a1 + 12) >= a2 )
    return 1;
  dwMaximumSizeLow = a2 + 0x4000;
  if ( a2 + 0x4000 >= a2 )
  {
    v5 = (void *)*((_QWORD *)a1 + 7);
    if ( (*((_BYTE *)a1 + 28) & 1) != 0 )
    {
      UnmapViewOfFile(*((LPCVOID *)a1 + 7));
      CloseHandle(*((HANDLE *)a1 + 5));
      FileMappingW = CreateFileMappingW(*((HANDLE *)a1 + 4), 0, 4u, 0, dwMaximumSizeLow, 0);
      *((_QWORD *)a1 + 5) = FileMappingW;
      if ( !FileMappingW )
        return 0;
      v7 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      *((_QWORD *)a1 + 7) = v7;
      if ( !v7 )
        return 0;
LABEL_10:
      *((_DWORD *)a1 + 12) = dwMaximumSizeLow;
      return 1;
    }
    ProcessHeap = GetProcessHeap();
    v9 = HeapReAlloc(ProcessHeap, 8u, v5, dwMaximumSizeLow);
    if ( v9 )
    {
      *((_QWORD *)a1 + 2) = v9;
      *((_QWORD *)a1 + 7) = v9;
      *((_DWORD *)a1 + 6) = dwMaximumSizeLow;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003ae38  push    rbx
0x18003ae3a  push    rbp
0x18003ae3b  push    rsi
0x18003ae3c  push    rdi
0x18003ae3d  sub     rsp, 38h
0x18003ae41  mov     rdi, rcx
0x18003ae44  cmp     [rcx+30h], edx
0x18003ae47  jb      short loc_18003AE50
0x18003ae49  mov     eax, 1
0x18003ae4e  jmp     short loc_18003AEC8
0x18003ae50  lea     esi, [rdx+4000h]
0x18003ae56  cmp     esi, edx
0x18003ae58  jb      short loc_18003AEC6
0x18003ae5a  test    byte ptr [rcx+1Ch], 1
0x18003ae5e  mov     rbp, [rcx+38h]
0x18003ae62  jz      short loc_18003AED1
0x18003ae64  mov     rcx, rbp; lpBaseAddress
0x18003ae67  call    cs:__imp_UnmapViewOfFile
0x18003ae6d  mov     rcx, [rdi+28h]; hObject
0x18003ae71  call    cs:__imp_CloseHandle
0x18003ae77  mov     rcx, [rdi+20h]; hFile
0x18003ae7b  xor     r9d, r9d; dwMaximumSizeHigh
0x18003ae7e  mov     [rsp+58h+lpName], 0; lpName
0x18003ae87  xor     edx, edx; lpFileMappingAttributes
0x18003ae89  mov     [rsp+58h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18003ae8d  lea     r8d, [r9+4]; flProtect
0x18003ae91  call    cs:__imp_CreateFileMappingW
0x18003ae97  mov     [rdi+28h], rax
0x18003ae9b  test    rax, rax
0x18003ae9e  jz      short loc_18003AEC6
0x18003aea0  xor     r9d, r9d; dwFileOffsetLow
0x18003aea3  mov     qword ptr [rsp+58h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18003aeac  xor     r8d, r8d; dwFileOffsetHigh
0x18003aeaf  mov     edx, 0F001Fh; dwDesiredAccess
0x18003aeb4  mov     rcx, rax; hFileMappingObject
0x18003aeb7  call    cs:__imp_MapViewOfFile
0x18003aebd  mov     [rdi+38h], rax
0x18003aec1  test    rax, rax
0x18003aec4  jnz     short loc_18003AEFB
0x18003aec6  xor     eax, eax
0x18003aec8  add     rsp, 38h
0x18003aecc  pop     rdi
0x18003aecd  pop     rsi
0x18003aece  pop     rbp
0x18003aecf  pop     rbx
0x18003aed0  retn
0x18003aed1  call    cs:__imp_GetProcessHeap
0x18003aed7  mov     r9d, esi; dwBytes
0x18003aeda  mov     r8, rbp; lpMem
0x18003aedd  mov     rcx, rax; hHeap
0x18003aee0  mov     edx, 8; dwFlags
0x18003aee5  call    cs:__imp_HeapReAlloc
0x18003aeeb  test    rax, rax
0x18003aeee  jz      short loc_18003AEC6
0x18003aef0  mov     [rdi+10h], rax
0x18003aef4  mov     [rdi+38h], rax
0x18003aef8  mov     [rdi+18h], esi
0x18003aefb  mov     [rdi+30h], esi
0x18003aefe  jmp     loc_18003AE49
```
