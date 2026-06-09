# _DebugMsg(uint,ushort const *,...)

- ea: `0x1800898a0`
- end: `0x180089c00`
- name: `?_DebugMsg@@YAXIPEBGZZ`
- size: `864`
- prototype: `void(unsigned int, const unsigned __int16 *, ...)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x180003770`
- `0x180049a90`
- `0x18007d320`
- `0x1800898a0`
- `0x180089c08`
- `0x180089ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089bda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800898e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800898e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008999c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180089a0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008999c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180089a0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089a06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089a06`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180089a61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180089a8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180089a99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180089a61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180089a8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180089a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089bbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089937`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089ac1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089937`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180089ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180089bc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180089bd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180089bc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180089bd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18008994d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18008994d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180089b74`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180089b98`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180089bb5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180089b74`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180089b98`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180089bb5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180089b41`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180089b41`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180089b1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180089b1e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180089ae3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180089ae3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void _DebugMsg(unsigned int a1, const unsigned __int16 *a2, ...)
{
  int v3; // r12d
  int v4; // r14d
  wchar_t *v5; // rsi
  const wchar_t *v6; // r15
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  size_t *v9; // r8
  DWORD v10; // ebx
  DWORD v11; // eax
  WCHAR *v12; // rax
  WCHAR *v13; // r14
  HANDLE FileW; // rax
  __int64 v15; // rbx
  void *v16; // rdi
  __int64 v17; // r8
  DWORD NumberOfBytesWritten[2]; // [rsp+78h] [rbp-90h] BYREF
  DWORD LastError; // [rsp+80h] [rbp-88h]
  int v20; // [rsp+84h] [rbp-84h]
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-80h] BYREF
  WCHAR OutputString[64]; // [rsp+98h] [rbp-70h] BYREF
  __int64 argList; // [rsp+188h] [rbp+80h] BYREF
  va_list va; // [rsp+188h] [rbp+80h]
  va_list va1; // [rsp+190h] [rbp+88h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  argList = va_arg(va1, _QWORD);
  v20 = 0;
  SystemTime = 0;
  LastError = GetLastError();
  if ( !*(_WORD *)&g_dwDebugLevel )
  {
LABEL_4:
    if ( a1 != 1 )
      goto LABEL_5;
    goto LABEL_6;
  }
  if ( *(unsigned __int16 *)&g_dwDebugLevel != 1 )
  {
    if ( *(unsigned __int16 *)&g_dwDebugLevel == 2 )
      goto LABEL_6;
    goto LABEL_4;
  }
  if ( a1 == 4 )
  {
LABEL_5:
    if ( (*(_DWORD *)&g_dwDebugLevel & 0x100000) == 0 )
      goto LABEL_33;
  }
LABEL_6:
  v3 = *(_DWORD *)&g_dwDebugLevel & 0x20000;
  v4 = *(_DWORD *)&g_dwDebugLevel & 0x10000;
  v5 = (wchar_t *)LocalAlloc(0x40u, 0x1000u);
  if ( v5 )
  {
    GetLocalTime(&SystemTime);
    if ( g_DebugCallerId == 1 )
    {
      v6 = L"GPMC";
    }
    else
    {
      v6 = L"GPPSCmdlet";
      if ( g_DebugCallerId != 2 )
        v6 = L"GPSVC";
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::GetImpl'::`2'::impl) )
    {
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      StringCchPrintfW(
        OutputString,
        0x3Cu,
        L"%s(%x.%x) %04d-%02d-%02d %02d:%02d:%02d:%03d ",
        v6,
        CurrentProcessId,
        CurrentThreadId,
        SystemTime.wYear,
        SystemTime.wMonth,
        SystemTime.wDay,
        SystemTime.wHour,
        SystemTime.wMinute,
        SystemTime.wSecond,
        SystemTime.wMilliseconds);
    }
    else
    {
      v10 = GetCurrentThreadId();
      v11 = GetCurrentProcessId();
      StringCchPrintfW(
        OutputString,
        0x3Cu,
        L"%s(%x.%x) %02d:%02d:%02d:%03d ",
        v6,
        v11,
        v10,
        SystemTime.wHour,
        SystemTime.wMinute,
        SystemTime.wSecond,
        SystemTime.wMilliseconds);
    }
    if ( v3 )
      OutputDebugStringW(OutputString);
    StringVPrintfWorkerW(v5, 0x800u, v9, a2, va);
    if ( v3 )
    {
      OutputDebugStringW(v5);
      OutputDebugStringW(L"\r\n");
    }
    GP_TRACELOGGING(a1, v5);
    if ( v4 )
    {
      NumberOfBytesWritten[0] = 0;
      v12 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
      v13 = v12;
      if ( v12 )
      {
        if ( ExpandEnvironmentStringsW(&g_szLogFileName, v12, 0x104u) - 1 <= 0x103 )
        {
          FileW = CreateFileW(v13, 6u, 1u, 0, 4u, 0x80u, 0);
          v15 = -1;
          v16 = FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            if ( SetFilePointer(FileW, 0, 0, 2u) != -1 )
            {
              v17 = -1;
              do
                ++v17;
              while ( OutputString[v17] );
              WriteFile(v16, OutputString, 2 * v17, NumberOfBytesWritten, 0);
              do
                ++v15;
              while ( v5[v15] );
              WriteFile(v16, v5, 2 * v15, NumberOfBytesWritten, 0);
              WriteFile(v16, L"\r\n", 4u, NumberOfBytesWritten, 0);
            }
            CloseHandle(v16);
          }
        }
        LocalFree(v13);
      }
    }
    LocalFree(v5);
  }
LABEL_33:
  SetLastError(LastError);
}

```

## disassembly

```asm
0x1800898a0  mov     rax, rsp
0x1800898a3  mov     [rax+10h], rdx
0x1800898a7  mov     [rax+18h], r8
0x1800898ab  mov     [rax+20h], r9
0x1800898af  push    rbp
0x1800898b0  push    rbx
0x1800898b1  push    rsi
0x1800898b2  push    rdi
0x1800898b3  push    r12
0x1800898b5  push    r13
0x1800898b7  push    r14
0x1800898b9  push    r15
0x1800898bb  lea     rbp, [rax-68h]
0x1800898bf  sub     rsp, 128h
0x1800898c6  mov     rax, cs:__security_cookie
0x1800898cd  xor     rax, rsp
0x1800898d0  mov     [rbp+60h+var_50], rax
0x1800898d4  xorps   xmm0, xmm0
0x1800898d7  xor     edi, edi
0x1800898d9  mov     qword ptr [rsp+160h+var_E8], rdi
0x1800898de  mov     r13d, ecx
0x1800898e1  movups  xmmword ptr [rbp+60h+SystemTime.wYear], xmm0
0x1800898e5  call    cs:__imp_GetLastError
0x1800898eb  mov     r14d, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x1800898f2  movzx   r8d, r14w
0x1800898f6  mov     [rsp+160h+var_E8], eax
0x1800898fa  test    r8d, r8d
0x1800898fd  jz      short loc_18008990B
0x1800898ff  sub     r8d, 1
0x180089903  jz      short loc_180089967
0x180089905  cmp     r8d, 1
0x180089909  jz      short loc_18008991C
0x18008990b  cmp     r13d, 1
0x18008990f  jz      short loc_18008991C
0x180089911  bt      r14d, 14h
0x180089916  jnb     loc_180089BD6
0x18008991c  mov     r12d, r14d
0x18008991f  mov     edx, 1000h; uBytes
0x180089924  mov     ecx, 40h ; '@'; uFlags
0x180089929  and     r12d, 20000h
0x180089930  and     r14d, 10000h
0x180089937  call    cs:__imp_LocalAlloc
0x18008993d  mov     rsi, rax
0x180089940  test    rax, rax
0x180089943  jz      loc_180089BD6
0x180089949  lea     rcx, [rbp+60h+SystemTime]; lpSystemTime
0x18008994d  call    cs:__imp_GetLocalTime
0x180089953  mov     eax, cs:?g_DebugCallerId@@3W4_DebugLoggerInvoker@@A; _DebugLoggerInvoker g_DebugCallerId
0x180089959  cmp     eax, 1
0x18008995c  jnz     short loc_18008996F
0x18008995e  lea     r15, aGpmc; "GPMC"
0x180089965  jmp     short loc_180089984
0x180089967  cmp     r13d, 4
0x18008996b  jnz     short loc_18008991C
0x18008996d  jmp     short loc_180089911
0x18008996f  cmp     eax, 2
0x180089972  lea     r15, aGppscmdlet; "GPPSCmdlet"
0x180089979  lea     rcx, aGpsvc_1; "GPSVC"
0x180089980  cmovnz  r15, rcx
0x180089984  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::GetImpl(void)'::`2'::impl
0x18008998b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::__private_IsEnabled(void)
0x180089990  test    al, al
0x180089992  jz      short loc_180089A06
0x180089994  call    cs:__imp_GetCurrentThreadId
0x18008999a  mov     edi, eax
0x18008999c  call    cs:__imp_GetCurrentProcessId
0x1800899a2  movzx   ecx, [rbp+60h+SystemTime.wMilliseconds]
0x1800899a6  movzx   edx, [rbp+60h+SystemTime.wSecond]
0x1800899aa  movzx   r8d, [rbp+60h+SystemTime.wMinute]
0x1800899af  movzx   r9d, [rbp+60h+SystemTime.wHour]
0x1800899b4  movzx   r10d, [rbp+60h+SystemTime.wDay]
0x1800899b9  movzx   r11d, [rbp+60h+SystemTime.wMonth]
0x1800899be  movzx   ebx, [rbp+60h+SystemTime.wYear]
0x1800899c2  mov     [rsp+60h], ecx
0x1800899c6  lea     rcx, [rbp+60h+OutputString]; unsigned __int16 *
0x1800899ca  mov     [rsp+160h+var_108], edx
0x1800899ce  mov     edx, 3Ch ; '<'; unsigned __int64
0x1800899d3  mov     [rsp+160h+var_110], r8d
0x1800899d8  lea     r8, aSXX04d02d02d02; "%s(%x.%x) %04d-%02d-%02d %02d:%02d:%02d"...
0x1800899df  mov     [rsp+160h+var_118], r9d
0x1800899e4  mov     r9, r15
0x1800899e7  mov     [rsp+160h+var_120], r10d
0x1800899ec  mov     [rsp+160h+var_128], r11d
0x1800899f1  mov     dword ptr [rsp+160h+hTemplateFile], ebx
0x1800899f5  mov     [rsp+160h+dwFlagsAndAttributes], edi
0x1800899f9  mov     dword ptr [rsp+160h+argList], eax
0x1800899fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180089a02  xor     edi, edi
0x180089a04  jmp     short loc_180089A58
0x180089a06  call    cs:__imp_GetCurrentThreadId
0x180089a0c  mov     ebx, eax
0x180089a0e  call    cs:__imp_GetCurrentProcessId
0x180089a14  movzx   ecx, [rbp+60h+SystemTime.wMilliseconds]
0x180089a18  movzx   edx, [rbp+60h+SystemTime.wSecond]
0x180089a1c  movzx   r8d, [rbp+60h+SystemTime.wMinute]
0x180089a21  movzx   r9d, [rbp+60h+SystemTime.wHour]
0x180089a26  mov     [rsp+160h+var_118], ecx
0x180089a2a  lea     rcx, [rbp+60h+OutputString]; unsigned __int16 *
0x180089a2e  mov     [rsp+160h+var_120], edx
0x180089a32  mov     edx, 3Ch ; '<'; unsigned __int64
0x180089a37  mov     [rsp+160h+var_128], r8d
0x180089a3c  lea     r8, aSXX02d02d02d03; "%s(%x.%x) %02d:%02d:%02d:%03d "
0x180089a43  mov     dword ptr [rsp+160h+hTemplateFile], r9d
0x180089a48  mov     r9, r15
0x180089a4b  mov     [rsp+160h+dwFlagsAndAttributes], ebx
0x180089a4f  mov     dword ptr [rsp+160h+argList], eax
0x180089a53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180089a58  test    r12d, r12d
0x180089a5b  jz      short loc_180089A67
0x180089a5d  lea     rcx, [rbp+60h+OutputString]; lpOutputString
0x180089a61  call    cs:__imp_OutputDebugStringW
0x180089a67  mov     r9, [rbp+60h+pszFormat]; pszFormat
0x180089a6b  lea     rax, [rbp+60h+arg_10]
0x180089a72  mov     edx, 800h; cchDest
0x180089a77  mov     [rsp+160h+argList], rax; argList
0x180089a7c  mov     rcx, rsi; pszDest
0x180089a7f  call    StringVPrintfWorkerW
0x180089a84  test    r12d, r12d
0x180089a87  jz      short loc_180089A9F
0x180089a89  mov     rcx, rsi; lpOutputString
0x180089a8c  call    cs:__imp_OutputDebugStringW
0x180089a92  lea     rcx, Buffer; "\r\n"
0x180089a99  call    cs:__imp_OutputDebugStringW
0x180089a9f  mov     rdx, rsi; unsigned __int16 *
0x180089aa2  mov     ecx, r13d; unsigned int
0x180089aa5  call    ?GP_TRACELOGGING@@YAXIPEBG@Z; GP_TRACELOGGING(uint,ushort const *)
0x180089aaa  test    r14d, r14d
0x180089aad  jz      loc_180089BCD
0x180089ab3  mov     edx, 208h; uBytes
0x180089ab8  mov     [rsp+160h+NumberOfBytesWritten], edi
0x180089abc  mov     ecx, 40h ; '@'; uFlags
0x180089ac1  call    cs:__imp_LocalAlloc
0x180089ac7  mov     r14, rax
0x180089aca  test    rax, rax
0x180089acd  jz      loc_180089BCD
0x180089ad3  mov     r8d, 104h; nSize
0x180089ad9  lea     rcx, ?g_szLogFileName@@3PAGA; lpSrc
0x180089ae0  mov     rdx, rax; lpDst
0x180089ae3  call    cs:__imp_ExpandEnvironmentStringsW
0x180089ae9  dec     eax
0x180089aeb  cmp     eax, 103h
0x180089af0  ja      loc_180089BC4
0x180089af6  mov     r12d, 4
0x180089afc  mov     [rsp+160h+hTemplateFile], rdi; hTemplateFile
0x180089b01  mov     [rsp+160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180089b09  xor     r9d, r9d; lpSecurityAttributes
0x180089b0c  mov     rcx, r14; lpFileName
0x180089b0f  mov     dword ptr [rsp+160h+argList], r12d; dwCreationDisposition
0x180089b14  lea     edx, [r12+2]; dwDesiredAccess
0x180089b19  lea     r8d, [r12-3]; dwShareMode
0x180089b1e  call    cs:__imp_CreateFileW
0x180089b24  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180089b28  mov     rdi, rax
0x180089b2b  cmp     rax, rbx
0x180089b2e  jz      loc_180089BC4
0x180089b34  lea     r9d, [r12-2]; dwMoveMethod
0x180089b39  xor     r8d, r8d; lpDistanceToMoveHigh
0x180089b3c  xor     edx, edx; lDistanceToMove
0x180089b3e  mov     rcx, rax; hFile
0x180089b41  call    cs:__imp_SetFilePointer
0x180089b47  cmp     eax, 0FFFFFFFFh
0x180089b4a  jz      short loc_180089BBB
0x180089b4c  lea     rax, [rbp+60h+OutputString]
0x180089b50  mov     r8, rbx
0x180089b53  xor     r15d, r15d
0x180089b56  inc     r8
0x180089b59  cmp     [rax+r8*2], r15w
0x180089b5e  jnz     short loc_180089B56
0x180089b60  add     r8d, r8d; nNumberOfBytesToWrite
0x180089b63  mov     [rsp+160h+argList], r15; lpOverlapped
0x180089b68  lea     r9, [rsp+160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180089b6d  mov     rcx, rdi; hFile
0x180089b70  lea     rdx, [rbp+60h+OutputString]; lpBuffer
0x180089b74  call    cs:__imp_WriteFile
0x180089b7a  inc     rbx
0x180089b7d  cmp     [rsi+rbx*2], r15w
0x180089b82  jnz     short loc_180089B7A
0x180089b84  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x180089b88  mov     [rsp+160h+argList], r15; lpOverlapped
0x180089b8d  lea     r9, [rsp+160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180089b92  mov     rdx, rsi; lpBuffer
0x180089b95  mov     rcx, rdi; hFile
0x180089b98  call    cs:__imp_WriteFile
0x180089b9e  lea     r9, [rsp+160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180089ba3  mov     [rsp+160h+argList], r15; lpOverlapped
0x180089ba8  mov     r8d, r12d; nNumberOfBytesToWrite
0x180089bab  lea     rdx, Buffer; "\r\n"
0x180089bb2  mov     rcx, rdi; hFile
0x180089bb5  call    cs:__imp_WriteFile
0x180089bbb  mov     rcx, rdi; hObject
0x180089bbe  call    cs:__imp_CloseHandle
0x180089bc4  mov     rcx, r14; hMem
0x180089bc7  call    cs:__imp_LocalFree
0x180089bcd  mov     rcx, rsi; hMem
0x180089bd0  call    cs:__imp_LocalFree
0x180089bd6  mov     ecx, [rsp+160h+var_E8]; dwErrCode
0x180089bda  call    cs:__imp_SetLastError
0x180089be0  mov     rcx, [rbp+60h+var_50]
0x180089be4  xor     rcx, rsp; StackCookie
0x180089be7  call    __security_check_cookie
0x180089bec  add     rsp, 128h
0x180089bf3  pop     r15
0x180089bf5  pop     r14
0x180089bf7  pop     r13
0x180089bf9  pop     r12
0x180089bfb  pop     rdi
0x180089bfc  pop     rsi
0x180089bfd  pop     rbx
0x180089bfe  pop     rbp
0x180089bff  retn
```
