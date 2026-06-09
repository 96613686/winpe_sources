# DfdGetDefaultPolicyAndSMART(HWND__ *,HINSTANCE__ *,char *,int)

- ea: `0x180002450`
- end: `0x1800025e6`
- name: `?DfdGetDefaultPolicyAndSMART@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEADH@Z`
- size: `406`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, char *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002450`
- `0x18000357c`
- `0x180005d68`
- `0x180006b10`
- `0x180007718`
- `0x180007754`
- `0x180007970`
- `0x180007bc0`
- `0x180008370`

## import_xrefs

- `ntdll!WinSqmStartSession` at `0x1800024fc`
- `ntdll!WinSqmStartSession` at `0x1800024fc`
- `ntdll!WinSqmIsOptedIn` at `0x1800024e6`
- `ntdll!WinSqmIsOptedIn` at `0x1800024e6`
- `ntdll!WinSqmSetDWORD` at `0x180002531`
- `ntdll!WinSqmSetDWORD` at `0x180002531`
- `KERNEL32!HeapSetInformation` at `0x180002481`
- `KERNEL32!HeapSetInformation` at `0x180002481`
- `ADVAPI32!EventRegister` at `0x1800024cd`
- `ADVAPI32!EventRegister` at `0x1800024cd`

## pseudocode

```c
// Weak service/task config audit 2026-06-06: SYSTEM DiskDiagnosticDataCollector entry; fixed task name only, policy/source registry is HKLM protected in RELEASE ACL probes.
__int64 __fastcall DfdGetDefaultPolicyAndSMART(HWND a1, HINSTANCE a2, char *a3)
{
  ULONG v3; // eax
  ULONGLONG v4; // rdx
  DfdCollector *v5; // rcx
  int IsOptedIn; // edi
  DfdManager *v7; // rcx
  unsigned int WDIPolicy; // ebx
  unsigned int SMARTCapability; // ebx
  unsigned __int16 v10; // ax
  unsigned int v12; // [rsp+20h] [rbp-19h] BYREF
  ULONGLONG RegHandle; // [rsp+28h] [rbp-11h] BYREF
  __int128 *v14; // [rsp+30h] [rbp-9h]
  __int64 started; // [rsp+38h] [rbp-1h]
  unsigned int v16; // [rsp+40h] [rbp+7h]
  char v17; // [rsp+44h] [rbp+Bh]
  __int64 v18; // [rsp+48h] [rbp+Fh]
  int v19; // [rsp+50h] [rbp+17h]
  _BYTE v20[16]; // [rsp+58h] [rbp+1Fh] BYREF
  unsigned int v21; // [rsp+68h] [rbp+2Fh]
  __int64 v22; // [rsp+70h] [rbp+37h]
  __int128 v23; // [rsp+78h] [rbp+3Fh] BYREF

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v23 = xmmword_18000BD80;
  v14 = &v23;
  v16 = 133384;
  v17 = 0;
  v19 = 0;
  v18 = 0;
  started = 0;
  v3 = EventRegister(&DFD_TASK_ETW_PROVIDER, 0, 0, &RegHandle);
  v4 = RegHandle;
  if ( v3 )
    v4 = 0;
  RegHandle = v4;
  v12 = 0;
  IsOptedIn = WinSqmIsOptedIn();
  if ( !IsOptedIn )
  {
    SMARTCapability = 0;
LABEL_8:
    DfdCollector::GetCollectorInvokeKey(v5, &v12);
    goto LABEL_9;
  }
  started = WinSqmStartSession(v14, v16, 0);
  v17 = 1;
  v22 = 0;
  WDIPolicy = DfdManager::GetWDIPolicy(v7);
  v21 = WDIPolicy;
  DfdManager::~DfdManager((DfdManager *)v20);
  WinSqmSetDWORD(started, 916, WDIPolicy);
  SMARTCapability = DfdCollector::GetSMARTCapability((DfdCollector *)&RegHandle);
  if ( SMARTCapability )
    goto LABEL_8;
  DfdCollector::WriteEvent((DfdCollector *)&RegHandle, &DFD_TASK_ETW_EVENT_OPT_IN);
  v10 = SetDFDTask(L"Microsoft-Windows-DiskDiagnosticDataCollector", 2);
  SMARTCapability = v10;
  if ( v10 )
    goto LABEL_8;
LABEL_9:
  if ( v12 < 3 )
  {
    if ( !IsOptedIn )
      DfdCollector::WriteEvent((DfdCollector *)&RegHandle, &DFD_TASK_ETW_EVENT_DEFERRED);
  }
  else
  {
    DfdCollector::WriteEvent((DfdCollector *)&RegHandle, &DFD_TASK_ETW_EVENT_GIVE_UP);
    SMARTCapability = (unsigned __int16)SetDFDTask(L"Microsoft-Windows-DiskDiagnosticDataCollector", 2);
  }
  DfdCollector::~DfdCollector((DfdCollector *)&RegHandle);
  return SMARTCapability;
}

```

## disassembly

```asm
0x180002450  mov     [rsp-8+arg_0], rbx; Weak service/task config audit 2026-06-06: SYSTEM DiskDiagnosticDataCollector entry; fixed task name only, policy/source registry is HKLM protected in RELEASE ACL probes.
0x180002455  mov     [rsp-8+arg_8], rdi
0x18000245a  push    rbp
0x18000245b  lea     rbp, [rsp-57h]
0x180002460  sub     rsp, 90h
0x180002467  mov     rax, cs:__security_cookie
0x18000246e  xor     rax, rsp
0x180002471  mov     [rbp+57h+var_8], rax
0x180002475  xor     r9d, r9d; HeapInformationLength
0x180002478  xor     r8d, r8d; HeapInformation
0x18000247b  lea     edx, [r9+1]; HeapInformationClass
0x18000247f  xor     ecx, ecx; HeapHandle
0x180002481  call    cs:__imp_HeapSetInformation
0x180002487  movups  xmm0, cs:xmmword_18000BD80
0x18000248e  movdqu  [rbp+57h+var_18], xmm0
0x180002493  lea     rax, [rbp+57h+var_18]
0x180002497  mov     [rbp+57h+var_60], rax
0x18000249b  mov     [rbp+57h+var_50], 20908h
0x1800024a2  mov     [rbp+57h+var_4C], 0
0x1800024a6  mov     [rbp+57h+var_40], 0
0x1800024ad  mov     [rbp+57h+var_48], 0
0x1800024b5  mov     [rbp+57h+var_58], 0
0x1800024bd  lea     r9, [rbp+57h+RegHandle]; RegHandle
0x1800024c1  xor     r8d, r8d; CallbackContext
0x1800024c4  xor     edx, edx; EnableCallback
0x1800024c6  lea     rcx, DFD_TASK_ETW_PROVIDER; ProviderId
0x1800024cd  call    cs:__imp_EventRegister
0x1800024d3  mov     rdx, [rbp+57h+RegHandle]
0x1800024d7  xor     ecx, ecx
0x1800024d9  test    eax, eax
0x1800024db  cmovnz  rdx, rcx
0x1800024df  mov     [rbp+57h+RegHandle], rdx
0x1800024e3  mov     [rbp+57h+var_70], ecx
0x1800024e6  call    cs:__imp_WinSqmIsOptedIn
0x1800024ec  mov     edi, eax
0x1800024ee  test    eax, eax
0x1800024f0  jz      short loc_18000256E
0x1800024f2  xor     r8d, r8d
0x1800024f5  mov     edx, [rbp+57h+var_50]
0x1800024f8  mov     rcx, [rbp+57h+var_60]
0x1800024fc  call    cs:__imp_WinSqmStartSession
0x180002502  mov     [rbp+57h+var_58], rax
0x180002506  mov     [rbp+57h+var_4C], 1
0x18000250a  mov     [rbp+57h+var_20], 0
0x180002512  call    ?GetWDIPolicy@DfdManager@@AEAAKXZ; DfdManager::GetWDIPolicy(void)
0x180002517  mov     ebx, eax
0x180002519  mov     [rbp+57h+var_28], eax
0x18000251c  lea     rcx, [rbp+57h+var_38]; this
0x180002520  call    ??1DfdManager@@QEAA@XZ; DfdManager::~DfdManager(void)
0x180002525  mov     r8d, ebx
0x180002528  mov     edx, 394h
0x18000252d  mov     rcx, [rbp+57h+var_58]
0x180002531  call    cs:__imp_WinSqmSetDWORD
0x180002537  lea     rcx, [rbp+57h+RegHandle]; this
0x18000253b  call    ?GetSMARTCapability@DfdCollector@@AEAAKXZ; DfdCollector::GetSMARTCapability(void)
0x180002540  mov     ebx, eax
0x180002542  test    eax, eax
0x180002544  jnz     short loc_180002570
0x180002546  lea     rdx, DFD_TASK_ETW_EVENT_OPT_IN; struct _EVENT_DESCRIPTOR *
0x18000254d  lea     rcx, [rbp+57h+RegHandle]; this
0x180002551  call    ?WriteEvent@DfdCollector@@AEAAXPEBU_EVENT_DESCRIPTOR@@@Z; DfdCollector::WriteEvent(_EVENT_DESCRIPTOR const *)
0x180002556  lea     edx, [rbx+2]
0x180002559  lea     rcx, aMicrosoftWindo_1; "Microsoft-Windows-DiskDiagnosticDataCol"...
0x180002560  call    ?SetDFDTask@@YAJPEBGW4DFD_JOB_ACTION@@@Z; SetDFDTask(ushort const *,DFD_JOB_ACTION)
0x180002565  movzx   ebx, ax
0x180002568  test    ebx, ebx
0x18000256a  jz      short loc_180002579
0x18000256c  jmp     short loc_180002570
0x18000256e  xor     ebx, ebx
0x180002570  lea     rdx, [rbp+57h+var_70]; unsigned int *
0x180002574  call    ?GetCollectorInvokeKey@DfdCollector@@AEAAXPEAK@Z; DfdCollector::GetCollectorInvokeKey(ulong *)
0x180002579  cmp     [rbp+57h+var_70], 3
0x18000257d  jb      short loc_1800025A5
0x18000257f  lea     rdx, DFD_TASK_ETW_EVENT_GIVE_UP; struct _EVENT_DESCRIPTOR *
0x180002586  lea     rcx, [rbp+57h+RegHandle]; this
0x18000258a  call    ?WriteEvent@DfdCollector@@AEAAXPEBU_EVENT_DESCRIPTOR@@@Z; DfdCollector::WriteEvent(_EVENT_DESCRIPTOR const *)
0x18000258f  mov     edx, 2
0x180002594  lea     rcx, aMicrosoftWindo_1; "Microsoft-Windows-DiskDiagnosticDataCol"...
0x18000259b  call    ?SetDFDTask@@YAJPEBGW4DFD_JOB_ACTION@@@Z; SetDFDTask(ushort const *,DFD_JOB_ACTION)
0x1800025a0  movzx   ebx, ax
0x1800025a3  jmp     short loc_1800025BA
0x1800025a5  test    edi, edi
0x1800025a7  jnz     short loc_1800025BA
0x1800025a9  lea     rdx, DFD_TASK_ETW_EVENT_DEFERRED; struct _EVENT_DESCRIPTOR *
0x1800025b0  lea     rcx, [rbp+57h+RegHandle]; this
0x1800025b4  call    ?WriteEvent@DfdCollector@@AEAAXPEBU_EVENT_DESCRIPTOR@@@Z; DfdCollector::WriteEvent(_EVENT_DESCRIPTOR const *)
0x1800025b9  nop
0x1800025ba  lea     rcx, [rbp+57h+RegHandle]; this
0x1800025be  call    ??1DfdCollector@@QEAA@XZ; DfdCollector::~DfdCollector(void)
0x1800025c3  mov     eax, ebx
0x1800025c5  mov     rcx, [rbp+57h+var_8]
0x1800025c9  xor     rcx, rsp; StackCookie
0x1800025cc  call    __security_check_cookie
0x1800025d1  lea     r11, [rsp+90h+var_s0]
0x1800025d9  mov     rbx, [r11+10h]
0x1800025dd  mov     rdi, [r11+18h]
0x1800025e1  mov     rsp, r11
0x1800025e4  pop     rbp
0x1800025e5  retn
```
