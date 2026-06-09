# Win32LiveSystemProvider::OpenMapping(ushort const *,ulong *,ushort *,ulong,void * *)

- ea: `0x180014ed0`
- end: `0x1800151a9`
- name: `?OpenMapping@Win32LiveSystemProvider@@UEAAJPEBGPEAKPEAGKPEAPEAX@Z`
- size: `729`
- prototype: `int(Win32LiveSystemProvider *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001710`
- `0x180014ed0`
- `0x18001bec8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001514b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001514b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800150d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800150d2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015133`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015091`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001516e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015091`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001516e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015177`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015061`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180015061`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014fc2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014fc2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180015080`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180015080`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180014ffa`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180014ffa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014f2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014f2e`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::OpenMapping(
        Win32LiveSystemProvider *this,
        WCHAR *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned int cchWideChar,
        void **a6)
{
  char *FileW; // rdi
  __int64 (__fastcall *v11)(WCHAR *, unsigned __int16 *, _QWORD); // rax
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
  v11 = (__int64 (__fastcall *)(WCHAR *, unsigned __int16 *, _QWORD))*((_QWORD *)this + 42);
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
0x180014ed0  push    rbx
0x180014ed2  push    rbp
0x180014ed3  push    rsi
0x180014ed4  push    rdi
0x180014ed5  push    r14
0x180014ed7  push    r15
0x180014ed9  sub     rsp, 1C8h
0x180014ee0  mov     rax, cs:__security_cookie
0x180014ee7  xor     rax, rsp
0x180014eea  mov     [rsp+1F8h+var_48], rax
0x180014ef2  mov     r15, [rsp+1F8h+arg_28]
0x180014efa  mov     rsi, rdx
0x180014efd  mov     rbp, r9
0x180014f00  mov     [rsp+1F8h+hTemplateFile], 0; hTemplateFile
0x180014f09  xor     r9d, r9d; lpSecurityAttributes
0x180014f0c  mov     [rsp+1F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180014f14  mov     r14, r8
0x180014f17  mov     [rsp+1F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180014f1f  mov     rbx, rcx
0x180014f22  mov     edx, 80000000h; dwDesiredAccess
0x180014f27  mov     rcx, rsi; lpFileName
0x180014f2a  lea     r8d, [r9+3]; dwShareMode
0x180014f2e  call    cs:__imp_CreateFileW
0x180014f34  mov     rdi, rax
0x180014f37  lea     rcx, [rax-1]
0x180014f3b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180014f3f  ja      short loc_180014F81
0x180014f41  mov     rax, [rbx+150h]
0x180014f48  mov     ebx, [rsp+1F8h+cchWideChar]
0x180014f4f  test    rax, rax
0x180014f52  jz      short loc_180014F6E
0x180014f54  mov     r8d, ebx
0x180014f57  mov     rdx, rbp
0x180014f5a  mov     rcx, rsi
0x180014f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f62  test    eax, eax
0x180014f64  jz      short loc_180014F6E
0x180014f66  cmp     eax, ebx
0x180014f68  jb      loc_18001507B
0x180014f6e  mov     r8d, ebx; int
0x180014f71  mov     rdx, rsi; unsigned __int16 *
0x180014f74  mov     rcx, rbp; unsigned __int16 *
0x180014f77  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x180014f7c  jmp     loc_18001507B
0x180014f81  call    cs:__imp_GetLastError
0x180014f87  cmp     eax, 78h ; 'x'
0x180014f8a  jnz     loc_180015070
0x180014f90  mov     [rsp+1F8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180014f99  lea     rax, [rsp+1F8h+MultiByteStr]
0x180014f9e  mov     [rsp+1F8h+hTemplateFile], 0; lpDefaultChar
0x180014fa7  or      r9d, 0FFFFFFFFh; cchWideChar
0x180014fab  mov     [rsp+1F8h+dwFlagsAndAttributes], 168h; cbMultiByte
0x180014fb3  mov     r8, rsi; lpWideCharStr
0x180014fb6  mov     edx, 400h; dwFlags
0x180014fbb  mov     qword ptr [rsp+1F8h+dwCreationDisposition], rax; lpMultiByteStr
0x180014fc0  xor     ecx, ecx; CodePage
0x180014fc2  call    cs:__imp_WideCharToMultiByte
0x180014fc8  test    eax, eax
0x180014fca  jle     loc_180015070
0x180014fd0  xor     r9d, r9d; lpSecurityAttributes
0x180014fd3  mov     [rsp+1F8h+hTemplateFile], 0; hTemplateFile
0x180014fdc  mov     [rsp+1F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180014fe4  lea     rcx, [rsp+1F8h+MultiByteStr]; lpFileName
0x180014fe9  mov     edx, 80000000h; dwDesiredAccess
0x180014fee  mov     [rsp+1F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180014ff6  lea     r8d, [r9+3]; dwShareMode
0x180014ffa  call    cs:__imp_CreateFileA
0x180015000  mov     rdi, rax
0x180015003  test    rax, rax
0x180015006  jz      loc_180015097
0x18001500c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015010  jz      short loc_180015075
0x180015012  mov     rax, [rbx+148h]
0x180015019  mov     ebx, [rsp+1F8h+cchWideChar]
0x180015020  test    rax, rax
0x180015023  jz      loc_180014F6E
0x180015029  mov     r8d, 168h
0x18001502f  lea     rdx, [rsp+1F8h+MultiByteStr]
0x180015034  lea     rcx, [rsp+1F8h+MultiByteStr]
0x180015039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001503e  dec     eax
0x180015040  cmp     eax, 166h
0x180015045  ja      loc_180014F6E
0x18001504b  mov     [rsp+1F8h+dwFlagsAndAttributes], ebx; cchWideChar
0x18001504f  lea     r8, [rsp+1F8h+MultiByteStr]; lpMultiByteStr
0x180015054  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180015058  mov     qword ptr [rsp+1F8h+dwCreationDisposition], rbp; lpWideCharStr
0x18001505d  xor     edx, edx; dwFlags
0x18001505f  xor     ecx, ecx; CodePage
0x180015061  call    cs:__imp_MultiByteToWideChar
0x180015067  test    eax, eax
0x180015069  jnz     short loc_18001507B
0x18001506b  jmp     loc_180014F6E
0x180015070  test    rdi, rdi
0x180015073  jz      short loc_180015097
0x180015075  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180015079  jz      short loc_180015097
0x18001507b  xor     edx, edx; lpFileSizeHigh
0x18001507d  mov     rcx, rdi; hFile
0x180015080  call    cs:__imp_GetFileSize
0x180015086  mov     [r14], eax
0x180015089  cmp     eax, 0FFFFFFFFh
0x18001508c  jnz     short loc_1800150C3
0x18001508e  mov     rcx, rdi; hObject
0x180015091  call    cs:__imp_CloseHandle
0x180015097  call    cs:__imp_GetLastError
0x18001509d  test    eax, eax
0x18001509f  jz      loc_180015182
0x1800150a5  call    cs:__imp_GetLastError
0x1800150ab  mov     ebx, eax
0x1800150ad  test    eax, eax
0x1800150af  jle     loc_180015187
0x1800150b5  movzx   ebx, ax
0x1800150b8  or      ebx, 80070000h
0x1800150be  jmp     loc_180015187
0x1800150c3  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x1800150ca  test    rax, rax
0x1800150cd  jnz     short loc_1800150DA
0x1800150cf  lea     ecx, [rax+78h]; dwErrCode
0x1800150d2  call    cs:__imp_SetLastError
0x1800150d8  jmp     short loc_18001508E
0x1800150da  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x1800150e1  test    rax, rax
0x1800150e4  jnz     short loc_1800150EB
0x1800150e6  lea     ecx, [rax+32h]
0x1800150e9  jmp     short loc_1800150D2
0x1800150eb  mov     rax, qword ptr cs:?g_Kernel32CallsMdwd@@3UKERNEL32_CALLS_MDWD@@C; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x1800150f2  xor     r9d, r9d
0x1800150f5  mov     qword ptr [rsp+1F8h+dwFlagsAndAttributes], 0
0x1800150fe  xor     edx, edx
0x180015100  mov     rcx, rdi
0x180015103  mov     [rsp+1F8h+dwCreationDisposition], 0
0x18001510b  lea     r8d, [r9+2]
0x18001510f  call    rax ; KERNEL32_CALLS_MDWD volatile g_Kernel32CallsMdwd
0x180015111  mov     rsi, rax
0x180015114  test    rax, rax
0x180015117  jz      loc_18001508E
0x18001511d  xor     r9d, r9d; dwFileOffsetLow
0x180015120  mov     qword ptr [rsp+1F8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180015129  xor     r8d, r8d; dwFileOffsetHigh
0x18001512c  mov     rcx, rax; hFileMappingObject
0x18001512f  lea     edx, [r9+4]; dwDesiredAccess
0x180015133  call    cs:__imp_MapViewOfFile
0x180015139  mov     rbp, rax
0x18001513c  test    rax, rax
0x18001513f  jnz     short loc_180015169
0x180015141  call    cs:__imp_GetLastError
0x180015147  test    eax, eax
0x180015149  jz      short loc_180015162
0x18001514b  call    cs:__imp_GetLastError
0x180015151  mov     ebx, eax
0x180015153  test    eax, eax
0x180015155  jle     short loc_18001516B
0x180015157  movzx   ebx, ax
0x18001515a  or      ebx, 80070000h
0x180015160  jmp     short loc_18001516B
0x180015162  mov     ebx, 80004005h
0x180015167  jmp     short loc_18001516B
0x180015169  xor     ebx, ebx
0x18001516b  mov     rcx, rsi; hObject
0x18001516e  call    cs:__imp_CloseHandle
0x180015174  mov     rcx, rdi; hObject
0x180015177  call    cs:__imp_CloseHandle
0x18001517d  mov     [r15], rbp
0x180015180  jmp     short loc_180015187
0x180015182  mov     ebx, 80004005h
0x180015187  mov     eax, ebx
0x180015189  mov     rcx, [rsp+1F8h+var_48]
0x180015191  xor     rcx, rsp; StackCookie
0x180015194  call    __security_check_cookie
0x180015199  add     rsp, 1C8h
0x1800151a0  pop     r15
0x1800151a2  pop     r14
0x1800151a4  pop     rdi
0x1800151a5  pop     rsi
0x1800151a6  pop     rbp
0x1800151a7  pop     rbx
0x1800151a8  retn
```
