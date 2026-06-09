# SleepStudyReportData::TelemetryAnalysisScreenOn(_GUID const &,ulong,ulong,ulong)

- ea: `0x18002d348`
- end: `0x18002d568`
- name: `?TelemetryAnalysisScreenOn@SleepStudyReportData@@QEAAJAEBU_GUID@@KKK@Z`
- size: `544`
- prototype: `__int64 __fastcall(SleepStudyReportData *__hidden this, const struct _GUID *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005b40`

## callees

- `0x180008740`
- `0x1800119e4`
- `0x18002d348`
- `0x18002d6a0`
- `0x18002dd98`
- `0x1800448ac`
- `0x180044f9c`
- `0x18004ca90`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18002d3e4`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002d3e4`
- `ntdll!RtlNtStatusToDosError` at `0x18002d3ec`
- `ntdll!RtlNtStatusToDosError` at `0x18002d3ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d436`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d436`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d50e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d50e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d52a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d52a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SleepStudyReportData::TelemetryAnalysisScreenOn(
        SleepStudyReportData *this,
        const struct _GUID *a2,
        int a3,
        int a4,
        unsigned int a5)
{
  NTSTATUS PersistedStateLocation; // eax
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // ebx
  bool v15; // cc
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rax
  const struct _tlgProvider_t *v19; // rcx
  __int64 v20; // rbx
  const struct _tlgProvider_t *v21; // rcx
  _BYTE v23[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v24 = 0;
  *(_QWORD *)Data = 0;
  hKey = 0;
  ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>::ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>(v23);
  hKey = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"SrumTelemetry",
                             0,
                             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SRUM\\Telemetry",
                             0,
                             SubKey,
                             520,
                             &v24);
  v10 = RtlNtStatusToDosError(PersistedStateLocation);
  v14 = v10;
  v15 = v10 <= 0;
  if ( v10 )
    goto LABEL_2;
  if ( v24 > 0x208 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 2u, &hKey);
  v14 = v10;
  v15 = v10 <= 0;
  if ( v10 )
    goto LABEL_2;
  if ( !*((_QWORD *)this + 36) )
    goto LABEL_13;
  v16 = *((_QWORD *)this + 35);
  v17 = *(_QWORD *)(v16 + 8);
  if ( (unsigned __int64)a5 > *(_QWORD *)(v17 + 32) )
    *(_DWORD *)(v17 + 36) = a5 - *(_DWORD *)(v17 + 32);
  *(_QWORD *)Data = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 16LL);
  v27 = *(_QWORD *)(v16 + 8) + 16LL;
  v18 = std::_Tree<std::_Tmap_traits<UsageEventInfo *,ScreenOnInstanceData *,std::less<UsageEventInfo *>,std::allocator<std::pair<UsageEventInfo * const,ScreenOnInstanceData *>>,0>>::_Find<UsageEventInfo *>(
          (char *)this + 352,
          &v27);
  v20 = v18;
  if ( v18 != *((_QWORD *)this + 44) )
  {
    *(struct _GUID *)*(_QWORD *)(v18 + 40) = *a2;
    *(_DWORD *)(*(_QWORD *)(v18 + 40) + 16LL) = a3;
    *(_DWORD *)(*(_QWORD *)(v18 + 40) + 20LL) = a4;
    AddScreenOnSummaryRow(
      v19,
      (const struct UsageEventInfo *)(*(_QWORD *)(v16 + 8) + 16LL),
      *(const struct ScreenOnInstanceData **)(v18 + 40));
    AddScreenOnE3Telemetry(
      v21,
      (const struct UsageEventInfo *)(*(_QWORD *)(v16 + 8) + 16LL),
      *(const struct ScreenOnInstanceData **)(v20 + 40));
  }
  v10 = RegSetValueExW(hKey, L"ScreenOnLatestAnalyzedSessionTimestamp", 0, 0xBu, Data, 8u);
  v14 = v10;
  v15 = v10 <= 0;
  if ( v10 )
  {
LABEL_2:
    if ( !v15 )
      v14 = (unsigned __int16)v10 | 0x80070000;
  }
  else
  {
LABEL_13:
    v14 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>(v23);
  return v14;
}

```

## disassembly

```asm
0x18002d348  mov     [rsp-8+arg_8], rbx
0x18002d34d  mov     [rsp-8+arg_10], rsi
0x18002d352  push    rbp
0x18002d353  push    rdi
0x18002d354  push    r12
0x18002d356  push    r14
0x18002d358  push    r15
0x18002d35a  lea     rbp, [rsp-180h]
0x18002d362  sub     rsp, 280h
0x18002d369  mov     rax, cs:__security_cookie
0x18002d370  xor     rax, rsp
0x18002d373  mov     [rbp+1A0h+var_30], rax
0x18002d37a  mov     r14d, r9d
0x18002d37d  mov     r15d, r8d
0x18002d380  mov     r12, rdx
0x18002d383  mov     rdi, rcx
0x18002d386  mov     [rsp+2A0h+var_25C], 0
0x18002d38e  mov     qword ptr [rsp+2A0h+Data], 0
0x18002d397  mov     [rsp+2A0h+hKey], 0
0x18002d3a0  lea     rcx, [rsp+2A0h+var_260]
0x18002d3a5  call    ??0?$ProviderRegistrationGuard@$1?ScreenOnStudyLoggingProvider@@3QEBU_tlgProvider_t@@EB@@QEAA@XZ; ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>::ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>(void)
0x18002d3aa  nop
0x18002d3ab  mov     [rsp+2A0h+hKey], 0
0x18002d3b4  lea     rax, [rsp+2A0h+var_25C]
0x18002d3b9  mov     [rsp+2A0h+var_270], rax
0x18002d3be  mov     esi, 208h
0x18002d3c3  mov     [rsp+2A0h+cbData], esi
0x18002d3c7  lea     rax, [rsp+2A0h+SubKey]
0x18002d3cc  mov     [rsp+2A0h+phkResult], rax
0x18002d3d1  xor     r9d, r9d
0x18002d3d4  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002d3db  xor     edx, edx
0x18002d3dd  lea     rcx, aSrumtelemetry; "SrumTelemetry"
0x18002d3e4  call    cs:__imp_RtlGetPersistedStateLocation
0x18002d3ea  mov     ecx, eax; Status
0x18002d3ec  call    cs:__imp_RtlNtStatusToDosError
0x18002d3f2  mov     ebx, eax
0x18002d3f4  test    eax, eax
0x18002d3f6  jz      short loc_18002D40C
0x18002d3f8  jle     loc_18002D520
0x18002d3fe  movzx   ebx, ax
0x18002d401  or      ebx, 80070000h
0x18002d407  jmp     loc_18002D520
0x18002d40c  cmp     [rsp+2A0h+var_25C], esi
0x18002d410  jbe     short loc_18002D417
0x18002d412  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d417  lea     rax, [rsp+2A0h+hKey]
0x18002d41c  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18002d421  mov     r9d, 2; samDesired
0x18002d427  xor     r8d, r8d; ulOptions
0x18002d42a  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18002d42f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d436  call    cs:__imp_RegOpenKeyExW
0x18002d43c  mov     ebx, eax
0x18002d43e  test    eax, eax
0x18002d440  jnz     short loc_18002D3F8
0x18002d442  cmp     qword ptr [rdi+120h], 0
0x18002d44a  jbe     loc_18002D51E
0x18002d450  mov     rsi, [rdi+118h]
0x18002d457  mov     rcx, [rsi+8]
0x18002d45b  cmp     [rcx+24h], eax
0x18002d45e  jnz     short loc_18002D471
0x18002d460  mov     eax, [rbp+1A0h+arg_20]
0x18002d466  cmp     eax, [rcx+20h]
0x18002d469  jbe     short loc_18002D471
0x18002d46b  sub     eax, [rcx+20h]
0x18002d46e  mov     [rcx+24h], eax
0x18002d471  mov     rax, [rsi+8]
0x18002d475  mov     rcx, [rax+10h]
0x18002d479  mov     qword ptr [rsp+2A0h+Data], rcx
0x18002d47e  mov     rax, [rsi+8]
0x18002d482  add     rax, 10h
0x18002d486  mov     [rsp+2A0h+var_248], rax
0x18002d48b  lea     rdx, [rsp+2A0h+var_248]
0x18002d490  lea     rcx, [rdi+160h]
0x18002d497  call    ??$_Find@PEAUUsageEventInfo@@@?$_Tree@V?$_Tmap_traits@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@U?$less@PEAUUsageEventInfo@@@std@@V?$allocator@U?$pair@QEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@@4@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@QEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@PEAX@1@AEBQEAUUsageEventInfo@@@Z; std::_Tree<std::_Tmap_traits<UsageEventInfo *,ScreenOnInstanceData *,std::less<UsageEventInfo *>,std::allocator<std::pair<UsageEventInfo * const,ScreenOnInstanceData *>>,0>>::_Find<UsageEventInfo *>(UsageEventInfo * const &)
0x18002d49c  mov     rbx, rax
0x18002d49f  cmp     rax, [rdi+160h]
0x18002d4a6  jz      short loc_18002D4E7
0x18002d4a8  mov     rax, [rax+28h]
0x18002d4ac  movups  xmm0, xmmword ptr [r12]
0x18002d4b1  movdqu  xmmword ptr [rax], xmm0
0x18002d4b5  mov     rax, [rbx+28h]
0x18002d4b9  mov     [rax+10h], r15d
0x18002d4bd  mov     rax, [rbx+28h]
0x18002d4c1  mov     [rax+14h], r14d
0x18002d4c5  mov     rdx, [rsi+8]
0x18002d4c9  add     rdx, 10h; struct UsageEventInfo *
0x18002d4cd  mov     r8, [rbx+28h]; struct ScreenOnInstanceData *
0x18002d4d1  call    ?AddScreenOnSummaryRow@@YAXPEBU_tlgProvider_t@@AEBUUsageEventInfo@@AEBUScreenOnInstanceData@@@Z; AddScreenOnSummaryRow(_tlgProvider_t const *,UsageEventInfo const &,ScreenOnInstanceData const &)
0x18002d4d6  mov     rdx, [rsi+8]
0x18002d4da  add     rdx, 10h; struct UsageEventInfo *
0x18002d4de  mov     r8, [rbx+28h]; struct ScreenOnInstanceData *
0x18002d4e2  call    ?AddScreenOnE3Telemetry@@YAXPEBU_tlgProvider_t@@AEBUUsageEventInfo@@AEBUScreenOnInstanceData@@@Z; AddScreenOnE3Telemetry(_tlgProvider_t const *,UsageEventInfo const &,ScreenOnInstanceData const &)
0x18002d4e7  mov     [rsp+2A0h+cbData], 8; cbData
0x18002d4ef  lea     rax, [rsp+2A0h+Data]
0x18002d4f4  mov     [rsp+2A0h+phkResult], rax; lpData
0x18002d4f9  mov     r9d, 0Bh; dwType
0x18002d4ff  xor     r8d, r8d; Reserved
0x18002d502  lea     rdx, ValueName; "ScreenOnLatestAnalyzedSessionTimestamp"
0x18002d509  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18002d50e  call    cs:__imp_RegSetValueExW
0x18002d514  mov     ebx, eax
0x18002d516  test    eax, eax
0x18002d518  jnz     loc_18002D3F8
0x18002d51e  xor     ebx, ebx
0x18002d520  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18002d525  test    rcx, rcx
0x18002d528  jz      short loc_18002D531
0x18002d52a  call    cs:__imp_RegCloseKey
0x18002d530  nop
0x18002d531  lea     rcx, [rsp+2A0h+var_260]
0x18002d536  call    ??1?$ProviderRegistrationGuard@$1?ScreenOnStudyLoggingProvider@@3QEBU_tlgProvider_t@@EB@@QEAA@XZ; ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const ScreenOnStudyLoggingProvider>(void)
0x18002d53b  mov     eax, ebx
0x18002d53d  mov     rcx, [rbp+1A0h+var_30]
0x18002d544  xor     rcx, rsp; StackCookie
0x18002d547  call    __security_check_cookie
0x18002d54c  lea     r11, [rsp+2A0h+var_20]
0x18002d554  mov     rbx, [r11+38h]
0x18002d558  mov     rsi, [r11+40h]
0x18002d55c  mov     rsp, r11
0x18002d55f  pop     r15
0x18002d561  pop     r14
0x18002d563  pop     r12
0x18002d565  pop     rdi
0x18002d566  pop     rbp
0x18002d567  retn
```
