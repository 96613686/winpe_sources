# DecodeFileW(ushort const *,uchar * *,ulong *,ulong)

- ea: `0x180010db0`
- end: `0x180010fa5`
- name: `?DecodeFileW@@YAJPEBGPEAPEAEPEAKK@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180008400`
- `0x180008610`
- `0x180010db0`
- `0x180012450`
- `0x180015cc0`
- `0x18001de68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010e6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010e6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f8c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180010e2f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180010e2f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010e4e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180010e4e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010e9d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180010e9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010dfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f6c`

## pseudocode

```c
__int64 __fastcall DecodeFileW(const unsigned __int16 *a1, unsigned __int8 **a2, unsigned int *a3, unsigned int a4)
{
  unsigned __int8 *v8; // rsi
  HANDLE FileW; // rax
  void *v10; // r14
  unsigned int v11; // ebx
  unsigned __int8 *v12; // rdi
  unsigned int v13; // ecx
  DWORD FileSize; // eax
  DWORD v15; // ebx
  unsigned __int8 *v16; // rax
  int v17; // edx
  unsigned __int8 *v18; // rax
  unsigned int v19; // eax
  int v20; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-28h] BYREF
  DWORD cchString; // [rsp+44h] [rbp-24h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int8 *v25; // [rsp+50h] [rbp-18h] BYREF

  v25 = 0;
  NumberOfBytesRead = 0;
  v24 = 0;
  v8 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v11 = myHLastError();
    CSPrintErrorLineFileData2(a1, 0x340327u, v11, 0);
    goto LABEL_28;
  }
  v12 = 0;
  if ( GetFileType(FileW) != 1 )
  {
    v11 = -2147024894;
    v13 = 3736359;
LABEL_24:
    v17 = v11;
    goto LABEL_25;
  }
  FileSize = GetFileSize(v10, 0);
  v15 = FileSize;
  cchString = FileSize;
  if ( FileSize == -1 )
  {
    v11 = myHLastError();
    goto LABEL_23;
  }
  if ( !FileSize )
  {
    v11 = -2147024883;
LABEL_23:
    v13 = 4653863;
    goto LABEL_24;
  }
  v16 = (unsigned __int8 *)LocalAlloc(0, FileSize);
  v12 = v16;
  if ( !v16 )
  {
    v11 = -2147024882;
    v13 = 5112615;
    goto LABEL_24;
  }
  if ( ReadFile(v10, v16, v15, &NumberOfBytesRead, 0) )
  {
    if ( NumberOfBytesRead != v15 )
    {
      v11 = -2147024858;
      v13 = 6292263;
      goto LABEL_24;
    }
    if ( a4 == 2 )
    {
      v18 = v12;
      v12 = 0;
    }
    else
    {
      v19 = myConvertSimpleUnicodeToAnsi(v12, &cchString);
      v11 = v19;
      if ( v19 )
      {
        v17 = v19;
        v13 = 7471911;
        goto LABEL_25;
      }
      v20 = myCryptStringToBinaryA((LPCSTR)v12, cchString, a4, &v25, &v24, 0, 0);
      v11 = v20;
      if ( v20 )
      {
        CSPrintErrorLineFileData2(0, 0x870327u, v20, -2147024883);
        v8 = v25;
        goto LABEL_26;
      }
      v18 = v25;
      v15 = v24;
    }
    *a3 = v15;
    v11 = 0;
    *a2 = v18;
    goto LABEL_26;
  }
  v11 = myHLastError();
  v17 = v11;
  v13 = 5505831;
LABEL_25:
  CSPrintErrorLineFile(v13, v17);
LABEL_26:
  CloseHandle(v10);
  if ( v12 )
    LocalFree(v12);
LABEL_28:
  if ( v11 && v8 )
    LocalFree(v8);
  return v11;
}

```

## disassembly

```asm
0x180010db0  push    rbp
0x180010db2  push    rbx
0x180010db3  push    rsi
0x180010db4  push    rdi
0x180010db5  push    r12
0x180010db7  push    r13
0x180010db9  push    r14
0x180010dbb  push    r15
0x180010dbd  mov     rbp, rsp
0x180010dc0  sub     rsp, 68h
0x180010dc4  xor     ebx, ebx
0x180010dc6  mov     r15d, r9d
0x180010dc9  mov     r12, r8
0x180010dcc  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x180010dd1  mov     r13, rdx
0x180010dd4  mov     [rsp+68h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180010dd8  xor     r9d, r9d; lpSecurityAttributes
0x180010ddb  mov     [rbp+var_18], rbx
0x180010ddf  lea     r8d, [rbx+1]; dwShareMode
0x180010de3  mov     [rbp+NumberOfBytesRead], ebx
0x180010de6  mov     edx, 80000000h; dwDesiredAccess
0x180010deb  mov     [rbp+var_20], ebx
0x180010dee  mov     rdi, rcx
0x180010df1  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180010df9  mov     esi, ebx
0x180010dfb  call    cs:__imp_CreateFileW
0x180010e01  mov     r14, rax
0x180010e04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010e08  jnz     short loc_180010E29
0x180010e0a  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010e0f  xor     r9d, r9d; int
0x180010e12  mov     r8d, eax; int
0x180010e15  mov     edx, 340327h; unsigned int
0x180010e1a  mov     rcx, rdi; unsigned __int16 *
0x180010e1d  mov     ebx, eax
0x180010e1f  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010e24  jmp     loc_180010F80
0x180010e29  mov     rcx, r14; hFile
0x180010e2c  mov     rdi, rbx
0x180010e2f  call    cs:__imp_GetFileType
0x180010e35  cmp     eax, 1
0x180010e38  jz      short loc_180010E49
0x180010e3a  mov     ebx, 80070002h
0x180010e3f  mov     ecx, 390327h
0x180010e44  jmp     loc_180010F62
0x180010e49  xor     edx, edx; lpFileSizeHigh
0x180010e4b  mov     rcx, r14; hFile
0x180010e4e  call    cs:__imp_GetFileSize
0x180010e54  mov     ebx, eax
0x180010e56  mov     [rbp+cchString], ebx
0x180010e59  cmp     eax, 0FFFFFFFFh
0x180010e5c  jz      loc_180010F56
0x180010e62  test    eax, eax
0x180010e64  jz      loc_180010F4F
0x180010e6a  mov     edx, ebx; uBytes
0x180010e6c  xor     ecx, ecx; uFlags
0x180010e6e  call    cs:__imp_LocalAlloc
0x180010e74  mov     rdi, rax
0x180010e77  test    rax, rax
0x180010e7a  jnz     short loc_180010E8B
0x180010e7c  mov     ebx, 8007000Eh
0x180010e81  mov     ecx, 4E0327h
0x180010e86  jmp     loc_180010F62
0x180010e8b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180010e8f  mov     qword ptr [rsp+68h+dwCreationDisposition], rsi; lpOverlapped
0x180010e94  mov     r8d, ebx; nNumberOfBytesToRead
0x180010e97  mov     rdx, rdi; lpBuffer
0x180010e9a  mov     rcx, r14; hFile
0x180010e9d  call    cs:__imp_ReadFile
0x180010ea3  test    eax, eax
0x180010ea5  jnz     short loc_180010EBA
0x180010ea7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010eac  mov     ebx, eax
0x180010eae  mov     edx, eax
0x180010eb0  mov     ecx, 540327h
0x180010eb5  jmp     loc_180010F64
0x180010eba  cmp     [rbp+NumberOfBytesRead], ebx
0x180010ebd  jz      short loc_180010ECE
0x180010ebf  mov     ebx, 80070026h
0x180010ec4  mov     ecx, 600327h
0x180010ec9  jmp     loc_180010F62
0x180010ece  cmp     r15d, 2
0x180010ed2  jnz     short loc_180010EDB
0x180010ed4  mov     rax, rdi
0x180010ed7  xor     edi, edi
0x180010ed9  jmp     short loc_180010F43
0x180010edb  lea     rdx, [rbp+cchString]; unsigned int *
0x180010edf  mov     rcx, rdi; unsigned __int8 *
0x180010ee2  call    ?myConvertSimpleUnicodeToAnsi@@YAJPEAEPEAK@Z; myConvertSimpleUnicodeToAnsi(uchar *,ulong *)
0x180010ee7  mov     ebx, eax
0x180010ee9  test    eax, eax
0x180010eeb  jz      short loc_180010EF6
0x180010eed  mov     edx, eax
0x180010eef  mov     ecx, 720327h
0x180010ef4  jmp     short loc_180010F64
0x180010ef6  mov     edx, [rbp+cchString]; cchString
0x180010ef9  lea     rax, [rbp+var_20]
0x180010efd  mov     [rsp+68h+hTemplateFile], rsi; unsigned int *
0x180010f02  lea     r9, [rbp+var_18]; unsigned __int8 **
0x180010f06  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi; unsigned int *
0x180010f0b  mov     r8d, r15d; unsigned int
0x180010f0e  mov     rcx, rdi; pszString
0x180010f11  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; unsigned int *
0x180010f16  call    ?myCryptStringToBinaryA@@YAJPEBDKKPEAPEAEPEAK22@Z; myCryptStringToBinaryA(char const *,ulong,ulong,uchar * *,ulong *,ulong *,ulong *)
0x180010f1b  mov     ebx, eax
0x180010f1d  test    eax, eax
0x180010f1f  jz      short loc_180010F3C
0x180010f21  mov     r9d, 8007000Dh; int
0x180010f27  mov     r8d, eax; int
0x180010f2a  mov     edx, 870327h; unsigned int
0x180010f2f  xor     ecx, ecx; unsigned __int16 *
0x180010f31  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010f36  mov     rsi, [rbp+var_18]
0x180010f3a  jmp     short loc_180010F69
0x180010f3c  mov     rax, [rbp+var_18]
0x180010f40  mov     ebx, [rbp+var_20]
0x180010f43  mov     [r12], ebx
0x180010f47  xor     ebx, ebx
0x180010f49  mov     [r13+0], rax
0x180010f4d  jmp     short loc_180010F69
0x180010f4f  mov     ebx, 8007000Dh
0x180010f54  jmp     short loc_180010F5D
0x180010f56  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010f5b  mov     ebx, eax
0x180010f5d  mov     ecx, 470327h; unsigned int
0x180010f62  mov     edx, ebx; int
0x180010f64  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180010f69  mov     rcx, r14; hObject
0x180010f6c  call    cs:__imp_CloseHandle
0x180010f72  test    rdi, rdi
0x180010f75  jz      short loc_180010F80
0x180010f77  mov     rcx, rdi; hMem
0x180010f7a  call    cs:__imp_LocalFree
0x180010f80  test    ebx, ebx
0x180010f82  jz      short loc_180010F92
0x180010f84  test    rsi, rsi
0x180010f87  jz      short loc_180010F92
0x180010f89  mov     rcx, rsi; hMem
0x180010f8c  call    cs:__imp_LocalFree
0x180010f92  mov     eax, ebx
0x180010f94  add     rsp, 68h
0x180010f98  pop     r15
0x180010f9a  pop     r14
0x180010f9c  pop     r13
0x180010f9e  pop     r12
0x180010fa0  pop     rdi
0x180010fa1  pop     rsi
0x180010fa2  pop     rbx
0x180010fa3  pop     rbp
0x180010fa4  retn
```
