# EnsureUserTasksCreated(void)

- ea: `0x18000f798`
- end: `0x18000f9e0`
- name: `?EnsureUserTasksCreated@@YAJXZ`
- size: `584`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010060`

## callees

- `0x18000bab4`
- `0x18000f798`
- `0x18003b010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18000f7b1`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18000f7b1`
- `DMCmnUtils!DmCreateTask` at `0x18000f93f`
- `DMCmnUtils!DmCreateTask` at `0x18000f93f`

## string_xrefs

- `0x18000f928`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-102)</Description>        <URI>\Microsoft\Windows\EnterpriseMgmt\Recreate MDM User Schedules</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>    </RegistrationInfo>    <Trigg`
- `0x18000f91c`: `-RescheduleUserTasks`
- `0x18000f92f`: `Schedule created by enrollment client to reschedule user tasks`

## pseudocode

```c
__int64 EnsureUserTasksCreated(void)
{
  __int64 DatabaseManagerInstance; // rbx
  __int64 (__fastcall *v1)(__int64, __int64, __int64 *); // rdi
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64 *); // rdi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int Task; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-10h]
  int v22; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v24; // [rsp+50h] [rbp+20h] BYREF
  __int64 v25; // [rsp+58h] [rbp+28h] BYREF

  v24 = 0;
  v25 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v1 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  v2 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = v1(DatabaseManagerInstance, 222306401, &v24);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x251,
      (unsigned int)"onecoreuap\\admin\\dm\\pushrouter\\prcorelib\\api.cpp",
      (const char *)(unsigned int)v3,
      v21);
    v5 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v4;
  }
  v8 = v24;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL);
  v10 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v9(v8, &v25);
  v4 = v11;
  if ( v11 == 1 )
  {
    v12 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 2147943568LL;
  }
  else
  {
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecoreuap\\admin\\dm\\pushrouter\\prcorelib\\api.cpp",
        (const char *)(unsigned int)v11,
        v21);
      v14 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v15 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return v4;
    }
    Task = DmCreateTask(
             L"\\Microsoft\\Windows\\EnterpriseMgmt",
             0,
             L"Schedule created by enrollment client to reschedule user tasks",
             L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsof"
              "t-com:asm.v3\">    <RegistrationInfo>        <Author>$(@%systemRoot%\\system32\\deviceenroller.exe,-101)</"
              "Author>        <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-102)</Description>        <URI>"
              "\\Microsoft\\Windows\\EnterpriseMgmt\\Recreate MDM User Schedules</URI>        <SecurityDescriptor>D:(A;;F"
              "A;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>    </RegistrationInfo>    <Triggers>        <LogonT"
              "rigger>            <Enabled>true</Enabled>            <Delay>PT1M</Delay>        </LogonTrigger>    </Trig"
              "gers>    <Principals>        <Principal id=\"LocalSystem\">            <UserId>S-1-5-18</UserId>          "
              "  <RunLevel>HighestAvailable</RunLevel>        </Principal>    </Principals>    <Settings>        <Multipl"
              "eInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>        <DisallowStartIfOnBatteries>false</DisallowSta"
              "rtIfOnBatteries>        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>        <AllowHardTerminate>"
              "false</AllowHardTerminate>        <StartWhenAvailable>true</StartWhenAvailable>        <RunOnlyIfNetworkAv"
              "ailable>true</RunOnlyIfNetworkAvailable>        <AllowStartOnDemand>true</AllowStartOnDemand>        <Hidd"
              "en>false</Hidden>        <RunOnlyIfIdle>false</RunOnlyIfIdle>        <UseUnifiedSchedulingEngine>true</Use"
              "UnifiedSchedulingEngine>    </Settings>    <Actions Context=\"LocalSystem\">        <Exec>            <Com"
              "mand>%windir%\\system32\\DeviceEnroller.exe</Command>        </Exec>    </Actions></Task>",
             L"-RescheduleUserTasks",
             0);
    v4 = Task;
    if ( Task < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecoreuap\\admin\\dm\\pushrouter\\prcorelib\\api.cpp",
        (const char *)(unsigned int)Task,
        v22);
      v17 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return v4;
    }
    v19 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000f798  mov     [rsp-18h+arg_10], rbx
0x18000f79d  push    rbp
0x18000f79e  push    rsi
0x18000f79f  push    rdi
0x18000f7a0  mov     rbp, rsp
0x18000f7a3  sub     rsp, 30h
0x18000f7a7  xor     esi, esi
0x18000f7a9  mov     [rbp+arg_0], rsi
0x18000f7ad  mov     [rbp+arg_8], rsi
0x18000f7b1  call    cs:__imp_GetDatabaseManagerInstance
0x18000f7b7  mov     rbx, rax
0x18000f7ba  mov     rcx, [rax]
0x18000f7bd  mov     rdi, [rcx+20h]
0x18000f7c1  mov     rcx, [rbp+arg_0]
0x18000f7c5  test    rcx, rcx
0x18000f7c8  jz      short loc_18000F7DB
0x18000f7ca  mov     [rbp+arg_0], rsi
0x18000f7ce  mov     rdx, [rcx]
0x18000f7d1  mov     rax, [rdx+10h]
0x18000f7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7da  nop
0x18000f7db  lea     r8, [rbp+arg_0]
0x18000f7df  mov     edx, 0D402061h
0x18000f7e4  mov     rcx, rbx
0x18000f7e7  mov     rax, rdi
0x18000f7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ef  mov     ebx, eax
0x18000f7f1  test    eax, eax
0x18000f7f3  jns     short loc_18000F849
0x18000f7f5  mov     rcx, [rbp+18h]; this
0x18000f7f9  mov     r9d, eax; char *
0x18000f7fc  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\pushrouter\\prco"...
0x18000f803  mov     edx, 251h; void *
0x18000f808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f80d  nop
0x18000f80e  mov     rcx, [rbp+arg_8]
0x18000f812  test    rcx, rcx
0x18000f815  jz      short loc_18000F828
0x18000f817  mov     [rbp+arg_8], rsi
0x18000f81b  mov     rax, [rcx]
0x18000f81e  mov     rax, [rax+10h]
0x18000f822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f827  nop
0x18000f828  mov     rcx, [rbp+arg_0]
0x18000f82c  test    rcx, rcx
0x18000f82f  jz      short loc_18000F842
0x18000f831  mov     [rbp+arg_0], rsi
0x18000f835  mov     rax, [rcx]
0x18000f838  mov     rax, [rax+10h]
0x18000f83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f841  nop
0x18000f842  mov     eax, ebx
0x18000f844  jmp     loc_18000F9D3
0x18000f849  mov     rbx, [rbp+arg_0]
0x18000f84d  mov     rax, [rbx]
0x18000f850  mov     rdi, [rax+18h]
0x18000f854  mov     rcx, [rbp+arg_8]
0x18000f858  test    rcx, rcx
0x18000f85b  jz      short loc_18000F86E
0x18000f85d  mov     [rbp+arg_8], rsi
0x18000f861  mov     rdx, [rcx]
0x18000f864  mov     rax, [rdx+10h]
0x18000f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f86d  nop
0x18000f86e  lea     rdx, [rbp+arg_8]
0x18000f872  mov     rcx, rbx
0x18000f875  mov     rax, rdi
0x18000f878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87d  mov     ebx, eax
0x18000f87f  cmp     eax, 1
0x18000f882  jnz     short loc_18000F8C2
0x18000f884  mov     rcx, [rbp+arg_8]
0x18000f888  test    rcx, rcx
0x18000f88b  jz      short loc_18000F89E
0x18000f88d  mov     [rbp+arg_8], rsi
0x18000f891  mov     rax, [rcx]
0x18000f894  mov     rax, [rax+10h]
0x18000f898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f89d  nop
0x18000f89e  mov     rcx, [rbp+arg_0]
0x18000f8a2  test    rcx, rcx
0x18000f8a5  jz      short loc_18000F8B8
0x18000f8a7  mov     [rbp+arg_0], rsi
0x18000f8ab  mov     rax, [rcx]
0x18000f8ae  mov     rax, [rax+10h]
0x18000f8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8b7  nop
0x18000f8b8  mov     eax, 80070490h
0x18000f8bd  jmp     loc_18000F9D3
0x18000f8c2  test    ebx, ebx
0x18000f8c4  jns     short loc_18000F918
0x18000f8c6  mov     rcx, [rbp+18h]; this
0x18000f8ca  mov     r9d, ebx; char *
0x18000f8cd  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\pushrouter\\prco"...
0x18000f8d4  mov     edx, 255h; void *
0x18000f8d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8de  nop
0x18000f8df  mov     rcx, [rbp+arg_8]
0x18000f8e3  test    rcx, rcx
0x18000f8e6  jz      short loc_18000F8F9
0x18000f8e8  mov     [rbp+arg_8], rsi
0x18000f8ec  mov     rax, [rcx]
0x18000f8ef  mov     rax, [rax+10h]
0x18000f8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f8  nop
0x18000f8f9  mov     rcx, [rbp+arg_0]
0x18000f8fd  test    rcx, rcx
0x18000f900  jz      short loc_18000F913
0x18000f902  mov     [rbp+arg_0], rsi
0x18000f906  mov     rax, [rcx]
0x18000f909  mov     rax, [rax+10h]
0x18000f90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f912  nop
0x18000f913  jmp     loc_18000F842
0x18000f918  mov     [rsp+30h+var_8], esi
0x18000f91c  lea     rax, aRescheduleuser; "-RescheduleUserTasks"
0x18000f923  mov     qword ptr [rsp+30h+var_10], rax; int
0x18000f928  lea     r9, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x18000f92f  lea     r8, aScheduleCreate_0; "Schedule created by enrollment client t"...
0x18000f936  xor     edx, edx
0x18000f938  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18000f93f  call    cs:__imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18000f945  mov     ebx, eax
0x18000f947  test    eax, eax
0x18000f949  jns     short loc_18000F99D
0x18000f94b  mov     rcx, [rbp+18h]; this
0x18000f94f  mov     r9d, eax; char *
0x18000f952  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\pushrouter\\prco"...
0x18000f959  mov     edx, 25Dh; void *
0x18000f95e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f963  nop
0x18000f964  mov     rcx, [rbp+arg_8]
0x18000f968  test    rcx, rcx
0x18000f96b  jz      short loc_18000F97E
0x18000f96d  mov     [rbp+arg_8], rsi
0x18000f971  mov     rax, [rcx]
0x18000f974  mov     rax, [rax+10h]
0x18000f978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f97d  nop
0x18000f97e  mov     rcx, [rbp+arg_0]
0x18000f982  test    rcx, rcx
0x18000f985  jz      short loc_18000F998
0x18000f987  mov     [rbp+arg_0], rsi
0x18000f98b  mov     rax, [rcx]
0x18000f98e  mov     rax, [rax+10h]
0x18000f992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f997  nop
0x18000f998  jmp     loc_18000F842
0x18000f99d  mov     rcx, [rbp+arg_8]
0x18000f9a1  test    rcx, rcx
0x18000f9a4  jz      short loc_18000F9B7
0x18000f9a6  mov     [rbp+arg_8], rsi
0x18000f9aa  mov     rax, [rcx]
0x18000f9ad  mov     rax, [rax+10h]
0x18000f9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b6  nop
0x18000f9b7  mov     rcx, [rbp+arg_0]
0x18000f9bb  test    rcx, rcx
0x18000f9be  jz      short loc_18000F9D1
0x18000f9c0  mov     [rbp+arg_0], rsi
0x18000f9c4  mov     rax, [rcx]
0x18000f9c7  mov     rax, [rax+10h]
0x18000f9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d0  nop
0x18000f9d1  xor     eax, eax
0x18000f9d3  mov     rbx, [rsp+30h+arg_10]
0x18000f9d8  add     rsp, 30h
0x18000f9dc  pop     rdi
0x18000f9dd  pop     rsi
0x18000f9de  pop     rbp
0x18000f9df  retn
```
