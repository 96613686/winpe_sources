# LsDisplayString(ushort const *,int)

- ea: `0x140001fc4`
- end: `0x140002138`
- name: `?LsDisplayString@@YAXPEBGH@Z`
- size: `372`
- prototype: `void __fastcall(LPCWCH lpWideCharStr, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001e14`
- `0x140001f34`

## callees

- `0x140001fc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400020ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400020ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002119`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400020a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000210b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400020a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000210b`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x140002037`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x140002037`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x140002075`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x140002075`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000206a`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000206a`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140001ff0`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140001ff0`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x140002009`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x140002009`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140002105`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140002105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002041`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000209c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400020e7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000209c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400020e7`

## pseudocode

```c
void __fastcall LsDisplayString(LPCWCH lpWideCharStr, int a2)
{
  HANDLE StdHandle; // rax
  __int64 v4; // rdi
  void *v5; // rsi
  DWORD FileType; // ebx
  UINT ConsoleOutputCP; // r15d
  unsigned int cbMultiByte; // r14d
  HANDLE ProcessHeap; // rax
  CHAR *v10; // rax
  CHAR *v11; // rbx
  int v12; // eax
  HANDLE v13; // rax
  DWORD NumberOfCharsWritten; // [rsp+78h] [rbp+10h] BYREF
  DWORD Mode; // [rsp+80h] [rbp+18h] BYREF

  Mode = 0;
  NumberOfCharsWritten = 0;
  StdHandle = GetStdHandle(-(a2 != 0) - 11);
  v4 = -1;
  v5 = StdHandle;
  if ( StdHandle != (HANDLE)-1LL )
  {
    FileType = GetFileType(StdHandle);
    if ( FileType || !GetLastError() )
    {
      if ( (FileType & 0xFFFF7FFF) == 2 && (GetConsoleMode(v5, &Mode) || GetLastError() != 6) )
      {
        do
          ++v4;
        while ( lpWideCharStr[v4] );
        WriteConsoleW(v5, lpWideCharStr, v4, &NumberOfCharsWritten, 0);
      }
      else
      {
        ConsoleOutputCP = GetConsoleOutputCP();
        cbMultiByte = WideCharToMultiByte(ConsoleOutputCP, 0, lpWideCharStr, -1, 0, 0, 0, 0);
        if ( cbMultiByte )
        {
          ProcessHeap = GetProcessHeap();
          v10 = (CHAR *)HeapAlloc(ProcessHeap, 8u, cbMultiByte);
          v11 = v10;
          if ( v10 )
          {
            v12 = WideCharToMultiByte(ConsoleOutputCP, 0, lpWideCharStr, -1, v10, cbMultiByte, 0, 0);
            if ( v12 )
              WriteFile(v5, v11, v12 - 1, &NumberOfCharsWritten, 0);
            v13 = GetProcessHeap();
            HeapFree(v13, 0, v11);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140001fc4  mov     rax, rsp
0x140001fc7  mov     [rax+8], rbx
0x140001fcb  mov     [rax+20h], rbp
0x140001fcf  push    rsi
0x140001fd0  push    rdi
0x140001fd1  push    r12
0x140001fd3  push    r14
0x140001fd5  push    r15
0x140001fd7  sub     rsp, 40h
0x140001fdb  xor     r12d, r12d
0x140001fde  mov     rbp, rcx
0x140001fe1  neg     edx
0x140001fe3  mov     [rax+18h], r12d
0x140001fe7  mov     [rax+10h], r12d
0x140001feb  sbb     ecx, ecx
0x140001fed  add     ecx, 0FFFFFFF5h; nStdHandle
0x140001ff0  call    cs:__imp_GetStdHandle
0x140001ff6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140001ffa  mov     rsi, rax
0x140001ffd  cmp     rax, rdi
0x140002000  jz      loc_14000211F
0x140002006  mov     rcx, rax; hFile
0x140002009  call    cs:__imp_GetFileType
0x14000200f  mov     ebx, eax
0x140002011  test    eax, eax
0x140002013  jnz     short loc_140002023
0x140002015  call    cs:__imp_GetLastError
0x14000201b  test    eax, eax
0x14000201d  jnz     loc_14000211F
0x140002023  btr     ebx, 0Fh
0x140002027  cmp     ebx, 2
0x14000202a  jnz     short loc_140002075
0x14000202c  lea     rdx, [rsp+68h+Mode]; lpMode
0x140002034  mov     rcx, rsi; hConsoleHandle
0x140002037  call    cs:__imp_GetConsoleMode
0x14000203d  test    eax, eax
0x14000203f  jnz     short loc_14000204C
0x140002041  call    cs:__imp_GetLastError
0x140002047  cmp     eax, 6
0x14000204a  jz      short loc_140002075
0x14000204c  inc     rdi
0x14000204f  cmp     [rbp+rdi*2+0], r12w
0x140002055  jnz     short loc_14000204C
0x140002057  lea     r9, [rsp+68h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14000205c  mov     [rsp+68h+lpReserved], r12; lpReserved
0x140002061  mov     r8d, edi; nNumberOfCharsToWrite
0x140002064  mov     rdx, rbp; lpBuffer
0x140002067  mov     rcx, rsi; hConsoleOutput
0x14000206a  call    cs:__imp_WriteConsoleW
0x140002070  jmp     loc_14000211F
0x140002075  call    cs:__imp_GetConsoleOutputCP
0x14000207b  mov     [rsp+68h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140002080  mov     r9d, edi; cchWideChar
0x140002083  mov     [rsp+68h+lpDefaultChar], r12; lpDefaultChar
0x140002088  mov     ecx, eax; CodePage
0x14000208a  mov     [rsp+68h+cbMultiByte], r12d; cbMultiByte
0x14000208f  mov     r8, rbp; lpWideCharStr
0x140002092  xor     edx, edx; dwFlags
0x140002094  mov     [rsp+68h+lpReserved], r12; lpMultiByteStr
0x140002099  mov     r15d, eax
0x14000209c  call    cs:__imp_WideCharToMultiByte
0x1400020a2  mov     r14d, eax
0x1400020a5  test    eax, eax
0x1400020a7  jz      short loc_14000211F
0x1400020a9  call    cs:__imp_GetProcessHeap
0x1400020af  mov     r8d, r14d; dwBytes
0x1400020b2  mov     edx, 8; dwFlags
0x1400020b7  mov     rcx, rax; hHeap
0x1400020ba  call    cs:__imp_HeapAlloc
0x1400020c0  mov     rbx, rax
0x1400020c3  test    rax, rax
0x1400020c6  jz      short loc_14000211F
0x1400020c8  mov     [rsp+68h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1400020cd  mov     r9d, edi; cchWideChar
0x1400020d0  mov     [rsp+68h+lpDefaultChar], r12; lpDefaultChar
0x1400020d5  mov     r8, rbp; lpWideCharStr
0x1400020d8  mov     [rsp+68h+cbMultiByte], r14d; cbMultiByte
0x1400020dd  xor     edx, edx; dwFlags
0x1400020df  mov     ecx, r15d; CodePage
0x1400020e2  mov     [rsp+68h+lpReserved], rax; lpMultiByteStr
0x1400020e7  call    cs:__imp_WideCharToMultiByte
0x1400020ed  test    eax, eax
0x1400020ef  jz      short loc_14000210B
0x1400020f1  lea     r8d, [rax-1]; nNumberOfBytesToWrite
0x1400020f5  mov     [rsp+68h+lpReserved], r12; lpOverlapped
0x1400020fa  lea     r9, [rsp+68h+NumberOfCharsWritten]; lpNumberOfBytesWritten
0x1400020ff  mov     rdx, rbx; lpBuffer
0x140002102  mov     rcx, rsi; hFile
0x140002105  call    cs:__imp_WriteFile
0x14000210b  call    cs:__imp_GetProcessHeap
0x140002111  mov     r8, rbx; lpMem
0x140002114  xor     edx, edx; dwFlags
0x140002116  mov     rcx, rax; hHeap
0x140002119  call    cs:__imp_HeapFree
0x14000211f  lea     r11, [rsp+68h+var_28]
0x140002124  mov     rbx, [r11+30h]
0x140002128  mov     rbp, [r11+48h]
0x14000212c  mov     rsp, r11
0x14000212f  pop     r15
0x140002131  pop     r14
0x140002133  pop     r12
0x140002135  pop     rdi
0x140002136  pop     rsi
0x140002137  retn
```
