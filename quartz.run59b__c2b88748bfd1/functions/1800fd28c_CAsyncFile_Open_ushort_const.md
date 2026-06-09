# CAsyncFile::Open(ushort const *)

- ea: `0x1800fd28c`
- end: `0x1800fd45f`
- name: `?Open@CAsyncFile@@QEAAJPEBG@Z`
- size: `467`
- prototype: `int(CAsyncFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800fcc70`

## callees

- `0x1800283c0`
- `0x18002f120`
- `0x1800fd28c`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x1800fd3de`
- `KERNEL32!GetFileSize` at `0x1800fd3de`
- `KERNEL32!GetFileType` at `0x1800fd33c`
- `KERNEL32!GetFileType` at `0x1800fd33c`
- `KERNEL32!CloseHandle` at `0x1800fd351`
- `KERNEL32!CloseHandle` at `0x1800fd3ac`
- `KERNEL32!CloseHandle` at `0x1800fd40c`
- `KERNEL32!CloseHandle` at `0x1800fd425`
- `KERNEL32!CloseHandle` at `0x1800fd351`
- `KERNEL32!CloseHandle` at `0x1800fd3ac`
- `KERNEL32!CloseHandle` at `0x1800fd40c`
- `KERNEL32!CloseHandle` at `0x1800fd425`
- `KERNEL32!GetLastError` at `0x1800fd31c`
- `KERNEL32!GetLastError` at `0x1800fd3f6`
- `KERNEL32!GetLastError` at `0x1800fd31c`
- `KERNEL32!GetLastError` at `0x1800fd3f6`
- `KERNEL32!CreateFileW` at `0x1800fd307`
- `KERNEL32!CreateFileW` at `0x1800fd393`
- `KERNEL32!CreateFileW` at `0x1800fd307`
- `KERNEL32!CreateFileW` at `0x1800fd393`

## pseudocode

```c
__int64 __fastcall CAsyncFile::Open(CAsyncFile *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  DWORD dwFlagsAndAttributes; // eax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  HANDLE v8; // rax
  void *v9; // rcx
  DWORD v10; // edi
  void *v11; // rcx
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF
  __int64 FileSizeHigh; // [rsp+80h] [rbp+18h] BYREF

  if ( *((_QWORD *)this + 5) != -1 )
    return 2147549183LL;
  v12 = 0;
  CAsyncFile::CalcAlignment(this, a2, (int *)this + 18, &v12);
  dwFlagsAndAttributes = 0x20000000;
  if ( v12 == 4 )
    dwFlagsAndAttributes = 0x8000000;
  FileW = CreateFileW(a2, 0x80000000, 5u, 0, 3u, dwFlagsAndAttributes, 0);
  *((_QWORD *)this + 5) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 6 )
      LastError = 3;
    return LastError | 0x80070000;
  }
  else if ( GetFileType(FileW) == 1 )
  {
    if ( *((int *)this + 18) > 1
      && (v8 = CreateFileW(a2, 0x80000000, 5u, 0, 3u, 0x8000000u, 0), *((_QWORD *)this + 6) = v8, v8 == (HANDLE)-1LL) )
    {
      CloseHandle(*((HANDLE *)this + 5));
      *((_QWORD *)this + 5) = -1;
      return AmGetLastErrorToHResult();
    }
    else
    {
      v9 = (void *)*((_QWORD *)this + 5);
      FileSizeHigh = 0;
      LODWORD(FileSizeHigh) = GetFileSize(v9, (LPDWORD)&FileSizeHigh + 1);
      if ( (_DWORD)FileSizeHigh == -1 && (v10 = GetLastError()) != 0 )
      {
        CloseHandle(*((HANDLE *)this + 5));
        v11 = (void *)*((_QWORD *)this + 6);
        *((_QWORD *)this + 5) = -1;
        if ( v11 != (void *)-1LL )
        {
          CloseHandle(v11);
          *((_QWORD *)this + 6) = -1;
        }
        return v10 | 0x80070000;
      }
      else
      {
        *((_QWORD *)this + 8) = FileSizeHigh;
        return 0;
      }
    }
  }
  else
  {
    CloseHandle(*((HANDLE *)this + 5));
    result = 2147942402LL;
    *((_QWORD *)this + 5) = -1;
  }
  return result;
}

```

## disassembly

```asm
0x1800fd28c  mov     [rsp+arg_8], rbx
0x1800fd291  push    rbp
0x1800fd292  push    rsi
0x1800fd293  push    rdi
0x1800fd294  push    r12
0x1800fd296  push    r15
0x1800fd298  sub     rsp, 40h
0x1800fd29c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800fd2a0  mov     rdi, rdx
0x1800fd2a3  mov     rbx, rcx
0x1800fd2a6  cmp     [rcx+28h], rbp
0x1800fd2aa  jz      short loc_1800FD2B6
0x1800fd2ac  mov     eax, 8000FFFFh
0x1800fd2b1  jmp     loc_1800FD44D
0x1800fd2b6  lea     r9, [rsp+68h+arg_0]; unsigned int *
0x1800fd2bb  mov     [rsp+68h+arg_0], 0
0x1800fd2c3  lea     r8, [rcx+48h]; int *
0x1800fd2c7  call    ?CalcAlignment@CAsyncFile@@AEAAXPEBGAEAJAEAK@Z; CAsyncFile::CalcAlignment(ushort const *,long &,ulong &)
0x1800fd2cc  cmp     [rsp+68h+arg_0], 4
0x1800fd2d1  mov     r15d, 3
0x1800fd2d7  mov     eax, 20000000h
0x1800fd2dc  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800fd2e5  mov     r12d, 8000000h
0x1800fd2eb  mov     edx, 80000000h; dwDesiredAccess
0x1800fd2f0  cmovz   eax, r12d
0x1800fd2f4  mov     rcx, rdi; lpFileName
0x1800fd2f7  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800fd2fb  lea     r8d, [r15+2]; dwShareMode
0x1800fd2ff  xor     r9d, r9d; lpSecurityAttributes
0x1800fd302  mov     [rsp+68h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800fd307  call    cs:__imp_CreateFileW
0x1800fd30e  nop     dword ptr [rax+rax+00h]
0x1800fd313  mov     [rbx+28h], rax
0x1800fd317  cmp     rax, rbp
0x1800fd31a  jnz     short loc_1800FD339
0x1800fd31c  call    cs:__imp_GetLastError
0x1800fd323  nop     dword ptr [rax+rax+00h]
0x1800fd328  cmp     eax, 6
0x1800fd32b  cmovz   eax, r15d
0x1800fd32f  or      eax, 80070000h
0x1800fd334  jmp     loc_1800FD44D
0x1800fd339  mov     rcx, rax; hFile
0x1800fd33c  call    cs:__imp_GetFileType
0x1800fd343  nop     dword ptr [rax+rax+00h]
0x1800fd348  cmp     eax, 1
0x1800fd34b  jz      short loc_1800FD36B
0x1800fd34d  mov     rcx, [rbx+28h]; hObject
0x1800fd351  call    cs:__imp_CloseHandle
0x1800fd358  nop     dword ptr [rax+rax+00h]
0x1800fd35d  mov     eax, 80070002h
0x1800fd362  mov     [rbx+28h], rbp
0x1800fd366  jmp     loc_1800FD44D
0x1800fd36b  cmp     dword ptr [rbx+48h], 1
0x1800fd36f  jle     short loc_1800FD3C6
0x1800fd371  xor     r9d, r9d; lpSecurityAttributes
0x1800fd374  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800fd37d  mov     [rsp+68h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800fd382  mov     edx, 80000000h; dwDesiredAccess
0x1800fd387  mov     rcx, rdi; lpFileName
0x1800fd38a  mov     [rsp+68h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800fd38f  lea     r8d, [r9+5]; dwShareMode
0x1800fd393  call    cs:__imp_CreateFileW
0x1800fd39a  nop     dword ptr [rax+rax+00h]
0x1800fd39f  mov     [rbx+30h], rax
0x1800fd3a3  cmp     rax, rbp
0x1800fd3a6  jnz     short loc_1800FD3C6
0x1800fd3a8  mov     rcx, [rbx+28h]; hObject
0x1800fd3ac  call    cs:__imp_CloseHandle
0x1800fd3b3  nop     dword ptr [rax+rax+00h]
0x1800fd3b8  mov     [rbx+28h], rbp
0x1800fd3bc  call    ?AmGetLastErrorToHResult@@YAJXZ; AmGetLastErrorToHResult(void)
0x1800fd3c1  jmp     loc_1800FD44D
0x1800fd3c6  mov     rcx, [rbx+28h]; hFile
0x1800fd3ca  lea     rdx, [rsp+68h+FileSizeHigh+4]; lpFileSizeHigh
0x1800fd3d2  mov     qword ptr [rsp+80h], 0
0x1800fd3de  call    cs:__imp_GetFileSize
0x1800fd3e5  nop     dword ptr [rax+rax+00h]
0x1800fd3ea  mov     dword ptr [rsp+68h+FileSizeHigh], eax
0x1800fd3f1  cmp     eax, 0FFFFFFFFh
0x1800fd3f4  jnz     short loc_1800FD43F
0x1800fd3f6  call    cs:__imp_GetLastError
0x1800fd3fd  nop     dword ptr [rax+rax+00h]
0x1800fd402  mov     edi, eax
0x1800fd404  test    eax, eax
0x1800fd406  jz      short loc_1800FD43F
0x1800fd408  mov     rcx, [rbx+28h]; hObject
0x1800fd40c  call    cs:__imp_CloseHandle
0x1800fd413  nop     dword ptr [rax+rax+00h]
0x1800fd418  mov     rcx, [rbx+30h]; hObject
0x1800fd41c  mov     [rbx+28h], rbp
0x1800fd420  cmp     rcx, rbp
0x1800fd423  jz      short loc_1800FD435
0x1800fd425  call    cs:__imp_CloseHandle
0x1800fd42c  nop     dword ptr [rax+rax+00h]
0x1800fd431  mov     [rbx+30h], rbp
0x1800fd435  or      edi, 80070000h
0x1800fd43b  mov     eax, edi
0x1800fd43d  jmp     short loc_1800FD44D
0x1800fd43f  mov     rax, [rsp+68h+FileSizeHigh]
0x1800fd447  mov     [rbx+40h], rax
0x1800fd44b  xor     eax, eax
0x1800fd44d  mov     rbx, [rsp+68h+arg_8]
0x1800fd452  add     rsp, 40h
0x1800fd456  pop     r15
0x1800fd458  pop     r12
0x1800fd45a  pop     rdi
0x1800fd45b  pop     rsi
0x1800fd45c  pop     rbp
0x1800fd45d  retn
```
