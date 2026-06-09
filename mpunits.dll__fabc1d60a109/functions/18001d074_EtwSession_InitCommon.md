# EtwSession_InitCommon

- ea: `0x18001d074`
- end: `0x18001d29f`
- name: `EtwSession_InitCommon`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001ced0`
- `0x1800252b0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000ac44`
- `0x18000b2a8`
- `0x18001d074`
- `0x18002d8a0`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d174`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d220`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d174`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d128`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001d114`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001d114`

## string_xrefs

- `0x18001d161`: `mpunits.dll`
- `0x18001d212`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwSession_InitCommon(
        __int64 a1,
        WCHAR *a2,
        void (__stdcall *a3)(PEVENT_TRACE pEvent),
        __int64 a4,
        void *a5)
{
  TRACEHANDLE v9; // rax
  DWORD LastError; // eax
  DWORD v11; // ebx
  HMODULE ModuleHandleA; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  HMODULE v18; // rax
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-D0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+1F0h] [rbp+F0h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileName = a2;
  Logfile.LoggerName = 0;
  Logfile.LogFileMode = 0x10000000;
  Logfile.EventCallback = a3;
  Logfile.Context = a5;
  if ( !a2 )
  {
    Logfile.LogFileMode = 268435712;
    Logfile.LoggerName = (LPWSTR)(a1 + 368);
  }
  *(_QWORD *)a1 = a4;
  *(_QWORD *)(a1 + 8) = a5;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v9 = OpenTraceW(&Logfile);
  *(_QWORD *)(a1 + 32) = v9;
  if ( v9 == -1 )
  {
    LastError = GetLastError();
    *(_DWORD *)&EventDescriptor.Level = 4;
    *(_DWORD *)&EventDescriptor.Id = 5;
    EventDescriptor.Keyword = 1;
    v11 = LastError;
    Etw_Trace1_int(&EventDescriptor);
    EventDescriptor = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    if ( v11 == 1392 )
    {
      v13 = 1392;
      v14 = 2124;
    }
    else
    {
      v13 = v11;
      v14 = 2036;
    }
    *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, v14, v13);
    LOBYTE(EventDescriptor.Keyword) = 1;
    MI_ReportErrorDetails_ForCustomError(5, (int)L"ETW Normalizer", 0, 0);
    return 1;
  }
  else
  {
    v16 = RxcScheduler_Schedule(0, (unsigned int)EtwSession_ConsumerThread, 0, a1, 0, 0);
    v17 = v16;
    if ( v16 )
    {
      trace_ETW_ThreadStartFail(v16);
      EventDescriptor = 0;
      v18 = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(v18, 2037, v17);
      LOBYTE(EventDescriptor.Keyword) = 1;
      MI_ReportErrorDetails_ForCustomError(v17, (int)L"ETW Normalizer", 0, 0);
      return v17;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18001d074  push    rbp
0x18001d076  push    rbx
0x18001d077  push    rsi
0x18001d078  push    rdi
0x18001d079  push    r12
0x18001d07b  push    r14
0x18001d07d  push    r15
0x18001d07f  lea     rbp, [rsp-110h]
0x18001d087  sub     rsp, 210h
0x18001d08e  mov     rax, cs:__security_cookie
0x18001d095  xor     rax, rsp
0x18001d098  mov     [rbp+140h+var_40], rax
0x18001d09f  mov     r14, [rbp+140h+arg_20]
0x18001d0a6  mov     rbx, r8
0x18001d0a9  mov     rdi, rdx
0x18001d0ac  mov     rsi, rcx
0x18001d0af  xor     edx, edx; Val
0x18001d0b1  lea     rcx, [rsp+240h+Logfile]; void *
0x18001d0b6  mov     r8d, 1C0h; Size
0x18001d0bc  mov     r15, r9
0x18001d0bf  call    memset_0
0x18001d0c4  xor     r12d, r12d
0x18001d0c7  mov     [rsp+240h+Logfile.LogFileName], rdi
0x18001d0cc  mov     [rsp+240h+Logfile.LoggerName], r12
0x18001d0d1  mov     dword ptr [rsp+240h+Logfile.1Ch], 10000000h
0x18001d0d9  mov     qword ptr [rbp+140h+Logfile.1A8h], rbx
0x18001d0e0  mov     [rbp+140h+Logfile.Context], r14
0x18001d0e7  test    rdi, rdi
0x18001d0ea  jnz     short loc_18001D100
0x18001d0ec  lea     rax, [rsi+170h]
0x18001d0f3  mov     dword ptr [rsp+240h+Logfile.1Ch], 10000100h
0x18001d0fb  mov     [rsp+240h+Logfile.LoggerName], rax
0x18001d100  mov     [rsi], r15
0x18001d103  lea     rcx, [rsp+240h+Logfile]; Logfile
0x18001d108  mov     [rsi+8], r14
0x18001d10c  mov     [rsi+18h], r12
0x18001d110  mov     [rsi+10h], r12
0x18001d114  call    cs:__imp_OpenTraceW
0x18001d11a  mov     [rsi+20h], rax
0x18001d11e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d122  jnz     loc_18001D1E4
0x18001d128  call    cs:__imp_GetLastError
0x18001d12e  mov     edi, 5
0x18001d133  mov     dword ptr [rbp+140h+EventDescriptor.Level], 4
0x18001d13d  mov     edx, eax
0x18001d13f  mov     dword ptr [rbp+140h+EventDescriptor.Id], edi
0x18001d145  lea     rcx, [rbp+140h+EventDescriptor]; EventDescriptor
0x18001d14c  mov     [rbp+140h+EventDescriptor.Keyword], 1
0x18001d157  mov     ebx, eax
0x18001d159  call    Etw_Trace1_int
0x18001d15e  xorps   xmm0, xmm0
0x18001d161  lea     rcx, ModuleName; "mpunits.dll"
0x18001d168  movups  xmmword ptr [rbp+140h+EventDescriptor.Id], xmm0
0x18001d16f  mov     esi, 570h
0x18001d174  call    cs:__imp_GetModuleHandleA
0x18001d17a  mov     rcx, rax
0x18001d17d  cmp     ebx, esi
0x18001d17f  jnz     short loc_18001D18B
0x18001d181  mov     r8d, esi
0x18001d184  mov     edx, 84Ch
0x18001d189  jmp     short loc_18001D193
0x18001d18b  mov     r8d, ebx
0x18001d18e  mov     edx, 7F4h
0x18001d193  call    _Intlstr_FormatString_FormatMessage
0x18001d198  mov     qword ptr [rbp+140h+EventDescriptor.Id], rax
0x18001d19f  lea     r9, [rbp+140h+EventDescriptor]
0x18001d1a6  mov     byte ptr [rbp+140h+EventDescriptor.Keyword], 1
0x18001d1ad  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001d1b4  movaps  xmm0, xmmword ptr [rbp+140h+EventDescriptor.Id]
0x18001d1bb  mov     r8d, 1
0x18001d1c1  mov     [rsp+240h+var_218], r12; __int64
0x18001d1c6  mov     ecx, edi; int
0x18001d1c8  movdqa  xmmword ptr [rbp+140h+EventDescriptor.Id], xmm0
0x18001d1d0  mov     [rsp+240h+var_220], r12; __int64
0x18001d1d5  call    MI_ReportErrorDetails_ForCustomError
0x18001d1da  mov     eax, 1
0x18001d1df  jmp     loc_18001D27E
0x18001d1e4  mov     [rsp+240h+var_218], r12
0x18001d1e9  lea     rdx, EtwSession_ConsumerThread
0x18001d1f0  mov     r9, rsi
0x18001d1f3  mov     [rsp+240h+var_220], r12
0x18001d1f8  xor     r8d, r8d
0x18001d1fb  xor     ecx, ecx
0x18001d1fd  call    RxcScheduler_Schedule
0x18001d202  mov     ebx, eax
0x18001d204  test    eax, eax
0x18001d206  jz      short loc_18001D27C
0x18001d208  mov     ecx, eax
0x18001d20a  call    trace_ETW_ThreadStartFail
0x18001d20f  xorps   xmm0, xmm0
0x18001d212  lea     rcx, ModuleName; "mpunits.dll"
0x18001d219  movups  xmmword ptr [rbp+140h+EventDescriptor.Id], xmm0
0x18001d220  call    cs:__imp_GetModuleHandleA
0x18001d226  mov     r8d, ebx
0x18001d229  mov     edx, 7F5h
0x18001d22e  mov     rcx, rax
0x18001d231  call    _Intlstr_FormatString_FormatMessage
0x18001d236  mov     qword ptr [rbp+140h+EventDescriptor.Id], rax
0x18001d23d  lea     r9, [rbp+140h+EventDescriptor]
0x18001d244  mov     byte ptr [rbp+140h+EventDescriptor.Keyword], 1
0x18001d24b  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001d252  movaps  xmm0, xmmword ptr [rbp+140h+EventDescriptor.Id]
0x18001d259  mov     r8d, 15h
0x18001d25f  mov     [rsp+240h+var_218], r12; __int64
0x18001d264  mov     ecx, ebx; int
0x18001d266  movdqa  xmmword ptr [rbp+140h+EventDescriptor.Id], xmm0
0x18001d26e  mov     [rsp+240h+var_220], r12; __int64
0x18001d273  call    MI_ReportErrorDetails_ForCustomError
0x18001d278  mov     eax, ebx
0x18001d27a  jmp     short loc_18001D27E
0x18001d27c  xor     eax, eax
0x18001d27e  mov     rcx, [rbp+140h+var_40]
0x18001d285  xor     rcx, rsp; StackCookie
0x18001d288  call    __security_check_cookie
0x18001d28d  add     rsp, 210h
0x18001d294  pop     r15
0x18001d296  pop     r14
0x18001d298  pop     r12
0x18001d29a  pop     rdi
0x18001d29b  pop     rsi
0x18001d29c  pop     rbx
0x18001d29d  pop     rbp
0x18001d29e  retn
```
