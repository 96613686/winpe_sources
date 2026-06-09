# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x180133a80`
- end: `0x180133bad`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `301`
- prototype: `int(FileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180133a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180133ac2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180133ac2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133b91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180133b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133b4b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180133af0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180133af0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180133b3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180133b3b`

## pseudocode

```c
__int64 __fastcall FileStream::Write(FileStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  void *v9; // rcx
  signed int v10; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  DWORD v13; // eax
  LONG lDistanceToMove; // [rsp+30h] [rbp-48h]
  LONG DistanceToMoveHigh; // [rsp+34h] [rbp-44h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  lDistanceToMove = *((_DWORD *)this + 22);
  DistanceToMoveHigh = *((_DWORD *)this + 23);
  if ( DistanceToMoveHigh < 0 )
    return 2147649733LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v9 = (void *)*((_QWORD *)this + 9);
  if ( v9 == (void *)-1LL )
  {
    v10 = -2147286782;
  }
  else
  {
    v10 = 0;
    if ( SetFilePointer(v9, lDistanceToMove, &DistanceToMoveHigh, 0) != -1 )
      goto LABEL_12;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_12:
      if ( WriteFile(*((HANDLE *)this + 9), a2, a3, &NumberOfBytesWritten, 0) )
        goto LABEL_13;
      v12 = GetLastError();
      v10 = v12;
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_13:
        v13 = NumberOfBytesWritten;
        v16 = NumberOfBytesWritten;
        *((_QWORD *)this + 11) += NumberOfBytesWritten;
        if ( a4 )
          *a4 = v13;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180133a80  mov     rax, rsp
0x180133a83  push    rbx
0x180133a84  push    rbp
0x180133a85  push    rsi
0x180133a86  push    rdi
0x180133a87  push    r14
0x180133a89  push    r15
0x180133a8b  sub     rsp, 48h
0x180133a8f  mov     dword ptr [rax+8], 0
0x180133a96  mov     rsi, r9
0x180133a99  mov     eax, [rcx+58h]
0x180133a9c  mov     r14d, r8d
0x180133a9f  mov     [rsp+78h+lDistanceToMove], eax
0x180133aa3  mov     r15, rdx
0x180133aa6  mov     eax, [rcx+5Ch]
0x180133aa9  mov     rdi, rcx
0x180133aac  mov     [rsp+78h+DistanceToMoveHigh], eax
0x180133ab0  test    eax, eax
0x180133ab2  jns     short loc_180133ABE
0x180133ab4  mov     eax, 800288C5h
0x180133ab9  jmp     loc_180133B9F
0x180133abe  add     rcx, 8; lpCriticalSection
0x180133ac2  call    cs:__imp_EnterCriticalSection
0x180133ac9  nop     dword ptr [rax+rax+00h]
0x180133ace  mov     rcx, [rdi+48h]; hFile
0x180133ad2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180133ad6  jnz     short loc_180133AE2
0x180133ad8  mov     ebx, 80030102h
0x180133add  jmp     loc_180133B8D
0x180133ae2  mov     edx, [rsp+78h+lDistanceToMove]; lDistanceToMove
0x180133ae6  lea     r8, [rsp+78h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180133aeb  xor     r9d, r9d; dwMoveMethod
0x180133aee  xor     ebx, ebx
0x180133af0  call    cs:__imp_SetFilePointer
0x180133af7  nop     dword ptr [rax+rax+00h]
0x180133afc  cmp     eax, 0FFFFFFFFh
0x180133aff  jnz     short loc_180133B20
0x180133b01  call    cs:__imp_GetLastError
0x180133b08  nop     dword ptr [rax+rax+00h]
0x180133b0d  mov     ebx, eax
0x180133b0f  test    eax, eax
0x180133b11  jle     short loc_180133B1C
0x180133b13  movzx   ebx, ax
0x180133b16  or      ebx, 80070000h
0x180133b1c  test    ebx, ebx
0x180133b1e  js      short loc_180133B8D
0x180133b20  mov     rcx, [rdi+48h]; hFile
0x180133b24  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180133b2c  mov     r8d, r14d; nNumberOfBytesToWrite
0x180133b2f  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180133b38  mov     rdx, r15; lpBuffer
0x180133b3b  call    cs:__imp_WriteFile
0x180133b42  nop     dword ptr [rax+rax+00h]
0x180133b47  test    eax, eax
0x180133b49  jnz     short loc_180133B6A
0x180133b4b  call    cs:__imp_GetLastError
0x180133b52  nop     dword ptr [rax+rax+00h]
0x180133b57  mov     ebx, eax
0x180133b59  test    eax, eax
0x180133b5b  jle     short loc_180133B66
0x180133b5d  movzx   ebx, ax
0x180133b60  or      ebx, 80070000h
0x180133b66  test    ebx, ebx
0x180133b68  js      short loc_180133B8D
0x180133b6a  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x180133b71  mov     dword ptr [rsp+78h+var_40], eax
0x180133b75  mov     dword ptr [rsp+78h+var_40+4], 0
0x180133b7d  mov     rdx, [rsp+78h+var_40]
0x180133b82  add     [rdi+58h], rdx
0x180133b86  test    rsi, rsi
0x180133b89  jz      short loc_180133B8D
0x180133b8b  mov     [rsi], eax
0x180133b8d  lea     rcx, [rdi+8]; lpCriticalSection
0x180133b91  call    cs:__imp_LeaveCriticalSection
0x180133b98  nop     dword ptr [rax+rax+00h]
0x180133b9d  mov     eax, ebx
0x180133b9f  add     rsp, 48h
0x180133ba3  pop     r15
0x180133ba5  pop     r14
0x180133ba7  pop     rdi
0x180133ba8  pop     rsi
0x180133ba9  pop     rbp
0x180133baa  pop     rbx
0x180133bab  retn
```
