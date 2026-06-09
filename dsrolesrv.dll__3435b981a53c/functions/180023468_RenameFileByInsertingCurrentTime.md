# RenameFileByInsertingCurrentTime

- ea: `0x180023468`
- end: `0x1800235ea`
- name: `RenameFileByInsertingCurrentTime`
- size: `386`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, wchar_t *lpNewFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000b480`

## callees

- `0x180008f24`
- `0x180008fd4`
- `0x18000e4d0`
- `0x180023468`
- `0x18002c050`

## import_xrefs

- `msvcrt!calloc` at `0x1800234b2`
- `msvcrt!calloc` at `0x1800234b2`
- `msvcrt!free` at `0x1800235c1`
- `msvcrt!free` at `0x1800235c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002350d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002350d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235b6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800235ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800235ac`

## pseudocode

```c
__int64 __fastcall RenameFileByInsertingCurrentTime(LPCWSTR lpExistingFileName, wchar_t *lpNewFileName)
{
  __int64 v2; // rbx
  wchar_t *v5; // rax
  wchar_t *v6; // rdi
  DWORD LastError; // ebx
  HRESULT v8; // eax
  const wchar_t *v9; // rsi
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-48h] BYREF

  v2 = -1;
  SystemTime = 0;
  do
    ++v2;
  while ( lpExistingFileName[v2] );
  v5 = (wchar_t *)calloc((unsigned int)(v2 + 1), 2u);
  v6 = v5;
  if ( v5 )
  {
    v8 = StringCchCopyW(v5, (unsigned int)(v2 + 1), lpExistingFileName);
    if ( v8 < 0 )
      goto LABEL_6;
    v9 = 0;
    while ( (_DWORD)v2 )
    {
      if ( v6[(unsigned int)(v2 - 1)] == 46 )
      {
        v6[(unsigned int)(v2 - 1)] = 0;
        v9 = &v6[(unsigned int)v2];
        break;
      }
      LODWORD(v2) = v2 - 1;
    }
    GetLocalTime(&SystemTime);
    v8 = StringCchPrintfW(
           lpNewFileName,
           0x105u,
           L"%s.%.04d%.02d%.02d-%.02d%.02d%.02d",
           v6,
           SystemTime.wYear,
           SystemTime.wMonth,
           SystemTime.wDay,
           SystemTime.wHour,
           SystemTime.wMinute,
           SystemTime.wSecond);
    if ( v8 < 0
      || v9
      && ((v8 = StringCchCatW(lpNewFileName, 0x105u, L"."), v8 < 0)
       || (v8 = StringCchCatW(lpNewFileName, 0x105u, v9), v8 < 0)) )
    {
LABEL_6:
      LastError = (unsigned __int16)v8;
    }
    else
    {
      LastError = 0;
      if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
        LastError = GetLastError();
    }
    free(v6);
  }
  else
  {
    return 8;
  }
  return LastError;
}

```

## disassembly

```asm
0x180023468  mov     [rsp+arg_10], rbx
0x18002346d  push    rbp
0x18002346e  push    rsi
0x18002346f  push    rdi
0x180023470  push    r14
0x180023472  push    r15
0x180023474  sub     rsp, 70h
0x180023478  mov     rax, cs:__security_cookie
0x18002347f  xor     rax, rsp
0x180023482  mov     [rsp+98h+var_38], rax
0x180023487  xorps   xmm0, xmm0
0x18002348a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002348e  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x180023493  xor     r15d, r15d
0x180023496  mov     rbp, rdx
0x180023499  mov     r14, rcx
0x18002349c  inc     rbx
0x18002349f  cmp     [rcx+rbx*2], r15w
0x1800234a4  jnz     short loc_18002349C
0x1800234a6  lea     eax, [rbx+1]
0x1800234a9  mov     edx, 2; Size
0x1800234ae  mov     ecx, eax; Count
0x1800234b0  mov     esi, eax
0x1800234b2  call    cs:__imp_calloc
0x1800234b8  mov     rdi, rax
0x1800234bb  test    rax, rax
0x1800234be  jnz     short loc_1800234C8
0x1800234c0  lea     ebx, [rax+8]
0x1800234c3  jmp     loc_1800235C7
0x1800234c8  mov     r8, r14; pszSrc
0x1800234cb  mov     rdx, rsi; cchDest
0x1800234ce  mov     rcx, rdi; pszDest
0x1800234d1  call    StringCchCopyW
0x1800234d6  test    eax, eax
0x1800234d8  jns     short loc_1800234E2
0x1800234da  movzx   ebx, ax
0x1800234dd  jmp     loc_1800235BE
0x1800234e2  mov     rsi, r15
0x1800234e5  test    ebx, ebx
0x1800234e7  jz      short loc_180023508
0x1800234e9  lea     eax, [rbx-1]
0x1800234ec  mov     edx, 2Eh ; '.'
0x1800234f1  mov     ecx, eax
0x1800234f3  cmp     dx, [rdi+rax*2]
0x1800234f7  jz      short loc_1800234FD
0x1800234f9  mov     ebx, eax
0x1800234fb  jmp     short loc_1800234E5
0x1800234fd  mov     eax, ebx
0x1800234ff  mov     [rdi+rcx*2], r15w
0x180023504  lea     rsi, [rdi+rax*2]
0x180023508  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x18002350d  call    cs:__imp_GetLocalTime
0x180023513  movzx   ecx, [rsp+98h+SystemTime.wMinute]
0x180023518  mov     ebx, 105h
0x18002351d  movzx   edx, [rsp+98h+SystemTime.wHour]
0x180023522  movzx   r8d, [rsp+98h+SystemTime.wDay]
0x180023528  movzx   r9d, [rsp+98h+SystemTime.wMonth]
0x18002352e  movzx   eax, [rsp+98h+SystemTime.wSecond]
0x180023533  movzx   r10d, [rsp+98h+SystemTime.wYear]
0x180023539  mov     [rsp+98h+var_50], eax
0x18002353d  mov     [rsp+98h+var_58], ecx
0x180023541  mov     rcx, rbp; pszDest
0x180023544  mov     [rsp+98h+var_60], edx
0x180023548  mov     edx, ebx; cchDest
0x18002354a  mov     [rsp+98h+var_68], r8d
0x18002354f  lea     r8, aS04d02d02d02d0; "%s.%.04d%.02d%.02d-%.02d%.02d%.02d"
0x180023556  mov     [rsp+98h+var_70], r9d
0x18002355b  mov     r9, rdi
0x18002355e  mov     [rsp+98h+var_78], r10d
0x180023563  call    StringCchPrintfW
0x180023568  test    eax, eax
0x18002356a  js      loc_1800234DA
0x180023570  test    rsi, rsi
0x180023573  jz      short loc_1800235A3
0x180023575  lea     r8, asc_18003D3A8; "."
0x18002357c  mov     edx, ebx; cchDest
0x18002357e  mov     rcx, rbp; pszDest
0x180023581  call    StringCchCatW
0x180023586  test    eax, eax
0x180023588  js      loc_1800234DA
0x18002358e  mov     r8, rsi; pszSrc
0x180023591  mov     edx, ebx; cchDest
0x180023593  mov     rcx, rbp; pszDest
0x180023596  call    StringCchCatW
0x18002359b  test    eax, eax
0x18002359d  js      loc_1800234DA
0x1800235a3  mov     rdx, rbp; lpNewFileName
0x1800235a6  mov     rcx, r14; lpExistingFileName
0x1800235a9  mov     ebx, r15d
0x1800235ac  call    cs:__imp_MoveFileW
0x1800235b2  test    eax, eax
0x1800235b4  jnz     short loc_1800235BE
0x1800235b6  call    cs:__imp_GetLastError
0x1800235bc  mov     ebx, eax
0x1800235be  mov     rcx, rdi; Block
0x1800235c1  call    cs:__imp_free
0x1800235c7  mov     eax, ebx
0x1800235c9  mov     rcx, [rsp+98h+var_38]
0x1800235ce  xor     rcx, rsp; StackCookie
0x1800235d1  call    __security_check_cookie
0x1800235d6  mov     rbx, [rsp+98h+arg_10]
0x1800235de  add     rsp, 70h
0x1800235e2  pop     r15
0x1800235e4  pop     r14
0x1800235e6  pop     rdi
0x1800235e7  pop     rsi
0x1800235e8  pop     rbp
0x1800235e9  retn
```
