# AssignedAccessLogonTask::ApplySingleAppAssignedAccess(void)

- ea: `0x1400e150c`
- end: `0x1400e164c`
- name: `?ApplySingleAppAssignedAccess@AssignedAccessLogonTask@@AEAAJXZ`
- size: `320`
- prototype: `__int64 __fastcall(AssignedAccessLogonTask *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400821c8`

## callees

- `0x1400e1190`
- `0x1400e150c`
- `0x1400e1654`
- `0x1401b1838`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400e1546`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400e1546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e159d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e15d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e160d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e159d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e15d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e160d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1400e1530`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1400e1530`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400e151d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400e151d`
- `USER32!LockWorkStation` at `0x1400e1568`
- `USER32!LockWorkStation` at `0x1400e1568`

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
          WPP_950c63c01e8d32baa84a78be8d346aba_Traceguids,
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
0x1400e150c  mov     qword ptr [rsp+pSessionId], rcx
0x1400e1511  sub     rsp, 28h
0x1400e1515  mov     [rsp+28h+pSessionId], 0
0x1400e151d  call    cs:__imp_GetCurrentProcessId
0x1400e1524  nop     dword ptr [rax+rax+00h]
0x1400e1529  mov     ecx, eax; dwProcessId
0x1400e152b  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x1400e1530  call    cs:__imp_ProcessIdToSessionId
0x1400e1537  nop     dword ptr [rax+rax+00h]
0x1400e153c  test    eax, eax
0x1400e153e  jz      loc_1400E15F4
0x1400e1544  xor     ecx, ecx; lpModuleName
0x1400e1546  call    cs:__imp_GetModuleHandleW
0x1400e154d  nop     dword ptr [rax+rax+00h]
0x1400e1552  test    rax, rax
0x1400e1555  jz      short loc_1400E15BC
0x1400e1557  mov     ecx, [rsp+28h+pSessionId]; unsigned int
0x1400e155b  mov     rdx, rax; HINSTANCE
0x1400e155e  call    ?Start@SessionChangeNotificationHandler@@SAJKPEAUHINSTANCE__@@@Z; SessionChangeNotificationHandler::Start(ulong,HINSTANCE__ *)
0x1400e1563  call    ?TurnOnLockScreenOverRemoteIfNeeded@SessionChangeNotificationHandler@@SAXXZ; SessionChangeNotificationHandler::TurnOnLockScreenOverRemoteIfNeeded(void)
0x1400e1568  call    cs:__imp_LockWorkStation
0x1400e156f  nop     dword ptr [rax+rax+00h]
0x1400e1574  test    eax, eax
0x1400e1576  jnz     loc_1400E1644
0x1400e157c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e1583  lea     rax, WPP_GLOBAL_Control
0x1400e158a  cmp     rcx, rax
0x1400e158d  jz      loc_1400E1644
0x1400e1593  test    byte ptr [rcx+1Ch], 2
0x1400e1597  jz      loc_1400E1644
0x1400e159d  call    cs:__imp_GetLastError
0x1400e15a4  nop     dword ptr [rax+rax+00h]
0x1400e15a9  test    eax, eax
0x1400e15ab  jle     short loc_1400E15B5
0x1400e15ad  movzx   eax, ax
0x1400e15b0  or      eax, 80070000h
0x1400e15b5  mov     edx, 0Bh
0x1400e15ba  jmp     short loc_1400E162A
0x1400e15bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e15c3  lea     rax, WPP_GLOBAL_Control
0x1400e15ca  cmp     rcx, rax
0x1400e15cd  jz      short loc_1400E1644
0x1400e15cf  test    byte ptr [rcx+1Ch], 2
0x1400e15d3  jz      short loc_1400E1644
0x1400e15d5  call    cs:__imp_GetLastError
0x1400e15dc  nop     dword ptr [rax+rax+00h]
0x1400e15e1  test    eax, eax
0x1400e15e3  jle     short loc_1400E15ED
0x1400e15e5  movzx   eax, ax
0x1400e15e8  or      eax, 80070000h
0x1400e15ed  mov     edx, 0Ch
0x1400e15f2  jmp     short loc_1400E162A
0x1400e15f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e15fb  lea     rax, WPP_GLOBAL_Control
0x1400e1602  cmp     rcx, rax
0x1400e1605  jz      short loc_1400E1644
0x1400e1607  test    byte ptr [rcx+1Ch], 2
0x1400e160b  jz      short loc_1400E1644
0x1400e160d  call    cs:__imp_GetLastError
0x1400e1614  nop     dword ptr [rax+rax+00h]
0x1400e1619  test    eax, eax
0x1400e161b  jle     short loc_1400E1625
0x1400e161d  movzx   eax, ax
0x1400e1620  or      eax, 80070000h
0x1400e1625  mov     edx, 0Dh
0x1400e162a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e1631  lea     r8, WPP_950c63c01e8d32baa84a78be8d346aba_Traceguids
0x1400e1638  mov     r9d, eax
0x1400e163b  mov     rcx, [rcx+10h]
0x1400e163f  call    WPP_SF_d
0x1400e1644  xor     eax, eax
0x1400e1646  add     rsp, 28h
0x1400e164a  retn
```
