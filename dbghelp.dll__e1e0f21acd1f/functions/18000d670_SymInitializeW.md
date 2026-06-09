# SymInitializeW

- ea: `0x18000d670`
- end: `0x18000d917`
- name: `SymInitializeW`
- size: `679`
- prototype: `BOOL __stdcall(HANDLE hProcess, PCWSTR UserSearchPath, BOOL fInvadeProcess)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000d570`

## callees

- `0x180008ad0`
- `0x18000aeec`
- `0x18000d670`
- `0x18000d920`
- `0x18000dac0`
- `0x18000dd90`
- `0x18000dfdc`
- `0x18000e278`
- `0x180027430`
- `0x1801a32cc`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18000d74f`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18000d74f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8de`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000d742`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000d769`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000d786`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000d742`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000d769`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000d786`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d6e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d6e2`
- `RPCRT4!UuidCreate` at `0x18000d70a`
- `RPCRT4!UuidCreate` at `0x18000d70a`

## string_xrefs

- `0x18000d73b`: `DBGHELP_TOKEN`

## pseudocode

```c
BOOL __stdcall SymInitializeW(HANDLE hProcess, PCWSTR UserSearchPath, BOOL fInvadeProcess)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // dl
  __int16 v9; // r8
  int v10; // r9d
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  void *v12; // rax
  __int64 v13; // rsi
  __int64 *v14; // rax
  DWORD ProcessModules; // esi
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-268h] BYREF
  long double v18; // [rsp+28h] [rbp-260h]
  UUID v19; // [rsp+30h] [rbp-258h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  SystemTimeAsFileTime = 0;
  if ( !dword_1802AF9C8 )
  {
    dword_1802AF9C8 = 1;
    dword_1802AF9B0 = 0;
    qword_1802AF9C0 = (__int64)&qword_1802AF9B8;
    qword_1802AF9B8 = (struct _PROCESS_ENTRY *)&qword_1802AF9B8;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    word_1802B1C10 = SystemTimeAsFileTime.dwLowDateTime;
    if ( !Debugger::Telemetry::g_telemetryInitialized )
    {
      Uuid = 0;
      UuidCreate(&Uuid);
      v19 = Uuid;
      DbgTelemetryInitializeForSession(v7, v6, &v19);
    }
  }
  ::Buffer = 0;
  GetEnvironmentVariableW(L"DBGHELP_TOKEN", &::Buffer, 0x7D1u);
  o((wchar_t)&::Buffer, v8, v9, v10, SystemTimeAsFileTime.dwLowDateTime, v18);
  if ( GetEnvironmentVariableW(L"DBGHELP_LOG", Buffer, 0x104u) )
    OpenLogFile(Buffer);
  if ( GetEnvironmentVariableW(L"DBGHELP_DBGOUT", Buffer, 0x104u) )
    dword_1802B09A8 = 1;
  ProcessEntry = FindProcessEntry(hProcess);
  if ( ProcessEntry )
  {
    if ( fInvadeProcess )
    {
      SetLastError(0x57u);
      return 0;
    }
    else
    {
      ++*((_DWORD *)ProcessEntry + 10);
      SetLastError(6u);
      return 1;
    }
  }
  else
  {
    v12 = (void *)pMemAlloc(0x1ACA8u);
    v13 = (__int64)v12;
    if ( v12 )
    {
      memset_0(v12, 0, 0x1ACA8u);
      *(_QWORD *)(v13 + 48) = hProcess;
      *(_DWORD *)(v13 + 40) = 1;
      *(_DWORD *)(v13 + 107600) = 88;
      *(_DWORD *)(v13 + 107680) = 2001;
      *(_DWORD *)(v13 + 109692) = 0;
      *(_QWORD *)(v13 + 24) = v13 + 16;
      *(_QWORD *)(v13 + 16) = v13 + 16;
      *(_DWORD *)(v13 + 56) = GetPID((DWORD)hProcess, 0);
      *(_DWORD *)(v13 + 109724) = 0;
      v14 = (__int64 *)qword_1802AF9C0;
      *(_QWORD *)v13 = &qword_1802AF9B8;
      *(_QWORD *)(v13 + 8) = v14;
      *v14 = v13;
      qword_1802AF9C0 = v13;
      ++dword_1802AF9B0;
      if ( SymSetSearchPathW(hProcess, UserSearchPath) )
      {
        if ( fInvadeProcess
          && (ProcessModules = GetProcessModules(
                                 (DWORD)hProcess,
                                 (int (*)(void *, const char *, unsigned __int64, unsigned int, void *))GetModule,
                                 0,
                                 0)) != 0 )
        {
          SymCleanup(hProcess);
          SetLastError(ProcessModules);
          return 0;
        }
        else
        {
          return 1;
        }
      }
      else
      {
        SymCleanup(hProcess);
        return 0;
      }
    }
    else
    {
      SetLastError(8u);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000d670  mov     [rsp+arg_10], rsi
0x18000d675  mov     [rsp+arg_18], rdi
0x18000d67a  push    r12
0x18000d67c  push    r14
0x18000d67e  push    r15
0x18000d680  sub     rsp, 270h
0x18000d687  mov     rax, cs:__security_cookie
0x18000d68e  xor     rax, rsp
0x18000d691  mov     [rsp+288h+var_28], rax
0x18000d699  mov     r15d, r8d
0x18000d69c  mov     r12, rdx
0x18000d69f  mov     rdi, rcx
0x18000d6a2  mov     qword ptr [rsp+288h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000d6ab  lea     r14, qword_1802AF9B8
0x18000d6b2  cmp     cs:dword_1802AF9C8, 0
0x18000d6b9  jnz     short loc_18000D725
0x18000d6bb  mov     cs:dword_1802AF9C8, 1
0x18000d6c5  mov     cs:dword_1802AF9B0, 0
0x18000d6cf  mov     cs:qword_1802AF9C0, r14
0x18000d6d6  mov     cs:qword_1802AF9B8, r14
0x18000d6dd  lea     rcx, [rsp+288h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d6e2  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d6e8  mov     rax, qword ptr [rsp+288h+SystemTimeAsFileTime.dwLowDateTime]
0x18000d6ed  mov     cs:word_1802B1C10, ax
0x18000d6f4  cmp     cs:?g_telemetryInitialized@Telemetry@Debugger@@3_NA, 0; bool Debugger::Telemetry::g_telemetryInitialized
0x18000d6fb  jnz     short loc_18000D725
0x18000d6fd  xorps   xmm0, xmm0
0x18000d700  movups  xmmword ptr [rsp+288h+Uuid.Data1], xmm0
0x18000d705  lea     rcx, [rsp+288h+Uuid]; Uuid
0x18000d70a  call    cs:__imp_UuidCreate
0x18000d710  movaps  xmm0, xmmword ptr [rsp+288h+Uuid.Data1]
0x18000d715  movdqa  [rsp+288h+var_258], xmm0
0x18000d71b  lea     r8, [rsp+288h+var_258]
0x18000d720  call    DbgTelemetryInitializeForSession
0x18000d725  xor     eax, eax
0x18000d727  mov     cs:Buffer, ax
0x18000d72e  mov     r8d, 7D1h; nSize
0x18000d734  lea     rdx, Buffer; lpBuffer
0x18000d73b  lea     rcx, aDbghelpToken; "DBGHELP_TOKEN"
0x18000d742  call    cs:__imp_GetEnvironmentVariableW
0x18000d748  lea     rcx, Buffer
0x18000d74f  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18000d755  mov     esi, 104h
0x18000d75a  mov     r8d, esi; nSize
0x18000d75d  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x18000d762  lea     rcx, aDbghelpLog; "DBGHELP_LOG"
0x18000d769  call    cs:__imp_GetEnvironmentVariableW
0x18000d76f  test    eax, eax
0x18000d771  jnz     loc_18000D88E
0x18000d777  mov     r8d, esi; nSize
0x18000d77a  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x18000d77f  lea     rcx, aDbghelpDbgout; "DBGHELP_DBGOUT"
0x18000d786  call    cs:__imp_GetEnvironmentVariableW
0x18000d78c  test    eax, eax
0x18000d78e  jz      short loc_18000D79A
0x18000d790  mov     cs:dword_1802B09A8, 1
0x18000d79a  mov     rcx, rdi; void *
0x18000d79d  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000d7a2  test    rax, rax
0x18000d7a5  jnz     loc_18000D89D
0x18000d7ab  mov     ecx, 1ACA8h; dwBytes
0x18000d7b0  call    pMemAlloc
0x18000d7b5  mov     rsi, rax
0x18000d7b8  test    rax, rax
0x18000d7bb  jz      loc_18000D853
0x18000d7c1  xor     edx, edx; Val
0x18000d7c3  mov     r8d, 1ACA8h; Size
0x18000d7c9  mov     rcx, rax; void *
0x18000d7cc  call    memset_0
0x18000d7d1  mov     [rsi+30h], rdi
0x18000d7d5  mov     dword ptr [rsi+28h], 1
0x18000d7dc  mov     dword ptr [rsi+1A450h], 58h ; 'X'
0x18000d7e6  mov     dword ptr [rsi+1A4A0h], 7D1h
0x18000d7f0  mov     dword ptr [rsi+1AC7Ch], 0
0x18000d7fa  lea     rax, [rsi+10h]
0x18000d7fe  mov     [rsi+18h], rax
0x18000d802  mov     [rax], rax
0x18000d805  xor     edx, edx; int
0x18000d807  mov     rcx, rdi; dwProcessId
0x18000d80a  call    ?GetPID@@YAKPEAXH@Z; GetPID(void *,int)
0x18000d80f  mov     [rsi+38h], eax
0x18000d812  mov     dword ptr [rsi+1AC9Ch], 0
0x18000d81c  mov     rax, cs:qword_1802AF9C0
0x18000d823  mov     [rsi], r14
0x18000d826  mov     [rsi+8], rax
0x18000d82a  mov     [rax], rsi
0x18000d82d  mov     cs:qword_1802AF9C0, rsi
0x18000d834  inc     cs:dword_1802AF9B0
0x18000d83a  mov     rdx, r12; SearchPathA
0x18000d83d  mov     rcx, rdi; hProcess
0x18000d840  call    SymSetSearchPathW
0x18000d845  test    eax, eax
0x18000d847  jz      short loc_18000D865
0x18000d849  test    r15d, r15d
0x18000d84c  jnz     short loc_18000D871
0x18000d84e  jmp     loc_18000D8DA
0x18000d853  mov     ecx, 8; dwErrCode
0x18000d858  call    cs:__imp_SetLastError
0x18000d85e  xor     eax, eax
0x18000d860  jmp     loc_18000D8ED
0x18000d865  mov     rcx, rdi; hProcess
0x18000d868  call    SymCleanup
0x18000d86d  xor     eax, eax
0x18000d86f  jmp     short loc_18000D8ED
0x18000d871  xor     r9d, r9d; int
0x18000d874  xor     r8d, r8d; void *
0x18000d877  lea     rdx, ?GetModule@@YAHPEAXPEBD_KK0@Z; int (*)(void *, const char *, unsigned __int64, unsigned int, void *)
0x18000d87e  mov     rcx, rdi; dwProcessId
0x18000d881  call    ?GetProcessModules@@YAKPEAXP6AH0PEBD_KK0@Z0H@Z; GetProcessModules(void *,int (*)(void *,char const *,unsigned __int64,ulong,void *),void *,int)
0x18000d886  mov     esi, eax
0x18000d888  test    eax, eax
0x18000d88a  jnz     short loc_18000D8C6
0x18000d88c  jmp     short loc_18000D8DA
0x18000d88e  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x18000d893  call    ?OpenLogFile@@YAXPEBG@Z; OpenLogFile(ushort const *)
0x18000d898  jmp     loc_18000D777
0x18000d89d  test    r15d, r15d
0x18000d8a0  jz      short loc_18000D8B1
0x18000d8a2  mov     ecx, 57h ; 'W'; dwErrCode
0x18000d8a7  call    cs:__imp_SetLastError
0x18000d8ad  xor     eax, eax
0x18000d8af  jmp     short loc_18000D8ED
0x18000d8b1  inc     dword ptr [rax+28h]
0x18000d8b4  mov     ecx, 6; dwErrCode
0x18000d8b9  call    cs:__imp_SetLastError
0x18000d8bf  mov     eax, 1
0x18000d8c4  jmp     short loc_18000D8ED
0x18000d8c6  mov     rcx, rdi; hProcess
0x18000d8c9  call    SymCleanup
0x18000d8ce  mov     ecx, esi; dwErrCode
0x18000d8d0  call    cs:__imp_SetLastError
0x18000d8d6  xor     eax, eax
0x18000d8d8  jmp     short loc_18000D8ED
0x18000d8da  jmp     short loc_18000D8E8
0x18000d8dc  mov     ecx, eax; dwErrCode
0x18000d8de  call    cs:__imp_SetLastError
0x18000d8e4  xor     eax, eax
0x18000d8e6  jmp     short loc_18000D8ED
0x18000d8e8  mov     eax, 1
0x18000d8ed  mov     rcx, [rsp+288h+var_28]
0x18000d8f5  xor     rcx, rsp; StackCookie
0x18000d8f8  call    __security_check_cookie
0x18000d8fd  lea     r11, [rsp+288h+var_18]
0x18000d905  mov     rsi, [r11+30h]
0x18000d909  mov     rdi, [r11+38h]
0x18000d90d  mov     rsp, r11
0x18000d910  pop     r15
0x18000d912  pop     r14
0x18000d914  pop     r12
0x18000d916  retn
```
