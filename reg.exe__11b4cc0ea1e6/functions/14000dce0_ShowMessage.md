# ShowMessage

- ea: `0x14000dce0`
- end: `0x14000e018`
- name: `ShowMessage`
- size: `824`
- prototype: `__int64 __fastcall(FILE *Stream, LPCWSTR lpString)`
- caller_count: `13`
- callee_count: `7`
- tags: ``

## callers

- `0x140002a28`
- `0x140002bc0`
- `0x140002f30`
- `0x140005940`
- `0x140005bac`
- `0x140006394`
- `0x140008788`
- `0x1400094a0`
- `0x140009574`
- `0x14000a3f8`
- `0x14000dbe8`
- `0x14000dc24`
- `0x14000e020`

## callees

- `0x140001bb2`
- `0x140001cc6`
- `0x140001d28`
- `0x14000d3e8`
- `0x14000d8b4`
- `0x14000dbe8`
- `0x14000dce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14000dfa0`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14000dfa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000de41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000def9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000de41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000def9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dff2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000df08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000df08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfff`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000de1b`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000de3a`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000df26`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000dfcc`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000dfeb`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000de1b`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000de3a`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000df26`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000dfcc`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000dfeb`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14000dd54`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14000dd54`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000dec6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000df74`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000dec6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000df74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dd68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dda7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000de5c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dd68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000dda7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000de5c`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000dd86`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000dddd`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000dd86`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000dddd`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000dea2`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000df46`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000dea2`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x14000df46`

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
0x14000dce0  mov     rax, rsp
0x14000dce3  push    rbx
0x14000dce4  push    rbp
0x14000dce5  push    rsi
0x14000dce6  push    rdi
0x14000dce7  push    r12
0x14000dce9  push    r13
0x14000dceb  push    r14
0x14000dced  push    r15
0x14000dcef  sub     rsp, 48h
0x14000dcf3  xor     r12d, r12d
0x14000dcf6  mov     rsi, rdx
0x14000dcf9  mov     [rax+8], r12d
0x14000dcfd  mov     rdi, rcx
0x14000dd00  test    rcx, rcx
0x14000dd03  jz      loc_14000DFF2
0x14000dd09  test    rdx, rdx
0x14000dd0c  jz      loc_14000DFF2
0x14000dd12  call    IsConsoleFile
0x14000dd17  lea     r13d, [r12+1]
0x14000dd1c  cmp     eax, r13d
0x14000dd1f  jnz     loc_14000DE59
0x14000dd25  mov     ecx, r13d; Ix
0x14000dd28  call    _o___acrt_iob_func_0
0x14000dd2d  lea     r15d, [r12+2]
0x14000dd32  cmp     rdi, rax
0x14000dd35  jnz     short loc_14000DD3E
0x14000dd37  mov     ecx, 0FFFFFFF5h
0x14000dd3c  jmp     short loc_14000DD54
0x14000dd3e  mov     ecx, r15d; Ix
0x14000dd41  call    _o___acrt_iob_func_0
0x14000dd46  cmp     rdi, rax
0x14000dd49  jnz     loc_14000DE41
0x14000dd4f  mov     ecx, 0FFFFFFF4h; nStdHandle
0x14000dd54  call    cs:__imp_GetStdHandle
0x14000dd5a  mov     rcx, rsi; lpString
0x14000dd5d  mov     [rsp+88h+NumberOfCharsWritten], r12d
0x14000dd65  mov     r14, rax
0x14000dd68  call    cs:__imp_lstrlenW
0x14000dd6e  lea     r9, [rsp+88h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14000dd76  mov     [rsp+88h+lpReserved], r12; lpReserved
0x14000dd7b  mov     r8d, eax; nNumberOfCharsToWrite
0x14000dd7e  mov     rdx, rsi; lpBuffer
0x14000dd81  mov     rcx, r14; hConsoleOutput
0x14000dd84  mov     ebx, eax
0x14000dd86  call    cs:__imp_WriteConsoleW
0x14000dd8c  test    eax, eax
0x14000dd8e  jz      short loc_14000DD99
0x14000dd90  cmp     ebx, [rsp+88h+NumberOfCharsWritten]
0x14000dd97  jz      short loc_14000DDFB
0x14000dd99  call    cs:__imp_GetLastError
0x14000dd9f  cmp     eax, 8
0x14000dda2  jnz     short loc_14000DE22
0x14000dda4  mov     rcx, rsi; lpString
0x14000dda7  call    cs:__imp_lstrlenW
0x14000ddad  mov     ebp, eax
0x14000ddaf  mov     ebx, r12d
0x14000ddb2  test    eax, eax
0x14000ddb4  jz      short loc_14000DDFB
0x14000ddb6  mov     eax, 400h
0x14000ddbb  mov     edi, ebp
0x14000ddbd  mov     [rsp+88h+lpReserved], r12; lpReserved
0x14000ddc2  sub     edi, ebx
0x14000ddc4  lea     r9, [rsp+88h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14000ddcc  cmp     edi, eax
0x14000ddce  mov     rcx, r14; hConsoleOutput
0x14000ddd1  cmova   edi, eax
0x14000ddd4  mov     eax, ebx
0x14000ddd6  mov     r8d, edi; nNumberOfCharsToWrite
0x14000ddd9  lea     rdx, [rsi+rax*2]; lpBuffer
0x14000dddd  call    cs:__imp_WriteConsoleW
0x14000dde3  test    eax, eax
0x14000dde5  jz      short loc_14000DE03
0x14000dde7  cmp     edi, [rsp+88h+NumberOfCharsWritten]
0x14000ddee  jnz     short loc_14000DE03
0x14000ddf0  mov     eax, 400h
0x14000ddf5  add     ebx, eax
0x14000ddf7  cmp     ebx, ebp
0x14000ddf9  jb      short loc_14000DDBB
0x14000ddfb  mov     eax, r13d
0x14000ddfe  jmp     loc_14000E007
0x14000de03  mov     ecx, r15d; Ix
0x14000de06  call    _o___acrt_iob_func_0
0x14000de0b  mov     rcx, rax
0x14000de0e  call    ShowLastError
0x14000de13  call    ReleaseGlobals
0x14000de18  mov     ecx, r13d; uExitCode
0x14000de1b  call    cs:__imp_ExitProcess
0x14000de22  mov     ecx, r15d; Ix
0x14000de25  call    _o___acrt_iob_func_0
0x14000de2a  mov     rcx, rax
0x14000de2d  call    ShowLastError
0x14000de32  call    ReleaseGlobals
0x14000de37  mov     ecx, r13d; uExitCode
0x14000de3a  call    cs:__imp_ExitProcess
0x14000de41  call    cs:__imp_GetLastError
0x14000de47  test    eax, eax
0x14000de49  jnz     loc_14000E005
0x14000de4f  mov     ecx, 42Bh
0x14000de54  jmp     loc_14000DFFF
0x14000de59  mov     rcx, rsi; lpString
0x14000de5c  call    cs:__imp_lstrlenW
0x14000de62  xor     edx, edx; Val
0x14000de64  lea     rcx, MultiByteStr; void *
0x14000de6b  mov     r8d, 100h; Size
0x14000de71  mov     r14d, eax
0x14000de74  call    memset_0
0x14000de79  mov     ebp, r12d
0x14000de7c  test    r14d, r14d
0x14000de7f  jz      loc_14000DDFB
0x14000de85  mov     ecx, 0FFh
0x14000de8a  mov     eax, ebp
0x14000de8c  mov     ebx, r14d
0x14000de8f  mov     [rsp+88h+NumberOfCharsWritten], r12d
0x14000de97  sub     ebx, ebp
0x14000de99  cmp     ebx, ecx
0x14000de9b  lea     r15, [rsi+rax*2]
0x14000de9f  cmova   ebx, ecx
0x14000dea2  call    cs:__imp_GetConsoleOutputCP
0x14000dea8  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x14000dead  mov     r9d, ebx; cchWideChar
0x14000deb0  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x14000deb5  mov     ecx, eax; CodePage
0x14000deb7  mov     [rsp+88h+cbMultiByte], r12d; cbMultiByte
0x14000debc  mov     r8, r15; lpWideCharStr
0x14000debf  xor     edx, edx; dwFlags
0x14000dec1  mov     [rsp+88h+lpReserved], r12; lpMultiByteStr
0x14000dec6  call    cs:__imp_WideCharToMultiByte
0x14000decc  test    eax, eax
0x14000dece  jz      loc_14000DFD3
0x14000ded4  cmp     eax, 0FFh
0x14000ded9  jbe     short loc_14000DF2D
0x14000dedb  add     eax, 0FFFFFF01h
0x14000dee0  cmp     eax, 3
0x14000dee3  jbe     short loc_14000DEEB
0x14000dee5  shr     eax, 1
0x14000dee7  sub     ebx, eax
0x14000dee9  jmp     short loc_14000DEED
0x14000deeb  dec     ebx
0x14000deed  mov     [rsp+88h+NumberOfCharsWritten], r12d
0x14000def5  test    ebx, ebx
0x14000def7  jnz     short loc_14000DEA2
0x14000def9  call    cs:__imp_GetLastError
0x14000deff  test    eax, eax
0x14000df01  jnz     short loc_14000DF0E
0x14000df03  mov     ecx, 42Bh; dwErrCode
0x14000df08  call    cs:__imp_SetLastError
0x14000df0e  mov     ecx, r13d; Ix
0x14000df11  call    _o___acrt_iob_func_0
0x14000df16  mov     rcx, rax
0x14000df19  call    ShowLastError
0x14000df1e  call    ReleaseGlobals
0x14000df23  mov     ecx, r13d; uExitCode
0x14000df26  call    cs:__imp_ExitProcess
0x14000df2d  cmp     eax, ebx
0x14000df2f  lea     rcx, MultiByteStr; void *
0x14000df36  mov     r8d, 100h; Size
0x14000df3c  cmovb   ebx, eax
0x14000df3f  xor     edx, edx; Val
0x14000df41  call    memset_0
0x14000df46  call    cs:__imp_GetConsoleOutputCP
0x14000df4c  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x14000df51  mov     r9d, ebx; cchWideChar
0x14000df54  mov     ecx, eax; CodePage
0x14000df56  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x14000df5b  lea     rax, MultiByteStr
0x14000df62  mov     [rsp+88h+cbMultiByte], 0FFh; cbMultiByte
0x14000df6a  mov     r8, r15; lpWideCharStr
0x14000df6d  mov     [rsp+88h+lpReserved], rax; lpMultiByteStr
0x14000df72  xor     edx, edx; dwFlags
0x14000df74  call    cs:__imp_WideCharToMultiByte
0x14000df7a  mov     [rsp+88h+NumberOfCharsWritten], eax
0x14000df81  test    eax, eax
0x14000df83  jz      short loc_14000DFB4
0x14000df85  lea     r8, MultiByteStr
0x14000df8c  mov     rcx, rdi; Stream
0x14000df8f  lea     rdx, Format; "%s"
0x14000df96  add     ebp, ebx
0x14000df98  call    fprintf
0x14000df9d  mov     rcx, rdi; Stream
0x14000dfa0  call    cs:__imp_fflush
0x14000dfa6  cmp     r14d, ebp
0x14000dfa9  jbe     loc_14000DDFB
0x14000dfaf  jmp     loc_14000DE85
0x14000dfb4  mov     ecx, r13d; Ix
0x14000dfb7  call    _o___acrt_iob_func_0
0x14000dfbc  mov     rcx, rax
0x14000dfbf  call    ShowLastError
0x14000dfc4  call    ReleaseGlobals
0x14000dfc9  mov     ecx, r13d; uExitCode
0x14000dfcc  call    cs:__imp_ExitProcess
0x14000dfd3  mov     ecx, r13d; Ix
0x14000dfd6  call    _o___acrt_iob_func_0
0x14000dfdb  mov     rcx, rax
0x14000dfde  call    ShowLastError
0x14000dfe3  call    ReleaseGlobals
0x14000dfe8  mov     ecx, r13d; uExitCode
0x14000dfeb  call    cs:__imp_ExitProcess
0x14000dff2  call    cs:__imp_GetLastError
0x14000dff8  test    eax, eax
0x14000dffa  jnz     short loc_14000E005
0x14000dffc  lea     ecx, [rax+57h]; dwErrCode
0x14000dfff  call    cs:__imp_SetLastError
0x14000e005  xor     eax, eax
0x14000e007  add     rsp, 48h
0x14000e00b  pop     r15
0x14000e00d  pop     r14
0x14000e00f  pop     r13
0x14000e011  pop     r12
0x14000e013  pop     rdi
0x14000e014  pop     rsi
0x14000e015  pop     rbp
0x14000e016  pop     rbx
0x14000e017  retn
```
