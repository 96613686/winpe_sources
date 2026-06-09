# PuWriteBootCode(void *,PU_DISK_PROPERTIES *)

- ea: `0x1801a984c`
- end: `0x1801a9a04`
- name: `?PuWriteBootCode@@YAKPEAXPEAVPU_DISK_PROPERTIES@@@Z`
- size: `440`
- prototype: `unsigned int __fastcall(HANDLE hFile, struct PU_DISK_PROPERTIES *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18019bf0c`
- `0x1801a4df0`

## callees

- `0x1800298d0`
- `0x1801a984c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a99cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a99cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9886`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a99dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a9886`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a99dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a98a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a98a8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a98fb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a98fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a98cb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a9991`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a98cb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a9991`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a99bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a99bf`

## pseudocode

```c
__int64 __fastcall PuWriteBootCode(HANDLE hFile, struct PU_DISK_PROPERTIES *a2)
{
  SIZE_T v2; // rdi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rdi
  _OWORD *v8; // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  __int128 v11; // xmm1
  HANDLE v12; // rax
  unsigned int v13; // edx
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+18h] BYREF

  v2 = *((unsigned int *)a2 + 40);
  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  if ( (unsigned int)v2 >= 0x200 )
  {
    ProcessHeap = GetProcessHeap();
    LastError = 8;
    if ( ProcessHeap )
    {
      v7 = HeapAlloc(ProcessHeap, 8u, v2);
      if ( v7 )
      {
        if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
          goto LABEL_11;
        if ( !ReadFile(hFile, v7, *((_DWORD *)a2 + 40), &NumberOfBytesRead, 0) )
          goto LABEL_11;
        v8 = v7;
        v9 = &x86BootCode;
        v10 = 3;
        do
        {
          *v8 = *v9;
          v8[1] = v9[1];
          v8[2] = v9[2];
          v8[3] = v9[3];
          v8[4] = v9[4];
          v8[5] = v9[5];
          v8[6] = v9[6];
          v11 = v9[7];
          v9 += 8;
          v8[7] = v11;
          v8 += 8;
          --v10;
        }
        while ( v10 );
        *v8 = *v9;
        v8[1] = v9[1];
        v8[2] = v9[2];
        *((_QWORD *)v8 + 6) = *((_QWORD *)v9 + 6);
        LastError = SetFilePointer(hFile, 0, 0, 0);
        if ( LastError == -1 || !WriteFile(hFile, v7, *((_DWORD *)a2 + 40), &NumberOfBytesWritten, 0) )
LABEL_11:
          LastError = GetLastError();
        v12 = GetProcessHeap();
        PmHeapFree(v12, v13, v7);
      }
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x1801a984c  mov     [rsp+arg_0], rbx
0x1801a9851  push    rbp
0x1801a9852  push    rsi
0x1801a9853  push    rdi
0x1801a9854  sub     rsp, 30h
0x1801a9858  mov     edi, [rdx+0A0h]
0x1801a985e  mov     rbp, rdx
0x1801a9861  mov     [rsp+48h+NumberOfBytesRead], 0
0x1801a9869  mov     rsi, rcx
0x1801a986c  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1801a9874  cmp     edi, 200h
0x1801a987a  jnb     short loc_1801A9886
0x1801a987c  mov     ebx, 57h ; 'W'
0x1801a9881  jmp     loc_1801A99F4
0x1801a9886  call    cs:__imp_GetProcessHeap
0x1801a988d  nop     dword ptr [rax+rax+00h]
0x1801a9892  mov     ebx, 8
0x1801a9897  test    rax, rax
0x1801a989a  jz      loc_1801A99F4
0x1801a98a0  mov     r8, rdi; dwBytes
0x1801a98a3  mov     edx, ebx; dwFlags
0x1801a98a5  mov     rcx, rax; hHeap
0x1801a98a8  call    cs:__imp_HeapAlloc
0x1801a98af  nop     dword ptr [rax+rax+00h]
0x1801a98b4  mov     rdi, rax
0x1801a98b7  test    rax, rax
0x1801a98ba  jz      loc_1801A99F4
0x1801a98c0  xor     r9d, r9d; dwMoveMethod
0x1801a98c3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801a98c6  xor     edx, edx; lDistanceToMove
0x1801a98c8  mov     rcx, rsi; hFile
0x1801a98cb  call    cs:__imp_SetFilePointer
0x1801a98d2  nop     dword ptr [rax+rax+00h]
0x1801a98d7  cmp     eax, 0FFFFFFFFh
0x1801a98da  jz      loc_1801A99CF
0x1801a98e0  mov     r8d, [rbp+0A0h]; nNumberOfBytesToRead
0x1801a98e7  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801a98ec  mov     rdx, rdi; lpBuffer
0x1801a98ef  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1801a98f8  mov     rcx, rsi; hFile
0x1801a98fb  call    cs:__imp_ReadFile
0x1801a9902  nop     dword ptr [rax+rax+00h]
0x1801a9907  test    eax, eax
0x1801a9909  jz      loc_1801A99CF
0x1801a990f  mov     rcx, rdi
0x1801a9912  lea     rax, ?x86BootCode@@3PAEA; uchar near * x86BootCode
0x1801a9919  lea     edx, [rbx-5]
0x1801a991c  lea     r8d, [rbx+78h]
0x1801a9920  movups  xmm0, xmmword ptr [rax]
0x1801a9923  movups  xmmword ptr [rcx], xmm0
0x1801a9926  movups  xmm1, xmmword ptr [rax+10h]
0x1801a992a  movups  xmmword ptr [rcx+10h], xmm1
0x1801a992e  movups  xmm0, xmmword ptr [rax+20h]
0x1801a9932  movups  xmmword ptr [rcx+20h], xmm0
0x1801a9936  movups  xmm1, xmmword ptr [rax+30h]
0x1801a993a  movups  xmmword ptr [rcx+30h], xmm1
0x1801a993e  movups  xmm0, xmmword ptr [rax+40h]
0x1801a9942  movups  xmmword ptr [rcx+40h], xmm0
0x1801a9946  movups  xmm1, xmmword ptr [rax+50h]
0x1801a994a  movups  xmmword ptr [rcx+50h], xmm1
0x1801a994e  movups  xmm0, xmmword ptr [rax+60h]
0x1801a9952  movups  xmmword ptr [rcx+60h], xmm0
0x1801a9956  movups  xmm1, xmmword ptr [rax+70h]
0x1801a995a  add     rax, r8
0x1801a995d  movups  xmmword ptr [rcx+70h], xmm1
0x1801a9961  add     rcx, r8
0x1801a9964  sub     rdx, 1; lDistanceToMove
0x1801a9968  jnz     short loc_1801A9920
0x1801a996a  movups  xmm0, xmmword ptr [rax]
0x1801a996d  xor     r9d, r9d; dwMoveMethod
0x1801a9970  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801a9973  movups  xmmword ptr [rcx], xmm0
0x1801a9976  movups  xmm1, xmmword ptr [rax+10h]
0x1801a997a  movups  xmmword ptr [rcx+10h], xmm1
0x1801a997e  movups  xmm0, xmmword ptr [rax+20h]
0x1801a9982  movups  xmmword ptr [rcx+20h], xmm0
0x1801a9986  mov     rax, [rax+30h]
0x1801a998a  mov     [rcx+30h], rax
0x1801a998e  mov     rcx, rsi; hFile
0x1801a9991  call    cs:__imp_SetFilePointer
0x1801a9998  nop     dword ptr [rax+rax+00h]
0x1801a999d  mov     ebx, eax
0x1801a999f  cmp     eax, 0FFFFFFFFh
0x1801a99a2  jz      short loc_1801A99CF
0x1801a99a4  mov     r8d, [rbp+0A0h]; nNumberOfBytesToWrite
0x1801a99ab  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801a99b0  mov     rdx, rdi; lpBuffer
0x1801a99b3  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1801a99bc  mov     rcx, rsi; hFile
0x1801a99bf  call    cs:__imp_WriteFile
0x1801a99c6  nop     dword ptr [rax+rax+00h]
0x1801a99cb  test    eax, eax
0x1801a99cd  jnz     short loc_1801A99DD
0x1801a99cf  call    cs:__imp_GetLastError
0x1801a99d6  nop     dword ptr [rax+rax+00h]
0x1801a99db  mov     ebx, eax
0x1801a99dd  call    cs:__imp_GetProcessHeap
0x1801a99e4  nop     dword ptr [rax+rax+00h]
0x1801a99e9  mov     rcx, rax; void *
0x1801a99ec  mov     r8, rdi; void *
0x1801a99ef  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a99f4  mov     eax, ebx
0x1801a99f6  mov     rbx, [rsp+48h+arg_0]
0x1801a99fb  add     rsp, 30h
0x1801a99ff  pop     rdi
0x1801a9a00  pop     rsi
0x1801a9a01  pop     rbp
0x1801a9a02  retn
```
