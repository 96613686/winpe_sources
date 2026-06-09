# ScheduleNetworkRetryTask(ushort const *)

- ea: `0x140012060`
- end: `0x140012282`
- name: `?ScheduleNetworkRetryTask@@YAJPEBG@Z`
- size: `546`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140012288`

## callees

- `0x14000b708`
- `0x14000baec`
- `0x14000f6b8`
- `0x140012060`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012169`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012169`
- `DMCmnUtils!DmCreateTask` at `0x14001221c`
- `DMCmnUtils!DmCreateTask` at `0x14001221c`
- `DMCmnUtils!DmIsTaskScheduled` at `0x140012099`
- `DMCmnUtils!DmIsTaskScheduled` at `0x140012099`
- `DMCmnUtils!BigStrcat` at `0x1400120e5`
- `DMCmnUtils!BigStrcat` at `0x1400121df`
- `DMCmnUtils!BigStrcat` at `0x1400120e5`
- `DMCmnUtils!BigStrcat` at `0x1400121df`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1400121b7`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1400121b7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400120b8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400120b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012132`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012132`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012251`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001222d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001223c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001222d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001223c`

## string_xrefs

- `0x1400121ff`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-102)</Description>        <URI>\Microsoft\Windows\EnterpriseMgmt\Schedule created for session retry</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>    </RegistrationInfo>   `
- `0x14001208f`: `Retry Schedule created for incomplete session`
- `0x140012206`: `Retry Schedule created for incomplete session`

## pseudocode

```c
__int64 __fastcall ScheduleNetworkRetryTask(const unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rsi
  WCHAR *v3; // r14
  signed int IsTaskScheduled; // ebx
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rdx
  LSTATUS v7; // eax
  signed int DWORD; // eax
  unsigned int v9; // r9d
  unsigned __int16 *v10; // rax
  COmaDmPrcLogger *Logger; // rax
  __int64 samDesired; // [rsp+28h] [rbp-28h]
  unsigned int v14; // [rsp+88h] [rbp+38h] BYREF
  int v15; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  v14 = 0;
  v2 = 0;
  hKey = 0;
  v15 = 0;
  v3 = 0;
  IsTaskScheduled = DmIsTaskScheduled(
                      L"\\Microsoft\\Windows\\EnterpriseMgmt",
                      a1,
                      L"Retry Schedule created for incomplete session",
                      &v15);
  if ( IsTaskScheduled >= 0 && !v15 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v6 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
    if ( !IsStateSeparationEnabled )
      v6 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
    v3 = BigStrcat(3u, v6, L"\\", a1);
    if ( !v3 )
      goto LABEL_6;
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    IsTaskScheduled = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        IsTaskScheduled = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      DWORD = OmaDmRegistryGetDWORD(hKey, 0, L"RetryCount", &v14);
      IsTaskScheduled = 0;
      if ( DWORD != -2147024894 )
        IsTaskScheduled = DWORD;
      if ( IsTaskScheduled >= 0 )
      {
        v9 = v14 + 1;
        v14 = v9;
        if ( v9 <= 6 )
        {
          IsTaskScheduled = OmaDmRegistrySetDWORD(hKey, 0, L"RetryCount", v9);
          if ( IsTaskScheduled >= 0 )
          {
            v10 = BigStrcat(3u, L"/o \"", a1, L"\" /c /v");
            v2 = v10;
            if ( !v10 )
            {
LABEL_6:
              IsTaskScheduled = -2147024882;
              goto LABEL_18;
            }
            LODWORD(samDesired) = 0;
            IsTaskScheduled = DmCreateTask(
                                L"\\Microsoft\\Windows\\EnterpriseMgmt",
                                a1,
                                L"Retry Schedule created for incomplete session",
                                L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"u"
                                 "rn:schemas-microsoft-com:asm.v3\">    <RegistrationInfo>        <Author>$(@%systemRoot%"
                                 "\\system32\\deviceenroller.exe,-101)</Author>        <Description>$(@%systemRoot%\\syst"
                                 "em32\\deviceenroller.exe,-102)</Description>        <URI>\\Microsoft\\Windows\\Enterpri"
                                 "seMgmt\\Schedule created for session retry</URI>        <SecurityDescriptor>D:(A;;FA;;;"
                                 "BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>    </RegistrationInfo>    <Triggers>"
                                 "      <!-- trigger WNF_CNET_DPU_GLOBAL_STATE_UNDER_TRACK = {0xa3bc2875, 0x1583002e} -->"
                                 "      <WnfStateChangeTrigger id=\"DataSenseTrigger\">        <StateName>7528bca32e00831"
                                 "5</StateName>        <Data>01</Data>        <DataOffset>0</DataOffset>      </WnfStateC"
                                 "hangeTrigger>      <!-- trigger WNF_SEB_FREE_NETWORK_PRESENT = {0xa3bc0875, 0x41840b3e}"
                                 " -->      <WnfStateChangeTrigger id=\"FreeNetworkTrigger\">        <StateName>7510BCA33"
                                 "E0B8441</StateName>        <Data>03</Data>        <DataOffset>0</DataOffset>      </Wnf"
                                 "StateChangeTrigger>    </Triggers>    <Principals>        <Principal id=\"LocalSystem\""
                                 ">            <UserId>S-1-5-18</UserId>            <RunLevel>HighestAvailable</RunLevel>"
                                 "        </Principal>    </Principals>    <Settings>        <MultipleInstancesPolicy>Ign"
                                 "oreNew</MultipleInstancesPolicy>        <DisallowStartIfOnBatteries>false</DisallowStar"
                                 "tIfOnBatteries>        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>        <A"
                                 "llowHardTerminate>false</AllowHardTerminate>        <StartWhenAvailable>true</StartWhen"
                                 "Available>        <RunOnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable>        <A"
                                 "llowStartOnDemand>true</AllowStartOnDemand>        <Hidden>false</Hidden>        <RunOn"
                                 "lyIfIdle>false</RunOnlyIfIdle>        <UseUnifiedSchedulingEngine>true</UseUnifiedSched"
                                 "ulingEngine>    </Settings>    <Actions Context=\"LocalSystem\">        <Exec>         "
                                 "   <Command>%windir%\\system32\\deviceenroller.exe</Command>        </Exec>    </Actions></Task>",
                                v10,
                                samDesired);
          }
        }
        else
        {
          DeleteRetryCount(a1);
          IsTaskScheduled = -2102657017;
        }
      }
    }
  }
LABEL_18:
  LocalFree(v2);
  LocalFree(v3);
  if ( hKey )
    RegCloseKey(hKey);
  Logger = COmaDmPrcLogger::GetLogger();
  COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduled(Logger, a1, v14, IsTaskScheduled);
  return (unsigned int)IsTaskScheduled;
}

```

## disassembly

```asm
0x140012060  push    rbp
0x140012062  push    rbx
0x140012063  push    rsi
0x140012064  push    rdi
0x140012065  push    r14
0x140012067  mov     rbp, rsp
0x14001206a  sub     rsp, 50h
0x14001206e  mov     rdi, rcx
0x140012071  mov     [rbp+arg_8], 0
0x140012078  xor     esi, esi
0x14001207a  lea     r9, [rbp+arg_10]
0x14001207e  mov     rdx, rcx
0x140012081  mov     [rbp+hKey], rsi
0x140012085  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14001208c  mov     [rbp+arg_10], esi
0x14001208f  lea     r8, aRetryScheduleC; "Retry Schedule created for incomplete s"...
0x140012096  xor     r14d, r14d
0x140012099  call    cs:__imp_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z; DmIsTaskScheduled(ushort const *,ushort const *,ushort const *,int *)
0x1400120a0  nop     dword ptr [rax+rax+00h]
0x1400120a5  mov     ebx, eax
0x1400120a7  test    eax, eax
0x1400120a9  js      loc_14001222A
0x1400120af  cmp     [rbp+arg_10], esi
0x1400120b2  jnz     loc_14001222A
0x1400120b8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400120bf  nop     dword ptr [rax+rax+00h]
0x1400120c4  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x1400120cb  mov     r9, rdi
0x1400120ce  test    al, al
0x1400120d0  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x1400120d7  lea     r8, asc_140019FC8; "\\"
0x1400120de  cmovz   rdx, rcx
0x1400120e2  lea     ecx, [rsi+3]
0x1400120e5  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400120ec  nop     dword ptr [rax+rax+00h]
0x1400120f1  mov     r14, rax
0x1400120f4  test    rax, rax
0x1400120f7  jnz     short loc_140012103
0x1400120f9  mov     ebx, 8007000Eh
0x1400120fe  jmp     loc_14001222A
0x140012103  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x140012108  lea     rax, [rbp+hKey]
0x14001210c  mov     [rsp+50h+phkResult], rax; phkResult
0x140012111  xor     r9d, r9d; lpClass
0x140012114  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140012119  xor     r8d, r8d; Reserved
0x14001211c  mov     dword ptr [rsp+50h+samDesired], 2001Fh; samDesired
0x140012124  mov     rdx, r14; lpSubKey
0x140012127  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001212e  mov     [rsp+50h+dwOptions], esi; dwOptions
0x140012132  call    cs:__imp_RegCreateKeyExW
0x140012139  nop     dword ptr [rax+rax+00h]
0x14001213e  mov     ebx, eax
0x140012140  test    eax, eax
0x140012142  jz      short loc_140012158
0x140012144  jle     loc_14001222A
0x14001214a  movzx   ebx, ax
0x14001214d  or      ebx, 80070000h
0x140012153  jmp     loc_14001222A
0x140012158  mov     rcx, [rbp+hKey]
0x14001215c  lea     r9, [rbp+arg_8]
0x140012160  lea     r8, ValueName; "RetryCount"
0x140012167  xor     edx, edx
0x140012169  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140012170  nop     dword ptr [rax+rax+00h]
0x140012175  xor     ebx, ebx
0x140012177  cmp     eax, 80070002h
0x14001217c  cmovnz  ebx, eax
0x14001217f  test    ebx, ebx
0x140012181  js      loc_14001222A
0x140012187  mov     r9d, [rbp+arg_8]
0x14001218b  inc     r9d
0x14001218e  mov     [rbp+arg_8], r9d
0x140012192  cmp     r9d, 6
0x140012196  jbe     short loc_1400121AA
0x140012198  mov     rcx, rdi; unsigned __int16 *
0x14001219b  call    ?DeleteRetryCount@@YAJPEBG@Z; DeleteRetryCount(ushort const *)
0x1400121a0  mov     ebx, 82AC0007h
0x1400121a5  jmp     loc_14001222A
0x1400121aa  mov     rcx, [rbp+hKey]
0x1400121ae  lea     r8, ValueName; "RetryCount"
0x1400121b5  xor     edx, edx
0x1400121b7  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400121be  nop     dword ptr [rax+rax+00h]
0x1400121c3  mov     ebx, eax
0x1400121c5  test    eax, eax
0x1400121c7  js      short loc_14001222A
0x1400121c9  lea     r9, aCV; "\" /c /v"
0x1400121d0  mov     r8, rdi
0x1400121d3  lea     rdx, aO; "/o \""
0x1400121da  mov     ecx, 3
0x1400121df  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400121e6  nop     dword ptr [rax+rax+00h]
0x1400121eb  mov     rsi, rax
0x1400121ee  test    rax, rax
0x1400121f1  jz      loc_1400120F9
0x1400121f7  mov     dword ptr [rsp+50h+samDesired], 0
0x1400121ff  lea     r9, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x140012206  lea     r8, aRetryScheduleC; "Retry Schedule created for incomplete s"...
0x14001220d  mov     qword ptr [rsp+50h+dwOptions], rax
0x140012212  mov     rdx, rdi
0x140012215  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14001221c  call    cs:__imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x140012223  nop     dword ptr [rax+rax+00h]
0x140012228  mov     ebx, eax
0x14001222a  mov     rcx, rsi; hMem
0x14001222d  call    cs:__imp_LocalFree
0x140012234  nop     dword ptr [rax+rax+00h]
0x140012239  mov     rcx, r14; hMem
0x14001223c  call    cs:__imp_LocalFree
0x140012243  nop     dword ptr [rax+rax+00h]
0x140012248  mov     rcx, [rbp+hKey]; hKey
0x14001224c  test    rcx, rcx
0x14001224f  jz      short loc_14001225D
0x140012251  call    cs:__imp_RegCloseKey
0x140012258  nop     dword ptr [rax+rax+00h]
0x14001225d  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140012262  mov     r8d, [rbp+arg_8]; unsigned int
0x140012266  mov     r9d, ebx; int
0x140012269  mov     rdx, rdi; unsigned __int16 *
0x14001226c  mov     rcx, rax; this
0x14001226f  call    ?LogOmaDmPrcOmaDmSessionRetryScheduled@COmaDmPrcLogger@@QEAAXPEBGKJ@Z; COmaDmPrcLogger::LogOmaDmPrcOmaDmSessionRetryScheduled(ushort const *,ulong,long)
0x140012274  mov     eax, ebx
0x140012276  add     rsp, 50h
0x14001227a  pop     r14
0x14001227c  pop     rdi
0x14001227d  pop     rsi
0x14001227e  pop     rbx
0x14001227f  pop     rbp
0x140012280  retn
```
