# NlPrintRoutineV(ulong,ushort *,char *)

- ea: `0x180007908`
- end: `0x180007e7d`
- name: `?NlPrintRoutineV@@YAXKPEAGPEAD@Z`
- size: `1397`
- prototype: `void(unsigned int, unsigned __int16 *, char *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180007518`
- `0x18000c440`
- `0x180024fc8`
- `0x180025114`
- `0x180040f18`

## callees

- `0x180007518`
- `0x180007908`
- `0x18000e910`
- `0x18000f3f0`
- `0x18000f4a4`
- `0x180040aa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000795d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007989`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000795d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007989`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180007ad2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180007ad2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007a0e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007a0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007e4a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007e4a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007de2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007de2`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a5b`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a5b`
- `ntdll!RtlEnterCriticalSection` at `0x180007a90`
- `ntdll!RtlEnterCriticalSection` at `0x180007a90`
- `ntdll!DbgPrint` at `0x180007a34`
- `ntdll!DbgPrint` at `0x180007e10`
- `ntdll!DbgPrint` at `0x180007a34`
- `ntdll!DbgPrint` at `0x180007e10`

## pseudocode

```c
void __fastcall NlPrintRoutineV(unsigned int a1, unsigned __int16 *a2, va_list a3)
{
  int v6; // esi
  DWORD FileSize; // eax
  DWORD LastError; // eax
  __int64 v9; // rsi
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // edi
  unsigned int v14; // edi
  const wchar_t *v15; // r9
  DWORD CurrentThreadId; // eax
  unsigned int v17; // ebx
  int v18; // eax
  const WCHAR *v19; // r8
  __int64 v20; // rax
  int v21; // eax
  DWORD v22; // eax
  __int64 NumberOfBytesWritten; // [rsp+40h] [rbp-48h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-40h] BYREF

  LODWORD(NumberOfBytesWritten) = 0;
  if ( (!a1 || (a1 & NlGlobalParameters) != 0)
    && (NlGlobalLogFileOutputBuffer || (NlGlobalLogFileOutputBuffer = (LPCWCH)LocalAlloc(0, 0x802u)) != 0)
    && (NlGlobalLogFileUtf8Buffer || (NlGlobalLogFileUtf8Buffer = (LPSTR)LocalAlloc(0, 0xC01u)) != 0) )
  {
    v6 = 0;
    if ( !dword_1800F7140 )
      goto LABEL_70;
    if ( *a2 == 10 && !a2[1] )
      return;
    if ( NlGlobalLogFile == (HANDLE)-1LL )
      goto LABEL_18;
    if ( !dword_1800F8EFC && ++dword_1800F8EF8 >= 50 )
    {
      dword_1800F8EF8 = 0;
      FileSize = GetFileSize(NlGlobalLogFile, 0);
      if ( FileSize == -1 )
      {
        LastError = GetLastError();
        DbgPrint("[NETLOGON] Cannot GetFileSize %ld\n", LastError);
      }
      else if ( FileSize > dword_1800F8104 )
      {
        dword_1800F8EFC = 1;
        RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
        NlOpenDebugFile(1);
        NlPrintRoutine(2u, L"Logfile truncated because it was larger than %ld bytes\n", (unsigned int)dword_1800F8104);
        RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
        dword_1800F8EFC = 0;
      }
    }
    if ( NlGlobalLogFile == (HANDLE)-1LL )
LABEL_18:
      v6 = swprintf_s((wchar_t *const)NlGlobalLogFileOutputBuffer, 0x401u, L"[NETLOGON] ");
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v9 = (unsigned int)(swprintf_s(
                          (wchar_t *const)&NlGlobalLogFileOutputBuffer[v6],
                          (unsigned int)(1025 - v6),
                          L"%02u/%02u %02u:%02u:%02u ",
                          SystemTime.wMonth,
                          SystemTime.wDay,
                          SystemTime.wHour,
                          SystemTime.wMinute,
                          SystemTime.wSecond,
                          NumberOfBytesWritten)
                      + v6);
    if ( a1 > 0x8000 )
    {
      if ( a1 > 0x800000 )
      {
        if ( a1 == 0x1000000 )
          goto LABEL_67;
        if ( a1 == 0x2000000 )
          goto LABEL_66;
        if ( a1 != 0x4000000 )
        {
          if ( a1 == 0x8000000 )
            goto LABEL_30;
          if ( a1 != 0x10000000 )
          {
LABEL_64:
            v15 = L"UNKNOWN";
            goto LABEL_68;
          }
        }
      }
      else
      {
        switch ( a1 )
        {
          case 0x800000u:
            goto LABEL_67;
          case 0x10000u:
            v15 = L"WORKER";
            goto LABEL_68;
          case 0x20000u:
LABEL_42:
            v15 = L"DNS";
            goto LABEL_68;
          case 0x40000u:
            v15 = L"PULSE";
            goto LABEL_68;
        }
        if ( a1 != 0x80000 )
        {
          if ( ((a1 - 0x100000) & 0xFFEFFFFF) != 0 )
          {
            if ( a1 == 0x400000 )
            {
              v15 = L"ENCRYPT";
              goto LABEL_68;
            }
            goto LABEL_64;
          }
          goto LABEL_67;
        }
      }
    }
    else
    {
      if ( a1 == 0x8000 )
      {
        v15 = L"PERF";
        goto LABEL_68;
      }
      if ( a1 <= 0x40 )
      {
        if ( a1 == 64 )
        {
          v15 = L"MSA";
          goto LABEL_68;
        }
        if ( !a1 )
        {
LABEL_69:
          CurrentThreadId = GetCurrentThreadId();
          v6 = swprintf_s(
                 (wchar_t *const)&NlGlobalLogFileOutputBuffer[v9],
                 (unsigned int)(1025 - v9),
                 L"[%lu] ",
                 CurrentThreadId)
             + v9;
LABEL_70:
          v17 = 1023;
          v18 = vsnwprintf_s(
                  (wchar_t *const)&NlGlobalLogFileOutputBuffer[v6],
                  (unsigned int)(1025 - v6),
                  (unsigned int)(1023 - v6),
                  a2,
                  a3);
          v19 = NlGlobalLogFileOutputBuffer;
          if ( v18 >= 0 )
          {
            v17 = v18 + v6;
            if ( !(v18 + v6) )
              goto LABEL_75;
          }
          else
          {
            *((_WORD *)NlGlobalLogFileOutputBuffer + 1022) = 10;
          }
          v20 = v17 - 1;
          if ( v19[v20] == 10 )
          {
            v19[v20] = 13;
            dword_1800F7140 = 1;
            v19[v17] = 10;
            v19[v17 + 1] = 0;
            goto LABEL_76;
          }
LABEL_75:
          dword_1800F7140 = 0;
LABEL_76:
          v21 = WideCharToMultiByte(0xFDE9u, 0, v19, -1, NlGlobalLogFileUtf8Buffer, 3073, 0, 0);
          if ( v21 )
          {
            if ( NlGlobalLogFile != (HANDLE)-1LL )
              WriteFile(NlGlobalLogFile, NlGlobalLogFileUtf8Buffer, v21 - 1, (LPDWORD)&NumberOfBytesWritten, 0);
          }
          else if ( !dword_1800F8EF4 )
          {
            v22 = GetLastError();
            DbgPrint("[NETLOGON] Cannot convert logfile output to UTF8 - WC2MB failed with 0x%08x\n", v22);
            dword_1800F8EF4 = 1;
          }
          return;
        }
        v10 = a1 - 1;
        if ( !v10 )
        {
          v15 = L"INIT";
          goto LABEL_68;
        }
        v11 = v10 - 1;
        if ( !v11 )
        {
          v15 = L"MISC";
          goto LABEL_68;
        }
        v12 = v11 - 2;
        if ( !v12 )
        {
          v15 = L"LOGON";
          goto LABEL_68;
        }
        v13 = v12 - 4;
        if ( v13 )
        {
          v14 = v13 - 8;
          if ( v14 )
          {
            if ( v14 == 16 )
            {
LABEL_30:
              v15 = L"SITE";
LABEL_68:
              v9 = (unsigned int)(swprintf_s(
                                    (wchar_t *const)&NlGlobalLogFileOutputBuffer[v9],
                                    (unsigned int)(1025 - v9),
                                    L"[%ws] ",
                                    v15)
                                + v9);
              goto LABEL_69;
            }
            goto LABEL_64;
          }
LABEL_66:
          v15 = L"MAILSLOT";
          goto LABEL_68;
        }
LABEL_67:
        v15 = L"SYNC";
        goto LABEL_68;
      }
      if ( a1 == 256 )
      {
        v15 = L"CRITICAL";
        goto LABEL_68;
      }
      if ( a1 != 512 )
      {
        if ( a1 == 1024 )
        {
          v15 = L"DOMAIN";
          goto LABEL_68;
        }
        if ( a1 == 2048 )
        {
          v15 = L"ERROR";
          goto LABEL_68;
        }
        if ( a1 != 4096 )
        {
          if ( a1 == 0x2000 )
          {
            v15 = L"CHANGELOG";
            goto LABEL_68;
          }
          if ( a1 != 0x4000 )
            goto LABEL_64;
          goto LABEL_42;
        }
      }
    }
    v15 = L"SESSION";
    goto LABEL_68;
  }
}

```

## disassembly

```asm
0x180007908  mov     [rsp+arg_0], rbx
0x18000790d  mov     [rsp+arg_18], rbp
0x180007912  push    rsi
0x180007913  push    rdi
0x180007914  push    r12
0x180007916  push    r14
0x180007918  push    r15
0x18000791a  sub     rsp, 60h
0x18000791e  mov     rax, cs:__security_cookie
0x180007925  xor     rax, rsp
0x180007928  mov     [rsp+88h+var_30], rax
0x18000792d  xor     r12d, r12d
0x180007930  mov     r15, r8
0x180007933  mov     dword ptr [rsp+88h+NumberOfBytesWritten], r12d
0x180007938  mov     r14, rdx
0x18000793b  mov     edi, ecx
0x18000793d  test    ecx, ecx
0x18000793f  jz      short loc_18000794D
0x180007941  test    cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, ecx; _NETLOGON_PARAMETERS NlGlobalParameters
0x180007947  jz      loc_180007E56
0x18000794d  cmp     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, r12; ushort * NlGlobalLogFileOutputBuffer
0x180007954  jnz     short loc_180007979
0x180007956  mov     edx, 802h; uBytes
0x18000795b  xor     ecx, ecx; uFlags
0x18000795d  call    cs:__imp_LocalAlloc
0x180007964  nop     dword ptr [rax+rax+00h]
0x180007969  mov     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, rax; ushort * NlGlobalLogFileOutputBuffer
0x180007970  test    rax, rax
0x180007973  jz      loc_180007E56
0x180007979  cmp     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, r12; uchar * NlGlobalLogFileUtf8Buffer
0x180007980  jnz     short loc_1800079A5
0x180007982  mov     edx, 0C01h; uBytes
0x180007987  xor     ecx, ecx; uFlags
0x180007989  call    cs:__imp_LocalAlloc
0x180007990  nop     dword ptr [rax+rax+00h]
0x180007995  mov     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, rax; uchar * NlGlobalLogFileUtf8Buffer
0x18000799c  test    rax, rax
0x18000799f  jz      loc_180007E56
0x1800079a5  cmp     cs:dword_1800F7140, r12d
0x1800079ac  mov     esi, r12d
0x1800079af  mov     eax, 0Ah
0x1800079b4  mov     ebp, 401h
0x1800079b9  jz      loc_180007D37
0x1800079bf  cmp     [r14], ax
0x1800079c3  jnz     short loc_1800079D0
0x1800079c5  cmp     [r14+2], r12w
0x1800079ca  jz      loc_180007E56
0x1800079d0  mov     rcx, cs:?NlGlobalLogFile@@3PEAXEA; hFile
0x1800079d7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800079db  jz      loc_180007AAD
0x1800079e1  cmp     cs:dword_1800F8EFC, r12d
0x1800079e8  jnz     loc_180007AA3
0x1800079ee  mov     eax, cs:dword_1800F8EF8
0x1800079f4  inc     eax
0x1800079f6  mov     cs:dword_1800F8EF8, eax
0x1800079fc  cmp     eax, 32h ; '2'
0x1800079ff  jl      loc_180007AA3
0x180007a05  xor     edx, edx; lpFileSizeHigh
0x180007a07  mov     cs:dword_1800F8EF8, r12d
0x180007a0e  call    cs:__imp_GetFileSize
0x180007a15  nop     dword ptr [rax+rax+00h]
0x180007a1a  cmp     eax, 0FFFFFFFFh
0x180007a1d  jnz     short loc_180007A42
0x180007a1f  call    cs:__imp_GetLastError
0x180007a26  nop     dword ptr [rax+rax+00h]
0x180007a2b  mov     edx, eax
0x180007a2d  lea     rcx, Format; "[NETLOGON] Cannot GetFileSize %ld\n"
0x180007a34  call    cs:__imp_DbgPrint
0x180007a3b  nop     dword ptr [rax+rax+00h]
0x180007a40  jmp     short loc_180007AA3
0x180007a42  cmp     eax, cs:dword_1800F8104
0x180007a48  jbe     short loc_180007AA3
0x180007a4a  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180007a51  mov     cs:dword_1800F8EFC, 1
0x180007a5b  call    cs:__imp_RtlLeaveCriticalSection
0x180007a62  nop     dword ptr [rax+rax+00h]
0x180007a67  mov     ecx, 1; int
0x180007a6c  call    ?NlOpenDebugFile@@YAXH@Z; NlOpenDebugFile(int)
0x180007a71  mov     r8d, cs:dword_1800F8104
0x180007a78  lea     rdx, aLogfileTruncat; "Logfile truncated because it was larger"...
0x180007a7f  mov     ecx, 2; unsigned int
0x180007a84  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007a89  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180007a90  call    cs:__imp_RtlEnterCriticalSection
0x180007a97  nop     dword ptr [rax+rax+00h]
0x180007a9c  mov     cs:dword_1800F8EFC, r12d
0x180007aa3  cmp     cs:?NlGlobalLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * NlGlobalLogFile
0x180007aab  jnz     short loc_180007AC5
0x180007aad  mov     rcx, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; Buffer
0x180007ab4  lea     r8, aNetlogon; "[NETLOGON] "
0x180007abb  mov     rdx, rbp; BufferCount
0x180007abe  call    swprintf_s
0x180007ac3  mov     esi, eax
0x180007ac5  xorps   xmm0, xmm0
0x180007ac8  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x180007acd  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x180007ad2  call    cs:__imp_GetLocalTime
0x180007ad9  nop     dword ptr [rax+rax+00h]
0x180007ade  movzx   r8d, [rsp+88h+SystemTime.wSecond]
0x180007ae4  mov     edx, ebp
0x180007ae6  mov     rax, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x180007aed  sub     edx, esi; BufferCount
0x180007aef  movzx   r10d, [rsp+88h+SystemTime.wMinute]
0x180007af5  movzx   r11d, [rsp+88h+SystemTime.wHour]
0x180007afb  movzx   ebx, [rsp+88h+SystemTime.wDay]
0x180007b00  movzx   r9d, [rsp+88h+SystemTime.wMonth]
0x180007b06  mov     dword ptr [rsp+88h+lpUsedDefaultChar], r8d
0x180007b0b  lea     r8, a02u02u02u02u02; "%02u/%02u %02u:%02u:%02u "
0x180007b12  mov     dword ptr [rsp+88h+lpDefaultChar], r10d
0x180007b17  mov     [rsp+88h+cbMultiByte], r11d
0x180007b1c  mov     ecx, esi
0x180007b1e  mov     dword ptr [rsp+88h+ArgList], ebx
0x180007b22  lea     rcx, [rax+rcx*2]; Buffer
0x180007b26  call    swprintf_s
0x180007b2b  add     esi, eax
0x180007b2d  mov     eax, 8000h
0x180007b32  cmp     edi, eax
0x180007b34  ja      loc_180007C41
0x180007b3a  jz      loc_180007C35
0x180007b40  cmp     edi, 40h ; '@'
0x180007b43  ja      short loc_180007BB5
0x180007b45  jz      short loc_180007BA9
0x180007b47  test    edi, edi
0x180007b49  jz      loc_180007D0B
0x180007b4f  sub     edi, 1
0x180007b52  jz      short loc_180007B9D
0x180007b54  sub     edi, 1
0x180007b57  jz      short loc_180007B91
0x180007b59  sub     edi, 2
0x180007b5c  jz      short loc_180007B85
0x180007b5e  sub     edi, 4
0x180007b61  jz      loc_180007CE7
0x180007b67  sub     edi, 8
0x180007b6a  jz      loc_180007CDE
0x180007b70  cmp     edi, 10h
0x180007b73  jnz     loc_180007CCC
0x180007b79  lea     r9, aSite; "SITE"
0x180007b80  jmp     loc_180007CEE
0x180007b85  lea     r9, aLogon; "LOGON"
0x180007b8c  jmp     loc_180007CEE
0x180007b91  lea     r9, aMisc; "MISC"
0x180007b98  jmp     loc_180007CEE
0x180007b9d  lea     r9, aInit; "INIT"
0x180007ba4  jmp     loc_180007CEE
0x180007ba9  lea     r9, aMsa; "MSA"
0x180007bb0  jmp     loc_180007CEE
0x180007bb5  cmp     edi, 100h
0x180007bbb  jz      short loc_180007C29
0x180007bbd  cmp     edi, 200h
0x180007bc3  jz      loc_180007CD5
0x180007bc9  cmp     edi, 400h
0x180007bcf  jz      short loc_180007C1D
0x180007bd1  cmp     edi, 800h
0x180007bd7  jz      short loc_180007C11
0x180007bd9  cmp     edi, 1000h
0x180007bdf  jz      loc_180007CD5
0x180007be5  cmp     edi, 2000h
0x180007beb  jz      short loc_180007C05
0x180007bed  cmp     edi, 4000h
0x180007bf3  jnz     loc_180007CCC
0x180007bf9  lea     r9, ServiceName; "DNS"
0x180007c00  jmp     loc_180007CEE
0x180007c05  lea     r9, aChangelog; "CHANGELOG"
0x180007c0c  jmp     loc_180007CEE
0x180007c11  lea     r9, aError; "ERROR"
0x180007c18  jmp     loc_180007CEE
0x180007c1d  lea     r9, aDomain; "DOMAIN"
0x180007c24  jmp     loc_180007CEE
0x180007c29  lea     r9, aCritical; "CRITICAL"
0x180007c30  jmp     loc_180007CEE
0x180007c35  lea     r9, aPerf; "PERF"
0x180007c3c  jmp     loc_180007CEE
0x180007c41  mov     eax, 800000h
0x180007c46  cmp     edi, eax
0x180007c48  ja      short loc_180007CA0
0x180007c4a  jz      loc_180007CE7
0x180007c50  cmp     edi, 10000h
0x180007c56  jz      short loc_180007C97
0x180007c58  cmp     edi, 20000h
0x180007c5e  jz      short loc_180007BF9
0x180007c60  cmp     edi, 40000h
0x180007c66  jz      short loc_180007C8E
0x180007c68  cmp     edi, 80000h
0x180007c6e  jz      short loc_180007CD5
0x180007c70  lea     eax, [rdi-100000h]
0x180007c76  test    eax, 0FFEFFFFFh
0x180007c7b  jz      short loc_180007CE7
0x180007c7d  cmp     edi, 400000h
0x180007c83  jnz     short loc_180007CCC
0x180007c85  lea     r9, aEncrypt; "ENCRYPT"
0x180007c8c  jmp     short loc_180007CEE
0x180007c8e  lea     r9, aPulse; "PULSE"
0x180007c95  jmp     short loc_180007CEE
0x180007c97  lea     r9, aWorker; "WORKER"
0x180007c9e  jmp     short loc_180007CEE
0x180007ca0  cmp     edi, 1000000h
0x180007ca6  jz      short loc_180007CE7
0x180007ca8  cmp     edi, 2000000h
0x180007cae  jz      short loc_180007CDE
0x180007cb0  cmp     edi, 4000000h
0x180007cb6  jz      short loc_180007CD5
0x180007cb8  cmp     edi, 8000000h
0x180007cbe  jz      loc_180007B79
0x180007cc4  cmp     edi, 10000000h
0x180007cca  jz      short loc_180007CD5
0x180007ccc  lea     r9, aUnknown_4; "UNKNOWN"
0x180007cd3  jmp     short loc_180007CEE
0x180007cd5  lea     r9, aSession; "SESSION"
0x180007cdc  jmp     short loc_180007CEE
0x180007cde  lea     r9, aMailslot; "MAILSLOT"
0x180007ce5  jmp     short loc_180007CEE
0x180007ce7  lea     r9, aSync; "SYNC"
0x180007cee  mov     rax, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x180007cf5  lea     r8, aWs_3; "[%ws] "
0x180007cfc  mov     edx, ebp
0x180007cfe  sub     edx, esi; BufferCount
0x180007d00  lea     rcx, [rax+rsi*2]; Buffer
0x180007d04  call    swprintf_s
0x180007d09  add     esi, eax
0x180007d0b  call    cs:__imp_GetCurrentThreadId
0x180007d12  nop     dword ptr [rax+rax+00h]
0x180007d17  mov     rcx, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x180007d1e  lea     r8, aLu; "[%lu] "
0x180007d25  mov     edx, ebp
0x180007d27  mov     r9d, eax
0x180007d2a  sub     edx, esi; BufferCount
0x180007d2c  lea     rcx, [rcx+rsi*2]; Buffer
0x180007d30  call    swprintf_s
0x180007d35  add     esi, eax
0x180007d37  mov     rax, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x180007d3e  mov     ebx, 3FFh
0x180007d43  mov     r8d, ebx
0x180007d46  mov     ecx, esi
0x180007d48  sub     ebp, esi
0x180007d4a  mov     [rsp+88h+ArgList], r15; ArgList
0x180007d4f  sub     r8d, esi; MaxCount
0x180007d52  mov     edx, ebp; BufferCount
0x180007d54  mov     r9, r14; Format
0x180007d57  lea     rcx, [rax+rcx*2]; Buffer
0x180007d5b  call    _vsnwprintf_s
0x180007d60  mov     r8, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; lpWideCharStr
0x180007d67  test    eax, eax
0x180007d69  jns     short loc_180007D7A
0x180007d6b  mov     edx, 0Ah
0x180007d70  mov     [r8+7FCh], dx
0x180007d78  jmp     short loc_180007D86
0x180007d7a  lea     ebx, [rax+rsi]
0x180007d7d  test    ebx, ebx
0x180007d7f  jz      short loc_180007DB2
0x180007d81  mov     edx, 0Ah
0x180007d86  lea     eax, [rbx-1]
0x180007d89  cmp     [r8+rax*2], dx
0x180007d8e  jnz     short loc_180007DB2
0x180007d90  mov     word ptr [r8+rax*2], 0Dh
0x180007d97  mov     eax, ebx
0x180007d99  mov     cs:dword_1800F7140, 1
0x180007da3  mov     [r8+rax*2], dx
0x180007da8  lea     eax, [rbx+1]
0x180007dab  mov     [r8+rax*2], r12w
0x180007db0  jmp     short loc_180007DB9
0x180007db2  mov     cs:dword_1800F7140, r12d
0x180007db9  mov     rax, cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA; uchar * NlGlobalLogFileUtf8Buffer
0x180007dc0  or      r9d, 0FFFFFFFFh; cchWideChar
0x180007dc4  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180007dc9  xor     edx, edx; dwFlags
0x180007dcb  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x180007dd0  mov     ecx, 0FDE9h; CodePage
0x180007dd5  mov     [rsp+88h+cbMultiByte], 0C01h; cbMultiByte
0x180007ddd  mov     [rsp+88h+ArgList], rax; lpMultiByteStr
0x180007de2  call    cs:__imp_WideCharToMultiByte
0x180007de9  nop     dword ptr [rax+rax+00h]
0x180007dee  test    eax, eax
0x180007df0  jnz     short loc_180007E28
0x180007df2  cmp     cs:dword_1800F8EF4, r12d
0x180007df9  jnz     short loc_180007E56
0x180007dfb  call    cs:__imp_GetLastError
0x180007e02  nop     dword ptr [rax+rax+00h]
0x180007e07  mov     edx, eax
0x180007e09  lea     rcx, aNetlogonCannot; "[NETLOGON] Cannot convert logfile outpu"...
0x180007e10  call    cs:__imp_DbgPrint
0x180007e17  nop     dword ptr [rax+rax+00h]
0x180007e1c  mov     cs:dword_1800F8EF4, 1
0x180007e26  jmp     short loc_180007E56
0x180007e28  mov     rcx, cs:?NlGlobalLogFile@@3PEAXEA; hFile
0x180007e2f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007e33  jz      short loc_180007E56
0x180007e35  mov     rdx, cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA; lpBuffer
0x180007e3c  lea     r8d, [rax-1]; nNumberOfBytesToWrite
0x180007e40  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180007e45  mov     [rsp+88h+ArgList], r12; lpOverlapped
0x180007e4a  call    cs:__imp_WriteFile
0x180007e51  nop     dword ptr [rax+rax+00h]
0x180007e56  mov     rcx, [rsp+88h+var_30]
0x180007e5b  xor     rcx, rsp; StackCookie
0x180007e5e  call    __security_check_cookie
0x180007e63  lea     r11, [rsp+88h+var_28]
0x180007e68  mov     rbx, [r11+30h]
0x180007e6c  mov     rbp, [r11+48h]
0x180007e70  mov     rsp, r11
0x180007e73  pop     r15
  ... truncated ...
```
