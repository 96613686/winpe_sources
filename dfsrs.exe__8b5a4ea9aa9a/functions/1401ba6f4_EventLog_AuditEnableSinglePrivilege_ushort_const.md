# EventLog::AuditEnableSinglePrivilege(ushort const *)

- ea: `0x1401ba6f4`
- end: `0x1401ba8c6`
- name: `?AuditEnableSinglePrivilege@EventLog@@AEAAPEAVFrsStatus@@PEBG@Z`
- size: `466`
- prototype: `struct FrsStatus *__fastcall(EventLog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1401bcb60`

## callees

- `0x1400036a0`
- `0x140012440`
- `0x1401b9494`
- `0x1401ba6f4`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1401ba72e`
- `KERNEL32!GetCurrentProcess` at `0x1401ba72e`
- `KERNEL32!GetLastError` at `0x1401ba771`
- `KERNEL32!GetLastError` at `0x1401ba7e1`
- `KERNEL32!GetLastError` at `0x1401ba85d`
- `KERNEL32!GetLastError` at `0x1401ba771`
- `KERNEL32!GetLastError` at `0x1401ba7e1`
- `KERNEL32!GetLastError` at `0x1401ba85d`
- `KERNEL32!GetCurrentThreadId` at `0x1401ba763`
- `KERNEL32!GetCurrentThreadId` at `0x1401ba7d3`
- `KERNEL32!GetCurrentThreadId` at `0x1401ba84f`
- `KERNEL32!GetCurrentThreadId` at `0x1401ba763`
- `KERNEL32!GetCurrentThreadId` at `0x1401ba7d3`
- `KERNEL32!GetCurrentThreadId` at `0x1401ba84f`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1401ba83f`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1401ba83f`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1401ba7c3`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1401ba7c3`
- `ADVAPI32!OpenProcessToken` at `0x1401ba745`
- `ADVAPI32!OpenProcessToken` at `0x1401ba745`

## string_xrefs

- `0x1401ba7ba`: `SeAuditPrivilege`
- `0x1401ba751`: `EventLog::AuditEnableSinglePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall EventLog::AuditEnableSinglePrivilege(EventLog *this, const unsigned __int16 *a2)
{
  __int64 v2; // rbx
  HANDLE CurrentProcess; // rax
  DWORD v4; // ebx
  DWORD v5; // eax
  __int64 v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  __int64 v9; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v12; // rcx
  void *TokenHandle; // [rsp+50h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+58h] [rbp-20h] BYREF

  v2 = 0;
  NewState.Privileges[0].Luid = 0;
  TokenHandle = 0;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    || (v4 = GetCurrentThreadId(),
        v5 = GetLastError(),
        (v2 = FrsStatusList::PushNewError(
                v6,
                v5,
                0,
                1,
                &PreviousState,
                "EventLog::AuditEnableSinglePrivilege",
                1491,
                v4,
                0)) == 0) )
  {
    if ( LookupPrivilegeValueW(0, L"SeAuditPrivilege", &NewState.Privileges[0].Luid)
      || (v7 = GetCurrentThreadId(),
          v8 = GetLastError(),
          (v2 = FrsStatusList::PushNewError(
                  v9,
                  v8,
                  0,
                  1,
                  &PreviousState,
                  "EventLog::AuditEnableSinglePrivilege",
                  1500,
                  v7,
                  0)) == 0) )
    {
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        v2 = FrsStatusList::PushNewError(
               v12,
               LastError,
               0,
               1,
               &PreviousState,
               "EventLog::AuditEnableSinglePrivilege",
               1512,
               CurrentThreadId,
               0);
      }
    }
  }
  scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>(&TokenHandle);
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x1401ba6f4  mov     r11, rsp
0x1401ba6f7  mov     [r11+8], rbx
0x1401ba6fb  mov     [r11+10h], rbp
0x1401ba6ff  push    r14
0x1401ba701  sub     rsp, 70h
0x1401ba705  mov     rax, cs:__security_cookie
0x1401ba70c  xor     rax, rsp
0x1401ba70f  mov     [rsp+78h+var_10], rax
0x1401ba714  xor     ebx, ebx
0x1401ba716  and     [r11-1Ch], rbx
0x1401ba71a  and     [r11-28h], rbx
0x1401ba71e  mov     [rsp+78h+NewState.PrivilegeCount], 1
0x1401ba726  mov     [rsp+78h+NewState.Privileges.Attributes], 2
0x1401ba72e  call    cs:__imp_GetCurrentProcess
0x1401ba735  nop     dword ptr [rax+rax+00h]
0x1401ba73a  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x1401ba73f  lea     edx, [rbx+28h]; DesiredAccess
0x1401ba742  mov     rcx, rax; ProcessHandle
0x1401ba745  call    cs:__imp_OpenProcessToken
0x1401ba74c  nop     dword ptr [rax+rax+00h]
0x1401ba751  lea     rbp, ReturnLength; "EventLog::AuditEnableSinglePrivilege"
0x1401ba758  lea     r14, PreviousState
0x1401ba75f  test    eax, eax
0x1401ba761  jnz     short loc_1401BA7B5
0x1401ba763  call    cs:__imp_GetCurrentThreadId
0x1401ba76a  nop     dword ptr [rax+rax+00h]
0x1401ba76f  mov     ebx, eax
0x1401ba771  call    cs:__imp_GetLastError
0x1401ba778  nop     dword ptr [rax+rax+00h]
0x1401ba77d  and     [rsp+78h+var_38], 0
0x1401ba783  mov     [rsp+78h+var_40], ebx
0x1401ba787  mov     [rsp+78h+var_48], 5D3h
0x1401ba78f  mov     [rsp+78h+ReturnLength], rbp
0x1401ba794  mov     [rsp+78h+PreviousState], r14
0x1401ba799  mov     r9d, 1
0x1401ba79f  xor     r8d, r8d
0x1401ba7a2  mov     edx, eax
0x1401ba7a4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ba7a9  mov     rbx, rax
0x1401ba7ac  test    rax, rax
0x1401ba7af  jnz     loc_1401BA898
0x1401ba7b5  lea     r8, [rsp+78h+NewState.Privileges]; lpLuid
0x1401ba7ba  lea     rdx, Name; "SeAuditPrivilege"
0x1401ba7c1  xor     ecx, ecx; lpSystemName
0x1401ba7c3  call    cs:__imp_LookupPrivilegeValueW
0x1401ba7ca  nop     dword ptr [rax+rax+00h]
0x1401ba7cf  test    eax, eax
0x1401ba7d1  jnz     short loc_1401BA821
0x1401ba7d3  call    cs:__imp_GetCurrentThreadId
0x1401ba7da  nop     dword ptr [rax+rax+00h]
0x1401ba7df  mov     ebx, eax
0x1401ba7e1  call    cs:__imp_GetLastError
0x1401ba7e8  nop     dword ptr [rax+rax+00h]
0x1401ba7ed  and     [rsp+78h+var_38], 0
0x1401ba7f3  mov     [rsp+78h+var_40], ebx
0x1401ba7f7  mov     [rsp+78h+var_48], 5DCh
0x1401ba7ff  mov     [rsp+78h+ReturnLength], rbp; ReturnLength
0x1401ba804  mov     [rsp+78h+PreviousState], r14; PreviousState
0x1401ba809  mov     r9d, 1
0x1401ba80f  xor     r8d, r8d
0x1401ba812  mov     edx, eax
0x1401ba814  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ba819  mov     rbx, rax
0x1401ba81c  test    rax, rax
0x1401ba81f  jnz     short loc_1401BA898
0x1401ba821  and     [rsp+78h+ReturnLength], 0
0x1401ba827  and     [rsp+78h+PreviousState], 0
0x1401ba82d  mov     r9d, 10h; BufferLength
0x1401ba833  lea     r8, [rsp+78h+NewState]; NewState
0x1401ba838  xor     edx, edx; DisableAllPrivileges
0x1401ba83a  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x1401ba83f  call    cs:__imp_AdjustTokenPrivileges
0x1401ba846  nop     dword ptr [rax+rax+00h]
0x1401ba84b  test    eax, eax
0x1401ba84d  jnz     short loc_1401BA898
0x1401ba84f  call    cs:__imp_GetCurrentThreadId
0x1401ba856  nop     dword ptr [rax+rax+00h]
0x1401ba85b  mov     ebx, eax
0x1401ba85d  call    cs:__imp_GetLastError
0x1401ba864  nop     dword ptr [rax+rax+00h]
0x1401ba869  and     [rsp+78h+var_38], 0
0x1401ba86f  mov     [rsp+78h+var_40], ebx
0x1401ba873  mov     [rsp+78h+var_48], 5E8h
0x1401ba87b  mov     [rsp+78h+ReturnLength], rbp
0x1401ba880  mov     [rsp+78h+PreviousState], r14
0x1401ba885  mov     r9d, 1
0x1401ba88b  xor     r8d, r8d
0x1401ba88e  mov     edx, eax
0x1401ba890  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ba895  mov     rbx, rax
0x1401ba898  lea     rcx, [rsp+78h+TokenHandle]
0x1401ba89d  call    ??1?$scoped_any@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@Unull_t@@$03@@QEAA@XZ; scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>(void)
0x1401ba8a2  mov     rax, rbx
0x1401ba8a5  mov     rcx, [rsp+78h+var_10]
0x1401ba8aa  xor     rcx, rsp; StackCookie
0x1401ba8ad  call    __security_check_cookie
0x1401ba8b2  lea     r11, [rsp+78h+var_8]
0x1401ba8b7  mov     rbx, [r11+10h]
0x1401ba8bb  mov     rbp, [r11+18h]
0x1401ba8bf  mov     rsp, r11
0x1401ba8c2  pop     r14
0x1401ba8c4  retn
```
