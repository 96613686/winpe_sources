# CGPNotification::NotifyThread(_POLICYCHANGEDINFO *)

- ea: `0x180093e90`
- end: `0x18009441e`
- name: `?NotifyThread@CGPNotification@@CAKPEAU_POLICYCHANGEDINFO@@@Z`
- size: `1422`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x180075ec0`
- `0x18009362c`
- `0x180093e90`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180094417`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180094417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009428b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009428b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800943f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800943f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009440c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009440c`
- `ntdll!RtlPublishWnfStateData` at `0x180094331`
- `ntdll!RtlPublishWnfStateData` at `0x180094331`
- `ntdll!RtlAdjustPrivilege` at `0x180093faa`
- `ntdll!RtlAdjustPrivilege` at `0x180094345`
- `ntdll!RtlAdjustPrivilege` at `0x180093faa`
- `ntdll!RtlAdjustPrivilege` at `0x180094345`
- `WINSTA!WinStationBroadcastSystemMessage` at `0x1800940ee`
- `WINSTA!WinStationBroadcastSystemMessage` at `0x18009422a`
- `WINSTA!WinStationBroadcastSystemMessage` at `0x1800940ee`
- `WINSTA!WinStationBroadcastSystemMessage` at `0x18009422a`
- `USER32!BroadcastSystemMessageExW` at `0x180093fec`
- `USER32!BroadcastSystemMessageExW` at `0x180093fec`

## string_xrefs

- `0x1800943b3`: `Failed to update privileges with 0x%x.`
- `0x1800943dc`: `Failed to update privileges with 0x%x.`
- `0x180094360`: `PolicyChangedThread: Leaving`
- `0x180094385`: `PolicyChangedThread: Leaving`

## pseudocode

```c
void __fastcall __noreturn CGPNotification::NotifyThread(unsigned int *Parameter)
{
  __int64 v1; // r8
  HMODULE v2; // r12
  unsigned int v4; // edi
  unsigned int v5; // eax
  NTSTATUS v6; // eax
  int v7; // esi
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD LastError; // eax
  DWORD v10; // eax
  int v11; // esi
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v13; // eax
  DWORD v14; // eax
  unsigned int i; // edi
  __int64 v16; // r8
  int v17; // r14d
  void (*v18)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v19; // eax
  DWORD v20; // eax
  __int64 v21; // rcx
  DWORD v22; // edi
  unsigned __int8 OldValue; // [rsp+90h] [rbp+40h] BYREF
  DWORD Info; // [rsp+98h] [rbp+48h] BYREF
  int v25; // [rsp+A0h] [rbp+50h] BYREF

  v1 = Parameter[2];
  v2 = (HMODULE)*((_QWORD *)Parameter + 4);
  OldValue = 0;
  v25 = 0;
  if ( !(_DWORD)v1 )
  {
    v4 = 0;
    if ( Parameter[6] )
    {
      do
      {
        v5 = LaunchUserProcessInSession(
               (unsigned __int16 *)Parameter,
               *(_DWORD *)(*((_QWORD *)Parameter + 2) + 4LL * v4),
               *(void **)Parameter);
        if ( v5 && *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"Failed to launch user process in session = %d. Status = 0x%x",
              *(unsigned int *)(*((_QWORD *)Parameter + 2) + 4LL * v4),
              v5);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"Failed to launch user process in session = %d. Status = 0x%x",
              *(unsigned int *)(*((_QWORD *)Parameter + 2) + 4LL * v4),
              v5);
          }
        }
        ++v4;
      }
      while ( v4 < Parameter[6] );
      v1 = Parameter[2];
    }
    else
    {
      v1 = 0;
    }
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Broadcast message for %d.", v1);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Broadcast message for %d.", v1);
    }
  }
  v6 = RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  if ( v6 < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to update privileges with 0x%x.", (unsigned int)v6);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to update privileges with 0x%x.", (unsigned int)v6);
      }
    }
    v22 = 5;
  }
  else
  {
    if ( Parameter[2] )
    {
      Info = 24;
      v7 = BroadcastSystemMessageExW(0x22u, &Info, 0x1Au, 1u, (LPARAM)L"Policy", 0);
      if ( v7 > 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Machine Broadcast Sent successfully to session 0");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Machine Broadcast Sent successfully to session 0");
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v8 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          v8(2u, L"Machine Broadcast to session 0 failed with %d, Error %d", (unsigned int)v7, LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v10 = GetLastError();
          RedirectDebugMsg(2u, L"Machine Broadcast to session 0 failed with %d, Error %d", (unsigned int)v7, v10);
        }
      }
      Info = 24;
      v11 = WinStationBroadcastSystemMessage(0, 1, 0, 10, 34, &Info, 26, 1, L"Policy", &v25);
      if ( v11 > 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Machine Broadcast Sent successfully to all user sessions");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Machine Broadcast Sent successfully to all user sessions");
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v12 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v13 = GetLastError();
          v12(2u, L"Machine Broadcast to user sessions failed with %d, Error %d", (unsigned int)v11, v13);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v14 = GetLastError();
          RedirectDebugMsg(2u, L"Machine Broadcast to user sessions failed with %d, Error %d", (unsigned int)v11, v14);
        }
      }
    }
    else
    {
      for ( i = 0; i < Parameter[6]; ++i )
      {
        v16 = *((_QWORD *)Parameter + 2);
        Info = 24;
        v17 = WinStationBroadcastSystemMessage(
                0,
                0,
                *(unsigned int *)(v16 + 4LL * i),
                10,
                34,
                &Info,
                26,
                0,
                L"Policy",
                &v25);
        if ( v17 > 0 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                4u,
                L"User Broadcast Sent successfully to session %d",
                *(unsigned int *)(*((_QWORD *)Parameter + 2) + 4LL * i));
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"User Broadcast Sent successfully to session %d",
                *(unsigned int *)(*((_QWORD *)Parameter + 2) + 4LL * i));
            }
          }
        }
        else if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v18 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v19 = GetLastError();
            v18(2u, L"User Broadcast failed with %d, Error %d", (unsigned int)v17, v19);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v20 = GetLastError();
            RedirectDebugMsg(2u, L"User Broadcast failed with %d, Error %d", (unsigned int)v17, v20);
          }
        }
      }
    }
    v21 = WNF_GPOL_SYSTEM_CHANGES;
    if ( !Parameter[2] )
      v21 = WNF_GPOL_USER_CHANGES;
    RtlPublishWnfStateData(v21, 0, 0, 0, 0);
    RtlAdjustPrivilege(7u, OldValue, 0, &OldValue);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"PolicyChangedThread: Leaving");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"PolicyChangedThread: Leaving");
      }
    }
    v22 = 0;
  }
  if ( !Parameter[2] )
    CloseHandle(*(HANDLE *)Parameter);
  LocalFree(*((HLOCAL *)Parameter + 2));
  LocalFree(Parameter);
  FreeLibraryAndExitThread(v2, v22);
}

```

## disassembly

```asm
0x180093e90  mov     [rsp-38h+arg_18], rbx
0x180093e95  push    rbp
0x180093e96  push    rsi
0x180093e97  push    rdi
0x180093e98  push    r12
0x180093e9a  push    r13
0x180093e9c  push    r14
0x180093e9e  push    r15
0x180093ea0  mov     rbp, rsp
0x180093ea3  sub     rsp, 50h
0x180093ea7  mov     r8d, [rcx+8]
0x180093eab  xor     r13d, r13d
0x180093eae  mov     r12, [rcx+20h]
0x180093eb2  mov     rbx, rcx
0x180093eb5  mov     [rbp+OldValue], r13b
0x180093eb9  mov     [rbp+arg_10], r13d
0x180093ebd  lea     r14d, [r13+2]
0x180093ec1  test    r8d, r8d
0x180093ec4  jnz     loc_180093F52
0x180093eca  mov     edi, r13d
0x180093ecd  cmp     [rcx+18h], r13d
0x180093ed1  jbe     short loc_180093F4F
0x180093ed3  mov     rdx, [rbx+10h]
0x180093ed7  mov     r8, [rbx]; void *
0x180093eda  mov     esi, edi
0x180093edc  mov     edx, [rdx+rsi*4]; unsigned int
0x180093edf  call    ?LaunchUserProcessInSession@@YAKPEBGKPEAX@Z; LaunchUserProcessInSession(ushort const *,ulong,void *)
0x180093ee4  mov     r9d, eax
0x180093ee7  test    eax, eax
0x180093ee9  jz      short loc_180093F42
0x180093eeb  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180093ef2  jz      short loc_180093F42
0x180093ef4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093efb  test    rax, rax
0x180093efe  jz      short loc_180093F19
0x180093f00  mov     r8, [rbx+10h]
0x180093f04  lea     rdx, aFailedToLaunch; "Failed to launch user process in sessio"...
0x180093f0b  mov     ecx, r14d
0x180093f0e  mov     r8d, [r8+rsi*4]
0x180093f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f17  jmp     short loc_180093F42
0x180093f19  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180093f20  jz      short loc_180093F42
0x180093f22  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093f29  jz      short loc_180093F42
0x180093f2b  mov     r8, [rbx+10h]
0x180093f2f  lea     rdx, aFailedToLaunch; "Failed to launch user process in sessio"...
0x180093f36  mov     ecx, r14d; unsigned int
0x180093f39  mov     r8d, [r8+rsi*4]
0x180093f3d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093f42  inc     edi
0x180093f44  cmp     edi, [rbx+18h]
0x180093f47  jb      short loc_180093ED3
0x180093f49  mov     r8d, [rbx+8]
0x180093f4d  jmp     short loc_180093F52
0x180093f4f  mov     r8d, r13d
0x180093f52  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180093f59  jz      short loc_180093F9D
0x180093f5b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093f62  test    rax, rax
0x180093f65  jz      short loc_180093F7A
0x180093f67  lea     rdx, aBroadcastMessa; "Broadcast message for %d."
0x180093f6e  mov     ecx, 4
0x180093f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f78  jmp     short loc_180093F9D
0x180093f7a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180093f81  jz      short loc_180093F9D
0x180093f83  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093f8a  jz      short loc_180093F9D
0x180093f8c  lea     rdx, aBroadcastMessa; "Broadcast message for %d."
0x180093f93  mov     ecx, 4; unsigned int
0x180093f98  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093f9d  xor     r8d, r8d; ForThread
0x180093fa0  lea     r9, [rbp+OldValue]; OldValue
0x180093fa4  mov     dl, 1; NewValue
0x180093fa6  lea     ecx, [r8+7]; Privilege
0x180093faa  call    cs:__imp_RtlAdjustPrivilege
0x180093fb0  test    eax, eax
0x180093fb2  js      loc_18009439B
0x180093fb8  cmp     [rbx+8], r13d
0x180093fbc  jz      loc_1800941CF
0x180093fc2  mov     r9d, 1; wParam
0x180093fc8  mov     [rsp+50h+pbsmInfo], r13; pbsmInfo
0x180093fcd  lea     r15, lParam; "Policy"
0x180093fd4  mov     [rbp+Info], 18h
0x180093fdb  lea     rdx, [rbp+Info]; lpInfo
0x180093fdf  mov     [rsp+50h+lParam], r15; lParam
0x180093fe4  lea     r8d, [r9+19h]; Msg
0x180093fe8  lea     ecx, [r9+21h]; flags
0x180093fec  call    cs:__imp_BroadcastSystemMessageExW
0x180093ff2  mov     esi, eax
0x180093ff4  test    eax, eax
0x180093ff6  jg      short loc_180094060
0x180093ff8  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180093fff  jz      loc_1800940AB
0x180094005  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009400c  test    rdi, rdi
0x18009400f  jz      short loc_180094031
0x180094011  call    cs:__imp_GetLastError
0x180094017  mov     r8d, esi
0x18009401a  lea     rdx, aMachineBroadca; "Machine Broadcast to session 0 failed w"...
0x180094021  mov     r9d, eax
0x180094024  mov     ecx, r14d
0x180094027  mov     rax, rdi
0x18009402a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009402f  jmp     short loc_1800940AB
0x180094031  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180094038  jz      short loc_1800940AB
0x18009403a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180094041  jz      short loc_1800940AB
0x180094043  call    cs:__imp_GetLastError
0x180094049  mov     r8d, esi
0x18009404c  lea     rdx, aMachineBroadca; "Machine Broadcast to session 0 failed w"...
0x180094053  mov     r9d, eax
0x180094056  mov     ecx, r14d; unsigned int
0x180094059  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009405e  jmp     short loc_1800940AB
0x180094060  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180094067  jz      short loc_1800940AB
0x180094069  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180094070  test    rax, rax
0x180094073  jz      short loc_180094088
0x180094075  lea     rdx, aMachineBroadca_0; "Machine Broadcast Sent successfully to "...
0x18009407c  mov     ecx, 4
0x180094081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094086  jmp     short loc_1800940AB
0x180094088  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18009408f  jz      short loc_1800940AB
0x180094091  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180094098  jz      short loc_1800940AB
0x18009409a  lea     rdx, aMachineBroadca_0; "Machine Broadcast Sent successfully to "...
0x1800940a1  mov     ecx, 4; unsigned int
0x1800940a6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800940ab  mov     ecx, 1
0x1800940b0  mov     [rbp+Info], 18h
0x1800940b7  lea     rax, [rbp+arg_10]
0x1800940bb  mov     edx, ecx
0x1800940bd  mov     [rsp+50h+var_8], rax
0x1800940c2  xor     r8d, r8d
0x1800940c5  mov     [rsp+50h+var_10], r15
0x1800940ca  lea     rax, [rbp+Info]
0x1800940ce  mov     [rsp+50h+var_18], rcx
0x1800940d3  lea     r9d, [rcx+9]
0x1800940d7  mov     [rsp+50h+var_20], 1Ah
0x1800940df  xor     ecx, ecx
0x1800940e1  mov     [rsp+50h+pbsmInfo], rax
0x1800940e6  mov     dword ptr [rsp+50h+lParam], 22h ; '"'
0x1800940ee  call    cs:__imp_WinStationBroadcastSystemMessage
0x1800940f4  mov     esi, eax
0x1800940f6  test    eax, eax
0x1800940f8  jg      short loc_180094170
0x1800940fa  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180094101  jz      loc_180094310
0x180094107  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009410e  test    rdi, rdi
0x180094111  jz      short loc_180094136
0x180094113  call    cs:__imp_GetLastError
0x180094119  mov     r8d, esi
0x18009411c  lea     rdx, aMachineBroadca_1; "Machine Broadcast to user sessions fail"...
0x180094123  mov     r9d, eax
0x180094126  mov     ecx, r14d
0x180094129  mov     rax, rdi
0x18009412c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094131  jmp     loc_180094310
0x180094136  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18009413d  jz      loc_180094310
0x180094143  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009414a  jz      loc_180094310
0x180094150  call    cs:__imp_GetLastError
0x180094156  mov     r8d, esi
0x180094159  lea     rdx, aMachineBroadca_1; "Machine Broadcast to user sessions fail"...
0x180094160  mov     r9d, eax
0x180094163  mov     ecx, r14d; unsigned int
0x180094166  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009416b  jmp     loc_180094310
0x180094170  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180094177  jz      loc_180094310
0x18009417d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180094184  test    rax, rax
0x180094187  jz      short loc_18009419F
0x180094189  lea     rdx, aMachineBroadca_2; "Machine Broadcast Sent successfully to "...
0x180094190  mov     ecx, 4
0x180094195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009419a  jmp     loc_180094310
0x18009419f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800941a6  jz      loc_180094310
0x1800941ac  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800941b3  jz      loc_180094310
0x1800941b9  lea     rdx, aMachineBroadca_2; "Machine Broadcast Sent successfully to "...
0x1800941c0  mov     ecx, 4; unsigned int
0x1800941c5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800941ca  jmp     loc_180094310
0x1800941cf  mov     edi, r13d
0x1800941d2  cmp     [rbx+18h], r13d
0x1800941d6  jbe     loc_180094310
0x1800941dc  lea     r15, lParam; "Policy"
0x1800941e3  mov     r8, [rbx+10h]
0x1800941e7  lea     rax, [rbp+arg_10]
0x1800941eb  mov     [rsp+50h+var_8], rax
0x1800941f0  mov     r9d, 0Ah
0x1800941f6  mov     [rsp+50h+var_10], r15
0x1800941fb  lea     rax, [rbp+Info]
0x1800941ff  mov     [rsp+50h+var_18], r13
0x180094204  xor     edx, edx
0x180094206  mov     [rsp+50h+var_20], 1Ah
0x18009420e  xor     ecx, ecx
0x180094210  mov     [rbp+Info], 18h
0x180094217  mov     [rsp+50h+pbsmInfo], rax
0x18009421c  mov     esi, edi
0x18009421e  mov     dword ptr [rsp+50h+lParam], 22h ; '"'
0x180094226  mov     r8d, [r8+rsi*4]
0x18009422a  call    cs:__imp_WinStationBroadcastSystemMessage
0x180094230  mov     r14d, eax
0x180094233  test    eax, eax
0x180094235  jg      short loc_1800942AA
0x180094237  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18009423e  jz      loc_180094305
0x180094244  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009424b  test    rsi, rsi
0x18009424e  jz      short loc_180094275
0x180094250  call    cs:__imp_GetLastError
0x180094256  mov     r8d, r14d
0x180094259  lea     rdx, aUserBroadcastF; "User Broadcast failed with %d, Error %d"
0x180094260  mov     r9d, eax
0x180094263  mov     ecx, 2
0x180094268  mov     rax, rsi
0x18009426b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094270  jmp     loc_180094305
0x180094275  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18009427c  jz      loc_180094305
0x180094282  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180094289  jz      short loc_180094305
0x18009428b  call    cs:__imp_GetLastError
0x180094291  mov     r8d, r14d
0x180094294  lea     rdx, aUserBroadcastF; "User Broadcast failed with %d, Error %d"
0x18009429b  mov     r9d, eax
0x18009429e  mov     ecx, 2; unsigned int
0x1800942a3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800942a8  jmp     short loc_180094305
0x1800942aa  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800942b1  jz      short loc_180094305
0x1800942b3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800942ba  test    rax, rax
0x1800942bd  jz      short loc_1800942DA
0x1800942bf  mov     r8, [rbx+10h]
0x1800942c3  lea     rdx, aUserBroadcastS; "User Broadcast Sent successfully to ses"...
0x1800942ca  mov     ecx, 4
0x1800942cf  mov     r8d, [r8+rsi*4]
0x1800942d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942d8  jmp     short loc_180094305
0x1800942da  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800942e1  jz      short loc_180094305
0x1800942e3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800942ea  jz      short loc_180094305
0x1800942ec  mov     r8, [rbx+10h]
0x1800942f0  lea     rdx, aUserBroadcastS; "User Broadcast Sent successfully to ses"...
0x1800942f7  mov     ecx, 4; unsigned int
0x1800942fc  mov     r8d, [r8+rsi*4]
0x180094300  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180094305  inc     edi
0x180094307  cmp     edi, [rbx+18h]
0x18009430a  jb      loc_1800941E3
0x180094310  mov     rcx, cs:WNF_GPOL_SYSTEM_CHANGES
0x180094317  xor     r9d, r9d
0x18009431a  xor     r8d, r8d
0x18009431d  mov     [rsp+50h+lParam], r13
0x180094322  xor     edx, edx
0x180094324  cmp     [rbx+8], r13d
0x180094328  jnz     short loc_180094331
0x18009432a  mov     rcx, cs:WNF_GPOL_USER_CHANGES
0x180094331  call    cs:__imp_RtlPublishWnfStateData
0x180094337  mov     dl, [rbp+OldValue]; NewValue
0x18009433a  lea     r9, [rbp+OldValue]; OldValue
0x18009433e  xor     r8d, r8d; ForThread
0x180094341  lea     ecx, [r8+7]; Privilege
0x180094345  call    cs:__imp_RtlAdjustPrivilege
0x18009434b  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180094352  jz      short loc_180094396
0x180094354  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009435b  test    rax, rax
0x18009435e  jz      short loc_180094373
0x180094360  lea     rdx, aPolicychangedt; "PolicyChangedThread: Leaving"
0x180094367  mov     ecx, 4
0x18009436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094371  jmp     short loc_180094396
0x180094373  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18009437a  jz      short loc_180094396
0x18009437c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180094383  jz      short loc_180094396
0x180094385  lea     rdx, aPolicychangedt; "PolicyChangedThread: Leaving"
0x18009438c  mov     ecx, 4; unsigned int
0x180094391  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180094396  mov     edi, r13d
0x180094399  jmp     short loc_1800943F0
0x18009439b  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800943a2  jz      short loc_1800943EB
0x1800943a4  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800943ab  test    r9, r9
0x1800943ae  jz      short loc_1800943C7
0x1800943b0  mov     r8d, eax
  ... truncated ...
```
