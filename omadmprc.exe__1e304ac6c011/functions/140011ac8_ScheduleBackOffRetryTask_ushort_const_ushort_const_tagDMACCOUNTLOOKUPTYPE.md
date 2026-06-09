# ScheduleBackOffRetryTask(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE)

- ea: `0x140011ac8`
- end: `0x140012057`
- name: `?ScheduleBackOffRetryTask@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@@Z`
- size: `1423`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140012288`

## callees

- `0x140008504`
- `0x140008ea0`
- `0x14000b708`
- `0x14000bbbc`
- `0x14000ed04`
- `0x14000fc54`
- `0x140010d08`
- `0x140011ac8`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140011ee0`
- `msvcrt!??3@YAXPEAX@Z` at `0x140012024`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011ee0`
- `msvcrt!??3@YAXPEAX@Z` at `0x140012024`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140011e68`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140011e68`
- `DMCmnUtils!DmCreateTask` at `0x140011fb0`
- `DMCmnUtils!DmCreateTask` at `0x140011fb0`
- `DMCmnUtils!DmIsTaskScheduled` at `0x140011dd8`
- `DMCmnUtils!DmIsTaskScheduled` at `0x140011dd8`
- `DMCmnUtils!BigStrcat` at `0x140011f2a`
- `DMCmnUtils!BigStrcat` at `0x140011f2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011c09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011c09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011bb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011c34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011cb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011e14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011ea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011f56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011fd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011bb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011c34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011cb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011e14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011ea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011f56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011fd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001200c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001200c`

## string_xrefs

- `0x140011f99`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-102)</Description>        <URI>\Microsoft\Windows\EnterpriseMgmt\SessionRetry\Retry Schedule created by OmaDm client when the server is unavailable</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS`
- `0x140011d48`: `Retry Schedule created for incomplete session %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ScheduleBackOffRetryTask(unsigned __int16 *a1, const WCHAR *a2)
{
  unsigned __int16 *v2; // rbx
  int valid; // eax
  unsigned int Task; // edi
  LSTATUS v5; // eax
  __int64 v6; // rax
  int InitiationIDFromKeyPath; // eax
  void **v8; // r9
  int v9; // eax
  int IsTaskScheduled; // eax
  COmaDmPrcLogger *Logger; // rax
  int DWORD; // eax
  unsigned int v13; // ebx
  COmaDmPrcLogger *v14; // rax
  void **v16; // rax
  COmaDmPrcLogger *v17; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-A8h]
  HKEY *p_hKey; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v29; // [rsp+70h] [rbp-90h]
  LPCWSTR *p_lpSubKey; // [rsp+78h] [rbp-88h]
  char *v31; // [rsp+80h] [rbp-80h]
  __int64 *v32; // [rsp+88h] [rbp-78h]
  char v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[32]; // [rsp+98h] [rbp-68h] BYREF
  void *v35[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v37; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v38[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v22 = a1;
  lpSubKey = a2;
  v21 = 0;
  v26 = 0;
  hKey = 0;
  v25 = 0;
  v37 = 7;
  v36 = 0;
  LOWORD(v35[0]) = 0;
  v2 = 0;
  v27 = 0;
  p_hKey = &hKey;
  v29 = &v22;
  p_lpSubKey = &lpSubKey;
  v31 = (char *)&v21 + 4;
  v32 = &v21;
  v33 = 1;
  valid = ModifyRetryCountInValidRange(a1, 1, (unsigned int *)&v21 + 1);
  Task = valid;
  LODWORD(v21) = valid;
  if ( valid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39C,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)valid,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
LABEL_28:
    Logger = COmaDmPrcLogger::GetLogger();
    COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(Logger, v22, lpSubKey, HIDWORD(v21), v21);
LABEL_48:
    if ( v37 >= 8 )
      operator delete(v35[0]);
    return Task;
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
  Task = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      Task = (unsigned __int16)v5 | 0x80070000;
    LODWORD(v21) = Task;
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  v6 = std::wstring::wstring(v34, (void *)lpSubKey);
  InitiationIDFromKeyPath = GetInitiationIDFromKeyPath(v6, v35);
  Task = InitiationIDFromKeyPath;
  LODWORD(v21) = InitiationIDFromKeyPath;
  if ( InitiationIDFromKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AC,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)InitiationIDFromKeyPath,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  if ( !v36 )
  {
    Task = -2147418113;
    LODWORD(v21) = -2147418113;
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  v8 = v35;
  if ( v37 >= 8 )
    v8 = (void **)v35[0];
  v9 = StringCchPrintfW(v38, 0x104u, L"Retry Schedule created for incomplete session %s", v8);
  Task = v9;
  LODWORD(v21) = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BA,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)v9,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  IsTaskScheduled = DmIsTaskScheduled(L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry", v22, v38, &v25);
  Task = IsTaskScheduled;
  LODWORD(v21) = IsTaskScheduled;
  if ( IsTaskScheduled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C1,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)IsTaskScheduled,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_28;
  }
  if ( v25 )
  {
    Task = -2147418113;
    goto LABEL_44;
  }
  DWORD = OmaDmRegistryGetDWORD(hKey, 0, L"RetryDelay", &v26);
  v13 = DWORD;
  LODWORD(v21) = DWORD;
  if ( DWORD >= 0 )
  {
    v16 = v35;
    if ( v37 >= 8 )
      v16 = (void **)v35[0];
    v2 = BigStrcat(5u, L"/o \"", v22, L"\" /InitiationID \"", v16, L"\" /c /v", v21);
    v27 = v2;
    if ( !v2 )
    {
      v13 = -2147024882;
      LODWORD(v21) = -2147024882;
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_33;
    }
    LODWORD(v20) = v26;
    Task = DmCreateTask(
             L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry",
             v22,
             v38,
             L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsof"
              "t-com:asm.v3\">    <RegistrationInfo>        <Author>$(@%systemRoot%\\system32\\deviceenroller.exe,-101)</"
              "Author>        <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-102)</Description>        <URI>"
              "\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry\\Retry Schedule created by OmaDm client when the server"
              " is unavailable</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescrip"
              "tor>    </RegistrationInfo>    <Triggers>    </Triggers>    <Principals>        <Principal id=\"LocalSyste"
              "m\">            <UserId>S-1-5-18</UserId>            <RunLevel>HighestAvailable</RunLevel>        </Princi"
              "pal>    </Principals>    <Settings>        <MultipleInstancesPolicy>Parallel</MultipleInstancesPolicy>    "
              "    <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>        <StopIfGoingOnBatteries>false</S"
              "topIfGoingOnBatteries>        <AllowHardTerminate>true</AllowHardTerminate>        <StartWhenAvailable>tru"
              "e</StartWhenAvailable>        <RunOnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable>        <IdleSett"
              "ings>        <StopOnIdleEnd>false</StopOnIdleEnd>        <RestartOnIdle>false</RestartOnIdle>        </Idl"
              "eSettings>        <AllowStartOnDemand>true</AllowStartOnDemand>        <Enabled>true</Enabled>        <Hid"
              "den>false</Hidden>        <RunOnlyIfIdle>false</RunOnlyIfIdle>        <DisallowStartOnRemoteAppSession>fal"
              "se</DisallowStartOnRemoteAppSession>        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine> "
              "       <WakeToRun>false</WakeToRun>        <ExecutionTimeLimit>PT1H</ExecutionTimeLimit>        <Priority>"
              "7</Priority>    </Settings>    <Actions Context=\"LocalSystem\">        <Exec>            <Command>%windir"
              "%\\system32\\deviceenroller.exe</Command>        </Exec>    </Actions></Task>",
             v2,
             v20);
LABEL_44:
    LODWORD(v21) = Task;
    if ( hKey )
      RegCloseKey(hKey);
    v17 = COmaDmPrcLogger::GetLogger();
    COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(v17, v22, lpSubKey, HIDWORD(v21), v21);
    if ( v2 )
      LocalFree(v2);
    goto LABEL_48;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3CB,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
    (const char *)(unsigned int)DWORD,
    phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_33:
  v14 = COmaDmPrcLogger::GetLogger();
  COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(v14, v22, lpSubKey, HIDWORD(v21), v21);
  if ( v37 >= 8 )
    operator delete(v35[0]);
  return v13;
}

```

## disassembly

```asm
0x140011ac8  mov     [rsp-8+arg_10], rbx
0x140011acd  mov     [rsp-8+arg_18], rdi
0x140011ad2  push    rbp
0x140011ad3  lea     rbp, [rsp-200h]
0x140011adb  sub     rsp, 300h
0x140011ae2  mov     rax, cs:__security_cookie
0x140011ae9  xor     rax, rsp
0x140011aec  mov     [rbp+200h+var_10], rax
0x140011af3  mov     [rsp+300h+var_2C8], rcx
0x140011af8  mov     [rsp+300h+lpSubKey], rdx
0x140011afd  mov     [rsp+300h+var_2D0], 0
0x140011b05  mov     [rsp+300h+var_2CC], 0
0x140011b0d  mov     [rsp+300h+var_2AC], 0
0x140011b15  mov     [rsp+300h+hKey], 0
0x140011b1e  mov     [rsp+300h+var_2B0], 0
0x140011b26  mov     [rbp+200h+var_230], 7
0x140011b2e  mov     [rbp+200h+var_238], 0
0x140011b36  xor     eax, eax
0x140011b38  mov     word ptr [rbp+200h+var_248], ax
0x140011b3c  xor     ebx, ebx
0x140011b3e  mov     [rsp+300h+var_2A8], rbx
0x140011b43  lea     rax, [rsp+300h+hKey]
0x140011b48  mov     [rsp+300h+var_298], rax
0x140011b4d  lea     rax, [rsp+300h+var_2C8]
0x140011b52  mov     [rsp+300h+var_290], rax
0x140011b57  lea     rax, [rsp+300h+lpSubKey]
0x140011b5c  mov     [rsp+300h+var_288], rax
0x140011b61  lea     rax, [rsp+300h+var_2CC]
0x140011b66  mov     [rbp+200h+var_280], rax
0x140011b6a  lea     rax, [rsp+300h+var_2D0]
0x140011b6f  mov     [rbp+200h+var_278], rax
0x140011b73  mov     [rbp+200h+var_270], 1
0x140011b77  lea     r8, [rsp+300h+var_2CC]; unsigned int *
0x140011b7c  lea     edx, [rbx+1]; int
0x140011b7f  call    ?ModifyRetryCountInValidRange@@YAJPEBGHPEAK@Z; ModifyRetryCountInValidRange(ushort const *,int,ulong *)
0x140011b84  mov     edi, eax
0x140011b86  mov     [rsp+300h+var_2D0], eax
0x140011b8a  test    eax, eax
0x140011b8c  jns     short loc_140011BEA
0x140011b8e  mov     rcx, [rbp+208h]; this
0x140011b95  mov     r9d, eax; char *
0x140011b98  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140011b9f  mov     edx, 39Ch; void *
0x140011ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011ba9  nop
0x140011baa  mov     rcx, [rsp+300h+hKey]; hKey
0x140011baf  test    rcx, rcx
0x140011bb2  jz      short loc_140011BC0
0x140011bb4  call    cs:__imp_RegCloseKey
0x140011bbb  nop     dword ptr [rax+rax+00h]
0x140011bc0  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011bc5  mov     ecx, [rsp+300h+var_2D0]
0x140011bc9  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011bcd  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011bd2  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011bd7  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011bdc  mov     rcx, rax; this
0x140011bdf  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011be4  nop
0x140011be5  jmp     loc_140012019
0x140011bea  lea     rax, [rsp+300h+hKey]
0x140011bef  mov     [rsp+300h+phkResult], rax; int
0x140011bf4  mov     r9d, 2001Fh; samDesired
0x140011bfa  xor     r8d, r8d; ulOptions
0x140011bfd  mov     rdx, [rsp+300h+lpSubKey]; lpSubKey
0x140011c02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011c09  call    cs:__imp_RegOpenKeyExW
0x140011c10  nop     dword ptr [rax+rax+00h]
0x140011c15  mov     edi, eax
0x140011c17  test    eax, eax
0x140011c19  jz      short loc_140011C6A
0x140011c1b  jle     short loc_140011C26
0x140011c1d  movzx   edi, ax
0x140011c20  or      edi, 80070000h
0x140011c26  mov     [rsp+300h+var_2D0], edi
0x140011c2a  mov     rcx, [rsp+300h+hKey]; hKey
0x140011c2f  test    rcx, rcx
0x140011c32  jz      short loc_140011C40
0x140011c34  call    cs:__imp_RegCloseKey
0x140011c3b  nop     dword ptr [rax+rax+00h]
0x140011c40  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011c45  mov     ecx, [rsp+300h+var_2D0]
0x140011c49  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011c4d  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011c52  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011c57  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011c5c  mov     rcx, rax; this
0x140011c5f  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011c64  nop
0x140011c65  jmp     loc_140011BE5
0x140011c6a  mov     rdx, [rsp+300h+lpSubKey]; Src
0x140011c6f  lea     rcx, [rbp+200h+var_268]; void *
0x140011c73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140011c78  lea     rdx, [rbp+200h+var_248]
0x140011c7c  mov     rcx, rax
0x140011c7f  call    ?GetInitiationIDFromKeyPath@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetInitiationIDFromKeyPath(std::wstring,std::wstring &)
0x140011c84  mov     edi, eax
0x140011c86  mov     [rsp+300h+var_2D0], eax
0x140011c8a  test    eax, eax
0x140011c8c  jns     short loc_140011CEA
0x140011c8e  mov     rcx, [rbp+208h]; this
0x140011c95  mov     r9d, eax; char *
0x140011c98  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140011c9f  mov     edx, 3ACh; void *
0x140011ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011ca9  nop
0x140011caa  mov     rcx, [rsp+300h+hKey]; hKey
0x140011caf  test    rcx, rcx
0x140011cb2  jz      short loc_140011CC0
0x140011cb4  call    cs:__imp_RegCloseKey
0x140011cbb  nop     dword ptr [rax+rax+00h]
0x140011cc0  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011cc5  mov     ecx, [rsp+300h+var_2D0]
0x140011cc9  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011ccd  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011cd2  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011cd7  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011cdc  mov     rcx, rax; this
0x140011cdf  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011ce4  nop
0x140011ce5  jmp     loc_140011BE5
0x140011cea  cmp     [rbp+200h+var_238], 0
0x140011cef  jnz     short loc_140011D3A
0x140011cf1  mov     edi, 8000FFFFh
0x140011cf6  mov     [rsp+300h+var_2D0], edi
0x140011cfa  mov     rcx, [rsp+300h+hKey]; hKey
0x140011cff  test    rcx, rcx
0x140011d02  jz      short loc_140011D10
0x140011d04  call    cs:__imp_RegCloseKey
0x140011d0b  nop     dword ptr [rax+rax+00h]
0x140011d10  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011d15  mov     ecx, [rsp+300h+var_2D0]
0x140011d19  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011d1d  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011d22  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011d27  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011d2c  mov     rcx, rax; this
0x140011d2f  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011d34  nop
0x140011d35  jmp     loc_140011BE5
0x140011d3a  lea     r9, [rbp+200h+var_248]
0x140011d3e  cmp     [rbp+200h+var_230], 8
0x140011d43  cmovnb  r9, [rbp+200h+var_248]
0x140011d48  lea     r8, aRetryScheduleC_0; "Retry Schedule created for incomplete s"...
0x140011d4f  mov     edx, 104h; unsigned __int64
0x140011d54  lea     rcx, [rbp+200h+var_220]; unsigned __int16 *
0x140011d58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140011d5d  mov     edi, eax
0x140011d5f  mov     [rsp+300h+var_2D0], eax
0x140011d63  test    eax, eax
0x140011d65  jns     short loc_140011DC3
0x140011d67  mov     rcx, [rbp+208h]; this
0x140011d6e  mov     r9d, eax; char *
0x140011d71  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140011d78  mov     edx, 3BAh; void *
0x140011d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011d82  nop
0x140011d83  mov     rcx, [rsp+300h+hKey]; hKey
0x140011d88  test    rcx, rcx
0x140011d8b  jz      short loc_140011D99
0x140011d8d  call    cs:__imp_RegCloseKey
0x140011d94  nop     dword ptr [rax+rax+00h]
0x140011d99  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011d9e  mov     ecx, [rsp+300h+var_2D0]
0x140011da2  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011da6  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011dab  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011db0  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011db5  mov     rcx, rax; this
0x140011db8  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011dbd  nop
0x140011dbe  jmp     loc_140011BE5
0x140011dc3  lea     r9, [rsp+300h+var_2B0]
0x140011dc8  lea     r8, [rbp+200h+var_220]
0x140011dcc  mov     rdx, [rsp+300h+var_2C8]
0x140011dd1  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\S"...
0x140011dd8  call    cs:__imp_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z; DmIsTaskScheduled(ushort const *,ushort const *,ushort const *,int *)
0x140011ddf  nop     dword ptr [rax+rax+00h]
0x140011de4  mov     edi, eax
0x140011de6  mov     [rsp+300h+var_2D0], eax
0x140011dea  test    eax, eax
0x140011dec  jns     short loc_140011E4A
0x140011dee  mov     rcx, [rbp+208h]; this
0x140011df5  mov     r9d, eax; char *
0x140011df8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140011dff  mov     edx, 3C1h; void *
0x140011e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011e09  nop
0x140011e0a  mov     rcx, [rsp+300h+hKey]; hKey
0x140011e0f  test    rcx, rcx
0x140011e12  jz      short loc_140011E20
0x140011e14  call    cs:__imp_RegCloseKey
0x140011e1b  nop     dword ptr [rax+rax+00h]
0x140011e20  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011e25  mov     ecx, [rsp+300h+var_2D0]
0x140011e29  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011e2d  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011e32  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011e37  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011e3c  mov     rcx, rax; this
0x140011e3f  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011e44  nop
0x140011e45  jmp     loc_140011BE5
0x140011e4a  cmp     [rsp+300h+var_2B0], 0
0x140011e4f  jnz     loc_140011FC0
0x140011e55  lea     r9, [rsp+300h+var_2AC]
0x140011e5a  lea     r8, aRetrydelay; "RetryDelay"
0x140011e61  xor     edx, edx
0x140011e63  mov     rcx, [rsp+300h+hKey]
0x140011e68  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140011e6f  nop     dword ptr [rax+rax+00h]
0x140011e74  mov     ebx, eax
0x140011e76  mov     [rsp+300h+var_2D0], eax
0x140011e7a  test    eax, eax
0x140011e7c  jns     short loc_140011EF3
0x140011e7e  mov     rcx, [rbp+208h]; this
0x140011e85  mov     r9d, eax; char *
0x140011e88  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140011e8f  mov     edx, 3CBh; void *
0x140011e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011e99  nop
0x140011e9a  mov     rcx, [rsp+300h+hKey]; hKey
0x140011e9f  test    rcx, rcx
0x140011ea2  jz      short loc_140011EB0
0x140011ea4  call    cs:__imp_RegCloseKey
0x140011eab  nop     dword ptr [rax+rax+00h]
0x140011eb0  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011eb5  mov     ecx, [rsp+300h+var_2D0]
0x140011eb9  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011ebd  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011ec2  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011ec7  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011ecc  mov     rcx, rax; this
0x140011ecf  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011ed4  nop
0x140011ed5  cmp     [rbp+200h+var_230], 8
0x140011eda  jb      short loc_140011EEC
0x140011edc  mov     rcx, [rbp+200h+var_248]
0x140011ee0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140011ee7  nop     dword ptr [rax+rax+00h]
0x140011eec  mov     eax, ebx
0x140011eee  jmp     loc_140012032
0x140011ef3  lea     rax, [rbp+200h+var_248]
0x140011ef7  cmp     [rbp+200h+var_230], 8
0x140011efc  cmovnb  rax, [rbp+200h+var_248]
0x140011f01  lea     rcx, aCV; "\" /c /v"
0x140011f08  mov     [rsp+300h+var_2D8], rcx
0x140011f0d  mov     [rsp+300h+phkResult], rax
0x140011f12  lea     r9, aInitiationid; "\" /InitiationID \""
0x140011f19  mov     r8, [rsp+300h+var_2C8]
0x140011f1e  lea     rdx, aO; "/o \""
0x140011f25  mov     ecx, 5
0x140011f2a  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140011f31  nop     dword ptr [rax+rax+00h]
0x140011f36  mov     rbx, rax
0x140011f39  mov     [rsp+300h+var_2A8], rax
0x140011f3e  test    rax, rax
0x140011f41  jnz     short loc_140011F8C
0x140011f43  mov     ebx, 8007000Eh
0x140011f48  mov     [rsp+300h+var_2D0], ebx
0x140011f4c  mov     rcx, [rsp+300h+hKey]; hKey
0x140011f51  test    rcx, rcx
0x140011f54  jz      short loc_140011F62
0x140011f56  call    cs:__imp_RegCloseKey
0x140011f5d  nop     dword ptr [rax+rax+00h]
0x140011f62  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011f67  mov     ecx, [rsp+300h+var_2D0]
0x140011f6b  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011f6f  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011f74  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011f79  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011f7e  mov     rcx, rax; this
0x140011f81  call    ?LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID@COmaDmPrcLogger@@QEAAXPEBG0KJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduledWithInitiationID(ushort const *,ushort const *,ulong,long)
0x140011f86  nop
0x140011f87  jmp     loc_140011ED5
0x140011f8c  mov     eax, [rsp+300h+var_2AC]
0x140011f90  mov     dword ptr [rsp+300h+var_2D8], eax
0x140011f94  mov     [rsp+300h+phkResult], rbx
0x140011f99  lea     r9, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x140011fa0  lea     r8, [rbp+200h+var_220]
0x140011fa4  mov     rdx, [rsp+300h+var_2C8]
0x140011fa9  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\S"...
0x140011fb0  call    cs:__imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x140011fb7  nop     dword ptr [rax+rax+00h]
0x140011fbc  mov     edi, eax
0x140011fbe  jmp     short loc_140011FC5
0x140011fc0  mov     edi, 8000FFFFh
0x140011fc5  mov     [rsp+300h+var_2D0], edi
0x140011fc9  mov     rcx, [rsp+300h+hKey]; hKey
0x140011fce  test    rcx, rcx
0x140011fd1  jz      short loc_140011FDF
0x140011fd3  call    cs:__imp_RegCloseKey
0x140011fda  nop     dword ptr [rax+rax+00h]
0x140011fdf  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140011fe4  mov     ecx, [rsp+300h+var_2D0]
0x140011fe8  mov     dword ptr [rsp+300h+phkResult], ecx; int
0x140011fec  mov     r9d, [rsp+300h+var_2CC]; unsigned int
0x140011ff1  mov     r8, [rsp+300h+lpSubKey]; unsigned __int16 *
0x140011ff6  mov     rdx, [rsp+300h+var_2C8]; unsigned __int16 *
0x140011ffb  mov     rcx, rax; this
  ... truncated ...
```
