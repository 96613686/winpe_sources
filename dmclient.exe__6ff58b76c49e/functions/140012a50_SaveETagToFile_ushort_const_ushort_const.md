# SaveETagToFile(ushort const *,ushort const *)

- ea: `0x140012a50`
- end: `0x140012b82`
- name: `?SaveETagToFile@@YAJPEBG0@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140011fec`

## callees

- `0x14000b5c4`
- `0x140012a50`

## import_xrefs

- `msvcrt!wcsnlen` at `0x140012b1d`
- `msvcrt!wcsnlen` at `0x140012b1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012a8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012a8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012b63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012b63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012b71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012b5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012b5d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140012b3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140012b3b`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x140012aef`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x140012aef`

## pseudocode

```c
__int64 __fastcall SaveETagToFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rdi
  void *File2; // rbp
  signed int LastError; // eax
  int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( a1 && a2 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
    if ( v6 )
    {
      v4 = StringCchPrintfW(v6, 0x104u, L"%s.%s", a1, L"etag");
      if ( v4 >= 0 )
      {
        File2 = (void *)CreateFile2(v6, 0x40000000, 1);
        if ( File2 == (void *)-1LL )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v9 = wcsnlen(a2, 0x104u);
          if ( !WriteFile(File2, a2, 2 * v9, &NumberOfBytesWritten, 0) )
          {
            v10 = GetLastError();
            v4 = v10;
            if ( v10 > 0 )
              v4 = (unsigned __int16)v10 | 0x80070000;
          }
          CloseHandle(File2);
        }
      }
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v6);
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
0x140012a50  push    rbx
0x140012a52  push    rbp
0x140012a53  push    rsi
0x140012a54  push    rdi
0x140012a55  sub     rsp, 38h
0x140012a59  mov     [rsp+58h+NumberOfBytesWritten], 0
0x140012a61  mov     rsi, rdx
0x140012a64  mov     rbx, rcx
0x140012a67  test    rcx, rcx
0x140012a6a  jnz     short loc_140012A76
0x140012a6c  mov     ebx, 80004003h
0x140012a71  jmp     loc_140012B77
0x140012a76  test    rsi, rsi
0x140012a79  jz      short loc_140012A6C
0x140012a7b  call    cs:__imp_GetProcessHeap
0x140012a81  mov     edx, 8; dwFlags
0x140012a86  mov     r8d, 208h; dwBytes
0x140012a8c  mov     rcx, rax; hHeap
0x140012a8f  call    cs:__imp_HeapAlloc
0x140012a95  mov     rdi, rax
0x140012a98  test    rax, rax
0x140012a9b  jnz     short loc_140012AA7
0x140012a9d  mov     ebx, 8007000Eh
0x140012aa2  jmp     loc_140012B77
0x140012aa7  lea     rax, aEtag; "etag"
0x140012aae  mov     r9, rbx
0x140012ab1  lea     r8, aSS; "%s.%s"
0x140012ab8  mov     [rsp+58h+lpOverlapped], rax
0x140012abd  mov     edx, 104h; unsigned __int64
0x140012ac2  mov     rcx, rdi; unsigned __int16 *
0x140012ac5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012aca  mov     ebx, eax
0x140012acc  test    eax, eax
0x140012ace  js      loc_140012B63
0x140012ad4  mov     r9d, 2
0x140012ada  mov     [rsp+58h+lpOverlapped], 0
0x140012ae3  mov     edx, 40000000h
0x140012ae8  mov     rcx, rdi
0x140012aeb  lea     r8d, [r9-1]
0x140012aef  call    cs:__imp_CreateFile2
0x140012af5  mov     rbp, rax
0x140012af8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140012afc  jnz     short loc_140012B15
0x140012afe  call    cs:__imp_GetLastError
0x140012b04  mov     ebx, eax
0x140012b06  test    eax, eax
0x140012b08  jle     short loc_140012B63
0x140012b0a  movzx   ebx, ax
0x140012b0d  or      ebx, 80070000h
0x140012b13  jmp     short loc_140012B63
0x140012b15  mov     edx, 104h; MaxCount
0x140012b1a  mov     rcx, rsi; Source
0x140012b1d  call    cs:__imp_wcsnlen
0x140012b23  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140012b28  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x140012b31  mov     rdx, rsi; lpBuffer
0x140012b34  mov     rcx, rbp; hFile
0x140012b37  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x140012b3b  call    cs:__imp_WriteFile
0x140012b41  test    eax, eax
0x140012b43  jnz     short loc_140012B5A
0x140012b45  call    cs:__imp_GetLastError
0x140012b4b  mov     ebx, eax
0x140012b4d  test    eax, eax
0x140012b4f  jle     short loc_140012B5A
0x140012b51  movzx   ebx, ax
0x140012b54  or      ebx, 80070000h
0x140012b5a  mov     rcx, rbp; hObject
0x140012b5d  call    cs:__imp_CloseHandle
0x140012b63  call    cs:__imp_GetProcessHeap
0x140012b69  mov     r8, rdi; lpMem
0x140012b6c  xor     edx, edx; dwFlags
0x140012b6e  mov     rcx, rax; hHeap
0x140012b71  call    cs:__imp_HeapFree
0x140012b77  mov     eax, ebx
0x140012b79  add     rsp, 38h
0x140012b7d  pop     rdi
0x140012b7e  pop     rsi
0x140012b7f  pop     rbp
0x140012b80  pop     rbx
0x140012b81  retn
```
