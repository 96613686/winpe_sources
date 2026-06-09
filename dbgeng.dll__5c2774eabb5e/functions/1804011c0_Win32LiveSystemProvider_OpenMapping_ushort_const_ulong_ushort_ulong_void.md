# Win32LiveSystemProvider::OpenMapping(ushort const *,ulong *,ushort *,ulong,void * *)

- ea: `0x1804011c0`
- end: `0x1804014f7`
- name: `?OpenMapping@Win32LiveSystemProvider@@UEAAJPEBGPEAKPEAGKPEAPEAX@Z`
- size: `823`
- prototype: `int(Win32LiveSystemProvider *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800f0f40`
- `0x1804011c0`
- `0x1804083a0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180401277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804013b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804013c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180401476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180401486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180401277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804013b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804013c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180401476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180401486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1804013f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1804013f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804013a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804014af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804014be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804013a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804014af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804014be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180401369`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180401369`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1804012be`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1804012be`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1804012fc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1804012fc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18040138e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18040138e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18040121e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18040121e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180401462`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180401462`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::OpenMapping(
        Win32LiveSystemProvider *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned int cchWideChar,
        void **a6)
{
  char *FileW; // rdi
  __int64 (__fastcall *v11)(const unsigned __int16 *, unsigned __int16 *, _QWORD); // rax
  int v12; // ebx
  unsigned int v13; // eax
  char *FileA; // rax
  unsigned int (__fastcall *v15)(CHAR *, CHAR *, __int64); // rax
  DWORD FileSize; // eax
  signed int LastError; // eax
  unsigned int v18; // ebx
  void *v19; // rax
  void *v20; // rsi
  void *v21; // rbp
  signed int v22; // eax
  CHAR MultiByteStr[368]; // [rsp+40h] [rbp-1B8h] BYREF

  FileW = (char *)CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() == 120 && WideCharToMultiByte(0, 0x400u, a2, -1, MultiByteStr, 360, 0, 0) > 0 )
    {
      FileA = (char *)CreateFileA(MultiByteStr, 0x80000000, 3u, 0, 3u, 0, 0);
      FileW = FileA;
      if ( !FileA )
        goto LABEL_18;
      if ( FileA != (char *)-1LL )
      {
        v15 = (unsigned int (__fastcall *)(CHAR *, CHAR *, __int64))*((_QWORD *)this + 41);
        v12 = cchWideChar;
        if ( !v15
          || v15(MultiByteStr, MultiByteStr, 360) - 1 > 0x166
          || !MultiByteToWideChar(0, 0, MultiByteStr, -1, a4, cchWideChar) )
        {
          goto LABEL_5;
        }
        goto LABEL_16;
      }
    }
    else if ( !FileW )
    {
      goto LABEL_18;
    }
    if ( FileW == (char *)-1LL )
      goto LABEL_18;
    goto LABEL_16;
  }
  v11 = (__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, _QWORD))*((_QWORD *)this + 42);
  v12 = cchWideChar;
  if ( !v11 || (v13 = v11(a2, a4, cchWideChar)) == 0 || v13 >= cchWideChar )
LABEL_5:
    GenStrCopyNW(a4, a2, v12);
LABEL_16:
  FileSize = GetFileSize(FileW, 0);
  *a3 = FileSize;
  if ( FileSize == -1 )
  {
LABEL_17:
    CloseHandle(FileW);
LABEL_18:
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147467259;
    }
    return v18;
  }
  if ( !g_Kernel32CallsMdwd )
  {
    SetLastError(0x78u);
    goto LABEL_17;
  }
  v19 = (void *)g_Kernel32CallsMdwd(FileW, 0, 2);
  v20 = v19;
  if ( !v19 )
    goto LABEL_17;
  v21 = MapViewOfFile(v19, 4u, 0, 0, 0);
  if ( v21 )
  {
    v18 = 0;
  }
  else if ( GetLastError() )
  {
    v22 = GetLastError();
    v18 = v22;
    if ( v22 > 0 )
      v18 = (unsigned __int16)v22 | 0x80070000;
  }
  else
  {
    v18 = -2147467259;
  }
  CloseHandle(v20);
  CloseHandle(FileW);
  *a6 = v21;
  return v18;
}

```

## disassembly

```asm
0x1804011c0  push    rbx
0x1804011c2  push    rbp
0x1804011c3  push    rsi
0x1804011c4  push    rdi
0x1804011c5  push    r14
0x1804011c7  push    r15
0x1804011c9  sub     rsp, 1C8h
0x1804011d0  mov     rax, cs:__security_cookie
0x1804011d7  xor     rax, rsp
0x1804011da  mov     [rsp+1F8h+var_48], rax
0x1804011e2  mov     r15, [rsp+1F8h+arg_28]
0x1804011ea  mov     rsi, rdx
0x1804011ed  mov     rbp, r9
0x1804011f0  mov     [rsp+1F8h+hTemplateFile], 0; hTemplateFile
0x1804011f9  xor     r9d, r9d; lpSecurityAttributes
0x1804011fc  mov     [rsp+1F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180401204  mov     r14, r8
0x180401207  mov     [rsp+1F8h+dwCreationDisposition], 3; dwCreationDisposition
0x18040120f  mov     rbx, rcx
0x180401212  mov     edx, 80000000h; dwDesiredAccess
0x180401217  mov     rcx, rsi; lpFileName
0x18040121a  lea     r8d, [r9+3]; dwShareMode
0x18040121e  call    cs:__imp_CreateFileW
0x180401225  nop     dword ptr [rax+rax+00h]
0x18040122a  mov     rdi, rax
0x18040122d  lea     rcx, [rax-1]
0x180401231  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180401235  ja      short loc_180401277
0x180401237  mov     rax, [rbx+150h]
0x18040123e  mov     ebx, [rsp+1F8h+cchWideChar]
0x180401245  test    rax, rax
0x180401248  jz      short loc_180401264
0x18040124a  mov     r8d, ebx
0x18040124d  mov     rdx, rbp
0x180401250  mov     rcx, rsi
0x180401253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180401258  test    eax, eax
0x18040125a  jz      short loc_180401264
0x18040125c  cmp     eax, ebx
0x18040125e  jb      loc_180401389
0x180401264  mov     r8d, ebx; int
0x180401267  mov     rdx, rsi; unsigned __int16 *
0x18040126a  mov     rcx, rbp; unsigned __int16 *
0x18040126d  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x180401272  jmp     loc_180401389
0x180401277  call    cs:__imp_GetLastError
0x18040127e  nop     dword ptr [rax+rax+00h]
0x180401283  cmp     eax, 78h ; 'x'
0x180401286  jnz     loc_18040137E
0x18040128c  mov     [rsp+1F8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180401295  lea     rax, [rsp+1F8h+MultiByteStr]
0x18040129a  mov     [rsp+1F8h+hTemplateFile], 0; lpDefaultChar
0x1804012a3  or      r9d, 0FFFFFFFFh; cchWideChar
0x1804012a7  mov     [rsp+1F8h+dwFlagsAndAttributes], 168h; cbMultiByte
0x1804012af  mov     r8, rsi; lpWideCharStr
0x1804012b2  mov     edx, 400h; dwFlags
0x1804012b7  mov     qword ptr [rsp+1F8h+dwCreationDisposition], rax; lpMultiByteStr
0x1804012bc  xor     ecx, ecx; CodePage
0x1804012be  call    cs:__imp_WideCharToMultiByte
0x1804012c5  nop     dword ptr [rax+rax+00h]
0x1804012ca  test    eax, eax
0x1804012cc  jle     loc_18040137E
0x1804012d2  xor     r9d, r9d; lpSecurityAttributes
0x1804012d5  mov     [rsp+1F8h+hTemplateFile], 0; hTemplateFile
0x1804012de  mov     [rsp+1F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1804012e6  lea     rcx, [rsp+1F8h+MultiByteStr]; lpFileName
0x1804012eb  mov     edx, 80000000h; dwDesiredAccess
0x1804012f0  mov     [rsp+1F8h+dwCreationDisposition], 3; dwCreationDisposition
0x1804012f8  lea     r8d, [r9+3]; dwShareMode
0x1804012fc  call    cs:__imp_CreateFileA
0x180401303  nop     dword ptr [rax+rax+00h]
0x180401308  mov     rdi, rax
0x18040130b  test    rax, rax
0x18040130e  jz      loc_1804013B1
0x180401314  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180401318  jz      short loc_180401383
0x18040131a  mov     rax, [rbx+148h]
0x180401321  mov     ebx, [rsp+1F8h+cchWideChar]
0x180401328  test    rax, rax
0x18040132b  jz      loc_180401264
0x180401331  mov     r8d, 168h
0x180401337  lea     rdx, [rsp+1F8h+MultiByteStr]
0x18040133c  lea     rcx, [rsp+1F8h+MultiByteStr]
0x180401341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180401346  dec     eax
0x180401348  cmp     eax, 166h
0x18040134d  ja      loc_180401264
0x180401353  mov     [rsp+1F8h+dwFlagsAndAttributes], ebx; cchWideChar
0x180401357  lea     r8, [rsp+1F8h+MultiByteStr]; lpMultiByteStr
0x18040135c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180401360  mov     qword ptr [rsp+1F8h+dwCreationDisposition], rbp; lpWideCharStr
0x180401365  xor     edx, edx; dwFlags
0x180401367  xor     ecx, ecx; CodePage
0x180401369  call    cs:__imp_MultiByteToWideChar
0x180401370  nop     dword ptr [rax+rax+00h]
0x180401375  test    eax, eax
0x180401377  jnz     short loc_180401389
0x180401379  jmp     loc_180401264
0x18040137e  test    rdi, rdi
0x180401381  jz      short loc_1804013B1
0x180401383  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180401387  jz      short loc_1804013B1
0x180401389  xor     edx, edx; lpFileSizeHigh
0x18040138b  mov     rcx, rdi; hFile
0x18040138e  call    cs:__imp_GetFileSize
0x180401395  nop     dword ptr [rax+rax+00h]
0x18040139a  mov     [r14], eax
0x18040139d  cmp     eax, 0FFFFFFFFh
0x1804013a0  jnz     short loc_1804013E9
0x1804013a2  mov     rcx, rdi; hObject
0x1804013a5  call    cs:__imp_CloseHandle
0x1804013ac  nop     dword ptr [rax+rax+00h]
0x1804013b1  call    cs:__imp_GetLastError
0x1804013b8  nop     dword ptr [rax+rax+00h]
0x1804013bd  test    eax, eax
0x1804013bf  jz      loc_1804014CF
0x1804013c5  call    cs:__imp_GetLastError
0x1804013cc  nop     dword ptr [rax+rax+00h]
0x1804013d1  mov     ebx, eax
0x1804013d3  test    eax, eax
0x1804013d5  jle     loc_1804014D4
0x1804013db  movzx   ebx, ax
0x1804013de  or      ebx, 80070000h
0x1804013e4  jmp     loc_1804014D4
0x1804013e9  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x1804013f0  test    rax, rax
0x1804013f3  jnz     short loc_180401406
0x1804013f5  lea     ecx, [rax+78h]; dwErrCode
0x1804013f8  call    cs:__imp_SetLastError
0x1804013ff  nop     dword ptr [rax+rax+00h]
0x180401404  jmp     short loc_1804013A2
0x180401406  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x18040140d  test    rax, rax
0x180401410  jnz     short loc_180401417
0x180401412  lea     ecx, [rax+32h]
0x180401415  jmp     short loc_1804013F8
0x180401417  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x18040141e  xor     r9d, r9d
0x180401421  mov     qword ptr [rsp+1F8h+dwFlagsAndAttributes], 0
0x18040142a  xor     edx, edx
0x18040142c  mov     rcx, rdi
0x18040142f  mov     [rsp+1F8h+dwCreationDisposition], 0
0x180401437  lea     r8d, [r9+2]
0x18040143b  call    rax ; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x18040143d  nop     dword ptr [rax]
0x180401440  mov     rsi, rax
0x180401443  test    rax, rax
0x180401446  jz      loc_1804013A2
0x18040144c  xor     r9d, r9d; dwFileOffsetLow
0x18040144f  mov     qword ptr [rsp+1F8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180401458  xor     r8d, r8d; dwFileOffsetHigh
0x18040145b  mov     rcx, rax; hFileMappingObject
0x18040145e  lea     edx, [r9+4]; dwDesiredAccess
0x180401462  call    cs:__imp_MapViewOfFile
0x180401469  nop     dword ptr [rax+rax+00h]
0x18040146e  mov     rbp, rax
0x180401471  test    rax, rax
0x180401474  jnz     short loc_1804014AA
0x180401476  call    cs:__imp_GetLastError
0x18040147d  nop     dword ptr [rax+rax+00h]
0x180401482  test    eax, eax
0x180401484  jz      short loc_1804014A3
0x180401486  call    cs:__imp_GetLastError
0x18040148d  nop     dword ptr [rax+rax+00h]
0x180401492  mov     ebx, eax
0x180401494  test    eax, eax
0x180401496  jle     short loc_1804014AC
0x180401498  movzx   ebx, ax
0x18040149b  or      ebx, 80070000h
0x1804014a1  jmp     short loc_1804014AC
0x1804014a3  mov     ebx, 80004005h
0x1804014a8  jmp     short loc_1804014AC
0x1804014aa  xor     ebx, ebx
0x1804014ac  mov     rcx, rsi; hObject
0x1804014af  call    cs:__imp_CloseHandle
0x1804014b6  nop     dword ptr [rax+rax+00h]
0x1804014bb  mov     rcx, rdi; hObject
0x1804014be  call    cs:__imp_CloseHandle
0x1804014c5  nop     dword ptr [rax+rax+00h]
0x1804014ca  mov     [r15], rbp
0x1804014cd  jmp     short loc_1804014D4
0x1804014cf  mov     ebx, 80004005h
0x1804014d4  mov     eax, ebx
0x1804014d6  mov     rcx, [rsp+1F8h+var_48]
0x1804014de  xor     rcx, rsp; StackCookie
0x1804014e1  call    __security_check_cookie
0x1804014e6  add     rsp, 1C8h
0x1804014ed  pop     r15
0x1804014ef  pop     r14
0x1804014f1  pop     rdi
0x1804014f2  pop     rsi
0x1804014f3  pop     rbp
0x1804014f4  pop     rbx
0x1804014f5  retn
```
