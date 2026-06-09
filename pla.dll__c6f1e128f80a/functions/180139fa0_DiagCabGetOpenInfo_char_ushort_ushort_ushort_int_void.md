# DiagCabGetOpenInfo(char *,ushort *,ushort *,ushort *,int *,void *)

- ea: `0x180139fa0`
- end: `0x18013a200`
- name: `?DiagCabGetOpenInfo@@YA_JPEADPEAG11PEAHPEAX@Z`
- size: `608`
- prototype: `INT_PTR __fastcall(const CHAR *pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180139fa0`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_errno` at `0x18013a0e5`
- `msvcrt!_errno` at `0x18013a0e5`
- `msvcrt!_wopen` at `0x18013a0d8`
- `msvcrt!_wopen` at `0x18013a0d8`
- `msvcrt!_get_osfhandle` at `0x18013a0fc`
- `msvcrt!_get_osfhandle` at `0x18013a0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a02f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a09e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a18a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a02f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a09e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a18a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a194`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18013a17c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18013a17c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a063`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a063`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a1b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a1b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a1c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a1c5`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18013a148`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18013a148`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18013a110`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18013a110`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a015`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a094`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a015`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18013a094`

## pseudocode

```c
INT_PTR __fastcall DiagCabGetOpenInfo(const CHAR *pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err)
{
  int v9; // esi
  int v10; // eax
  int cchWideChar; // edi
  signed int v12; // eax
  int v13; // ebx
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v17; // rbp
  signed int v18; // eax
  int v19; // eax
  void *osfhandle; // rax
  signed int LastError; // eax
  signed int v22; // eax
  signed int v23; // eax
  HANDLE v24; // rax
  INT_PTR result; // rax
  struct _FILETIME LocalFileTime; // [rsp+30h] [rbp-98h] BYREF
  int *v27; // [rsp+38h] [rbp-90h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+40h] [rbp-88h] BYREF

  v27 = err;
  LocalFileTime = 0;
  v9 = -1;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v10 = MultiByteToWideChar(0xFDE9u, 8u, pszName, -1, 0, 0);
  cchWideChar = v10;
  if ( v10 )
  {
    v14 = 2LL * (v10 + 1);
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, v14);
    v17 = lpWideCharStr;
    if ( !lpWideCharStr )
    {
      v13 = -2147024882;
LABEL_36:
      result = -1;
      *v27 = v13;
      return result;
    }
    if ( MultiByteToWideChar(0xFDE9u, 8u, pszName, -1, lpWideCharStr, cchWideChar) )
    {
      v19 = _wopen(v17, 0x8000, 0);
      v9 = v19;
      if ( v19 != -1 )
      {
        osfhandle = (void *)_get_osfhandle(v19);
        if ( osfhandle != (void *)-1LL )
        {
          if ( !GetFileInformationByHandle(osfhandle, &FileInformation) && GetLastError() )
          {
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_34;
          }
          if ( !FileTimeToLocalFileTime(&FileInformation.ftLastWriteTime, &LocalFileTime) && GetLastError() )
          {
            v22 = GetLastError();
            v13 = v22;
            if ( v22 > 0 )
              v13 = (unsigned __int16)v22 | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_34;
          }
          if ( FileTimeToDosDateTime(&LocalFileTime, pdate, ptime) || !GetLastError() )
          {
            v13 = 0;
          }
          else
          {
            v23 = GetLastError();
            v13 = v23;
            if ( v23 > 0 )
              v13 = (unsigned __int16)v23 | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_34;
          }
          *pattribs = FileInformation.dwFileAttributes & 0x27;
LABEL_34:
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v17);
          goto LABEL_35;
        }
      }
      v13 = *_errno();
      if ( v13 <= 0 )
        goto LABEL_34;
      v13 = (unsigned __int16)v13;
    }
    else
    {
      if ( !GetLastError() )
      {
        v13 = 0;
        goto LABEL_34;
      }
      v18 = GetLastError();
      v13 = v18;
      if ( v18 <= 0 )
        goto LABEL_34;
      v13 = (unsigned __int16)v18;
    }
    v13 |= 0x80070000;
    goto LABEL_34;
  }
  if ( !GetLastError() )
    return v9;
  v12 = GetLastError();
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
LABEL_35:
  if ( v13 < 0 )
    goto LABEL_36;
  return v9;
}

```

## disassembly

```asm
0x180139fa0  push    rbx
0x180139fa2  push    rbp
0x180139fa3  push    rsi
0x180139fa4  push    rdi
0x180139fa5  push    r12
0x180139fa7  push    r13
0x180139fa9  push    r14
0x180139fab  push    r15
0x180139fad  sub     rsp, 88h
0x180139fb4  mov     rax, cs:__security_cookie
0x180139fbb  xor     rax, rsp
0x180139fbe  mov     [rsp+0C8h+var_50], rax
0x180139fc3  mov     rax, [rsp+0C8h+err]
0x180139fcb  xorps   xmm0, xmm0
0x180139fce  xor     ebx, ebx
0x180139fd0  mov     [rsp+0C8h+var_90], rax
0x180139fd5  xor     eax, eax
0x180139fd7  mov     [rsp+0C8h+cchWideChar], ebx; cchWideChar
0x180139fdb  mov     r12, r8
0x180139fde  mov     [rsp+0C8h+FileInformation.nFileIndexLow], eax
0x180139fe2  mov     r13, r9
0x180139fe5  mov     qword ptr [rsp+0C8h+LocalFileTime.dwLowDateTime], rbx
0x180139fea  mov     r15, rdx
0x180139fed  mov     [rsp+0C8h+lpWideCharStr], rbx; lpWideCharStr
0x180139ff2  mov     r14, rcx
0x180139ff5  lea     edx, [rax+8]; dwFlags
0x180139ff8  mov     r8, rcx; lpMultiByteStr
0x180139ffb  or      esi, 0FFFFFFFFh
0x180139ffe  or      r9d, esi; cbMultiByte
0x18013a001  mov     ecx, 0FDE9h; CodePage
0x18013a006  movups  xmmword ptr [rsp+0C8h+FileInformation.dwFileAttributes], xmm0
0x18013a00b  movups  xmmword ptr [rsp+0C8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18013a010  movups  xmmword ptr [rsp+0C8h+FileInformation.nFileSizeHigh], xmm0
0x18013a015  call    cs:__imp_MultiByteToWideChar
0x18013a01b  mov     edi, eax
0x18013a01d  test    eax, eax
0x18013a01f  jnz     short loc_18013A04D
0x18013a021  call    cs:__imp_GetLastError
0x18013a027  test    eax, eax
0x18013a029  jz      loc_18013A1DC
0x18013a02f  call    cs:__imp_GetLastError
0x18013a035  mov     ebx, eax
0x18013a037  test    eax, eax
0x18013a039  jle     loc_18013A1CB
0x18013a03f  movzx   ebx, ax
0x18013a042  or      ebx, 80070000h
0x18013a048  jmp     loc_18013A1CB
0x18013a04d  inc     eax
0x18013a04f  movsxd  rbx, eax
0x18013a052  add     rbx, rbx
0x18013a055  call    cs:__imp_GetProcessHeap
0x18013a05b  mov     r8, rbx; dwBytes
0x18013a05e  xor     edx, edx; dwFlags
0x18013a060  mov     rcx, rax; hHeap
0x18013a063  call    cs:__imp_HeapAlloc
0x18013a069  mov     rbp, rax
0x18013a06c  test    rax, rax
0x18013a06f  jnz     short loc_18013A07B
0x18013a071  mov     ebx, 8007000Eh
0x18013a076  jmp     loc_18013A1CF
0x18013a07b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18013a07f  mov     [rsp+0C8h+cchWideChar], edi; cchWideChar
0x18013a083  mov     r8, r14; lpMultiByteStr
0x18013a086  mov     [rsp+0C8h+lpWideCharStr], rbp; lpWideCharStr
0x18013a08b  mov     ecx, 0FDE9h; CodePage
0x18013a090  lea     edx, [r9+9]; dwFlags
0x18013a094  call    cs:__imp_MultiByteToWideChar
0x18013a09a  test    eax, eax
0x18013a09c  jnz     short loc_18013A0CD
0x18013a09e  call    cs:__imp_GetLastError
0x18013a0a4  test    eax, eax
0x18013a0a6  jnz     short loc_18013A0AF
0x18013a0a8  xor     ebx, ebx
0x18013a0aa  jmp     loc_18013A1B7
0x18013a0af  call    cs:__imp_GetLastError
0x18013a0b5  mov     ebx, eax
0x18013a0b7  test    eax, eax
0x18013a0b9  jle     loc_18013A1B7
0x18013a0bf  movzx   ebx, ax
0x18013a0c2  or      ebx, 80070000h
0x18013a0c8  jmp     loc_18013A1B7
0x18013a0cd  xor     r8d, r8d
0x18013a0d0  mov     edx, 8000h; OpenFlag
0x18013a0d5  mov     rcx, rbp; FileName
0x18013a0d8  call    cs:__imp__wopen
0x18013a0de  mov     esi, eax
0x18013a0e0  cmp     eax, 0FFFFFFFFh
0x18013a0e3  jnz     short loc_18013A0FA
0x18013a0e5  call    cs:__imp__errno
0x18013a0eb  mov     ebx, [rax]
0x18013a0ed  test    ebx, ebx
0x18013a0ef  jle     loc_18013A1B7
0x18013a0f5  movzx   ebx, bx
0x18013a0f8  jmp     short loc_18013A0C2
0x18013a0fa  mov     ecx, eax; FileHandle
0x18013a0fc  call    cs:__imp__get_osfhandle
0x18013a102  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013a106  jz      short loc_18013A0E5
0x18013a108  lea     rdx, [rsp+0C8h+FileInformation]; lpFileInformation
0x18013a10d  mov     rcx, rax; hFile
0x18013a110  call    cs:__imp_GetFileInformationByHandle
0x18013a116  mov     edi, 80070000h
0x18013a11b  test    eax, eax
0x18013a11d  jnz     short loc_18013A13E
0x18013a11f  call    cs:__imp_GetLastError
0x18013a125  test    eax, eax
0x18013a127  jz      short loc_18013A13E
0x18013a129  call    cs:__imp_GetLastError
0x18013a12f  mov     ebx, eax
0x18013a131  test    eax, eax
0x18013a133  jle     short loc_18013A13A
0x18013a135  movzx   ebx, ax
0x18013a138  or      ebx, edi
0x18013a13a  test    ebx, ebx
0x18013a13c  js      short loc_18013A1B7
0x18013a13e  lea     rdx, [rsp+0C8h+LocalFileTime]; lpLocalFileTime
0x18013a143  lea     rcx, [rsp+0C8h+FileInformation.ftLastWriteTime]; lpFileTime
0x18013a148  call    cs:__imp_FileTimeToLocalFileTime
0x18013a14e  test    eax, eax
0x18013a150  jnz     short loc_18013A171
0x18013a152  call    cs:__imp_GetLastError
0x18013a158  test    eax, eax
0x18013a15a  jz      short loc_18013A171
0x18013a15c  call    cs:__imp_GetLastError
0x18013a162  mov     ebx, eax
0x18013a164  test    eax, eax
0x18013a166  jle     short loc_18013A16D
0x18013a168  movzx   ebx, ax
0x18013a16b  or      ebx, edi
0x18013a16d  test    ebx, ebx
0x18013a16f  js      short loc_18013A1B7
0x18013a171  mov     r8, r12; lpFatTime
0x18013a174  lea     rcx, [rsp+0C8h+LocalFileTime]; lpFileTime
0x18013a179  mov     rdx, r15; lpFatDate
0x18013a17c  call    cs:__imp_FileTimeToDosDateTime
0x18013a182  test    eax, eax
0x18013a184  jz      short loc_18013A18A
0x18013a186  xor     ebx, ebx
0x18013a188  jmp     short loc_18013A1A9
0x18013a18a  call    cs:__imp_GetLastError
0x18013a190  test    eax, eax
0x18013a192  jz      short loc_18013A186
0x18013a194  call    cs:__imp_GetLastError
0x18013a19a  mov     ebx, eax
0x18013a19c  test    eax, eax
0x18013a19e  jle     short loc_18013A1A5
0x18013a1a0  movzx   ebx, ax
0x18013a1a3  or      ebx, edi
0x18013a1a5  test    ebx, ebx
0x18013a1a7  js      short loc_18013A1B7
0x18013a1a9  movzx   eax, word ptr [rsp+0C8h+FileInformation.dwFileAttributes]
0x18013a1ae  and     ax, 27h
0x18013a1b2  mov     [r13+0], ax
0x18013a1b7  call    cs:__imp_GetProcessHeap
0x18013a1bd  mov     r8, rbp; lpMem
0x18013a1c0  xor     edx, edx; dwFlags
0x18013a1c2  mov     rcx, rax; hHeap
0x18013a1c5  call    cs:__imp_HeapFree
0x18013a1cb  test    ebx, ebx
0x18013a1cd  jns     short loc_18013A1DC
0x18013a1cf  mov     rcx, [rsp+0C8h+var_90]
0x18013a1d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18013a1d8  mov     [rcx], ebx
0x18013a1da  jmp     short loc_18013A1DF
0x18013a1dc  movsxd  rax, esi
0x18013a1df  mov     rcx, [rsp+0C8h+var_50]
0x18013a1e4  xor     rcx, rsp; StackCookie
0x18013a1e7  call    __security_check_cookie
0x18013a1ec  add     rsp, 88h
0x18013a1f3  pop     r15
0x18013a1f5  pop     r14
0x18013a1f7  pop     r13
0x18013a1f9  pop     r12
0x18013a1fb  pop     rdi
0x18013a1fc  pop     rsi
0x18013a1fd  pop     rbp
0x18013a1fe  pop     rbx
0x18013a1ff  retn
```
