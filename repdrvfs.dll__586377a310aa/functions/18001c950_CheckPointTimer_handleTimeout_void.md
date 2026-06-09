# CheckPointTimer::handleTimeout(void)

- ea: `0x18001c950`
- end: `0x18001cc43`
- name: `?handleTimeout@CheckPointTimer@@UEAAHXZ`
- size: `755`
- prototype: `__int64 __fastcall(CheckPointTimer *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001ad80`
- `0x18001c950`
- `0x18001d258`
- `0x18001d5f0`
- `0x18001d6b0`
- `0x180029fbc`
- `0x180038e38`
- `0x18003abac`
- `0x18003b9f8`
- `0x18003c16c`
- `0x18003c21c`
- `0x18003c8a0`
- `0x18003d050`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001cb9e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001cb9e`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18001c96f`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18001c96f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001cb32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cb07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cb07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ca93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ca93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cabb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb28`

## pseudocode

```c
__int64 __fastcall CheckPointTimer::handleTimeout(CheckPointTimer *this)
{
  unsigned int v2; // edx
  int v3; // r14d
  int v4; // esi
  BOOL v5; // edi
  char v6; // si
  signed int v7; // r14d
  __int64 v8; // rdx
  int v9; // r8d
  LSTATUS v10; // eax
  signed int v11; // ebx
  LSTATUS v12; // eax
  _BYTE v14[8]; // [rsp+60h] [rbp-19h] BYREF
  LSTATUS (__stdcall *v15)(HKEY); // [rsp+68h] [rbp-11h]
  HKEY v16; // [rsp+70h] [rbp-9h]
  _BYTE v17[8]; // [rsp+78h] [rbp-1h] BYREF
  LSTATUS (__stdcall *v18)(HKEY, LPCWSTR, REGSAM, DWORD); // [rsp+80h] [rbp+7h]
  HKEY v19; // [rsp+88h] [rbp+Fh]
  const WCHAR *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]
  DWORD dwDisposition; // [rsp+E8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+F0h] [rbp+77h] BYREF
  HKEY v24; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( !(unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    dwDisposition = 0;
    if ( _InterlockedIncrement(&CheckPointTimer::lCheckpointCalls) != 1 )
    {
LABEL_41:
      _InterlockedDecrement(&CheckPointTimer::lCheckpointCalls);
      return 0;
    }
    v3 = 0;
    v4 = CLock::WriteLock((CLock *)&g_readWriteLock, v2);
    v5 = v4 == 0;
    if ( !v4 )
    {
      ++*((_DWORD *)this + 16);
      if ( dword_180058AFC )
        CPageSource::Checkpoint((CPageSource *)qword_180058B00, *((_DWORD *)this + 16) / 0x3Cu);
    }
    if ( !v4 )
    {
      CLock::WriteUnlock((CLock *)&g_readWriteLock);
      v5 = 0;
    }
    if ( (CRepositoryCorruption::m_dwCorruptionType & 0x80u) == 0 )
    {
      v6 = 0;
      if ( !CRepositoryCorruption::m_dwCorruptionType && !CRepositoryCorruption::m_pPendingCorruptionReport )
        goto LABEL_14;
      v3 = 1;
    }
    else
    {
      v6 = 1;
    }
    _InterlockedExchange(&CRepositoryCorruption::m_bReportReadyToSend, 1);
LABEL_14:
    IsRestoreInProgress(&dwDisposition);
    if ( !dwDisposition && v3 )
    {
      v7 = CRepositoryCorruption::ReportCorruption(1);
      dwDisposition = 1;
      GetRestoreType(&dwDisposition, v8, v9);
      if ( dwDisposition == 1 )
      {
        hKey = 0;
        v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"software\\microsoft\\wbem\\cimom", 0, 0x2000000u, &hKey);
        v11 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            v11 = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          v11 = v7;
        }
        if ( v11 >= 0 )
        {
          v14[0] = 0;
          v15 = RegCloseKey;
          v16 = hKey;
          v24 = 0;
          dwDisposition = 0;
          v12 = RegCreateKeyExW(hKey, L"RepositoryRestoreInProgress", 0, 0, 1u, 0, 0, &v24, &dwDisposition);
          if ( v12 )
          {
            if ( v12 > 0 )
              v11 = (unsigned __int16)v12 | 0x80070000;
            else
              v11 = v12;
          }
          if ( v11 >= 0 )
          {
            RegCloseKey(v24);
            v17[0] = 0;
            v18 = RegDeleteKeyExW;
            v19 = hKey;
            v20 = L"RepositoryRestoreInProgress";
            v21 = 0;
            if ( (int)RestoreWMIRepository() >= 0 )
              v6 = 1;
            ScopeGuardImpl4<long (*)(HKEY__ *,unsigned short const *,unsigned long,unsigned long),HKEY__ *,unsigned short const *,int,int>::~ScopeGuardImpl4<long (*)(HKEY__ *,unsigned short const *,unsigned long,unsigned long),HKEY__ *,unsigned short const *,int,int>(v17);
          }
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(v14);
        }
      }
      else
      {
        SetRepositoryCheckOnStartup(1);
      }
    }
    if ( CRepositoryCorruption::m_bReportReadyToSend == 1 )
    {
      _InterlockedExchange(&CRepositoryCorruption::m_bReportReadyToSend, 0);
      CRepositoryCorruption::ReportCorruption(0);
      if ( CRepositoryCorruption::m_pPendingCorruptionReport )
      {
        CWin32DefaultArena::WbemMemFree(CRepositoryCorruption::m_pPendingCorruptionReport);
        CRepositoryCorruption::m_pPendingCorruptionReport = 0;
      }
      _InterlockedExchange(&CRepositoryCorruption::m_dwCorruptionType, 0);
      _InterlockedExchange(&CRepositoryCorruption::m_bCalledByStartup, 0);
      _InterlockedExchange((volatile __int32 *)&CRepositoryCorruption::m_dwImproperShutdownFlag, 0);
      _InterlockedExchange((volatile __int32 *)&CRepositoryCorruption::m_dwRecoverType, 0);
      if ( v6 )
        ReportFutureCorruption();
    }
    if ( 0x133F84CFE133F84DLL
       * ((__int64)(*((_QWORD *)&CRepositoryCorruption::m_aCorruptedBackup + 1)
                  - CRepositoryCorruption::m_aCorruptedBackup) >> 2) )
    {
      CRepositoryCorruption::ReportInconsistentBackupCorruption();
      *((_QWORD *)&CRepositoryCorruption::m_aCorruptedBackup + 1) = CRepositoryCorruption::m_aCorruptedBackup;
    }
    if ( v5 )
      CLock::WriteUnlock((CLock *)&g_readWriteLock);
    goto LABEL_41;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c950  mov     [rsp-8+arg_0], rbx
0x18001c955  push    rbp
0x18001c956  push    rsi
0x18001c957  push    rdi
0x18001c958  push    r12
0x18001c95a  push    r13
0x18001c95c  push    r14
0x18001c95e  push    r15
0x18001c960  lea     rbp, [rsp-27h]
0x18001c965  sub     rsp, 0A0h
0x18001c96c  mov     rbx, rcx
0x18001c96f  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18001c975  xor     r15d, r15d
0x18001c978  test    al, al
0x18001c97a  jnz     loc_18001CC26
0x18001c980  mov     [rbp+57h+dwDisposition], r15d
0x18001c984  lea     r12d, [r15+1]
0x18001c988  mov     eax, r12d
0x18001c98b  lock xadd cs:?lCheckpointCalls@CheckPointTimer@@2JC, eax; long volatile CheckPointTimer::lCheckpointCalls
0x18001c993  add     eax, r12d
0x18001c996  cmp     eax, r12d
0x18001c999  jnz     loc_18001CC1F
0x18001c99f  mov     r14d, r15d
0x18001c9a2  lea     r13, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18001c9a9  mov     [rbp+57h+var_80], r13
0x18001c9ad  mov     [rbp+57h+var_78], r15d
0x18001c9b1  mov     rcx, r13; this
0x18001c9b4  call    ?WriteLock@CLock@@QEAAHK@Z; CLock::WriteLock(ulong)
0x18001c9b9  mov     esi, eax
0x18001c9bb  mov     edi, r15d
0x18001c9be  test    eax, eax
0x18001c9c0  setz    dil
0x18001c9c4  mov     [rbp+57h+var_78], edi
0x18001c9c7  test    dil, dil
0x18001c9ca  jz      short loc_18001C9F3
0x18001c9cc  add     [rbx+40h], r12d
0x18001c9d0  mov     eax, 88888889h
0x18001c9d5  mul     dword ptr [rbx+40h]
0x18001c9d8  shr     edx, 5; bool
0x18001c9db  imul    eax, edx, 3Ch ; '<'
0x18001c9de  cmp     cs:dword_180058AFC, r15d
0x18001c9e5  jz      short loc_18001C9F3
0x18001c9e7  lea     rcx, qword_180058B00; this
0x18001c9ee  call    ?Checkpoint@CPageSource@@QEAAK_N@Z; CPageSource::Checkpoint(bool)
0x18001c9f3  test    esi, esi
0x18001c9f5  jnz     short loc_18001CA06
0x18001c9f7  mov     rcx, r13; this
0x18001c9fa  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x18001c9ff  mov     edi, r15d
0x18001ca02  mov     [rbp+57h+var_78], r15d
0x18001ca06  mov     eax, cs:?m_dwCorruptionType@CRepositoryCorruption@@2JA; long CRepositoryCorruption::m_dwCorruptionType
0x18001ca0c  test    al, al
0x18001ca0e  jns     short loc_18001CA15
0x18001ca10  mov     sil, r12b
0x18001ca13  jmp     short loc_18001CA28
0x18001ca15  mov     sil, r15b
0x18001ca18  test    eax, eax
0x18001ca1a  jnz     short loc_18001CA25
0x18001ca1c  cmp     cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA, r15; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18001ca23  jz      short loc_18001CA31
0x18001ca25  mov     r14d, r12d
0x18001ca28  mov     eax, r12d
0x18001ca2b  xchg    eax, cs:?m_bReportReadyToSend@CRepositoryCorruption@@2JA; long CRepositoryCorruption::m_bReportReadyToSend
0x18001ca31  lea     rcx, [rbp+57h+dwDisposition]; unsigned int *
0x18001ca35  call    ?IsRestoreInProgress@@YAJAEAK@Z; IsRestoreInProgress(ulong &)
0x18001ca3a  cmp     [rbp+57h+dwDisposition], r15d
0x18001ca3e  jnz     loc_18001CB79
0x18001ca44  test    r14d, r14d
0x18001ca47  jz      loc_18001CB79
0x18001ca4d  mov     cl, r12b; bool
0x18001ca50  call    ?ReportCorruption@CRepositoryCorruption@@SAJ_N@Z; CRepositoryCorruption::ReportCorruption(bool)
0x18001ca55  mov     r14d, eax
0x18001ca58  mov     [rbp+57h+dwDisposition], r12d
0x18001ca5c  lea     rcx, [rbp+57h+dwDisposition]; unsigned int *
0x18001ca60  call    ?GetRestoreType@@YAJAEAK@Z; GetRestoreType(ulong &)
0x18001ca65  cmp     [rbp+57h+dwDisposition], r12d
0x18001ca69  jnz     loc_18001CB71
0x18001ca6f  mov     [rbp+57h+hKey], r15
0x18001ca73  lea     rax, [rbp+57h+hKey]
0x18001ca77  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001ca7c  mov     r9d, 2000000h; samDesired
0x18001ca82  xor     r8d, r8d; ulOptions
0x18001ca85  lea     rdx, SubKey; "software\\microsoft\\wbem\\cimom"
0x18001ca8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ca93  call    cs:__imp_RegOpenKeyExW
0x18001ca99  mov     ebx, eax
0x18001ca9b  test    eax, eax
0x18001ca9d  jz      short loc_18001CAAC
0x18001ca9f  jle     short loc_18001CAAF
0x18001caa1  movzx   ebx, ax
0x18001caa4  or      ebx, 80070000h
0x18001caaa  jmp     short loc_18001CAAF
0x18001caac  mov     ebx, r14d
0x18001caaf  test    ebx, ebx
0x18001cab1  js      loc_18001CB79
0x18001cab7  mov     rcx, [rbp+57h+hKey]; hKey
0x18001cabb  mov     rax, cs:__imp_RegCloseKey
0x18001cac2  mov     [rbp+57h+var_70], r15b
0x18001cac6  mov     [rbp+57h+var_68], rax
0x18001caca  mov     [rbp+57h+var_60], rcx
0x18001cace  mov     [rbp+57h+arg_18], r15
0x18001cad2  mov     [rbp+57h+dwDisposition], r15d
0x18001cad6  lea     rax, [rbp+57h+dwDisposition]
0x18001cada  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18001cadf  lea     rax, [rbp+57h+arg_18]
0x18001cae3  mov     [rsp+0D0h+var_98], rax; phkResult
0x18001cae8  mov     [rsp+0D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001caed  mov     [rsp+0D0h+samDesired], r15d; samDesired
0x18001caf2  mov     dword ptr [rsp+0D0h+phkResult], r12d; dwOptions
0x18001caf7  xor     r9d, r9d; lpClass
0x18001cafa  xor     r8d, r8d; Reserved
0x18001cafd  lea     r14, aRepositoryrest; "RepositoryRestoreInProgress"
0x18001cb04  mov     rdx, r14; lpSubKey
0x18001cb07  call    cs:__imp_RegCreateKeyExW
0x18001cb0d  test    eax, eax
0x18001cb0f  jz      short loc_18001CB20
0x18001cb11  jg      short loc_18001CB17
0x18001cb13  mov     ebx, eax
0x18001cb15  jmp     short loc_18001CB20
0x18001cb17  movzx   ebx, ax
0x18001cb1a  or      ebx, 80070000h
0x18001cb20  test    ebx, ebx
0x18001cb22  js      short loc_18001CB66
0x18001cb24  mov     rcx, [rbp+57h+arg_18]; hKey
0x18001cb28  call    cs:__imp_RegCloseKey
0x18001cb2e  mov     rcx, [rbp+57h+hKey]
0x18001cb32  mov     rax, cs:__imp_RegDeleteKeyExW
0x18001cb39  mov     [rbp+57h+var_58], r15b
0x18001cb3d  mov     [rbp+57h+var_50], rax
0x18001cb41  mov     [rbp+57h+var_48], rcx
0x18001cb45  mov     [rbp+57h+var_40], r14
0x18001cb49  mov     [rbp+57h+var_38], r15
0x18001cb4d  call    ?RestoreWMIRepository@@YAJXZ; RestoreWMIRepository(void)
0x18001cb52  movzx   esi, sil
0x18001cb56  test    eax, eax
0x18001cb58  cmovns  esi, r12d
0x18001cb5c  lea     rcx, [rbp+57h+var_58]
0x18001cb60  call    ??1?$ScopeGuardImpl4@P6AJPEAUHKEY__@@PEBGKK@ZPEAU1@PEBGHH@@QEAA@XZ; ScopeGuardImpl4<long (*)(HKEY__ *,ushort const *,ulong,ulong),HKEY__ *,ushort const *,int,int>::~ScopeGuardImpl4<long (*)(HKEY__ *,ushort const *,ulong,ulong),HKEY__ *,ushort const *,int,int>(void)
0x18001cb65  nop
0x18001cb66  lea     rcx, [rbp+57h+var_70]
0x18001cb6a  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18001cb6f  jmp     short loc_18001CB79
0x18001cb71  mov     cl, r12b; bool
0x18001cb74  call    ?SetRepositoryCheckOnStartup@@YAJ_N@Z; SetRepositoryCheckOnStartup(bool)
0x18001cb79  cmp     cs:?m_bReportReadyToSend@CRepositoryCorruption@@2JA, r12d; long CRepositoryCorruption::m_bReportReadyToSend
0x18001cb80  jnz     short loc_18001CBDA
0x18001cb82  mov     eax, r15d
0x18001cb85  xchg    eax, cs:?m_bReportReadyToSend@CRepositoryCorruption@@2JA; long CRepositoryCorruption::m_bReportReadyToSend
0x18001cb8b  xor     ecx, ecx; bool
0x18001cb8d  call    ?ReportCorruption@CRepositoryCorruption@@SAJ_N@Z; CRepositoryCorruption::ReportCorruption(bool)
0x18001cb92  mov     rcx, cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18001cb99  test    rcx, rcx
0x18001cb9c  jz      short loc_18001CBAC
0x18001cb9e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001cba4  nop
0x18001cba5  mov     cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA, r15; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18001cbac  mov     eax, r15d
0x18001cbaf  xchg    eax, cs:?m_dwCorruptionType@CRepositoryCorruption@@2JA; long CRepositoryCorruption::m_dwCorruptionType
0x18001cbb5  mov     ecx, r15d
0x18001cbb8  xchg    ecx, cs:?m_bCalledByStartup@CRepositoryCorruption@@2JA; long CRepositoryCorruption::m_bCalledByStartup
0x18001cbbe  mov     eax, r15d
0x18001cbc1  xchg    eax, cs:?m_dwImproperShutdownFlag@CRepositoryCorruption@@2KA; ulong CRepositoryCorruption::m_dwImproperShutdownFlag
0x18001cbc7  mov     ecx, r15d
0x18001cbca  xchg    ecx, cs:?m_dwRecoverType@CRepositoryCorruption@@2KA; ulong CRepositoryCorruption::m_dwRecoverType
0x18001cbd0  test    sil, sil
0x18001cbd3  jz      short loc_18001CBDA
0x18001cbd5  call    ?ReportFutureCorruption@@YAJXZ; ReportFutureCorruption(void)
0x18001cbda  mov     rax, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A+8; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18001cbe1  sub     rax, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18001cbe8  sar     rax, 2
0x18001cbec  mov     rcx, 133F84CFE133F84Dh
0x18001cbf6  imul    rax, rcx
0x18001cbfa  test    rax, rax
0x18001cbfd  jz      short loc_18001CC12
0x18001cbff  call    ?ReportInconsistentBackupCorruption@CRepositoryCorruption@@SAJXZ; CRepositoryCorruption::ReportInconsistentBackupCorruption(void)
0x18001cc04  mov     rax, qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18001cc0b  mov     qword ptr cs:?m_aCorruptedBackup@CRepositoryCorruption@@2V?$vector@UWMIRepositoryCorruptionReport@@V?$wbem_allocator@UWMIRepositoryCorruptionReport@@@@@std@@A+8, rax; std::vector<WMIRepositoryCorruptionReport,wbem_allocator<WMIRepositoryCorruptionReport>> CRepositoryCorruption::m_aCorruptedBackup
0x18001cc12  test    edi, edi
0x18001cc14  jz      short loc_18001CC1F
0x18001cc16  mov     rcx, r13; this
0x18001cc19  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x18001cc1e  nop
0x18001cc1f  lock dec cs:?lCheckpointCalls@CheckPointTimer@@2JC; long volatile CheckPointTimer::lCheckpointCalls
0x18001cc26  xor     eax, eax
0x18001cc28  mov     rbx, [rsp+0D0h+arg_0]
0x18001cc30  add     rsp, 0A0h
0x18001cc37  pop     r15
0x18001cc39  pop     r14
0x18001cc3b  pop     r13
0x18001cc3d  pop     r12
0x18001cc3f  pop     rdi
0x18001cc40  pop     rsi
0x18001cc41  pop     rbp
0x18001cc42  retn
```
