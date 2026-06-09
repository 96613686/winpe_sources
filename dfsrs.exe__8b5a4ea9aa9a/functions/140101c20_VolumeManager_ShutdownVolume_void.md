# VolumeManager::ShutdownVolume(void)

- ea: `0x140101c20`
- end: `0x14010210e`
- name: `?ShutdownVolume@VolumeManager@@UEAAXXZ`
- size: `1262`
- prototype: `void __fastcall(VolumeManager *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x14000c910`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001b620`
- `0x1400248ac`
- `0x140069770`
- `0x1400727e8`
- `0x1400f1628`
- `0x1400f16e4`
- `0x1400f6c1c`
- `0x140101c20`
- `0x1401b9494`
- `0x1401bf3d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140101e8f`
- `KERNEL32!LeaveCriticalSection` at `0x140101ea8`
- `KERNEL32!LeaveCriticalSection` at `0x140101e8f`
- `KERNEL32!LeaveCriticalSection` at `0x140101ea8`
- `KERNEL32!EnterCriticalSection` at `0x140101e07`
- `KERNEL32!EnterCriticalSection` at `0x140101ec1`
- `KERNEL32!EnterCriticalSection` at `0x140101e07`
- `KERNEL32!EnterCriticalSection` at `0x140101ec1`
- `KERNEL32!GetCurrentThreadId` at `0x140101d17`
- `KERNEL32!GetCurrentThreadId` at `0x140101d5b`
- `KERNEL32!GetCurrentThreadId` at `0x140101f09`
- `KERNEL32!GetCurrentThreadId` at `0x140101f2d`
- `KERNEL32!GetCurrentThreadId` at `0x140101d17`
- `KERNEL32!GetCurrentThreadId` at `0x140101d5b`
- `KERNEL32!GetCurrentThreadId` at `0x140101f09`
- `KERNEL32!GetCurrentThreadId` at `0x140101f2d`

## string_xrefs

- `0x140101e47`: `Update volumeInfoHistory`
- `0x140101de9`: `Changed state. volId:%? volPath:%? volState:%?`
- `0x140102062`: `Changed state. volId:%? volPath:%? volState:%?`
- `0x1401020d5`: `(Ignored) Canceled.  volId:%? volPath:%? volState:%? Error:%?`
- `0x140101cbc`: `Shutting down volume. volId:%? volPath:%? volState:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VolumeManager::ShutdownVolume(VolumeManager *this)
{
  __int64 v2; // rcx
  struct FrsStatus *v3; // rax
  __int64 v4; // rcx
  struct MonitorContext *v5; // rbx
  struct MonitorContext *v6; // rcx
  int v7; // ebx
  __int64 v8; // rcx
  struct FrsStatus *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  DWORD v12; // [rsp+38h] [rbp-A1h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-A1h]
  DWORD v14; // [rsp+38h] [rbp-A1h]
  DWORD v15; // [rsp+38h] [rbp-A1h]
  __int64 v16; // [rsp+50h] [rbp-89h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-81h] BYREF
  int v18; // [rsp+60h] [rbp-79h]
  const wchar_t *v19; // [rsp+68h] [rbp-71h] BYREF
  int v20; // [rsp+70h] [rbp-69h]
  int v21; // [rsp+74h] [rbp-65h]
  const wchar_t *v22; // [rsp+78h] [rbp-61h]
  __int64 v23; // [rsp+80h] [rbp-59h] BYREF
  void **v24; // [rsp+88h] [rbp-51h] BYREF
  __int64 v25; // [rsp+90h] [rbp-49h] BYREF
  __int64 v26; // [rsp+98h] [rbp-41h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-39h] BYREF
  const wchar_t *v28; // [rsp+A8h] [rbp-31h] BYREF
  int v29; // [rsp+B0h] [rbp-29h]
  int v30; // [rsp+B4h] [rbp-25h]
  const wchar_t *v31; // [rsp+B8h] [rbp-21h]
  const wchar_t *v32; // [rsp+C0h] [rbp-19h] BYREF
  int v33; // [rsp+C8h] [rbp-11h]
  int v34; // [rsp+CCh] [rbp-Dh]
  const wchar_t *v35; // [rsp+D0h] [rbp-9h]
  const wchar_t *v36; // [rsp+D8h] [rbp-1h] BYREF
  int v37; // [rsp+E0h] [rbp+7h]
  int v38; // [rsp+E4h] [rbp+Bh]
  const wchar_t *v39; // [rsp+E8h] [rbp+Fh]
  int v40; // [rsp+140h] [rbp+67h] BYREF
  int v41; // [rsp+148h] [rbp+6Fh] BYREF
  int v42; // [rsp+150h] [rbp+77h] BYREF
  struct FrsStatus *v43; // [rsp+158h] [rbp+7Fh] BYREF

  v43 = 0;
  ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (VolumeManager *)((char *)this + 592));
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v28 = L"VolumeManager::ShutdownVolume";
    v29 = 4763;
    v30 = 5;
    v31 = L"VLMG";
    v40 = *((_DWORD *)this + 108);
    v26 = *((_QWORD *)this + 22) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v28,
      (unsigned int)L"Shutting down volume. volId:%? volPath:%? volState:%?",
      (_DWORD)this + 184,
      (unsigned int)&v26,
      (__int64)&v40);
  }
  if ( *((_DWORD *)this + 108) == 1 )
    goto LABEL_17;
  if ( *((_DWORD *)this + 108) != 2 )
  {
    switch ( *((_DWORD *)this + 108) )
    {
      case 3:
      case 4:
        goto LABEL_17;
      case 5:
        CurrentThreadId = GetCurrentThreadId();
        v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v4,
                                   9451,
                                   0,
                                   3,
                                   "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                                   "VolumeManager::ShutdownVolume",
                                   4787,
                                   CurrentThreadId,
                                   0);
        goto LABEL_13;
      case 6:
        goto LABEL_17;
    }
    if ( (unsigned int)(*((_DWORD *)this + 108) - 7) <= 1 )
    {
      v12 = GetCurrentThreadId();
      v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v2,
                                 9450,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                                 "VolumeManager::ShutdownVolume",
                                 4780,
                                 v12,
                                 0);
LABEL_13:
      v43 = v3;
      goto LABEL_16;
    }
  }
  v3 = v43;
LABEL_16:
  if ( v3 )
    goto LABEL_41;
LABEL_17:
  *((_DWORD *)this + 108) = 5;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v32 = L"VolumeManager::ShutdownVolume";
    v33 = 4810;
    v34 = 5;
    v35 = L"VLMG";
    v41 = *((_DWORD *)this + 108);
    v27 = *((_QWORD *)this + 22) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v32,
      (unsigned int)L"Changed state. volId:%? volPath:%? volState:%?",
      (_DWORD)this + 184,
      (unsigned int)&v27,
      (__int64)&v41);
  }
  v5 = g_MonitorContext;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 288));
  *((_DWORD *)v5 + 70) = 1;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v36 = L"VolumeManager::ShutdownVolume";
    v37 = 4816;
    v38 = 5;
    v39 = L"VLMG";
    dbgobj::DbgPrint<unsigned short>(&v36, L"Update volumeInfoHistory");
  }
  *((_DWORD *)this + 104) = 1;
  StateHistory::Delete((struct MonitorContext *)((char *)g_MonitorContext + 224), (VolumeManager *)((char *)this + 296));
  v6 = g_MonitorContext;
  *((_DWORD *)g_MonitorContext + 70) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 288));
  v7 = --v18;
  LeaveCriticalSection(lpCriticalSection);
  VolumeManager::FinalizeVolumeManager(this);
  EnterCriticalSection(lpCriticalSection);
  v18 = v7 + 1;
  if ( *((_DWORD *)this + 108) != 1 )
  {
    if ( *((_DWORD *)this + 108) == 2 )
      goto LABEL_35;
    if ( *((_DWORD *)this + 108) != 3 && *((_DWORD *)this + 108) != 4 )
    {
      if ( *((_DWORD *)this + 108) == 5 )
        goto LABEL_35;
      if ( *((_DWORD *)this + 108) != 6 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 108) - 7) <= 1 )
        {
          v14 = GetCurrentThreadId();
          v9 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v8,
                                     9450,
                                     0,
                                     3,
                                     "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                                     "VolumeManager::ShutdownVolume",
                                     4859,
                                     v14,
                                     0);
          goto LABEL_34;
        }
LABEL_35:
        if ( *((_DWORD *)this + 188) )
        {
          v23 = 0;
          v11 = Config::ConfigInstance<Config::ContentSet>::Get((char *)this + 232);
          v23 = v11;
          FilePath::FilePath((FilePath *)&v24, (const unsigned __int16 *)(*(_QWORD *)(v11 + 280) + 18LL));
          FilePath::TrimLongPathChars((FilePath *)&v24);
          FrsEvent::Log(1073743832, v11 + 160, v25 + 18);
          v24 = &FilePath::`vftable';
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v25);
          ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v23);
        }
        *((_DWORD *)this + 108) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v19 = L"VolumeManager::ShutdownVolume";
          v20 = 4910;
          v21 = 5;
          v22 = L"VLMG";
          v42 = *((_DWORD *)this + 108);
          v16 = *((_QWORD *)this + 22) + 18LL;
          dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
            (unsigned int)&v19,
            (unsigned int)L"Changed state. volId:%? volPath:%? volState:%?",
            (_DWORD)this + 184,
            (unsigned int)&v16,
            (__int64)&v42);
        }
        goto LABEL_46;
      }
    }
  }
  v15 = GetCurrentThreadId();
  v9 = (struct FrsStatus *)FrsStatusList::PushNewError(
                             v10,
                             9455,
                             0,
                             3,
                             "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                             "VolumeManager::ShutdownVolume",
                             4874,
                             v15,
                             0);
LABEL_34:
  v43 = v9;
  if ( !v9 )
    goto LABEL_35;
LABEL_41:
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
  {
    v19 = L"VolumeManager::ShutdownVolume";
    v20 = 4915;
    v21 = 3;
    v22 = L"VLMG";
    v42 = *((_DWORD *)this + 108);
    v16 = *((_QWORD *)this + 22) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE,FrsStatus>(
      (unsigned int)&v19,
      (unsigned int)L"(Ignored) Canceled.  volId:%? volPath:%? volState:%? Error:%?",
      (_DWORD)this + 184,
      (unsigned int)&v16,
      (__int64)&v42,
      (__int64)v43);
  }
  CLEAR_ERROR(&v43);
LABEL_46:
  ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
}

```

## disassembly

```asm
0x140101c20  push    rbp
0x140101c22  push    rbx
0x140101c23  push    rsi
0x140101c24  push    rdi
0x140101c25  push    r12
0x140101c27  push    r13
0x140101c29  push    r14
0x140101c2b  push    r15
0x140101c2d  lea     rbp, [rsp-1Fh]
0x140101c32  sub     rsp, 0F8h
0x140101c39  mov     rdi, rcx
0x140101c3c  xor     esi, esi
0x140101c3e  mov     [rbp+57h+arg_18], rsi
0x140101c42  lea     rdx, [rcx+250h]; struct ScopedCS *
0x140101c49  lea     rcx, [rsp+130h+lpCriticalSection]; this
0x140101c4e  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140101c53  nop
0x140101c54  lea     r14d, [rsi+5]
0x140101c58  lea     r12, aVolumemanagerS_2; "VolumeManager::ShutdownVolume"
0x140101c5f  lea     r13, aVlmg; "VLMG"
0x140101c66  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140101c6d  test    rax, rax
0x140101c70  jz      short loc_140101CCC
0x140101c72  cmp     [rax+40h], esi
0x140101c75  jz      short loc_140101CCC
0x140101c77  cmp     [rax+38h], r14d
0x140101c7b  jl      short loc_140101CCC
0x140101c7d  mov     [rbp+57h+var_88], r12
0x140101c81  mov     [rbp+57h+var_80], 129Bh
0x140101c88  mov     [rbp+57h+var_7C], r14d
0x140101c8c  mov     [rbp+57h+var_78], r13
0x140101c90  mov     eax, [rdi+1B0h]
0x140101c96  mov     [rbp+57h+arg_0], eax
0x140101c99  mov     rax, [rdi+0B0h]
0x140101ca0  add     rax, 12h
0x140101ca4  mov     [rbp+57h+var_98], rax
0x140101ca8  lea     r8, [rdi+0B8h]
0x140101caf  lea     rax, [rbp+57h+arg_0]
0x140101cb3  mov     [rsp+130h+var_110], rax
0x140101cb8  lea     r9, [rbp+57h+var_98]
0x140101cbc  lea     rdx, aShuttingDownVo; "Shutting down volume. volId:%? volPath:"...
0x140101cc3  lea     rcx, [rbp+57h+var_88]
0x140101cc7  call    ??$DbgPrint@GU_GUID@@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x140101ccc  mov     ecx, [rdi+1B0h]
0x140101cd2  lea     rbx, aVolumemanagerS; "VolumeManager::ShutdownVolume"
0x140101cd9  mov     r15d, 3
0x140101cdf  sub     ecx, 1
0x140101ce2  jz      loc_140101D8C
0x140101ce8  sub     ecx, 1
0x140101ceb  jz      loc_140101D7F
0x140101cf1  sub     ecx, 1
0x140101cf4  jz      loc_140101D8C
0x140101cfa  sub     ecx, 1
0x140101cfd  jz      loc_140101D8C
0x140101d03  sub     ecx, 1
0x140101d06  jz      short loc_140101D5B
0x140101d08  sub     ecx, 1
0x140101d0b  jz      short loc_140101D8C
0x140101d0d  sub     ecx, 1
0x140101d10  jz      short loc_140101D17
0x140101d12  cmp     ecx, 1
0x140101d15  jnz     short loc_140101D7F
0x140101d17  call    cs:__imp_GetCurrentThreadId
0x140101d1e  nop     dword ptr [rax+rax+00h]
0x140101d23  mov     [rsp+130h+var_F0], rsi
0x140101d28  mov     [rsp+130h+var_F8], eax
0x140101d2c  mov     [rsp+130h+var_100], 12ACh
0x140101d34  mov     edx, 24EAh
0x140101d39  mov     [rsp+130h+var_108], rbx
0x140101d3e  lea     rax, aBaseFsRemotefs_105; "base\\fs\\remotefs\\frs\\src\\sync\\vol"...
0x140101d45  xor     r8d, r8d
0x140101d48  mov     r9d, r15d
0x140101d4b  mov     [rsp+130h+var_110], rax
0x140101d50  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140101d55  mov     [rbp+57h+arg_18], rax
0x140101d59  jmp     short loc_140101D83
0x140101d5b  call    cs:__imp_GetCurrentThreadId
0x140101d62  nop     dword ptr [rax+rax+00h]
0x140101d67  mov     [rsp+130h+var_F0], rsi
0x140101d6c  mov     [rsp+130h+var_F8], eax
0x140101d70  mov     [rsp+130h+var_100], 12B3h
0x140101d78  mov     edx, 24EBh
0x140101d7d  jmp     short loc_140101D39
0x140101d7f  mov     rax, [rbp+57h+arg_18]
0x140101d83  test    rax, rax
0x140101d86  jnz     loc_140102074
0x140101d8c  mov     [rdi+1B0h], r14d
0x140101d93  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140101d9a  test    rax, rax
0x140101d9d  jz      short loc_140101DF9
0x140101d9f  cmp     [rax+40h], esi
0x140101da2  jz      short loc_140101DF9
0x140101da4  cmp     [rax+38h], r14d
0x140101da8  jl      short loc_140101DF9
0x140101daa  mov     [rbp+57h+var_70], r12
0x140101dae  mov     [rbp+57h+var_68], 12CAh
0x140101db5  mov     [rbp+57h+var_64], r14d
0x140101db9  mov     [rbp+57h+var_60], r13
0x140101dbd  mov     eax, [rdi+1B0h]
0x140101dc3  mov     [rbp+57h+arg_8], eax
0x140101dc6  mov     rax, [rdi+0B0h]
0x140101dcd  add     rax, 12h
0x140101dd1  mov     [rbp+57h+var_90], rax
0x140101dd5  lea     r8, [rdi+0B8h]
0x140101ddc  lea     rax, [rbp+57h+arg_8]
0x140101de0  mov     [rsp+130h+var_110], rax
0x140101de5  lea     r9, [rbp+57h+var_90]
0x140101de9  lea     rdx, aChangedStateVo; "Changed state. volId:%? volPath:%? volS"...
0x140101df0  lea     rcx, [rbp+57h+var_70]
0x140101df4  call    ??$DbgPrint@GU_GUID@@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x140101df9  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x140101e00  lea     rcx, [rbx+120h]; lpCriticalSection
0x140101e07  call    cs:__imp_EnterCriticalSection
0x140101e0e  nop     dword ptr [rax+rax+00h]
0x140101e13  mov     dword ptr [rbx+118h], 1
0x140101e1d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140101e24  test    rax, rax
0x140101e27  jz      short loc_140101E57
0x140101e29  cmp     [rax+40h], esi
0x140101e2c  jz      short loc_140101E57
0x140101e2e  cmp     [rax+38h], r14d
0x140101e32  jl      short loc_140101E57
0x140101e34  mov     [rbp+57h+var_58], r12
0x140101e38  mov     [rbp+57h+var_50], 12D0h
0x140101e3f  mov     [rbp+57h+var_4C], r14d
0x140101e43  mov     [rbp+57h+var_48], r13
0x140101e47  lea     rdx, aUpdateVolumein; "Update volumeInfoHistory"
0x140101e4e  lea     rcx, [rbp+57h+var_58]
0x140101e52  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140101e57  mov     dword ptr [rdi+1A0h], 1
0x140101e61  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x140101e68  add     rcx, 0E0h; this
0x140101e6f  lea     rdx, [rdi+128h]; struct HistoryRecord *
0x140101e76  call    ?Delete@StateHistory@@MEAAXPEAVHistoryRecord@@@Z; StateHistory::Delete(HistoryRecord *)
0x140101e7b  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x140101e82  mov     [rcx+118h], esi
0x140101e88  add     rcx, 120h; lpCriticalSection
0x140101e8f  call    cs:__imp_LeaveCriticalSection
0x140101e96  nop     dword ptr [rax+rax+00h]
0x140101e9b  mov     ebx, [rbp+57h+var_D0]
0x140101e9e  dec     ebx
0x140101ea0  mov     [rbp+57h+var_D0], ebx
0x140101ea3  mov     rcx, [rsp+130h+lpCriticalSection]; lpCriticalSection
0x140101ea8  call    cs:__imp_LeaveCriticalSection
0x140101eaf  nop     dword ptr [rax+rax+00h]
0x140101eb4  mov     rcx, rdi; this
0x140101eb7  call    ?FinalizeVolumeManager@VolumeManager@@IEAAXXZ; VolumeManager::FinalizeVolumeManager(void)
0x140101ebc  mov     rcx, [rsp+130h+lpCriticalSection]; lpCriticalSection
0x140101ec1  call    cs:__imp_EnterCriticalSection
0x140101ec8  nop     dword ptr [rax+rax+00h]
0x140101ecd  lea     eax, [rbx+1]
0x140101ed0  mov     [rbp+57h+var_D0], eax
0x140101ed3  mov     ecx, [rdi+1B0h]
0x140101ed9  sub     ecx, 1
0x140101edc  jz      short loc_140101F2D
0x140101ede  sub     ecx, 1
0x140101ee1  jz      loc_140101F7F
0x140101ee7  sub     ecx, 1
0x140101eea  jz      short loc_140101F2D
0x140101eec  sub     ecx, 1
0x140101eef  jz      short loc_140101F2D
0x140101ef1  sub     ecx, 1
0x140101ef4  jz      loc_140101F7F
0x140101efa  sub     ecx, 1
0x140101efd  jz      short loc_140101F2D
0x140101eff  sub     ecx, 1
0x140101f02  jz      short loc_140101F09
0x140101f04  cmp     ecx, 1
0x140101f07  jnz     short loc_140101F7F
0x140101f09  call    cs:__imp_GetCurrentThreadId
0x140101f10  nop     dword ptr [rax+rax+00h]
0x140101f15  mov     [rsp+130h+var_F0], rsi
0x140101f1a  mov     [rsp+130h+var_F8], eax
0x140101f1e  mov     [rsp+130h+var_100], 12FBh
0x140101f26  mov     edx, 24EAh
0x140101f2b  jmp     short loc_140101F4F
0x140101f2d  call    cs:__imp_GetCurrentThreadId
0x140101f34  nop     dword ptr [rax+rax+00h]
0x140101f39  mov     [rsp+130h+var_F0], rsi
0x140101f3e  mov     [rsp+130h+var_F8], eax
0x140101f42  mov     [rsp+130h+var_100], 130Ah
0x140101f4a  mov     edx, 24EFh
0x140101f4f  lea     rax, aVolumemanagerS; "VolumeManager::ShutdownVolume"
0x140101f56  mov     [rsp+130h+var_108], rax
0x140101f5b  lea     rax, aBaseFsRemotefs_105; "base\\fs\\remotefs\\frs\\src\\sync\\vol"...
0x140101f62  mov     [rsp+130h+var_110], rax
0x140101f67  mov     r9d, r15d
0x140101f6a  xor     r8d, r8d
0x140101f6d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140101f72  mov     [rbp+57h+arg_18], rax
0x140101f76  test    rax, rax
0x140101f79  jnz     loc_140102074
0x140101f7f  cmp     [rdi+2F0h], esi
0x140101f85  jz      short loc_140101FF4
0x140101f87  mov     [rbp+57h+var_B0], rsi
0x140101f8b  lea     rcx, [rdi+0E8h]
0x140101f92  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x140101f97  mov     rbx, rax
0x140101f9a  mov     [rbp+57h+var_B0], rax
0x140101f9e  mov     rdx, [rax+118h]
0x140101fa5  add     rdx, 12h; unsigned __int16 *
0x140101fa9  lea     rcx, [rbp+57h+var_A8]; this
0x140101fad  call    ??0FilePath@@QEAA@PEBG@Z; FilePath::FilePath(ushort const *)
0x140101fb2  nop
0x140101fb3  lea     rcx, [rbp+57h+var_A8]; this
0x140101fb7  call    ?TrimLongPathChars@FilePath@@QEAAXXZ; FilePath::TrimLongPathChars(void)
0x140101fbc  mov     r8, [rbp+57h+var_A0]
0x140101fc0  add     r8, 12h
0x140101fc4  lea     rdx, [rbx+0A0h]
0x140101fcb  mov     ecx, 400007D8h
0x140101fd0  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum2@@PEBG1@Z; FrsEvent::Log(FrsEventsEnum2,ushort const *,ushort const *)
0x140101fd5  nop
0x140101fd6  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140101fdd  mov     [rbp+57h+var_A8], rax
0x140101fe1  lea     rcx, [rbp+57h+var_A0]
0x140101fe5  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140101fea  nop
0x140101feb  lea     rcx, [rbp+57h+var_B0]
0x140101fef  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x140101ff4  mov     dword ptr [rdi+1B0h], 1
0x140101ffe  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140102005  test    rax, rax
0x140102008  jz      loc_1401020EF
0x14010200e  cmp     [rax+40h], esi
0x140102011  jz      loc_1401020EF
0x140102017  cmp     [rax+38h], r14d
0x14010201b  jl      loc_1401020EF
0x140102021  mov     [rbp+57h+var_C8], r12
0x140102025  mov     [rbp+57h+var_C0], 132Eh
0x14010202c  mov     [rbp+57h+var_BC], r14d
0x140102030  mov     [rbp+57h+var_B8], r13
0x140102034  mov     eax, [rdi+1B0h]
0x14010203a  mov     [rbp+57h+arg_10], eax
0x14010203d  mov     rax, [rdi+0B0h]
0x140102044  add     rax, 12h
0x140102048  mov     [rsp+130h+var_E0], rax
0x14010204d  lea     r8, [rdi+0B8h]
0x140102054  lea     rax, [rbp+57h+arg_10]
0x140102058  mov     [rsp+130h+var_110], rax
0x14010205d  lea     r9, [rsp+130h+var_E0]
0x140102062  lea     rdx, aChangedStateVo; "Changed state. volId:%? volPath:%? volS"...
0x140102069  lea     rcx, [rbp+57h+var_C8]
0x14010206d  call    ??$DbgPrint@GU_GUID@@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x140102072  jmp     short loc_1401020EF
0x140102074  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14010207b  test    rax, rax
0x14010207e  jz      short loc_1401020E5
0x140102080  cmp     [rax+40h], esi
0x140102083  jz      short loc_1401020E5
0x140102085  cmp     [rax+38h], r15d
0x140102089  jl      short loc_1401020E5
0x14010208b  mov     [rbp+57h+var_C8], r12
0x14010208f  mov     [rbp+57h+var_C0], 1333h
0x140102096  mov     [rbp+57h+var_BC], r15d
0x14010209a  mov     [rbp+57h+var_B8], r13
0x14010209e  mov     eax, [rdi+1B0h]
0x1401020a4  mov     [rbp+57h+arg_10], eax
0x1401020a7  mov     rax, [rdi+0B0h]
0x1401020ae  add     rax, 12h
0x1401020b2  mov     [rsp+130h+var_E0], rax
0x1401020b7  lea     r8, [rdi+0B8h]
0x1401020be  mov     rax, [rbp+57h+arg_18]
0x1401020c2  mov     [rsp+130h+var_108], rax
0x1401020c7  lea     rax, [rbp+57h+arg_10]
0x1401020cb  mov     [rsp+130h+var_110], rax
0x1401020d0  lea     r9, [rsp+130h+var_E0]
0x1401020d5  lea     rdx, aIgnoredCancele; "(Ignored) Canceled.  volId:%? volPath:%"...
0x1401020dc  lea     rcx, [rbp+57h+var_C8]
0x1401020e0  call    ??$DbgPrint@GU_GUID@@PEBGW4VOLUME_STATE@BaseVolumeManager@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE,FrsStatus>(ushort const *,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &,FrsStatus const &)
0x1401020e5  lea     rcx, [rbp+57h+arg_18]; struct FrsStatus **
0x1401020e9  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401020ee  nop
0x1401020ef  lea     rcx, [rsp+130h+lpCriticalSection]; this
0x1401020f4  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x1401020f9  add     rsp, 0F8h
0x140102100  pop     r15
0x140102102  pop     r14
0x140102104  pop     r13
0x140102106  pop     r12
0x140102108  pop     rdi
0x140102109  pop     rsi
0x14010210a  pop     rbx
0x14010210b  pop     rbp
0x14010210c  retn
```
