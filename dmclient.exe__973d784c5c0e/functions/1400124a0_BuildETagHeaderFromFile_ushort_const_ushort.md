# BuildETagHeaderFromFile(ushort const *,ushort * *)

- ea: `0x1400124a0`
- end: `0x1400126bc`
- name: `?BuildETagHeaderFromFile@@YAJPEBGPEAPEAG@Z`
- size: `540`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140012928`

## callees

- `0x14000b904`
- `0x1400124a0`
- `0x1400195e2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400124f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012632`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400124f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012632`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400124db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001261b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400124db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001261b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001269a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001269a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400125f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400125f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001267a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001267a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400125e7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400125e7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1400125b5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1400125b5`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x14001255e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x14001255e`

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
0x1400124a0  mov     [rsp+arg_8], rbx
0x1400124a5  mov     [rsp+arg_10], rbp
0x1400124aa  push    rsi
0x1400124ab  push    rdi
0x1400124ac  push    r14
0x1400124ae  sub     rsp, 30h
0x1400124b2  mov     [rsp+48h+NumberOfBytesRead], 0
0x1400124ba  mov     rsi, rdx
0x1400124bd  mov     rbx, rcx
0x1400124c0  test    rcx, rcx
0x1400124c3  jnz     short loc_1400124CF
0x1400124c5  mov     ebx, 80004003h
0x1400124ca  jmp     loc_1400126A6
0x1400124cf  test    rsi, rsi
0x1400124d2  jz      short loc_1400124C5
0x1400124d4  mov     qword ptr [rdx], 0
0x1400124db  call    cs:__imp_GetProcessHeap
0x1400124e2  nop     dword ptr [rax+rax+00h]
0x1400124e7  mov     r14d, 208h
0x1400124ed  mov     edx, 8; dwFlags
0x1400124f2  mov     rcx, rax; hHeap
0x1400124f5  mov     r8d, r14d; dwBytes
0x1400124f8  call    cs:__imp_HeapAlloc
0x1400124ff  nop     dword ptr [rax+rax+00h]
0x140012504  mov     rdi, rax
0x140012507  test    rax, rax
0x14001250a  jnz     short loc_140012516
0x14001250c  mov     ebx, 8007000Eh
0x140012511  jmp     loc_1400126A6
0x140012516  lea     rax, aEtag; "etag"
0x14001251d  mov     r9, rbx
0x140012520  lea     r8, aSS; "%s.%s"
0x140012527  mov     [rsp+48h+lpOverlapped], rax
0x14001252c  mov     edx, 104h; unsigned __int64
0x140012531  mov     rcx, rdi; unsigned __int16 *
0x140012534  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012539  mov     ebx, eax
0x14001253b  test    eax, eax
0x14001253d  js      loc_140012686
0x140012543  mov     r9d, 3
0x140012549  mov     [rsp+48h+lpOverlapped], 0
0x140012552  mov     edx, 80000000h
0x140012557  mov     rcx, rdi
0x14001255a  lea     r8d, [r9-2]
0x14001255e  call    cs:__imp_CreateFile2
0x140012565  nop     dword ptr [rax+rax+00h]
0x14001256a  mov     r8, r14; Size
0x14001256d  xor     edx, edx; Val
0x14001256f  mov     rcx, rdi; void *
0x140012572  mov     rbp, rax
0x140012575  call    memset_0
0x14001257a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14001257e  jnz     short loc_1400125B0
0x140012580  call    cs:__imp_GetLastError
0x140012587  nop     dword ptr [rax+rax+00h]
0x14001258c  mov     ebx, eax
0x14001258e  cmp     eax, 2
0x140012591  jnz     short loc_14001259A
0x140012593  xor     ebx, ebx
0x140012595  jmp     loc_140012686
0x14001259a  test    eax, eax
0x14001259c  jle     loc_140012686
0x1400125a2  movzx   ebx, ax
0x1400125a5  or      ebx, 80070000h
0x1400125ab  jmp     loc_140012686
0x1400125b0  xor     edx, edx; lpFileSizeHigh
0x1400125b2  mov     rcx, rbp; hFile
0x1400125b5  call    cs:__imp_GetFileSize
0x1400125bc  nop     dword ptr [rax+rax+00h]
0x1400125c1  cmp     eax, r14d
0x1400125c4  jbe     short loc_1400125D0
0x1400125c6  mov     ebx, 8007007Ah
0x1400125cb  jmp     loc_140012677
0x1400125d0  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400125d5  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1400125de  mov     r8d, eax; nNumberOfBytesToRead
0x1400125e1  mov     rdx, rdi; lpBuffer
0x1400125e4  mov     rcx, rbp; hFile
0x1400125e7  call    cs:__imp_ReadFile
0x1400125ee  nop     dword ptr [rax+rax+00h]
0x1400125f3  test    eax, eax
0x1400125f5  jnz     short loc_140012614
0x1400125f7  call    cs:__imp_GetLastError
0x1400125fe  nop     dword ptr [rax+rax+00h]
0x140012603  mov     ebx, eax
0x140012605  test    eax, eax
0x140012607  jle     short loc_140012677
0x140012609  movzx   ebx, ax
0x14001260c  or      ebx, 80070000h
0x140012612  jmp     short loc_140012677
0x140012614  mov     ebx, [rsp+48h+NumberOfBytesRead]
0x140012618  add     ebx, 3Eh ; '>'
0x14001261b  call    cs:__imp_GetProcessHeap
0x140012622  nop     dword ptr [rax+rax+00h]
0x140012627  mov     r8d, ebx; dwBytes
0x14001262a  mov     edx, 8; dwFlags
0x14001262f  mov     rcx, rax; hHeap
0x140012632  call    cs:__imp_HeapAlloc
0x140012639  nop     dword ptr [rax+rax+00h]
0x14001263e  mov     r14, rax
0x140012641  test    rax, rax
0x140012644  jnz     short loc_14001264D
0x140012646  mov     ebx, 8007000Eh
0x14001264b  jmp     short loc_140012677
0x14001264d  shr     rbx, 1
0x140012650  lea     r9, aIfNoneMatch; "If-None-Match:"
0x140012657  mov     rdx, rbx; unsigned __int64
0x14001265a  mov     [rsp+48h+lpOverlapped], rdi
0x14001265f  lea     r8, aSS_1; "%s%s"
0x140012666  mov     rcx, r14; unsigned __int16 *
0x140012669  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001266e  mov     ebx, eax
0x140012670  test    eax, eax
0x140012672  js      short loc_140012677
0x140012674  mov     [rsi], r14
0x140012677  mov     rcx, rbp; hObject
0x14001267a  call    cs:__imp_CloseHandle
0x140012681  nop     dword ptr [rax+rax+00h]
0x140012686  call    cs:__imp_GetProcessHeap
0x14001268d  nop     dword ptr [rax+rax+00h]
0x140012692  mov     r8, rdi; lpMem
0x140012695  xor     edx, edx; dwFlags
0x140012697  mov     rcx, rax; hHeap
0x14001269a  call    cs:__imp_HeapFree
0x1400126a1  nop     dword ptr [rax+rax+00h]
0x1400126a6  mov     rbp, [rsp+48h+arg_10]
0x1400126ab  mov     eax, ebx
0x1400126ad  mov     rbx, [rsp+48h+arg_8]
0x1400126b2  add     rsp, 30h
0x1400126b6  pop     r14
0x1400126b8  pop     rdi
0x1400126b9  pop     rsi
0x1400126ba  retn
```
