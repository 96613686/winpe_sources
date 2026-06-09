# CDebug::Msg(ulong,ushort const *,char *)

- ea: `0x1800b7ed8`
- end: `0x1800b82ba`
- name: `?Msg@CDebug@@AEAAXKPEBGPEAD@Z`
- size: `994`
- prototype: `void __fastcall(CDebug *__hidden this, unsigned int, const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x180072a08`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18000a52c`
- `0x180049a90`
- `0x180072f8c`
- `0x18007d320`
- `0x180089c08`
- `0x1800b7ed8`
- `0x1800b8510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8192`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b826e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b827c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b828a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8192`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b826e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b827c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b828a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b7fe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b8005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b7fe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b8005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7fd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7ff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7fd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7ff5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b80ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b8080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b8080`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800b7fba`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800b7fba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b81ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b8210`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b8234`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b8251`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b81ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b8210`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b8234`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b8251`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800b81b5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800b81b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b8172`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b8172`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b8135`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b8135`

## pseudocode

```c
void __fastcall CDebug::Msg(CDebug *this, __int16 a2, const unsigned __int16 *a3, va_list a4)
{
  DWORD LastError; // eax
  int v7; // edi
  int v8; // r14d
  bool v9; // zf
  const WCHAR *v10; // rsi
  DWORD CurrentThreadId; // r12d
  const unsigned __int16 *v12; // rbx
  DWORD CurrentProcessId; // eax
  int wYear; // ecx
  int wMonth; // edx
  int wDay; // r8d
  DWORD v17; // r15d
  size_t *v18; // r8
  wchar_t *v19; // rbx
  va_list FileW; // rax
  __int64 v21; // rdi
  va_list v22; // r14
  __int64 v23; // r8
  __int64 v24; // r8
  DWORD dwErrCode; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v26; // [rsp+68h] [rbp-98h] BYREF
  va_list argList; // [rsp+70h] [rbp-90h] BYREF
  STRSAFE_LPCWSTR pszFormat; // [rsp+78h] [rbp-88h] BYREF
  char v29; // [rsp+84h] [rbp-7Ch]
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  WCHAR OutputString[128]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Dst[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  argList = a4;
  pszFormat = a3;
  LastError = GetLastError();
  v9 = *((_BYTE *)this + 64) == 0;
  dwErrCode = LastError;
  if ( v9 )
    return;
  v7 = *((_DWORD *)this + 17) & 0x10000;
  v8 = *((_DWORD *)this + 17) & 0x20000;
  if ( !v8 && !v7 || !*((_WORD *)this + 34) )
    goto LABEL_42;
  if ( *((_WORD *)this + 34) != 1 )
  {
    if ( *((_WORD *)this + 34) == 2 )
    {
      v9 = (a2 & 7) == 0;
      goto LABEL_9;
    }
LABEL_42:
    SetLastError(LastError);
    return;
  }
  v9 = (a2 & 3) == 0;
LABEL_9:
  if ( v9 )
    goto LABEL_42;
  if ( a2 == 1 )
  {
    v10 = L" [ASSERT] ";
  }
  else if ( a2 == 2 )
  {
    v10 = L" [WARNING] ";
  }
  else
  {
    v10 = L" [VERBOSE] ";
    if ( a2 != 4 )
      v10 = L" [<Unknown message type>] ";
  }
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::GetImpl'::`2'::impl) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = L"[%x.%x] %04d-%02d-%02d %02d:%02d:%02d:%03d ";
    CurrentProcessId = GetCurrentProcessId();
    wYear = SystemTime.wYear;
    wMonth = SystemTime.wMonth;
    wDay = SystemTime.wDay;
  }
  else
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = L"[%x.%x] %2d/%02d/%4d %02d:%02d:%02d:%03d ";
    CurrentProcessId = GetCurrentProcessId();
    wYear = SystemTime.wMonth;
    wMonth = SystemTime.wDay;
    wDay = SystemTime.wYear;
  }
  v17 = dwErrCode;
  if ( (int)StringCchPrintfW(
              OutputString,
              0x80u,
              v12,
              CurrentProcessId,
              CurrentThreadId,
              wYear,
              wMonth,
              wDay,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              SystemTime.wMilliseconds) >= 0 )
  {
    v26 = (wchar_t *)LocalAlloc(0x40u, 0x1000u);
    v19 = v26;
    if ( v26 )
    {
      if ( StringVPrintfWorkerW(v26, 0x800u, v18, pszFormat, argList) < 0 )
      {
LABEL_22:
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v26);
        return;
      }
      if ( v8 )
      {
        OutputDebugStringW(OutputString);
        OutputDebugStringW(v10);
        OutputDebugStringW(v26);
        OutputDebugStringW(L"\r\n");
      }
      if ( v7 )
      {
        operator+((CWString *)&pszFormat, L"%systemroot%\\debug\\usermode\\");
        if ( !v29 )
        {
LABEL_27:
          CWString::Reset((CWString *)&pszFormat);
          goto LABEL_22;
        }
        if ( ExpandEnvironmentStringsW(pszFormat, Dst, 0x105u) - 1 > 0x103 )
        {
          SetLastError(dwErrCode);
          goto LABEL_27;
        }
        FileW = (va_list)CreateFileW(Dst, 6u, 1u, 0, 4u, 0x80u, 0);
        v21 = -1;
        argList = FileW;
        v22 = FileW;
        if ( FileW == (va_list)-1LL )
        {
          GetLastError();
LABEL_31:
          SetLastError(dwErrCode);
          XHandle::~XHandle((void **)&argList);
          goto LABEL_27;
        }
        if ( SetFilePointer(FileW, 0, 0, 2u) == -1 )
          goto LABEL_31;
        dwErrCode = 0;
        v23 = -1;
        do
          ++v23;
        while ( OutputString[v23] );
        WriteFile(v22, OutputString, 2 * v23, &dwErrCode, 0);
        v24 = -1;
        do
          ++v24;
        while ( v10[v24] );
        WriteFile(v22, v10, 2 * v24, &dwErrCode, 0);
        do
          ++v21;
        while ( v19[v21] );
        WriteFile(v22, v19, 2 * v21, &dwErrCode, 0);
        WriteFile(v22, L"\r\n", 4u, &dwErrCode, 0);
        XHandle::~XHandle((void **)&argList);
        CWString::Reset((CWString *)&pszFormat);
      }
    }
    SetLastError(v17);
    goto LABEL_22;
  }
}

```

## disassembly

```asm
0x1800b7ed8  mov     [rsp-8+arg_8], rbx
0x1800b7edd  push    rbp
0x1800b7ede  push    rsi
0x1800b7edf  push    rdi
0x1800b7ee0  push    r12
0x1800b7ee2  push    r13
0x1800b7ee4  push    r14
0x1800b7ee6  push    r15
0x1800b7ee8  lea     rbp, [rsp-2C0h]
0x1800b7ef0  sub     rsp, 3C0h
0x1800b7ef7  mov     rax, cs:__security_cookie
0x1800b7efe  xor     rax, rsp
0x1800b7f01  mov     [rbp+2F0h+var_40], rax
0x1800b7f08  mov     [rsp+3F0h+var_380], r9
0x1800b7f0d  mov     ebx, edx
0x1800b7f0f  mov     [rsp+3F0h+pszFormat], r8
0x1800b7f14  mov     r13, rcx
0x1800b7f17  call    cs:__imp_GetLastError
0x1800b7f1d  cmp     byte ptr [r13+40h], 0
0x1800b7f22  mov     r15d, eax
0x1800b7f25  mov     [rsp+3F0h+dwErrCode], eax
0x1800b7f29  jz      loc_1800B8290
0x1800b7f2f  mov     r14d, [r13+44h]
0x1800b7f33  mov     edi, r14d
0x1800b7f36  and     edi, 10000h
0x1800b7f3c  and     r14d, 20000h
0x1800b7f43  jnz     short loc_1800B7F4D
0x1800b7f45  test    edi, edi
0x1800b7f47  jz      loc_1800B8287
0x1800b7f4d  movzx   eax, word ptr [r13+44h]
0x1800b7f52  test    eax, eax
0x1800b7f54  jz      loc_1800B8287
0x1800b7f5a  sub     eax, 1
0x1800b7f5d  jz      short loc_1800B7F6D
0x1800b7f5f  cmp     eax, 1
0x1800b7f62  jnz     loc_1800B8287
0x1800b7f68  test    bl, 7
0x1800b7f6b  jmp     short loc_1800B7F70
0x1800b7f6d  test    bl, 3
0x1800b7f70  setnz   al
0x1800b7f73  test    al, al
0x1800b7f75  jz      loc_1800B8287
0x1800b7f7b  movzx   eax, bx
0x1800b7f7e  cmp     eax, 1
0x1800b7f81  jnz     short loc_1800B7F8C
0x1800b7f83  lea     rsi, OutputString; " [ASSERT] "
0x1800b7f8a  jmp     short loc_1800B7FAF
0x1800b7f8c  cmp     eax, 2
0x1800b7f8f  jnz     short loc_1800B7F9A
0x1800b7f91  lea     rsi, aWarning; " [WARNING] "
0x1800b7f98  jmp     short loc_1800B7FAF
0x1800b7f9a  cmp     eax, 4
0x1800b7f9d  lea     rsi, aVerbose; " [VERBOSE] "
0x1800b7fa4  lea     rcx, aUnknownMessage; " [<Unknown message type>] "
0x1800b7fab  cmovnz  rsi, rcx
0x1800b7faf  xorps   xmm0, xmm0
0x1800b7fb2  lea     rcx, [rbp+2F0h+SystemTime]; lpSystemTime
0x1800b7fb6  movups  xmmword ptr [rbp+2F0h+SystemTime.wYear], xmm0
0x1800b7fba  call    cs:__imp_GetLocalTime
0x1800b7fc0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::GetImpl(void)'::`2'::impl
0x1800b7fc7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddFullTimestampsToGPOLogs>::__private_IsEnabled(void)
0x1800b7fcc  test    al, al
0x1800b7fce  jz      short loc_1800B7FF5
0x1800b7fd0  call    cs:__imp_GetCurrentThreadId
0x1800b7fd6  mov     r12d, eax
0x1800b7fd9  lea     rbx, aXX04d02d02d02d; "[%x.%x] %04d-%02d-%02d %02d:%02d:%02d:%"...
0x1800b7fe0  call    cs:__imp_GetCurrentProcessId
0x1800b7fe6  movzx   ecx, [rbp+2F0h+SystemTime.wYear]
0x1800b7fea  movzx   edx, [rbp+2F0h+SystemTime.wMonth]
0x1800b7fee  movzx   r8d, [rbp+2F0h+SystemTime.wDay]
0x1800b7ff3  jmp     short loc_1800B8018
0x1800b7ff5  call    cs:__imp_GetCurrentThreadId
0x1800b7ffb  mov     r12d, eax
0x1800b7ffe  lea     rbx, aXX2d02d4d02d02; "[%x.%x] %2d/%02d/%4d %02d:%02d:%02d:%03"...
0x1800b8005  call    cs:__imp_GetCurrentProcessId
0x1800b800b  movzx   ecx, [rbp+2F0h+SystemTime.wMonth]
0x1800b800f  movzx   edx, [rbp+2F0h+SystemTime.wDay]
0x1800b8013  movzx   r8d, [rbp+2F0h+SystemTime.wYear]
0x1800b8018  movzx   r9d, [rbp+2F0h+SystemTime.wHour]
0x1800b801d  movzx   r15d, [rbp+2F0h+SystemTime.wMilliseconds]
0x1800b8022  movzx   r11d, [rbp+2F0h+SystemTime.wSecond]
0x1800b8027  movzx   r10d, [rbp+2F0h+SystemTime.wMinute]
0x1800b802c  mov     [rsp+3F0h+var_398], r15d
0x1800b8031  mov     [rsp+3F0h+var_3A0], r11d
0x1800b8036  mov     [rsp+3F0h+var_3A8], r10d
0x1800b803b  mov     [rsp+3F0h+var_3B0], r9d
0x1800b8040  mov     r9d, eax
0x1800b8043  mov     [rsp+3F0h+var_3B8], r8d
0x1800b8048  mov     r8, rbx; unsigned __int16 *
0x1800b804b  mov     dword ptr [rsp+3F0h+hTemplateFile], edx
0x1800b804f  mov     edx, 80h; unsigned __int64
0x1800b8054  mov     [rsp+3F0h+dwFlagsAndAttributes], ecx
0x1800b8058  lea     rcx, [rbp+2F0h+OutputString]; unsigned __int16 *
0x1800b805c  mov     dword ptr [rsp+3F0h+argList], r12d
0x1800b8061  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b8066  mov     r15d, [rsp+3F0h+dwErrCode]
0x1800b806b  xor     r12d, r12d
0x1800b806e  test    eax, eax
0x1800b8070  js      loc_1800B8290
0x1800b8076  mov     edx, 1000h; uBytes
0x1800b807b  lea     ecx, [r12+40h]; uFlags
0x1800b8080  call    cs:__imp_LocalAlloc
0x1800b8086  mov     [rsp+3F0h+var_388], rax
0x1800b808b  mov     rbx, rax
0x1800b808e  test    rax, rax
0x1800b8091  jz      loc_1800B826B
0x1800b8097  mov     rax, [rsp+3F0h+var_380]
0x1800b809c  mov     edx, 800h; cchDest
0x1800b80a1  mov     r9, [rsp+3F0h+pszFormat]; pszFormat
0x1800b80a6  mov     rcx, rbx; pszDest
0x1800b80a9  mov     [rsp+3F0h+argList], rax; argList
0x1800b80ae  call    StringVPrintfWorkerW
0x1800b80b3  test    eax, eax
0x1800b80b5  jns     short loc_1800B80C6
0x1800b80b7  lea     rcx, [rsp+3F0h+var_388]
0x1800b80bc  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b80c1  jmp     loc_1800B8290
0x1800b80c6  test    r14d, r14d
0x1800b80c9  jz      short loc_1800B80F4
0x1800b80cb  lea     rcx, [rbp+2F0h+OutputString]; lpOutputString
0x1800b80cf  call    cs:__imp_OutputDebugStringW
0x1800b80d5  mov     rcx, rsi; lpOutputString
0x1800b80d8  call    cs:__imp_OutputDebugStringW
0x1800b80de  mov     rcx, rbx; lpOutputString
0x1800b80e1  call    cs:__imp_OutputDebugStringW
0x1800b80e7  lea     rcx, asc_1801152C4; "\r\n"
0x1800b80ee  call    cs:__imp_OutputDebugStringW
0x1800b80f4  test    edi, edi
0x1800b80f6  jz      loc_1800B826B
0x1800b80fc  lea     r8, [r13+20h]
0x1800b8100  lea     rdx, aSystemrootDebu; "%systemroot%\\debug\\usermode\\"
0x1800b8107  lea     rcx, [rsp+3F0h+pszFormat]; this
0x1800b810c  call    ??H@YA?AVCWString@@PEBGAEBV0@@Z; operator+(ushort const *,CWString const &)
0x1800b8111  cmp     [rbp+2F0h+var_36C], r12b
0x1800b8115  jnz     short loc_1800B8123
0x1800b8117  lea     rcx, [rsp+3F0h+pszFormat]; this
0x1800b811c  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x1800b8121  jmp     short loc_1800B80B7
0x1800b8123  mov     rcx, [rsp+3F0h+pszFormat]; lpSrc
0x1800b8128  lea     rdx, [rbp+2F0h+Dst]; lpDst
0x1800b812f  mov     r8d, 105h; nSize
0x1800b8135  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b813b  dec     eax
0x1800b813d  cmp     eax, 103h
0x1800b8142  ja      loc_1800B8279
0x1800b8148  mov     r13d, 4
0x1800b814e  mov     [rsp+3F0h+hTemplateFile], r12; hTemplateFile
0x1800b8153  mov     [rsp+3F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b815b  lea     rcx, [rbp+2F0h+Dst]; lpFileName
0x1800b8162  xor     r9d, r9d; lpSecurityAttributes
0x1800b8165  mov     dword ptr [rsp+3F0h+argList], r13d; dwCreationDisposition
0x1800b816a  lea     edx, [r13+2]; dwDesiredAccess
0x1800b816e  lea     r8d, [r13-3]; dwShareMode
0x1800b8172  call    cs:__imp_CreateFileW
0x1800b8178  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b817c  mov     [rsp+3F0h+var_380], rax
0x1800b8181  mov     r14, rax
0x1800b8184  cmp     rax, rdi
0x1800b8187  jnz     short loc_1800B81A7
0x1800b8189  call    cs:__imp_GetLastError
0x1800b818f  mov     ecx, r15d; dwErrCode
0x1800b8192  call    cs:__imp_SetLastError
0x1800b8198  lea     rcx, [rsp+3F0h+var_380]; this
0x1800b819d  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800b81a2  jmp     loc_1800B8117
0x1800b81a7  mov     r9d, 2; dwMoveMethod
0x1800b81ad  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800b81b0  xor     edx, edx; lDistanceToMove
0x1800b81b2  mov     rcx, r14; hFile
0x1800b81b5  call    cs:__imp_SetFilePointer
0x1800b81bb  cmp     eax, 0FFFFFFFFh
0x1800b81be  jz      short loc_1800B818F
0x1800b81c0  mov     [rsp+3F0h+dwErrCode], r12d
0x1800b81c5  lea     rax, [rbp+2F0h+OutputString]
0x1800b81c9  mov     r8, rdi
0x1800b81cc  inc     r8
0x1800b81cf  cmp     [rax+r8*2], r12w
0x1800b81d4  jnz     short loc_1800B81CC
0x1800b81d6  add     r8d, r8d; nNumberOfBytesToWrite
0x1800b81d9  mov     [rsp+3F0h+argList], r12; lpOverlapped
0x1800b81de  lea     r9, [rsp+3F0h+dwErrCode]; lpNumberOfBytesWritten
0x1800b81e3  mov     rcx, r14; hFile
0x1800b81e6  lea     rdx, [rbp+2F0h+OutputString]; lpBuffer
0x1800b81ea  call    cs:__imp_WriteFile
0x1800b81f0  mov     r8, rdi
0x1800b81f3  inc     r8
0x1800b81f6  cmp     [rsi+r8*2], r12w
0x1800b81fb  jnz     short loc_1800B81F3
0x1800b81fd  add     r8d, r8d; nNumberOfBytesToWrite
0x1800b8200  mov     [rsp+3F0h+argList], r12; lpOverlapped
0x1800b8205  lea     r9, [rsp+3F0h+dwErrCode]; lpNumberOfBytesWritten
0x1800b820a  mov     rdx, rsi; lpBuffer
0x1800b820d  mov     rcx, r14; hFile
0x1800b8210  call    cs:__imp_WriteFile
0x1800b8216  inc     rdi
0x1800b8219  cmp     [rbx+rdi*2], r12w
0x1800b821e  jnz     short loc_1800B8216
0x1800b8220  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x1800b8224  mov     [rsp+3F0h+argList], r12; lpOverlapped
0x1800b8229  lea     r9, [rsp+3F0h+dwErrCode]; lpNumberOfBytesWritten
0x1800b822e  mov     rdx, rbx; lpBuffer
0x1800b8231  mov     rcx, r14; hFile
0x1800b8234  call    cs:__imp_WriteFile
0x1800b823a  lea     r9, [rsp+3F0h+dwErrCode]; lpNumberOfBytesWritten
0x1800b823f  mov     [rsp+3F0h+argList], r12; lpOverlapped
0x1800b8244  mov     r8d, r13d; nNumberOfBytesToWrite
0x1800b8247  lea     rdx, asc_1801152C4; "\r\n"
0x1800b824e  mov     rcx, r14; hFile
0x1800b8251  call    cs:__imp_WriteFile
0x1800b8257  lea     rcx, [rsp+3F0h+var_380]; this
0x1800b825c  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800b8261  lea     rcx, [rsp+3F0h+pszFormat]; this
0x1800b8266  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x1800b826b  mov     ecx, r15d; dwErrCode
0x1800b826e  call    cs:__imp_SetLastError
0x1800b8274  jmp     loc_1800B80B7
0x1800b8279  mov     ecx, r15d; dwErrCode
0x1800b827c  call    cs:__imp_SetLastError
0x1800b8282  jmp     loc_1800B8117
0x1800b8287  mov     ecx, r15d; dwErrCode
0x1800b828a  call    cs:__imp_SetLastError
0x1800b8290  mov     rcx, [rbp+2F0h+var_40]
0x1800b8297  xor     rcx, rsp; StackCookie
0x1800b829a  call    __security_check_cookie
0x1800b829f  mov     rbx, [rsp+3F0h+arg_8]
0x1800b82a7  add     rsp, 3C0h
0x1800b82ae  pop     r15
0x1800b82b0  pop     r14
0x1800b82b2  pop     r13
0x1800b82b4  pop     r12
0x1800b82b6  pop     rdi
0x1800b82b7  pop     rsi
0x1800b82b8  pop     rbp
0x1800b82b9  retn
```
