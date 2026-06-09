# BackupWriteStream

- ea: `0x18006a5a0`
- end: `0x18006a6c9`
- name: `BackupWriteStream`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180054428`
- `0x180069e20`

## callees

- `0x180030d34`
- `0x18006a5a0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18006a620`
- `ntdll!NtFsControlFile` at `0x18006a620`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006a641`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006a641`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a638`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a65b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a638`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a65b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006a69d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006a69d`

## pseudocode

```c
int __fastcall BackupWriteStream(HANDLE hFile, __int64 a2, __int64 a3)
{
  bool v3; // zf
  int result; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-10h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+88h] [rbp+28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+30h] BYREF
  __int64 DistanceToMoveHigh; // [rsp+98h] [rbp+38h] BYREF

  v3 = *(_BYTE *)(a2 + 1129) == 0;
  IoStatusBlock = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  DistanceToMoveHigh = 0;
  if ( !v3 )
  {
    if ( (*(_BYTE *)(a2 + 4) & 8) != 0 )
      NtFsControlFile(hFile, 0, 0, 0, &IoStatusBlock, 0x900C4u, 0, 0, 0, 0);
    DistanceToMoveHigh = *(_QWORD *)(a2 + 8);
    SetFilePointer(hFile, DistanceToMoveHigh, (PLONG)&DistanceToMoveHigh + 1, 0);
    SetEndOfFile(hFile);
    DistanceToMoveHigh = 0;
    SetFilePointer(hFile, 0, (PLONG)&DistanceToMoveHigh + 1, 0);
    *(_BYTE *)(a2 + 1129) = 0;
  }
  result = ComputeRequestSize(a2, *(unsigned int *)(a3 + 16), &nNumberOfBytesToWrite);
  if ( result )
  {
    if ( nNumberOfBytesToWrite )
    {
      result = WriteFile(hFile, *(LPCVOID *)a3, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      v8 = NumberOfBytesWritten;
      *(_QWORD *)(a2 + 1056) += NumberOfBytesWritten;
      v9 = *(_DWORD **)(a3 + 8);
      *(_DWORD *)(a3 + 16) -= v8;
      *v9 += v8;
      *(_QWORD *)a3 += v8;
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006a5a0  mov     rax, rsp
0x18006a5a3  mov     [rax+8], rbx
0x18006a5a7  push    rbp
0x18006a5a8  push    rsi
0x18006a5a9  push    rdi
0x18006a5aa  mov     rbp, rsp
0x18006a5ad  sub     rsp, 60h
0x18006a5b1  cmp     byte ptr [rdx+469h], 0
0x18006a5b8  xorps   xmm0, xmm0
0x18006a5bb  movups  xmmword ptr [rbp+var_10], xmm0
0x18006a5bf  mov     rdi, r8
0x18006a5c2  mov     [rbp+nNumberOfBytesToWrite], 0
0x18006a5c9  mov     rbx, rdx
0x18006a5cc  mov     [rbp+NumberOfBytesWritten], 0
0x18006a5d3  mov     rsi, rcx
0x18006a5d6  mov     qword ptr [rbp+DistanceToMoveHigh], 0
0x18006a5de  jz      loc_18006A668
0x18006a5e4  test    byte ptr [rdx+4], 8
0x18006a5e8  jz      short loc_18006A626
0x18006a5ea  mov     dword ptr [rax-30h], 0
0x18006a5f1  xor     r9d, r9d; ApcContext
0x18006a5f4  mov     qword ptr [rax-38h], 0
0x18006a5fc  xor     r8d, r8d; ApcRoutine
0x18006a5ff  mov     dword ptr [rax-40h], 0
0x18006a606  xor     edx, edx; Event
0x18006a608  mov     qword ptr [rax-48h], 0
0x18006a610  mov     dword ptr [rax-50h], 900C4h
0x18006a617  lea     rax, [rbp+var_10]
0x18006a61b  mov     [rsp+60h+IoStatusBlock], rax; IoStatusBlock
0x18006a620  call    cs:__imp_NtFsControlFile
0x18006a626  mov     rdx, [rbx+8]; lDistanceToMove
0x18006a62a  lea     r8, [rbp+arg_1C]; lpDistanceToMoveHigh
0x18006a62e  xor     r9d, r9d; dwMoveMethod
0x18006a631  mov     qword ptr [rbp+DistanceToMoveHigh], rdx
0x18006a635  mov     rcx, rsi; hFile
0x18006a638  call    cs:__imp_SetFilePointer
0x18006a63e  mov     rcx, rsi; hFile
0x18006a641  call    cs:__imp_SetEndOfFile
0x18006a647  xor     r9d, r9d; dwMoveMethod
0x18006a64a  mov     qword ptr [rbp+DistanceToMoveHigh], 0
0x18006a652  lea     r8, [rbp+arg_1C]; lpDistanceToMoveHigh
0x18006a656  xor     edx, edx; lDistanceToMove
0x18006a658  mov     rcx, rsi; hFile
0x18006a65b  call    cs:__imp_SetFilePointer
0x18006a661  mov     byte ptr [rbx+469h], 0
0x18006a668  mov     edx, [rdi+10h]
0x18006a66b  lea     r8, [rbp+nNumberOfBytesToWrite]
0x18006a66f  mov     rcx, rbx
0x18006a672  call    ComputeRequestSize
0x18006a677  test    eax, eax
0x18006a679  jz      short loc_18006A6B9
0x18006a67b  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18006a67f  test    r8d, r8d
0x18006a682  jnz     short loc_18006A68A
0x18006a684  lea     eax, [r8+1]
0x18006a688  jmp     short loc_18006A6B9
0x18006a68a  mov     rdx, [rdi]; lpBuffer
0x18006a68d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006a691  mov     rcx, rsi; hFile
0x18006a694  mov     [rsp+60h+IoStatusBlock], 0; lpOverlapped
0x18006a69d  call    cs:__imp_WriteFile
0x18006a6a3  mov     edx, [rbp+NumberOfBytesWritten]
0x18006a6a6  add     [rbx+420h], rdx
0x18006a6ad  mov     rcx, [rdi+8]
0x18006a6b1  sub     [rdi+10h], edx
0x18006a6b4  add     [rcx], edx
0x18006a6b6  add     [rdi], rdx
0x18006a6b9  mov     rbx, [rsp+60h+arg_0]
0x18006a6c1  add     rsp, 60h
0x18006a6c5  pop     rdi
0x18006a6c6  pop     rsi
0x18006a6c7  pop     rbp
0x18006a6c8  retn
```
