# FileStream::Read(void *,ulong,ulong *)

- ea: `0x1800c5f30`
- end: `0x1800c607f`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `335`
- prototype: `int(FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800c5f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5f72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5f72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5ff7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6054`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c5f9a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c5f9a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c5fc0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c5fc0`

## pseudocode

```c
__int64 __fastcall FileStream::Read(FileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v8; // rcx
  signed int v9; // ebx
  DWORD v10; // eax
  signed int LastError; // eax
  signed int v13; // eax
  LONG lDistanceToMove; // [rsp+30h] [rbp-28h]
  LONG DistanceToMoveHigh; // [rsp+34h] [rbp-24h] BYREF
  __int64 v16; // [rsp+38h] [rbp-20h]
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

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
      goto LABEL_16;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
    {
LABEL_16:
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
0x1800c5f30  mov     rax, rsp
0x1800c5f33  mov     [rax+10h], rbx
0x1800c5f37  mov     [rax+18h], rbp
0x1800c5f3b  mov     [rax+20h], rsi
0x1800c5f3f  push    rdi
0x1800c5f40  push    r14
0x1800c5f42  push    r15
0x1800c5f44  sub     rsp, 40h
0x1800c5f48  and     dword ptr [rax+8], 0
0x1800c5f4c  mov     rsi, r9
0x1800c5f4f  mov     eax, [rcx+58h]
0x1800c5f52  mov     r14d, r8d
0x1800c5f55  mov     [rsp+58h+lDistanceToMove], eax
0x1800c5f59  mov     r15, rdx
0x1800c5f5c  mov     eax, [rcx+5Ch]
0x1800c5f5f  mov     rdi, rcx
0x1800c5f62  mov     [rsp+58h+DistanceToMoveHigh], eax
0x1800c5f66  test    eax, eax
0x1800c5f68  js      loc_1800C601F
0x1800c5f6e  add     rcx, 8; lpCriticalSection
0x1800c5f72  call    cs:__imp_EnterCriticalSection
0x1800c5f79  nop     dword ptr [rax+rax+00h]
0x1800c5f7e  mov     rcx, [rdi+48h]; hFile
0x1800c5f82  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c5f86  jz      loc_1800C6042
0x1800c5f8c  mov     edx, [rsp+58h+lDistanceToMove]; lDistanceToMove
0x1800c5f90  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800c5f95  xor     r9d, r9d; dwMoveMethod
0x1800c5f98  xor     ebx, ebx
0x1800c5f9a  call    cs:__imp_SetFilePointer
0x1800c5fa1  nop     dword ptr [rax+rax+00h]
0x1800c5fa6  cmp     eax, 0FFFFFFFFh
0x1800c5fa9  jz      short loc_1800C6026
0x1800c5fab  mov     rcx, [rdi+48h]; hFile
0x1800c5faf  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c5fb4  and     [rsp+58h+var_38], 0
0x1800c5fba  mov     r8d, r14d; nNumberOfBytesToRead
0x1800c5fbd  mov     rdx, r15; lpBuffer
0x1800c5fc0  call    cs:__imp_ReadFile
0x1800c5fc7  nop     dword ptr [rax+rax+00h]
0x1800c5fcc  test    eax, eax
0x1800c5fce  jz      loc_1800C6054
0x1800c5fd4  and     dword ptr [rsp+58h+var_20+4], 0
0x1800c5fd9  mov     eax, [rsp+58h+NumberOfBytesRead]
0x1800c5fdd  mov     dword ptr [rsp+58h+var_20], eax
0x1800c5fe1  mov     rdx, [rsp+58h+var_20]
0x1800c5fe6  add     [rdi+58h], rdx
0x1800c5fea  test    rsi, rsi
0x1800c5fed  jnz     loc_1800C6078
0x1800c5ff3  lea     rcx, [rdi+8]; lpCriticalSection
0x1800c5ff7  call    cs:__imp_LeaveCriticalSection
0x1800c5ffe  nop     dword ptr [rax+rax+00h]
0x1800c6003  mov     eax, ebx
0x1800c6005  mov     rbx, [rsp+58h+arg_8]
0x1800c600a  mov     rbp, [rsp+58h+arg_10]
0x1800c600f  mov     rsi, [rsp+58h+arg_18]
0x1800c6014  add     rsp, 40h
0x1800c6018  pop     r15
0x1800c601a  pop     r14
0x1800c601c  pop     rdi
0x1800c601d  retn
0x1800c601f  mov     eax, 800288C5h
0x1800c6024  jmp     short loc_1800C6005
0x1800c6026  call    cs:__imp_GetLastError
0x1800c602d  nop     dword ptr [rax+rax+00h]
0x1800c6032  mov     ebx, eax
0x1800c6034  test    eax, eax
0x1800c6036  jg      short loc_1800C6049
0x1800c6038  test    ebx, ebx
0x1800c603a  jns     loc_1800C5FAB
0x1800c6040  jmp     short loc_1800C5FF3
0x1800c6042  mov     ebx, 80030102h
0x1800c6047  jmp     short loc_1800C5FF3
0x1800c6049  movzx   ebx, ax
0x1800c604c  or      ebx, 80070000h
0x1800c6052  jmp     short loc_1800C6038
0x1800c6054  call    cs:__imp_GetLastError
0x1800c605b  nop     dword ptr [rax+rax+00h]
0x1800c6060  mov     ebx, eax
0x1800c6062  test    eax, eax
0x1800c6064  jle     short loc_1800C606F
0x1800c6066  movzx   ebx, ax
0x1800c6069  or      ebx, 80070000h
0x1800c606f  test    ebx, ebx
0x1800c6071  js      short loc_1800C5FF3
0x1800c6073  jmp     loc_1800C5FD4
0x1800c6078  mov     [rsi], eax
0x1800c607a  jmp     loc_1800C5FF3
```
