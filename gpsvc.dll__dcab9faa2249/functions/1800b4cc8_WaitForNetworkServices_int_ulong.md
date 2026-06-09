# WaitForNetworkServices(int,ulong)

- ea: `0x1800b4cc8`
- end: `0x1800b5107`
- name: `?WaitForNetworkServices@@YAKHK@Z`
- size: `1087`
- prototype: `unsigned int __fastcall(int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180091eec`

## callees

- `0x1800526e0`
- `0x180075ec0`
- `0x1800b42f8`
- `0x1800b44d8`
- `0x1800b49e0`
- `0x1800b4cc8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4de0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4de0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4e3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4e3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4e49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4e49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4ce7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4ef5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4fd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b505c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b50d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4ce7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4ef5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b4fd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b505c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800b50d8`

## string_xrefs

- `0x1800b4d9d`: `Waiting for NTDS.IndexRecreateEvent with timeout %d`
- `0x1800b4dc3`: `Waiting for NTDS.IndexRecreateEvent with timeout %d`
- `0x1800b4dd2`: `NTDS.IndexRecreateEvent`
- `0x1800b4e07`: `WaitForNetworkServices: Beginning WaitForSingleObject.`
- `0x1800b4e2a`: `WaitForNetworkServices: Beginning WaitForSingleObject.`
- `0x1800b4e6c`: `WaitForNetworkServices: Failed WaitForSingleObject.`
- `0x1800b4e9a`: `WaitForNetworkServices: Failed WaitForSingleObject.`
- `0x1800b4ec3`: `WaitForNetworkServices: Completed WaitForSingleObject.`
- `0x1800b4ee6`: `WaitForNetworkServices: Completed WaitForSingleObject.`

## pseudocode

```c
__int64 __fastcall WaitForNetworkServices(int a1, DWORD a2)
{
  DWORD TickCount; // edi
  DWORD v5; // ebx
  DWORD v6; // ebp
  DWORD v7; // ebx
  HANDLE v8; // rdi
  DWORD v9; // eax
  DWORD v10; // edx
  DWORD v11; // esi
  DWORD v12; // ebx
  DWORD v13; // edi
  DWORD v14; // ebx
  DWORD v15; // eax
  DWORD dwMilliseconds; // [rsp+58h] [rbp+10h] BYREF

  dwMilliseconds = a2;
  TickCount = GetTickCount();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Waiting for SamSs with timeout %d", a2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Waiting for SamSs with timeout %d", a2);
    }
  }
  if ( !(unsigned int)WaitForServiceToStart(L"SamSs", a2) )
    return 258;
  v6 = GetTickCount();
  v5 = CalculateTimeLeftToWait(TickCount, v6, &dwMilliseconds);
  if ( v5 )
    return v5;
  v7 = dwMilliseconds;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Waiting for NTDS.IndexRecreateEvent with timeout %d", dwMilliseconds);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Waiting for NTDS.IndexRecreateEvent with timeout %d", dwMilliseconds);
    }
  }
  v8 = OpenEventW(0x100000u, 0, L"NTDS.IndexRecreateEvent");
  if ( !v8 )
  {
LABEL_38:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Waiting for NETLOGON with timeout %d", v7);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Waiting for NETLOGON with timeout %d", v7);
      }
    }
    if ( (unsigned int)WaitForServiceToStart(L"NETLOGON", v7) )
    {
      v11 = GetTickCount();
      v5 = CalculateTimeLeftToWait(v6, v11, &dwMilliseconds);
      if ( v5 )
        return v5;
      v12 = dwMilliseconds;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Waiting for MUP with timeout %d", dwMilliseconds);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Waiting for MUP with timeout %d", dwMilliseconds);
        }
      }
      if ( (unsigned int)WaitForMUP(v12, a1) )
      {
        v13 = GetTickCount();
        v5 = CalculateTimeLeftToWait(v11, v13, &dwMilliseconds);
        if ( v5 )
          return v5;
        v14 = dwMilliseconds;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Waiting for DS with timeout %d", dwMilliseconds);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Waiting for DS with timeout %d", dwMilliseconds);
          }
        }
        if ( (unsigned int)WaitForDS(v14) )
        {
          v15 = GetTickCount();
          return CalculateTimeLeftToWait(v13, v15, &dwMilliseconds);
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Waiting for NETLOGON failed with timeout %d", v7);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Waiting for NETLOGON failed with timeout %d", v7);
      }
    }
    return 258;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"WaitForNetworkServices: Beginning WaitForSingleObject.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"WaitForNetworkServices: Beginning WaitForSingleObject.");
    }
  }
  v5 = WaitForSingleObject(v8, v7);
  CloseHandle(v8);
  if ( v5 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"WaitForNetworkServices: Failed WaitForSingleObject.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"WaitForNetworkServices: Failed WaitForSingleObject.");
      }
    }
    return v5;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"WaitForNetworkServices: Completed WaitForSingleObject.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"WaitForNetworkServices: Completed WaitForSingleObject.");
    }
  }
  v9 = GetTickCount();
  v5 = CalculateTimeLeftToWait(v6, v9, &dwMilliseconds);
  if ( !v5 )
  {
    v7 = dwMilliseconds;
    v6 = v10;
    goto LABEL_38;
  }
  return v5;
}

```

## disassembly

```asm
0x1800b4cc8  mov     [rsp+arg_0], rbx
0x1800b4ccd  mov     [rsp+arg_10], rbp
0x1800b4cd2  push    rsi
0x1800b4cd3  push    rdi
0x1800b4cd4  push    r12
0x1800b4cd6  push    r14
0x1800b4cd8  push    r15
0x1800b4cda  sub     rsp, 20h
0x1800b4cde  mov     ebx, edx
0x1800b4ce0  mov     [rsp+48h+dwMilliseconds], edx
0x1800b4ce4  mov     r14d, ecx
0x1800b4ce7  call    cs:__imp_GetTickCount
0x1800b4ced  xor     r15d, r15d
0x1800b4cf0  mov     r12d, 4
0x1800b4cf6  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4cfd  mov     edi, eax
0x1800b4cff  jz      short loc_1800B4D45
0x1800b4d01  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4d08  test    rax, rax
0x1800b4d0b  jz      short loc_1800B4D21
0x1800b4d0d  mov     r8d, ebx
0x1800b4d10  lea     rdx, aWaitingForSams; "Waiting for SamSs with timeout %d"
0x1800b4d17  mov     ecx, r12d
0x1800b4d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d1f  jmp     short loc_1800B4D45
0x1800b4d21  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4d28  jz      short loc_1800B4D45
0x1800b4d2a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4d31  jz      short loc_1800B4D45
0x1800b4d33  mov     r8d, ebx
0x1800b4d36  lea     rdx, aWaitingForSams; "Waiting for SamSs with timeout %d"
0x1800b4d3d  mov     ecx, r12d; unsigned int
0x1800b4d40  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4d45  mov     edx, ebx; unsigned int
0x1800b4d47  lea     rcx, ServiceName; "SamSs"
0x1800b4d4e  call    ?WaitForServiceToStart@@YAHPEBGK@Z; WaitForServiceToStart(ushort const *,ulong)
0x1800b4d53  test    eax, eax
0x1800b4d55  jnz     short loc_1800B4D61
0x1800b4d57  mov     ebx, 102h
0x1800b4d5c  jmp     loc_1800B50EE
0x1800b4d61  call    cs:__imp_GetTickCount
0x1800b4d67  lea     r8, [rsp+48h+dwMilliseconds]; unsigned int *
0x1800b4d6c  mov     ecx, edi; unsigned int
0x1800b4d6e  mov     edx, eax; unsigned int
0x1800b4d70  mov     ebp, eax
0x1800b4d72  call    ?CalculateTimeLeftToWait@@YAKKKPEAK@Z; CalculateTimeLeftToWait(ulong,ulong,ulong *)
0x1800b4d77  mov     ebx, eax
0x1800b4d79  test    eax, eax
0x1800b4d7b  jnz     loc_1800B50EE
0x1800b4d81  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4d88  mov     ebx, [rsp+48h+dwMilliseconds]
0x1800b4d8c  jz      short loc_1800B4DD2
0x1800b4d8e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4d95  test    rax, rax
0x1800b4d98  jz      short loc_1800B4DAE
0x1800b4d9a  mov     r8d, ebx
0x1800b4d9d  lea     rdx, aWaitingForNtds; "Waiting for NTDS.IndexRecreateEvent wit"...
0x1800b4da4  mov     ecx, r12d
0x1800b4da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4dac  jmp     short loc_1800B4DD2
0x1800b4dae  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4db5  jz      short loc_1800B4DD2
0x1800b4db7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4dbe  jz      short loc_1800B4DD2
0x1800b4dc0  mov     r8d, ebx
0x1800b4dc3  lea     rdx, aWaitingForNtds; "Waiting for NTDS.IndexRecreateEvent wit"...
0x1800b4dca  mov     ecx, r12d; unsigned int
0x1800b4dcd  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4dd2  lea     r8, aNtdsIndexrecre; "NTDS.IndexRecreateEvent"
0x1800b4dd9  xor     edx, edx; bInheritHandle
0x1800b4ddb  mov     ecx, 100000h; dwDesiredAccess
0x1800b4de0  call    cs:__imp_OpenEventW
0x1800b4de6  mov     rdi, rax
0x1800b4de9  test    rax, rax
0x1800b4dec  jz      loc_1800B4F19
0x1800b4df2  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4df9  jz      short loc_1800B4E39
0x1800b4dfb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4e02  test    rax, rax
0x1800b4e05  jz      short loc_1800B4E18
0x1800b4e07  lea     rdx, aWaitfornetwork_1; "WaitForNetworkServices: Beginning WaitF"...
0x1800b4e0e  mov     ecx, r12d
0x1800b4e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e16  jmp     short loc_1800B4E39
0x1800b4e18  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4e1f  jz      short loc_1800B4E39
0x1800b4e21  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4e28  jz      short loc_1800B4E39
0x1800b4e2a  lea     rdx, aWaitfornetwork_1; "WaitForNetworkServices: Beginning WaitF"...
0x1800b4e31  mov     ecx, r12d; unsigned int
0x1800b4e34  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4e39  mov     edx, ebx; dwMilliseconds
0x1800b4e3b  mov     rcx, rdi; hHandle
0x1800b4e3e  call    cs:__imp_WaitForSingleObject
0x1800b4e44  mov     rcx, rdi; hObject
0x1800b4e47  mov     ebx, eax
0x1800b4e49  call    cs:__imp_CloseHandle
0x1800b4e4f  test    ebx, ebx
0x1800b4e51  jz      short loc_1800B4EAE
0x1800b4e53  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4e5a  jz      loc_1800B50EE
0x1800b4e60  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4e67  test    rax, rax
0x1800b4e6a  jz      short loc_1800B4E80
0x1800b4e6c  lea     rdx, aWaitfornetwork_2; "WaitForNetworkServices: Failed WaitForS"...
0x1800b4e73  mov     ecx, r12d
0x1800b4e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e7b  jmp     loc_1800B50EE
0x1800b4e80  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4e87  jz      loc_1800B50EE
0x1800b4e8d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4e94  jz      loc_1800B50EE
0x1800b4e9a  lea     rdx, aWaitfornetwork_2; "WaitForNetworkServices: Failed WaitForS"...
0x1800b4ea1  mov     ecx, r12d; unsigned int
0x1800b4ea4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4ea9  jmp     loc_1800B50EE
0x1800b4eae  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4eb5  jz      short loc_1800B4EF5
0x1800b4eb7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4ebe  test    rax, rax
0x1800b4ec1  jz      short loc_1800B4ED4
0x1800b4ec3  lea     rdx, aWaitfornetwork; "WaitForNetworkServices: Completed WaitF"...
0x1800b4eca  mov     ecx, r12d
0x1800b4ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ed2  jmp     short loc_1800B4EF5
0x1800b4ed4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4edb  jz      short loc_1800B4EF5
0x1800b4edd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4ee4  jz      short loc_1800B4EF5
0x1800b4ee6  lea     rdx, aWaitfornetwork; "WaitForNetworkServices: Completed WaitF"...
0x1800b4eed  mov     ecx, r12d; unsigned int
0x1800b4ef0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4ef5  call    cs:__imp_GetTickCount
0x1800b4efb  lea     r8, [rsp+48h+dwMilliseconds]; unsigned int *
0x1800b4f00  mov     ecx, ebp; unsigned int
0x1800b4f02  mov     edx, eax; unsigned int
0x1800b4f04  call    ?CalculateTimeLeftToWait@@YAKKKPEAK@Z; CalculateTimeLeftToWait(ulong,ulong,ulong *)
0x1800b4f09  mov     ebx, eax
0x1800b4f0b  test    eax, eax
0x1800b4f0d  jnz     loc_1800B50EE
0x1800b4f13  mov     ebx, [rsp+48h+dwMilliseconds]
0x1800b4f17  mov     ebp, edx
0x1800b4f19  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4f20  jz      short loc_1800B4F66
0x1800b4f22  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4f29  test    rax, rax
0x1800b4f2c  jz      short loc_1800B4F42
0x1800b4f2e  mov     r8d, ebx
0x1800b4f31  lea     rdx, aWaitingForNetl; "Waiting for NETLOGON with timeout %d"
0x1800b4f38  mov     ecx, r12d
0x1800b4f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4f40  jmp     short loc_1800B4F66
0x1800b4f42  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4f49  jz      short loc_1800B4F66
0x1800b4f4b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4f52  jz      short loc_1800B4F66
0x1800b4f54  mov     r8d, ebx
0x1800b4f57  lea     rdx, aWaitingForNetl; "Waiting for NETLOGON with timeout %d"
0x1800b4f5e  mov     ecx, r12d; unsigned int
0x1800b4f61  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4f66  mov     edx, ebx; unsigned int
0x1800b4f68  lea     rcx, aNetlogon; "NETLOGON"
0x1800b4f6f  call    ?WaitForServiceToStart@@YAHPEBGK@Z; WaitForServiceToStart(ushort const *,ulong)
0x1800b4f74  test    eax, eax
0x1800b4f76  jnz     short loc_1800B4FD9
0x1800b4f78  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4f7f  jz      loc_1800B4D57
0x1800b4f85  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4f8c  test    rax, rax
0x1800b4f8f  jz      short loc_1800B4FA8
0x1800b4f91  mov     r8d, ebx
0x1800b4f94  lea     rdx, aWaitingForNetl_0; "Waiting for NETLOGON failed with timeou"...
0x1800b4f9b  mov     ecx, r12d
0x1800b4f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4fa3  jmp     loc_1800B4D57
0x1800b4fa8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4faf  jz      loc_1800B4D57
0x1800b4fb5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4fbc  jz      loc_1800B4D57
0x1800b4fc2  mov     r8d, ebx
0x1800b4fc5  lea     rdx, aWaitingForNetl_0; "Waiting for NETLOGON failed with timeou"...
0x1800b4fcc  mov     ecx, r12d; unsigned int
0x1800b4fcf  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4fd4  jmp     loc_1800B4D57
0x1800b4fd9  call    cs:__imp_GetTickCount
0x1800b4fdf  lea     r8, [rsp+48h+dwMilliseconds]; unsigned int *
0x1800b4fe4  mov     ecx, ebp; unsigned int
0x1800b4fe6  mov     edx, eax; unsigned int
0x1800b4fe8  mov     esi, eax
0x1800b4fea  call    ?CalculateTimeLeftToWait@@YAKKKPEAK@Z; CalculateTimeLeftToWait(ulong,ulong,ulong *)
0x1800b4fef  mov     ebx, eax
0x1800b4ff1  test    eax, eax
0x1800b4ff3  jnz     loc_1800B50EE
0x1800b4ff9  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b5000  mov     ebx, [rsp+48h+dwMilliseconds]
0x1800b5004  jz      short loc_1800B504A
0x1800b5006  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b500d  test    rax, rax
0x1800b5010  jz      short loc_1800B5026
0x1800b5012  mov     r8d, ebx
0x1800b5015  lea     rdx, aWaitingForMupW; "Waiting for MUP with timeout %d"
0x1800b501c  mov     ecx, r12d
0x1800b501f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5024  jmp     short loc_1800B504A
0x1800b5026  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b502d  jz      short loc_1800B504A
0x1800b502f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b5036  jz      short loc_1800B504A
0x1800b5038  mov     r8d, ebx
0x1800b503b  lea     rdx, aWaitingForMupW; "Waiting for MUP with timeout %d"
0x1800b5042  mov     ecx, r12d; unsigned int
0x1800b5045  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b504a  mov     edx, r14d; int
0x1800b504d  mov     ecx, ebx; dwMilliseconds
0x1800b504f  call    ?WaitForMUP@@YAHKH@Z; WaitForMUP(ulong,int)
0x1800b5054  test    eax, eax
0x1800b5056  jz      loc_1800B4D57
0x1800b505c  call    cs:__imp_GetTickCount
0x1800b5062  lea     r8, [rsp+48h+dwMilliseconds]; unsigned int *
0x1800b5067  mov     ecx, esi; unsigned int
0x1800b5069  mov     edx, eax; unsigned int
0x1800b506b  mov     edi, eax
0x1800b506d  call    ?CalculateTimeLeftToWait@@YAKKKPEAK@Z; CalculateTimeLeftToWait(ulong,ulong,ulong *)
0x1800b5072  mov     ebx, eax
0x1800b5074  test    eax, eax
0x1800b5076  jnz     short loc_1800B50EE
0x1800b5078  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b507f  mov     ebx, [rsp+48h+dwMilliseconds]
0x1800b5083  jz      short loc_1800B50C9
0x1800b5085  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b508c  test    rax, rax
0x1800b508f  jz      short loc_1800B50A5
0x1800b5091  mov     r8d, ebx
0x1800b5094  lea     rdx, aWaitingForDsWi; "Waiting for DS with timeout %d"
0x1800b509b  mov     ecx, r12d
0x1800b509e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b50a3  jmp     short loc_1800B50C9
0x1800b50a5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b50ac  jz      short loc_1800B50C9
0x1800b50ae  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b50b5  jz      short loc_1800B50C9
0x1800b50b7  mov     r8d, ebx
0x1800b50ba  lea     rdx, aWaitingForDsWi; "Waiting for DS with timeout %d"
0x1800b50c1  mov     ecx, r12d; unsigned int
0x1800b50c4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b50c9  mov     ecx, ebx; dwMilliseconds
0x1800b50cb  call    ?WaitForDS@@YAHK@Z; WaitForDS(ulong)
0x1800b50d0  test    eax, eax
0x1800b50d2  jz      loc_1800B4D57
0x1800b50d8  call    cs:__imp_GetTickCount
0x1800b50de  lea     r8, [rsp+48h+dwMilliseconds]; unsigned int *
0x1800b50e3  mov     ecx, edi; unsigned int
0x1800b50e5  mov     edx, eax; unsigned int
0x1800b50e7  call    ?CalculateTimeLeftToWait@@YAKKKPEAK@Z; CalculateTimeLeftToWait(ulong,ulong,ulong *)
0x1800b50ec  mov     ebx, eax
0x1800b50ee  mov     rbp, [rsp+48h+arg_10]
0x1800b50f3  mov     eax, ebx
0x1800b50f5  mov     rbx, [rsp+48h+arg_0]
0x1800b50fa  add     rsp, 20h
0x1800b50fe  pop     r15
0x1800b5100  pop     r14
0x1800b5102  pop     r12
0x1800b5104  pop     rdi
0x1800b5105  pop     rsi
0x1800b5106  retn
```
