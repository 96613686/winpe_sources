# _wdospawn

- ea: `0x18001c4a0`
- end: `0x18001c846`
- name: `_wdospawn`
- size: `934`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001a59c`
- `0x18001b018`

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001c4a0`
- `0x18001d300`
- `0x18001d50c`
- `0x18002f050`
- `0x18003d710`
- `0x18007d030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c7e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c7fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c80c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c7e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c7fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c80c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001c7c7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001c7c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001c777`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001c777`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c7b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c7b9`

## pseudocode

```c
__int64 __fastcall wdospawn(unsigned int a1, const WCHAR *a2, WCHAR *a3, void *a4)
{
  char v6; // r15
  WCHAR *v7; // r12
  int v8; // ebx
  bool v9; // sf
  BYTE *v10; // rax
  int v11; // r14d
  LPBYTE lpReserved2; // rax
  int v13; // r8d
  __int64 hProcess; // rsi
  BYTE *v15; // r9
  LPBYTE v16; // rdx
  __int64 v17; // rax
  BYTE v18; // cl
  __int64 v19; // rax
  int v20; // r14d
  int v21; // ecx
  BYTE *v22; // r12
  BYTE *v23; // r15
  __int64 v24; // rdx
  int v25; // edx
  size_t v26; // rdi
  unsigned int *v27; // rax
  const WCHAR *v28; // rcx
  BOOL v29; // ebx
  DWORD LastError; // edi
  DWORD v32; // eax
  int v33; // [rsp+58h] [rbp-79h]
  WCHAR *v34; // [rsp+60h] [rbp-71h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-69h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-49h] BYREF
  DWORD ExitCode; // [rsp+138h] [rbp+67h] BYREF
  LPCWSTR lpApplicationName; // [rsp+140h] [rbp+6Fh]
  LPVOID lpEnvironment; // [rsp+150h] [rbp+7Fh]

  lpEnvironment = a4;
  lpApplicationName = a2;
  *(&StartupInfo.cb + 1) = 0;
  memset_thunk_772440563353939046(&StartupInfo, 0, 0x64u);
  ExitCode = 0;
  v6 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a1 >= 4 )
  {
    if ( a1 != 4 )
    {
      *_doserrno() = 0;
      *errno() = 22;
      invalid_parameter(0, 0, 0, 0, 0);
    }
    v6 = 1;
  }
  v7 = a3;
  v34 = a3;
  while ( *a3 )
  {
    do
      ++a3;
    while ( *a3 );
    if ( a3[1] )
      *a3++ = 32;
  }
  memset_thunk_772440563353939046(&StartupInfo.cb + 1, 0, 0x64u);
  v8 = nhandle;
  StartupInfo.cb = 104;
  v9 = nhandle < 0;
  if ( nhandle )
  {
    do
    {
      if ( *(_BYTE *)(_pioinfo[(v8 - 1LL) >> 5] + 56LL * (((_BYTE)v8 - 1) & 0x1F) + 8) )
        break;
      --v8;
    }
    while ( v8 );
    v9 = v8 < 0;
  }
  if ( v9
    || (unsigned __int64)v8 >= 0x1C71
    || (StartupInfo.cbReserved2 = 8 * v8 + v8 + 4,
        v10 = (BYTE *)calloc_crt(StartupInfo.cbReserved2, 1),
        (StartupInfo.lpReserved2 = v10) == 0) )
  {
    *errno() = 12;
    return -1;
  }
  else
  {
    *(_DWORD *)v10 = v8;
    v11 = 0;
    lpReserved2 = StartupInfo.lpReserved2;
    v13 = 0;
    hProcess = -1;
    v15 = &StartupInfo.lpReserved2[v8 + 4];
    v16 = StartupInfo.lpReserved2 + 4;
    if ( v8 > 0 )
    {
      do
      {
        v17 = _pioinfo[(unsigned __int64)(unsigned int)v13 >> 5];
        v18 = *(_BYTE *)(v17 + 56LL * (v13 & 0x1F) + 8);
        if ( (v18 & 0x10) != 0 )
        {
          *v16 = 0;
          v19 = -1;
        }
        else
        {
          *v16 = v18;
          v19 = *(_QWORD *)(v17 + 56LL * (v13 & 0x1F));
        }
        *(_QWORD *)v15 = v19;
        ++v13;
        v15 += 8;
        ++v16;
      }
      while ( v13 < v8 );
      lpReserved2 = StartupInfo.lpReserved2;
    }
    if ( v6 )
    {
      v20 = 3;
      if ( v8 < 3 )
        v20 = v8;
      if ( v20 > 0 )
      {
        v21 = 0;
        v22 = &lpReserved2[v8 + 4];
        v23 = lpReserved2 + 4;
        if ( (unsigned int)v20 < 2 )
          goto LABEL_34;
        v24 = v20 - 1;
        if ( v23 <= &v22[8 * v24] && &v23[v24] >= v22 )
          goto LABEL_34;
        v25 = v20 - (v20 & 1);
        do
          v21 += 2;
        while ( v21 < v25 );
        v33 = v21;
        v26 = 2LL * ((v25 + 1) / 2);
        memset_thunk_772440563353939046(v23, 0, v26);
        memset_thunk_772440563353939046(v22, -1, 8 * v26);
        v21 = v33;
        v23 += v26;
        v22 += 8 * v26;
        while ( v21 < v20 )
        {
LABEL_34:
          *v23++ = 0;
          *(_QWORD *)v22 = -1;
          ++v21;
          v22 += 8;
        }
        v7 = v34;
      }
      v11 = 8;
    }
    v27 = _doserrno();
    v28 = lpApplicationName;
    *v27 = 0;
    v29 = CreateProcessW(v28, v7, 0, 0, 1, v11 | 0x400, lpEnvironment, 0, &StartupInfo, &ProcessInformation);
    LastError = GetLastError();
    free(StartupInfo.lpReserved2);
    if ( v29 )
    {
      if ( a1 == 2 )
        exit(0);
      if ( a1 )
      {
        if ( a1 == 4 )
        {
          CloseHandle(ProcessInformation.hProcess);
          hProcess = 0;
        }
        else
        {
          hProcess = (__int64)ProcessInformation.hProcess;
        }
      }
      else
      {
        WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
        if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
        {
          hProcess = (int)ExitCode;
        }
        else
        {
          v32 = GetLastError();
          dosmaperr(v32);
        }
        CloseHandle(ProcessInformation.hProcess);
      }
      CloseHandle(ProcessInformation.hThread);
    }
    else
    {
      dosmaperr(LastError);
    }
    return hProcess;
  }
}

```

## disassembly

```asm
0x18001c4a0  mov     rax, rsp
0x18001c4a3  mov     [rax+18h], rbx
0x18001c4a7  mov     [rax+20h], r9
0x18001c4ab  mov     [rax+10h], rdx
0x18001c4af  push    rbp
0x18001c4b0  push    rsi
0x18001c4b1  push    rdi
0x18001c4b2  push    r12
0x18001c4b4  push    r13
0x18001c4b6  push    r14
0x18001c4b8  push    r15
0x18001c4ba  lea     rbp, [rax-5Fh]
0x18001c4be  sub     rsp, 0F0h
0x18001c4c5  xor     eax, eax
0x18001c4c7  mov     rbx, r8
0x18001c4ca  mov     r13d, ecx
0x18001c4cd  mov     dword ptr [rbp+57h+StartupInfo+4], eax
0x18001c4d0  xor     edx, edx; Val
0x18001c4d2  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18001c4d6  lea     edi, [rax+64h]
0x18001c4d9  mov     r8d, edi; Size
0x18001c4dc  call    memset$thunk$772440563353939046
0x18001c4e1  xor     esi, esi
0x18001c4e3  xor     eax, eax
0x18001c4e5  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18001c4e9  xorps   xmm0, xmm0
0x18001c4ec  mov     [rbp+57h+ExitCode], esi
0x18001c4ef  mov     r15b, sil
0x18001c4f2  mov     ecx, r13d
0x18001c4f5  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18001c4f9  test    r13d, r13d
0x18001c4fc  jz      short loc_18001C540
0x18001c4fe  sub     ecx, 1
0x18001c501  jz      short loc_18001C540
0x18001c503  sub     ecx, 1
0x18001c506  jz      short loc_18001C540
0x18001c508  sub     ecx, 1
0x18001c50b  jz      short loc_18001C540
0x18001c50d  cmp     ecx, 1
0x18001c510  jz      short loc_18001C53D
0x18001c512  call    __doserrno
0x18001c517  mov     [rax], esi
0x18001c519  call    _errno
0x18001c51e  xor     r9d, r9d; LineNo
0x18001c521  mov     [rsp+120h+Reserved], rsi; Reserved
0x18001c526  xor     r8d, r8d; FileName
0x18001c529  xor     edx, edx; FunctionName
0x18001c52b  xor     ecx, ecx; Expression
0x18001c52d  mov     dword ptr [rax], 16h
0x18001c533  call    _invalid_parameter
0x18001c538  jmp     loc_18001C81F
0x18001c53d  mov     r15b, 1
0x18001c540  mov     r12, rbx
0x18001c543  mov     [rbp+57h+var_C8], rbx
0x18001c547  jmp     short loc_18001C561
0x18001c549  add     rbx, 2
0x18001c54d  cmp     [rbx], si
0x18001c550  jnz     short loc_18001C549
0x18001c552  cmp     [rbx+2], si
0x18001c556  jz      short loc_18001C561
0x18001c558  mov     word ptr [rbx], 20h ; ' '
0x18001c55d  add     rbx, 2
0x18001c561  cmp     [rbx], si
0x18001c564  jnz     short loc_18001C549
0x18001c566  mov     r8, rdi; Size
0x18001c569  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18001c56d  xor     edx, edx; Val
0x18001c56f  call    memset$thunk$772440563353939046
0x18001c574  mov     ebx, cs:_nhandle
0x18001c57a  lea     r8, __pioinfo
0x18001c581  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18001c588  test    ebx, ebx
0x18001c58a  jz      short loc_18001C5B2
0x18001c58c  lea     eax, [rbx-1]
0x18001c58f  movsxd  rdx, ebx
0x18001c592  and     eax, 1Fh
0x18001c595  dec     rdx
0x18001c598  imul    rcx, rax, 38h ; '8'
0x18001c59c  sar     rdx, 5
0x18001c5a0  mov     rax, [r8+rdx*8]
0x18001c5a4  cmp     [rax+rcx+8], sil
0x18001c5a9  jnz     short loc_18001C5B0
0x18001c5ab  sub     ebx, 1
0x18001c5ae  jnz     short loc_18001C58C
0x18001c5b0  test    ebx, ebx
0x18001c5b2  js      loc_18001C814
0x18001c5b8  movsxd  rdi, ebx
0x18001c5bb  cmp     rdi, 1C71h
0x18001c5c2  jnb     loc_18001C814
0x18001c5c8  movzx   eax, bx
0x18001c5cb  lea     ecx, [rbx+4]
0x18001c5ce  shl     ax, 3
0x18001c5d2  mov     edx, 1
0x18001c5d7  add     cx, ax
0x18001c5da  movzx   ecx, cx
0x18001c5dd  mov     [rbp+57h+StartupInfo.cbReserved2], cx
0x18001c5e1  call    _calloc_crt
0x18001c5e6  mov     [rbp+57h+StartupInfo.lpReserved2], rax
0x18001c5ea  test    rax, rax
0x18001c5ed  jz      loc_18001C814
0x18001c5f3  mov     [rax], ebx
0x18001c5f5  mov     r14d, esi
0x18001c5f8  mov     rax, [rbp+57h+StartupInfo.lpReserved2]
0x18001c5fc  mov     r8d, esi
0x18001c5ff  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001c603  lea     r9, [rax+4]
0x18001c607  add     r9, rdi
0x18001c60a  lea     rdx, [rax+4]
0x18001c60e  test    ebx, ebx
0x18001c610  jle     short loc_18001C65C
0x18001c612  lea     r11, __pioinfo
0x18001c619  mov     ecx, r8d
0x18001c61c  and     ecx, 1Fh
0x18001c61f  mov     eax, r8d
0x18001c622  imul    r10, rcx, 38h ; '8'
0x18001c626  shr     rax, 5
0x18001c62a  mov     rax, [r11+rax*8]
0x18001c62e  mov     cl, [rax+r10+8]
0x18001c633  test    cl, 10h
0x18001c636  jnz     short loc_18001C640
0x18001c638  mov     [rdx], cl
0x18001c63a  mov     rax, [rax+r10]
0x18001c63e  jmp     short loc_18001C646
0x18001c640  mov     [rdx], r14b
0x18001c643  mov     rax, rsi
0x18001c646  mov     [r9], rax
0x18001c649  inc     r8d
0x18001c64c  add     r9, 8
0x18001c650  inc     rdx
0x18001c653  cmp     r8d, ebx
0x18001c656  jl      short loc_18001C619
0x18001c658  mov     rax, [rbp+57h+StartupInfo.lpReserved2]
0x18001c65c  test    r15b, r15b
0x18001c65f  jz      loc_18001C729
0x18001c665  mov     r14d, 3
0x18001c66b  cmp     ebx, r14d
0x18001c66e  cmovl   r14d, ebx
0x18001c672  test    r14d, r14d
0x18001c675  jle     loc_18001C723
0x18001c67b  lea     r12, [rax+4]
0x18001c67f  xor     ecx, ecx
0x18001c681  add     r12, rdi
0x18001c684  lea     r15, [rax+4]
0x18001c688  cmp     r14d, 2
0x18001c68c  jb      short loc_18001C70B
0x18001c68e  lea     eax, [r14-1]
0x18001c692  movsxd  rdx, eax
0x18001c695  lea     rax, [r12+rdx*8]
0x18001c699  cmp     r15, rax
0x18001c69c  ja      short loc_18001C6A7
0x18001c69e  lea     rax, [rdx+r15]
0x18001c6a2  cmp     rax, r12
0x18001c6a5  jnb     short loc_18001C70B
0x18001c6a7  mov     eax, r14d
0x18001c6aa  and     eax, 80000001h
0x18001c6af  jge     short loc_18001C6B8
0x18001c6b1  dec     eax
0x18001c6b3  or      eax, 0FFFFFFFEh
0x18001c6b6  inc     eax
0x18001c6b8  mov     edx, r14d
0x18001c6bb  sub     edx, eax
0x18001c6bd  add     ecx, 2
0x18001c6c0  cmp     ecx, edx
0x18001c6c2  jl      short loc_18001C6BD
0x18001c6c4  lea     eax, [rdx+1]
0x18001c6c7  mov     [rbp+57h+var_D0], ecx
0x18001c6ca  cdq
0x18001c6cb  sub     eax, edx
0x18001c6cd  xor     edx, edx; Val
0x18001c6cf  sar     eax, 1
0x18001c6d1  movsxd  rcx, eax
0x18001c6d4  lea     rdi, [rcx+rcx]
0x18001c6d8  mov     rcx, r15; void *
0x18001c6db  mov     r8, rdi; Size
0x18001c6de  call    memset$thunk$772440563353939046
0x18001c6e3  lea     rbx, ds:0[rdi*8]
0x18001c6eb  mov     rdx, rsi; Val
0x18001c6ee  mov     r8, rbx
0x18001c6f1  mov     rcx, r12; void *
0x18001c6f4  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18001c6f8  call    memset$thunk$772440563353939046
0x18001c6fd  mov     ecx, [rbp+57h+var_D0]
0x18001c700  add     r15, rdi
0x18001c703  add     r12, rbx
0x18001c706  cmp     ecx, r14d
0x18001c709  jge     short loc_18001C71F
0x18001c70b  mov     byte ptr [r15], 0
0x18001c70f  inc     r15
0x18001c712  mov     [r12], rsi
0x18001c716  inc     ecx
0x18001c718  lea     r12, [r12+8]
0x18001c71d  jmp     short loc_18001C706
0x18001c71f  mov     r12, [rbp+57h+var_C8]
0x18001c723  mov     r14d, 8
0x18001c729  call    __doserrno
0x18001c72e  mov     rcx, [rbp+57h+lpApplicationName]; lpApplicationName
0x18001c732  bts     r14d, 0Ah
0x18001c737  xor     r9d, r9d; lpThreadAttributes
0x18001c73a  xor     r8d, r8d; lpProcessAttributes
0x18001c73d  mov     rdx, r12; lpCommandLine
0x18001c740  mov     dword ptr [rax], 0
0x18001c746  lea     rax, [rbp+57h+ProcessInformation]
0x18001c74a  mov     [rsp+48h], rax; lpProcessInformation
0x18001c74f  lea     rax, [rbp+57h+StartupInfo]
0x18001c753  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x18001c758  mov     rax, [rbp+57h+arg_18]
0x18001c75c  mov     [rsp+120h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001c765  mov     [rsp+120h+lpEnvironment], rax; lpEnvironment
0x18001c76a  mov     [rsp+120h+dwCreationFlags], r14d; dwCreationFlags
0x18001c76f  mov     dword ptr [rsp+120h+Reserved], 1; bInheritHandles
0x18001c777  call    cs:__imp_CreateProcessW
0x18001c77d  mov     ebx, eax
0x18001c77f  call    cs:__imp_GetLastError
0x18001c785  mov     rcx, [rbp+57h+StartupInfo.lpReserved2]; Block
0x18001c789  mov     edi, eax
0x18001c78b  call    free
0x18001c790  test    ebx, ebx
0x18001c792  jnz     short loc_18001C7A3
0x18001c794  mov     ecx, edi
0x18001c796  call    _dosmaperr
0x18001c79b  mov     rax, rsi
0x18001c79e  jmp     loc_18001C823
0x18001c7a3  cmp     r13d, 2
0x18001c7a7  jz      loc_18001C83E
0x18001c7ad  test    r13d, r13d
0x18001c7b0  jnz     short loc_18001C7F0
0x18001c7b2  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18001c7b6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c7b9  call    cs:__imp_WaitForSingleObject
0x18001c7bf  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18001c7c3  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18001c7c7  call    cs:__imp_GetExitCodeProcess
0x18001c7cd  test    eax, eax
0x18001c7cf  jz      short loc_18001C7D7
0x18001c7d1  movsxd  rsi, [rbp+57h+ExitCode]
0x18001c7d5  jmp     short loc_18001C7E4
0x18001c7d7  call    cs:__imp_GetLastError
0x18001c7dd  mov     ecx, eax
0x18001c7df  call    _dosmaperr
0x18001c7e4  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18001c7e8  call    cs:__imp_CloseHandle
0x18001c7ee  jmp     short loc_18001C808
0x18001c7f0  cmp     r13d, 4
0x18001c7f4  jnz     short loc_18001C804
0x18001c7f6  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18001c7fa  call    cs:__imp_CloseHandle
0x18001c800  xor     esi, esi
0x18001c802  jmp     short loc_18001C808
0x18001c804  mov     rsi, [rbp+57h+ProcessInformation.hProcess]
0x18001c808  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18001c80c  call    cs:__imp_CloseHandle
0x18001c812  jmp     short loc_18001C79B
0x18001c814  call    _errno
0x18001c819  mov     dword ptr [rax], 0Ch
0x18001c81f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c823  mov     rbx, [rsp+120h+arg_10]
0x18001c82b  add     rsp, 0F0h
0x18001c832  pop     r15
0x18001c834  pop     r14
0x18001c836  pop     r13
0x18001c838  pop     r12
0x18001c83a  pop     rdi
0x18001c83b  pop     rsi
0x18001c83c  pop     rbp
0x18001c83d  retn
0x18001c83e  xor     ecx, ecx; Code
0x18001c840  call    _exit
```
