# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x180005944`
- end: `0x180005d20`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `988`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `27`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001060`
- `0x180001110`
- `0x1800011c0`
- `0x180005890`
- `0x180007ab4`
- `0x180008dd0`
- `0x18000b640`
- `0x18000e05c`
- `0x18000eaf8`
- `0x18000edb4`
- `0x180016ffc`
- `0x1800170a0`
- `0x1800191e8`
- `0x180031050`
- `0x1800370bc`
- `0x180038930`
- `0x18004fed4`
- `0x180050154`
- `0x1800504c0`
- `0x18005061c`
- `0x180050754`
- `0x180050b6c`
- `0x180050ea0`
- `0x1800514a0`
- `0x180051dfc`
- `0x180052490`
- `0x180052654`

## callees

- `0x180001e60`
- `0x180005944`
- `0x180005d28`
- `0x180006038`
- `0x18000717c`
- `0x1800072b0`
- `0x18000757c`
- `0x180014ec8`
- `0x1800430c4`
- `0x180043110`
- `0x180043a58`
- `0x180043b0c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005989`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005989`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ce5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cf2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ce5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cf2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005c90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005c90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c88`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005aa2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005aa2`
- `ADVAPI32!RegisterEventSourceW` at `0x180005bf0`
- `ADVAPI32!RegisterEventSourceW` at `0x180005bf0`
- `ADVAPI32!ReportEventW` at `0x180005c2b`
- `ADVAPI32!ReportEventW` at `0x180005c2b`
- `ADVAPI32!DeregisterEventSource` at `0x180005c34`
- `ADVAPI32!DeregisterEventSource` at `0x180005c34`

## string_xrefs

- `0x180005cb9`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

## pseudocode

```c
void CError::WriteToLog(CError *this, unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  const unsigned __int16 *v4; // rax
  int v8; // r15d
  wchar_t v9; // cx
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // r8d
  unsigned __int16 *v14; // r9
  DWORD v15; // edi
  unsigned int v16; // edx
  unsigned __int16 *v17; // r8
  DWORD v18; // r12d
  unsigned int v19; // r13d
  WORD v20; // di
  __int64 v21; // rbx
  __int64 v22; // rcx
  int ProcessLogger; // eax
  const unsigned __int16 *v24; // rdx
  int v25; // r8d
  HANDLE v26; // rbx
  __int64 v27; // rcx
  BOOL v28; // r14d
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-A8h]
  struct _EXCEPTION_POINTERS *nSize; // [rsp+28h] [rbp-A0h]
  unsigned int v33; // [rsp+60h] [rbp-68h] BYREF
  int v34; // [rsp+64h] [rbp-64h]
  __int64 v35; // [rsp+68h] [rbp-60h]
  __int64 v36; // [rsp+70h] [rbp-58h] BYREF
  LPCWSTR Strings[10]; // [rsp+78h] [rbp-50h] BYREF
  va_list va; // [rsp+F0h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  v8 = 0;
  v34 = 0;
  if ( dword_180072270 )
  {
    EnterCriticalSection(&CriticalSection);
    v8 = 1;
    v34 = 1;
    v4 = a4;
  }
  v9 = 0;
  word_180073860 = 0;
  if ( v4 )
  {
    StringCchVPrintfW(&word_180073860, 0x3FDu, v4, va);
    word_18007405A = 0;
    Strings[1] = 0;
    v9 = word_180073860;
  }
  if ( v9 )
    StringCchCatW(&word_180073860, 0x400u, L"\r\n");
  v10 = -1;
  do
    ++v10;
  while ( *(&word_180073860 + v10) );
  v33 = 1024 - v10;
  AppendApplicationInfo((unsigned __int16 *)v10, (unsigned int)a2, &v33);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v12, v11, &v33);
  v15 = *(_DWORD *)this;
  if ( *(_DWORD *)this )
  {
    StringCchCopyW(&Filename, 0x81u, L"\r\n*** Error Code = 0x%08x : %s");
    GetFormatString(0x3A2u, &Filename);
    Buffer = 0;
    FormatMessageW(0x1200u, 0, v15, 0, &Buffer, 0x80u, 0);
    StringCchPrintfW(&word_180074070, 0x400u, &Filename, v15, &Buffer);
    SafeAppend(&word_180074070, v16, v17, &v33);
  }
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v13, v14, &v33);
  AppendComsvcsFileVersion(v12, v11, &v33);
  v18 = *((_DWORD *)this + 2);
  v19 = *((unsigned __int16 *)this + 2);
  Strings[0] = &word_180073860;
  if ( v18 >> 30 < 2 )
  {
    v20 = 4;
  }
  else if ( v18 >> 30 == 2 )
  {
    v20 = 2;
  }
  else
  {
    v20 = 1;
  }
  v21 = 0;
  v35 = 0;
  v22 = 0;
  if ( g_pfnGetProcessLogger )
  {
    v36 = 0;
    ProcessLogger = g_pfnGetProcessLogger(&v36);
    v22 = 0;
    if ( ProcessLogger >= 0 )
    {
      v21 = v36;
      v35 = v36;
      v22 = v36;
    }
  }
  if ( v22 )
  {
    nSize = 0;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v21 + 24LL))(v21, v20, v19, v18, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v35 = 0;
  }
  else
  {
    v26 = RegisterEventSourceW(0, L"COM+");
    if ( v26 )
    {
      ReportEventW(v26, v20, v19, v18, 0, 1u, 0, Strings, 0);
      DeregisterEventSource(v26);
    }
  }
  v27 = 3221225472LL;
  v28 = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v8 )
    LeaveCriticalSection(&CriticalSection);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      nSize = (struct _EXCEPTION_POINTERS *)a2;
      LODWORD(lpBuffer) = CurrentThreadId;
      StringCchPrintfW(
        &word_180074880,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        lpBuffer);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_180074880);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v27, v24, v25, v28, *((_DWORD *)this + 11), nSize);
  }
}

```

## disassembly

```asm
0x180005944  mov     [rsp+arg_18], r9
0x180005949  mov     [rsp+arg_10], r8d
0x18000594e  mov     [rsp+arg_8], rdx
0x180005953  push    rbx
0x180005954  push    rsi
0x180005955  push    rdi
0x180005956  push    r12
0x180005958  push    r13
0x18000595a  push    r14
0x18000595c  push    r15
0x18000595e  sub     rsp, 90h
0x180005965  mov     rax, r9
0x180005968  mov     r12d, r8d
0x18000596b  mov     r13, rdx
0x18000596e  mov     rsi, rcx
0x180005971  xor     edi, edi
0x180005973  mov     r15d, edi
0x180005976  mov     [rsp+0C8h+var_64], edi
0x18000597a  cmp     cs:dword_180072270, edi
0x180005980  jz      short loc_1800059A5
0x180005982  lea     rcx, CriticalSection; lpCriticalSection
0x180005989  call    cs:__imp_EnterCriticalSection
0x18000598f  lea     r14d, [rdi+1]
0x180005993  mov     r15d, r14d
0x180005996  mov     [rsp+0C8h+var_64], r14d
0x18000599b  mov     rax, [rsp+0C8h+arg_18]
0x1800059a3  jmp     short loc_1800059AB
0x1800059a5  mov     r14d, 1
0x1800059ab  mov     ecx, edi
0x1800059ad  mov     cs:word_180073860, cx
0x1800059b4  lea     rbx, word_180073860
0x1800059bb  test    rax, rax
0x1800059be  jz      short loc_1800059F6
0x1800059c0  mov     [rsp+0C8h+var_48], rdi
0x1800059c8  lea     r9, [rsp+0C8h+arg_20]; char *
0x1800059d0  mov     r8, rax; unsigned __int16 *
0x1800059d3  mov     edx, 3FDh; unsigned __int64
0x1800059d8  mov     rcx, rbx; unsigned __int16 *
0x1800059db  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x1800059e0  mov     cs:word_18007405A, di
0x1800059e7  mov     [rsp+0C8h+var_48], rdi
0x1800059ef  movzx   ecx, cs:word_180073860
0x1800059f6  test    cx, cx
0x1800059f9  jz      short loc_180005A0F
0x1800059fb  lea     r8, asc_180062E00; "\r\n"
0x180005a02  mov     edx, 400h; unsigned __int64
0x180005a07  mov     rcx, rbx; unsigned __int16 *
0x180005a0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005a0f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005a13  inc     rcx; unsigned __int16 *
0x180005a16  cmp     [rbx+rcx*2], di
0x180005a1a  jnz     short loc_180005A13
0x180005a1c  mov     eax, 400h
0x180005a21  sub     eax, ecx
0x180005a23  mov     [rsp+0C8h+var_68], eax
0x180005a27  lea     r8, [rsp+0C8h+var_68]; unsigned int *
0x180005a2c  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x180005a31  cmp     [rsi+28h], edi
0x180005a34  jz      short loc_180005A40
0x180005a36  lea     r8, [rsp+0C8h+var_68]; unsigned int *
0x180005a3b  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x180005a40  mov     edi, [rsi]
0x180005a42  test    edi, edi
0x180005a44  jz      loc_180005AE0
0x180005a4a  lea     r8, aErrorCode0x08x; "\r\n*** Error Code = 0x%08x : %s"
0x180005a51  mov     edx, 81h; unsigned __int64
0x180005a56  lea     rcx, Filename; unsigned __int16 *
0x180005a5d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005a62  lea     rdx, Filename; unsigned __int16 *
0x180005a69  mov     ecx, 3A2h; unsigned int
0x180005a6e  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x180005a73  xor     eax, eax
0x180005a75  mov     cs:Buffer, ax
0x180005a7c  mov     [rsp+0C8h+Arguments], rax; Arguments
0x180005a81  mov     [rsp+0C8h+nSize], 80h; nSize
0x180005a89  lea     rax, Buffer
0x180005a90  mov     [rsp+0C8h+lpBuffer], rax; lpBuffer
0x180005a95  xor     r9d, r9d; dwLanguageId
0x180005a98  mov     r8d, edi; dwMessageId
0x180005a9b  xor     edx, edx; lpSource
0x180005a9d  mov     ecx, 1200h; dwFlags
0x180005aa2  call    cs:__imp_FormatMessageW
0x180005aa8  lea     rax, Buffer
0x180005aaf  mov     [rsp+0C8h+lpBuffer], rax
0x180005ab4  mov     r9d, edi
0x180005ab7  lea     r8, Filename; unsigned __int16 *
0x180005abe  mov     edx, 400h; unsigned __int64
0x180005ac3  lea     rcx, word_180074070; unsigned __int16 *
0x180005aca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005acf  lea     r9, [rsp+0C8h+var_68]; unsigned int *
0x180005ad4  lea     rcx, word_180074070; unsigned __int16 *
0x180005adb  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x180005ae0  cmp     dword ptr [rsi], 0
0x180005ae3  jnz     short loc_180005AEB
0x180005ae5  cmp     dword ptr [rsi+28h], 0
0x180005ae9  jz      short loc_180005B00
0x180005aeb  lea     rax, [rsp+0C8h+var_68]
0x180005af0  mov     [rsp+0C8h+lpBuffer], rax; unsigned int *
0x180005af5  mov     edx, r12d; unsigned int
0x180005af8  mov     rcx, r13; unsigned __int16 *
0x180005afb  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x180005b00  lea     r8, [rsp+0C8h+var_68]; unsigned int *
0x180005b05  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x180005b0a  mov     r12d, [rsi+8]
0x180005b0e  movzx   r13d, word ptr [rsi+4]
0x180005b13  mov     [rsp+0C8h+Strings], rbx
0x180005b18  mov     eax, r12d
0x180005b1b  shr     eax, 1Eh
0x180005b1e  xor     r9d, r9d
0x180005b21  test    eax, eax
0x180005b23  jz      short loc_180005B46
0x180005b25  sub     eax, 1
0x180005b28  jz      short loc_180005B46
0x180005b2a  sub     eax, 1
0x180005b2d  jz      short loc_180005B3F
0x180005b2f  cmp     eax, 1
0x180005b32  jz      short loc_180005B3A
0x180005b34  movzx   edi, r14w
0x180005b38  jmp     short loc_180005B4B
0x180005b3a  mov     edi, r14d
0x180005b3d  jmp     short loc_180005B4B
0x180005b3f  mov     edi, 2
0x180005b44  jmp     short loc_180005B4B
0x180005b46  mov     edi, 4
0x180005b4b  mov     [rsp+0C8h+var_60], r9
0x180005b50  mov     rbx, r9
0x180005b53  mov     [rsp+0C8h+var_60], rbx
0x180005b58  mov     rcx, r9
0x180005b5b  mov     rax, cs:?g_pfnGetProcessLogger@@3P6AJPEAX@ZEA; long (*g_pfnGetProcessLogger)(void *)
0x180005b62  test    rax, rax
0x180005b65  jz      short loc_180005B8D
0x180005b67  mov     [rsp+0C8h+var_58], r9
0x180005b6c  lea     rcx, [rsp+0C8h+var_58]
0x180005b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b76  xor     r9d, r9d
0x180005b79  mov     ecx, r9d
0x180005b7c  test    eax, eax
0x180005b7e  js      short loc_180005B8D
0x180005b80  mov     rbx, [rsp+0C8h+var_58]
0x180005b85  mov     [rsp+0C8h+var_60], rbx
0x180005b8a  mov     rcx, rbx
0x180005b8d  test    rcx, rcx
0x180005b90  jz      short loc_180005BE7
0x180005b92  mov     rax, [rbx]
0x180005b95  mov     r8d, r13d
0x180005b98  movzx   edx, di
0x180005b9b  mov     [rsp+0C8h+var_80], r9d
0x180005ba0  mov     [rsp+0C8h+lpRawData], r9
0x180005ba5  mov     dword ptr [rsp+0C8h+lpStrings], r14d
0x180005baa  lea     rcx, [rsp+0C8h+Strings]
0x180005baf  mov     [rsp+0C8h+Arguments], rcx
0x180005bb4  mov     qword ptr [rsp+0C8h+nSize], r9
0x180005bb9  mov     dword ptr [rsp+0C8h+lpBuffer], r9d
0x180005bbe  mov     r9d, r12d
0x180005bc1  mov     rcx, rbx
0x180005bc4  mov     rax, [rax+18h]
0x180005bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bcd  mov     rax, [rbx]
0x180005bd0  mov     rcx, rbx
0x180005bd3  mov     rax, [rax+10h]
0x180005bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bdc  mov     [rsp+0C8h+var_60], 0
0x180005be5  jmp     short loc_180005C3A
0x180005be7  lea     rdx, SourceName; "COM+"
0x180005bee  xor     ecx, ecx; lpUNCServerName
0x180005bf0  call    cs:__imp_RegisterEventSourceW
0x180005bf6  mov     rbx, rax
0x180005bf9  xor     ecx, ecx
0x180005bfb  test    rax, rax
0x180005bfe  jz      short loc_180005C3A
0x180005c00  mov     [rsp+0C8h+lpRawData], rcx; lpRawData
0x180005c05  lea     rax, [rsp+0C8h+Strings]
0x180005c0a  mov     [rsp+0C8h+lpStrings], rax; lpStrings
0x180005c0f  mov     dword ptr [rsp+0C8h+Arguments], ecx; dwDataSize
0x180005c13  mov     word ptr [rsp+0C8h+nSize], r14w; wNumStrings
0x180005c19  mov     [rsp+0C8h+lpBuffer], rcx; lpUserSid
0x180005c1e  mov     r9d, r12d; dwEventID
0x180005c21  movzx   r8d, r13w; wCategory
0x180005c25  movzx   edx, di; wType
0x180005c28  mov     rcx, rbx; hEventLog
0x180005c2b  call    cs:__imp_ReportEventW
0x180005c31  mov     rcx, rbx; hEventLog
0x180005c34  call    cs:__imp_DeregisterEventSource
0x180005c3a  mov     eax, [rsi+8]
0x180005c3d  mov     ecx, 0C0000000h
0x180005c42  and     eax, ecx
0x180005c44  xor     r14d, r14d
0x180005c47  cmp     eax, ecx
0x180005c49  setz    r14b
0x180005c4d  test    r15d, r15d
0x180005c50  jz      short loc_180005C5F
0x180005c52  lea     rcx, CriticalSection; lpCriticalSection
0x180005c59  call    cs:__imp_LeaveCriticalSection
0x180005c5f  cmp     dword ptr [rsi+28h], 0
0x180005c63  jz      loc_180005D0D
0x180005c69  cmp     dword ptr [rsi+2Ch], 0
0x180005c6d  jz      loc_180005CF8
0x180005c73  call    cs:__imp_IsDebuggerPresent
0x180005c79  test    eax, eax
0x180005c7b  jnz     short loc_180005C86
0x180005c7d  cmp     ds:7FFE02D4h, al
0x180005c84  jz      short loc_180005CF8
0x180005c86  mov     ebx, [rsi]
0x180005c88  call    cs:__imp_GetCurrentThreadId
0x180005c8e  mov     edi, eax
0x180005c90  call    cs:__imp_GetCurrentProcessId
0x180005c96  mov     dword ptr [rsp+0C8h+lpStrings], ebx
0x180005c9a  mov     ecx, [rsp+0C8h+arg_10]
0x180005ca1  mov     dword ptr [rsp+0C8h+Arguments], ecx
0x180005ca5  mov     rcx, [rsp+0C8h+arg_8]
0x180005cad  mov     qword ptr [rsp+0C8h+nSize], rcx; struct _EXCEPTION_POINTERS *
0x180005cb2  mov     dword ptr [rsp+0C8h+lpBuffer], edi
0x180005cb6  mov     r9d, eax
0x180005cb9  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x180005cc0  mov     edx, 3FFh; unsigned __int64
0x180005cc5  lea     rcx, word_180074880; unsigned __int16 *
0x180005ccc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005cd1  lea     rcx, OutputString; "\n#####################################"...
0x180005cd8  call    cs:__imp_OutputDebugStringW
0x180005cde  lea     rcx, word_180074880; lpOutputString
0x180005ce5  call    cs:__imp_OutputDebugStringW
0x180005ceb  lea     rcx, asc_180065F30; "#######################################"...
0x180005cf2  call    cs:__imp_OutputDebugStringW
0x180005cf8  cmp     dword ptr [rsi+28h], 0
0x180005cfc  jz      short loc_180005D0D
0x180005cfe  mov     eax, [rsi+2Ch]
0x180005d01  mov     dword ptr [rsp+0C8h+lpBuffer], eax; int
0x180005d05  mov     r9d, r14d; int
0x180005d08  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x180005d0d  add     rsp, 90h
0x180005d14  pop     r15
0x180005d16  pop     r14
0x180005d18  pop     r13
0x180005d1a  pop     r12
0x180005d1c  pop     rdi
0x180005d1d  pop     rsi
0x180005d1e  pop     rbx
0x180005d1f  retn
0x1800559e3  push    rbp
0x1800559e5  sub     rsp, 60h
0x1800559e9  mov     rbp, rdx
0x1800559ec  cmp     dword ptr [rbp+64h], 0
0x1800559f0  jz      short loc_180055A00
0x1800559f2  lea     rcx, CriticalSection; lpCriticalSection
0x1800559f9  call    cs:__imp_LeaveCriticalSection
0x1800559ff  nop
0x180055a00  add     rsp, 60h
0x180055a04  pop     rbp
0x180055a05  retn
```
