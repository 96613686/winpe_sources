# ILOG_FILE::PositionToEOF(_ULARGE_INTEGER *)

- ea: `0x18000d424`
- end: `0x18000d592`
- name: `?PositionToEOF@ILOG_FILE@@AEAAHPEAT_ULARGE_INTEGER@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(ILOG_FILE *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d2f8`

## callees

- `0x18000d424`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d467`
- `KERNEL32!GetLastError` at `0x18000d4ca`
- `KERNEL32!GetLastError` at `0x18000d52e`
- `KERNEL32!GetLastError` at `0x18000d569`
- `KERNEL32!GetLastError` at `0x18000d467`
- `KERNEL32!GetLastError` at `0x18000d4ca`
- `KERNEL32!GetLastError` at `0x18000d52e`
- `KERNEL32!GetLastError` at `0x18000d569`
- `KERNEL32!GetFileSize` at `0x18000d453`
- `KERNEL32!GetFileSize` at `0x18000d453`
- `KERNEL32!SetFilePointer` at `0x18000d4bf`
- `KERNEL32!SetFilePointer` at `0x18000d523`
- `KERNEL32!SetFilePointer` at `0x18000d55e`
- `KERNEL32!SetFilePointer` at `0x18000d4bf`
- `KERNEL32!SetFilePointer` at `0x18000d523`
- `KERNEL32!SetFilePointer` at `0x18000d55e`
- `KERNEL32!ReadFile` at `0x18000d4eb`
- `KERNEL32!ReadFile` at `0x18000d4eb`

## pseudocode

```c
__int64 __fastcall ILOG_FILE::PositionToEOF(HANDLE *this, union _ULARGE_INTEGER *a2)
{
  DWORD FileSize; // eax
  unsigned int v5; // esi
  unsigned __int64 v6; // rbx
  ULONGLONG v7; // rdi
  HANDLE v8; // rcx
  LONG v9; // edx
  HANDLE v11; // rcx
  LONG lDistanceToMove[2]; // [rsp+30h] [rbp-20h] BYREF
  ULONGLONG v13; // [rsp+38h] [rbp-18h] BYREF
  LONG v14[2]; // [rsp+40h] [rbp-10h] BYREF
  char Buffer; // [rsp+90h] [rbp+40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+50h] BYREF
  ULONGLONG FileSizeHigh; // [rsp+A8h] [rbp+58h] BYREF

  *(_QWORD *)v14 = 0;
  FileSizeHigh = 0;
  FileSize = GetFileSize(*this, (LPDWORD)&FileSizeHigh + 1);
  LODWORD(FileSizeHigh) = FileSize;
  if ( FileSize == -1 )
  {
    v5 = 0;
    if ( GetLastError() )
      return v5;
    FileSize = FileSizeHigh;
  }
  if ( FileSize && !(FileSize % *((_DWORD *)this + 5)) )
  {
    v5 = 1;
    Buffer = 0;
    v6 = 0;
    NumberOfBytesRead = 0;
    *(_QWORD *)lDistanceToMove = FileSizeHigh;
    v7 = FileSizeHigh - 1;
    while ( 1 )
    {
      v8 = *this;
      v13 = v6 + ((v7 - v6) >> 1);
      if ( SetFilePointer(v8, v13, (PLONG)&v13 + 1, 0) == -1 )
      {
        if ( GetLastError() )
          break;
      }
      if ( !ReadFile(*this, &Buffer, 1u, &NumberOfBytesRead, 0) )
        break;
      if ( Buffer )
      {
        v9 = lDistanceToMove[0];
        v6 = v13 + 1;
      }
      else
      {
        v9 = v13;
        *(_QWORD *)lDistanceToMove = v13;
        v7 = v13 - 1;
      }
      if ( v6 > v7 )
      {
        if ( SetFilePointer(*this, v9, &lDistanceToMove[1], 0) != -1 || !GetLastError() )
        {
          *a2 = *(union _ULARGE_INTEGER *)lDistanceToMove;
          return v5;
        }
        return 0;
      }
    }
    return 0;
  }
  v11 = *this;
  *(_QWORD *)v14 = 0;
  if ( SetFilePointer(v11, 0, &v14[1], 2u) == -1 && GetLastError() )
    return 0;
  a2->QuadPart = FileSizeHigh;
  return 1;
}

```

## disassembly

```asm
0x18000d424  push    rbp
0x18000d426  push    rbx
0x18000d427  push    rsi
0x18000d428  push    rdi
0x18000d429  push    r13
0x18000d42b  push    r14
0x18000d42d  push    r15
0x18000d42f  mov     rbp, rsp
0x18000d432  sub     rsp, 50h
0x18000d436  mov     r15, rdx
0x18000d439  mov     qword ptr [rbp+var_10], 0
0x18000d441  mov     r14, rcx
0x18000d444  mov     [rbp+FileSizeHigh], 0
0x18000d44c  mov     rcx, [rcx]; hFile
0x18000d44f  lea     rdx, [rbp+FileSizeHigh+4]; lpFileSizeHigh
0x18000d453  call    cs:__imp_GetFileSize
0x18000d459  or      r13d, 0FFFFFFFFh
0x18000d45d  mov     dword ptr [rbp+FileSizeHigh], eax
0x18000d460  cmp     eax, r13d
0x18000d463  jnz     short loc_18000D478
0x18000d465  xor     esi, esi
0x18000d467  call    cs:__imp_GetLastError
0x18000d46d  test    eax, eax
0x18000d46f  jnz     loc_18000D543
0x18000d475  mov     eax, dword ptr [rbp+FileSizeHigh]
0x18000d478  test    eax, eax
0x18000d47a  jz      loc_18000D547
0x18000d480  xor     edx, edx
0x18000d482  div     dword ptr [r14+14h]
0x18000d486  test    edx, edx
0x18000d488  jnz     loc_18000D547
0x18000d48e  mov     rax, [rbp+FileSizeHigh]
0x18000d492  lea     esi, [rdx+1]
0x18000d495  mov     [rbp+Buffer], dl
0x18000d498  xor     ebx, ebx
0x18000d49a  mov     [rbp+NumberOfBytesRead], edx
0x18000d49d  mov     qword ptr [rbp+lDistanceToMove], rax
0x18000d4a1  lea     rdi, [rax-1]
0x18000d4a5  mov     rcx, [r14]; hFile
0x18000d4a8  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18000d4ac  mov     rdx, rdi
0x18000d4af  xor     r9d, r9d; dwMoveMethod
0x18000d4b2  sub     rdx, rbx
0x18000d4b5  shr     rdx, 1
0x18000d4b8  add     rdx, rbx; lDistanceToMove
0x18000d4bb  mov     [rbp-18h], rdx
0x18000d4bf  call    cs:__imp_SetFilePointer
0x18000d4c5  cmp     eax, r13d
0x18000d4c8  jnz     short loc_18000D4D4
0x18000d4ca  call    cs:__imp_GetLastError
0x18000d4d0  test    eax, eax
0x18000d4d2  jnz     short loc_18000D541
0x18000d4d4  mov     rcx, [r14]; hFile
0x18000d4d7  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d4db  mov     r8d, esi; nNumberOfBytesToRead
0x18000d4de  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18000d4e7  lea     rdx, [rbp+Buffer]; lpBuffer
0x18000d4eb  call    cs:__imp_ReadFile
0x18000d4f1  test    eax, eax
0x18000d4f3  jz      short loc_18000D541
0x18000d4f5  cmp     [rbp+Buffer], 0
0x18000d4f9  jnz     short loc_18000D509
0x18000d4fb  mov     rdx, [rbp-18h]
0x18000d4ff  mov     qword ptr [rbp+lDistanceToMove], rdx
0x18000d503  lea     rdi, [rdx-1]
0x18000d507  jmp     short loc_18000D514
0x18000d509  mov     rbx, [rbp-18h]
0x18000d50d  mov     rdx, qword ptr [rbp+lDistanceToMove]; lDistanceToMove
0x18000d511  inc     rbx
0x18000d514  cmp     rbx, rdi
0x18000d517  jbe     short loc_18000D4A5
0x18000d519  mov     rcx, [r14]; hFile
0x18000d51c  lea     r8, [rbp+lDistanceToMove+4]; lpDistanceToMoveHigh
0x18000d520  xor     r9d, r9d; dwMoveMethod
0x18000d523  call    cs:__imp_SetFilePointer
0x18000d529  cmp     eax, r13d
0x18000d52c  jnz     short loc_18000D538
0x18000d52e  call    cs:__imp_GetLastError
0x18000d534  test    eax, eax
0x18000d536  jnz     short loc_18000D541
0x18000d538  mov     rax, qword ptr [rbp+lDistanceToMove]
0x18000d53c  mov     [r15], rax
0x18000d53f  jmp     short loc_18000D543
0x18000d541  xor     esi, esi
0x18000d543  mov     eax, esi
0x18000d545  jmp     short loc_18000D583
0x18000d547  mov     rcx, [r14]; hFile
0x18000d54a  lea     r8, [rbp+var_10+4]; lpDistanceToMoveHigh
0x18000d54e  mov     r9d, 2; dwMoveMethod
0x18000d554  mov     qword ptr [rbp+var_10], 0
0x18000d55c  xor     edx, edx; lDistanceToMove
0x18000d55e  call    cs:__imp_SetFilePointer
0x18000d564  cmp     eax, r13d
0x18000d567  jnz     short loc_18000D577
0x18000d569  call    cs:__imp_GetLastError
0x18000d56f  test    eax, eax
0x18000d571  jz      short loc_18000D577
0x18000d573  xor     eax, eax
0x18000d575  jmp     short loc_18000D583
0x18000d577  mov     rax, [rbp+FileSizeHigh]
0x18000d57b  mov     [r15], rax
0x18000d57e  mov     eax, 1
0x18000d583  add     rsp, 50h
0x18000d587  pop     r15
0x18000d589  pop     r14
0x18000d58b  pop     r13
0x18000d58d  pop     rdi
0x18000d58e  pop     rsi
0x18000d58f  pop     rbx
0x18000d590  pop     rbp
0x18000d591  retn
```
