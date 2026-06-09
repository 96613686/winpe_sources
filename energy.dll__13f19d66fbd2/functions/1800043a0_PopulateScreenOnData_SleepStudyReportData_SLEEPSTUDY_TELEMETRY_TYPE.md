# PopulateScreenOnData(SleepStudyReportData &,_SLEEPSTUDY_TELEMETRY_TYPE)

- ea: `0x1800043a0`
- end: `0x18000465f`
- name: `?PopulateScreenOnData@@YAXAEAUSleepStudyReportData@@W4_SLEEPSTUDY_TELEMETRY_TYPE@@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005b40`
- `0x1800778f0`

## callees

- `0x1800043a0`
- `0x180004668`
- `0x180008740`
- `0x180008da0`
- `0x1800395d8`
- `0x18003bb60`
- `0x1800432f0`
- `0x180043324`
- `0x1800454b4`
- `0x18004ca90`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180004444`
- `ntdll!RtlGetPersistedStateLocation` at `0x180004444`
- `ntdll!RtlNtStatusToDosError` at `0x18000444c`
- `ntdll!RtlNtStatusToDosError` at `0x18000444c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000447e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000447e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800045ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800045ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PopulateScreenOnData(SleepStudyReportData *a1, int a2)
{
  NTSTATUS PersistedStateLocation; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  _QWORD *i; // rcx
  _QWORD *v9; // rbx
  _QWORD *v10; // rbx
  ScreenOnInstanceData *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  ScreenOnInstanceData *v15; // rdi
  __int64 *v16; // rbx
  ScreenOnInstanceData *v17; // rax
  ScreenOnInstanceData *v18; // r14
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v23; // [rsp+58h] [rbp-A8h] BYREF
  ScreenOnInstanceData *v24; // [rsp+60h] [rbp-A0h]
  ScreenOnInstanceData *v25; // [rsp+68h] [rbp-98h]
  _BYTE v26[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v19 = 0;
  *(_QWORD *)Data = 0;
  hKey = 0;
  cbData = 0;
  SleepStudyReportData::AnnotateRecentUsageForScreenOnStudy(a1);
  if ( a2 == 1 )
  {
    *(_QWORD *)Data = 0;
    hKey = 0;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"SrumTelemetry",
                               0,
                               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SRUM\\Telemetry",
                               0,
                               SubKey,
                               520,
                               &v19);
    if ( !RtlNtStatusToDosError(PersistedStateLocation) )
    {
      if ( v19 > 0x208 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
      {
        cbData = 8;
        RegQueryValueExW(hKey, L"ScreenOnLatestAnalyzedSessionTimestamp", 0, 0, Data, &cbData);
        RegCloseKey(hKey);
      }
    }
    i = (_QWORD *)*((_QWORD *)a1 + 35);
LABEL_8:
    for ( i = (_QWORD *)*i; ; i = v10 )
    {
      v9 = (_QWORD *)*((_QWORD *)a1 + 35);
      if ( i == v9 )
        break;
      if ( i[2] > *(_QWORD *)Data && i[3] >= 0x23C34600u )
        goto LABEL_8;
      v10 = (_QWORD *)*i;
      *(_QWORD *)i[1] = *i;
      *(_QWORD *)(*i + 8LL) = i[1];
      --*((_QWORD *)a1 + 36);
      std::_Deallocate<16>(i, 0x38u);
    }
    while ( 1 )
    {
      v9 = (_QWORD *)*v9;
      if ( v9 == *((_QWORD **)a1 + 35) )
        break;
      v11 = (ScreenOnInstanceData *)operator new(0x768u);
      v25 = v11;
      if ( v11 )
        v15 = ScreenOnInstanceData::ScreenOnInstanceData(v11);
      else
        v15 = 0;
      if ( !v15 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v13, v12, v14);
      if ( v9[3] >= 0x165A0BC00uLL )
        ScreenOnInstanceData::AddSrumData(v15, (const struct UsageEventInfo *)(v9 + 2));
      v23 = v9 + 2;
      v24 = v15;
      std::_Tree<std::_Tmap_traits<UsageEventInfo *,ScreenOnInstanceData *,std::less<UsageEventInfo *>,std::allocator<std::pair<UsageEventInfo * const,ScreenOnInstanceData *>>,0>>::_Emplace<std::pair<UsageEventInfo *,ScreenOnInstanceData *>>(
        (char *)a1 + 352,
        v26,
        &v23);
    }
  }
  else
  {
    v16 = (__int64 *)*((_QWORD *)a1 + 35);
    while ( 1 )
    {
      v16 = (__int64 *)*v16;
      if ( v16 == *((__int64 **)a1 + 35) )
        break;
      v17 = (ScreenOnInstanceData *)operator new(0x768u);
      v25 = v17;
      if ( v17 )
        v18 = ScreenOnInstanceData::ScreenOnInstanceData(v17);
      else
        v18 = 0;
      if ( v18 )
      {
        ScreenOnInstanceData::AddSrumData(v18, (const struct UsageEventInfo *)(v16 + 2));
        v23 = v16 + 2;
        v24 = v18;
        std::map<UsageEventInfo *,ScreenOnInstanceData *>::insert<std::pair<UsageEventInfo *,ScreenOnInstanceData *>,0>(
          (char *)a1 + 352,
          v26,
          &v23);
      }
    }
  }
}

```

## disassembly

```asm
0x1800043a0  mov     [rsp-8+arg_8], rbx
0x1800043a5  mov     [rsp-8+arg_10], rsi
0x1800043aa  push    rbp
0x1800043ab  push    rdi
0x1800043ac  push    r14
0x1800043ae  lea     rbp, [rsp-1A0h]
0x1800043b6  sub     rsp, 2A0h
0x1800043bd  mov     rax, cs:__security_cookie
0x1800043c4  xor     rax, rsp
0x1800043c7  mov     [rbp+1B0h+var_20], rax
0x1800043ce  mov     ebx, edx
0x1800043d0  mov     rsi, rcx
0x1800043d3  mov     [rsp+2B0h+var_270], 0
0x1800043db  mov     qword ptr [rsp+2B0h+Data], 0
0x1800043e4  mov     [rsp+2B0h+hKey], 0
0x1800043ed  mov     [rsp+2B0h+cbData], 0
0x1800043f5  call    ?AnnotateRecentUsageForScreenOnStudy@SleepStudyReportData@@QEAAXXZ; SleepStudyReportData::AnnotateRecentUsageForScreenOnStudy(void)
0x1800043fa  cmp     ebx, 1
0x1800043fd  jnz     loc_1800045C1
0x180004403  mov     qword ptr [rsp+2B0h+Data], 0
0x18000440c  mov     [rsp+2B0h+hKey], 0
0x180004415  lea     rax, [rsp+2B0h+var_270]
0x18000441a  mov     [rsp+2B0h+var_280], rax
0x18000441f  mov     ebx, 208h
0x180004424  mov     dword ptr [rsp+2B0h+lpcbData], ebx
0x180004428  lea     rax, [rbp+1B0h+SubKey]
0x18000442c  mov     [rsp+2B0h+phkResult], rax
0x180004431  xor     r9d, r9d
0x180004434  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000443b  xor     edx, edx
0x18000443d  lea     rcx, aSrumtelemetry; "SrumTelemetry"
0x180004444  call    cs:__imp_RtlGetPersistedStateLocation
0x18000444a  mov     ecx, eax; Status
0x18000444c  call    cs:__imp_RtlNtStatusToDosError
0x180004452  test    eax, eax
0x180004454  jnz     short loc_18000448C
0x180004456  cmp     [rsp+2B0h+var_270], ebx
0x18000445a  ja      loc_1800045FC
0x180004460  lea     rax, [rsp+2B0h+hKey]
0x180004465  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000446a  mov     r9d, 1; samDesired
0x180004470  xor     r8d, r8d; ulOptions
0x180004473  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x180004477  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000447e  call    cs:__imp_RegOpenKeyExW
0x180004484  test    eax, eax
0x180004486  jz      loc_18000457D
0x18000448c  mov     rcx, [rsi+118h]
0x180004493  mov     rcx, [rcx]
0x180004496  mov     rbx, [rsi+118h]
0x18000449d  cmp     rcx, rbx
0x1800044a0  jz      short loc_1800044DC
0x1800044a2  mov     rax, qword ptr [rsp+2B0h+Data]
0x1800044a7  cmp     [rcx+10h], rax
0x1800044ab  ja      loc_180004606
0x1800044b1  mov     rbx, [rcx]
0x1800044b4  mov     rax, [rcx+8]
0x1800044b8  mov     [rax], rbx
0x1800044bb  mov     rdx, [rcx]
0x1800044be  mov     rax, [rcx+8]
0x1800044c2  mov     [rdx+8], rax
0x1800044c6  dec     qword ptr [rsi+120h]
0x1800044cd  mov     edx, 38h ; '8'
0x1800044d2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800044d7  mov     rcx, rbx
0x1800044da  jmp     short loc_180004496
0x1800044dc  mov     rbx, [rbx]
0x1800044df  cmp     rbx, [rsi+118h]
0x1800044e6  jz      short loc_180004556
0x1800044e8  mov     ecx, 768h; dwBytes
0x1800044ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044f2  mov     [rsp+2B0h+var_248], rax
0x1800044f7  test    rax, rax
0x1800044fa  jz      loc_1800045F5
0x180004500  mov     rcx, rax; this
0x180004503  call    ??0ScreenOnInstanceData@@QEAA@XZ; ScreenOnInstanceData::ScreenOnInstanceData(void)
0x180004508  mov     rdi, rax
0x18000450b  test    rdi, rdi
0x18000450e  jz      loc_180004619
0x180004514  mov     rax, 165A0BC00h
0x18000451e  cmp     [rbx+18h], rax
0x180004522  jb      short loc_180004530
0x180004524  lea     rdx, [rbx+10h]; struct UsageEventInfo *
0x180004528  mov     rcx, rdi; this
0x18000452b  call    ?AddSrumData@ScreenOnInstanceData@@QEAAXAEBUUsageEventInfo@@@Z; ScreenOnInstanceData::AddSrumData(UsageEventInfo const &)
0x180004530  lea     rax, [rbx+10h]
0x180004534  mov     [rsp+2B0h+var_258], rax
0x180004539  mov     [rsp+2B0h+var_250], rdi
0x18000453e  lea     rcx, [rsi+160h]
0x180004545  lea     r8, [rsp+2B0h+var_258]
0x18000454a  lea     rdx, [rsp+2B0h+var_240]
0x18000454f  call    ??$_Emplace@U?$pair@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@@?$_Tree@V?$_Tmap_traits@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@U?$less@PEAUUsageEventInfo@@@std@@V?$allocator@U?$pair@QEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@1@@Z; std::_Tree<std::_Tmap_traits<UsageEventInfo *,ScreenOnInstanceData *,std::less<UsageEventInfo *>,std::allocator<std::pair<UsageEventInfo * const,ScreenOnInstanceData *>>,0>>::_Emplace<std::pair<UsageEventInfo *,ScreenOnInstanceData *>>(std::pair<UsageEventInfo *,ScreenOnInstanceData *> &&)
0x180004554  jmp     short loc_1800044DC
0x180004556  mov     rcx, [rbp+1B0h+var_20]
0x18000455d  xor     rcx, rsp; StackCookie
0x180004560  call    __security_check_cookie
0x180004565  lea     r11, [rsp+2B0h+var_10]
0x18000456d  mov     rbx, [r11+28h]
0x180004571  mov     rsi, [r11+30h]
0x180004575  mov     rsp, r11
0x180004578  pop     r14
0x18000457a  pop     rdi
0x18000457b  pop     rbp
0x18000457c  retn
0x18000457d  mov     [rsp+2B0h+cbData], 8
0x180004585  lea     rax, [rsp+2B0h+cbData]
0x18000458a  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000458f  lea     rax, [rsp+2B0h+Data]
0x180004594  mov     [rsp+2B0h+phkResult], rax; lpData
0x180004599  xor     r9d, r9d; lpType
0x18000459c  xor     r8d, r8d; lpReserved
0x18000459f  lea     rdx, ValueName; "ScreenOnLatestAnalyzedSessionTimestamp"
0x1800045a6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800045ab  call    cs:__imp_RegQueryValueExW
0x1800045b1  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800045b6  call    cs:__imp_RegCloseKey
0x1800045bc  jmp     loc_18000448C
0x1800045c1  mov     rbx, [rsi+118h]
0x1800045c8  mov     rbx, [rbx]
0x1800045cb  cmp     rbx, [rsi+118h]
0x1800045d2  jz      short loc_180004556
0x1800045d4  mov     ecx, 768h; dwBytes
0x1800045d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045de  mov     [rsp+2B0h+var_248], rax
0x1800045e3  test    rax, rax
0x1800045e6  jz      short loc_180004623
0x1800045e8  mov     rcx, rax; this
0x1800045eb  call    ??0ScreenOnInstanceData@@QEAA@XZ; ScreenOnInstanceData::ScreenOnInstanceData(void)
0x1800045f0  mov     r14, rax
0x1800045f3  jmp     short loc_180004626
0x1800045f5  xor     edi, edi
0x1800045f7  jmp     loc_18000450B
0x1800045fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004601  jmp     loc_180004460
0x180004606  cmp     qword ptr [rcx+18h], 23C34600h
0x18000460e  jnb     loc_180004493
0x180004614  jmp     loc_1800044B1
0x180004619  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000461e  jmp     loc_180004514
0x180004623  xor     r14d, r14d
0x180004626  test    r14, r14
0x180004629  jz      short loc_1800045C8
0x18000462b  lea     rdi, [rbx+10h]
0x18000462f  mov     rdx, rdi; struct UsageEventInfo *
0x180004632  mov     rcx, r14; this
0x180004635  call    ?AddSrumData@ScreenOnInstanceData@@QEAAXAEBUUsageEventInfo@@@Z; ScreenOnInstanceData::AddSrumData(UsageEventInfo const &)
0x18000463a  mov     [rsp+2B0h+var_258], rdi
0x18000463f  mov     [rsp+2B0h+var_250], r14
0x180004644  lea     rcx, [rsi+160h]
0x18000464b  lea     r8, [rsp+2B0h+var_258]
0x180004650  lea     rdx, [rsp+2B0h+var_240]
0x180004655  call    ??$insert@U?$pair@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@$0A@@?$map@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@U?$less@PEAUUsageEventInfo@@@std@@V?$allocator@U?$pair@QEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEAUUsageEventInfo@@PEAUScreenOnInstanceData@@@1@@Z; std::map<UsageEventInfo *,ScreenOnInstanceData *>::insert<std::pair<UsageEventInfo *,ScreenOnInstanceData *>,0>(std::pair<UsageEventInfo *,ScreenOnInstanceData *> &&)
0x18000465a  jmp     loc_1800045C8
```
