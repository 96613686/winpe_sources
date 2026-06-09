# DpspInitializeGlobalStateInfo(void)

- ea: `0x18000e4c8`
- end: `0x18000e9cd`
- name: `?DpspInitializeGlobalStateInfo@@YAJXZ`
- size: `1285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f940`

## callees

- `0x1800013a0`
- `0x180009090`
- `0x18000a856`
- `0x18000e4c8`
- `0x180016f70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e97c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e97c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e888`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e91b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e962`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e888`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e91b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e962`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e730`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e77a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e7be`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e803`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e84c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e730`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e77a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e7be`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e803`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e84c`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000e4ee`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000e4ee`

## pseudocode

```c
__int64 DpspInitializeGlobalStateInfo(void)
{
  void *v0; // rax
  signed int Args; // ebx
  void *v2; // rax
  void *v3; // rax
  void *v4; // rax
  void *v5; // rax
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  size_t Size; // [rsp+50h] [rbp+20h] BYREF

  LODWORD(Size) = 68;
  InitializeSListHead(&g_QueuedResolutionListHead);
  g_ulQueueSize = 512;
  g_pLocalSysSid = 0;
  g_pLocalServSid = 0;
  g_pNullSid = 0;
  g_pAdminSid = 0;
  g_pEveryoneSid = 0;
  g_pScenarioHead = 0;
  g_pSessionHead = 0;
  g_pInstanceHead = 0;
  g_pHostHead = 0;
  g_pAlpcCompletion = 0;
  g_hServerPort = 0;
  g_hWorkerShutdown = 0;
  g_hTPShutdown = 0;
  g_hGroupPolicyControl = 0;
  g_hDataRetentionControl = 0;
  g_ulTotalEvents = 0;
  g_ulConnectionId = 0;
  g_DirSizeLimit = 0x8000000;
  g_CurrentDirSize = 0x8000000;
  g_pTaskService = 0;
  g_pTaskFolder = 0;
  g_lUnloadableDMCount = 0;
  g_lReceivedMessageCount = 0;
  g_lExpectedMessageCount = 0;
  g_lExpectedRejectionMessageCount = 0;
  g_lExpectedClientMessageCount = 0;
  g_DataRetentionCount = 0;
  g_WdiDir = 0;
  g_AllocUnit = 0;
  memset_0(g_RegisteredEventTable, 0, sizeof(g_RegisteredEventTable));
  memset_0(g_SpamEventTable, 0, 0x808u);
  *(_OWORD *)&g_WorkerThreadHandles = 0;
  DpspInitializeTask();
  v0 = (void *)WdipAlloc((unsigned int)Size);
  g_pLocalSysSid = v0;
  if ( v0 )
  {
    memset_0(v0, 0, (unsigned int)Size);
    v2 = (void *)WdipAlloc((unsigned int)Size);
    g_pLocalServSid = v2;
    if ( v2 )
    {
      memset_0(v2, 0, (unsigned int)Size);
      v3 = (void *)WdipAlloc((unsigned int)Size);
      g_pNullSid = v3;
      if ( v3 )
      {
        memset_0(v3, 0, (unsigned int)Size);
        v4 = (void *)WdipAlloc((unsigned int)Size);
        g_pAdminSid = v4;
        if ( v4 )
        {
          memset_0(v4, 0, (unsigned int)Size);
          v5 = (void *)WdipAlloc((unsigned int)Size);
          g_pEveryoneSid = v5;
          if ( v5 )
          {
            memset_0(v5, 0, (unsigned int)Size);
            if ( CreateWellKnownSid(WinLocalSystemSid, 0, g_pLocalSysSid, (DWORD *)&Size) )
              goto LABEL_16;
            LastError = GetLastError();
            Args = LastError;
            if ( LastError > 0 )
              Args = (unsigned __int16)LastError | 0x80070000;
            if ( Args >= 0 )
            {
LABEL_16:
              LODWORD(Size) = 68;
              if ( CreateWellKnownSid(WinLocalServiceSid, 0, g_pLocalServSid, (DWORD *)&Size) )
                goto LABEL_21;
              v7 = GetLastError();
              Args = v7;
              if ( v7 > 0 )
                Args = (unsigned __int16)v7 | 0x80070000;
              if ( Args >= 0 )
              {
LABEL_21:
                LODWORD(Size) = 68;
                if ( CreateWellKnownSid(WinNullSid, 0, g_pNullSid, (DWORD *)&Size) )
                  goto LABEL_26;
                v8 = GetLastError();
                Args = v8;
                if ( v8 > 0 )
                  Args = (unsigned __int16)v8 | 0x80070000;
                if ( Args >= 0 )
                {
LABEL_26:
                  LODWORD(Size) = 68;
                  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, g_pAdminSid, (DWORD *)&Size) )
                    goto LABEL_31;
                  v9 = GetLastError();
                  Args = v9;
                  if ( v9 > 0 )
                    Args = (unsigned __int16)v9 | 0x80070000;
                  if ( Args >= 0 )
                  {
LABEL_31:
                    LODWORD(Size) = 68;
                    if ( CreateWellKnownSid(WinWorldSid, 0, g_pEveryoneSid, (DWORD *)&Size) )
                      goto LABEL_36;
                    v10 = GetLastError();
                    Args = v10;
                    if ( v10 > 0 )
                      Args = (unsigned __int16)v10 | 0x80070000;
                    if ( Args >= 0 )
                    {
LABEL_36:
                      g_hWorkerShutdown = CreateEventW(0, 1, 0, 0);
                      if ( (((unsigned __int64)g_hWorkerShutdown + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
                        goto LABEL_41;
                      v11 = GetLastError();
                      Args = v11;
                      if ( v11 > 0 )
                        Args = (unsigned __int16)v11 | 0x80070000;
                      if ( Args >= 0 )
                      {
LABEL_41:
                        g_hTPShutdown = CreateEventW(0, 1, 0, 0);
                        if ( (((unsigned __int64)g_hTPShutdown + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
                          goto LABEL_46;
                        v12 = GetLastError();
                        Args = v12;
                        if ( v12 > 0 )
                          Args = (unsigned __int16)v12 | 0x80070000;
                        if ( Args >= 0 )
                        {
LABEL_46:
                          g_hGroupPolicyControl = CreateEventW(0, 0, 0, 0);
                          if ( (((unsigned __int64)g_hGroupPolicyControl + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
                            goto LABEL_51;
                          v13 = GetLastError();
                          Args = v13;
                          if ( v13 > 0 )
                            Args = (unsigned __int16)v13 | 0x80070000;
                          if ( Args >= 0 )
                          {
LABEL_51:
                            g_hDataRetentionControl = CreateEventW(0, 1, 0, 0);
                            if ( (char *)g_hDataRetentionControl - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
                            {
                              v14 = GetLastError();
                              Args = v14;
                              if ( v14 > 0 )
                                Args = (unsigned __int16)v14 | 0x80070000;
                              if ( Args < 0 )
                                WdipTraceError(
                                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                                  (int)L"DpspInitializeGlobalStateInfo",
                                  2679,
                                  (int)L"Error = %d",
                                  Args);
                            }
                            else
                            {
                              return 0;
                            }
                          }
                          else
                          {
                            WdipTraceError(
                              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                              (int)L"DpspInitializeGlobalStateInfo",
                              2676,
                              (int)L"Error = %d",
                              Args);
                          }
                        }
                        else
                        {
                          WdipTraceError(
                            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                            (int)L"DpspInitializeGlobalStateInfo",
                            2673,
                            (int)L"Error = %d",
                            Args);
                        }
                      }
                      else
                      {
                        WdipTraceError(
                          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                          (int)L"DpspInitializeGlobalStateInfo",
                          2670,
                          (int)L"Error = %d",
                          Args);
                      }
                    }
                    else
                    {
                      WdipTraceError(
                        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                        (int)L"DpspInitializeGlobalStateInfo",
                        2667,
                        (int)L"Error = %d",
                        Args);
                    }
                  }
                  else
                  {
                    WdipTraceError(
                      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                      (int)L"DpspInitializeGlobalStateInfo",
                      2659,
                      (int)L"Error = %d",
                      Args);
                  }
                }
                else
                {
                  WdipTraceError(
                    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                    (int)L"DpspInitializeGlobalStateInfo",
                    2651,
                    (int)L"Error = %d",
                    Args);
                }
              }
              else
              {
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                  (int)L"DpspInitializeGlobalStateInfo",
                  2643,
                  (int)L"Error = %d",
                  Args);
              }
            }
            else
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                (int)L"DpspInitializeGlobalStateInfo",
                2635,
                (int)L"Error = %d",
                Args);
            }
          }
          else
          {
            Args = -2147024882;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
              (int)L"DpspInitializeGlobalStateInfo",
              2627,
              (int)L"Error = %d",
              14);
          }
        }
        else
        {
          Args = -2147024882;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
            (int)L"DpspInitializeGlobalStateInfo",
            2620,
            (int)L"Error = %d",
            14);
        }
      }
      else
      {
        Args = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
          (int)L"DpspInitializeGlobalStateInfo",
          2613,
          (int)L"Error = %d",
          14);
      }
    }
    else
    {
      Args = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
        (int)L"DpspInitializeGlobalStateInfo",
        2606,
        (int)L"Error = %d",
        14);
    }
  }
  else
  {
    Args = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"DpspInitializeGlobalStateInfo",
      2599,
      (int)L"Error = %d",
      14);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x18000e4c8  mov     [rsp-18h+arg_8], rbx
0x18000e4cd  mov     [rsp-18h+arg_10], rsi
0x18000e4d2  push    rbp
0x18000e4d3  push    rdi
0x18000e4d4  push    r14
0x18000e4d6  mov     rbp, rsp
0x18000e4d9  sub     rsp, 30h
0x18000e4dd  mov     r14d, 44h ; 'D'
0x18000e4e3  lea     rcx, g_QueuedResolutionListHead; ListHead
0x18000e4ea  mov     dword ptr [rbp+Size], r14d
0x18000e4ee  call    cs:__imp_InitializeSListHead
0x18000e4f4  xor     edi, edi
0x18000e4f6  mov     cs:?g_ulQueueSize@@3KA, 200h; ulong g_ulQueueSize
0x18000e500  mov     cs:g_pLocalSysSid, rdi
0x18000e507  lea     rcx, g_RegisteredEventTable; void *
0x18000e50e  mov     cs:g_pLocalServSid, rdi
0x18000e515  mov     eax, 8000000h
0x18000e51a  mov     cs:g_pNullSid, rdi
0x18000e521  mov     ebx, 808h
0x18000e526  mov     cs:g_pAdminSid, rdi
0x18000e52d  mov     r8d, ebx; Size
0x18000e530  mov     cs:g_pEveryoneSid, rdi
0x18000e537  xor     edx, edx; Val
0x18000e539  mov     cs:g_pScenarioHead, rdi
0x18000e540  mov     cs:g_pSessionHead, rdi
0x18000e547  mov     cs:g_pInstanceHead, rdi
0x18000e54e  mov     cs:g_pHostHead, rdi
0x18000e555  mov     cs:g_pAlpcCompletion, rdi
0x18000e55c  mov     cs:g_hServerPort, rdi
0x18000e563  mov     cs:g_hWorkerShutdown, rdi
0x18000e56a  mov     cs:g_hTPShutdown, rdi
0x18000e571  mov     cs:g_hGroupPolicyControl, rdi
0x18000e578  mov     cs:g_hDataRetentionControl, rdi
0x18000e57f  mov     cs:g_ulTotalEvents, edi
0x18000e585  mov     cs:g_ulConnectionId, rdi
0x18000e58c  mov     cs:g_DirSizeLimit, rax
0x18000e593  mov     cs:g_CurrentDirSize, rax
0x18000e59a  mov     cs:g_pTaskService, rdi
0x18000e5a1  mov     cs:g_pTaskFolder, rdi
0x18000e5a8  mov     cs:g_lUnloadableDMCount, edi
0x18000e5ae  mov     cs:g_lReceivedMessageCount, edi
0x18000e5b4  mov     cs:g_lExpectedMessageCount, edi
0x18000e5ba  mov     cs:g_lExpectedRejectionMessageCount, edi
0x18000e5c0  mov     cs:g_lExpectedClientMessageCount, edi
0x18000e5c6  mov     cs:g_DataRetentionCount, edi
0x18000e5cc  mov     cs:g_WdiDir, rdi
0x18000e5d3  mov     cs:g_AllocUnit, edi
0x18000e5d9  call    memset_0
0x18000e5de  mov     r8d, ebx; Size
0x18000e5e1  lea     rcx, g_SpamEventTable; void *
0x18000e5e8  xor     edx, edx; Val
0x18000e5ea  call    memset_0
0x18000e5ef  xorps   xmm0, xmm0
0x18000e5f2  movups  cs:g_WorkerThreadHandles, xmm0
0x18000e5f9  call    DpspInitializeTask
0x18000e5fe  mov     ecx, dword ptr [rbp+Size]
0x18000e601  call    WdipAlloc
0x18000e606  mov     cs:g_pLocalSysSid, rax
0x18000e60d  test    rax, rax
0x18000e610  jnz     short loc_18000E62A
0x18000e612  mov     ebx, 8007000Eh
0x18000e617  mov     dword ptr [rsp+30h+Args], 0Eh
0x18000e61f  mov     r8d, 0A27h
0x18000e625  jmp     loc_18000E99E
0x18000e62a  mov     r8d, dword ptr [rbp+Size]; Size
0x18000e62e  xor     edx, edx; Val
0x18000e630  mov     rcx, rax; void *
0x18000e633  call    memset_0
0x18000e638  mov     ecx, dword ptr [rbp+Size]
0x18000e63b  call    WdipAlloc
0x18000e640  mov     cs:g_pLocalServSid, rax
0x18000e647  test    rax, rax
0x18000e64a  jnz     short loc_18000E664
0x18000e64c  mov     ebx, 8007000Eh
0x18000e651  mov     dword ptr [rsp+30h+Args], 0Eh
0x18000e659  mov     r8d, 0A2Eh
0x18000e65f  jmp     loc_18000E99E
0x18000e664  mov     r8d, dword ptr [rbp+Size]; Size
0x18000e668  xor     edx, edx; Val
0x18000e66a  mov     rcx, rax; void *
0x18000e66d  call    memset_0
0x18000e672  mov     ecx, dword ptr [rbp+Size]
0x18000e675  call    WdipAlloc
0x18000e67a  mov     cs:g_pNullSid, rax
0x18000e681  test    rax, rax
0x18000e684  jnz     short loc_18000E69E
0x18000e686  mov     ebx, 8007000Eh
0x18000e68b  mov     dword ptr [rsp+30h+Args], 0Eh
0x18000e693  mov     r8d, 0A35h
0x18000e699  jmp     loc_18000E99E
0x18000e69e  mov     r8d, dword ptr [rbp+Size]; Size
0x18000e6a2  xor     edx, edx; Val
0x18000e6a4  mov     rcx, rax; void *
0x18000e6a7  call    memset_0
0x18000e6ac  mov     ecx, dword ptr [rbp+Size]
0x18000e6af  call    WdipAlloc
0x18000e6b4  mov     cs:g_pAdminSid, rax
0x18000e6bb  test    rax, rax
0x18000e6be  jnz     short loc_18000E6D8
0x18000e6c0  mov     ebx, 8007000Eh
0x18000e6c5  mov     dword ptr [rsp+30h+Args], 0Eh
0x18000e6cd  mov     r8d, 0A3Ch
0x18000e6d3  jmp     loc_18000E99E
0x18000e6d8  mov     r8d, dword ptr [rbp+Size]; Size
0x18000e6dc  xor     edx, edx; Val
0x18000e6de  mov     rcx, rax; void *
0x18000e6e1  call    memset_0
0x18000e6e6  mov     ecx, dword ptr [rbp+Size]
0x18000e6e9  call    WdipAlloc
0x18000e6ee  mov     cs:g_pEveryoneSid, rax
0x18000e6f5  test    rax, rax
0x18000e6f8  jnz     short loc_18000E712
0x18000e6fa  mov     ebx, 8007000Eh
0x18000e6ff  mov     dword ptr [rsp+30h+Args], 0Eh
0x18000e707  mov     r8d, 0A43h
0x18000e70d  jmp     loc_18000E99E
0x18000e712  mov     r8d, dword ptr [rbp+Size]; Size
0x18000e716  xor     edx, edx; Val
0x18000e718  mov     rcx, rax; void *
0x18000e71b  call    memset_0
0x18000e720  mov     r8, cs:g_pLocalSysSid; pSid
0x18000e727  lea     r9, [rbp+Size]; cbSid
0x18000e72b  xor     edx, edx; DomainSid
0x18000e72d  lea     ecx, [rdx+16h]; WellKnownSidType
0x18000e730  call    cs:__imp_CreateWellKnownSid
0x18000e736  mov     esi, 80070000h
0x18000e73b  test    eax, eax
0x18000e73d  jnz     short loc_18000E766
0x18000e73f  call    cs:__imp_GetLastError
0x18000e745  mov     ebx, eax
0x18000e747  test    eax, eax
0x18000e749  jle     short loc_18000E750
0x18000e74b  movzx   ebx, ax
0x18000e74e  or      ebx, esi
0x18000e750  test    ebx, ebx
0x18000e752  jns     short loc_18000E766
0x18000e754  movzx   eax, bx
0x18000e757  mov     r8d, 0A4Bh
0x18000e75d  mov     dword ptr [rsp+30h+Args], eax
0x18000e761  jmp     loc_18000E99E
0x18000e766  mov     r8, cs:g_pLocalServSid; pSid
0x18000e76d  lea     r9, [rbp+Size]; cbSid
0x18000e771  xor     edx, edx; DomainSid
0x18000e773  mov     dword ptr [rbp+Size], r14d
0x18000e777  lea     ecx, [rdx+17h]; WellKnownSidType
0x18000e77a  call    cs:__imp_CreateWellKnownSid
0x18000e780  test    eax, eax
0x18000e782  jnz     short loc_18000E7AB
0x18000e784  call    cs:__imp_GetLastError
0x18000e78a  mov     ebx, eax
0x18000e78c  test    eax, eax
0x18000e78e  jle     short loc_18000E795
0x18000e790  movzx   ebx, ax
0x18000e793  or      ebx, esi
0x18000e795  test    ebx, ebx
0x18000e797  jns     short loc_18000E7AB
0x18000e799  movzx   eax, bx
0x18000e79c  mov     r8d, 0A53h
0x18000e7a2  mov     dword ptr [rsp+30h+Args], eax
0x18000e7a6  jmp     loc_18000E99E
0x18000e7ab  mov     r8, cs:g_pNullSid; pSid
0x18000e7b2  lea     r9, [rbp+Size]; cbSid
0x18000e7b6  xor     edx, edx; DomainSid
0x18000e7b8  mov     dword ptr [rbp+Size], r14d
0x18000e7bc  xor     ecx, ecx; WellKnownSidType
0x18000e7be  call    cs:__imp_CreateWellKnownSid
0x18000e7c4  test    eax, eax
0x18000e7c6  jnz     short loc_18000E7EF
0x18000e7c8  call    cs:__imp_GetLastError
0x18000e7ce  mov     ebx, eax
0x18000e7d0  test    eax, eax
0x18000e7d2  jle     short loc_18000E7D9
0x18000e7d4  movzx   ebx, ax
0x18000e7d7  or      ebx, esi
0x18000e7d9  test    ebx, ebx
0x18000e7db  jns     short loc_18000E7EF
0x18000e7dd  movzx   eax, bx
0x18000e7e0  mov     r8d, 0A5Bh
0x18000e7e6  mov     dword ptr [rsp+30h+Args], eax
0x18000e7ea  jmp     loc_18000E99E
0x18000e7ef  mov     r8, cs:g_pAdminSid; pSid
0x18000e7f6  lea     r9, [rbp+Size]; cbSid
0x18000e7fa  xor     edx, edx; DomainSid
0x18000e7fc  mov     dword ptr [rbp+Size], r14d
0x18000e800  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18000e803  call    cs:__imp_CreateWellKnownSid
0x18000e809  test    eax, eax
0x18000e80b  jnz     short loc_18000E834
0x18000e80d  call    cs:__imp_GetLastError
0x18000e813  mov     ebx, eax
0x18000e815  test    eax, eax
0x18000e817  jle     short loc_18000E81E
0x18000e819  movzx   ebx, ax
0x18000e81c  or      ebx, esi
0x18000e81e  test    ebx, ebx
0x18000e820  jns     short loc_18000E834
0x18000e822  movzx   eax, bx
0x18000e825  mov     r8d, 0A63h
0x18000e82b  mov     dword ptr [rsp+30h+Args], eax
0x18000e82f  jmp     loc_18000E99E
0x18000e834  mov     r8, cs:g_pEveryoneSid; pSid
0x18000e83b  lea     r9, [rbp+Size]; cbSid
0x18000e83f  xor     edx, edx; DomainSid
0x18000e841  mov     dword ptr [rbp+Size], r14d
0x18000e845  lea     r14d, [rdx+1]
0x18000e849  mov     ecx, r14d; WellKnownSidType
0x18000e84c  call    cs:__imp_CreateWellKnownSid
0x18000e852  test    eax, eax
0x18000e854  jnz     short loc_18000E87D
0x18000e856  call    cs:__imp_GetLastError
0x18000e85c  mov     ebx, eax
0x18000e85e  test    eax, eax
0x18000e860  jle     short loc_18000E867
0x18000e862  movzx   ebx, ax
0x18000e865  or      ebx, esi
0x18000e867  test    ebx, ebx
0x18000e869  jns     short loc_18000E87D
0x18000e86b  movzx   eax, bx
0x18000e86e  mov     r8d, 0A6Bh
0x18000e874  mov     dword ptr [rsp+30h+Args], eax
0x18000e878  jmp     loc_18000E99E
0x18000e87d  xor     r9d, r9d; lpName
0x18000e880  xor     r8d, r8d; bInitialState
0x18000e883  mov     edx, r14d; bManualReset
0x18000e886  xor     ecx, ecx; lpEventAttributes
0x18000e888  call    cs:__imp_CreateEventW
0x18000e88e  mov     cs:g_hWorkerShutdown, rax
0x18000e895  inc     rax
0x18000e898  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e89e  jnz     short loc_18000E8C7
0x18000e8a0  call    cs:__imp_GetLastError
0x18000e8a6  mov     ebx, eax
0x18000e8a8  test    eax, eax
0x18000e8aa  jle     short loc_18000E8B1
0x18000e8ac  movzx   ebx, ax
0x18000e8af  or      ebx, esi
0x18000e8b1  test    ebx, ebx
0x18000e8b3  jns     short loc_18000E8C7
0x18000e8b5  movzx   eax, bx
0x18000e8b8  mov     r8d, 0A6Eh
0x18000e8be  mov     dword ptr [rsp+30h+Args], eax
0x18000e8c2  jmp     loc_18000E99E
0x18000e8c7  xor     r9d, r9d; lpName
0x18000e8ca  xor     r8d, r8d; bInitialState
0x18000e8cd  mov     edx, r14d; bManualReset
0x18000e8d0  xor     ecx, ecx; lpEventAttributes
0x18000e8d2  call    cs:__imp_CreateEventW
0x18000e8d8  mov     cs:g_hTPShutdown, rax
0x18000e8df  inc     rax
0x18000e8e2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e8e8  jnz     short loc_18000E911
0x18000e8ea  call    cs:__imp_GetLastError
0x18000e8f0  mov     ebx, eax
0x18000e8f2  test    eax, eax
0x18000e8f4  jle     short loc_18000E8FB
0x18000e8f6  movzx   ebx, ax
0x18000e8f9  or      ebx, esi
0x18000e8fb  test    ebx, ebx
0x18000e8fd  jns     short loc_18000E911
0x18000e8ff  movzx   eax, bx
0x18000e902  mov     r8d, 0A71h
0x18000e908  mov     dword ptr [rsp+30h+Args], eax
0x18000e90c  jmp     loc_18000E99E
0x18000e911  xor     r9d, r9d; lpName
0x18000e914  xor     r8d, r8d; bInitialState
0x18000e917  xor     edx, edx; bManualReset
0x18000e919  xor     ecx, ecx; lpEventAttributes
0x18000e91b  call    cs:__imp_CreateEventW
0x18000e921  mov     cs:g_hGroupPolicyControl, rax
0x18000e928  inc     rax
0x18000e92b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e931  jnz     short loc_18000E957
0x18000e933  call    cs:__imp_GetLastError
0x18000e939  mov     ebx, eax
0x18000e93b  test    eax, eax
0x18000e93d  jle     short loc_18000E944
0x18000e93f  movzx   ebx, ax
0x18000e942  or      ebx, esi
0x18000e944  test    ebx, ebx
0x18000e946  jns     short loc_18000E957
0x18000e948  movzx   eax, bx
0x18000e94b  mov     r8d, 0A74h
0x18000e951  mov     dword ptr [rsp+30h+Args], eax
0x18000e955  jmp     short loc_18000E99E
0x18000e957  xor     r9d, r9d; lpName
0x18000e95a  xor     r8d, r8d; bInitialState
0x18000e95d  mov     edx, r14d; bManualReset
0x18000e960  xor     ecx, ecx; lpEventAttributes
0x18000e962  call    cs:__imp_CreateEventW
0x18000e968  mov     cs:g_hDataRetentionControl, rax
0x18000e96f  dec     rax
0x18000e972  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e976  ja      short loc_18000E97C
0x18000e978  mov     ebx, edi
0x18000e97a  jmp     short loc_18000E9B8
0x18000e97c  call    cs:__imp_GetLastError
0x18000e982  mov     ebx, eax
0x18000e984  test    eax, eax
0x18000e986  jle     short loc_18000E98D
0x18000e988  movzx   ebx, ax
  ... truncated ...
```
