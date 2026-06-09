# TextFileLogger::GetFirstAvailableFile(ushort *,unsigned __int64,ushort *,TLogData *)

- ea: `0x180012fbc`
- end: `0x180013138`
- name: `?GetFirstAvailableFile@TextFileLogger@@AEAAJPEAG_K0PEAUTLogData@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(TextFileLogger *this, unsigned __int16 *, __int64, unsigned __int16 *, wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180012b68`

## callees

- `0x180012fbc`
- `0x180013c30`
- `0x18002e110`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001303b`
- `msvcrt!wcscpy_s` at `0x18001303b`
- `KERNEL32!GetFileAttributesExW` at `0x18001304b`
- `KERNEL32!GetFileAttributesExW` at `0x18001304b`
- `KERNEL32!GetLastError` at `0x18001306e`
- `KERNEL32!GetLastError` at `0x18001306e`
- `IisRTL!PuDbgPrint` at `0x1800130bf`
- `IisRTL!PuDbgPrint` at `0x18001310b`
- `IisRTL!PuDbgPrint` at `0x1800130bf`
- `IisRTL!PuDbgPrint` at `0x18001310b`

## string_xrefs

- `0x1800130b8`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`
- `0x180013104`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`

## pseudocode

```c
__int64 __fastcall TextFileLogger::GetFirstAvailableFile(
        TextFileLogger *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        wchar_t *a5)
{
  unsigned int i; // ebx
  unsigned __int64 v9; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  _OWORD FileInformation[2]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+50h] [rbp-28h]

  memset(FileInformation, 0, sizeof(FileInformation));
  v14 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i == -1 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
          779,
          "TextFileLogger::GetFirstAvailableFile",
          "Could not find an available file\n");
      return 2147942418LL;
    }
    TLogData::SetVersion((TLogData *)a5, i);
    v9 = a4 - a2;
    if ( v9 > 0x104 && v9 != 0 )
      return 2147942934LL;
    wcscpy_s(a4, 260 - v9, a5 + 22);
    if ( !GetFileAttributesExW(a2, GetFileExInfoStandard, FileInformation) )
      break;
    if ( v14 < (unsigned int)(*((_DWORD *)this + 2) / *((_DWORD *)this + 3)) )
    {
      *((_DWORD *)a5 + 8) = v14;
      return 0;
    }
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 == -2147024894 )
  {
    *((_DWORD *)a5 + 8) = 0;
    return 0;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
      765,
      "TextFileLogger::GetFirstAvailableFile",
      "Could not fetch attributes, hr=0x%x\n",
      v11);
  return v11;
}

```

## disassembly

```asm
0x180012fbc  mov     [rsp+arg_0], rbx
0x180012fc1  mov     [rsp+arg_10], rbp
0x180012fc6  push    rsi
0x180012fc7  push    rdi
0x180012fc8  push    r14
0x180012fca  sub     rsp, 60h
0x180012fce  mov     rax, cs:__security_cookie
0x180012fd5  xor     rax, rsp
0x180012fd8  mov     [rsp+78h+var_20], rax
0x180012fdd  mov     rdi, [rsp+78h+arg_20]
0x180012fe5  xorps   xmm0, xmm0
0x180012fe8  xor     eax, eax
0x180012fea  mov     r14, r9
0x180012fed  movups  [rsp+78h+FileInformation], xmm0
0x180012ff2  mov     [rsp+78h+var_28], eax
0x180012ff6  xor     ebx, ebx
0x180012ff8  movups  [rsp+78h+var_38], xmm0
0x180012ffd  mov     rbp, rdx
0x180013000  mov     rsi, rcx
0x180013003  cmp     ebx, 0FFFFFFFFh
0x180013006  jnb     loc_1800130DB
0x18001300c  mov     edx, ebx; unsigned int
0x18001300e  mov     rcx, rdi; this
0x180013011  call    ?SetVersion@TLogData@@QEAAXK@Z; TLogData::SetVersion(ulong)
0x180013016  mov     rax, r14
0x180013019  mov     edx, 104h
0x18001301e  sub     rax, rbp
0x180013021  sar     rax, 1
0x180013024  sub     rdx, rax; SizeInWords
0x180013027  cmp     rdx, 104h
0x18001302e  ja      loc_1800130D4
0x180013034  lea     r8, [rdi+2Ch]; Source
0x180013038  mov     rcx, r14; Destination
0x18001303b  call    cs:__imp_wcscpy_s
0x180013041  lea     r8, [rsp+78h+FileInformation]; lpFileInformation
0x180013046  xor     edx, edx; fInfoLevelId
0x180013048  mov     rcx, rbp; lpFileName
0x18001304b  call    cs:__imp_GetFileAttributesExW
0x180013051  test    eax, eax
0x180013053  jz      short loc_18001306E
0x180013055  mov     eax, [rsi+8]
0x180013058  xor     edx, edx
0x18001305a  div     dword ptr [rsi+0Ch]
0x18001305d  mov     ecx, [rsp+78h+var_28]
0x180013061  cmp     ecx, eax
0x180013063  jb      short loc_180013069
0x180013065  inc     ebx
0x180013067  jmp     short loc_180013003
0x180013069  mov     [rdi+20h], ecx
0x18001306c  jmp     short loc_1800130D0
0x18001306e  call    cs:__imp_GetLastError
0x180013074  mov     ebx, eax
0x180013076  test    eax, eax
0x180013078  jle     short loc_180013083
0x18001307a  movzx   ebx, ax
0x18001307d  or      ebx, 80070000h
0x180013083  cmp     ebx, 80070002h
0x180013089  jz      short loc_1800130C9
0x18001308b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180013092  jz      short loc_1800130C5
0x180013094  mov     rcx, cs:g_pDebug
0x18001309b  lea     rax, aCouldNotFetchA; "Could not fetch attributes, hr=0x%x\n"
0x1800130a2  mov     [rsp+78h+var_50], ebx
0x1800130a6  lea     r9, aTextfilelogger_5; "TextFileLogger::GetFirstAvailableFile"
0x1800130ad  mov     r8d, 2FDh
0x1800130b3  mov     [rsp+78h+var_58], rax
0x1800130b8  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x1800130bf  call    cs:__imp_PuDbgPrint
0x1800130c5  mov     eax, ebx
0x1800130c7  jmp     short loc_180013116
0x1800130c9  mov     dword ptr [rdi+20h], 0
0x1800130d0  xor     eax, eax
0x1800130d2  jmp     short loc_180013116
0x1800130d4  mov     eax, 80070216h
0x1800130d9  jmp     short loc_180013116
0x1800130db  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800130e2  jz      short loc_180013111
0x1800130e4  mov     rcx, cs:g_pDebug
0x1800130eb  lea     rax, aCouldNotFindAn; "Could not find an available file\n"
0x1800130f2  lea     r9, aTextfilelogger_5; "TextFileLogger::GetFirstAvailableFile"
0x1800130f9  mov     [rsp+78h+var_58], rax
0x1800130fe  mov     r8d, 30Bh
0x180013104  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x18001310b  call    cs:__imp_PuDbgPrint
0x180013111  mov     eax, 80070012h
0x180013116  mov     rcx, [rsp+78h+var_20]
0x18001311b  xor     rcx, rsp; StackCookie
0x18001311e  call    __security_check_cookie
0x180013123  lea     r11, [rsp+78h+var_18]
0x180013128  mov     rbx, [r11+20h]
0x18001312c  mov     rbp, [r11+30h]
0x180013130  mov     rsp, r11
0x180013133  pop     r14
0x180013135  pop     rdi
0x180013136  pop     rsi
0x180013137  retn
```
