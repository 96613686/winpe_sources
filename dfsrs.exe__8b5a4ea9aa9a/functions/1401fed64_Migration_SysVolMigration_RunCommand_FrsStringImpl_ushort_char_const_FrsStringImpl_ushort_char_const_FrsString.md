# Migration::SysVolMigration::RunCommand(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)

- ea: `0x1401fed64`
- end: `0x1401ff1c7`
- name: `?RunCommand@SysVolMigration@Migration@@AEAAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@00@Z`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1401fea68`

## callees

- `0x1400046cc`
- `0x14000cd1c`
- `0x14001c31c`
- `0x140046a44`
- `0x14005c620`
- `0x14011d640`
- `0x140154d28`
- `0x1401b9494`
- `0x1401fed64`
- `0x140223010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1401fee7e`
- `KERNEL32!CreateFileW` at `0x1401fee7e`
- `KERNEL32!WaitForMultipleObjects` at `0x1401ff0bb`
- `KERNEL32!WaitForMultipleObjects` at `0x1401ff0bb`
- `KERNEL32!TerminateProcess` at `0x1401ff12e`
- `KERNEL32!TerminateProcess` at `0x1401ff12e`
- `KERNEL32!GetStdHandle` at `0x1401fef3f`
- `KERNEL32!GetStdHandle` at `0x1401fef3f`
- `KERNEL32!CreateProcessW` at `0x1401fefbd`
- `KERNEL32!CreateProcessW` at `0x1401fefbd`
- `KERNEL32!GetLastError` at `0x1401feeb0`
- `KERNEL32!GetLastError` at `0x1401fefdf`
- `KERNEL32!GetLastError` at `0x1401feeb0`
- `KERNEL32!GetLastError` at `0x1401fefdf`
- `KERNEL32!GetCurrentThreadId` at `0x1401feea2`
- `KERNEL32!GetCurrentThreadId` at `0x1401fefd1`
- `KERNEL32!GetCurrentThreadId` at `0x1401ff151`
- `KERNEL32!GetCurrentThreadId` at `0x1401feea2`
- `KERNEL32!GetCurrentThreadId` at `0x1401fefd1`
- `KERNEL32!GetCurrentThreadId` at `0x1401ff151`

## string_xrefs

- `0x1401fed97`: `Migration::SysVolMigration::RunCommand`
- `0x1401ff050`: `Migration::SysVolMigration::RunCommand`
- `0x1401ff0e3`: `Migration::SysVolMigration::RunCommand`
- `0x1401fee0e`: `[MIG] Run command '%?' outputFile:%? systemFolder:%?`
- `0x1401feecd`: `Migration::SysVolMigration::RunCommand`
- `0x1401feffc`: `Migration::SysVolMigration::RunCommand`
- `0x1401ff16e`: `Migration::SysVolMigration::RunCommand`
- `0x1401ff078`: `[MIG] CreateProcess(%?) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Migration::SysVolMigration::RunCommand(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rsi
  unsigned int *v9; // rdi
  const wchar_t *v10; // rdx
  __int64 v11; // rbx
  HANDLE v12; // rax
  DWORD CurrentThreadId; // edi
  DWORD LastError; // eax
  DWORD v15; // ebx
  DWORD v16; // eax
  DWORD v17; // eax
  __int64 v18; // rcx
  __int64 v20; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES ThreadAttributes; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE Handles; // [rsp+80h] [rbp-88h] BYREF
  __int64 v24; // [rsp+88h] [rbp-80h]
  const wchar_t *v25; // [rsp+90h] [rbp-78h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-70h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+B0h] [rbp-58h] BYREF
  const wchar_t *v28; // [rsp+C8h] [rbp-40h] BYREF
  int v29; // [rsp+D0h] [rbp-38h]
  int v30; // [rsp+D4h] [rbp-34h]
  const wchar_t *v31; // [rsp+D8h] [rbp-30h]
  struct _STARTUPINFOW StartupInfo; // [rsp+E8h] [rbp-20h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = L"SYSM";
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    *(_QWORD *)&ThreadAttributes.nLength = L"Migration::SysVolMigration::RunCommand";
    ThreadAttributes.lpSecurityDescriptor = (LPVOID)0x400000D56LL;
    *(_QWORD *)&ThreadAttributes.bInheritHandle = L"SYSM";
    v20 = *(_QWORD *)a4 + 18LL;
    Handles = (HANDLE)(*(_QWORD *)a3 + 18LL);
    v21 = *(_QWORD *)a2 + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,unsigned short const *>(
      (unsigned int)&ThreadAttributes,
      (unsigned int)L"[MIG] Run command '%?' outputFile:%? systemFolder:%?",
      (unsigned int)&v21,
      (unsigned int)&Handles,
      (__int64)&v20);
  }
  v11 = -1;
  v20 = -1;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *))(**(_QWORD **)(a1 + 80) + 48LL))(
          *(_QWORD *)(a1 + 80),
          v10) )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = 0;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
    v12 = CreateFileW((LPCWSTR)(*(_QWORD *)a3 + 18LL), 0x100004u, 7u, &SecurityAttributes, 4u, 0x80u, 0);
    detail::scoped_any_helper<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,value_const<void *,-1>,0>::reset(
      &v20,
      v12);
    v11 = v20;
    if ( v20 == -1 )
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      v9 = (unsigned int *)FrsStatusList::PushNewError(
                             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                             LastError,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                             "Migration::SysVolMigration::RunCommand",
                             3439,
                             CurrentThreadId,
                             0);
      if ( v9 )
        goto LABEL_22;
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 48LL))(*(_QWORD *)(a1 + 80)) )
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 257;
    StartupInfo.wShowWindow = 0;
    StartupInfo.hStdInput = GetStdHandle(0xFFFFFFF6);
    StartupInfo.hStdOutput = (HANDLE)v11;
    StartupInfo.hStdError = (HANDLE)v11;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    *(_QWORD *)&ThreadAttributes.nLength = 24;
    ThreadAttributes.lpSecurityDescriptor = 0;
    *(_QWORD *)&ThreadAttributes.bInheritHandle = 1;
    if ( CreateProcessW(
           0,
           (LPWSTR)(*(_QWORD *)a2 + 18LL),
           0,
           &ThreadAttributes,
           1,
           0x8000000u,
           0,
           (LPCWSTR)(*(_QWORD *)a4 + 18LL),
           &StartupInfo,
           &ProcessInformation) )
    {
      Handles = ProcessInformation.hProcess;
      v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 32LL))(*(_QWORD *)(a1 + 80));
      if ( WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF) == 1 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v28 = L"Migration::SysVolMigration::RunCommand";
          v29 = 3489;
          v30 = 4;
          v31 = L"SYSM";
          v21 = *(_QWORD *)a2 + 18LL;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(
            &v28,
            L"[MIG] Kill process '%?' following shutdown",
            &v21);
        }
        TerminateProcess(ProcessInformation.hProcess, 0);
      }
    }
    else
    {
      v15 = GetCurrentThreadId();
      v16 = GetLastError();
      v9 = (unsigned int *)FrsStatusList::PushNewError(
                             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                             v16,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
                             "Migration::SysVolMigration::RunCommand",
                             3468,
                             v15,
                             0);
      if ( v9 && g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        Handles = L"Migration::SysVolMigration::RunCommand";
        v24 = 0x200000D90LL;
        v25 = L"SYSM";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
          &Handles,
          L"[MIG] CreateProcess(%?) failed",
          a2);
      }
    }
    CloseHandleEx(&ProcessInformation.hThread);
    CloseHandleEx(&ProcessInformation.hProcess);
    if ( v9 )
    {
LABEL_22:
      v17 = GetCurrentThreadId();
      v8 = FrsStatusList::PushNewError(
             v18,
             v9[1],
             v9[2],
             *v9,
             "base\\fs\\remotefs\\frs\\src\\ad\\migration.cpp",
             "Migration::SysVolMigration::RunCommand",
             3500,
             v17,
             v9);
    }
  }
  scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,value_const<void *,-1>,0>::~scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,value_const<void *,-1>,0>(&v20);
  return v8;
}

```

## disassembly

```asm
0x1401fed64  mov     rax, rsp
0x1401fed67  mov     [rax+8], rbx
0x1401fed6b  mov     [rax+10h], rsi
0x1401fed6f  mov     [rax+18h], rdi
0x1401fed73  push    rbp
0x1401fed74  push    r12
0x1401fed76  push    r13
0x1401fed78  push    r14
0x1401fed7a  push    r15
0x1401fed7c  lea     rbp, [rax-78h]
0x1401fed80  sub     rsp, 150h
0x1401fed87  mov     r13, r9
0x1401fed8a  mov     r12, r8
0x1401fed8d  mov     r14, rdx
0x1401fed90  mov     r15, rcx
0x1401fed93  xor     esi, esi
0x1401fed95  mov     edi, esi
0x1401fed97  lea     rcx, aMigrationSysvo_76; "Migration::SysVolMigration::RunCommand"
0x1401fed9e  lea     rdx, aSysm; "SYSM"
0x1401feda5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401fedac  test    rax, rax
0x1401fedaf  jz      short loc_1401FEE1F
0x1401fedb1  cmp     [rax+40h], esi
0x1401fedb4  jz      short loc_1401FEE1F
0x1401fedb6  cmp     dword ptr [rax+38h], 4
0x1401fedba  jl      short loc_1401FEE1F
0x1401fedbc  mov     qword ptr [rsp+170h+ThreadAttributes.nLength], rcx
0x1401fedc1  mov     dword ptr [rsp+170h+ThreadAttributes.lpSecurityDescriptor], 0D56h
0x1401fedc9  mov     dword ptr [rsp+170h+ThreadAttributes.lpSecurityDescriptor+4], 4
0x1401fedd1  mov     qword ptr [rsp+170h+ThreadAttributes.bInheritHandle], rdx
0x1401fedd6  mov     rax, [r9]
0x1401fedd9  add     rax, 12h
0x1401feddd  mov     [rsp+170h+var_120], rax
0x1401fede2  mov     rax, [r8]
0x1401fede5  add     rax, 12h
0x1401fede9  mov     [rsp+170h+Handles], rax
0x1401fedee  mov     rax, [r14]
0x1401fedf1  add     rax, 12h
0x1401fedf5  mov     [rsp+170h+var_118], rax
0x1401fedfa  lea     rax, [rsp+170h+var_120]
0x1401fedff  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x1401fee04  lea     r9, [rsp+170h+Handles]
0x1401fee09  lea     r8, [rsp+170h+var_118]
0x1401fee0e  lea     rdx, aMigRunCommandO; "[MIG] Run command '%?' outputFile:%? sy"...
0x1401fee15  lea     rcx, [rsp+170h+ThreadAttributes]
0x1401fee1a  call    ??$DbgPrint@GPEBGPEBGPEBG@dbgobj@@QEAA_KPEBGAEBQEBG11@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort const *,ushort const *>(ushort const *,ushort const * const &,ushort const * const &,ushort const * const &)
0x1401fee1f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1401fee23  mov     [rsp+170h+var_120], rbx
0x1401fee28  mov     rcx, [r15+50h]
0x1401fee2c  mov     rax, [rcx]
0x1401fee2f  mov     rax, [rax+30h]
0x1401fee33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401fee38  test    al, al
0x1401fee3a  jnz     loc_1401FEEFF
0x1401fee40  mov     qword ptr [rbp+70h+SecurityAttributes.nLength], 18h
0x1401fee48  mov     [rbp+70h+SecurityAttributes.lpSecurityDescriptor], rsi
0x1401fee4c  mov     qword ptr [rbp+70h+SecurityAttributes.bInheritHandle], 1
0x1401fee54  mov     rcx, [r12]
0x1401fee58  add     rcx, 12h; lpFileName
0x1401fee5c  mov     [rsp+170h+hTemplateFile], rsi; hTemplateFile
0x1401fee61  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1401fee69  mov     [rsp+170h+dwCreationDisposition], 4; dwCreationDisposition
0x1401fee71  lea     r9, [rbp+70h+SecurityAttributes]; lpSecurityAttributes
0x1401fee75  mov     edx, 100004h; dwDesiredAccess
0x1401fee7a  lea     r8d, [rbx+8]; dwShareMode
0x1401fee7e  call    cs:__imp_CreateFileW
0x1401fee85  nop     dword ptr [rax+rax+00h]
0x1401fee8a  mov     rdx, rax
0x1401fee8d  lea     rcx, [rsp+170h+var_120]
0x1401fee92  call    ?reset@?$scoped_any_helper@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@U?$value_const@PEAX$0?0@@$0A@@detail@@SAXAEAV?$scoped_any@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@U?$value_const@PEAX$0?0@@$0A@@@PEAX@Z; detail::scoped_any_helper<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,value_const<void *,-1>,0>::reset(scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,value_const<void *,-1>,0> &,void *)
0x1401fee97  mov     rbx, [rsp+170h+var_120]
0x1401fee9c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1401feea0  jnz     short loc_1401FEEFF
0x1401feea2  call    cs:__imp_GetCurrentThreadId
0x1401feea9  nop     dword ptr [rax+rax+00h]
0x1401feeae  mov     edi, eax
0x1401feeb0  call    cs:__imp_GetLastError
0x1401feeb7  nop     dword ptr [rax+rax+00h]
0x1401feebc  mov     [rsp+170h+lpStartupInfo], rsi
0x1401feec1  mov     dword ptr [rsp+170h+lpCurrentDirectory], edi
0x1401feec5  mov     dword ptr [rsp+170h+hTemplateFile], 0D6Fh
0x1401feecd  lea     rcx, aMigrationSysvo_19; "Migration::SysVolMigration::RunCommand"
0x1401feed4  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], rcx
0x1401feed9  lea     rcx, aBaseFsRemotefs_99; "base\\fs\\remotefs\\frs\\src\\ad\\migra"...
0x1401feee0  mov     qword ptr [rsp+170h+dwCreationDisposition], rcx
0x1401feee5  lea     r9d, [rbx+2]
0x1401feee9  xor     r8d, r8d
0x1401feeec  mov     edx, eax
0x1401feeee  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401feef3  mov     rdi, rax
0x1401feef6  test    rax, rax
0x1401feef9  jnz     loc_1401FF151
0x1401feeff  mov     rcx, [r15+50h]
0x1401fef03  mov     rdx, [rcx]
0x1401fef06  mov     rax, [rdx+30h]
0x1401fef0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401fef0f  test    al, al
0x1401fef11  jnz     loc_1401FF198
0x1401fef17  mov     r12d, 68h ; 'h'
0x1401fef1d  mov     r8d, r12d; Size
0x1401fef20  xor     edx, edx; Val
0x1401fef22  lea     rcx, [rbp+70h+StartupInfo]; void *
0x1401fef26  call    memset_0
0x1401fef2b  mov     [rbp+70h+StartupInfo.cb], r12d
0x1401fef2f  mov     [rbp+70h+StartupInfo.dwFlags], 101h
0x1401fef36  mov     [rbp+70h+StartupInfo.wShowWindow], si
0x1401fef3a  mov     ecx, 0FFFFFFF6h; nStdHandle
0x1401fef3f  call    cs:__imp_GetStdHandle
0x1401fef46  nop     dword ptr [rax+rax+00h]
0x1401fef4b  mov     [rbp+70h+StartupInfo.hStdInput], rax
0x1401fef4f  mov     [rbp+70h+StartupInfo.hStdOutput], rbx
0x1401fef53  mov     [rbp+70h+StartupInfo.hStdError], rbx
0x1401fef57  xorps   xmm0, xmm0
0x1401fef5a  xor     eax, eax
0x1401fef5c  movups  xmmword ptr [rbp+70h+ProcessInformation.hProcess], xmm0
0x1401fef60  mov     qword ptr [rbp+70h+ProcessInformation.dwProcessId], rax
0x1401fef64  mov     qword ptr [rsp+170h+ThreadAttributes.nLength], 18h
0x1401fef6d  mov     [rsp+170h+ThreadAttributes.lpSecurityDescriptor], rsi
0x1401fef72  lea     r12d, [rax+1]
0x1401fef76  mov     qword ptr [rsp+170h+ThreadAttributes.bInheritHandle], r12
0x1401fef7b  mov     rax, [r13+0]
0x1401fef7f  add     rax, 12h
0x1401fef83  mov     rdx, [r14]
0x1401fef86  add     rdx, 12h; lpCommandLine
0x1401fef8a  lea     rcx, [rbp+70h+ProcessInformation]
0x1401fef8e  mov     [rsp+170h+lpProcessInformation], rcx; lpProcessInformation
0x1401fef93  lea     rcx, [rbp+70h+StartupInfo]
0x1401fef97  mov     [rsp+170h+lpStartupInfo], rcx; lpStartupInfo
0x1401fef9c  mov     [rsp+170h+lpCurrentDirectory], rax; lpCurrentDirectory
0x1401fefa1  mov     [rsp+170h+hTemplateFile], rsi; lpEnvironment
0x1401fefa6  mov     [rsp+170h+dwFlagsAndAttributes], 8000000h; dwCreationFlags
0x1401fefae  mov     [rsp+170h+dwCreationDisposition], r12d; bInheritHandles
0x1401fefb3  lea     r9, [rsp+170h+ThreadAttributes]; lpThreadAttributes
0x1401fefb8  xor     r8d, r8d; lpProcessAttributes
0x1401fefbb  xor     ecx, ecx; lpApplicationName
0x1401fefbd  call    cs:__imp_CreateProcessW
0x1401fefc4  nop     dword ptr [rax+rax+00h]
0x1401fefc9  test    eax, eax
0x1401fefcb  jnz     loc_1401FF08E
0x1401fefd1  call    cs:__imp_GetCurrentThreadId
0x1401fefd8  nop     dword ptr [rax+rax+00h]
0x1401fefdd  mov     ebx, eax
0x1401fefdf  call    cs:__imp_GetLastError
0x1401fefe6  nop     dword ptr [rax+rax+00h]
0x1401fefeb  mov     [rsp+170h+lpStartupInfo], rsi
0x1401feff0  mov     dword ptr [rsp+170h+lpCurrentDirectory], ebx
0x1401feff4  mov     dword ptr [rsp+170h+hTemplateFile], 0D8Ch
0x1401feffc  lea     rcx, aMigrationSysvo_19; "Migration::SysVolMigration::RunCommand"
0x1401ff003  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], rcx
0x1401ff008  lea     rcx, aBaseFsRemotefs_99; "base\\fs\\remotefs\\frs\\src\\ad\\migra"...
0x1401ff00f  mov     qword ptr [rsp+170h+dwCreationDisposition], rcx
0x1401ff014  mov     r9d, r12d
0x1401ff017  xor     r8d, r8d
0x1401ff01a  mov     edx, eax
0x1401ff01c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ff021  mov     rdi, rax
0x1401ff024  test    rax, rax
0x1401ff027  jz      loc_1401FF13A
0x1401ff02d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ff034  test    rax, rax
0x1401ff037  jz      loc_1401FF13A
0x1401ff03d  cmp     [rax+40h], esi
0x1401ff040  jz      loc_1401FF13A
0x1401ff046  cmp     dword ptr [rax+38h], 2
0x1401ff04a  jl      loc_1401FF13A
0x1401ff050  lea     rax, aMigrationSysvo_76; "Migration::SysVolMigration::RunCommand"
0x1401ff057  mov     [rsp+170h+Handles], rax
0x1401ff05c  mov     dword ptr [rbp+70h+var_F0], 0D90h
0x1401ff063  mov     dword ptr [rbp+70h+var_F0+4], 2
0x1401ff06a  lea     rax, aSysm; "SYSM"
0x1401ff071  mov     [rbp+70h+var_E8], rax
0x1401ff075  mov     r8, r14
0x1401ff078  lea     rdx, aMigCreateproce; "[MIG] CreateProcess(%?) failed"
0x1401ff07f  lea     rcx, [rsp+170h+Handles]
0x1401ff084  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1401ff089  jmp     loc_1401FF13A
0x1401ff08e  mov     rax, [rbp+70h+ProcessInformation.hProcess]
0x1401ff092  mov     [rsp+170h+Handles], rax
0x1401ff097  mov     rcx, [r15+50h]
0x1401ff09b  mov     rax, [rcx]
0x1401ff09e  mov     rax, [rax+20h]
0x1401ff0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ff0a7  mov     [rbp+70h+var_F0], rax
0x1401ff0ab  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1401ff0af  xor     r8d, r8d; bWaitAll
0x1401ff0b2  lea     rdx, [rsp+170h+Handles]; lpHandles
0x1401ff0b7  lea     ecx, [r8+2]; nCount
0x1401ff0bb  call    cs:__imp_WaitForMultipleObjects
0x1401ff0c2  nop     dword ptr [rax+rax+00h]
0x1401ff0c7  cmp     eax, r12d
0x1401ff0ca  jnz     short loc_1401FF13A
0x1401ff0cc  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ff0d3  test    rax, rax
0x1401ff0d6  jz      short loc_1401FF128
0x1401ff0d8  cmp     [rax+40h], esi
0x1401ff0db  jz      short loc_1401FF128
0x1401ff0dd  cmp     dword ptr [rax+38h], 4
0x1401ff0e1  jl      short loc_1401FF128
0x1401ff0e3  lea     rax, aMigrationSysvo_76; "Migration::SysVolMigration::RunCommand"
0x1401ff0ea  mov     [rbp+70h+var_B0], rax
0x1401ff0ee  mov     [rbp+70h+var_A8], 0DA1h
0x1401ff0f5  mov     [rbp+70h+var_A4], 4
0x1401ff0fc  lea     rax, aSysm; "SYSM"
0x1401ff103  mov     [rbp+70h+var_A0], rax
0x1401ff107  mov     rax, [r14]
0x1401ff10a  add     rax, 12h
0x1401ff10e  mov     [rsp+170h+var_118], rax
0x1401ff113  lea     r8, [rsp+170h+var_118]
0x1401ff118  lea     rdx, aMigKillProcess; "[MIG] Kill process '%?' following shutd"...
0x1401ff11f  lea     rcx, [rbp+70h+var_B0]
0x1401ff123  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401ff128  xor     edx, edx; uExitCode
0x1401ff12a  mov     rcx, [rbp+70h+ProcessInformation.hProcess]; hProcess
0x1401ff12e  call    cs:__imp_TerminateProcess
0x1401ff135  nop     dword ptr [rax+rax+00h]
0x1401ff13a  lea     rcx, [rbp+70h+ProcessInformation.hThread]; void **
0x1401ff13e  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1401ff143  lea     rcx, [rbp+70h+ProcessInformation]; void **
0x1401ff147  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1401ff14c  test    rdi, rdi
0x1401ff14f  jz      short loc_1401FF198
0x1401ff151  call    cs:__imp_GetCurrentThreadId
0x1401ff158  nop     dword ptr [rax+rax+00h]
0x1401ff15d  mov     [rsp+170h+lpStartupInfo], rdi
0x1401ff162  mov     dword ptr [rsp+170h+lpCurrentDirectory], eax
0x1401ff166  mov     dword ptr [rsp+170h+hTemplateFile], 0DACh
0x1401ff16e  lea     rax, aMigrationSysvo_19; "Migration::SysVolMigration::RunCommand"
0x1401ff175  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], rax
0x1401ff17a  lea     rax, aBaseFsRemotefs_99; "base\\fs\\remotefs\\frs\\src\\ad\\migra"...
0x1401ff181  mov     qword ptr [rsp+170h+dwCreationDisposition], rax
0x1401ff186  mov     r9d, [rdi]
0x1401ff189  mov     r8d, [rdi+8]
0x1401ff18d  mov     edx, [rdi+4]
0x1401ff190  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ff195  mov     rsi, rax
0x1401ff198  lea     rcx, [rsp+170h+var_120]
0x1401ff19d  call    ??1?$scoped_any@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@U?$value_const@PEAX$0?0@@$0A@@@QEAA@XZ; scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,value_const<void *,-1>,0>::~scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,value_const<void *,-1>,0>(void)
0x1401ff1a2  mov     rax, rsi
0x1401ff1a5  lea     r11, [rsp+170h+var_20]
0x1401ff1ad  mov     rbx, [r11+30h]
0x1401ff1b1  mov     rsi, [r11+38h]
0x1401ff1b5  mov     rdi, [r11+40h]
0x1401ff1b9  mov     rsp, r11
0x1401ff1bc  pop     r15
0x1401ff1be  pop     r14
0x1401ff1c0  pop     r13
0x1401ff1c2  pop     r12
0x1401ff1c4  pop     rbp
0x1401ff1c5  retn
```
