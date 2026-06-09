# DebugClient::EndSession(ulong)

- ea: `0x1801aa1f0`
- end: `0x1801aa452`
- name: `?EndSession@DebugClient@@UEAAJK@Z`
- size: `610`
- prototype: `__int64 __fastcall(DebugClient *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800797ec`
- `0x180099f30`
- `0x1800b94c4`
- `0x1800c6710`
- `0x1801a8f80`
- `0x1801a9138`
- `0x1801aa1f0`
- `0x18028c2dc`
- `0x1802aa190`
- `0x1802bdf98`
- `0x18037a2cc`
- `0x1803f5eb0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_ctime64` at `0x1801aa24a`
- `api-ms-win-crt-time-l1-1-0!_ctime64` at `0x1801aa24a`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1801aa238`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1801aa238`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801aa2a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801aa2a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801aa423`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801aa423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801aa37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801aa39e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801aa37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801aa39e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1801aa3ec`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1801aa3ec`

## pseudocode

```c
__int64 __fastcall DebugClient::EndSession(DebugClient *this, unsigned int a2)
{
  DebugClient *v4; // rcx
  char *v5; // rax
  DebuggerMeasuresLogger *Instance; // rax
  bool v7; // dl
  unsigned int v9; // edi
  int v10; // edx
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  DWORD CurrentProcessId; // eax
  DWORD v18; // eax
  DebuggerMeasuresLogger *v19; // rax

  if ( a2 <= 4 )
  {
    if ( a2 == 3 )
    {
      while ( g_DbgRpcActiveServers )
        DbgRpcDeregisterActiveServer(g_DbgRpcActiveServers);
      Instance = DebuggerMeasuresLogger::GetInstance();
      v7 = 1;
      goto LABEL_9;
    }
    if ( a2 == 4 )
    {
      v4 = (DebugClient *)((char *)this - 8);
      if ( (*((_BYTE *)v4 + 164) & 1) != 0 )
      {
        DebugClient::Disable(v4);
        *((_QWORD *)this + 38) = _time64(0);
        v5 = _ctime64((const __time64_t *)this + 38);
        dprintf(L"%s disconnected at %hs", (char *)this + 176, v5);
        Instance = DebuggerMeasuresLogger::GetInstance();
        v7 = 0;
LABEL_9:
        DebuggerMeasuresLogger::EndCurrentSession(Instance, v7);
        return 0;
      }
      return 2147942487LL;
    }
    EnterCriticalSection(&g_EngineLock);
    v9 = 1;
    ++g_EngineNesting;
    if ( IsSecureMode() )
    {
      if ( g_Target )
      {
        if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) <= 1 )
        {
          v10 = *((_DWORD *)g_Target + 1027);
          if ( (unsigned int)(v10 - 1024) > 5 && v10 != 3143 )
          {
            v11 = -2147024891;
LABEL_35:
            FlushCallbacks();
            --g_EngineNesting;
            LeaveCriticalSection(&g_EngineLock);
            v19 = DebuggerMeasuresLogger::GetInstance();
            DebuggerMeasuresLogger::EndCurrentSession(v19, 0);
            return (unsigned int)v11;
          }
        }
      }
    }
    if ( g_EngineNesting >= 2 )
    {
      v11 = -2147024681;
      goto LABEL_35;
    }
    if ( g_AutoSaveSettings && !DebuggerSettings::s_settingsIgnoreDefaultConfig )
    {
      g_AutoSaveSettings = 0;
      if ( (int)DebuggerSettings::WriteSettingsToXML(0, 0) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v13, v12, v14, v15);
    }
    if ( a2 == 1 )
    {
      v16 = 0;
    }
    else
    {
      if ( a2 != 2 )
        goto LABEL_27;
      v16 = 1;
    }
    v11 = SeparateAllProcesses((char *)this - 8, v16);
    if ( v11 < 0 )
      goto LABEL_35;
LABEL_27:
    if ( (unsigned int)AnySystemProcesses(0) && (g_GlobalProcOptions & 1) == 0 )
    {
      CurrentProcessId = GetCurrentProcessId();
      ErrOut(L"(%d): FATAL ERROR: Exiting Debugger while debugging CSR\n", CurrentProcessId);
      v18 = GetCurrentProcessId();
      MEMORY[0]("(%d): FATAL ERROR: Exiting Debugger while debugging CSR\n", v18);
      if ( g_DebuggerPlatformId == 2 )
        MEMORY[0](6, 0, 0, 0, 0, 0);
      DebugBreak();
    }
    if ( a2 != 1 )
      v9 = (a2 != 2) + 2;
    DiscardSession(v9);
    v11 = 0;
    goto LABEL_35;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1801aa1f0  push    rbx
0x1801aa1f2  push    rbp
0x1801aa1f3  push    rdi
0x1801aa1f4  push    r14
0x1801aa1f6  sub     rsp, 48h
0x1801aa1fa  mov     ebp, edx
0x1801aa1fc  mov     r14, rcx
0x1801aa1ff  cmp     edx, 4
0x1801aa202  ja      loc_1801AA442
0x1801aa208  cmp     edx, 3
0x1801aa20b  jz      short loc_1801AA27D
0x1801aa20d  cmp     edx, 4
0x1801aa210  jnz     loc_1801AA2A2
0x1801aa216  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1801aa21a  lea     edi, [rdx-3]
0x1801aa21d  test    [rcx+0A4h], dil
0x1801aa224  jz      loc_1801AA442
0x1801aa22a  call    ?Disable@DebugClient@@QEAAXXZ; DebugClient::Disable(void)
0x1801aa22f  xor     ecx, ecx; Time
0x1801aa231  lea     rbx, [r14+130h]
0x1801aa238  call    cs:__imp__time64
0x1801aa23f  nop     dword ptr [rax+rax+00h]
0x1801aa244  mov     rcx, rbx; Time
0x1801aa247  mov     [rbx], rax
0x1801aa24a  call    cs:__imp__ctime64
0x1801aa251  nop     dword ptr [rax+rax+00h]
0x1801aa256  mov     r8, rax
0x1801aa259  lea     rdx, [r14+0B0h]
0x1801aa260  lea     rcx, aSDisconnectedA; "%s disconnected at %hs"
0x1801aa267  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801aa26c  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801aa271  xor     edx, edx
0x1801aa273  jmp     short loc_1801AA293
0x1801aa275  mov     rcx, rax; struct DbgRpcActiveServer *
0x1801aa278  call    ?DbgRpcDeregisterActiveServer@@YAXPEAUDbgRpcActiveServer@@@Z; DbgRpcDeregisterActiveServer(DbgRpcActiveServer *)
0x1801aa27d  mov     rax, cs:?g_DbgRpcActiveServers@@3PEAUDbgRpcActiveServer@@EA; DbgRpcActiveServer * g_DbgRpcActiveServers
0x1801aa284  test    rax, rax
0x1801aa287  jnz     short loc_1801AA275
0x1801aa289  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801aa28e  mov     edx, 1; bool
0x1801aa293  mov     rcx, rax; this
0x1801aa296  call    ?EndCurrentSession@DebuggerMeasuresLogger@@QEAAX_N@Z; DebuggerMeasuresLogger::EndCurrentSession(bool)
0x1801aa29b  xor     eax, eax
0x1801aa29d  jmp     loc_1801AA447
0x1801aa2a2  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801aa2a9  call    cs:__imp_EnterCriticalSection
0x1801aa2b0  nop     dword ptr [rax+rax+00h]
0x1801aa2b5  mov     edi, 1
0x1801aa2ba  add     cs:?g_EngineNesting@@3KA, edi; ulong g_EngineNesting
0x1801aa2c0  call    ?IsSecureMode@@YA_NXZ; IsSecureMode(void)
0x1801aa2c5  test    al, al
0x1801aa2c7  jz      short loc_1801AA305
0x1801aa2c9  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1801aa2d0  test    rcx, rcx
0x1801aa2d3  jz      short loc_1801AA305
0x1801aa2d5  mov     eax, [rcx+1008h]
0x1801aa2db  sub     eax, 2
0x1801aa2de  cmp     eax, edi
0x1801aa2e0  ja      short loc_1801AA305
0x1801aa2e2  mov     edx, [rcx+100Ch]
0x1801aa2e8  lea     eax, [rdx-400h]
0x1801aa2ee  cmp     eax, 5
0x1801aa2f1  jbe     short loc_1801AA305
0x1801aa2f3  cmp     edx, 0C47h
0x1801aa2f9  jz      short loc_1801AA305
0x1801aa2fb  mov     ebx, 80070005h
0x1801aa300  jmp     loc_1801AA411
0x1801aa305  cmp     cs:?g_EngineNesting@@3KA, 2; ulong g_EngineNesting
0x1801aa30c  jb      short loc_1801AA318
0x1801aa30e  mov     ebx, 800700D7h
0x1801aa313  jmp     loc_1801AA411
0x1801aa318  cmp     cs:?g_AutoSaveSettings@@3_NA, 0; bool g_AutoSaveSettings
0x1801aa31f  jz      short loc_1801AA343
0x1801aa321  cmp     cs:?s_settingsIgnoreDefaultConfig@DebuggerSettings@@0_NA, 0; bool DebuggerSettings::s_settingsIgnoreDefaultConfig
0x1801aa328  jnz     short loc_1801AA343
0x1801aa32a  xor     edx, edx; bool
0x1801aa32c  mov     cs:?g_AutoSaveSettings@@3_NA, 0; bool g_AutoSaveSettings
0x1801aa333  xor     ecx, ecx; unsigned __int16 *
0x1801aa335  call    ?WriteSettingsToXML@DebuggerSettings@@SAJPEBG_N@Z; DebuggerSettings::WriteSettingsToXML(ushort const *,bool)
0x1801aa33a  test    eax, eax
0x1801aa33c  jns     short loc_1801AA343
0x1801aa33e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801aa343  cmp     ebp, edi
0x1801aa345  jnz     short loc_1801AA34B
0x1801aa347  xor     edx, edx
0x1801aa349  jmp     short loc_1801AA352
0x1801aa34b  cmp     ebp, 2
0x1801aa34e  jnz     short loc_1801AA365
0x1801aa350  mov     edx, edi
0x1801aa352  lea     rcx, [r14-8]
0x1801aa356  call    ?SeparateAllProcesses@@YAJPEAVDebugClient@@W4SEPARATION_MODE@@@Z; SeparateAllProcesses(DebugClient *,SEPARATION_MODE)
0x1801aa35b  mov     ebx, eax
0x1801aa35d  test    eax, eax
0x1801aa35f  js      loc_1801AA411
0x1801aa365  xor     ecx, ecx; int
0x1801aa367  call    ?AnySystemProcesses@@YAHH@Z; AnySystemProcesses(int)
0x1801aa36c  test    eax, eax
0x1801aa36e  jz      loc_1801AA3F8
0x1801aa374  test    byte ptr cs:?g_GlobalProcOptions@@3KA, dil; ulong g_GlobalProcOptions
0x1801aa37b  jnz     short loc_1801AA3F8
0x1801aa37d  call    cs:__imp_GetCurrentProcessId
0x1801aa384  nop     dword ptr [rax+rax+00h]
0x1801aa389  mov     edx, eax
0x1801aa38b  lea     rcx, aDFatalErrorExi; "(%d): FATAL ERROR: Exiting Debugger whi"...
0x1801aa392  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801aa397  mov     rbx, cs:qword_18082DC10
0x1801aa39e  call    cs:__imp_GetCurrentProcessId
0x1801aa3a5  nop     dword ptr [rax+rax+00h]
0x1801aa3aa  mov     edx, eax
0x1801aa3ac  lea     rcx, aDFatalErrorExi_0; "(%d): FATAL ERROR: Exiting Debugger whi"...
0x1801aa3b3  mov     rax, rbx
0x1801aa3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa3bb  cmp     cs:?g_DebuggerPlatformId@@3KA, 2; ulong g_DebuggerPlatformId
0x1801aa3c2  jnz     short loc_1801AA3EC
0x1801aa3c4  mov     rax, cs:qword_18082DCC8
0x1801aa3cb  xor     edx, edx
0x1801aa3cd  mov     [rsp+68h+var_40], 0
0x1801aa3d6  xor     r9d, r9d
0x1801aa3d9  xor     r8d, r8d
0x1801aa3dc  mov     [rsp+68h+var_48], 0
0x1801aa3e4  lea     ecx, [rdx+6]
0x1801aa3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa3ec  call    cs:__imp_DebugBreak
0x1801aa3f3  nop     dword ptr [rax+rax+00h]
0x1801aa3f8  cmp     ebp, edi
0x1801aa3fa  jz      short loc_1801AA408
0x1801aa3fc  xor     edi, edi
0x1801aa3fe  cmp     ebp, 2
0x1801aa401  setnz   dil
0x1801aa405  add     edi, 2
0x1801aa408  mov     ecx, edi; unsigned int
0x1801aa40a  call    ?DiscardSession@@YAXK@Z; DiscardSession(ulong)
0x1801aa40f  xor     ebx, ebx
0x1801aa411  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1801aa416  dec     cs:?g_EngineNesting@@3KA; ulong g_EngineNesting
0x1801aa41c  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801aa423  call    cs:__imp_LeaveCriticalSection
0x1801aa42a  nop     dword ptr [rax+rax+00h]
0x1801aa42f  call    ?GetInstance@DebuggerMeasuresLogger@@SAPEAV1@XZ; DebuggerMeasuresLogger::GetInstance(void)
0x1801aa434  xor     edx, edx; bool
0x1801aa436  mov     rcx, rax; this
0x1801aa439  call    ?EndCurrentSession@DebuggerMeasuresLogger@@QEAAX_N@Z; DebuggerMeasuresLogger::EndCurrentSession(bool)
0x1801aa43e  mov     eax, ebx
0x1801aa440  jmp     short loc_1801AA447
0x1801aa442  mov     eax, 80070057h
0x1801aa447  add     rsp, 48h
0x1801aa44b  pop     r14
0x1801aa44d  pop     rdi
0x1801aa44e  pop     rbp
0x1801aa44f  pop     rbx
0x1801aa450  retn
```
