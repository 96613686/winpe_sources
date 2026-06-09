# ShowMessage

- ea: `0x14000e864`
- end: `0x14000ec25`
- name: `ShowMessage`
- size: `961`
- prototype: `__int64 __fastcall(FILE *Stream, LPCWSTR lpString)`
- caller_count: `13`
- callee_count: `7`
- tags: ``

## callers

- `0x140002b6c`
- `0x140002d40`
- `0x140003068`
- `0x140005c78`
- `0x140005ef0`
- `0x14000672c`
- `0x140008cbc`
- `0x140009a50`
- `0x140009b2c`
- `0x14000aa4c`
- `0x14000e75c`
- `0x14000e798`
- `0x14000ec2c`

## callees

- `0x140001bb2`
- `0x140001cc6`
- `0x140001d28`
- `0x14000ddc4`
- `0x14000e3bc`
- `0x14000e75c`
- `0x14000e864`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14000eb8e`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14000eb8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000eac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ebf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000eac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ebf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ec05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ec05`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000e9c7`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000e9ec`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000eb02`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000ebc0`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000ebe5`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000e9c7`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000e9ec`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000eb02`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000ebc0`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000ebe5`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14000e8d8`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14000e8d8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000ea90`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000eb5c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000ea90`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000eb5c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e8f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e947`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000ea1a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e8f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e947`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000ea1a`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000e916`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000e983`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000e916`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000e983`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000ea66`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000eb28`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000ea66`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000eb28`

## pseudocode

```c
__int64 __fastcall ShowMessage(FILE *Stream, LPCWSTR lpString)
{
  DWORD v4; // ecx
  HANDLE StdHandle; // rax
  void *v6; // r14
  DWORD v7; // ebx
  unsigned int v8; // ebp
  unsigned int i; // ebx
  DWORD v10; // edi
  FILE *v12; // rax
  FILE *v13; // rax
  DWORD v14; // ecx
  unsigned int v15; // r14d
  unsigned int v16; // ebp
  unsigned int v17; // ebx
  UINT ConsoleOutputCP; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  FILE *v21; // rax
  UINT v22; // eax
  FILE *v23; // rax
  FILE *v24; // rax
  DWORD NumberOfCharsWritten; // [rsp+90h] [rbp+8h] BYREF

  NumberOfCharsWritten = 0;
  if ( Stream && lpString )
  {
    if ( (unsigned int)IsConsoleFile() != 1 )
    {
      v15 = lstrlenW(lpString);
      memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
      v16 = 0;
      while ( v15 > v16 )
      {
        NumberOfCharsWritten = 0;
        v17 = v15 - v16;
        if ( v15 - v16 > 0xFF )
          v17 = 255;
        while ( 1 )
        {
          ConsoleOutputCP = GetConsoleOutputCP();
          v19 = WideCharToMultiByte(ConsoleOutputCP, 0, &lpString[v16], v17, 0, 0, 0, 0);
          if ( !v19 )
          {
            v24 = o___acrt_iob_func_0(1u);
            ShowLastError(v24);
            ReleaseGlobals();
            ExitProcess(1u);
          }
          if ( v19 <= 0xFF )
            break;
          v20 = v19 - 255;
          if ( v20 <= 3 )
            --v17;
          else
            v17 -= v20 >> 1;
          NumberOfCharsWritten = 0;
          if ( !v17 )
          {
            if ( !GetLastError() )
              SetLastError(0x42Bu);
            v21 = o___acrt_iob_func_0(1u);
            ShowLastError(v21);
            ReleaseGlobals();
            ExitProcess(1u);
          }
        }
        if ( v19 < v17 )
          v17 = v19;
        memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
        v22 = GetConsoleOutputCP();
        NumberOfCharsWritten = WideCharToMultiByte(v22, 0, &lpString[v16], v17, MultiByteStr, 255, 0, 0);
        if ( !NumberOfCharsWritten )
        {
          v23 = o___acrt_iob_func_0(1u);
          ShowLastError(v23);
          ReleaseGlobals();
          ExitProcess(1u);
        }
        v16 += v17;
        fprintf(Stream, "%s", MultiByteStr);
        fflush(Stream);
      }
      return 1;
    }
    if ( Stream == o___acrt_iob_func_0(1u) )
    {
      v4 = -11;
LABEL_8:
      StdHandle = GetStdHandle(v4);
      NumberOfCharsWritten = 0;
      v6 = StdHandle;
      v7 = lstrlenW(lpString);
      if ( !WriteConsoleW(v6, lpString, v7, &NumberOfCharsWritten, 0) || v7 != NumberOfCharsWritten )
      {
        if ( GetLastError() != 8 )
        {
          v13 = o___acrt_iob_func_0(2u);
          ShowLastError(v13);
          ReleaseGlobals();
          ExitProcess(1u);
        }
        v8 = lstrlenW(lpString);
        for ( i = 0; i < v8; i += 1024 )
        {
          v10 = v8 - i;
          if ( v8 - i > 0x400 )
            v10 = 1024;
          if ( !WriteConsoleW(v6, &lpString[i], v10, &NumberOfCharsWritten, 0) || v10 != NumberOfCharsWritten )
          {
            v12 = o___acrt_iob_func_0(2u);
            ShowLastError(v12);
            ReleaseGlobals();
            ExitProcess(1u);
          }
        }
      }
      return 1;
    }
    if ( Stream == o___acrt_iob_func_0(2u) )
    {
      v4 = -12;
      goto LABEL_8;
    }
    if ( !GetLastError() )
    {
      v14 = 1067;
LABEL_43:
      SetLastError(v14);
    }
  }
  else if ( !GetLastError() )
  {
    v14 = 87;
    goto LABEL_43;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e864  mov     rax, rsp
0x14000e867  push    rbx
0x14000e868  push    rbp
0x14000e869  push    rsi
0x14000e86a  push    rdi
0x14000e86b  push    r12
0x14000e86d  push    r13
0x14000e86f  push    r14
0x14000e871  push    r15
0x14000e873  sub     rsp, 48h
0x14000e877  xor     r12d, r12d
0x14000e87a  mov     rsi, rdx
0x14000e87d  mov     [rax+8], r12d
0x14000e881  mov     rdi, rcx
0x14000e884  test    rcx, rcx
0x14000e887  jz      loc_14000EBF2
0x14000e88d  test    rdx, rdx
0x14000e890  jz      loc_14000EBF2
0x14000e896  call    IsConsoleFile
0x14000e89b  lea     r13d, [r12+1]
0x14000e8a0  cmp     eax, r13d
0x14000e8a3  jnz     loc_14000EA17
0x14000e8a9  mov     ecx, r13d; Ix
0x14000e8ac  call    _o___acrt_iob_func_0
0x14000e8b1  lea     r15d, [r12+2]
0x14000e8b6  cmp     rdi, rax
0x14000e8b9  jnz     short loc_14000E8C2
0x14000e8bb  mov     ecx, 0FFFFFFF5h
0x14000e8c0  jmp     short loc_14000E8D8
0x14000e8c2  mov     ecx, r15d; Ix
0x14000e8c5  call    _o___acrt_iob_func_0
0x14000e8ca  cmp     rdi, rax
0x14000e8cd  jnz     loc_14000E9F9
0x14000e8d3  mov     ecx, 0FFFFFFF4h; nStdHandle
0x14000e8d8  call    cs:__imp_GetStdHandle
0x14000e8df  nop     dword ptr [rax+rax+00h]
0x14000e8e4  mov     rcx, rsi; lpString
0x14000e8e7  mov     [rsp+88h+NumberOfCharsWritten], r12d
0x14000e8ef  mov     r14, rax
0x14000e8f2  call    cs:__imp_lstrlenW
0x14000e8f9  nop     dword ptr [rax+rax+00h]
0x14000e8fe  lea     r9, [rsp+88h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14000e906  mov     [rsp+88h+lpReserved], r12; lpReserved
0x14000e90b  mov     r8d, eax; nNumberOfCharsToWrite
0x14000e90e  mov     rdx, rsi; lpBuffer
0x14000e911  mov     rcx, r14; hConsoleOutput
0x14000e914  mov     ebx, eax
0x14000e916  call    cs:__imp_WriteConsoleW
0x14000e91d  nop     dword ptr [rax+rax+00h]
0x14000e922  test    eax, eax
0x14000e924  jz      short loc_14000E92F
0x14000e926  cmp     ebx, [rsp+88h+NumberOfCharsWritten]
0x14000e92d  jz      short loc_14000E9A7
0x14000e92f  call    cs:__imp_GetLastError
0x14000e936  nop     dword ptr [rax+rax+00h]
0x14000e93b  cmp     eax, 8
0x14000e93e  jnz     loc_14000E9D4
0x14000e944  mov     rcx, rsi; lpString
0x14000e947  call    cs:__imp_lstrlenW
0x14000e94e  nop     dword ptr [rax+rax+00h]
0x14000e953  mov     ebp, eax
0x14000e955  mov     ebx, r12d
0x14000e958  test    eax, eax
0x14000e95a  jz      short loc_14000E9A7
0x14000e95c  mov     eax, 400h
0x14000e961  mov     edi, ebp
0x14000e963  mov     [rsp+88h+lpReserved], r12; lpReserved
0x14000e968  sub     edi, ebx
0x14000e96a  lea     r9, [rsp+88h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14000e972  cmp     edi, eax
0x14000e974  mov     rcx, r14; hConsoleOutput
0x14000e977  cmova   edi, eax
0x14000e97a  mov     eax, ebx
0x14000e97c  mov     r8d, edi; nNumberOfCharsToWrite
0x14000e97f  lea     rdx, [rsi+rax*2]; lpBuffer
0x14000e983  call    cs:__imp_WriteConsoleW
0x14000e98a  nop     dword ptr [rax+rax+00h]
0x14000e98f  test    eax, eax
0x14000e991  jz      short loc_14000E9AF
0x14000e993  cmp     edi, [rsp+88h+NumberOfCharsWritten]
0x14000e99a  jnz     short loc_14000E9AF
0x14000e99c  mov     eax, 400h
0x14000e9a1  add     ebx, eax
0x14000e9a3  cmp     ebx, ebp
0x14000e9a5  jb      short loc_14000E961
0x14000e9a7  mov     eax, r13d
0x14000e9aa  jmp     loc_14000EC13
0x14000e9af  mov     ecx, r15d; Ix
0x14000e9b2  call    _o___acrt_iob_func_0
0x14000e9b7  mov     rcx, rax
0x14000e9ba  call    ShowLastError
0x14000e9bf  call    ReleaseGlobals
0x14000e9c4  mov     ecx, r13d; uExitCode
0x14000e9c7  call    cs:__imp_ExitProcess
0x14000e9d4  mov     ecx, r15d; Ix
0x14000e9d7  call    _o___acrt_iob_func_0
0x14000e9dc  mov     rcx, rax
0x14000e9df  call    ShowLastError
0x14000e9e4  call    ReleaseGlobals
0x14000e9e9  mov     ecx, r13d; uExitCode
0x14000e9ec  call    cs:__imp_ExitProcess
0x14000e9f9  call    cs:__imp_GetLastError
0x14000ea00  nop     dword ptr [rax+rax+00h]
0x14000ea05  test    eax, eax
0x14000ea07  jnz     loc_14000EC11
0x14000ea0d  mov     ecx, 42Bh
0x14000ea12  jmp     loc_14000EC05
0x14000ea17  mov     rcx, rsi; lpString
0x14000ea1a  call    cs:__imp_lstrlenW
0x14000ea21  nop     dword ptr [rax+rax+00h]
0x14000ea26  xor     edx, edx; Val
0x14000ea28  lea     rcx, MultiByteStr; void *
0x14000ea2f  mov     r8d, 100h; Size
0x14000ea35  mov     r14d, eax
0x14000ea38  call    memset_0
0x14000ea3d  mov     ebp, r12d
0x14000ea40  test    r14d, r14d
0x14000ea43  jz      loc_14000E9A7
0x14000ea49  mov     ecx, 0FFh
0x14000ea4e  mov     eax, ebp
0x14000ea50  mov     ebx, r14d
0x14000ea53  mov     [rsp+88h+NumberOfCharsWritten], r12d
0x14000ea5b  sub     ebx, ebp
0x14000ea5d  cmp     ebx, ecx
0x14000ea5f  lea     r15, [rsi+rax*2]
0x14000ea63  cmova   ebx, ecx
0x14000ea66  call    cs:__imp_GetConsoleOutputCP
0x14000ea6d  nop     dword ptr [rax+rax+00h]
0x14000ea72  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x14000ea77  mov     r9d, ebx; cchWideChar
0x14000ea7a  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x14000ea7f  mov     ecx, eax; CodePage
0x14000ea81  mov     [rsp+88h+cbMultiByte], r12d; cbMultiByte
0x14000ea86  mov     r8, r15; lpWideCharStr
0x14000ea89  xor     edx, edx; dwFlags
0x14000ea8b  mov     [rsp+88h+lpReserved], r12; lpMultiByteStr
0x14000ea90  call    cs:__imp_WideCharToMultiByte
0x14000ea97  nop     dword ptr [rax+rax+00h]
0x14000ea9c  test    eax, eax
0x14000ea9e  jz      loc_14000EBCD
0x14000eaa4  cmp     eax, 0FFh
0x14000eaa9  jbe     short loc_14000EB0F
0x14000eaab  add     eax, 0FFFFFF01h
0x14000eab0  cmp     eax, 3
0x14000eab3  jbe     short loc_14000EABB
0x14000eab5  shr     eax, 1
0x14000eab7  sub     ebx, eax
0x14000eab9  jmp     short loc_14000EABD
0x14000eabb  dec     ebx
0x14000eabd  mov     [rsp+88h+NumberOfCharsWritten], r12d
0x14000eac5  test    ebx, ebx
0x14000eac7  jnz     short loc_14000EA66
0x14000eac9  call    cs:__imp_GetLastError
0x14000ead0  nop     dword ptr [rax+rax+00h]
0x14000ead5  test    eax, eax
0x14000ead7  jnz     short loc_14000EAEA
0x14000ead9  mov     ecx, 42Bh; dwErrCode
0x14000eade  call    cs:__imp_SetLastError
0x14000eae5  nop     dword ptr [rax+rax+00h]
0x14000eaea  mov     ecx, r13d; Ix
0x14000eaed  call    _o___acrt_iob_func_0
0x14000eaf2  mov     rcx, rax
0x14000eaf5  call    ShowLastError
0x14000eafa  call    ReleaseGlobals
0x14000eaff  mov     ecx, r13d; uExitCode
0x14000eb02  call    cs:__imp_ExitProcess
0x14000eb0f  cmp     eax, ebx
0x14000eb11  lea     rcx, MultiByteStr; void *
0x14000eb18  mov     r8d, 100h; Size
0x14000eb1e  cmovb   ebx, eax
0x14000eb21  xor     edx, edx; Val
0x14000eb23  call    memset_0
0x14000eb28  call    cs:__imp_GetConsoleOutputCP
0x14000eb2f  nop     dword ptr [rax+rax+00h]
0x14000eb34  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x14000eb39  mov     r9d, ebx; cchWideChar
0x14000eb3c  mov     ecx, eax; CodePage
0x14000eb3e  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x14000eb43  lea     rax, MultiByteStr
0x14000eb4a  mov     [rsp+88h+cbMultiByte], 0FFh; cbMultiByte
0x14000eb52  mov     r8, r15; lpWideCharStr
0x14000eb55  mov     [rsp+88h+lpReserved], rax; lpMultiByteStr
0x14000eb5a  xor     edx, edx; dwFlags
0x14000eb5c  call    cs:__imp_WideCharToMultiByte
0x14000eb63  nop     dword ptr [rax+rax+00h]
0x14000eb68  mov     [rsp+88h+NumberOfCharsWritten], eax
0x14000eb6f  test    eax, eax
0x14000eb71  jz      short loc_14000EBA8
0x14000eb73  lea     r8, MultiByteStr
0x14000eb7a  mov     rcx, rdi; Stream
0x14000eb7d  lea     rdx, Format; "%s"
0x14000eb84  add     ebp, ebx
0x14000eb86  call    fprintf
0x14000eb8b  mov     rcx, rdi; Stream
0x14000eb8e  call    cs:__imp_fflush
0x14000eb95  nop     dword ptr [rax+rax+00h]
0x14000eb9a  cmp     r14d, ebp
0x14000eb9d  jbe     loc_14000E9A7
0x14000eba3  jmp     loc_14000EA49
0x14000eba8  mov     ecx, r13d; Ix
0x14000ebab  call    _o___acrt_iob_func_0
0x14000ebb0  mov     rcx, rax
0x14000ebb3  call    ShowLastError
0x14000ebb8  call    ReleaseGlobals
0x14000ebbd  mov     ecx, r13d; uExitCode
0x14000ebc0  call    cs:__imp_ExitProcess
0x14000ebcd  mov     ecx, r13d; Ix
0x14000ebd0  call    _o___acrt_iob_func_0
0x14000ebd5  mov     rcx, rax
0x14000ebd8  call    ShowLastError
0x14000ebdd  call    ReleaseGlobals
0x14000ebe2  mov     ecx, r13d; uExitCode
0x14000ebe5  call    cs:__imp_ExitProcess
0x14000ebf2  call    cs:__imp_GetLastError
0x14000ebf9  nop     dword ptr [rax+rax+00h]
0x14000ebfe  test    eax, eax
0x14000ec00  jnz     short loc_14000EC11
0x14000ec02  lea     ecx, [rax+57h]; dwErrCode
0x14000ec05  call    cs:__imp_SetLastError
0x14000ec0c  nop     dword ptr [rax+rax+00h]
0x14000ec11  xor     eax, eax
0x14000ec13  add     rsp, 48h
0x14000ec17  pop     r15
0x14000ec19  pop     r14
0x14000ec1b  pop     r13
0x14000ec1d  pop     r12
0x14000ec1f  pop     rdi
0x14000ec20  pop     rsi
0x14000ec21  pop     rbp
0x14000ec22  pop     rbx
0x14000ec23  retn
```
