# SipFile::Read(unsigned __int64,ulong,void *,ulong *)

- ea: `0x180004ec0`
- end: `0x180004fcd`
- name: `?Read@SipFile@@QEAAK_KKPEAXPEAK@Z`
- size: `269`
- prototype: `unsigned int(SipFile *__hidden this, unsigned __int64, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003c70`
- `0x180003fe4`

## callees

- `0x180004ec0`
- `0x1800054a2`
- `0x1800054ae`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180004f58`
- `KERNEL32!SetFilePointerEx` at `0x180004f58`
- `KERNEL32!ReadFile` at `0x180004f9f`
- `KERNEL32!ReadFile` at `0x180004f9f`
- `KERNEL32!GetLastError` at `0x180004f62`
- `KERNEL32!GetLastError` at `0x180004f62`

## pseudocode

```c
__int64 __fastcall SipFile::Read(SipFile *this, __int64 a2, unsigned int a3, void *a4, unsigned int *a5)
{
  unsigned int *v5; // rdi
  size_t v7; // rbx
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 NumberOfBytesRead; // [rsp+58h] [rbp+10h] BYREF

  NumberOfBytesRead = a2;
  v5 = a5;
  v7 = a3;
  if ( !a5 )
    return 87;
  *a5 = 0;
  if ( !a3 || !a4 )
    return 87;
  memset_0(a4, 0, a3);
  v9 = *((_QWORD *)this + 1);
  if ( !v9 )
  {
    if ( !SetFilePointerEx(*((HANDLE *)this + 4), 0, 0, 0) )
      return GetLastError();
    LODWORD(NumberOfBytesRead) = 0;
    *v5 = 0;
    memset_0(a4, 0, v7);
    if ( !ReadFile(*((HANDLE *)this + 4), a4, v7, (LPDWORD)&NumberOfBytesRead, 0) )
      return GetLastError();
    v12 = NumberOfBytesRead;
    v11 = 0;
LABEL_12:
    *v5 = v12;
    return v11;
  }
  v10 = *(_QWORD *)(v9 + 112);
  if ( *(_DWORD *)(v10 + 4) <= (unsigned int)v7 )
  {
    v11 = 0;
    memcpy_0(a4, *(const void **)(v10 + 8), *(unsigned int *)(v10 + 4));
    v12 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 112LL) + 4LL);
    goto LABEL_12;
  }
  return 8;
}

```

## disassembly

```asm
0x180004ec0  mov     [rsp+arg_0], rbx
0x180004ec5  mov     [rsp+arg_10], rbp
0x180004eca  mov     [rsp+NumberOfBytesRead], rdx
0x180004ecf  push    rsi
0x180004ed0  push    rdi
0x180004ed1  push    r14
0x180004ed3  sub     rsp, 30h
0x180004ed7  mov     rdi, [rsp+48h+arg_20]
0x180004edc  mov     rsi, r9
0x180004edf  mov     ebx, r8d
0x180004ee2  mov     rbp, rcx
0x180004ee5  test    rdi, rdi
0x180004ee8  jz      loc_180004FB3
0x180004eee  mov     dword ptr [rdi], 0
0x180004ef4  test    r8d, r8d
0x180004ef7  jz      loc_180004FB3
0x180004efd  test    r9, r9
0x180004f00  jz      loc_180004FB3
0x180004f06  mov     r8d, ebx; Size
0x180004f09  xor     edx, edx; Val
0x180004f0b  mov     rcx, r9; void *
0x180004f0e  call    memset_0
0x180004f13  mov     rdx, [rbp+8]; liDistanceToMove
0x180004f17  test    rdx, rdx
0x180004f1a  jz      short loc_180004F4E
0x180004f1c  mov     rdx, [rdx+70h]
0x180004f20  cmp     [rdx+4], ebx
0x180004f23  jbe     short loc_180004F2F
0x180004f25  mov     ebx, 8
0x180004f2a  jmp     loc_180004FB8
0x180004f2f  mov     r8d, [rdx+4]; Size
0x180004f33  xor     ebx, ebx
0x180004f35  mov     rdx, [rdx+8]; Src
0x180004f39  mov     rcx, rsi; void *
0x180004f3c  call    memcpy_0
0x180004f41  mov     rax, [rbp+8]
0x180004f45  mov     rcx, [rax+70h]
0x180004f49  mov     eax, [rcx+4]
0x180004f4c  jmp     short loc_180004FAF
0x180004f4e  mov     rcx, [rbp+20h]; hFile
0x180004f52  xor     r9d, r9d; dwMoveMethod
0x180004f55  xor     r8d, r8d; lpNewFilePointer
0x180004f58  call    cs:__imp_SetFilePointerEx
0x180004f5e  test    eax, eax
0x180004f60  jnz     short loc_180004F6C
0x180004f62  call    cs:__imp_GetLastError
0x180004f68  mov     ebx, eax
0x180004f6a  jmp     short loc_180004FB8
0x180004f6c  mov     r8, rbx; Size
0x180004f6f  mov     dword ptr [rsp+48h+NumberOfBytesRead], 0
0x180004f77  xor     edx, edx; Val
0x180004f79  mov     dword ptr [rdi], 0
0x180004f7f  mov     rcx, rsi; void *
0x180004f82  call    memset_0
0x180004f87  mov     rcx, [rbp+20h]; hFile
0x180004f8b  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180004f90  mov     r8d, ebx; nNumberOfBytesToRead
0x180004f93  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180004f9c  mov     rdx, rsi; lpBuffer
0x180004f9f  call    cs:__imp_ReadFile
0x180004fa5  test    eax, eax
0x180004fa7  jz      short loc_180004F62
0x180004fa9  mov     eax, dword ptr [rsp+48h+NumberOfBytesRead]
0x180004fad  xor     ebx, ebx
0x180004faf  mov     [rdi], eax
0x180004fb1  jmp     short loc_180004FB8
0x180004fb3  mov     ebx, 57h ; 'W'
0x180004fb8  mov     rbp, [rsp+48h+arg_10]
0x180004fbd  mov     eax, ebx
0x180004fbf  mov     rbx, [rsp+48h+arg_0]
0x180004fc4  add     rsp, 30h
0x180004fc8  pop     r14
0x180004fca  pop     rdi
0x180004fcb  pop     rsi
0x180004fcc  retn
```
