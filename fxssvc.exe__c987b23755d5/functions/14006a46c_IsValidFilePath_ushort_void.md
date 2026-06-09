# IsValidFilePath(ushort *,void *)

- ea: `0x14006a46c`
- end: `0x14006a674`
- name: `?IsValidFilePath@@YAHPEAGPEAX@Z`
- size: `520`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *, HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x14006bff4`

## callees

- `0x140002c43`
- `0x140004ce4`
- `0x140004d44`
- `0x140068fcc`
- `0x14006a46c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetFileInformationByHandle` at `0x14006a5d6`
- `KERNEL32!GetFileInformationByHandle` at `0x14006a5d6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14006a504`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14006a504`
- `KERNEL32!GetLastError` at `0x14006a637`
- `KERNEL32!GetLastError` at `0x14006a637`
- `msvcrt!wcsnlen` at `0x14006a548`
- `msvcrt!wcsnlen` at `0x14006a558`
- `msvcrt!wcsnlen` at `0x14006a56d`
- `msvcrt!wcsnlen` at `0x14006a548`
- `msvcrt!wcsnlen` at `0x14006a558`
- `msvcrt!wcsnlen` at `0x14006a56d`
- `msvcrt!_wcsnicmp` at `0x14006a525`
- `msvcrt!_wcsnicmp` at `0x14006a57d`
- `msvcrt!_wcsnicmp` at `0x14006a525`
- `msvcrt!_wcsnicmp` at `0x14006a57d`
- `msvcrt!free` at `0x14006a62f`
- `msvcrt!free` at `0x14006a62f`

## pseudocode

```c
_BOOL8 __fastcall IsValidFilePath(unsigned __int16 *a1, HANDLE hFile)
{
  int v4; // ebx
  char v5; // si
  size_t v6; // rbx
  size_t v7; // rax
  WCHAR *v8; // rcx
  size_t v9; // rax
  signed int LastError; // eax
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String2[12]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR szFilePath[520]; // [rsp+80h] [rbp-80h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  memset_0(szFilePath, 0, sizeof(szFilePath));
  wcscpy(String2, L"\\\\?\\");
  if ( hFile == (HANDLE)-1LL )
  {
    v4 = -2147024809;
    return v4 >= 0;
  }
  if ( GetFinalPathNameByHandleW(hFile, szFilePath, 0x208u, 0) - 1 <= 0x207 )
  {
    if ( _wcsnicmp(a1, String2, 4u) )
    {
      a1 = ConvertFullPathToLongUNC(a1);
      v5 = 1;
    }
    else
    {
      v5 = 0;
    }
    v6 = wcsnlen(a1, 0x208u);
    v7 = wcsnlen(szFilePath, 0x208u);
    v8 = szFilePath;
    if ( v7 >= v6 )
      v8 = a1;
    v9 = wcsnlen(v8, 0x208u);
    if ( _wcsnicmp(szFilePath, a1, v9) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (_DWORD)a1,
          (__int64)szFilePath);
      }
    }
    else if ( GetFileInformationByHandle(hFile, &FileInformation) )
    {
      if ( FileInformation.nNumberOfLinks <= 1 )
      {
        v4 = 0;
        goto LABEL_22;
      }
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, a1);
      }
    }
    v4 = -2147024735;
LABEL_22:
    if ( v5 && a1 )
      free(a1);
    return v4 >= 0;
  }
  LastError = GetLastError();
  v4 = -2147024896;
  if ( LastError <= 0 )
    v4 = LastError;
  return v4 >= 0;
}

```

## disassembly

```asm
0x14006a46c  mov     [rsp-8+arg_10], rbx
0x14006a471  push    rbp
0x14006a472  push    rsi
0x14006a473  push    rdi
0x14006a474  push    r14
0x14006a476  push    r15
0x14006a478  lea     rbp, [rsp-3A0h]
0x14006a480  sub     rsp, 4A0h
0x14006a487  mov     rax, cs:__security_cookie
0x14006a48e  xor     rax, rsp
0x14006a491  mov     [rbp+3C0h+var_30], rax
0x14006a498  xorps   xmm0, xmm0
0x14006a49b  mov     r14, rdx
0x14006a49e  mov     rdi, rcx
0x14006a4a1  xor     eax, eax
0x14006a4a3  xor     edx, edx; Val
0x14006a4a5  mov     [rsp+4C0h+FileInformation.nFileIndexLow], eax
0x14006a4a9  lea     rcx, [rbp+3C0h+szFilePath]; void *
0x14006a4ad  mov     r8d, 410h; Size
0x14006a4b3  movups  xmmword ptr [rsp+4C0h+FileInformation.dwFileAttributes], xmm0
0x14006a4b8  movups  xmmword ptr [rsp+4C0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x14006a4bd  movups  xmmword ptr [rsp+4C0h+FileInformation.nFileSizeHigh], xmm0
0x14006a4c2  call    memset_0
0x14006a4c7  movsd   xmm0, qword ptr cs:asc_14008F9A0; "\\\\?\\"
0x14006a4cf  movzx   eax, word ptr cs:asc_14008F9A0+8; ""
0x14006a4d6  movsd   qword ptr [rsp+4C0h+String2], xmm0
0x14006a4dc  mov     [rsp+4C0h+var_450], ax
0x14006a4e1  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14006a4e5  jnz     short loc_14006A4F1
0x14006a4e7  mov     ebx, 80070057h
0x14006a4ec  jmp     loc_14006A647
0x14006a4f1  mov     r15d, 208h
0x14006a4f7  lea     rdx, [rbp+3C0h+szFilePath]; lpszFilePath
0x14006a4fb  mov     r8d, r15d; cchFilePath
0x14006a4fe  xor     r9d, r9d; dwFlags
0x14006a501  mov     rcx, r14; hFile
0x14006a504  call    cs:__imp_GetFinalPathNameByHandleW
0x14006a50a  dec     eax
0x14006a50c  cmp     eax, 207h
0x14006a511  ja      loc_14006A637
0x14006a517  mov     r8d, 4; MaxCount
0x14006a51d  lea     rdx, [rsp+4C0h+String2]; String2
0x14006a522  mov     rcx, rdi; String1
0x14006a525  call    cs:__imp__wcsnicmp
0x14006a52b  test    eax, eax
0x14006a52d  jz      short loc_14006A53F
0x14006a52f  mov     rcx, rdi; unsigned __int16 *
0x14006a532  call    ?ConvertFullPathToLongUNC@@YAPEAGPEAG@Z; ConvertFullPathToLongUNC(ushort *)
0x14006a537  mov     rdi, rax
0x14006a53a  mov     sil, 1
0x14006a53d  jmp     short loc_14006A542
0x14006a53f  xor     sil, sil
0x14006a542  mov     rdx, r15; MaxCount
0x14006a545  mov     rcx, rdi; Source
0x14006a548  call    cs:__imp_wcsnlen
0x14006a54e  mov     rdx, r15; MaxCount
0x14006a551  lea     rcx, [rbp+3C0h+szFilePath]; Source
0x14006a555  mov     rbx, rax
0x14006a558  call    cs:__imp_wcsnlen
0x14006a55e  mov     rdx, r15; MaxCount
0x14006a561  lea     rcx, [rbp+3C0h+szFilePath]
0x14006a565  cmp     rax, rbx
0x14006a568  jb      short loc_14006A56D
0x14006a56a  mov     rcx, rdi; Source
0x14006a56d  call    cs:__imp_wcsnlen
0x14006a573  mov     rdx, rdi; String2
0x14006a576  lea     rcx, [rbp+3C0h+szFilePath]; String1
0x14006a57a  mov     r8, rax; MaxCount
0x14006a57d  call    cs:__imp__wcsnicmp
0x14006a583  test    eax, eax
0x14006a585  jz      short loc_14006A5CE
0x14006a587  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a58e  lea     rax, WPP_GLOBAL_Control
0x14006a595  cmp     rcx, rax
0x14006a598  jz      short loc_14006A5C7
0x14006a59a  test    byte ptr [rcx+1Ch], 2
0x14006a59e  jz      short loc_14006A5C7
0x14006a5a0  cmp     byte ptr [rcx+19h], 2
0x14006a5a4  jb      short loc_14006A5C7
0x14006a5a6  mov     rcx, [rcx+10h]
0x14006a5aa  lea     rax, [rbp+3C0h+szFilePath]
0x14006a5ae  mov     edx, 51h ; 'Q'
0x14006a5b3  mov     [rsp+4C0h+var_4A0], rax
0x14006a5b8  mov     r9, rdi
0x14006a5bb  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006a5c2  call    WPP_SF_SS
0x14006a5c7  mov     ebx, 800700A1h
0x14006a5cc  jmp     short loc_14006A622
0x14006a5ce  lea     rdx, [rsp+4C0h+FileInformation]; lpFileInformation
0x14006a5d3  mov     rcx, r14; hFile
0x14006a5d6  call    cs:__imp_GetFileInformationByHandle
0x14006a5dc  test    eax, eax
0x14006a5de  jz      short loc_14006A5C7
0x14006a5e0  cmp     [rsp+4C0h+FileInformation.nNumberOfLinks], 1
0x14006a5e5  jbe     short loc_14006A620
0x14006a5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a5ee  lea     rax, WPP_GLOBAL_Control
0x14006a5f5  cmp     rcx, rax
0x14006a5f8  jz      short loc_14006A5C7
0x14006a5fa  test    byte ptr [rcx+1Ch], 2
0x14006a5fe  jz      short loc_14006A5C7
0x14006a600  cmp     byte ptr [rcx+19h], 2
0x14006a604  jb      short loc_14006A5C7
0x14006a606  mov     rcx, [rcx+10h]
0x14006a60a  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006a611  mov     edx, 52h ; 'R'
0x14006a616  mov     r9, rdi
0x14006a619  call    WPP_SF_S
0x14006a61e  jmp     short loc_14006A5C7
0x14006a620  xor     ebx, ebx
0x14006a622  test    sil, sil
0x14006a625  jz      short loc_14006A647
0x14006a627  test    rdi, rdi
0x14006a62a  jz      short loc_14006A647
0x14006a62c  mov     rcx, rdi; Block
0x14006a62f  call    cs:__imp_free
0x14006a635  jmp     short loc_14006A647
0x14006a637  call    cs:__imp_GetLastError
0x14006a63d  test    eax, eax
0x14006a63f  mov     ebx, 80070000h
0x14006a644  cmovle  ebx, eax
0x14006a647  not     ebx
0x14006a649  shr     ebx, 1Fh
0x14006a64c  mov     eax, ebx
0x14006a64e  mov     rcx, [rbp+3C0h+var_30]
0x14006a655  xor     rcx, rsp; StackCookie
0x14006a658  call    __security_check_cookie
0x14006a65d  mov     rbx, [rsp+4C0h+arg_10]
0x14006a665  add     rsp, 4A0h
0x14006a66c  pop     r15
0x14006a66e  pop     r14
0x14006a670  pop     rdi
0x14006a671  pop     rsi
0x14006a672  pop     rbp
0x14006a673  retn
```
