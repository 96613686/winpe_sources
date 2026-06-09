# NlPrintRoutineV(ulong,ushort *,char *)

- ea: `0x180007618`
- end: `0x180007b3e`
- name: `?NlPrintRoutineV@@YAXKPEAGPEAD@Z`
- size: `1318`
- prototype: `void(unsigned int, unsigned __int16 *, char *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180007278`
- `0x18000bd98`
- `0x180023f3c`
- `0x180024074`
- `0x18003e71c`

## callees

- `0x180007278`
- `0x180007618`
- `0x18000e270`
- `0x18000ed40`
- `0x18000edf4`
- `0x18003e350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000771d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000771d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000766d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007693`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000766d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007693`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800077b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800077b8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007712`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007712`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007b12`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007b12`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007abc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180007abc`
- `ntdll!RtlLeaveCriticalSection` at `0x18000774d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000774d`
- `ntdll!RtlEnterCriticalSection` at `0x18000777c`
- `ntdll!RtlEnterCriticalSection` at `0x18000777c`
- `ntdll!DbgPrint` at `0x18000772c`
- `ntdll!DbgPrint` at `0x180007ade`
- `ntdll!DbgPrint` at `0x18000772c`
- `ntdll!DbgPrint` at `0x180007ade`

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
    if ( !dword_1800F0140 )
      goto LABEL_70;
    if ( *a2 == 10 && !a2[1] )
      return;
    if ( NlGlobalLogFile == (HANDLE)-1LL )
      goto LABEL_18;
    if ( !dword_1800F1F44 && ++dword_1800F1F40 >= 50 )
    {
      dword_1800F1F40 = 0;
      FileSize = GetFileSize(NlGlobalLogFile, 0);
      if ( FileSize == -1 )
      {
        LastError = GetLastError();
        DbgPrint("[NETLOGON] Cannot GetFileSize %ld\n", LastError);
      }
      else if ( FileSize > dword_1800F1104 )
      {
        dword_1800F1F44 = 1;
        RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
        NlOpenDebugFile(1);
        NlPrintRoutine(2u, L"Logfile truncated because it was larger than %ld bytes\n", (unsigned int)dword_1800F1104);
        RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
        dword_1800F1F44 = 0;
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
            dword_1800F0140 = 1;
            v19[v17] = 10;
            v19[v17 + 1] = 0;
            goto LABEL_76;
          }
LABEL_75:
          dword_1800F0140 = 0;
LABEL_76:
          v21 = WideCharToMultiByte(0xFDE9u, 0, v19, -1, NlGlobalLogFileUtf8Buffer, 3073, 0, 0);
          if ( v21 )
          {
            if ( NlGlobalLogFile != (HANDLE)-1LL )
              WriteFile(NlGlobalLogFile, NlGlobalLogFileUtf8Buffer, v21 - 1, (LPDWORD)&NumberOfBytesWritten, 0);
          }
          else if ( !dword_1800F1F3C )
          {
            v22 = GetLastError();
            DbgPrint("[NETLOGON] Cannot convert logfile output to UTF8 - WC2MB failed with 0x%08x\n", v22);
            dword_1800F1F3C = 1;
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
0x180007618  mov     [rsp+arg_0], rbx
0x18000761d  mov     [rsp+arg_18], rbp
0x180007622  push    rsi
0x180007623  push    rdi
0x180007624  push    r12
0x180007626  push    r14
0x180007628  push    r15
0x18000762a  sub     rsp, 60h
0x18000762e  mov     rax, cs:__security_cookie
0x180007635  xor     rax, rsp
0x180007638  mov     [rsp+88h+var_30], rax
0x18000763d  xor     r12d, r12d
0x180007640  mov     r15, r8
0x180007643  mov     dword ptr [rsp+88h+NumberOfBytesWritten], r12d
0x180007648  mov     r14, rdx
0x18000764b  mov     edi, ecx
0x18000764d  test    ecx, ecx
0x18000764f  jz      short loc_18000765D
0x180007651  test    cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, ecx; _NETLOGON_PARAMETERS NlGlobalParameters
0x180007657  jz      loc_180007B18
0x18000765d  cmp     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, r12; ushort * NlGlobalLogFileOutputBuffer
0x180007664  jnz     short loc_180007683
0x180007666  mov     edx, 802h; uBytes
0x18000766b  xor     ecx, ecx; uFlags
0x18000766d  call    cs:__imp_LocalAlloc
0x180007673  mov     cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA, rax; ushort * NlGlobalLogFileOutputBuffer
0x18000767a  test    rax, rax
0x18000767d  jz      loc_180007B18
0x180007683  cmp     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, r12; uchar * NlGlobalLogFileUtf8Buffer
0x18000768a  jnz     short loc_1800076A9
0x18000768c  mov     edx, 0C01h; uBytes
0x180007691  xor     ecx, ecx; uFlags
0x180007693  call    cs:__imp_LocalAlloc
0x180007699  mov     cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA, rax; uchar * NlGlobalLogFileUtf8Buffer
0x1800076a0  test    rax, rax
0x1800076a3  jz      loc_180007B18
0x1800076a9  cmp     cs:dword_1800F0140, r12d
0x1800076b0  mov     esi, r12d
0x1800076b3  mov     eax, 0Ah
0x1800076b8  mov     ebp, 401h
0x1800076bd  jz      loc_180007A11
0x1800076c3  cmp     [r14], ax
0x1800076c7  jnz     short loc_1800076D4
0x1800076c9  cmp     [r14+2], r12w
0x1800076ce  jz      loc_180007B18
0x1800076d4  mov     rcx, cs:?NlGlobalLogFile@@3PEAXEA; hFile
0x1800076db  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800076df  jz      loc_180007793
0x1800076e5  cmp     cs:dword_1800F1F44, r12d
0x1800076ec  jnz     loc_180007789
0x1800076f2  mov     eax, cs:dword_1800F1F40
0x1800076f8  inc     eax
0x1800076fa  mov     cs:dword_1800F1F40, eax
0x180007700  cmp     eax, 32h ; '2'
0x180007703  jl      loc_180007789
0x180007709  xor     edx, edx; lpFileSizeHigh
0x18000770b  mov     cs:dword_1800F1F40, r12d
0x180007712  call    cs:__imp_GetFileSize
0x180007718  cmp     eax, 0FFFFFFFFh
0x18000771b  jnz     short loc_180007734
0x18000771d  call    cs:__imp_GetLastError
0x180007723  mov     edx, eax
0x180007725  lea     rcx, Format; "[NETLOGON] Cannot GetFileSize %ld\n"
0x18000772c  call    cs:__imp_DbgPrint
0x180007732  jmp     short loc_180007789
0x180007734  cmp     eax, cs:dword_1800F1104
0x18000773a  jbe     short loc_180007789
0x18000773c  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180007743  mov     cs:dword_1800F1F44, 1
0x18000774d  call    cs:__imp_RtlLeaveCriticalSection
0x180007753  mov     ecx, 1; int
0x180007758  call    ?NlOpenDebugFile@@YAXH@Z; NlOpenDebugFile(int)
0x18000775d  mov     r8d, cs:dword_1800F1104
0x180007764  lea     rdx, aLogfileTruncat; "Logfile truncated because it was larger"...
0x18000776b  mov     ecx, 2; unsigned int
0x180007770  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180007775  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000777c  call    cs:__imp_RtlEnterCriticalSection
0x180007782  mov     cs:dword_1800F1F44, r12d
0x180007789  cmp     cs:?NlGlobalLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * NlGlobalLogFile
0x180007791  jnz     short loc_1800077AB
0x180007793  mov     rcx, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; Buffer
0x18000779a  lea     r8, aNetlogon; "[NETLOGON] "
0x1800077a1  mov     rdx, rbp; BufferCount
0x1800077a4  call    swprintf_s
0x1800077a9  mov     esi, eax
0x1800077ab  xorps   xmm0, xmm0
0x1800077ae  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x1800077b3  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x1800077b8  call    cs:__imp_GetLocalTime
0x1800077be  movzx   r8d, [rsp+88h+SystemTime.wSecond]
0x1800077c4  mov     edx, ebp
0x1800077c6  mov     rax, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x1800077cd  sub     edx, esi; BufferCount
0x1800077cf  movzx   r10d, [rsp+88h+SystemTime.wMinute]
0x1800077d5  movzx   r11d, [rsp+88h+SystemTime.wHour]
0x1800077db  movzx   ebx, [rsp+88h+SystemTime.wDay]
0x1800077e0  movzx   r9d, [rsp+88h+SystemTime.wMonth]
0x1800077e6  mov     dword ptr [rsp+88h+lpUsedDefaultChar], r8d
0x1800077eb  lea     r8, a02u02u02u02u02; "%02u/%02u %02u:%02u:%02u "
0x1800077f2  mov     dword ptr [rsp+88h+lpDefaultChar], r10d
0x1800077f7  mov     [rsp+88h+cbMultiByte], r11d
0x1800077fc  mov     ecx, esi
0x1800077fe  mov     dword ptr [rsp+88h+ArgList], ebx
0x180007802  lea     rcx, [rax+rcx*2]; Buffer
0x180007806  call    swprintf_s
0x18000780b  add     esi, eax
0x18000780d  mov     eax, 8000h
0x180007812  cmp     edi, eax
0x180007814  ja      loc_180007921
0x18000781a  jz      loc_180007915
0x180007820  cmp     edi, 40h ; '@'
0x180007823  ja      short loc_180007895
0x180007825  jz      short loc_180007889
0x180007827  test    edi, edi
0x180007829  jz      loc_1800079EB
0x18000782f  sub     edi, 1
0x180007832  jz      short loc_18000787D
0x180007834  sub     edi, 1
0x180007837  jz      short loc_180007871
0x180007839  sub     edi, 2
0x18000783c  jz      short loc_180007865
0x18000783e  sub     edi, 4
0x180007841  jz      loc_1800079C7
0x180007847  sub     edi, 8
0x18000784a  jz      loc_1800079BE
0x180007850  cmp     edi, 10h
0x180007853  jnz     loc_1800079AC
0x180007859  lea     r9, aSite; "SITE"
0x180007860  jmp     loc_1800079CE
0x180007865  lea     r9, aLogon; "LOGON"
0x18000786c  jmp     loc_1800079CE
0x180007871  lea     r9, aMisc; "MISC"
0x180007878  jmp     loc_1800079CE
0x18000787d  lea     r9, aInit; "INIT"
0x180007884  jmp     loc_1800079CE
0x180007889  lea     r9, aMsa; "MSA"
0x180007890  jmp     loc_1800079CE
0x180007895  cmp     edi, 100h
0x18000789b  jz      short loc_180007909
0x18000789d  cmp     edi, 200h
0x1800078a3  jz      loc_1800079B5
0x1800078a9  cmp     edi, 400h
0x1800078af  jz      short loc_1800078FD
0x1800078b1  cmp     edi, 800h
0x1800078b7  jz      short loc_1800078F1
0x1800078b9  cmp     edi, 1000h
0x1800078bf  jz      loc_1800079B5
0x1800078c5  cmp     edi, 2000h
0x1800078cb  jz      short loc_1800078E5
0x1800078cd  cmp     edi, 4000h
0x1800078d3  jnz     loc_1800079AC
0x1800078d9  lea     r9, ServiceName; "DNS"
0x1800078e0  jmp     loc_1800079CE
0x1800078e5  lea     r9, aChangelog; "CHANGELOG"
0x1800078ec  jmp     loc_1800079CE
0x1800078f1  lea     r9, aError; "ERROR"
0x1800078f8  jmp     loc_1800079CE
0x1800078fd  lea     r9, aDomain; "DOMAIN"
0x180007904  jmp     loc_1800079CE
0x180007909  lea     r9, aCritical; "CRITICAL"
0x180007910  jmp     loc_1800079CE
0x180007915  lea     r9, aPerf; "PERF"
0x18000791c  jmp     loc_1800079CE
0x180007921  mov     eax, 800000h
0x180007926  cmp     edi, eax
0x180007928  ja      short loc_180007980
0x18000792a  jz      loc_1800079C7
0x180007930  cmp     edi, 10000h
0x180007936  jz      short loc_180007977
0x180007938  cmp     edi, 20000h
0x18000793e  jz      short loc_1800078D9
0x180007940  cmp     edi, 40000h
0x180007946  jz      short loc_18000796E
0x180007948  cmp     edi, 80000h
0x18000794e  jz      short loc_1800079B5
0x180007950  lea     eax, [rdi-100000h]
0x180007956  test    eax, 0FFEFFFFFh
0x18000795b  jz      short loc_1800079C7
0x18000795d  cmp     edi, 400000h
0x180007963  jnz     short loc_1800079AC
0x180007965  lea     r9, aEncrypt; "ENCRYPT"
0x18000796c  jmp     short loc_1800079CE
0x18000796e  lea     r9, aPulse; "PULSE"
0x180007975  jmp     short loc_1800079CE
0x180007977  lea     r9, aWorker; "WORKER"
0x18000797e  jmp     short loc_1800079CE
0x180007980  cmp     edi, 1000000h
0x180007986  jz      short loc_1800079C7
0x180007988  cmp     edi, 2000000h
0x18000798e  jz      short loc_1800079BE
0x180007990  cmp     edi, 4000000h
0x180007996  jz      short loc_1800079B5
0x180007998  cmp     edi, 8000000h
0x18000799e  jz      loc_180007859
0x1800079a4  cmp     edi, 10000000h
0x1800079aa  jz      short loc_1800079B5
0x1800079ac  lea     r9, aUnknown_4; "UNKNOWN"
0x1800079b3  jmp     short loc_1800079CE
0x1800079b5  lea     r9, aSession; "SESSION"
0x1800079bc  jmp     short loc_1800079CE
0x1800079be  lea     r9, aMailslot; "MAILSLOT"
0x1800079c5  jmp     short loc_1800079CE
0x1800079c7  lea     r9, aSync; "SYNC"
0x1800079ce  mov     rax, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x1800079d5  lea     r8, aWs_3; "[%ws] "
0x1800079dc  mov     edx, ebp
0x1800079de  sub     edx, esi; BufferCount
0x1800079e0  lea     rcx, [rax+rsi*2]; Buffer
0x1800079e4  call    swprintf_s
0x1800079e9  add     esi, eax
0x1800079eb  call    cs:__imp_GetCurrentThreadId
0x1800079f1  mov     rcx, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x1800079f8  lea     r8, aLu; "[%lu] "
0x1800079ff  mov     edx, ebp
0x180007a01  mov     r9d, eax
0x180007a04  sub     edx, esi; BufferCount
0x180007a06  lea     rcx, [rcx+rsi*2]; Buffer
0x180007a0a  call    swprintf_s
0x180007a0f  add     esi, eax
0x180007a11  mov     rax, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; ushort * NlGlobalLogFileOutputBuffer
0x180007a18  mov     ebx, 3FFh
0x180007a1d  mov     r8d, ebx
0x180007a20  mov     ecx, esi
0x180007a22  sub     ebp, esi
0x180007a24  mov     [rsp+88h+ArgList], r15; ArgList
0x180007a29  sub     r8d, esi; MaxCount
0x180007a2c  mov     edx, ebp; BufferCount
0x180007a2e  mov     r9, r14; Format
0x180007a31  lea     rcx, [rax+rcx*2]; Buffer
0x180007a35  call    _vsnwprintf_s
0x180007a3a  mov     r8, cs:?NlGlobalLogFileOutputBuffer@@3PEAGEA; lpWideCharStr
0x180007a41  test    eax, eax
0x180007a43  jns     short loc_180007A54
0x180007a45  mov     edx, 0Ah
0x180007a4a  mov     [r8+7FCh], dx
0x180007a52  jmp     short loc_180007A60
0x180007a54  lea     ebx, [rax+rsi]
0x180007a57  test    ebx, ebx
0x180007a59  jz      short loc_180007A8C
0x180007a5b  mov     edx, 0Ah
0x180007a60  lea     eax, [rbx-1]
0x180007a63  cmp     [r8+rax*2], dx
0x180007a68  jnz     short loc_180007A8C
0x180007a6a  mov     word ptr [r8+rax*2], 0Dh
0x180007a71  mov     eax, ebx
0x180007a73  mov     cs:dword_1800F0140, 1
0x180007a7d  mov     [r8+rax*2], dx
0x180007a82  lea     eax, [rbx+1]
0x180007a85  mov     [r8+rax*2], r12w
0x180007a8a  jmp     short loc_180007A93
0x180007a8c  mov     cs:dword_1800F0140, r12d
0x180007a93  mov     rax, cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA; uchar * NlGlobalLogFileUtf8Buffer
0x180007a9a  or      r9d, 0FFFFFFFFh; cchWideChar
0x180007a9e  mov     [rsp+88h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180007aa3  xor     edx, edx; dwFlags
0x180007aa5  mov     [rsp+88h+lpDefaultChar], r12; lpDefaultChar
0x180007aaa  mov     ecx, 0FDE9h; CodePage
0x180007aaf  mov     [rsp+88h+cbMultiByte], 0C01h; cbMultiByte
0x180007ab7  mov     [rsp+88h+ArgList], rax; lpMultiByteStr
0x180007abc  call    cs:__imp_WideCharToMultiByte
0x180007ac2  test    eax, eax
0x180007ac4  jnz     short loc_180007AF0
0x180007ac6  cmp     cs:dword_1800F1F3C, r12d
0x180007acd  jnz     short loc_180007B18
0x180007acf  call    cs:__imp_GetLastError
0x180007ad5  mov     edx, eax
0x180007ad7  lea     rcx, aNetlogonCannot; "[NETLOGON] Cannot convert logfile outpu"...
0x180007ade  call    cs:__imp_DbgPrint
0x180007ae4  mov     cs:dword_1800F1F3C, 1
0x180007aee  jmp     short loc_180007B18
0x180007af0  mov     rcx, cs:?NlGlobalLogFile@@3PEAXEA; hFile
0x180007af7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007afb  jz      short loc_180007B18
0x180007afd  mov     rdx, cs:?NlGlobalLogFileUtf8Buffer@@3PEAEEA; lpBuffer
0x180007b04  lea     r8d, [rax-1]; nNumberOfBytesToWrite
0x180007b08  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180007b0d  mov     [rsp+88h+ArgList], r12; lpOverlapped
0x180007b12  call    cs:__imp_WriteFile
0x180007b18  mov     rcx, [rsp+88h+var_30]
0x180007b1d  xor     rcx, rsp; StackCookie
0x180007b20  call    __security_check_cookie
0x180007b25  lea     r11, [rsp+88h+var_28]
0x180007b2a  mov     rbx, [r11+30h]
0x180007b2e  mov     rbp, [r11+48h]
0x180007b32  mov     rsp, r11
0x180007b35  pop     r15
0x180007b37  pop     r14
0x180007b39  pop     r12
0x180007b3b  pop     rdi
0x180007b3c  pop     rsi
0x180007b3d  retn
```
