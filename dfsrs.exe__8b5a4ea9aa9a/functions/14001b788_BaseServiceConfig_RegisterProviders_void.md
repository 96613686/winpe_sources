# BaseServiceConfig::RegisterProviders(void)

- ea: `0x14001b788`
- end: `0x14001bcfa`
- name: `?RegisterProviders@BaseServiceConfig@@QEAAPEAVFrsStatus@@XZ`
- size: `1394`
- prototype: `struct FrsStatus *__fastcall(BaseServiceConfig *__hidden this)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14000dfa0`
- `0x14000f35c`
- `0x14000fad0`
- `0x140010fe0`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cb00`
- `0x14000eaa0`
- `0x14001b620`
- `0x14001b788`
- `0x14003a858`
- `0x1400c8e18`
- `0x1400c8ea4`
- `0x1401af7c0`
- `0x1401b8fb0`
- `0x1401b9494`
- `0x1401ba178`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001b8cd`
- `KERNEL32!GetCurrentThreadId` at `0x14001ba6c`
- `KERNEL32!GetCurrentThreadId` at `0x14001bc1e`
- `KERNEL32!GetCurrentThreadId` at `0x14001b8cd`
- `KERNEL32!GetCurrentThreadId` at `0x14001ba6c`
- `KERNEL32!GetCurrentThreadId` at `0x14001bc1e`

## string_xrefs

- `0x14001b8f6`: `base\fs\remotefs\frs\src\main\baseserviceconfig.cpp`
- `0x14001ba95`: `base\fs\remotefs\frs\src\main\baseserviceconfig.cpp`
- `0x14001bc47`: `base\fs\remotefs\frs\src\main\baseserviceconfig.cpp`
- `0x14001b7d4`: `BaseServiceConfig::RegisterProviders`
- `0x14001b994`: `BaseServiceConfig::RegisterProviders`
- `0x14001b9ee`: `BaseServiceConfig::RegisterProviders`
- `0x14001bacf`: `BaseServiceConfig::RegisterProviders`
- `0x14001bb3a`: `BaseServiceConfig::RegisterProviders`
- `0x14001bba3`: `BaseServiceConfig::RegisterProviders`
- `0x14001bc86`: `BaseServiceConfig::RegisterProviders`
- `0x14001b819`: `Registering the Configuration Provider`
- `0x14001b877`: `Failed to register Configuration Provider, retry. Error:0x%x`
- `0x14001b8ea`: `BaseServiceConfig::RegisterProviders`
- `0x14001ba89`: `BaseServiceConfig::RegisterProviders`
- `0x14001bc3b`: `BaseServiceConfig::RegisterProviders`
- `0x14001b955`: `Successfully registered Configuration Provider with WMI`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall BaseServiceConfig::RegisterProviders(BaseServiceConfig *this)
{
  __int64 v2; // rbx
  int v3; // r15d
  ConfigManager *v4; // r14
  const wchar_t *v5; // r12
  LPCRITICAL_SECTION v6; // rax
  signed int v7; // eax
  unsigned __int16 v8; // cx
  bool v9; // sf
  const wchar_t **v10; // rax
  const wchar_t *v11; // rbx
  Dword *v12; // rax
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  signed int v15; // eax
  unsigned __int16 v16; // cx
  const wchar_t **v17; // rax
  const wchar_t *v18; // rbx
  Dword *v19; // rax
  DWORD v20; // eax
  __int64 v21; // rcx
  signed int v22; // eax
  const wchar_t **v23; // rax
  Dword *v24; // rax
  DWORD v25; // eax
  __int64 v26; // rcx
  unsigned int v28; // [rsp+58h] [rbp-29h] BYREF
  void *Block; // [rsp+60h] [rbp-21h] BYREF
  const wchar_t *v30; // [rsp+68h] [rbp-19h] BYREF
  int v31; // [rsp+70h] [rbp-11h]
  int v32; // [rsp+74h] [rbp-Dh]
  const wchar_t *v33; // [rsp+78h] [rbp-9h]
  const wchar_t *v34; // [rsp+80h] [rbp-1h] BYREF
  int v35; // [rsp+88h] [rbp+7h]
  int v36; // [rsp+8Ch] [rbp+Bh]
  const wchar_t *v37; // [rsp+90h] [rbp+Fh]

  v2 = 0;
  v28 = 0;
  v3 = 0;
  v4 = (BaseServiceConfig *)((char *)this + 8);
  v5 = &pServiceName;
  v6 = g_DebugLog;
  if ( *((_DWORD *)this + 2) )
    goto LABEL_19;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v30 = L"BaseServiceConfig::RegisterProviders";
    v31 = 332;
    v32 = 5;
    v33 = L"SCFG";
    dbgobj::DbgPrint<unsigned short>(&v30, L"Registering the Configuration Provider");
  }
  v7 = ConfigManager::Register(v4);
  v8 = v7;
  v28 = v7;
  v9 = v7 < 0;
  v6 = g_DebugLog;
  if ( !v9 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = L"BaseServiceConfig::RegisterProviders";
      v31 = 342;
      v32 = 4;
      v33 = L"SCFG";
      dbgobj::DbgPrint<unsigned short>(&v30, L"Successfully registered Configuration Provider with WMI");
      v6 = g_DebugLog;
    }
    goto LABEL_19;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
  {
    v30 = L"BaseServiceConfig::RegisterProviders";
    v31 = 335;
    v32 = 3;
    v33 = L"SCFG";
    dbgobj::DbgPrint<unsigned short,unsigned int>(
      &v30,
      L"Failed to register Configuration Provider, retry. Error:0x%x",
      &v28);
    v8 = v28;
  }
  v10 = (const wchar_t **)W32ErrorString::W32ErrorString((W32ErrorString *)&Block, v8);
  v11 = &pServiceName;
  if ( *v10 )
    v11 = *v10;
  v12 = Dword::Dword((Dword *)&v34, v28, 10);
  FrsEvent::Log(3221231576LL, v12, v11);
  operator delete[](Block);
  CurrentThreadId = GetCurrentThreadId();
  v2 = FrsStatusList::PushNewError(
         v14,
         v28,
         0,
         4,
         "base\\fs\\remotefs\\frs\\src\\main\\baseserviceconfig.cpp",
         "BaseServiceConfig::RegisterProviders",
         339,
         CurrentThreadId,
         0);
  v6 = g_DebugLog;
  if ( !v2 )
  {
LABEL_19:
    if ( !*((_DWORD *)this + 160) )
    {
      if ( v6 && LODWORD(v6[1].LockSemaphore) && SLODWORD(v6[1].OwningThread) >= 5 )
      {
        v34 = L"BaseServiceConfig::RegisterProviders";
        v35 = 350;
        v36 = 5;
        v37 = L"SCFG";
        dbgobj::DbgPrint<unsigned short>(&v34, L"Registering the Monitoring Provider");
      }
      v15 = MonitorManager::Register((BaseServiceConfig *)((char *)this + 640));
      v16 = v15;
      v28 = v15;
      v9 = v15 < 0;
      v6 = g_DebugLog;
      if ( v9 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v34 = L"BaseServiceConfig::RegisterProviders";
          v35 = 353;
          v36 = 3;
          v37 = L"SCFG";
          dbgobj::DbgPrint<unsigned short,unsigned int>(
            &v34,
            L"Failed to register Monitoring Provider, retry. Error:0x%x",
            &v28);
          v16 = v28;
        }
        v17 = (const wchar_t **)W32ErrorString::W32ErrorString((W32ErrorString *)&Block, v16);
        v18 = &pServiceName;
        if ( *v17 )
          v18 = *v17;
        v19 = Dword::Dword((Dword *)&v34, v28, 10);
        FrsEvent::Log(3221231576LL, v19, v18);
        operator delete[](Block);
        v20 = GetCurrentThreadId();
        v2 = FrsStatusList::PushNewError(
               v21,
               v28,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\main\\baseserviceconfig.cpp",
               "BaseServiceConfig::RegisterProviders",
               357,
               v20,
               0);
        v6 = g_DebugLog;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v34 = L"BaseServiceConfig::RegisterProviders";
          v35 = 360;
          v36 = 4;
          v37 = L"SCFG";
          dbgobj::DbgPrint<unsigned short>(&v34, L"Successfully registered Monitoring Provider with WMI");
          v6 = g_DebugLog;
        }
        v3 = 1;
      }
    }
  }
  if ( v2 )
    return (struct FrsStatus *)v2;
  if ( *((_DWORD *)this + 168) )
    goto LABEL_56;
  if ( v6 && LODWORD(v6[1].LockSemaphore) && SLODWORD(v6[1].OwningThread) >= 5 )
  {
    v34 = L"BaseServiceConfig::RegisterProviders";
    v35 = 370;
    v36 = 5;
    v37 = L"SCFG";
    dbgobj::DbgPrint<unsigned short>(&v34, L"Registering the WmiV2 Provider");
  }
  v22 = Wmiv2Manager::Register((BaseServiceConfig *)((char *)this + 672), v4, (BaseServiceConfig *)((char *)this + 640));
  v28 = v22;
  if ( v22 >= 0 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v34 = L"BaseServiceConfig::RegisterProviders";
      v35 = 380;
      v36 = 4;
      v37 = L"SCFG";
      dbgobj::DbgPrint<unsigned short>(&v34, L"Successfully registered WmiV2 Provider");
    }
    goto LABEL_56;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
  {
    v34 = L"BaseServiceConfig::RegisterProviders";
    v35 = 373;
    v36 = 3;
    v37 = L"SCFG";
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v34, L"Failed to register WmiV2 Provider, retry. Error:0x%x", &v28);
    LOWORD(v22) = v28;
  }
  v23 = (const wchar_t **)W32ErrorString::W32ErrorString((W32ErrorString *)&Block, (unsigned __int16)v22);
  if ( *v23 )
    v5 = *v23;
  v24 = Dword::Dword((Dword *)&v34, v28, 10);
  FrsEvent::Log(3221231576LL, v24, v5);
  operator delete[](Block);
  v25 = GetCurrentThreadId();
  v2 = FrsStatusList::PushNewError(
         v26,
         v28,
         0,
         4,
         "base\\fs\\remotefs\\frs\\src\\main\\baseserviceconfig.cpp",
         "BaseServiceConfig::RegisterProviders",
         377,
         v25,
         0);
  if ( !v2 )
  {
LABEL_56:
    if ( v3 )
      FrsEvent::Log(1073747926);
  }
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x14001b788  mov     rax, rsp
0x14001b78b  mov     [rax+10h], rbx
0x14001b78f  mov     [rax+18h], rsi
0x14001b793  mov     [rax+20h], rdi
0x14001b797  push    rbp
0x14001b798  push    r12
0x14001b79a  push    r13
0x14001b79c  push    r14
0x14001b79e  push    r15
0x14001b7a0  lea     rbp, [rax-5Fh]
0x14001b7a4  sub     rsp, 0B0h
0x14001b7ab  mov     rax, cs:__security_cookie
0x14001b7b2  xor     rax, rsp
0x14001b7b5  mov     [rbp+57h+var_28], rax
0x14001b7b9  mov     rsi, rcx
0x14001b7bc  xor     r13d, r13d
0x14001b7bf  mov     ebx, r13d
0x14001b7c2  mov     [rbp+57h+var_80], r13d
0x14001b7c6  mov     r15d, r13d
0x14001b7c9  lea     r14, [rcx+8]
0x14001b7cd  lea     r12, pServiceName
0x14001b7d4  lea     rdi, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001b7db  lea     rcx, aScfg; "SCFG"
0x14001b7e2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001b7e9  cmp     [r14], r13d
0x14001b7ec  jnz     loc_14001B973
0x14001b7f2  test    rax, rax
0x14001b7f5  jz      short loc_14001B829
0x14001b7f7  cmp     [rax+40h], r13d
0x14001b7fb  jz      short loc_14001B829
0x14001b7fd  cmp     dword ptr [rax+38h], 5
0x14001b801  jl      short loc_14001B829
0x14001b803  mov     [rbp+57h+var_70], rdi
0x14001b807  mov     [rbp+57h+var_68], 14Ch
0x14001b80e  mov     [rbp+57h+var_64], 5
0x14001b815  mov     [rbp+57h+var_60], rcx
0x14001b819  lea     rdx, aRegisteringThe_0; "Registering the Configuration Provider"
0x14001b820  lea     rcx, [rbp+57h+var_70]
0x14001b824  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14001b829  mov     rcx, r14; this
0x14001b82c  call    ?Register@ConfigManager@@QEAAJXZ; ConfigManager::Register(void)
0x14001b831  mov     ecx, eax
0x14001b833  mov     [rbp+57h+var_80], eax
0x14001b836  test    eax, eax
0x14001b838  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001b83f  jns     loc_14001B927
0x14001b845  test    rax, rax
0x14001b848  jz      short loc_14001B88A
0x14001b84a  cmp     [rax+40h], r13d
0x14001b84e  jz      short loc_14001B88A
0x14001b850  cmp     dword ptr [rax+38h], 3
0x14001b854  jl      short loc_14001B88A
0x14001b856  mov     [rbp+57h+var_70], rdi
0x14001b85a  mov     [rbp+57h+var_68], 14Fh
0x14001b861  mov     [rbp+57h+var_64], 3
0x14001b868  lea     rax, aScfg; "SCFG"
0x14001b86f  mov     [rbp+57h+var_60], rax
0x14001b873  lea     r8, [rbp+57h+var_80]
0x14001b877  lea     rdx, aFailedToRegist_8; "Failed to register Configuration Provid"...
0x14001b87e  lea     rcx, [rbp+57h+var_70]
0x14001b882  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14001b887  mov     ecx, [rbp+57h+var_80]
0x14001b88a  movzx   edx, cx; unsigned int
0x14001b88d  lea     rcx, [rbp+57h+Block]; this
0x14001b891  call    ??0W32ErrorString@@QEAA@K@Z; W32ErrorString::W32ErrorString(ulong)
0x14001b896  nop
0x14001b897  mov     rbx, r12
0x14001b89a  cmp     [rax], r13
0x14001b89d  cmovnz  rbx, [rax]
0x14001b8a1  mov     r8d, 0Ah; int
0x14001b8a7  mov     edx, [rbp+57h+var_80]; unsigned int
0x14001b8aa  lea     rcx, [rbp+57h+var_58]; this
0x14001b8ae  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x14001b8b3  mov     r8, rbx
0x14001b8b6  mov     rdx, rax
0x14001b8b9  mov     ecx, 0C00017D8h
0x14001b8be  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum2@@PEBG1@Z; FrsEvent::Log(FrsEventsEnum2,ushort const *,ushort const *)
0x14001b8c3  nop
0x14001b8c4  mov     rcx, [rbp+57h+Block]; Block
0x14001b8c8  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14001b8cd  call    cs:__imp_GetCurrentThreadId
0x14001b8d4  nop     dword ptr [rax+rax+00h]
0x14001b8d9  mov     [rsp+0D0h+var_90], r13
0x14001b8de  mov     dword ptr [rsp+0D0h+var_98], eax
0x14001b8e2  mov     [rsp+0D0h+var_A0], 153h
0x14001b8ea  lea     rax, aBaseservicecon_3; "BaseServiceConfig::RegisterProviders"
0x14001b8f1  mov     qword ptr [rsp+0D0h+var_A8], rax
0x14001b8f6  lea     rax, aBaseFsRemotefs_31; "base\\fs\\remotefs\\frs\\src\\main\\bas"...
0x14001b8fd  mov     [rsp+0D0h+var_B0], rax
0x14001b902  mov     r9d, 4
0x14001b908  xor     r8d, r8d
0x14001b90b  mov     edx, [rbp+57h+var_80]
0x14001b90e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14001b913  mov     rbx, rax
0x14001b916  test    rax, rax
0x14001b919  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001b920  jz      short loc_14001B96C
0x14001b922  jmp     loc_14001BB10
0x14001b927  test    rax, rax
0x14001b92a  jz      short loc_14001B96C
0x14001b92c  cmp     [rax+40h], r13d
0x14001b930  jz      short loc_14001B96C
0x14001b932  cmp     dword ptr [rax+38h], 4
0x14001b936  jl      short loc_14001B96C
0x14001b938  mov     [rbp+57h+var_70], rdi
0x14001b93c  mov     [rbp+57h+var_68], 156h
0x14001b943  mov     [rbp+57h+var_64], 4
0x14001b94a  lea     rax, aScfg; "SCFG"
0x14001b951  mov     [rbp+57h+var_60], rax
0x14001b955  lea     rdx, aSuccessfullyRe; "Successfully registered Configuration P"...
0x14001b95c  lea     rcx, [rbp+57h+var_70]
0x14001b960  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14001b965  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001b96c  lea     rcx, aScfg; "SCFG"
0x14001b973  lea     rdi, [rsi+280h]
0x14001b97a  cmp     [rdi], r13d
0x14001b97d  jnz     loc_14001BB10
0x14001b983  test    rax, rax
0x14001b986  jz      short loc_14001B9C1
0x14001b988  cmp     [rax+40h], r13d
0x14001b98c  jz      short loc_14001B9C1
0x14001b98e  cmp     dword ptr [rax+38h], 5
0x14001b992  jl      short loc_14001B9C1
0x14001b994  lea     rax, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001b99b  mov     [rbp+57h+var_58], rax
0x14001b99f  mov     [rbp+57h+var_50], 15Eh
0x14001b9a6  mov     [rbp+57h+var_4C], 5
0x14001b9ad  mov     [rbp+57h+var_48], rcx
0x14001b9b1  lea     rdx, aRegisteringThe; "Registering the Monitoring Provider"
0x14001b9b8  lea     rcx, [rbp+57h+var_58]
0x14001b9bc  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14001b9c1  mov     rcx, rdi; this
0x14001b9c4  call    ?Register@MonitorManager@@QEAAJXZ; MonitorManager::Register(void)
0x14001b9c9  mov     ecx, eax
0x14001b9cb  mov     [rbp+57h+var_80], eax
0x14001b9ce  test    eax, eax
0x14001b9d0  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001b9d7  jns     loc_14001BABE
0x14001b9dd  test    rax, rax
0x14001b9e0  jz      short loc_14001BA29
0x14001b9e2  cmp     [rax+40h], r13d
0x14001b9e6  jz      short loc_14001BA29
0x14001b9e8  cmp     dword ptr [rax+38h], 3
0x14001b9ec  jl      short loc_14001BA29
0x14001b9ee  lea     rax, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001b9f5  mov     [rbp+57h+var_58], rax
0x14001b9f9  mov     [rbp+57h+var_50], 161h
0x14001ba00  mov     [rbp+57h+var_4C], 3
0x14001ba07  lea     rax, aScfg; "SCFG"
0x14001ba0e  mov     [rbp+57h+var_48], rax
0x14001ba12  lea     r8, [rbp+57h+var_80]
0x14001ba16  lea     rdx, aFailedToRegist_0; "Failed to register Monitoring Provider,"...
0x14001ba1d  lea     rcx, [rbp+57h+var_58]
0x14001ba21  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14001ba26  mov     ecx, [rbp+57h+var_80]
0x14001ba29  movzx   edx, cx; unsigned int
0x14001ba2c  lea     rcx, [rbp+57h+Block]; this
0x14001ba30  call    ??0W32ErrorString@@QEAA@K@Z; W32ErrorString::W32ErrorString(ulong)
0x14001ba35  nop
0x14001ba36  mov     rbx, r12
0x14001ba39  cmp     [rax], r13
0x14001ba3c  cmovnz  rbx, [rax]
0x14001ba40  mov     r8d, 0Ah; int
0x14001ba46  mov     edx, [rbp+57h+var_80]; unsigned int
0x14001ba49  lea     rcx, [rbp+57h+var_58]; this
0x14001ba4d  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x14001ba52  mov     r8, rbx
0x14001ba55  mov     rdx, rax
0x14001ba58  mov     ecx, 0C00017D8h
0x14001ba5d  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum2@@PEBG1@Z; FrsEvent::Log(FrsEventsEnum2,ushort const *,ushort const *)
0x14001ba62  nop
0x14001ba63  mov     rcx, [rbp+57h+Block]; Block
0x14001ba67  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14001ba6c  call    cs:__imp_GetCurrentThreadId
0x14001ba73  nop     dword ptr [rax+rax+00h]
0x14001ba78  mov     [rsp+0D0h+var_90], r13
0x14001ba7d  mov     dword ptr [rsp+0D0h+var_98], eax
0x14001ba81  mov     [rsp+0D0h+var_A0], 165h
0x14001ba89  lea     rax, aBaseservicecon_3; "BaseServiceConfig::RegisterProviders"
0x14001ba90  mov     qword ptr [rsp+0D0h+var_A8], rax
0x14001ba95  lea     rax, aBaseFsRemotefs_31; "base\\fs\\remotefs\\frs\\src\\main\\bas"...
0x14001ba9c  mov     [rsp+0D0h+var_B0], rax
0x14001baa1  mov     r9d, 4
0x14001baa7  xor     r8d, r8d
0x14001baaa  mov     edx, [rbp+57h+var_80]
0x14001baad  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14001bab2  mov     rbx, rax
0x14001bab5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001babc  jmp     short loc_14001BB10
0x14001babe  test    rax, rax
0x14001bac1  jz      short loc_14001BB0A
0x14001bac3  cmp     [rax+40h], r13d
0x14001bac7  jz      short loc_14001BB0A
0x14001bac9  cmp     dword ptr [rax+38h], 4
0x14001bacd  jl      short loc_14001BB0A
0x14001bacf  lea     rax, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001bad6  mov     [rbp+57h+var_58], rax
0x14001bada  mov     [rbp+57h+var_50], 168h
0x14001bae1  mov     [rbp+57h+var_4C], 4
0x14001bae8  lea     rax, aScfg; "SCFG"
0x14001baef  mov     [rbp+57h+var_48], rax
0x14001baf3  lea     rdx, aSuccessfullyRe_1; "Successfully registered Monitoring Prov"...
0x14001bafa  lea     rcx, [rbp+57h+var_58]
0x14001bafe  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14001bb03  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001bb0a  mov     r15d, 1
0x14001bb10  test    rbx, rbx
0x14001bb13  jnz     loc_14001BCC9
0x14001bb19  lea     rdi, [rsi+2A0h]
0x14001bb20  cmp     [rdi], r13d
0x14001bb23  jnz     loc_14001BCBA
0x14001bb29  test    rax, rax
0x14001bb2c  jz      short loc_14001BB6E
0x14001bb2e  cmp     [rax+40h], r13d
0x14001bb32  jz      short loc_14001BB6E
0x14001bb34  cmp     dword ptr [rax+38h], 5
0x14001bb38  jl      short loc_14001BB6E
0x14001bb3a  lea     rax, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001bb41  mov     [rbp+57h+var_58], rax
0x14001bb45  mov     [rbp+57h+var_50], 172h
0x14001bb4c  mov     [rbp+57h+var_4C], 5
0x14001bb53  lea     rax, aScfg; "SCFG"
0x14001bb5a  mov     [rbp+57h+var_48], rax
0x14001bb5e  lea     rdx, aRegisteringThe_1; "Registering the WmiV2 Provider"
0x14001bb65  lea     rcx, [rbp+57h+var_58]
0x14001bb69  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14001bb6e  lea     r8, [rsi+280h]; struct MonitorManager *
0x14001bb75  mov     rdx, r14; struct ConfigManager *
0x14001bb78  mov     rcx, rdi; this
0x14001bb7b  call    ?Register@Wmiv2Manager@@QEAAJPEAVConfigManager@@PEAVMonitorManager@@@Z; Wmiv2Manager::Register(ConfigManager *,MonitorManager *)
0x14001bb80  mov     [rbp+57h+var_80], eax
0x14001bb83  test    eax, eax
0x14001bb85  jns     loc_14001BC6E
0x14001bb8b  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001bb92  test    rcx, rcx
0x14001bb95  jz      short loc_14001BBDE
0x14001bb97  cmp     [rcx+40h], r13d
0x14001bb9b  jz      short loc_14001BBDE
0x14001bb9d  cmp     dword ptr [rcx+38h], 3
0x14001bba1  jl      short loc_14001BBDE
0x14001bba3  lea     rax, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001bbaa  mov     [rbp+57h+var_58], rax
0x14001bbae  mov     [rbp+57h+var_50], 175h
0x14001bbb5  mov     [rbp+57h+var_4C], 3
0x14001bbbc  lea     rax, aScfg; "SCFG"
0x14001bbc3  mov     [rbp+57h+var_48], rax
0x14001bbc7  lea     r8, [rbp+57h+var_80]
0x14001bbcb  lea     rdx, aFailedToRegist_7; "Failed to register WmiV2 Provider, retr"...
0x14001bbd2  lea     rcx, [rbp+57h+var_58]
0x14001bbd6  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14001bbdb  mov     eax, [rbp+57h+var_80]
0x14001bbde  movzx   edx, ax; unsigned int
0x14001bbe1  lea     rcx, [rbp+57h+Block]; this
0x14001bbe5  call    ??0W32ErrorString@@QEAA@K@Z; W32ErrorString::W32ErrorString(ulong)
0x14001bbea  nop
0x14001bbeb  cmp     [rax], r13
0x14001bbee  cmovnz  r12, [rax]
0x14001bbf2  mov     r8d, 0Ah; int
0x14001bbf8  mov     edx, [rbp+57h+var_80]; unsigned int
0x14001bbfb  lea     rcx, [rbp+57h+var_58]; this
0x14001bbff  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x14001bc04  mov     r8, r12
0x14001bc07  mov     rdx, rax
0x14001bc0a  mov     ecx, 0C00017D8h
0x14001bc0f  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum2@@PEBG1@Z; FrsEvent::Log(FrsEventsEnum2,ushort const *,ushort const *)
0x14001bc14  nop
0x14001bc15  mov     rcx, [rbp+57h+Block]; Block
0x14001bc19  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14001bc1e  call    cs:__imp_GetCurrentThreadId
0x14001bc25  nop     dword ptr [rax+rax+00h]
0x14001bc2a  mov     [rsp+0D0h+var_90], r13
0x14001bc2f  mov     dword ptr [rsp+0D0h+var_98], eax
0x14001bc33  mov     [rsp+0D0h+var_A0], 179h
0x14001bc3b  lea     rax, aBaseservicecon_3; "BaseServiceConfig::RegisterProviders"
0x14001bc42  mov     qword ptr [rsp+0D0h+var_A8], rax
0x14001bc47  lea     rax, aBaseFsRemotefs_31; "base\\fs\\remotefs\\frs\\src\\main\\bas"...
0x14001bc4e  mov     [rsp+0D0h+var_B0], rax
0x14001bc53  mov     r9d, 4
0x14001bc59  xor     r8d, r8d
0x14001bc5c  mov     edx, [rbp+57h+var_80]
0x14001bc5f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14001bc64  mov     rbx, rax
0x14001bc67  test    rax, rax
0x14001bc6a  jnz     short loc_14001BCC9
0x14001bc6c  jmp     short loc_14001BCBA
0x14001bc6e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001bc75  test    rax, rax
0x14001bc78  jz      short loc_14001BCBA
0x14001bc7a  cmp     [rax+40h], r13d
0x14001bc7e  jz      short loc_14001BCBA
0x14001bc80  cmp     dword ptr [rax+38h], 4
0x14001bc84  jl      short loc_14001BCBA
0x14001bc86  lea     rax, aBaseservicecon_1; "BaseServiceConfig::RegisterProviders"
0x14001bc8d  mov     [rbp+57h+var_58], rax
0x14001bc91  mov     [rbp+57h+var_50], 17Ch
0x14001bc98  mov     [rbp+57h+var_4C], 4
0x14001bc9f  lea     rax, aScfg; "SCFG"
0x14001bca6  mov     [rbp+57h+var_48], rax
0x14001bcaa  lea     rdx, aSuccessfullyRe_0; "Successfully registered WmiV2 Provider"
0x14001bcb1  lea     rcx, [rbp+57h+var_58]
  ... truncated ...
```
