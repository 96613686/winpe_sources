# FileStream::Read(void *,ulong,ulong *)

- ea: `0x1800db9b0`
- end: `0x1800dbaee`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `318`
- prototype: `int(FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800db9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db9ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800db9ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dba75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dba75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dba98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dba98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbab4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800dba14`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800dba14`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800dba40`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800dba40`

## pseudocode

```c
__int64 __fastcall FileStream::Read(FileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v8; // rcx
  signed int v9; // ebx
  DWORD v10; // eax
  signed int LastError; // eax
  signed int v13; // eax
  LONG lDistanceToMove; // [rsp+30h] [rbp-48h]
  LONG DistanceToMoveHigh; // [rsp+34h] [rbp-44h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  lDistanceToMove = *((_DWORD *)this + 22);
  DistanceToMoveHigh = *((_DWORD *)this + 23);
  if ( DistanceToMoveHigh < 0 )
    return 2147649733LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v8 = (void *)*((_QWORD *)this + 9);
  if ( v8 == (void *)-1LL )
  {
    v9 = -2147286782;
  }
  else
  {
    v9 = 0;
    if ( SetFilePointer(v8, lDistanceToMove, &DistanceToMoveHigh, 0) != -1 )
      goto LABEL_15;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
    {
LABEL_15:
      if ( ReadFile(*((HANDLE *)this + 9), a2, a3, &NumberOfBytesRead, 0) )
        goto LABEL_5;
      v13 = GetLastError();
      v9 = v13;
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      if ( v9 >= 0 )
      {
LABEL_5:
        v10 = NumberOfBytesRead;
        v16 = NumberOfBytesRead;
        *((_QWORD *)this + 11) += NumberOfBytesRead;
        if ( a4 )
          *a4 = v10;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800db9b0  mov     rax, rsp
0x1800db9b3  push    rbx
0x1800db9b4  push    rbp
0x1800db9b5  push    rsi
0x1800db9b6  push    rdi
0x1800db9b7  push    r14
0x1800db9b9  push    r15
0x1800db9bb  sub     rsp, 48h
0x1800db9bf  mov     dword ptr [rax+8], 0
0x1800db9c6  mov     rsi, r9
0x1800db9c9  mov     eax, [rcx+58h]
0x1800db9cc  mov     r14d, r8d
0x1800db9cf  mov     [rsp+78h+lDistanceToMove], eax
0x1800db9d3  mov     r15, rdx
0x1800db9d6  mov     eax, [rcx+5Ch]
0x1800db9d9  mov     rdi, rcx
0x1800db9dc  mov     [rsp+78h+DistanceToMoveHigh], eax
0x1800db9e0  test    eax, eax
0x1800db9e2  js      loc_1800DBA91
0x1800db9e8  add     rcx, 8; lpCriticalSection
0x1800db9ec  call    cs:__imp_EnterCriticalSection
0x1800db9f3  nop     dword ptr [rax+rax+00h]
0x1800db9f8  mov     rcx, [rdi+48h]; hFile
0x1800db9fc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dba00  jz      loc_1800DBAD8
0x1800dba06  mov     edx, [rsp+78h+lDistanceToMove]; lDistanceToMove
0x1800dba0a  lea     r8, [rsp+78h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800dba0f  xor     r9d, r9d; dwMoveMethod
0x1800dba12  xor     ebx, ebx
0x1800dba14  call    cs:__imp_SetFilePointer
0x1800dba1b  nop     dword ptr [rax+rax+00h]
0x1800dba20  cmp     eax, 0FFFFFFFFh
0x1800dba23  jz      short loc_1800DBA98
0x1800dba25  mov     rcx, [rdi+48h]; hFile
0x1800dba29  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800dba31  mov     r8d, r14d; nNumberOfBytesToRead
0x1800dba34  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800dba3d  mov     rdx, r15; lpBuffer
0x1800dba40  call    cs:__imp_ReadFile
0x1800dba47  nop     dword ptr [rax+rax+00h]
0x1800dba4c  test    eax, eax
0x1800dba4e  jz      short loc_1800DBAB4
0x1800dba50  mov     eax, [rsp+78h+NumberOfBytesRead]
0x1800dba57  mov     dword ptr [rsp+78h+var_40], eax
0x1800dba5b  mov     dword ptr [rsp+78h+var_40+4], 0
0x1800dba63  mov     rdx, [rsp+78h+var_40]
0x1800dba68  add     [rdi+58h], rdx
0x1800dba6c  test    rsi, rsi
0x1800dba6f  jnz     short loc_1800DBAEA
0x1800dba71  lea     rcx, [rdi+8]; lpCriticalSection
0x1800dba75  call    cs:__imp_LeaveCriticalSection
0x1800dba7c  nop     dword ptr [rax+rax+00h]
0x1800dba81  mov     eax, ebx
0x1800dba83  add     rsp, 48h
0x1800dba87  pop     r15
0x1800dba89  pop     r14
0x1800dba8b  pop     rdi
0x1800dba8c  pop     rsi
0x1800dba8d  pop     rbp
0x1800dba8e  pop     rbx
0x1800dba8f  retn
0x1800dba91  mov     eax, 800288C5h
0x1800dba96  jmp     short loc_1800DBA83
0x1800dba98  call    cs:__imp_GetLastError
0x1800dba9f  nop     dword ptr [rax+rax+00h]
0x1800dbaa4  mov     ebx, eax
0x1800dbaa6  test    eax, eax
0x1800dbaa8  jg      short loc_1800DBADF
0x1800dbaaa  test    ebx, ebx
0x1800dbaac  jns     loc_1800DBA25
0x1800dbab2  jmp     short loc_1800DBA71
0x1800dbab4  call    cs:__imp_GetLastError
0x1800dbabb  nop     dword ptr [rax+rax+00h]
0x1800dbac0  mov     ebx, eax
0x1800dbac2  test    eax, eax
0x1800dbac4  jle     short loc_1800DBACF
0x1800dbac6  movzx   ebx, ax
0x1800dbac9  or      ebx, 80070000h
0x1800dbacf  test    ebx, ebx
0x1800dbad1  js      short loc_1800DBA71
0x1800dbad3  jmp     loc_1800DBA50
0x1800dbad8  mov     ebx, 80030102h
0x1800dbadd  jmp     short loc_1800DBA71
0x1800dbadf  movzx   ebx, ax
0x1800dbae2  or      ebx, 80070000h
0x1800dbae8  jmp     short loc_1800DBAAA
0x1800dbaea  mov     [rsi], eax
0x1800dbaec  jmp     short loc_1800DBA71
```
