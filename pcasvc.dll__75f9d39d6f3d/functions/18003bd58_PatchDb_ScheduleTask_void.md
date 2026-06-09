# PatchDb_ScheduleTask(void)

- ea: `0x18003bd58`
- end: `0x18003c090`
- name: `?PatchDb_ScheduleTask@@YAKXZ`
- size: `824`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003bc20`

## callees

- `0x180012920`
- `0x18003bd58`
- `0x1800f7010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003be5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18003beed`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bf47`
- `OLEAUT32!__imp_SysAllocString` at `0x18003be5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18003beed`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bf47`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bff9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c002`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c00b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bff9`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c002`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c00b`
- `OLEAUT32!__imp_VariantInit` at `0x18003bd95`
- `OLEAUT32!__imp_VariantInit` at `0x18003bd95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bdbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bdbb`

## string_xrefs

- `0x18003bdd4`: `PatchDb_ScheduleTask`
- `0x18003be75`: `PatchDb_ScheduleTask`
- `0x18003be68`: `Failed to allocate task folder name`
- `0x18003bf40`: `PcaPatchDbTask`
- `0x18003bee6`: `\n<Task version="1.6" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n  <RegistrationInfo>\n    <Source>Microsoft Corporation</Source>\n    <Author>Microsoft Corporation</Author>\n    <Version>1.0</Version>\n    <Description>Updates compatibility database</Description>\n    <URI>\Microsoft\Windows\Application Experience\PCA Patch Db Task</URI>\n    <SecurityDescriptor>D:(A;;GA;;;BA)(A;;GA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>\n  </RegistrationInfo>\n  <Triggers>\n    <TimeTrig`
- `0x18003bdc7`: `Failed to create a task scheduler %x`
- `0x18003bf00`: `Failed to allocate task definition content`
- `0x18003bed4`: `Failed to create task definition %x`
- `0x18003bf5a`: `Failed to allocate task name`
- `0x18003bf2e`: `Failed to put task definition %x`
- `0x18003bfe2`: `Failed to register task %x`

## pseudocode

```c
__int64 PatchDb_ScheduleTask(void)
{
  OLECHAR *v0; // rsi
  OLECHAR *v1; // r14
  OLECHAR *v2; // rdi
  HRESULT v3; // ebx
  const char *v4; // r9
  int v5; // r8d
  __int64 v6; // rax
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  BSTR v8; // rax
  BSTR v9; // rax
  __int64 (__fastcall *v10)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, _DWORD, VARIANTARG *, __int64 *); // rax
  VARIANTARG pvarg; // [rsp+50h] [rbp-79h] BYREF
  VARIANTARG v13; // [rsp+70h] [rbp-59h] BYREF
  VARIANTARG v14; // [rsp+90h] [rbp-39h] BYREF
  VARIANTARG v15; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v16; // [rsp+D0h] [rbp+7h] BYREF
  IRecordInfo *pRecInfo; // [rsp+E0h] [rbp+17h]
  LPVOID ppv; // [rsp+130h] [rbp+67h] BYREF
  __int64 v19; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+140h] [rbp+77h] BYREF
  __int64 v21; // [rsp+148h] [rbp+7Fh] BYREF

  v0 = 0;
  ppv = 0;
  v20 = 0;
  v19 = 0;
  v1 = 0;
  v21 = 0;
  v2 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v3 < 0 )
  {
    v4 = "Failed to create a task scheduler %x";
    v5 = 363;
LABEL_7:
    AslLogCallPrintf(1, (unsigned int)"PatchDb_ScheduleTask", v5, (_DWORD)v4);
    goto LABEL_21;
  }
  v16 = *(_OWORD *)&pvarg.vt;
  v6 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v13 = pvarg;
  v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v6 + 80);
  v14 = pvarg;
  v15 = pvarg;
  v3 = v7(ppv, &v15, &v14, &v13, &v16);
  if ( v3 < 0 )
  {
    v4 = "Failed to connect to scheduler %x";
    v5 = 370;
    goto LABEL_7;
  }
  v8 = SysAllocString(L"Microsoft\\Windows\\Application Experience");
  v0 = v8;
  if ( !v8 )
  {
    v4 = "Failed to allocate task folder name";
    v5 = 377;
    goto LABEL_7;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v8, &v20);
  if ( v3 < 0 )
  {
    v4 = "Failed to get scheduler folder %x";
    v5 = 384;
    goto LABEL_7;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, 0, &v19);
  if ( v3 < 0 )
  {
    v4 = "Failed to create task definition %x";
    v5 = 391;
    goto LABEL_7;
  }
  v9 = SysAllocString(
         L"\n"
          "<Task version=\"1.6\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\n"
          "  <RegistrationInfo>\n"
          "    <Source>Microsoft Corporation</Source>\n"
          "    <Author>Microsoft Corporation</Author>\n"
          "    <Version>1.0</Version>\n"
          "    <Description>Updates compatibility database</Description>\n"
          "    <URI>\\Microsoft\\Windows\\Application Experience\\PCA Patch Db Task</URI>\n"
          "    <SecurityDescriptor>D:(A;;GA;;;BA)(A;;GA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>\n"
          "  </RegistrationInfo>\n"
          "  <Triggers>\n"
          "    <TimeTrigger>\n"
          "      <Repetition>\n"
          "        <Interval>PT12H</Interval>\n"
          "        <StopAtDurationEnd>false</StopAtDurationEnd>\n"
          "      </Repetition>\n"
          "      <StartBoundary>2008-09-01T03:00:00</StartBoundary>\n"
          "      <Enabled>true</Enabled>\n"
          "      <RandomDelay>PT2H</RandomDelay>\n"
          "    </TimeTrigger>\n"
          "  </Triggers>\n"
          "  <Principals>\n"
          "    <Principal id=\"LocalSystem\">\n"
          "      <UserId>S-1-5-18</UserId>\n"
          "      <RunLevel>LeastPrivilege</RunLevel>\n"
          "    </Principal>\n"
          "  </Principals>\n"
          "  <Settings>\n"
          "    <MultipleInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>\n"
          "    <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
          "    <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
          "    <AllowHardTerminate>true</AllowHardTerminate>\n"
          "    <StartWhenAvailable>true</StartWhenAvailable>\n"
          "    <RunOnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable>\n"
          "    <IdleSettings>\n"
          "      <StopOnIdleEnd>false</StopOnIdleEnd>\n"
          "    </IdleSettings>\n"
          "    <AllowStartOnDemand>true</AllowStartOnDemand>\n"
          "    <Enabled>true</Enabled>\n"
          "    <Hidden>false</Hidden>\n"
          "    <RunOnlyIfIdle>false</RunOnlyIfIdle>\n"
          "    <DisallowStartOnRemoteAppSession>false</DisallowStartOnRemoteAppSession>\n"
          "    <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
          "    <WakeToRun>false</WakeToRun>\n"
          "    <ExecutionTimeLimit>P1D</ExecutionTimeLimit>\n"
          "    <Priority>7</Priority>\n"
          "  </Settings>\n"
          "  <Actions Context=\"LocalSystem\">\n"
          "    <Exec>\n"
          "      <Command>%windir%\\system32\\rundll32.exe</Command>\n"
          "      <Arguments>%windir%\\system32\\PcaSvc.dll,PcaPatchSdbTask</Arguments>\n"
          "    </Exec>\n"
          "  </Actions>\n"
          "</Task>\n");
  v2 = v9;
  if ( !v9 )
  {
    v3 = -2147024888;
    v4 = "Failed to allocate task definition content";
    v5 = 399;
    goto LABEL_7;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v19 + 160LL))(v19, v9);
  if ( v3 < 0 )
  {
    v4 = "Failed to put task definition %x";
    v5 = 406;
    goto LABEL_7;
  }
  v1 = SysAllocString(L"PcaPatchDbTask");
  if ( !v1 )
  {
    v3 = -2147024888;
    v4 = "Failed to allocate task name";
    v5 = 414;
    goto LABEL_7;
  }
  v10 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, VARIANTARG *, VARIANTARG *, _DWORD, VARIANTARG *, __int64 *))(*(_QWORD *)v20 + 136LL);
  v15 = pvarg;
  v14 = pvarg;
  v13 = pvarg;
  v3 = v10(v20, v1, v19, 6, &v13, &v14, 0, &v15, &v21);
  if ( v3 < 0 )
  {
    v4 = "Failed to register task %x";
    v5 = 428;
    goto LABEL_7;
  }
  v3 = 0;
LABEL_21:
  SysFreeString(v0);
  SysFreeString(v1);
  SysFreeString(v2);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v3 < 0 )
  {
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v3;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003bd58  push    rbp
0x18003bd5a  push    rbx
0x18003bd5b  push    rsi
0x18003bd5c  push    rdi
0x18003bd5d  push    r12
0x18003bd5f  push    r14
0x18003bd61  lea     rbp, [rsp-2Fh]
0x18003bd66  sub     rsp, 0F8h
0x18003bd6d  xor     esi, esi
0x18003bd6f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003bd73  xorps   xmm0, xmm0
0x18003bd76  mov     [rbp+57h+arg_0], rsi
0x18003bd7a  xor     eax, eax
0x18003bd7c  mov     [rbp+57h+arg_10], rsi
0x18003bd80  mov     [rbp+57h+arg_8], rsi
0x18003bd84  xor     r14d, r14d
0x18003bd87  mov     [rbp+57h+arg_18], rsi
0x18003bd8b  xor     edi, edi
0x18003bd8d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003bd91  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003bd95  call    cs:__imp_VariantInit
0x18003bd9b  lea     rax, [rbp+57h+arg_0]
0x18003bd9f  xor     edx, edx; pUnkOuter
0x18003bda1  lea     r12d, [rsi+1]
0x18003bda5  mov     [rsp+120h+ppv], rax; ppv
0x18003bdaa  mov     r8d, r12d; dwClsContext
0x18003bdad  lea     r9, IID_ITaskService; riid
0x18003bdb4  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003bdbb  call    cs:__imp_CoCreateInstance
0x18003bdc1  mov     ebx, eax
0x18003bdc3  test    eax, eax
0x18003bdc5  jns     short loc_18003BDEC
0x18003bdc7  lea     r9, aFailedToCreate_83; "Failed to create a task scheduler %x"
0x18003bdce  mov     r8d, 16Bh
0x18003bdd4  lea     rdx, aPatchdbSchedul; "PatchDb_ScheduleTask"
0x18003bddb  mov     dword ptr [rsp+120h+ppv], eax
0x18003bddf  mov     ecx, r12d
0x18003bde2  call    AslLogCallPrintf
0x18003bde7  jmp     loc_18003BFF6
0x18003bdec  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18003bdf0  lea     rdx, [rbp+57h+var_50]
0x18003bdf4  mov     rcx, [rbp+57h+arg_0]
0x18003bdf8  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18003bdfd  lea     r9, [rbp+57h+var_B0]
0x18003be01  mov     [rsp+120h+ppv], rdx
0x18003be06  lea     r8, [rbp+57h+var_90]
0x18003be0a  lea     rdx, [rbp+57h+var_70]
0x18003be0e  movaps  [rbp+57h+var_50], xmm1
0x18003be12  mov     rax, [rcx]
0x18003be15  movsd   [rbp+57h+var_40], xmm0
0x18003be1a  movaps  [rbp+57h+var_B0], xmm1
0x18003be1e  movsd   [rbp+57h+var_A0], xmm0
0x18003be23  mov     rax, [rax+50h]
0x18003be27  movaps  [rbp+57h+var_90], xmm1
0x18003be2b  movsd   [rbp+57h+var_80], xmm0
0x18003be30  movaps  [rbp+57h+var_70], xmm1
0x18003be34  movsd   [rbp+57h+var_60], xmm0
0x18003be39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be3e  mov     ebx, eax
0x18003be40  test    eax, eax
0x18003be42  jns     short loc_18003BE53
0x18003be44  lea     r9, aFailedToConnec_2; "Failed to connect to scheduler %x"
0x18003be4b  mov     r8d, 172h
0x18003be51  jmp     short loc_18003BDD4
0x18003be53  lea     rcx, psz; "Microsoft\\Windows\\Application Experie"...
0x18003be5a  call    cs:__imp_SysAllocString
0x18003be60  mov     rsi, rax
0x18003be63  test    rax, rax
0x18003be66  jnz     short loc_18003BE89
0x18003be68  lea     r9, aFailedToAlloca_6; "Failed to allocate task folder name"
0x18003be6f  mov     r8d, 179h
0x18003be75  lea     rdx, aPatchdbSchedul; "PatchDb_ScheduleTask"
0x18003be7c  mov     ecx, r12d
0x18003be7f  call    AslLogCallPrintf
0x18003be84  jmp     loc_18003BFF6
0x18003be89  mov     rcx, [rbp+57h+arg_0]
0x18003be8d  lea     r8, [rbp+57h+arg_10]
0x18003be91  mov     rdx, rsi
0x18003be94  mov     rax, [rcx]
0x18003be97  mov     rax, [rax+38h]
0x18003be9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bea0  mov     ebx, eax
0x18003bea2  test    eax, eax
0x18003bea4  jns     short loc_18003BEB8
0x18003bea6  lea     r9, aFailedToGetSch_0; "Failed to get scheduler folder %x"
0x18003bead  mov     r8d, 180h
0x18003beb3  jmp     loc_18003BDD4
0x18003beb8  mov     rcx, [rbp+57h+arg_0]
0x18003bebc  lea     r8, [rbp+57h+arg_8]
0x18003bec0  xor     edx, edx
0x18003bec2  mov     rax, [rcx]
0x18003bec5  mov     rax, [rax+48h]
0x18003bec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bece  mov     ebx, eax
0x18003bed0  test    eax, eax
0x18003bed2  jns     short loc_18003BEE6
0x18003bed4  lea     r9, aFailedToCreate; "Failed to create task definition %x"
0x18003bedb  mov     r8d, 187h
0x18003bee1  jmp     loc_18003BDD4
0x18003bee6  lea     rcx, aTaskVersion16X; "\n<Task version=\"1.6\" xmlns=\"http://"...
0x18003beed  call    cs:__imp_SysAllocString
0x18003bef3  mov     rdi, rax
0x18003bef6  test    rax, rax
0x18003bef9  jnz     short loc_18003BF12
0x18003befb  mov     ebx, 80070008h
0x18003bf00  lea     r9, aFailedToAlloca_36; "Failed to allocate task definition cont"...
0x18003bf07  mov     r8d, 18Fh
0x18003bf0d  jmp     loc_18003BE75
0x18003bf12  mov     rcx, [rbp+57h+arg_8]
0x18003bf16  mov     rdx, rdi
0x18003bf19  mov     rax, [rcx]
0x18003bf1c  mov     rax, [rax+0A0h]
0x18003bf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf28  mov     ebx, eax
0x18003bf2a  test    eax, eax
0x18003bf2c  jns     short loc_18003BF40
0x18003bf2e  lea     r9, aFailedToPutTas; "Failed to put task definition %x"
0x18003bf35  mov     r8d, 196h
0x18003bf3b  jmp     loc_18003BDD4
0x18003bf40  lea     rcx, aPcapatchdbtask; "PcaPatchDbTask"
0x18003bf47  call    cs:__imp_SysAllocString
0x18003bf4d  mov     r14, rax
0x18003bf50  test    rax, rax
0x18003bf53  jnz     short loc_18003BF6C
0x18003bf55  mov     ebx, 80070008h
0x18003bf5a  lea     r9, aFailedToAlloca_17; "Failed to allocate task name"
0x18003bf61  mov     r8d, 19Eh
0x18003bf67  jmp     loc_18003BE75
0x18003bf6c  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18003bf70  lea     rdx, [rbp+57h+arg_18]
0x18003bf74  mov     rcx, [rbp+57h+arg_10]
0x18003bf78  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18003bf7d  mov     r9d, 6
0x18003bf83  mov     r8, [rbp+57h+arg_8]
0x18003bf87  mov     [rsp+120h+var_E0], rdx
0x18003bf8c  lea     rdx, [rbp+57h+var_70]
0x18003bf90  mov     rax, [rcx]
0x18003bf93  mov     [rsp+120h+var_E8], rdx
0x18003bf98  lea     rdx, [rbp+57h+var_90]
0x18003bf9c  mov     [rsp+120h+var_F0], 0
0x18003bfa4  mov     [rsp+120h+var_F8], rdx
0x18003bfa9  lea     rdx, [rbp+57h+var_B0]
0x18003bfad  mov     rax, [rax+88h]
0x18003bfb4  mov     [rsp+120h+ppv], rdx
0x18003bfb9  mov     rdx, r14
0x18003bfbc  movaps  [rbp+57h+var_70], xmm1
0x18003bfc0  movsd   [rbp+57h+var_60], xmm0
0x18003bfc5  movaps  [rbp+57h+var_90], xmm1
0x18003bfc9  movsd   [rbp+57h+var_80], xmm0
0x18003bfce  movaps  [rbp+57h+var_B0], xmm1
0x18003bfd2  movsd   [rbp+57h+var_A0], xmm0
0x18003bfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfdc  mov     ebx, eax
0x18003bfde  test    eax, eax
0x18003bfe0  jns     short loc_18003BFF4
0x18003bfe2  lea     r9, aFailedToRegist_1; "Failed to register task %x"
0x18003bfe9  mov     r8d, 1ACh
0x18003bfef  jmp     loc_18003BDD4
0x18003bff4  xor     ebx, ebx
0x18003bff6  mov     rcx, rsi; bstrString
0x18003bff9  call    cs:__imp_SysFreeString
0x18003bfff  mov     rcx, r14; bstrString
0x18003c002  call    cs:__imp_SysFreeString
0x18003c008  mov     rcx, rdi; bstrString
0x18003c00b  call    cs:__imp_SysFreeString
0x18003c011  mov     rcx, [rbp+57h+arg_18]
0x18003c015  test    rcx, rcx
0x18003c018  jz      short loc_18003C026
0x18003c01a  mov     rax, [rcx]
0x18003c01d  mov     rax, [rax+10h]
0x18003c021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c026  mov     rcx, [rbp+57h+arg_8]
0x18003c02a  test    rcx, rcx
0x18003c02d  jz      short loc_18003C03B
0x18003c02f  mov     rax, [rcx]
0x18003c032  mov     rax, [rax+10h]
0x18003c036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c03b  mov     rcx, [rbp+57h+arg_10]
0x18003c03f  test    rcx, rcx
0x18003c042  jz      short loc_18003C050
0x18003c044  mov     rax, [rcx]
0x18003c047  mov     rax, [rax+10h]
0x18003c04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c050  mov     rcx, [rbp+57h+arg_0]
0x18003c054  test    rcx, rcx
0x18003c057  jz      short loc_18003C065
0x18003c059  mov     rax, [rcx]
0x18003c05c  mov     rax, [rax+10h]
0x18003c060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c065  test    ebx, ebx
0x18003c067  js      short loc_18003C06D
0x18003c069  xor     ebx, ebx
0x18003c06b  jmp     short loc_18003C07E
0x18003c06d  mov     eax, ebx
0x18003c06f  and     eax, 1FFF0000h
0x18003c074  cmp     eax, 70000h
0x18003c079  jnz     short loc_18003C07E
0x18003c07b  movzx   ebx, bx
0x18003c07e  mov     eax, ebx
0x18003c080  add     rsp, 0F8h
0x18003c087  pop     r14
0x18003c089  pop     r12
0x18003c08b  pop     rdi
0x18003c08c  pop     rsi
0x18003c08d  pop     rbx
0x18003c08e  pop     rbp
0x18003c08f  retn
```
