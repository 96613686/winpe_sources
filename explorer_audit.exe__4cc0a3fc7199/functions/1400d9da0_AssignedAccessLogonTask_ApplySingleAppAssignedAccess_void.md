# AssignedAccessLogonTask::ApplySingleAppAssignedAccess(void)

- ea: `0x1400d9da0`
- end: `0x1400d9eb5`
- name: `?ApplySingleAppAssignedAccess@AssignedAccessLogonTask@@AEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(AssignedAccessLogonTask *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14001f2fc`

## callees

- `0x1400d9a74`
- `0x1400d9da0`
- `0x1400d9ebc`
- `0x1401b34e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400d9dce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400d9dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9e7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400d9db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400d9db1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1400d9dbe`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1400d9dbe`
- `USER32!LockWorkStation` at `0x1400d9dea`
- `USER32!LockWorkStation` at `0x1400d9dea`

## pseudocode

```c
__int64 __fastcall AssignedAccessLogonTask::ApplySingleAppAssignedAccess(AssignedAccessLogonTask *this)
{
  DWORD CurrentProcessId; // eax
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  __int64 v4; // rdx
  DWORD pSessionId; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+34h] [rbp+Ch]

  v7 = HIDWORD(this);
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
    {
      SessionChangeNotificationHandler::Start(pSessionId, ModuleHandleW);
      SessionChangeNotificationHandler::TurnOnLockScreenOverRemoteIfNeeded();
      if ( !LockWorkStation()
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v4 = 11;
LABEL_19:
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v4,
          &WPP_950c63c01e8d32baa84a78be8d346aba_Traceguids,
          (unsigned int)LastError);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v4 = 12;
      goto LABEL_19;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = 13;
    goto LABEL_19;
  }
  return 0;
}

```

## disassembly

```asm
0x1400d9da0  mov     qword ptr [rsp+pSessionId], rcx
0x1400d9da5  sub     rsp, 28h
0x1400d9da9  mov     [rsp+28h+pSessionId], 0
0x1400d9db1  call    cs:__imp_GetCurrentProcessId
0x1400d9db7  mov     ecx, eax; dwProcessId
0x1400d9db9  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x1400d9dbe  call    cs:__imp_ProcessIdToSessionId
0x1400d9dc4  test    eax, eax
0x1400d9dc6  jz      loc_1400D9E64
0x1400d9dcc  xor     ecx, ecx; lpModuleName
0x1400d9dce  call    cs:__imp_GetModuleHandleW
0x1400d9dd4  test    rax, rax
0x1400d9dd7  jz      short loc_1400D9E32
0x1400d9dd9  mov     ecx, [rsp+28h+pSessionId]; unsigned int
0x1400d9ddd  mov     rdx, rax; HINSTANCE
0x1400d9de0  call    ?Start@SessionChangeNotificationHandler@@SAJKPEAUHINSTANCE__@@@Z; SessionChangeNotificationHandler::Start(ulong,HINSTANCE__ *)
0x1400d9de5  call    ?TurnOnLockScreenOverRemoteIfNeeded@SessionChangeNotificationHandler@@SAXXZ; SessionChangeNotificationHandler::TurnOnLockScreenOverRemoteIfNeeded(void)
0x1400d9dea  call    cs:__imp_LockWorkStation
0x1400d9df0  test    eax, eax
0x1400d9df2  jnz     loc_1400D9EAE
0x1400d9df8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9dff  lea     rax, WPP_GLOBAL_Control
0x1400d9e06  cmp     rcx, rax
0x1400d9e09  jz      loc_1400D9EAE
0x1400d9e0f  test    byte ptr [rcx+1Ch], 2
0x1400d9e13  jz      loc_1400D9EAE
0x1400d9e19  call    cs:__imp_GetLastError
0x1400d9e1f  test    eax, eax
0x1400d9e21  jle     short loc_1400D9E2B
0x1400d9e23  movzx   eax, ax
0x1400d9e26  or      eax, 80070000h
0x1400d9e2b  mov     edx, 0Bh
0x1400d9e30  jmp     short loc_1400D9E94
0x1400d9e32  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9e39  lea     rax, WPP_GLOBAL_Control
0x1400d9e40  cmp     rcx, rax
0x1400d9e43  jz      short loc_1400D9EAE
0x1400d9e45  test    byte ptr [rcx+1Ch], 2
0x1400d9e49  jz      short loc_1400D9EAE
0x1400d9e4b  call    cs:__imp_GetLastError
0x1400d9e51  test    eax, eax
0x1400d9e53  jle     short loc_1400D9E5D
0x1400d9e55  movzx   eax, ax
0x1400d9e58  or      eax, 80070000h
0x1400d9e5d  mov     edx, 0Ch
0x1400d9e62  jmp     short loc_1400D9E94
0x1400d9e64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9e6b  lea     rax, WPP_GLOBAL_Control
0x1400d9e72  cmp     rcx, rax
0x1400d9e75  jz      short loc_1400D9EAE
0x1400d9e77  test    byte ptr [rcx+1Ch], 2
0x1400d9e7b  jz      short loc_1400D9EAE
0x1400d9e7d  call    cs:__imp_GetLastError
0x1400d9e83  test    eax, eax
0x1400d9e85  jle     short loc_1400D9E8F
0x1400d9e87  movzx   eax, ax
0x1400d9e8a  or      eax, 80070000h
0x1400d9e8f  mov     edx, 0Dh
0x1400d9e94  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9e9b  lea     r8, WPP_950c63c01e8d32baa84a78be8d346aba_Traceguids
0x1400d9ea2  mov     r9d, eax
0x1400d9ea5  mov     rcx, [rcx+10h]
0x1400d9ea9  call    WPP_SF_d
0x1400d9eae  xor     eax, eax
0x1400d9eb0  add     rsp, 28h
0x1400d9eb4  retn
```
