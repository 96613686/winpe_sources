# GetSystemVolumeFreeSpace

- ea: `0x18010678c`
- end: `0x180106a03`
- name: `GetSystemVolumeFreeSpace`
- size: `631`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180138638`
- `0x18013bb30`
- `0x1801cf630`

## callees

- `0x180013250`
- `0x180033d50`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x18010678c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801067dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801068a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801067dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801068a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106966`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1801067cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180106892`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1801067cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180106892`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180106956`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180106956`

## string_xrefs

- `0x1801067fc`: `Failed to get windows directory.`
- `0x1801068c5`: `Failed to get windows directory.`

## pseudocode

```c
__int64 __fastcall GetSystemVolumeFreeSpace(__int64 a1, union _ULARGE_INTEGER *a2, union _ULARGE_INTEGER *a3)
{
  UINT SystemWindowsDirectoryW; // eax
  UINT v6; // ebx
  signed int LastError; // ebx
  int v8; // edx
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // ebx
  UINT v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  __int64 v17; // r9
  int v18; // edx
  unsigned int v19; // eax
  unsigned int v21; // [rsp+20h] [rbp-30h]
  unsigned int v22; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v23[2]; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  lpBuffer[0] = 0;
  if ( a2 )
    a2->QuadPart = 0;
  if ( a3 )
    a3->QuadPart = 0;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v6 = SystemWindowsDirectoryW;
  if ( !SystemWindowsDirectoryW )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v22 = v9;
      LOBYTE(v8) = 1;
      *(_QWORD *)v23 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {0}",
        (__int64)v23);
    }
    if ( LastError )
    {
      v10 = 1321;
LABEL_23:
      v17 = (unsigned int)LastError;
LABEL_24:
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v10,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)v17,
              v21);
      goto LABEL_36;
    }
    goto LABEL_35;
  }
  v11 = SczAlloc(lpBuffer, SystemWindowsDirectoryW);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v14 = GetSystemWindowsDirectoryW(lpBuffer[0], v6);
    if ( v14 )
    {
      if ( v14 >= v6 )
      {
        v17 = 122;
        v10 = 1330;
        goto LABEL_24;
      }
      if ( !GetDiskFreeSpaceExW(lpBuffer[0], 0, a2, a3) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get disk space information");
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
          else
            v19 = LastError;
          v22 = v19;
          LOBYTE(v18) = 1;
          *(_QWORD *)v23 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v18,
            3,
            (unsigned int)": {0}",
            (__int64)v23);
        }
        if ( LastError )
        {
          v10 = 1335;
          goto LABEL_23;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        else
          v16 = LastError;
        v22 = v16;
        LOBYTE(v15) = 1;
        *(_QWORD *)v23 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {0}",
          (__int64)v23);
      }
      if ( LastError )
      {
        v10 = 1326;
        goto LABEL_23;
      }
    }
LABEL_35:
    v13 = 0;
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52A,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)(unsigned int)v11,
    v21);
  v13 = v12;
LABEL_36:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpBuffer);
  return v13;
}

```

## disassembly

```asm
0x18010678c  mov     [rsp-18h+arg_0], rbx
0x180106791  mov     [rsp-18h+arg_18], rsi
0x180106796  push    rbp
0x180106797  push    rdi
0x180106798  push    r14
0x18010679a  mov     rbp, rsp
0x18010679d  sub     rsp, 50h
0x1801067a1  mov     [rbp+lpBuffer], 0
0x1801067a9  mov     rsi, r8
0x1801067ac  mov     r14, rdx
0x1801067af  test    rdx, rdx
0x1801067b2  jz      short loc_1801067BB
0x1801067b4  mov     qword ptr [rdx], 0
0x1801067bb  test    rsi, rsi
0x1801067be  jz      short loc_1801067C7
0x1801067c0  mov     qword ptr [r8], 0
0x1801067c7  xor     edx, edx; uSize
0x1801067c9  xor     ecx, ecx; lpBuffer
0x1801067cb  call    cs:__imp_GetSystemWindowsDirectoryW
0x1801067d2  nop     dword ptr [rax+rax+00h]
0x1801067d7  mov     ebx, eax
0x1801067d9  test    eax, eax
0x1801067db  jnz     short loc_18010685B
0x1801067dd  call    cs:__imp_GetLastError
0x1801067e4  nop     dword ptr [rax+rax+00h]
0x1801067e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801067f0  mov     ebx, eax
0x1801067f2  test    rcx, rcx
0x1801067f5  jz      short loc_180106849
0x1801067f7  mov     edi, 3
0x1801067fc  lea     r9, aFailedToGetWin_4; "Failed to get windows directory."
0x180106803  mov     r8d, edi
0x180106806  xor     edx, edx
0x180106808  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010680d  test    ebx, ebx
0x18010680f  jg      short loc_180106815
0x180106811  mov     eax, ebx
0x180106813  jmp     short loc_18010681D
0x180106815  movzx   eax, bx
0x180106818  or      eax, 80070000h
0x18010681d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180106824  lea     r9, a0; ": {0}"
0x18010682b  mov     [rbp+var_20], eax
0x18010682e  mov     r8d, edi
0x180106831  lea     rax, [rbp+var_20]
0x180106835  mov     dl, 1
0x180106837  mov     qword ptr [rbp+var_18], rax
0x18010683b  lea     rax, [rbp+var_18]
0x18010683f  mov     qword ptr [rsp+50h+var_30], rax
0x180106844  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180106849  test    ebx, ebx
0x18010684b  jz      loc_1801069E0
0x180106851  mov     edx, 529h
0x180106856  jmp     loc_18010691F
0x18010685b  mov     rdx, rbx
0x18010685e  lea     rcx, [rbp+lpBuffer]
0x180106862  call    SczAlloc
0x180106867  mov     edi, eax
0x180106869  test    eax, eax
0x18010686b  jns     short loc_18010688C
0x18010686d  mov     rcx, [rbp+18h]; this
0x180106871  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180106878  mov     r9d, eax; char *
0x18010687b  mov     edx, 52Ah; void *
0x180106880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106885  mov     ebx, edi
0x180106887  jmp     loc_1801069E2
0x18010688c  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x180106890  mov     edx, ebx; uSize
0x180106892  call    cs:__imp_GetSystemWindowsDirectoryW
0x180106899  nop     dword ptr [rax+rax+00h]
0x18010689e  test    eax, eax
0x1801068a0  jnz     loc_180106939
0x1801068a6  call    cs:__imp_GetLastError
0x1801068ad  nop     dword ptr [rax+rax+00h]
0x1801068b2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801068b9  mov     ebx, eax
0x1801068bb  test    rcx, rcx
0x1801068be  jz      short loc_180106912
0x1801068c0  mov     edi, 3
0x1801068c5  lea     r9, aFailedToGetWin_4; "Failed to get windows directory."
0x1801068cc  mov     r8d, edi
0x1801068cf  xor     edx, edx
0x1801068d1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801068d6  test    ebx, ebx
0x1801068d8  jg      short loc_1801068DE
0x1801068da  mov     eax, ebx
0x1801068dc  jmp     short loc_1801068E6
0x1801068de  movzx   eax, bx
0x1801068e1  or      eax, 80070000h
0x1801068e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801068ed  lea     r9, a0; ": {0}"
0x1801068f4  mov     [rbp+var_20], eax
0x1801068f7  mov     r8d, edi
0x1801068fa  lea     rax, [rbp+var_20]
0x1801068fe  mov     dl, 1
0x180106900  mov     qword ptr [rbp+var_18], rax
0x180106904  lea     rax, [rbp+var_18]
0x180106908  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x18010690d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180106912  test    ebx, ebx
0x180106914  jz      loc_1801069E0
0x18010691a  mov     edx, 52Eh; void *
0x18010691f  mov     r9d, ebx; char *
0x180106922  mov     rcx, [rbp+18h]; this
0x180106926  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18010692d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180106932  mov     ebx, eax
0x180106934  jmp     loc_1801069E2
0x180106939  cmp     eax, ebx
0x18010693b  jb      short loc_18010694A
0x18010693d  mov     r9d, 7Ah ; 'z'
0x180106943  mov     edx, 532h
0x180106948  jmp     short loc_180106922
0x18010694a  mov     rcx, [rbp+lpBuffer]; lpDirectoryName
0x18010694e  mov     r9, rsi; lpTotalNumberOfFreeBytes
0x180106951  mov     r8, r14; lpTotalNumberOfBytes
0x180106954  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180106956  call    cs:__imp_GetDiskFreeSpaceExW
0x18010695d  nop     dword ptr [rax+rax+00h]
0x180106962  test    eax, eax
0x180106964  jnz     short loc_1801069E0
0x180106966  call    cs:__imp_GetLastError
0x18010696d  nop     dword ptr [rax+rax+00h]
0x180106972  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180106979  mov     ebx, eax
0x18010697b  test    rcx, rcx
0x18010697e  jz      short loc_1801069D2
0x180106980  mov     edi, 3
0x180106985  lea     r9, aFailedToGetDis_1; "Failed to get disk space information"
0x18010698c  mov     r8d, edi
0x18010698f  xor     edx, edx
0x180106991  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180106996  test    ebx, ebx
0x180106998  jg      short loc_18010699E
0x18010699a  mov     eax, ebx
0x18010699c  jmp     short loc_1801069A6
0x18010699e  movzx   eax, bx
0x1801069a1  or      eax, 80070000h
0x1801069a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801069ad  lea     r9, a0; ": {0}"
0x1801069b4  mov     [rbp+var_20], eax
0x1801069b7  mov     r8d, edi
0x1801069ba  lea     rax, [rbp+var_20]
0x1801069be  mov     dl, 1
0x1801069c0  mov     qword ptr [rbp+var_18], rax
0x1801069c4  lea     rax, [rbp+var_18]
0x1801069c8  mov     qword ptr [rsp+50h+var_30], rax
0x1801069cd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801069d2  test    ebx, ebx
0x1801069d4  jz      short loc_1801069E0
0x1801069d6  mov     edx, 537h
0x1801069db  jmp     loc_18010691F
0x1801069e0  xor     ebx, ebx
0x1801069e2  lea     rcx, [rbp+lpBuffer]
0x1801069e6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801069eb  lea     r11, [rsp+50h+var_s0]
0x1801069f0  mov     eax, ebx
0x1801069f2  mov     rbx, [r11+20h]
0x1801069f6  mov     rsi, [r11+38h]
0x1801069fa  mov     rsp, r11
0x1801069fd  pop     r14
0x1801069ff  pop     rdi
0x180106a00  pop     rbp
0x180106a01  retn
```
