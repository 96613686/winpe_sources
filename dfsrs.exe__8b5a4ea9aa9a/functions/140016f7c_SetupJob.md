# SetupJob

- ea: `0x140016f7c`
- end: `0x140017234`
- name: `SetupJob`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140015408`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000cdc0`
- `0x14000e34c`
- `0x140012440`
- `0x140016f7c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CreateJobObjectW` at `0x140016fa0`
- `KERNEL32!CreateJobObjectW` at `0x140016fa0`
- `KERNEL32!SetInformationJobObject` at `0x14001707f`
- `KERNEL32!SetInformationJobObject` at `0x14001707f`
- `KERNEL32!AssignProcessToJobObject` at `0x140017139`
- `KERNEL32!AssignProcessToJobObject` at `0x140017139`
- `KERNEL32!GetCurrentProcess` at `0x140017127`
- `KERNEL32!GetCurrentProcess` at `0x140017127`
- `KERNEL32!GetLastError` at `0x140016fcb`
- `KERNEL32!GetLastError` at `0x1400170a1`
- `KERNEL32!GetLastError` at `0x14001715b`
- `KERNEL32!GetLastError` at `0x140016fcb`
- `KERNEL32!GetLastError` at `0x1400170a1`
- `KERNEL32!GetLastError` at `0x14001715b`
- `KERNEL32!GetCurrentThreadId` at `0x140016fbd`
- `KERNEL32!GetCurrentThreadId` at `0x140017093`
- `KERNEL32!GetCurrentThreadId` at `0x14001714d`
- `KERNEL32!GetCurrentThreadId` at `0x140016fbd`
- `KERNEL32!GetCurrentThreadId` at `0x140017093`
- `KERNEL32!GetCurrentThreadId` at `0x14001714d`

## string_xrefs

- `0x140017045`: `Failed CreateJobObject. Err:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SetupJob()
{
  HANDLE JobObjectW; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  struct FrsStatus *v3; // r8
  const wchar_t *v4; // rdx
  DWORD v5; // ebx
  DWORD v6; // eax
  HANDLE CurrentProcess; // rax
  DWORD v8; // ebx
  DWORD v9; // eax
  const wchar_t *v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v14; // [rsp+60h] [rbp-A0h]
  struct FrsStatus *v15; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v16[2]; // [rsp+70h] [rbp-90h] BYREF
  int JobObjectInformation; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[12]; // [rsp+84h] [rbp-7Ch] BYREF
  int v19; // [rsp+90h] [rbp-70h]

  JobObjectW = CreateJobObjectW(0, 0);
  v16[0] = JobObjectW;
  if ( !JobObjectW )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                               "SetupJob",
                               185,
                               CurrentThreadId,
                               0);
    v15 = v3;
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 3 )
      goto LABEL_17;
    v12 = 186;
    v4 = L"Failed CreateJobObject. Err:%?";
    goto LABEL_16;
  }
  JobObjectInformation = 0;
  memset_0(v18, 0, 0x8Cu);
  v19 = 0x2000;
  if ( !SetInformationJobObject(JobObjectW, JobObjectExtendedLimitInformation, &JobObjectInformation, 0x90u) )
  {
    v5 = GetCurrentThreadId();
    v6 = GetLastError();
    v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                               v6,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                               "SetupJob",
                               195,
                               v5,
                               0);
    v15 = v3;
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 3 )
      goto LABEL_17;
    v12 = 196;
    v4 = L"Failed SetInformationJobObject. Err:%?";
    goto LABEL_16;
  }
  CurrentProcess = GetCurrentProcess();
  if ( AssignProcessToJobObject(JobObjectW, CurrentProcess) )
  {
    v16[0] = 0;
    return scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>(v16);
  }
  v8 = GetCurrentThreadId();
  v9 = GetLastError();
  v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                             "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                             v9,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                             "SetupJob",
                             202,
                             v8,
                             0);
  v15 = v3;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
  {
    v12 = 203;
    v4 = L"Failed AssignProcessToJobObject. Err:%?";
LABEL_16:
    v11 = L"SetupJob";
    v13 = 3;
    v14 = L"MAIN";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v11, v4, v3);
  }
LABEL_17:
  CLEAR_ERROR(&v15);
  return scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>(v16);
}

```

## disassembly

```asm
0x140016f7c  mov     [rsp-8+arg_0], rbx
0x140016f81  push    rbp
0x140016f82  lea     rbp, [rsp-20h]
0x140016f87  sub     rsp, 120h
0x140016f8e  mov     rax, cs:__security_cookie
0x140016f95  xor     rax, rsp
0x140016f98  mov     [rbp+20h+var_10], rax
0x140016f9c  xor     edx, edx; lpName
0x140016f9e  xor     ecx, ecx; lpJobAttributes
0x140016fa0  call    cs:__imp_CreateJobObjectW
0x140016fa7  nop     dword ptr [rax+rax+00h]
0x140016fac  mov     rbx, rax
0x140016faf  mov     [rsp+120h+var_B0], rax
0x140016fb4  test    rax, rax
0x140016fb7  jnz     loc_140017051
0x140016fbd  call    cs:__imp_GetCurrentThreadId
0x140016fc4  nop     dword ptr [rax+rax+00h]
0x140016fc9  mov     ebx, eax
0x140016fcb  call    cs:__imp_GetLastError
0x140016fd2  nop     dword ptr [rax+rax+00h]
0x140016fd7  and     [rsp+120h+var_E0], 0
0x140016fdd  mov     [rsp+120h+var_E8], ebx
0x140016fe1  mov     [rsp+120h+var_F0], 0B9h
0x140016fe9  lea     rcx, aSetupjob_0; "SetupJob"
0x140016ff0  mov     [rsp+120h+var_F8], rcx
0x140016ff5  lea     rcx, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x140016ffc  mov     [rsp+120h+var_100], rcx
0x140017001  mov     r9d, 1
0x140017007  xor     r8d, r8d
0x14001700a  mov     edx, eax
0x14001700c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140017011  mov     r8, rax
0x140017014  mov     [rsp+120h+var_B8], rax
0x140017019  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140017020  test    rcx, rcx
0x140017023  jz      loc_1400171FA
0x140017029  cmp     dword ptr [rcx+40h], 0
0x14001702d  jz      loc_1400171FA
0x140017033  cmp     dword ptr [rcx+38h], 3
0x140017037  jl      loc_1400171FA
0x14001703d  mov     [rsp+120h+var_C8], 0BAh
0x140017045  lea     rdx, aFailedCreatejo; "Failed CreateJobObject. Err:%?"
0x14001704c  jmp     loc_1400171D0
0x140017051  and     [rbp+20h+JobObjectInformation], 0
0x140017055  xor     edx, edx; Val
0x140017057  mov     r8d, 8Ch; Size
0x14001705d  lea     rcx, [rbp+20h+var_9C]; void *
0x140017061  call    memset_0
0x140017066  mov     [rbp+20h+var_90], 2000h
0x14001706d  mov     r9d, 90h; cbJobObjectInformationLength
0x140017073  lea     r8, [rbp+20h+JobObjectInformation]; lpJobObjectInformation
0x140017077  mov     edx, 9; JobObjectInformationClass
0x14001707c  mov     rcx, rbx; hJob
0x14001707f  call    cs:__imp_SetInformationJobObject
0x140017086  nop     dword ptr [rax+rax+00h]
0x14001708b  test    eax, eax
0x14001708d  jnz     loc_140017127
0x140017093  call    cs:__imp_GetCurrentThreadId
0x14001709a  nop     dword ptr [rax+rax+00h]
0x14001709f  mov     ebx, eax
0x1400170a1  call    cs:__imp_GetLastError
0x1400170a8  nop     dword ptr [rax+rax+00h]
0x1400170ad  and     [rsp+120h+var_E0], 0
0x1400170b3  mov     [rsp+120h+var_E8], ebx
0x1400170b7  mov     [rsp+120h+var_F0], 0C3h
0x1400170bf  lea     rcx, aSetupjob_0; "SetupJob"
0x1400170c6  mov     [rsp+120h+var_F8], rcx
0x1400170cb  lea     rcx, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x1400170d2  mov     [rsp+120h+var_100], rcx
0x1400170d7  mov     r9d, 1
0x1400170dd  xor     r8d, r8d
0x1400170e0  mov     edx, eax
0x1400170e2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400170e7  mov     r8, rax
0x1400170ea  mov     [rsp+120h+var_B8], rax
0x1400170ef  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400170f6  test    rcx, rcx
0x1400170f9  jz      loc_1400171FA
0x1400170ff  cmp     dword ptr [rcx+40h], 0
0x140017103  jz      loc_1400171FA
0x140017109  cmp     dword ptr [rcx+38h], 3
0x14001710d  jl      loc_1400171FA
0x140017113  mov     [rsp+120h+var_C8], 0C4h
0x14001711b  lea     rdx, aFailedSetinfor; "Failed SetInformationJobObject. Err:%?"
0x140017122  jmp     loc_1400171D0
0x140017127  call    cs:__imp_GetCurrentProcess
0x14001712e  nop     dword ptr [rax+rax+00h]
0x140017133  mov     rdx, rax; hProcess
0x140017136  mov     rcx, rbx; hJob
0x140017139  call    cs:__imp_AssignProcessToJobObject
0x140017140  nop     dword ptr [rax+rax+00h]
0x140017145  test    eax, eax
0x140017147  jnz     loc_140017206
0x14001714d  call    cs:__imp_GetCurrentThreadId
0x140017154  nop     dword ptr [rax+rax+00h]
0x140017159  mov     ebx, eax
0x14001715b  call    cs:__imp_GetLastError
0x140017162  nop     dword ptr [rax+rax+00h]
0x140017167  and     [rsp+120h+var_E0], 0
0x14001716d  mov     [rsp+120h+var_E8], ebx
0x140017171  mov     [rsp+120h+var_F0], 0CAh
0x140017179  lea     rcx, aSetupjob_0; "SetupJob"
0x140017180  mov     [rsp+120h+var_F8], rcx
0x140017185  lea     rcx, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x14001718c  mov     [rsp+120h+var_100], rcx
0x140017191  mov     r9d, 1
0x140017197  xor     r8d, r8d
0x14001719a  mov     edx, eax
0x14001719c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400171a1  mov     r8, rax
0x1400171a4  mov     [rsp+120h+var_B8], rax
0x1400171a9  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400171b0  test    rcx, rcx
0x1400171b3  jz      short loc_1400171FA
0x1400171b5  cmp     dword ptr [rcx+40h], 0
0x1400171b9  jz      short loc_1400171FA
0x1400171bb  cmp     dword ptr [rcx+38h], 3
0x1400171bf  jl      short loc_1400171FA
0x1400171c1  mov     [rsp+120h+var_C8], 0CBh
0x1400171c9  lea     rdx, aFailedAssignpr; "Failed AssignProcessToJobObject. Err:%?"
0x1400171d0  lea     rcx, aSetupjob; "SetupJob"
0x1400171d7  lea     rax, aMain_1; "MAIN"
0x1400171de  mov     [rsp+120h+var_D0], rcx
0x1400171e3  mov     [rsp+120h+var_C4], 3
0x1400171eb  mov     [rsp+120h+var_C0], rax
0x1400171f0  lea     rcx, [rsp+120h+var_D0]
0x1400171f5  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400171fa  lea     rcx, [rsp+120h+var_B8]; struct FrsStatus **
0x1400171ff  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140017204  jmp     short loc_14001720C
0x140017206  and     [rsp+120h+var_B0], 0
0x14001720c  lea     rcx, [rsp+120h+var_B0]
0x140017211  call    ??1?$scoped_any@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@Unull_t@@$03@@QEAA@XZ; scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>(void)
0x140017216  mov     rcx, [rbp+20h+var_10]
0x14001721a  xor     rcx, rsp; StackCookie
0x14001721d  call    __security_check_cookie
0x140017222  mov     rbx, [rsp+120h+arg_0]
0x14001722a  add     rsp, 120h
0x140017231  pop     rbp
0x140017232  retn
```
