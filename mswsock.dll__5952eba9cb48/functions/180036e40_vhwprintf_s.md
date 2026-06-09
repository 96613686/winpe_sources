# vhwprintf_s

- ea: `0x180036e40`
- end: `0x18003707a`
- name: `vhwprintf_s`
- size: `570`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Format, va_list ArgList)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180036e10`

## callees

- `0x180022c40`
- `0x180036e40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180036e7a`
- `ntdll!RtlAllocateHeap` at `0x180036ecc`
- `ntdll!RtlAllocateHeap` at `0x180036e7a`
- `ntdll!RtlAllocateHeap` at `0x180036ecc`
- `ntdll!RtlReAllocateHeap` at `0x180036f8c`
- `ntdll!RtlReAllocateHeap` at `0x180036f8c`
- `ntdll!RtlFreeHeap` at `0x180036fc4`
- `ntdll!RtlFreeHeap` at `0x180037058`
- `ntdll!RtlFreeHeap` at `0x180036fc4`
- `ntdll!RtlFreeHeap` at `0x180037058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f21`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180036f09`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180036f63`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180036ffe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180036f09`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180036f63`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180036ffe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037030`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036e63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036eb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036f75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036fb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036e63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036eb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036f75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036fb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037044`

## pseudocode

```c
__int64 __fastcall vhwprintf_s(HANDLE hFile, wchar_t *Format, va_list ArgList)
{
  HANDLE ProcessHeap; // rax
  wchar_t *Heap; // rax
  WCHAR *v8; // rbp
  int cbMultiByte; // edi
  HANDLE v11; // rax
  CHAR *lpMultiByteStr; // rax
  CHAR *v13; // rsi
  DWORD v14; // eax
  DWORD v15; // ebx
  HANDLE v16; // rax
  CHAR *v17; // rcx
  HANDLE v18; // rax
  HANDLE v19; // rax
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  ProcessHeap = GetProcessHeap();
  Heap = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, 0x1000u);
  v8 = Heap;
  if ( !Heap )
    return 0xFFFFFFFFLL;
  cbMultiByte = vswprintf_s(Heap, 0x7FFu, Format, ArgList);
  if ( cbMultiByte > 0 )
  {
    ++cbMultiByte;
    v11 = GetProcessHeap();
    lpMultiByteStr = (CHAR *)RtlAllocateHeap(v11, 0, cbMultiByte);
    v13 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      v14 = WideCharToMultiByte(0, 0, v8, cbMultiByte, lpMultiByteStr, cbMultiByte, 0, 0);
      NumberOfBytesWritten = v14;
      if ( !v14 )
      {
        if ( GetLastError() == 122 )
        {
          v15 = WideCharToMultiByte(0, 0, v8, cbMultiByte, 0, 0, 0, 0);
          NumberOfBytesWritten = v15;
          v16 = GetProcessHeap();
          v17 = (CHAR *)RtlReAllocateHeap(v16, 0, v13, v15);
          if ( !v17 )
          {
            NumberOfBytesWritten = 0;
LABEL_9:
            cbMultiByte = -1;
            goto LABEL_10;
          }
          v13 = v17;
          v14 = WideCharToMultiByte(0, 0, v8, cbMultiByte, v17, NumberOfBytesWritten, 0, 0);
          NumberOfBytesWritten = v14;
        }
        else
        {
          v14 = NumberOfBytesWritten;
        }
        if ( !v14 )
          goto LABEL_9;
      }
      WriteFile(hFile, v13, v14 - 1, &NumberOfBytesWritten, 0);
LABEL_10:
      if ( v13 )
      {
        v18 = GetProcessHeap();
        RtlFreeHeap(v18, 0, v13);
      }
      goto LABEL_17;
    }
    cbMultiByte = -1;
  }
LABEL_17:
  v19 = GetProcessHeap();
  RtlFreeHeap(v19, 0, v8);
  return (unsigned int)cbMultiByte;
}

```

## disassembly

```asm
0x180036e40  mov     [rsp+arg_0], rbx
0x180036e45  mov     [rsp+arg_8], rbp
0x180036e4a  push    rsi
0x180036e4b  push    rdi
0x180036e4c  push    r14
0x180036e4e  sub     rsp, 40h
0x180036e52  mov     rbx, r8
0x180036e55  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180036e5d  mov     rdi, rdx
0x180036e60  mov     r14, rcx
0x180036e63  call    cs:__imp_GetProcessHeap
0x180036e6a  nop     dword ptr [rax+rax+00h]
0x180036e6f  xor     edx, edx; Flags
0x180036e71  mov     r8d, 1000h; Size
0x180036e77  mov     rcx, rax; HeapHandle
0x180036e7a  call    cs:__imp_RtlAllocateHeap
0x180036e81  nop     dword ptr [rax+rax+00h]
0x180036e86  mov     rbp, rax
0x180036e89  test    rax, rax
0x180036e8c  jnz     short loc_180036E96
0x180036e8e  or      eax, 0FFFFFFFFh
0x180036e91  jmp     loc_180037066
0x180036e96  mov     r9, rbx; ArgList
0x180036e99  mov     r8, rdi; Format
0x180036e9c  mov     edx, 7FFh; BufferCount
0x180036ea1  mov     rcx, rbp; Buffer
0x180036ea4  call    vswprintf_s
0x180036ea9  mov     edi, eax
0x180036eab  test    eax, eax
0x180036ead  jle     loc_180037044
0x180036eb3  inc     edi
0x180036eb5  movsxd  rbx, edi
0x180036eb8  call    cs:__imp_GetProcessHeap
0x180036ebf  nop     dword ptr [rax+rax+00h]
0x180036ec4  mov     r8, rbx; Size
0x180036ec7  xor     edx, edx; Flags
0x180036ec9  mov     rcx, rax; HeapHandle
0x180036ecc  call    cs:__imp_RtlAllocateHeap
0x180036ed3  nop     dword ptr [rax+rax+00h]
0x180036ed8  mov     rsi, rax
0x180036edb  test    rax, rax
0x180036ede  jz      loc_180037041
0x180036ee4  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180036eed  mov     r9d, edi; cchWideChar
0x180036ef0  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x180036ef9  mov     r8, rbp; lpWideCharStr
0x180036efc  mov     [rsp+58h+cbMultiByte], edi; cbMultiByte
0x180036f00  xor     edx, edx; dwFlags
0x180036f02  xor     ecx, ecx; CodePage
0x180036f04  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x180036f09  call    cs:__imp_WideCharToMultiByte
0x180036f10  nop     dword ptr [rax+rax+00h]
0x180036f15  mov     [rsp+58h+NumberOfBytesWritten], eax
0x180036f19  test    eax, eax
0x180036f1b  jnz     loc_180037018
0x180036f21  call    cs:__imp_GetLastError
0x180036f28  nop     dword ptr [rax+rax+00h]
0x180036f2d  cmp     eax, 7Ah ; 'z'
0x180036f30  jnz     loc_180037010
0x180036f36  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180036f3f  mov     r9d, edi; cchWideChar
0x180036f42  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x180036f4b  mov     r8, rbp; lpWideCharStr
0x180036f4e  mov     [rsp+58h+cbMultiByte], 0; cbMultiByte
0x180036f56  xor     edx, edx; dwFlags
0x180036f58  xor     ecx, ecx; CodePage
0x180036f5a  mov     [rsp+58h+lpMultiByteStr], 0; lpMultiByteStr
0x180036f63  call    cs:__imp_WideCharToMultiByte
0x180036f6a  nop     dword ptr [rax+rax+00h]
0x180036f6f  mov     ebx, eax
0x180036f71  mov     [rsp+58h+NumberOfBytesWritten], ebx
0x180036f75  call    cs:__imp_GetProcessHeap
0x180036f7c  nop     dword ptr [rax+rax+00h]
0x180036f81  mov     r9d, ebx; Size
0x180036f84  mov     r8, rsi; Ptr
0x180036f87  mov     rcx, rax; Heap
0x180036f8a  xor     edx, edx; Flags
0x180036f8c  call    cs:__imp_RtlReAllocateHeap
0x180036f93  nop     dword ptr [rax+rax+00h]
0x180036f98  mov     rcx, rax
0x180036f9b  test    rax, rax
0x180036f9e  jnz     short loc_180036FD2
0x180036fa0  mov     [rsp+58h+NumberOfBytesWritten], eax
0x180036fa4  or      edi, 0FFFFFFFFh
0x180036fa7  test    rsi, rsi
0x180036faa  jz      loc_180037044
0x180036fb0  call    cs:__imp_GetProcessHeap
0x180036fb7  nop     dword ptr [rax+rax+00h]
0x180036fbc  mov     r8, rsi; P
0x180036fbf  xor     edx, edx; Flags
0x180036fc1  mov     rcx, rax; HeapHandle
0x180036fc4  call    cs:__imp_RtlFreeHeap
0x180036fcb  nop     dword ptr [rax+rax+00h]
0x180036fd0  jmp     short loc_180037044
0x180036fd2  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x180036fd6  mov     rsi, rcx
0x180036fd9  mov     [rsp+58h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180036fe2  mov     r9d, edi; cchWideChar
0x180036fe5  mov     [rsp+58h+lpDefaultChar], 0; lpDefaultChar
0x180036fee  mov     r8, rbp; lpWideCharStr
0x180036ff1  mov     [rsp+58h+cbMultiByte], eax; cbMultiByte
0x180036ff5  xor     edx, edx; dwFlags
0x180036ff7  mov     [rsp+58h+lpMultiByteStr], rcx; lpMultiByteStr
0x180036ffc  xor     ecx, ecx; CodePage
0x180036ffe  call    cs:__imp_WideCharToMultiByte
0x180037005  nop     dword ptr [rax+rax+00h]
0x18003700a  mov     [rsp+58h+NumberOfBytesWritten], eax
0x18003700e  jmp     short loc_180037014
0x180037010  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x180037014  test    eax, eax
0x180037016  jz      short loc_180036FA4
0x180037018  lea     r8d, [rax-1]; nNumberOfBytesToWrite
0x18003701c  mov     [rsp+58h+lpMultiByteStr], 0; lpOverlapped
0x180037025  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003702a  mov     rdx, rsi; lpBuffer
0x18003702d  mov     rcx, r14; hFile
0x180037030  call    cs:__imp_WriteFile
0x180037037  nop     dword ptr [rax+rax+00h]
0x18003703c  jmp     loc_180036FA7
0x180037041  or      edi, 0FFFFFFFFh
0x180037044  call    cs:__imp_GetProcessHeap
0x18003704b  nop     dword ptr [rax+rax+00h]
0x180037050  mov     r8, rbp; P
0x180037053  xor     edx, edx; Flags
0x180037055  mov     rcx, rax; HeapHandle
0x180037058  call    cs:__imp_RtlFreeHeap
0x18003705f  nop     dword ptr [rax+rax+00h]
0x180037064  mov     eax, edi
0x180037066  mov     rbx, [rsp+58h+arg_0]
0x18003706b  mov     rbp, [rsp+58h+arg_8]
0x180037070  add     rsp, 40h
0x180037074  pop     r14
0x180037076  pop     rdi
0x180037077  pop     rsi
0x180037078  retn
```
