# _dospawn

- ea: `0x18001bba4`
- end: `0x18001bf43`
- name: `_dospawn`
- size: `927`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180018f44`
- `0x180019aa8`

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001bba4`
- `0x18001d300`
- `0x18001d50c`
- `0x18002f050`
- `0x18003d710`
- `0x18007d030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bee5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf09`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001bec4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001bec4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x18001be74`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x18001be74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001beb6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001beb6`

## pseudocode

```c
__int64 __fastcall dospawn(unsigned int a1, const CHAR *a2, CHAR *a3, void *a4)
{
  char v6; // r15
  CHAR *v7; // r12
  int v8; // ebx
  bool v9; // sf
  BYTE *v10; // rax
  DWORD dwCreationFlags; // r14d
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
  const CHAR *v28; // rcx
  BOOL v29; // ebx
  DWORD LastError; // edi
  DWORD v32; // eax
  int v33; // [rsp+58h] [rbp-79h]
  CHAR *v34; // [rsp+60h] [rbp-71h]
  _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-69h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+88h] [rbp-49h] BYREF
  DWORD ExitCode; // [rsp+138h] [rbp+67h] BYREF
  LPCSTR lpApplicationName; // [rsp+140h] [rbp+6Fh]
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
    dwCreationFlags = 0;
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
      dwCreationFlags = 8;
    }
    v27 = _doserrno();
    v28 = lpApplicationName;
    *v27 = 0;
    v29 = CreateProcessA(v28, v7, 0, 0, 1, dwCreationFlags, lpEnvironment, 0, &StartupInfo, &ProcessInformation);
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
0x18001bba4  mov     rax, rsp
0x18001bba7  mov     [rax+18h], rbx
0x18001bbab  mov     [rax+20h], r9
0x18001bbaf  mov     [rax+10h], rdx
0x18001bbb3  push    rbp
0x18001bbb4  push    rsi
0x18001bbb5  push    rdi
0x18001bbb6  push    r12
0x18001bbb8  push    r13
0x18001bbba  push    r14
0x18001bbbc  push    r15
0x18001bbbe  lea     rbp, [rax-5Fh]
0x18001bbc2  sub     rsp, 0F0h
0x18001bbc9  xor     eax, eax
0x18001bbcb  mov     rbx, r8
0x18001bbce  mov     r13d, ecx
0x18001bbd1  mov     dword ptr [rbp+57h+StartupInfo+4], eax
0x18001bbd4  xor     edx, edx; Val
0x18001bbd6  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18001bbda  lea     edi, [rax+64h]
0x18001bbdd  mov     r8d, edi; Size
0x18001bbe0  call    memset$thunk$772440563353939046
0x18001bbe5  xor     esi, esi
0x18001bbe7  lea     r14d, [rdi-63h]
0x18001bbeb  xor     eax, eax
0x18001bbed  mov     [rbp+57h+ExitCode], esi
0x18001bbf0  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18001bbf4  xorps   xmm0, xmm0
0x18001bbf7  mov     r15b, sil
0x18001bbfa  mov     ecx, r13d
0x18001bbfd  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18001bc01  test    r13d, r13d
0x18001bc04  jz      short loc_18001BC48
0x18001bc06  sub     ecx, r14d
0x18001bc09  jz      short loc_18001BC48
0x18001bc0b  sub     ecx, r14d
0x18001bc0e  jz      short loc_18001BC48
0x18001bc10  sub     ecx, r14d
0x18001bc13  jz      short loc_18001BC48
0x18001bc15  cmp     ecx, r14d
0x18001bc18  jz      short loc_18001BC45
0x18001bc1a  call    __doserrno
0x18001bc1f  mov     [rax], esi
0x18001bc21  call    _errno
0x18001bc26  xor     r9d, r9d; LineNo
0x18001bc29  mov     [rsp+120h+Reserved], rsi; Reserved
0x18001bc2e  xor     r8d, r8d; FileName
0x18001bc31  xor     edx, edx; FunctionName
0x18001bc33  xor     ecx, ecx; Expression
0x18001bc35  mov     dword ptr [rax], 16h
0x18001bc3b  call    _invalid_parameter
0x18001bc40  jmp     loc_18001BF1C
0x18001bc45  mov     r15b, r14b
0x18001bc48  mov     r12, rbx
0x18001bc4b  mov     [rbp+57h+var_C8], rbx
0x18001bc4f  jmp     short loc_18001BC65
0x18001bc51  add     rbx, r14
0x18001bc54  cmp     [rbx], sil
0x18001bc57  jnz     short loc_18001BC51
0x18001bc59  cmp     [rbx+1], sil
0x18001bc5d  jz      short loc_18001BC65
0x18001bc5f  mov     byte ptr [rbx], 20h ; ' '
0x18001bc62  inc     rbx
0x18001bc65  cmp     [rbx], sil
0x18001bc68  jnz     short loc_18001BC51
0x18001bc6a  mov     r8, rdi; Size
0x18001bc6d  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18001bc71  xor     edx, edx; Val
0x18001bc73  call    memset$thunk$772440563353939046
0x18001bc78  mov     ebx, cs:_nhandle
0x18001bc7e  lea     r8, __pioinfo
0x18001bc85  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18001bc8c  test    ebx, ebx
0x18001bc8e  jz      short loc_18001BCB6
0x18001bc90  lea     eax, [rbx-1]
0x18001bc93  movsxd  rdx, ebx
0x18001bc96  and     eax, 1Fh
0x18001bc99  sub     rdx, r14
0x18001bc9c  imul    rcx, rax, 38h ; '8'
0x18001bca0  sar     rdx, 5
0x18001bca4  mov     rax, [r8+rdx*8]
0x18001bca8  cmp     [rax+rcx+8], sil
0x18001bcad  jnz     short loc_18001BCB4
0x18001bcaf  sub     ebx, r14d
0x18001bcb2  jnz     short loc_18001BC90
0x18001bcb4  test    ebx, ebx
0x18001bcb6  js      loc_18001BF11
0x18001bcbc  movsxd  rdi, ebx
0x18001bcbf  cmp     rdi, 1C71h
0x18001bcc6  jnb     loc_18001BF11
0x18001bccc  movzx   eax, bx
0x18001bccf  lea     ecx, [rbx+4]
0x18001bcd2  shl     ax, 3
0x18001bcd6  mov     rdx, r14
0x18001bcd9  add     cx, ax
0x18001bcdc  movzx   ecx, cx
0x18001bcdf  mov     [rbp+57h+StartupInfo.cbReserved2], cx
0x18001bce3  call    _calloc_crt
0x18001bce8  mov     [rbp+57h+StartupInfo.lpReserved2], rax
0x18001bcec  test    rax, rax
0x18001bcef  jz      loc_18001BF11
0x18001bcf5  mov     [rax], ebx
0x18001bcf7  mov     r14d, esi
0x18001bcfa  mov     rax, [rbp+57h+StartupInfo.lpReserved2]
0x18001bcfe  mov     r8d, esi
0x18001bd01  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001bd05  lea     r9, [rax+4]
0x18001bd09  add     r9, rdi
0x18001bd0c  lea     rdx, [rax+4]
0x18001bd10  test    ebx, ebx
0x18001bd12  jle     short loc_18001BD5E
0x18001bd14  lea     r11, __pioinfo
0x18001bd1b  mov     ecx, r8d
0x18001bd1e  and     ecx, 1Fh
0x18001bd21  mov     eax, r8d
0x18001bd24  imul    r10, rcx, 38h ; '8'
0x18001bd28  shr     rax, 5
0x18001bd2c  mov     rax, [r11+rax*8]
0x18001bd30  mov     cl, [rax+r10+8]
0x18001bd35  test    cl, 10h
0x18001bd38  jnz     short loc_18001BD42
0x18001bd3a  mov     [rdx], cl
0x18001bd3c  mov     rax, [rax+r10]
0x18001bd40  jmp     short loc_18001BD48
0x18001bd42  mov     [rdx], r14b
0x18001bd45  mov     rax, rsi
0x18001bd48  mov     [r9], rax
0x18001bd4b  inc     r8d
0x18001bd4e  add     r9, 8
0x18001bd52  inc     rdx
0x18001bd55  cmp     r8d, ebx
0x18001bd58  jl      short loc_18001BD1B
0x18001bd5a  mov     rax, [rbp+57h+StartupInfo.lpReserved2]
0x18001bd5e  test    r15b, r15b
0x18001bd61  jz      loc_18001BE2B
0x18001bd67  mov     r14d, 3
0x18001bd6d  cmp     ebx, r14d
0x18001bd70  cmovl   r14d, ebx
0x18001bd74  test    r14d, r14d
0x18001bd77  jle     loc_18001BE25
0x18001bd7d  lea     r12, [rax+4]
0x18001bd81  xor     ecx, ecx
0x18001bd83  add     r12, rdi
0x18001bd86  lea     r15, [rax+4]
0x18001bd8a  cmp     r14d, 2
0x18001bd8e  jb      short loc_18001BE0D
0x18001bd90  lea     eax, [r14-1]
0x18001bd94  movsxd  rdx, eax
0x18001bd97  lea     rax, [r12+rdx*8]
0x18001bd9b  cmp     r15, rax
0x18001bd9e  ja      short loc_18001BDA9
0x18001bda0  lea     rax, [rdx+r15]
0x18001bda4  cmp     rax, r12
0x18001bda7  jnb     short loc_18001BE0D
0x18001bda9  mov     eax, r14d
0x18001bdac  and     eax, 80000001h
0x18001bdb1  jge     short loc_18001BDBA
0x18001bdb3  dec     eax
0x18001bdb5  or      eax, 0FFFFFFFEh
0x18001bdb8  inc     eax
0x18001bdba  mov     edx, r14d
0x18001bdbd  sub     edx, eax
0x18001bdbf  add     ecx, 2
0x18001bdc2  cmp     ecx, edx
0x18001bdc4  jl      short loc_18001BDBF
0x18001bdc6  lea     eax, [rdx+1]
0x18001bdc9  mov     [rbp+57h+var_D0], ecx
0x18001bdcc  cdq
0x18001bdcd  sub     eax, edx
0x18001bdcf  xor     edx, edx; Val
0x18001bdd1  sar     eax, 1
0x18001bdd3  movsxd  rcx, eax
0x18001bdd6  lea     rdi, [rcx+rcx]
0x18001bdda  mov     rcx, r15; void *
0x18001bddd  mov     r8, rdi; Size
0x18001bde0  call    memset$thunk$772440563353939046
0x18001bde5  lea     rbx, ds:0[rdi*8]
0x18001bded  mov     rdx, rsi; Val
0x18001bdf0  mov     r8, rbx
0x18001bdf3  mov     rcx, r12; void *
0x18001bdf6  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18001bdfa  call    memset$thunk$772440563353939046
0x18001bdff  mov     ecx, [rbp+57h+var_D0]
0x18001be02  add     r15, rdi
0x18001be05  add     r12, rbx
0x18001be08  cmp     ecx, r14d
0x18001be0b  jge     short loc_18001BE21
0x18001be0d  mov     byte ptr [r15], 0
0x18001be11  inc     r15
0x18001be14  mov     [r12], rsi
0x18001be18  inc     ecx
0x18001be1a  lea     r12, [r12+8]
0x18001be1f  jmp     short loc_18001BE08
0x18001be21  mov     r12, [rbp+57h+var_C8]
0x18001be25  mov     r14d, 8
0x18001be2b  call    __doserrno
0x18001be30  mov     rcx, [rbp+57h+lpApplicationName]; lpApplicationName
0x18001be34  xor     r9d, r9d; lpThreadAttributes
0x18001be37  xor     r8d, r8d; lpProcessAttributes
0x18001be3a  mov     rdx, r12; lpCommandLine
0x18001be3d  mov     dword ptr [rax], 0
0x18001be43  lea     rax, [rbp+57h+ProcessInformation]
0x18001be47  mov     [rsp+48h], rax; lpProcessInformation
0x18001be4c  lea     rax, [rbp+57h+StartupInfo]
0x18001be50  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x18001be55  mov     rax, [rbp+57h+arg_18]
0x18001be59  mov     [rsp+120h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001be62  mov     [rsp+120h+lpEnvironment], rax; lpEnvironment
0x18001be67  mov     [rsp+120h+dwCreationFlags], r14d; dwCreationFlags
0x18001be6c  mov     dword ptr [rsp+120h+Reserved], 1; bInheritHandles
0x18001be74  call    cs:__imp_CreateProcessA
0x18001be7a  mov     ebx, eax
0x18001be7c  call    cs:__imp_GetLastError
0x18001be82  mov     rcx, [rbp+57h+StartupInfo.lpReserved2]; Block
0x18001be86  mov     edi, eax
0x18001be88  call    free
0x18001be8d  test    ebx, ebx
0x18001be8f  jnz     short loc_18001BEA0
0x18001be91  mov     ecx, edi
0x18001be93  call    _dosmaperr
0x18001be98  mov     rax, rsi
0x18001be9b  jmp     loc_18001BF20
0x18001bea0  cmp     r13d, 2
0x18001bea4  jz      loc_18001BF3B
0x18001beaa  test    r13d, r13d
0x18001bead  jnz     short loc_18001BEED
0x18001beaf  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18001beb3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001beb6  call    cs:__imp_WaitForSingleObject
0x18001bebc  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18001bec0  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18001bec4  call    cs:__imp_GetExitCodeProcess
0x18001beca  test    eax, eax
0x18001becc  jz      short loc_18001BED4
0x18001bece  movsxd  rsi, [rbp+57h+ExitCode]
0x18001bed2  jmp     short loc_18001BEE1
0x18001bed4  call    cs:__imp_GetLastError
0x18001beda  mov     ecx, eax
0x18001bedc  call    _dosmaperr
0x18001bee1  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18001bee5  call    cs:__imp_CloseHandle
0x18001beeb  jmp     short loc_18001BF05
0x18001beed  cmp     r13d, 4
0x18001bef1  jnz     short loc_18001BF01
0x18001bef3  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18001bef7  call    cs:__imp_CloseHandle
0x18001befd  xor     esi, esi
0x18001beff  jmp     short loc_18001BF05
0x18001bf01  mov     rsi, [rbp+57h+ProcessInformation.hProcess]
0x18001bf05  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18001bf09  call    cs:__imp_CloseHandle
0x18001bf0f  jmp     short loc_18001BE98
0x18001bf11  call    _errno
0x18001bf16  mov     dword ptr [rax], 0Ch
0x18001bf1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bf20  mov     rbx, [rsp+120h+arg_10]
0x18001bf28  add     rsp, 0F0h
0x18001bf2f  pop     r15
0x18001bf31  pop     r14
0x18001bf33  pop     r13
0x18001bf35  pop     r12
0x18001bf37  pop     rdi
0x18001bf38  pop     rsi
0x18001bf39  pop     rbp
0x18001bf3a  retn
0x18001bf3b  xor     ecx, ecx; Code
0x18001bf3d  call    _exit
```
