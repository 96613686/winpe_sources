# ensureDirectoryUNC

- ea: `0x140009454`
- end: `0x14000987e`
- name: `ensureDirectoryUNC`
- size: `1066`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000488c`
- `0x1400072bc`

## callees

- `0x140001508`
- `0x140008620`
- `0x140008a78`
- `0x140008e64`
- `0x140008f3c`
- `0x140009454`
- `0x14000e450`
- `0x14000e4e0`

## import_xrefs

- `msvcrt!__doserrno` at `0x14000972c`
- `msvcrt!__doserrno` at `0x140009770`
- `msvcrt!__doserrno` at `0x14000972c`
- `msvcrt!__doserrno` at `0x140009770`
- `msvcrt!_errno` at `0x1400096fb`
- `msvcrt!_errno` at `0x14000970c`
- `msvcrt!_errno` at `0x140009734`
- `msvcrt!_errno` at `0x140009778`
- `msvcrt!_errno` at `0x1400096fb`
- `msvcrt!_errno` at `0x14000970c`
- `msvcrt!_errno` at `0x140009734`
- `msvcrt!_errno` at `0x140009778`
- `msvcrt!printf` at `0x140009758`
- `msvcrt!printf` at `0x140009758`
- `USER32!CharNextExA` at `0x1400094c7`
- `USER32!CharNextExA` at `0x140009526`
- `USER32!CharNextExA` at `0x1400094c7`
- `USER32!CharNextExA` at `0x140009526`
- `KERNEL32!GetCurrentProcessId` at `0x14000967f`
- `KERNEL32!GetCurrentProcessId` at `0x14000967f`
- `KERNEL32!CreateDirectoryW` at `0x1400095c8`
- `KERNEL32!CreateDirectoryW` at `0x1400095c8`
- `KERNEL32!CloseHandle` at `0x140009821`
- `KERNEL32!CloseHandle` at `0x140009821`
- `KERNEL32!GetLastError` at `0x140009704`
- `KERNEL32!GetLastError` at `0x14000973c`
- `KERNEL32!GetLastError` at `0x140009704`
- `KERNEL32!GetLastError` at `0x14000973c`
- `KERNEL32!CreateFileW` at `0x1400096eb`
- `KERNEL32!CreateFileW` at `0x1400096eb`

## string_xrefs

- `0x140009815`: `Could not create file in directory: %1`
- `0x14000974a`: `EnsureDirectory: Cant create file: %s, errno=%d, _doserrno=%d, GLE=%d\n`
- `0x140009793`: `Path is invalid: %1`
- `0x1400097ef`: `Ran out of temp file names after %1 attempts: %2`

## pseudocode

```c
__int64 __fastcall ensureDirectoryUNC(char *a1, int a2, __int64 a3)
{
  char v3; // al
  __int64 v4; // rbx
  LPSTR i; // rdx
  CHAR v8; // al
  LPSTR v9; // rbx
  __int64 v10; // rsi
  CHAR v11; // al
  CHAR v12; // al
  unsigned __int64 v13; // rcx
  char *v14; // rax
  char *v15; // r8
  __int64 v16; // rdx
  char *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rcx
  int v22; // r14d
  int v23; // edi
  size_t v24; // r12
  char *v25; // r13
  DWORD CurrentProcessId; // eax
  __int64 v27; // r8
  HANDLE FileW; // rax
  int *v29; // rbx
  int *v30; // rax
  unsigned int v31; // edi
  int v32; // ebx
  DWORD LastError; // eax
  unsigned int v34; // ebx
  int *v35; // rax
  __int64 v36; // rcx
  const char *v37; // r9
  const char *v38; // rdx
  char v42[4096]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PathName[4096]; // [rsp+1050h] [rbp+F50h] BYREF

  v3 = *a1;
  v4 = a3;
  for ( i = a1; v3; v3 = *i )
  {
    if ( v3 == 92 )
      break;
    if ( v3 == 47 )
      break;
    if ( v3 == 58 )
    {
      v8 = i[1];
      if ( v8 != 92 && v8 != 47 )
        break;
    }
    i = CharNextExA(0, i, 0);
  }
  v42[0] = 0;
  if ( *i || !a2 )
  {
    v9 = a1;
    if ( *a1 )
    {
      v10 = a3;
      while ( 1 )
      {
        v11 = *v9;
        if ( !*v9 )
          break;
        do
        {
          if ( v11 == 92 )
            break;
          if ( v11 == 47 )
            break;
          if ( v11 == 58 )
          {
            v12 = v9[1];
            if ( v12 != 92 && v12 != 47 )
              break;
          }
          v9 = CharNextExA(0, v9, 0);
          v11 = *v9;
        }
        while ( *v9 );
        if ( *v9 || !a2 )
        {
          v13 = (int)v9 - (int)a1;
          if ( (_DWORD)v9 != (_DWORD)a1 && (*v9 == 58 || *(v9 - 1) == 58) )
            v13 = (int)v9 - (int)a1 + 1LL;
          if ( v13 > 0x7FFFFFFE )
          {
            v42[0] = 0;
            goto LABEL_70;
          }
          v14 = a1;
          v15 = v42;
          v16 = 4096;
          do
          {
            if ( !v13 )
              break;
            if ( !*v14 )
              break;
            *v15++ = *v14++;
            --v13;
            --v16;
          }
          while ( v16 );
          v17 = v15 - 1;
          if ( v16 )
            v17 = v15;
          *v17 = 0;
          if ( !v16 )
            goto LABEL_70;
          if ( !(unsigned int)GetFullPathUNCW(v42, PathName, v15, a3) )
            return 0;
          CreateDirectoryW(PathName, 0);
        }
        if ( !*v9 )
          break;
        ++v9;
      }
      v4 = a3;
    }
    else
    {
      v4 = a3;
    }
  }
  v18 = -1;
  do
    ++v18;
  while ( v42[v18] );
  if ( !v18 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a1[v19] );
    if ( v19 && (*a1 == 92 || *a1 == 47) )
    {
      v42[0] = *a1;
      v42[1] = 0;
    }
  }
  v20 = -1;
  do
    ++v20;
  while ( v42[v20] );
  if ( !v20 )
  {
    v21 = 0;
LABEL_56:
    v22 = 0;
    v23 = 0;
    v24 = 4096 - v21;
    v25 = &v42[v21];
    while ( 1 )
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( StringCbPrintfA(v25, v24, "CAB%5.5d.TMP", v23 + CurrentProcessId) < 0 )
        goto LABEL_69;
      if ( !(unsigned int)GetFullPathUNCW(v42, PathName, v27, v4) )
        return 0;
      FileW = CreateFileW(PathName, 0xC0000000, 1u, 0, 1u, 0x4000100u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        CloseHandle(FileW);
        return 1;
      }
      v29 = _errno();
      *v29 = GetLastError();
      v30 = _errno();
      switch ( *v30 )
      {
        case 3:
          goto LABEL_63;
        case 5:
          if ( ++v22 >= 5 )
          {
            v36 = a3;
            v37 = v42;
            v42[v20] = 0;
            v38 = "Could not create file in directory: %1";
            goto LABEL_71;
          }
          break;
        case 183:
          break;
        default:
LABEL_63:
          v31 = *__doserrno();
          v32 = *_errno();
          LastError = GetLastError();
          printf("EnsureDirectory: Cant create file: %s, errno=%d, _doserrno=%d, GLE=%d\n", v42, v32, v31, LastError);
          v42[v20] = 0;
          v34 = *__doserrno();
          v35 = _errno();
          ErrSet(a3, "Path is invalid: %1", "%s%d%d", v42, *v35, v34);
          return 0;
      }
      v4 = a3;
      if ( ++v23 >= 999 )
      {
        v42[v20] = 0;
        ErrSet(a3, "Ran out of temp file names after %1 attempts: %2", "%d%s", v23, v42);
        return 0;
      }
    }
  }
  if ( v20 <= 0xFFE )
  {
    v21 = v20 + (int)appendPathSeparator(&v42[v20 - 1]);
    goto LABEL_56;
  }
LABEL_69:
  v10 = a3;
LABEL_70:
  v37 = a1;
  v38 = "File name too long: %1";
  v36 = v10;
LABEL_71:
  ErrSet(v36, v38, "%s", v37);
  return 0;
}

```

## disassembly

```asm
0x140009454  mov     [rsp-8+arg_8], rbx
0x140009459  push    rbp
0x14000945a  push    rsi
0x14000945b  push    rdi
0x14000945c  push    r12
0x14000945e  push    r13
0x140009460  push    r14
0x140009462  push    r15
0x140009464  lea     rbp, [rsp-2F60h]
0x14000946c  mov     eax, 3060h
0x140009471  call    _alloca_probe
0x140009476  sub     rsp, rax
0x140009479  mov     rax, cs:__security_cookie
0x140009480  xor     rax, rsp
0x140009483  mov     [rbp+2F90h+var_40], rax
0x14000948a  mov     al, [rcx]
0x14000948c  mov     rbx, r8
0x14000948f  mov     edi, edx
0x140009491  mov     [rsp+3090h+var_3050], rbx
0x140009496  mov     r15, rcx
0x140009499  mov     rdx, rcx
0x14000949c  mov     r14b, 5Ch ; '\'
0x14000949f  mov     r13b, 2Fh ; '/'
0x1400094a2  xor     r12d, r12d
0x1400094a5  jmp     short loc_1400094D2
0x1400094a7  cmp     al, r14b
0x1400094aa  jz      short loc_1400094D6
0x1400094ac  cmp     al, r13b
0x1400094af  jz      short loc_1400094D6
0x1400094b1  cmp     al, 3Ah ; ':'
0x1400094b3  jnz     short loc_1400094C2
0x1400094b5  mov     al, [rdx+1]
0x1400094b8  cmp     al, r14b
0x1400094bb  jz      short loc_1400094C2
0x1400094bd  cmp     al, r13b
0x1400094c0  jnz     short loc_1400094D6
0x1400094c2  xor     ecx, ecx; CodePage
0x1400094c4  xor     r8d, r8d; dwFlags
0x1400094c7  call    cs:__imp_CharNextExA
0x1400094cd  mov     rdx, rax; lpCurrentChar
0x1400094d0  mov     al, [rax]
0x1400094d2  test    al, al
0x1400094d4  jnz     short loc_1400094A7
0x1400094d6  mov     [rsp+3090h+var_3040], r12b
0x1400094db  cmp     [rdx], r12b
0x1400094de  jnz     short loc_1400094E8
0x1400094e0  test    edi, edi
0x1400094e2  jnz     loc_1400095EF
0x1400094e8  mov     rbx, r15
0x1400094eb  cmp     [r15], r12b
0x1400094ee  jz      loc_1400095EA
0x1400094f4  mov     rsi, [rsp+3090h+var_3050]
0x1400094f9  mov     al, [rbx]
0x1400094fb  test    al, al
0x1400094fd  jz      loc_1400095E5
0x140009503  cmp     al, r14b
0x140009506  jz      short loc_140009535
0x140009508  cmp     al, r13b
0x14000950b  jz      short loc_140009535
0x14000950d  cmp     al, 3Ah ; ':'
0x14000950f  jnz     short loc_14000951E
0x140009511  mov     al, [rbx+1]
0x140009514  cmp     al, r14b
0x140009517  jz      short loc_14000951E
0x140009519  cmp     al, r13b
0x14000951c  jnz     short loc_140009535
0x14000951e  xor     ecx, ecx; CodePage
0x140009520  xor     r8d, r8d; dwFlags
0x140009523  mov     rdx, rbx; lpCurrentChar
0x140009526  call    cs:__imp_CharNextExA
0x14000952c  mov     rbx, rax
0x14000952f  mov     al, [rax]
0x140009531  test    al, al
0x140009533  jnz     short loc_140009503
0x140009535  cmp     [rbx], r12b
0x140009538  jnz     short loc_140009542
0x14000953a  test    edi, edi
0x14000953c  jnz     loc_1400095CE
0x140009542  mov     eax, ebx
0x140009544  sub     eax, r15d
0x140009547  movsxd  rcx, eax
0x14000954a  jz      short loc_14000955A
0x14000954c  cmp     byte ptr [rbx], 3Ah ; ':'
0x14000954f  jz      short loc_140009557
0x140009551  cmp     byte ptr [rbx-1], 3Ah ; ':'
0x140009555  jnz     short loc_14000955A
0x140009557  inc     rcx
0x14000955a  cmp     rcx, 7FFFFFFEh
0x140009561  ja      short loc_1400095DB
0x140009563  mov     rax, r15
0x140009566  lea     r8, [rsp+3090h+var_3040]
0x14000956b  mov     edx, 1000h
0x140009570  test    rcx, rcx
0x140009573  jz      short loc_14000958F
0x140009575  mov     r9b, [rax]
0x140009578  test    r9b, r9b
0x14000957b  jz      short loc_14000958F
0x14000957d  mov     [r8], r9b
0x140009580  inc     rax
0x140009583  inc     r8
0x140009586  dec     rcx
0x140009589  sub     rdx, 1
0x14000958d  jnz     short loc_140009570
0x14000958f  test    rdx, rdx
0x140009592  lea     rax, [r8-1]
0x140009596  cmovnz  rax, r8
0x14000959a  mov     [rax], r12b
0x14000959d  jz      loc_140009833
0x1400095a3  mov     r9, rsi
0x1400095a6  lea     rdx, [rbp+2F90h+PathName]
0x1400095ad  lea     rcx, [rsp+3090h+var_3040]
0x1400095b2  call    GetFullPathUNCW
0x1400095b7  test    eax, eax
0x1400095b9  jz      loc_14000984C
0x1400095bf  xor     edx, edx; lpSecurityAttributes
0x1400095c1  lea     rcx, [rbp+2F90h+PathName]; lpPathName
0x1400095c8  call    cs:__imp_CreateDirectoryW
0x1400095ce  cmp     [rbx], r12b
0x1400095d1  jz      short loc_1400095E5
0x1400095d3  inc     rbx
0x1400095d6  jmp     loc_1400094F9
0x1400095db  mov     [rsp+3090h+var_3040], r12b
0x1400095e0  jmp     loc_140009833
0x1400095e5  mov     rbx, rsi
0x1400095e8  jmp     short loc_1400095EF
0x1400095ea  mov     rbx, [rsp+3090h+var_3050]
0x1400095ef  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400095f3  lea     rcx, [rsp+3090h+var_3040]
0x1400095f8  mov     rax, rdx
0x1400095fb  inc     rax
0x1400095fe  cmp     [rcx+rax], r12b
0x140009602  jnz     short loc_1400095FB
0x140009604  test    rax, rax
0x140009607  jnz     short loc_140009630
0x140009609  mov     rax, rdx
0x14000960c  inc     rax
0x14000960f  cmp     [r15+rax], r12b
0x140009613  jnz     short loc_14000960C
0x140009615  test    rax, rax
0x140009618  jz      short loc_140009630
0x14000961a  mov     al, [r15]
0x14000961d  cmp     al, r14b
0x140009620  jz      short loc_140009627
0x140009622  cmp     al, r13b
0x140009625  jnz     short loc_140009630
0x140009627  mov     [rsp+3090h+var_3040], al
0x14000962b  mov     [rsp+3090h+var_303F], r12b
0x140009630  lea     rax, [rsp+3090h+var_3040]
0x140009635  mov     rsi, rdx
0x140009638  inc     rsi
0x14000963b  cmp     [rax+rsi], r12b
0x14000963f  jnz     short loc_140009638
0x140009641  test    rsi, rsi
0x140009644  jz      short loc_140009665
0x140009646  cmp     rsi, 0FFEh
0x14000964d  ja      loc_14000982E
0x140009653  lea     rcx, [rsp+rsi+3090h+var_3041]
0x140009658  call    appendPathSeparator
0x14000965d  movsxd  rcx, eax
0x140009660  add     rcx, rsi
0x140009663  jmp     short loc_140009668
0x140009665  mov     rcx, rsi
0x140009668  mov     r14d, r12d
0x14000966b  lea     r13, [rsp+3090h+var_3040]
0x140009670  mov     edi, r12d
0x140009673  mov     r12d, 1000h
0x140009679  sub     r12, rcx
0x14000967c  add     r13, rcx
0x14000967f  call    cs:__imp_GetCurrentProcessId
0x140009685  lea     r8, pszFormat; "CAB%5.5d.TMP"
0x14000968c  mov     rdx, r12; cbDest
0x14000968f  mov     rcx, r13; pszDest
0x140009692  lea     r9d, [rdi+rax]
0x140009696  call    StringCbPrintfA
0x14000969b  test    eax, eax
0x14000969d  js      loc_14000982E
0x1400096a3  mov     r9, rbx
0x1400096a6  lea     rdx, [rbp+2F90h+PathName]
0x1400096ad  lea     rcx, [rsp+3090h+var_3040]
0x1400096b2  call    GetFullPathUNCW
0x1400096b7  test    eax, eax
0x1400096b9  jz      loc_14000984C
0x1400096bf  xor     r9d, r9d; lpSecurityAttributes
0x1400096c2  mov     [rsp+3090h+hTemplateFile], 0; hTemplateFile
0x1400096cb  mov     [rsp+3090h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x1400096d3  lea     rcx, [rbp+2F90h+PathName]; lpFileName
0x1400096da  mov     edx, 0C0000000h; dwDesiredAccess
0x1400096df  mov     [rsp+3090h+dwCreationDisposition], 1; dwCreationDisposition
0x1400096e7  lea     r8d, [r9+1]; dwShareMode
0x1400096eb  call    cs:__imp_CreateFileW
0x1400096f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400096f5  jnz     loc_14000981E
0x1400096fb  call    cs:__imp__errno
0x140009701  mov     rbx, rax
0x140009704  call    cs:__imp_GetLastError
0x14000970a  mov     [rbx], eax
0x14000970c  call    cs:__imp__errno
0x140009712  cmp     dword ptr [rax], 3
0x140009715  jz      short loc_14000972C
0x140009717  cmp     dword ptr [rax], 5
0x14000971a  jz      loc_1400097AA
0x140009720  cmp     dword ptr [rax], 0B7h
0x140009726  jz      loc_1400097B3
0x14000972c  call    cs:__imp___doserrno
0x140009732  mov     edi, [rax]
0x140009734  call    cs:__imp__errno
0x14000973a  mov     ebx, [rax]
0x14000973c  call    cs:__imp_GetLastError
0x140009742  mov     r9d, edi
0x140009745  lea     rdx, [rsp+3090h+var_3040]
0x14000974a  lea     rcx, aEnsuredirector; "EnsureDirectory: Cant create file: %s, "...
0x140009751  mov     [rsp+3090h+dwCreationDisposition], eax
0x140009755  mov     r8d, ebx
0x140009758  call    cs:__imp_printf
0x14000975e  cmp     rsi, 1000h
0x140009765  jnb     loc_140009878
0x14000976b  mov     [rsp+rsi+3090h+var_3040], 0
0x140009770  call    cs:__imp___doserrno
0x140009776  mov     ebx, [rax]
0x140009778  call    cs:__imp__errno
0x14000977e  mov     rcx, [rsp+3090h+var_3050]
0x140009783  lea     r9, [rsp+3090h+var_3040]
0x140009788  mov     [rsp+3090h+dwFlagsAndAttributes], ebx
0x14000978c  lea     r8, aSDD; "%s%d%d"
0x140009793  lea     rdx, aPathIsInvalid1; "Path is invalid: %1"
0x14000979a  mov     eax, [rax]
0x14000979c  mov     [rsp+3090h+dwCreationDisposition], eax
0x1400097a0  call    ErrSet
0x1400097a5  jmp     loc_14000984C
0x1400097aa  inc     r14d
0x1400097ad  cmp     r14d, 5
0x1400097b1  jge     short loc_1400097FD
0x1400097b3  mov     rbx, [rsp+3090h+var_3050]
0x1400097b8  inc     edi
0x1400097ba  cmp     edi, 3E7h
0x1400097c0  jl      loc_14000967F
0x1400097c6  cmp     rsi, 1000h
0x1400097cd  jnb     loc_140009878
0x1400097d3  lea     rax, [rsp+3090h+var_3040]
0x1400097d8  mov     [rsp+rsi+3090h+var_3040], 0
0x1400097dd  mov     r9d, edi
0x1400097e0  mov     qword ptr [rsp+3090h+dwCreationDisposition], rax
0x1400097e5  lea     r8, aDS; "%d%s"
0x1400097ec  mov     rcx, rbx
0x1400097ef  lea     rdx, aRanOutOfTempFi; "Ran out of temp file names after %1 att"...
0x1400097f6  call    ErrSet
0x1400097fb  jmp     short loc_14000984C
0x1400097fd  cmp     rsi, 1000h
0x140009804  jnb     short loc_140009878
0x140009806  mov     rcx, [rsp+3090h+var_3050]
0x14000980b  lea     r9, [rsp+3090h+var_3040]
0x140009810  mov     [rsp+rsi+3090h+var_3040], 0
0x140009815  lea     rdx, aCouldNotCreate; "Could not create file in directory: %1"
0x14000981c  jmp     short loc_140009840
0x14000981e  mov     rcx, rax; hObject
0x140009821  call    cs:__imp_CloseHandle
0x140009827  mov     eax, 1
0x14000982c  jmp     short loc_14000984E
0x14000982e  mov     rsi, [rsp+3090h+var_3050]
0x140009833  mov     r9, r15
0x140009836  lea     rdx, aFileNameTooLon; "File name too long: %1"
0x14000983d  mov     rcx, rsi
0x140009840  lea     r8, aS_4; "%s"
0x140009847  call    ErrSet
0x14000984c  xor     eax, eax
0x14000984e  mov     rcx, [rbp+2F90h+var_40]
0x140009855  xor     rcx, rsp; StackCookie
0x140009858  call    __security_check_cookie
0x14000985d  mov     rbx, [rsp+3090h+arg_8]
0x140009865  add     rsp, 3060h
0x14000986c  pop     r15
0x14000986e  pop     r14
0x140009870  pop     r13
0x140009872  pop     r12
0x140009874  pop     rdi
0x140009875  pop     rsi
0x140009876  pop     rbp
0x140009877  retn
0x140009878  call    __report_rangecheckfailure
```
