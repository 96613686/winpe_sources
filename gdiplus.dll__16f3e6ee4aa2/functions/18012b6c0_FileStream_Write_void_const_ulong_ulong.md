# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x18012b6c0`
- end: `0x18012b7c8`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `264`
- prototype: `int(FileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18012b6c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012b702`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012b702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b7b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b773`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18012b72a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18012b72a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18012b769`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18012b769`

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
0x18012b6c0  mov     rax, rsp
0x18012b6c3  push    rbx
0x18012b6c4  push    rbp
0x18012b6c5  push    rsi
0x18012b6c6  push    rdi
0x18012b6c7  push    r14
0x18012b6c9  push    r15
0x18012b6cb  sub     rsp, 48h
0x18012b6cf  mov     dword ptr [rax+8], 0
0x18012b6d6  mov     rsi, r9
0x18012b6d9  mov     eax, [rcx+58h]
0x18012b6dc  mov     r14d, r8d
0x18012b6df  mov     [rsp+78h+lDistanceToMove], eax
0x18012b6e3  mov     r15, rdx
0x18012b6e6  mov     eax, [rcx+5Ch]
0x18012b6e9  mov     rdi, rcx
0x18012b6ec  mov     [rsp+78h+DistanceToMoveHigh], eax
0x18012b6f0  test    eax, eax
0x18012b6f2  jns     short loc_18012B6FE
0x18012b6f4  mov     eax, 800288C5h
0x18012b6f9  jmp     loc_18012B7BB
0x18012b6fe  add     rcx, 8; lpCriticalSection
0x18012b702  call    cs:__imp_EnterCriticalSection
0x18012b708  mov     rcx, [rdi+48h]; hFile
0x18012b70c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012b710  jnz     short loc_18012B71C
0x18012b712  mov     ebx, 80030102h
0x18012b717  jmp     loc_18012B7AF
0x18012b71c  mov     edx, [rsp+78h+lDistanceToMove]; lDistanceToMove
0x18012b720  lea     r8, [rsp+78h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18012b725  xor     r9d, r9d; dwMoveMethod
0x18012b728  xor     ebx, ebx
0x18012b72a  call    cs:__imp_SetFilePointer
0x18012b730  cmp     eax, 0FFFFFFFFh
0x18012b733  jnz     short loc_18012B74E
0x18012b735  call    cs:__imp_GetLastError
0x18012b73b  mov     ebx, eax
0x18012b73d  test    eax, eax
0x18012b73f  jle     short loc_18012B74A
0x18012b741  movzx   ebx, ax
0x18012b744  or      ebx, 80070000h
0x18012b74a  test    ebx, ebx
0x18012b74c  js      short loc_18012B7AF
0x18012b74e  mov     rcx, [rdi+48h]; hFile
0x18012b752  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18012b75a  mov     r8d, r14d; nNumberOfBytesToWrite
0x18012b75d  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18012b766  mov     rdx, r15; lpBuffer
0x18012b769  call    cs:__imp_WriteFile
0x18012b76f  test    eax, eax
0x18012b771  jnz     short loc_18012B78C
0x18012b773  call    cs:__imp_GetLastError
0x18012b779  mov     ebx, eax
0x18012b77b  test    eax, eax
0x18012b77d  jle     short loc_18012B788
0x18012b77f  movzx   ebx, ax
0x18012b782  or      ebx, 80070000h
0x18012b788  test    ebx, ebx
0x18012b78a  js      short loc_18012B7AF
0x18012b78c  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x18012b793  mov     dword ptr [rsp+78h+var_40], eax
0x18012b797  mov     dword ptr [rsp+78h+var_40+4], 0
0x18012b79f  mov     rdx, [rsp+78h+var_40]
0x18012b7a4  add     [rdi+58h], rdx
0x18012b7a8  test    rsi, rsi
0x18012b7ab  jz      short loc_18012B7AF
0x18012b7ad  mov     [rsi], eax
0x18012b7af  lea     rcx, [rdi+8]; lpCriticalSection
0x18012b7b3  call    cs:__imp_LeaveCriticalSection
0x18012b7b9  mov     eax, ebx
0x18012b7bb  add     rsp, 48h
0x18012b7bf  pop     r15
0x18012b7c1  pop     r14
0x18012b7c3  pop     rdi
0x18012b7c4  pop     rsi
0x18012b7c5  pop     rbp
0x18012b7c6  pop     rbx
0x18012b7c7  retn
```
