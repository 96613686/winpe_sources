# CLogger::PreInit(int *,int *,int)

- ea: `0x18006cf24`
- end: `0x18006d1a6`
- name: `?PreInit@CLogger@@QEAAJPEAH0H@Z`
- size: `642`
- prototype: `int(CLogger *__hidden this, int *, int *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e55c`

## callees

- `0x18000d1f0`
- `0x180021524`
- `0x18002c61c`
- `0x18006b26c`
- `0x18006b540`
- `0x18006b774`
- `0x18006bea0`
- `0x18006c134`
- `0x18006c284`
- `0x18006cf24`
- `0x1800cffcc`
- `0x1800e4010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18006cf66`
- `KERNEL32!GetProcAddress` at `0x18006cf66`
- `KERNEL32!CloseHandle` at `0x18006d03b`
- `KERNEL32!CloseHandle` at `0x18006d03b`
- `KERNEL32!CreateFileA` at `0x18006d02c`
- `KERNEL32!CreateFileA` at `0x18006d02c`
- `KERNEL32!LoadLibraryW` at `0x18006cf42`
- `KERNEL32!LoadLibraryW` at `0x18006cf42`

## string_xrefs

- `0x18006cf3b`: `MqLogMgr.dll`
- `0x18006cf5c`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall CLogger::PreInit(CLogger *this, wchar_t *a2, wchar_t *a3, int a4)
{
  HMODULE LibraryW; // rax
  int inited; // ebx
  int v9; // eax
  unsigned __int16 v10; // r8
  FARPROC ProcAddress; // rax
  CLogger *v12; // rcx
  unsigned __int16 v13; // r8
  signed int LogFileCreated; // eax
  HANDLE FileA; // rax
  CLogger *v16; // rcx
  bool v17; // zf
  signed int LogFile; // eax
  CLogger *v20; // rcx
  CLogger *v21; // rcx
  CLogger *v22; // rcx

  CLogger::ChooseFileName(this, a2, a3);
  LibraryW = LoadLibraryW(L"MqLogMgr.dll");
  inited = -1072823314;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject");
    if ( !ProcAddress )
    {
      v9 = -1072823314;
      v10 = 80;
      goto LABEL_7;
    }
    v9 = ((__int64 (__fastcall *)(GUID *, GUID *, void *))ProcAddress)(&CLSID_CLogMgr, &IID_IClassFactory, &g_Logger);
    if ( v9 < 0 )
    {
      v10 = 90;
      goto LABEL_7;
    }
    LogFileCreated = CLogger::GetLogFileCreated(v12, (int *)a3);
    inited = LogFileCreated;
    if ( LogFileCreated < 0 )
    {
      EvReportWithError(0xC000081C, LogFileCreated, 0);
      v13 = 1668;
      goto LABEL_8;
    }
    FileA = CreateFileA(&FileName, 0x80000000, 1u, 0, 3u, 0, 0);
    if ( FileA == (HANDLE)-1LL )
    {
      *(_DWORD *)a2 = 0;
      if ( a4 || *(_DWORD *)a3 )
      {
        inited = -2147024894;
        EvReportWithError(0xC000081C, 0x80070002, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 57), 15, &WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids);
        return (unsigned int)inited;
      }
    }
    else
    {
      CloseHandle(FileA);
      v17 = *(_DWORD *)a3 == 0;
      *(_DWORD *)a2 = 1;
      if ( !v17 || a4 )
        return 0;
    }
    *(_DWORD *)a2 = 0;
    LogFile = CLogger::CreateLogFile(v16);
    inited = LogFile;
    if ( LogFile < 0 )
    {
      EvReportWithError(0xC000081C, LogFile, 0);
      v13 = 30;
      goto LABEL_8;
    }
    inited = CLogger::InitLog(v20);
    if ( inited < 0 )
    {
      v13 = 1010;
      goto LABEL_8;
    }
    inited = CLogger::CreateInitialChkpoints(v21);
    if ( inited < 0 )
    {
      v13 = 1020;
      goto LABEL_8;
    }
    inited = CLogger::InitLogRead(v22);
    if ( inited < 0 )
    {
      v13 = 1030;
      goto LABEL_8;
    }
    inited = (*(__int64 (__fastcall **)(CLogger *, __int64, __int64 *))(*(_QWORD *)xmmword_18013B020 + 72LL))(
               xmmword_18013B020,
               1,
               &qword_18013B158);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 4) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 57),
        16,
        &WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids,
        qword_18013B158,
        inited);
    if ( inited < 0 )
    {
      v13 = 1040;
      goto LABEL_8;
    }
    return 0;
  }
  v9 = -1072823314;
  v10 = 70;
LABEL_7:
  LogMsgHR(v9, (wchar_t *)L"xactlog", v10);
  EvReportWithError(0xC000081C, 0xC00E03EE, 0);
  v13 = 1669;
LABEL_8:
  LogMsgHR(inited, (wchar_t *)L"xactlog", v13);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006cf24  push    rbx
0x18006cf26  push    rbp
0x18006cf27  push    rsi
0x18006cf28  push    rdi
0x18006cf29  sub     rsp, 48h
0x18006cf2d  mov     ebp, r9d
0x18006cf30  mov     rdi, r8
0x18006cf33  mov     rsi, rdx
0x18006cf36  call    ?ChooseFileName@CLogger@@AEAAXPEA_W0@Z; CLogger::ChooseFileName(wchar_t *,wchar_t *)
0x18006cf3b  lea     rcx, LibFileName; "MqLogMgr.dll"
0x18006cf42  call    cs:__imp_LoadLibraryW
0x18006cf48  mov     ebx, 0C00E03EEh
0x18006cf4d  test    rax, rax
0x18006cf50  jnz     short loc_18006CF5C
0x18006cf52  mov     eax, ebx
0x18006cf54  mov     r8d, 46h ; 'F'
0x18006cf5a  jmp     short loc_18006CF9F
0x18006cf5c  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x18006cf63  mov     rcx, rax; hModule
0x18006cf66  call    cs:__imp_GetProcAddress
0x18006cf6c  test    rax, rax
0x18006cf6f  jnz     short loc_18006CF7B
0x18006cf71  mov     eax, ebx
0x18006cf73  mov     r8d, 50h ; 'P'
0x18006cf79  jmp     short loc_18006CF9F
0x18006cf7b  lea     r8, ?g_Logger@@3VCLogger@@A; CLogger g_Logger
0x18006cf82  lea     rdx, IID_IClassFactory
0x18006cf89  lea     rcx, CLSID_CLogMgr
0x18006cf90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf95  test    eax, eax
0x18006cf97  jns     short loc_18006CFD8
0x18006cf99  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x18006cf9f  lea     rdx, aXactlog; "xactlog"
0x18006cfa6  mov     ecx, eax; int
0x18006cfa8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006cfad  xor     ecx, ecx
0x18006cfaf  mov     edx, ebx; dwMessageId
0x18006cfb1  movzx   r8d, cx; unsigned __int16
0x18006cfb5  mov     ecx, 0C000081Ch; unsigned int
0x18006cfba  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x18006cfbf  mov     r8d, 685h; unsigned __int16
0x18006cfc5  lea     rdx, aXactlog; "xactlog"
0x18006cfcc  mov     ecx, ebx; int
0x18006cfce  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18006cfd3  jmp     loc_18006D19B
0x18006cfd8  mov     rdx, rdi; int *
0x18006cfdb  call    ?GetLogFileCreated@CLogger@@QEAAJPEAH@Z; CLogger::GetLogFileCreated(int *)
0x18006cfe0  mov     ebx, eax
0x18006cfe2  test    eax, eax
0x18006cfe4  jns     short loc_18006D000
0x18006cfe6  xor     ecx, ecx
0x18006cfe8  mov     edx, eax; dwMessageId
0x18006cfea  movzx   r8d, cx; unsigned __int16
0x18006cfee  mov     ecx, 0C000081Ch; unsigned int
0x18006cff3  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x18006cff8  mov     r8d, 684h
0x18006cffe  jmp     short loc_18006CFC5
0x18006d000  xor     r9d, r9d; lpSecurityAttributes
0x18006d003  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18006d00c  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18006d014  lea     rcx, FileName; lpFileName
0x18006d01b  mov     edx, 80000000h; dwDesiredAccess
0x18006d020  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18006d028  lea     r8d, [r9+1]; dwShareMode
0x18006d02c  call    cs:__imp_CreateFileA
0x18006d032  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006d036  jz      short loc_18006D057
0x18006d038  mov     rcx, rax; hObject
0x18006d03b  call    cs:__imp_CloseHandle
0x18006d041  cmp     dword ptr [rdi], 0
0x18006d044  mov     dword ptr [rsi], 1
0x18006d04a  jnz     short loc_18006D050
0x18006d04c  test    ebp, ebp
0x18006d04e  jz      short loc_18006D06D
0x18006d050  xor     eax, eax
0x18006d052  jmp     loc_18006D19D
0x18006d057  mov     dword ptr [rsi], 0
0x18006d05d  test    ebp, ebp
0x18006d05f  jnz     loc_18006D150
0x18006d065  cmp     [rdi], ebp
0x18006d067  jnz     loc_18006D150
0x18006d06d  mov     dword ptr [rsi], 0
0x18006d073  call    ?CreateLogFile@CLogger@@AEAAJXZ; CLogger::CreateLogFile(void)
0x18006d078  mov     ebx, eax
0x18006d07a  test    eax, eax
0x18006d07c  jns     short loc_18006D09B
0x18006d07e  xor     ecx, ecx
0x18006d080  mov     edx, eax; dwMessageId
0x18006d082  movzx   r8d, cx; unsigned __int16
0x18006d086  mov     ecx, 0C000081Ch; unsigned int
0x18006d08b  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x18006d090  mov     r8d, 1Eh
0x18006d096  jmp     loc_18006CFC5
0x18006d09b  call    ?InitLog@CLogger@@AEAAJXZ; CLogger::InitLog(void)
0x18006d0a0  mov     ebx, eax
0x18006d0a2  test    eax, eax
0x18006d0a4  jns     short loc_18006D0B1
0x18006d0a6  mov     r8d, 3F2h
0x18006d0ac  jmp     loc_18006CFC5
0x18006d0b1  call    ?CreateInitialChkpoints@CLogger@@AEAAJXZ; CLogger::CreateInitialChkpoints(void)
0x18006d0b6  mov     ebx, eax
0x18006d0b8  test    eax, eax
0x18006d0ba  jns     short loc_18006D0C7
0x18006d0bc  mov     r8d, 3FCh
0x18006d0c2  jmp     loc_18006CFC5
0x18006d0c7  call    ?InitLogRead@CLogger@@AEAAJXZ; CLogger::InitLogRead(void)
0x18006d0cc  mov     ebx, eax
0x18006d0ce  test    eax, eax
0x18006d0d0  jns     short loc_18006D0DD
0x18006d0d2  mov     r8d, 406h
0x18006d0d8  jmp     loc_18006CFC5
0x18006d0dd  mov     rcx, qword ptr cs:xmmword_18013B020
0x18006d0e4  lea     r8, qword_18013B158
0x18006d0eb  mov     edx, 1
0x18006d0f0  mov     rax, [rcx]
0x18006d0f3  mov     rax, [rax+48h]
0x18006d0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0fc  mov     ebx, eax
0x18006d0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d105  lea     rax, WPP_GLOBAL_Control
0x18006d10c  cmp     rcx, rax
0x18006d10f  jz      short loc_18006D13D
0x18006d111  test    byte ptr [rcx+1D4h], 4
0x18006d118  jz      short loc_18006D13D
0x18006d11a  mov     r9, cs:qword_18013B158
0x18006d121  lea     r8, WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids
0x18006d128  mov     rcx, [rcx+1C8h]
0x18006d12f  mov     edx, 10h
0x18006d134  mov     [rsp+68h+dwCreationDisposition], ebx
0x18006d138  call    WPP_SF_qD
0x18006d13d  test    ebx, ebx
0x18006d13f  jns     loc_18006D050
0x18006d145  mov     r8d, 410h
0x18006d14b  jmp     loc_18006CFC5
0x18006d150  xor     eax, eax
0x18006d152  mov     ebx, 80070002h
0x18006d157  movzx   r8d, ax; unsigned __int16
0x18006d15b  mov     edx, ebx; dwMessageId
0x18006d15d  mov     ecx, 0C000081Ch; unsigned int
0x18006d162  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x18006d167  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d16e  lea     rax, WPP_GLOBAL_Control
0x18006d175  cmp     rcx, rax
0x18006d178  jz      short loc_18006D19B
0x18006d17a  test    byte ptr [rcx+1D4h], 1
0x18006d181  jz      short loc_18006D19B
0x18006d183  mov     rcx, [rcx+1C8h]
0x18006d18a  lea     r8, WPP_7d15b6d6d8ce317b682bc5190fed0d44_Traceguids
0x18006d191  mov     edx, 0Fh
0x18006d196  call    WPP_SF_
0x18006d19b  mov     eax, ebx
0x18006d19d  add     rsp, 48h
0x18006d1a1  pop     rdi
0x18006d1a2  pop     rsi
0x18006d1a3  pop     rbp
0x18006d1a4  pop     rbx
0x18006d1a5  retn
```
