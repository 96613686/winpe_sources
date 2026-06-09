# WaitForDS(ulong)

- ea: `0x1800b44d8`
- end: `0x1800b49d9`
- name: `?WaitForDS@@YAHK@Z`
- size: `1281`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b4cc8`

## callees

- `0x180003770`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800b44d8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4568`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4628`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4568`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4628`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b477e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b477e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b45c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4687`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b480e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b45c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4687`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b480e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4617`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b46d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b48a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4617`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b46d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b48a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b48bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b48bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4711`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4711`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4756`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4888`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4756`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4888`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800b47a5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800b47a5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b4980`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b4980`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b49a3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b49a3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b4998`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b4998`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileIntW` at `0x1800b496c`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileIntW` at `0x1800b496c`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800b4533`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800b4533`
- `DSROLE!DsRoleFreeMemory` at `0x1800b49ae`
- `DSROLE!DsRoleFreeMemory` at `0x1800b49ae`

## string_xrefs

- `0x1800b455d`: `NtdsDelayedStartupCompletedEvent`
- `0x1800b458f`: `WaitForDS (NtdsDelayedStartupCompletedEvent): Beginning WaitForSingleObject.`
- `0x1800b45b2`: `WaitForDS (NtdsDelayedStartupCompletedEvent): Beginning WaitForSingleObject.`
- `0x1800b45e2`: `WaitForDS (NtdsDelayedStartupCompletedEvent): Completed WaitForSingleObject.`
- `0x1800b4605`: `WaitForDS (NtdsDelayedStartupCompletedEvent): Completed WaitForSingleObject.`
- `0x1800b461d`: `NTDSInitialSyncsCompleted`
- `0x1800b464f`: `WaitForDS (NTDSInitialSyncsCompleted): Beginning WaitForSingleObject.`
- `0x1800b4672`: `WaitForDS (NTDSInitialSyncsCompleted): Beginning WaitForSingleObject.`
- `0x1800b46a2`: `WaitForDS (NTDSInitialSyncsCompleted): Completed WaitForSingleObject.`
- `0x1800b46c5`: `WaitForDS (NTDSInitialSyncsCompleted): Completed WaitForSingleObject.`
- `0x1800b4703`: `SYSTEM\CurrentControlSet\Services\netlogon\parameters`
- `0x1800b4745`: `SysVolReady`
- `0x1800b4881`: `SysVolReady`
- `0x1800b476f`: `SysVolReadyEvent`
- `0x1800b47d6`: `WaitForDS (SysVolReadyEvent): Beginning WaitForSingleObject.`
- `0x1800b47f9`: `WaitForDS (SysVolReadyEvent): Beginning WaitForSingleObject.`
- `0x1800b4829`: `WaitForDS (SysVolReadyEvent): Completed WaitForSingleObject.`
- `0x1800b484c`: `WaitForDS (SysVolReadyEvent): Completed WaitForSingleObject.`
- `0x1800b491f`: `Testing sysvol path of %ls`
- `0x1800b4949`: `Testing sysvol path of %ls`
- `0x1800b495b`: `MaxRetrySysvolAccess`

## pseudocode

```c
__int64 __fastcall WaitForDS(DWORD dwMilliseconds)
{
  unsigned int v2; // edi
  HANDLE v3; // rbx
  HANDLE v4; // rbx
  LSTATUS v5; // eax
  HANDLE EventW; // rax
  void *v7; // rbx
  int v8; // esi
  DWORD v9; // r14d
  int v10; // ebx
  UINT ProfileIntW; // esi
  HANDLE FirstFileW; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  PBYTE Buffer; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[512]; // [rsp+2A0h] [rbp+1A0h] BYREF

  Buffer = 0;
  v2 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer) )
  {
    if ( (unsigned int)(*(_DWORD *)Buffer - 4) <= 1 )
    {
      v3 = OpenEventW(0x100000u, 0, L"NtdsDelayedStartupCompletedEvent");
      if ( v3 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"WaitForDS (NtdsDelayedStartupCompletedEvent): Beginning WaitForSingleObject.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"WaitForDS (NtdsDelayedStartupCompletedEvent): Beginning WaitForSingleObject.");
          }
        }
        WaitForSingleObject(v3, dwMilliseconds);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"WaitForDS (NtdsDelayedStartupCompletedEvent): Completed WaitForSingleObject.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"WaitForDS (NtdsDelayedStartupCompletedEvent): Completed WaitForSingleObject.");
          }
        }
        CloseHandle(v3);
      }
      v4 = OpenEventW(0x100000u, 0, L"NTDSInitialSyncsCompleted");
      if ( v4 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"WaitForDS (NTDSInitialSyncsCompleted): Beginning WaitForSingleObject.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"WaitForDS (NTDSInitialSyncsCompleted): Beginning WaitForSingleObject.");
          }
        }
        WaitForSingleObject(v4, dwMilliseconds);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"WaitForDS (NTDSInitialSyncsCompleted): Completed WaitForSingleObject.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"WaitForDS (NTDSInitialSyncsCompleted): Completed WaitForSingleObject.");
          }
        }
        CloseHandle(v4);
      }
    }
    if ( *(_DWORD *)Buffer == 5 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\netlogon\\parameters",
              0,
              0x20019u,
              &hKey) )
      {
        *(_DWORD *)Data = 0;
        cbData = 4;
        Type = 4;
        v5 = RegQueryValueExW(hKey, L"SysVolReady", 0, &Type, Data, &cbData);
        if ( v5 )
        {
          if ( v5 == 2 )
            v2 = 1;
        }
        else if ( !*(_DWORD *)Data )
        {
          EventW = CreateEventW(0, 1, 0, L"SysVolReadyEvent");
          v7 = EventW;
          if ( EventW )
          {
            v8 = 0;
            if ( !RegNotifyChangeKeyValue(hKey, 0, 4u, EventW, 1) )
            {
              v9 = dwMilliseconds / 3;
              while ( 1 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"WaitForDS (SysVolReadyEvent): Beginning WaitForSingleObject.");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"WaitForDS (SysVolReadyEvent): Beginning WaitForSingleObject.");
                  }
                }
                WaitForSingleObject(v7, v9);
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"WaitForDS (SysVolReadyEvent): Completed WaitForSingleObject.");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"WaitForDS (SysVolReadyEvent): Completed WaitForSingleObject.");
                  }
                }
                cbData = 4;
                RegQueryValueExW(hKey, L"SysVolReady", 0, &Type, Data, &cbData);
                if ( *(_DWORD *)Data )
                  break;
                if ( (unsigned int)++v8 >= 3 )
                  goto LABEL_54;
              }
              v2 = 1;
            }
LABEL_54:
            CloseHandle(v7);
          }
        }
        RegCloseKey(hKey);
      }
    }
    else
    {
      v2 = 1;
    }
    if ( (unsigned int)(*(_DWORD *)Buffer - 4) <= 1
      && (int)StringCchPrintfW(FileName, 0x200u, L"\\\\%s\\sysvol\\*.*", *((_QWORD *)Buffer + 2)) >= 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Testing sysvol path of %ls", FileName);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Testing sysvol path of %ls", FileName);
        }
      }
      v10 = 0;
      ProfileIntW = GetProfileIntW(L"WINLOGON", L"MaxRetrySysvolAccess", 180);
      while ( 1 )
      {
        FirstFileW = FindFirstFileW(FileName, &FindFileData);
        if ( FirstFileW != (HANDLE)-1LL )
          break;
        if ( ++v10 > ProfileIntW )
          goto LABEL_72;
        Sleep(0x3E8u);
      }
      FindClose(FirstFileW);
    }
LABEL_72:
    DsRoleFreeMemory(Buffer);
  }
  return v2;
}

```

## disassembly

```asm
0x1800b44d8  push    rbp
0x1800b44da  push    rbx
0x1800b44db  push    rsi
0x1800b44dc  push    rdi
0x1800b44dd  push    r12
0x1800b44df  push    r13
0x1800b44e1  push    r14
0x1800b44e3  push    r15
0x1800b44e5  lea     rbp, [rsp-5B8h]
0x1800b44ed  sub     rsp, 6B8h
0x1800b44f4  mov     rax, cs:__security_cookie
0x1800b44fb  xor     rax, rsp
0x1800b44fe  mov     [rbp+5F0h+var_50], rax
0x1800b4505  mov     r14d, ecx
0x1800b4508  xor     r15d, r15d
0x1800b450b  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x1800b4510  mov     [rsp+6F0h+Buffer], r15
0x1800b4515  xor     edx, edx; Val
0x1800b4517  mov     r8d, 250h; Size
0x1800b451d  mov     edi, r15d
0x1800b4520  call    memset_0
0x1800b4525  lea     r13d, [r15+1]
0x1800b4529  xor     ecx, ecx; lpServer
0x1800b452b  mov     edx, r13d; InfoLevel
0x1800b452e  lea     r8, [rsp+6F0h+Buffer]; Buffer
0x1800b4533  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800b4539  test    eax, eax
0x1800b453b  jnz     loc_1800B49B4
0x1800b4541  mov     rax, [rsp+6F0h+Buffer]
0x1800b4546  lea     r12d, [r15+4]
0x1800b454a  mov     ecx, [rax]
0x1800b454c  sub     ecx, r12d
0x1800b454f  cmp     ecx, r13d
0x1800b4552  ja      loc_1800B46DD
0x1800b4558  mov     esi, 100000h
0x1800b455d  lea     r8, Name; "NtdsDelayedStartupCompletedEvent"
0x1800b4564  mov     ecx, esi; dwDesiredAccess
0x1800b4566  xor     edx, edx; bInheritHandle
0x1800b4568  call    cs:__imp_OpenEventW
0x1800b456e  mov     rbx, rax
0x1800b4571  test    rax, rax
0x1800b4574  jz      loc_1800B461D
0x1800b457a  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4581  jz      short loc_1800B45C1
0x1800b4583  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b458a  test    rax, rax
0x1800b458d  jz      short loc_1800B45A0
0x1800b458f  lea     rdx, aWaitfordsNtdsd; "WaitForDS (NtdsDelayedStartupCompletedE"...
0x1800b4596  mov     ecx, r12d
0x1800b4599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b459e  jmp     short loc_1800B45C1
0x1800b45a0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b45a7  jz      short loc_1800B45C1
0x1800b45a9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b45b0  jz      short loc_1800B45C1
0x1800b45b2  lea     rdx, aWaitfordsNtdsd; "WaitForDS (NtdsDelayedStartupCompletedE"...
0x1800b45b9  mov     ecx, r12d; unsigned int
0x1800b45bc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b45c1  mov     edx, r14d; dwMilliseconds
0x1800b45c4  mov     rcx, rbx; hHandle
0x1800b45c7  call    cs:__imp_WaitForSingleObject
0x1800b45cd  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b45d4  jz      short loc_1800B4614
0x1800b45d6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b45dd  test    rax, rax
0x1800b45e0  jz      short loc_1800B45F3
0x1800b45e2  lea     rdx, aWaitfordsNtdsd_0; "WaitForDS (NtdsDelayedStartupCompletedE"...
0x1800b45e9  mov     ecx, r12d
0x1800b45ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b45f1  jmp     short loc_1800B4614
0x1800b45f3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b45fa  jz      short loc_1800B4614
0x1800b45fc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4603  jz      short loc_1800B4614
0x1800b4605  lea     rdx, aWaitfordsNtdsd_0; "WaitForDS (NtdsDelayedStartupCompletedE"...
0x1800b460c  mov     ecx, r12d; unsigned int
0x1800b460f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4614  mov     rcx, rbx; hObject
0x1800b4617  call    cs:__imp_CloseHandle
0x1800b461d  lea     r8, aNtdsinitialsyn; "NTDSInitialSyncsCompleted"
0x1800b4624  xor     edx, edx; bInheritHandle
0x1800b4626  mov     ecx, esi; dwDesiredAccess
0x1800b4628  call    cs:__imp_OpenEventW
0x1800b462e  mov     rbx, rax
0x1800b4631  test    rax, rax
0x1800b4634  jz      loc_1800B46DD
0x1800b463a  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4641  jz      short loc_1800B4681
0x1800b4643  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b464a  test    rax, rax
0x1800b464d  jz      short loc_1800B4660
0x1800b464f  lea     rdx, aWaitfordsNtdsi; "WaitForDS (NTDSInitialSyncsCompleted): "...
0x1800b4656  mov     ecx, r12d
0x1800b4659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b465e  jmp     short loc_1800B4681
0x1800b4660  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4667  jz      short loc_1800B4681
0x1800b4669  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4670  jz      short loc_1800B4681
0x1800b4672  lea     rdx, aWaitfordsNtdsi; "WaitForDS (NTDSInitialSyncsCompleted): "...
0x1800b4679  mov     ecx, r12d; unsigned int
0x1800b467c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4681  mov     edx, r14d; dwMilliseconds
0x1800b4684  mov     rcx, rbx; hHandle
0x1800b4687  call    cs:__imp_WaitForSingleObject
0x1800b468d  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4694  jz      short loc_1800B46D4
0x1800b4696  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b469d  test    rax, rax
0x1800b46a0  jz      short loc_1800B46B3
0x1800b46a2  lea     rdx, aWaitfordsNtdsi_0; "WaitForDS (NTDSInitialSyncsCompleted): "...
0x1800b46a9  mov     ecx, r12d
0x1800b46ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b46b1  jmp     short loc_1800B46D4
0x1800b46b3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b46ba  jz      short loc_1800B46D4
0x1800b46bc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b46c3  jz      short loc_1800B46D4
0x1800b46c5  lea     rdx, aWaitfordsNtdsi_0; "WaitForDS (NTDSInitialSyncsCompleted): "...
0x1800b46cc  mov     ecx, r12d; unsigned int
0x1800b46cf  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b46d4  mov     rcx, rbx; hObject
0x1800b46d7  call    cs:__imp_CloseHandle
0x1800b46dd  mov     rax, [rsp+6F0h+Buffer]
0x1800b46e2  cmp     dword ptr [rax], 5
0x1800b46e5  jnz     loc_1800B48C5
0x1800b46eb  lea     rax, [rsp+6F0h+hKey]
0x1800b46f0  mov     [rsp+6F0h+hKey], r15
0x1800b46f5  mov     r9d, 20019h; samDesired
0x1800b46fb  mov     [rsp+6F0h+phkResult], rax; phkResult
0x1800b4700  xor     r8d, r8d; ulOptions
0x1800b4703  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\ne"...
0x1800b470a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4711  call    cs:__imp_RegOpenKeyExW
0x1800b4717  test    eax, eax
0x1800b4719  jnz     loc_1800B48C8
0x1800b471f  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800b4724  lea     rax, [rsp+6F0h+cbData]
0x1800b4729  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x1800b472e  lea     r9, [rsp+6F0h+Type]; lpType
0x1800b4733  lea     rax, [rsp+6F0h+Data]
0x1800b4738  mov     dword ptr [rsp+6F0h+Data], r15d
0x1800b473d  xor     r8d, r8d; lpReserved
0x1800b4740  mov     [rsp+6F0h+phkResult], rax; lpData
0x1800b4745  lea     rdx, aSysvolready; "SysVolReady"
0x1800b474c  mov     [rsp+6F0h+cbData], r12d
0x1800b4751  mov     [rsp+6F0h+Type], r12d
0x1800b4756  call    cs:__imp_RegQueryValueExW
0x1800b475c  test    eax, eax
0x1800b475e  jnz     loc_1800B48B1
0x1800b4764  cmp     dword ptr [rsp+6F0h+Data], r15d
0x1800b4769  jnz     loc_1800B48B8
0x1800b476f  lea     r9, aSysvolreadyeve; "SysVolReadyEvent"
0x1800b4776  xor     r8d, r8d; bInitialState
0x1800b4779  mov     edx, r13d; bManualReset
0x1800b477c  xor     ecx, ecx; lpEventAttributes
0x1800b477e  call    cs:__imp_CreateEventW
0x1800b4784  mov     rbx, rax
0x1800b4787  test    rax, rax
0x1800b478a  jz      loc_1800B48B8
0x1800b4790  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800b4795  mov     r9, rax; hEvent
0x1800b4798  mov     r8d, r12d; dwNotifyFilter
0x1800b479b  mov     dword ptr [rsp+6F0h+phkResult], r13d; fAsynchronous
0x1800b47a0  xor     edx, edx; bWatchSubtree
0x1800b47a2  mov     esi, r15d
0x1800b47a5  call    cs:__imp_RegNotifyChangeKeyValue
0x1800b47ab  test    eax, eax
0x1800b47ad  jnz     loc_1800B48A6
0x1800b47b3  mov     eax, 0AAAAAAABh
0x1800b47b8  mul     r14d
0x1800b47bb  mov     r14d, edx
0x1800b47be  shr     r14d, 1
0x1800b47c1  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b47c8  jz      short loc_1800B4808
0x1800b47ca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b47d1  test    rax, rax
0x1800b47d4  jz      short loc_1800B47E7
0x1800b47d6  lea     rdx, aWaitfordsSysvo; "WaitForDS (SysVolReadyEvent): Beginning"...
0x1800b47dd  mov     ecx, r12d
0x1800b47e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47e5  jmp     short loc_1800B4808
0x1800b47e7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b47ee  jz      short loc_1800B4808
0x1800b47f0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b47f7  jz      short loc_1800B4808
0x1800b47f9  lea     rdx, aWaitfordsSysvo; "WaitForDS (SysVolReadyEvent): Beginning"...
0x1800b4800  mov     ecx, r12d; unsigned int
0x1800b4803  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4808  mov     edx, r14d; dwMilliseconds
0x1800b480b  mov     rcx, rbx; hHandle
0x1800b480e  call    cs:__imp_WaitForSingleObject
0x1800b4814  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b481b  jz      short loc_1800B485B
0x1800b481d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4824  test    rax, rax
0x1800b4827  jz      short loc_1800B483A
0x1800b4829  lea     rdx, aWaitfordsSysvo_0; "WaitForDS (SysVolReadyEvent): Completed"...
0x1800b4830  mov     ecx, r12d
0x1800b4833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4838  jmp     short loc_1800B485B
0x1800b483a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4841  jz      short loc_1800B485B
0x1800b4843  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b484a  jz      short loc_1800B485B
0x1800b484c  lea     rdx, aWaitfordsSysvo_0; "WaitForDS (SysVolReadyEvent): Completed"...
0x1800b4853  mov     ecx, r12d; unsigned int
0x1800b4856  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b485b  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800b4860  lea     rax, [rsp+6F0h+cbData]
0x1800b4865  mov     [rsp+6F0h+lpcbData], rax; lpcbData
0x1800b486a  lea     r9, [rsp+6F0h+Type]; lpType
0x1800b486f  lea     rax, [rsp+6F0h+Data]
0x1800b4874  mov     [rsp+6F0h+cbData], r12d
0x1800b4879  xor     r8d, r8d; lpReserved
0x1800b487c  mov     [rsp+6F0h+phkResult], rax; lpData
0x1800b4881  lea     rdx, aSysvolready; "SysVolReady"
0x1800b4888  call    cs:__imp_RegQueryValueExW
0x1800b488e  cmp     dword ptr [rsp+6F0h+Data], r15d
0x1800b4893  jnz     short loc_1800B48A3
0x1800b4895  add     esi, r13d
0x1800b4898  cmp     esi, 3
0x1800b489b  jb      loc_1800B47C1
0x1800b48a1  jmp     short loc_1800B48A6
0x1800b48a3  mov     edi, r13d
0x1800b48a6  mov     rcx, rbx; hObject
0x1800b48a9  call    cs:__imp_CloseHandle
0x1800b48af  jmp     short loc_1800B48B8
0x1800b48b1  cmp     eax, 2
0x1800b48b4  cmovz   edi, r13d
0x1800b48b8  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1800b48bd  call    cs:__imp_RegCloseKey
0x1800b48c3  jmp     short loc_1800B48C8
0x1800b48c5  mov     edi, r13d
0x1800b48c8  mov     r9, [rsp+6F0h+Buffer]
0x1800b48cd  mov     eax, [r9]
0x1800b48d0  sub     eax, r12d
0x1800b48d3  cmp     eax, r13d
0x1800b48d6  ja      loc_1800B49A9
0x1800b48dc  mov     r9, [r9+10h]
0x1800b48e0  lea     r8, aSSysvol; "\\\\%s\\sysvol\\*.*"
0x1800b48e7  mov     edx, 200h; unsigned __int64
0x1800b48ec  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x1800b48f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b48f8  test    eax, eax
0x1800b48fa  js      loc_1800B49A9
0x1800b4900  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4907  jz      short loc_1800B4955
0x1800b4909  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4910  test    rax, rax
0x1800b4913  jz      short loc_1800B492D
0x1800b4915  lea     r8, [rbp+5F0h+FileName]
0x1800b491c  mov     ecx, r12d
0x1800b491f  lea     rdx, aTestingSysvolP; "Testing sysvol path of %ls"
0x1800b4926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b492b  jmp     short loc_1800B4955
0x1800b492d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4934  jz      short loc_1800B4955
0x1800b4936  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b493d  jz      short loc_1800B4955
0x1800b493f  lea     r8, [rbp+5F0h+FileName]
0x1800b4946  mov     ecx, r12d; unsigned int
0x1800b4949  lea     rdx, aTestingSysvolP; "Testing sysvol path of %ls"
0x1800b4950  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4955  mov     r8d, 0B4h; nDefault
0x1800b495b  lea     rdx, aMaxretrysysvol; "MaxRetrySysvolAccess"
0x1800b4962  lea     rcx, aWinlogon; "WINLOGON"
0x1800b4969  mov     ebx, r15d
0x1800b496c  call    cs:__imp_GetProfileIntW
0x1800b4972  mov     esi, eax
0x1800b4974  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x1800b4979  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x1800b4980  call    cs:__imp_FindFirstFileW
0x1800b4986  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b498a  jnz     short loc_1800B49A0
0x1800b498c  add     ebx, r13d
0x1800b498f  cmp     ebx, esi
0x1800b4991  ja      short loc_1800B49A9
0x1800b4993  mov     ecx, 3E8h; dwMilliseconds
0x1800b4998  call    cs:__imp_Sleep
0x1800b499e  jmp     short loc_1800B4974
0x1800b49a0  mov     rcx, rax; hFindFile
0x1800b49a3  call    cs:__imp_FindClose
0x1800b49a9  mov     rcx, [rsp+6F0h+Buffer]; Buffer
0x1800b49ae  call    cs:__imp_DsRoleFreeMemory
0x1800b49b4  mov     eax, edi
0x1800b49b6  mov     rcx, [rbp+5F0h+var_50]
0x1800b49bd  xor     rcx, rsp; StackCookie
0x1800b49c0  call    __security_check_cookie
0x1800b49c5  add     rsp, 6B8h
0x1800b49cc  pop     r15
0x1800b49ce  pop     r14
0x1800b49d0  pop     r13
0x1800b49d2  pop     r12
0x1800b49d4  pop     rdi
0x1800b49d5  pop     rsi
0x1800b49d6  pop     rbx
0x1800b49d7  pop     rbp
0x1800b49d8  retn
```
