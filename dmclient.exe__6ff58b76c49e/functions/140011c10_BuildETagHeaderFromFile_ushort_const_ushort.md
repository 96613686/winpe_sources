# BuildETagHeaderFromFile(ushort const *,ushort * *)

- ea: `0x140011c10`
- end: `0x140011de3`
- name: `?BuildETagHeaderFromFile@@YAJPEBGPEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140011fec`

## callees

- `0x14000b5c4`
- `0x140011c10`
- `0x1400187b2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011c62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011d72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011c62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011d72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011c4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011d61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011dba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011c4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011d61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011dba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011dc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011db4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011db4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140011d39`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140011d39`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140011d0d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140011d0d`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x140011cc2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x140011cc2`

## pseudocode

```c
__int64 __fastcall BuildETagHeaderFromFile(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rdi
  void *File2; // rbp
  signed int LastError; // eax
  DWORD FileSize; // eax
  signed int v10; // eax
  unsigned __int64 v11; // rbx
  HANDLE v12; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r14
  HANDLE v15; // rax
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
    if ( v6 )
    {
      v4 = StringCchPrintfW(v6, 0x104u, L"%s.%s", a1, L"etag");
      if ( v4 >= 0 )
      {
        File2 = (void *)CreateFile2(v6, 0x80000000LL, 1);
        memset_0(v6, 0, 0x208u);
        if ( File2 == (void *)-1LL )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError == 2 )
          {
            v4 = 0;
          }
          else if ( LastError > 0 )
          {
            v4 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          FileSize = GetFileSize(File2, 0);
          if ( FileSize <= 0x208 )
          {
            if ( ReadFile(File2, v6, FileSize, &NumberOfBytesRead, 0) )
            {
              v11 = NumberOfBytesRead + 62;
              v12 = GetProcessHeap();
              v13 = (unsigned __int16 *)HeapAlloc(v12, 8u, (unsigned int)v11);
              v14 = v13;
              if ( v13 )
              {
                v4 = StringCchPrintfW(v13, v11 >> 1, L"%s%s", L"If-None-Match:", v6);
                if ( v4 >= 0 )
                  *a2 = v14;
              }
              else
              {
                v4 = -2147024882;
              }
            }
            else
            {
              v10 = GetLastError();
              v4 = v10;
              if ( v10 > 0 )
                v4 = (unsigned __int16)v10 | 0x80070000;
            }
          }
          else
          {
            v4 = -2147024774;
          }
          CloseHandle(File2);
        }
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v6);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140011c10  mov     [rsp+arg_8], rbx
0x140011c15  mov     [rsp+arg_10], rbp
0x140011c1a  push    rsi
0x140011c1b  push    rdi
0x140011c1c  push    r14
0x140011c1e  sub     rsp, 30h
0x140011c22  mov     [rsp+48h+NumberOfBytesRead], 0
0x140011c2a  mov     rsi, rdx
0x140011c2d  mov     rbx, rcx
0x140011c30  test    rcx, rcx
0x140011c33  jnz     short loc_140011C3F
0x140011c35  mov     ebx, 80004003h
0x140011c3a  jmp     loc_140011DCE
0x140011c3f  test    rsi, rsi
0x140011c42  jz      short loc_140011C35
0x140011c44  mov     qword ptr [rdx], 0
0x140011c4b  call    cs:__imp_GetProcessHeap
0x140011c51  mov     r14d, 208h
0x140011c57  mov     edx, 8; dwFlags
0x140011c5c  mov     rcx, rax; hHeap
0x140011c5f  mov     r8d, r14d; dwBytes
0x140011c62  call    cs:__imp_HeapAlloc
0x140011c68  mov     rdi, rax
0x140011c6b  test    rax, rax
0x140011c6e  jnz     short loc_140011C7A
0x140011c70  mov     ebx, 8007000Eh
0x140011c75  jmp     loc_140011DCE
0x140011c7a  lea     rax, aEtag; "etag"
0x140011c81  mov     r9, rbx
0x140011c84  lea     r8, aSS; "%s.%s"
0x140011c8b  mov     [rsp+48h+lpOverlapped], rax
0x140011c90  mov     edx, 104h; unsigned __int64
0x140011c95  mov     rcx, rdi; unsigned __int16 *
0x140011c98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140011c9d  mov     ebx, eax
0x140011c9f  test    eax, eax
0x140011ca1  js      loc_140011DBA
0x140011ca7  mov     r9d, 3
0x140011cad  mov     [rsp+48h+lpOverlapped], 0
0x140011cb6  mov     edx, 80000000h
0x140011cbb  mov     rcx, rdi
0x140011cbe  lea     r8d, [r9-2]
0x140011cc2  call    cs:__imp_CreateFile2
0x140011cc8  mov     r8, r14; Size
0x140011ccb  xor     edx, edx; Val
0x140011ccd  mov     rcx, rdi; void *
0x140011cd0  mov     rbp, rax
0x140011cd3  call    memset_0
0x140011cd8  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140011cdc  jnz     short loc_140011D08
0x140011cde  call    cs:__imp_GetLastError
0x140011ce4  mov     ebx, eax
0x140011ce6  cmp     eax, 2
0x140011ce9  jnz     short loc_140011CF2
0x140011ceb  xor     ebx, ebx
0x140011ced  jmp     loc_140011DBA
0x140011cf2  test    eax, eax
0x140011cf4  jle     loc_140011DBA
0x140011cfa  movzx   ebx, ax
0x140011cfd  or      ebx, 80070000h
0x140011d03  jmp     loc_140011DBA
0x140011d08  xor     edx, edx; lpFileSizeHigh
0x140011d0a  mov     rcx, rbp; hFile
0x140011d0d  call    cs:__imp_GetFileSize
0x140011d13  cmp     eax, r14d
0x140011d16  jbe     short loc_140011D22
0x140011d18  mov     ebx, 8007007Ah
0x140011d1d  jmp     loc_140011DB1
0x140011d22  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140011d27  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x140011d30  mov     r8d, eax; nNumberOfBytesToRead
0x140011d33  mov     rdx, rdi; lpBuffer
0x140011d36  mov     rcx, rbp; hFile
0x140011d39  call    cs:__imp_ReadFile
0x140011d3f  test    eax, eax
0x140011d41  jnz     short loc_140011D5A
0x140011d43  call    cs:__imp_GetLastError
0x140011d49  mov     ebx, eax
0x140011d4b  test    eax, eax
0x140011d4d  jle     short loc_140011DB1
0x140011d4f  movzx   ebx, ax
0x140011d52  or      ebx, 80070000h
0x140011d58  jmp     short loc_140011DB1
0x140011d5a  mov     ebx, [rsp+48h+NumberOfBytesRead]
0x140011d5e  add     ebx, 3Eh ; '>'
0x140011d61  call    cs:__imp_GetProcessHeap
0x140011d67  mov     r8d, ebx; dwBytes
0x140011d6a  mov     edx, 8; dwFlags
0x140011d6f  mov     rcx, rax; hHeap
0x140011d72  call    cs:__imp_HeapAlloc
0x140011d78  mov     r14, rax
0x140011d7b  test    rax, rax
0x140011d7e  jnz     short loc_140011D87
0x140011d80  mov     ebx, 8007000Eh
0x140011d85  jmp     short loc_140011DB1
0x140011d87  shr     rbx, 1
0x140011d8a  lea     r9, aIfNoneMatch; "If-None-Match:"
0x140011d91  mov     rdx, rbx; unsigned __int64
0x140011d94  mov     [rsp+48h+lpOverlapped], rdi
0x140011d99  lea     r8, aSS_1; "%s%s"
0x140011da0  mov     rcx, r14; unsigned __int16 *
0x140011da3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140011da8  mov     ebx, eax
0x140011daa  test    eax, eax
0x140011dac  js      short loc_140011DB1
0x140011dae  mov     [rsi], r14
0x140011db1  mov     rcx, rbp; hObject
0x140011db4  call    cs:__imp_CloseHandle
0x140011dba  call    cs:__imp_GetProcessHeap
0x140011dc0  mov     r8, rdi; lpMem
0x140011dc3  xor     edx, edx; dwFlags
0x140011dc5  mov     rcx, rax; hHeap
0x140011dc8  call    cs:__imp_HeapFree
0x140011dce  mov     rbp, [rsp+48h+arg_10]
0x140011dd3  mov     eax, ebx
0x140011dd5  mov     rbx, [rsp+48h+arg_8]
0x140011dda  add     rsp, 30h
0x140011dde  pop     r14
0x140011de0  pop     rdi
0x140011de1  pop     rsi
0x140011de2  retn
```
