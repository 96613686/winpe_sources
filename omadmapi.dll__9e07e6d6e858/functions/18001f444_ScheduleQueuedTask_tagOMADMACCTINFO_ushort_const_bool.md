# ScheduleQueuedTask(tagOMADMACCTINFO,ushort const *,bool)

- ea: `0x18001f444`
- end: `0x18001f68a`
- name: `?ScheduleQueuedTask@@YAJUtagOMADMACCTINFO@@PEBG_N@Z`
- size: `582`
- prototype: `int __high(struct tagOMADMACCTINFO, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019684`

## callees

- `0x180011b98`
- `0x18001eb48`
- `0x18001f444`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18001f4c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18001f4c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f66e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f66e`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001f559`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001f559`
- `DMCmnUtils!BigStrcat` at `0x18001f506`
- `DMCmnUtils!BigStrcat` at `0x18001f59b`
- `DMCmnUtils!BigStrcat` at `0x18001f506`
- `DMCmnUtils!BigStrcat` at `0x18001f59b`
- `DMCmnUtils!DmIsTaskScheduled` at `0x18001f480`
- `DMCmnUtils!DmIsTaskScheduled` at `0x18001f480`
- `DMCmnUtils!DmCreateTask` at `0x18001f625`
- `DMCmnUtils!DmCreateTask` at `0x18001f625`

## string_xrefs

- `0x18001f60d`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-102)</Description>        <URI>\Microsoft\Windows\EnterpriseMgmt\Queued Schedule created for queued alerts</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>    </RegistrationI`
- `0x18001f472`: `Queued Schedule created for queued alerts`
- `0x18001f614`: `Queued Schedule created for queued alerts`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ScheduleQueuedTask(__int64 a1, const unsigned __int16 *a2, char a3)
{
  int IsTaskScheduled; // eax
  unsigned int v7; // ebx
  const unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  int DWORD; // eax
  int Task; // edi
  __int64 v13; // rdx
  const char *v14; // [rsp+20h] [rbp-28h]
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v17; // [rsp+60h] [rbp+18h] BYREF
  void *v18; // [rsp+68h] [rbp+20h] BYREF

  v17 = 0;
  if ( a3 )
  {
    LODWORD(v18) = 0;
    IsTaskScheduled = DmIsTaskScheduled(
                        L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
                        a2,
                        L"Queued Schedule created for queued alerts",
                        (int *)&v18);
    v7 = IsTaskScheduled;
    if ( IsTaskScheduled < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
        (const char *)(unsigned int)IsTaskScheduled,
        (int)v14);
      return v7;
    }
    if ( (_DWORD)v18 )
      return 0;
  }
  if ( _o_wcstod(*(_QWORD *)(a1 + 472), 0) >= 4.0 )
  {
    v14 = L"Batching";
    v9 = BigStrcat(4u, qword_180032D98, *(_QWORD *)(a1 + 24), L"\\");
    v10 = (unsigned __int16 *)v9;
    v18 = (void *)v9;
    if ( !v9 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
        (const char *)0x8007000ELL,
        (int)L"Batching");
      return v7;
    }
    DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, v9, L"WindowSize", &v17);
    Task = DWORD;
    if ( DWORD == -2147024894 )
    {
      v17 = 300;
    }
    else if ( DWORD < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
        (const char *)(unsigned int)DWORD,
        (int)L"Batching");
      goto LABEL_23;
    }
    LocalFree(v10);
  }
  v10 = BigStrcat(3u, L"/o \"", a2, L"\" /c /q");
  v18 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)0x8007000ELL,
      (int)v14);
    return v7;
  }
  Task = DmCreateTask(
           L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
           a2,
           L"Queued Schedule created for queued alerts",
           L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft-"
            "com:asm.v3\">    <RegistrationInfo>        <Author>$(@%systemRoot%\\system32\\deviceenroller.exe,-101)</Auth"
            "or>        <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-102)</Description>        <URI>\\Micr"
            "osoft\\Windows\\EnterpriseMgmt\\Queued Schedule created for queued alerts</URI>        <SecurityDescriptor>D"
            ":(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>    </RegistrationInfo>    <Triggers>      <!-- "
            "trigger WNF_CNET_DPU_GLOBAL_STATE_UNDER_TRACK = {0xa3bc2875, 0x1583002e} -->      <WnfStateChangeTrigger id="
            "\"DataSenseTrigger\">        <StateName>7528bca32e008315</StateName>        <Data>01</Data>        <DataOffs"
            "et>0</DataOffset>      </WnfStateChangeTrigger>      <!-- trigger WNF_SEB_FREE_NETWORK_PRESENT = {0xa3bc0875"
            ", 0x41840b3e} -->      <WnfStateChangeTrigger id=\"FreeNetworkTrigger\">        <StateName>7510BCA33E0B8441<"
            "/StateName>        <Data>03</Data>        <DataOffset>0</DataOffset>      </WnfStateChangeTrigger>    </Trig"
            "gers>    <Principals>        <Principal id=\"LocalSystem\">            <UserId>S-1-5-18</UserId>            "
            "<RunLevel>HighestAvailable</RunLevel>        </Principal>    </Principals>    <Settings>        <MultipleIns"
            "tancesPolicy>IgnoreNew</MultipleInstancesPolicy>        <DisallowStartIfOnBatteries>false</DisallowStartIfOn"
            "Batteries>        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>        <AllowHardTerminate>false</A"
            "llowHardTerminate>        <StartWhenAvailable>true</StartWhenAvailable>        <RunOnlyIfNetworkAvailable>tr"
            "ue</RunOnlyIfNetworkAvailable>        <AllowStartOnDemand>true</AllowStartOnDemand>        <Hidden>false</Hi"
            "dden>        <RunOnlyIfIdle>false</RunOnlyIfIdle>        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedul"
            "ingEngine>    </Settings>    <Actions Context=\"LocalSystem\">        <Exec>            <Command>%windir%\\s"
            "ystem32\\deviceenroller.exe</Command>        </Exec>    </Actions></Task>",
           v10,
           v17 / 0x3C);
  if ( Task >= 0 )
  {
    if ( !a3 )
      goto LABEL_23;
    Task = RunQueuedSession(a2);
    if ( Task >= 0 )
      goto LABEL_23;
    v13 = 336;
  }
  else
  {
    v13 = 328;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
    (const char *)(unsigned int)Task,
    v15);
LABEL_23:
  LocalFree(v10);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x18001f444  mov     rax, rsp
0x18001f447  mov     [rax+8], rbx
0x18001f44b  push    rbp
0x18001f44c  push    rsi
0x18001f44d  push    rdi
0x18001f44e  sub     rsp, 30h
0x18001f452  mov     bpl, r8b
0x18001f455  mov     rsi, rdx
0x18001f458  mov     rdi, rcx
0x18001f45b  mov     dword ptr [rax+18h], 0
0x18001f462  test    r8b, r8b
0x18001f465  jz      short loc_18001F4C0
0x18001f467  mov     dword ptr [rax+20h], 0
0x18001f46e  lea     r9, [rax+20h]
0x18001f472  lea     r8, aQueuedSchedule; "Queued Schedule created for queued aler"...
0x18001f479  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x18001f480  call    cs:__imp_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z; DmIsTaskScheduled(ushort const *,ushort const *,ushort const *,int *)
0x18001f487  nop     dword ptr [rax+rax+00h]
0x18001f48c  mov     ebx, eax
0x18001f48e  test    eax, eax
0x18001f490  jns     short loc_18001F4B2
0x18001f492  mov     rcx, [rsp+48h]; this
0x18001f497  mov     r9d, eax; char *
0x18001f49a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001f4a1  mov     edx, 124h; void *
0x18001f4a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4ab  mov     eax, ebx
0x18001f4ad  jmp     loc_18001F67C
0x18001f4b2  cmp     dword ptr [rsp+48h+arg_18], 0
0x18001f4b7  jz      short loc_18001F4C0
0x18001f4b9  xor     eax, eax
0x18001f4bb  jmp     loc_18001F67C
0x18001f4c0  xor     edx, edx
0x18001f4c2  mov     rcx, [rdi+1D8h]
0x18001f4c9  call    cs:__imp__o_wcstod
0x18001f4d0  nop     dword ptr [rax+rax+00h]
0x18001f4d5  comisd  xmm0, cs:__real@4010000000000000
0x18001f4dd  jb      loc_18001F585
0x18001f4e3  lea     rax, aBatching; "Batching"
0x18001f4ea  mov     qword ptr [rsp+48h+var_28], rax; int
0x18001f4ef  lea     r9, asc_1800273F4; "\\"
0x18001f4f6  mov     r8, [rdi+18h]
0x18001f4fa  mov     rdx, cs:qword_180032D98
0x18001f501  mov     ecx, 4
0x18001f506  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18001f50d  nop     dword ptr [rax+rax+00h]
0x18001f512  mov     rbx, rax
0x18001f515  mov     [rsp+48h+arg_18], rax
0x18001f51a  test    rax, rax
0x18001f51d  jnz     short loc_18001F543
0x18001f51f  mov     rcx, [rsp+48h]; this
0x18001f524  mov     ebx, 8007000Eh
0x18001f529  mov     r9d, ebx; char *
0x18001f52c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001f533  mov     edx, 132h; void *
0x18001f538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f53d  nop
0x18001f53e  jmp     loc_18001F4AB
0x18001f543  lea     r9, [rsp+48h+arg_10]
0x18001f548  lea     r8, aWindowsize; "WindowSize"
0x18001f54f  mov     rdx, rbx
0x18001f552  mov     rcx, 0FFFFFFFF80000002h
0x18001f559  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001f560  nop     dword ptr [rax+rax+00h]
0x18001f565  mov     edi, eax
0x18001f567  cmp     eax, 80070002h
0x18001f56c  jnz     short loc_18001F5D8
0x18001f56e  mov     [rsp+48h+arg_10], 12Ch
0x18001f576  mov     rcx, rbx; hMem
0x18001f579  call    cs:__imp_LocalFree
0x18001f580  nop     dword ptr [rax+rax+00h]
0x18001f585  lea     r9, aCQ; "\" /c /q"
0x18001f58c  mov     r8, rsi
0x18001f58f  lea     rdx, aO; "/o \""
0x18001f596  mov     ecx, 3
0x18001f59b  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18001f5a2  nop     dword ptr [rax+rax+00h]
0x18001f5a7  mov     rbx, rax
0x18001f5aa  mov     [rsp+48h+arg_18], rax
0x18001f5af  test    rax, rax
0x18001f5b2  jnz     short loc_18001F5F8
0x18001f5b4  mov     rcx, [rsp+48h]; this
0x18001f5b9  mov     ebx, 8007000Eh
0x18001f5be  mov     r9d, ebx; char *
0x18001f5c1  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001f5c8  mov     edx, 13Eh; void *
0x18001f5cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f5d2  nop
0x18001f5d3  jmp     loc_18001F4AB
0x18001f5d8  test    edi, edi
0x18001f5da  jns     short loc_18001F576
0x18001f5dc  mov     rcx, [rsp+48h]; this
0x18001f5e1  mov     r9d, edi; char *
0x18001f5e4  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001f5eb  mov     edx, 13Ah; void *
0x18001f5f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f5f5  nop
0x18001f5f6  jmp     short loc_18001F66B
0x18001f5f8  mov     eax, 88888889h
0x18001f5fd  mul     [rsp+48h+arg_10]
0x18001f601  shr     edx, 5
0x18001f604  mov     [rsp+48h+var_20], edx
0x18001f608  mov     qword ptr [rsp+48h+var_28], rbx; int
0x18001f60d  lea     r9, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x18001f614  lea     r8, aQueuedSchedule; "Queued Schedule created for queued aler"...
0x18001f61b  mov     rdx, rsi
0x18001f61e  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x18001f625  call    cs:__imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18001f62c  nop     dword ptr [rax+rax+00h]
0x18001f631  mov     edi, eax
0x18001f633  test    eax, eax
0x18001f635  jns     short loc_18001F63E
0x18001f637  mov     edx, 148h
0x18001f63c  jmp     short loc_18001F656
0x18001f63e  test    bpl, bpl
0x18001f641  jz      short loc_18001F66B
0x18001f643  mov     rcx, rsi; unsigned __int16 *
0x18001f646  call    ?RunQueuedSession@@YAJPEBG@Z; RunQueuedSession(ushort const *)
0x18001f64b  mov     edi, eax
0x18001f64d  test    eax, eax
0x18001f64f  jns     short loc_18001F66B
0x18001f651  mov     edx, 150h; void *
0x18001f656  mov     r9d, edi; char *
0x18001f659  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001f660  mov     rcx, [rsp+48h]; this
0x18001f665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f66a  nop
0x18001f66b  mov     rcx, rbx; hMem
0x18001f66e  call    cs:__imp_LocalFree
0x18001f675  nop     dword ptr [rax+rax+00h]
0x18001f67a  mov     eax, edi
0x18001f67c  mov     rbx, [rsp+48h+arg_0]
0x18001f681  add     rsp, 30h
0x18001f685  pop     rdi
0x18001f686  pop     rsi
0x18001f687  pop     rbp
0x18001f688  retn
```
