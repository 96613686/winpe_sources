# PsmpInitialize

- ea: `0x18001f1b0`
- end: `0x18001f564`
- name: `PsmpInitialize`
- size: `948`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001cd80`

## callees

- `0x1800137a4`
- `0x180014e68`
- `0x180017360`
- `0x180017ce4`
- `0x1800192fc`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001c1f8`
- `0x18001c5a8`
- `0x18001ca2c`
- `0x18001f038`
- `0x18001f1b0`
- `0x18001f7a8`
- `0x180020228`
- `0x1800220b4`
- `0x180025078`

## import_xrefs

- `ntdll!TpAllocWork` at `0x18001f3e8`
- `ntdll!TpAllocWork` at `0x18001f3e8`
- `ntdll!NtQuerySystemInformation` at `0x18001f294`
- `ntdll!NtQuerySystemInformation` at `0x18001f294`
- `ntdll!RtlInitializeSRWLock` at `0x18001f27e`
- `ntdll!RtlInitializeSRWLock` at `0x18001f27e`
- `ext-ms-win-core-psm-service-l1-1-3!PsmInitializeServiceExtension4` at `0x18001f477`
- `ext-ms-win-core-psm-service-l1-1-3!PsmInitializeServiceExtension4` at `0x18001f477`
- `ext-ms-win-core-psm-service-l1-1-5!PsmCrmStart` at `0x18001f428`
- `ext-ms-win-core-psm-service-l1-1-5!PsmCrmStart` at `0x18001f428`
- `ext-ms-win-core-psm-extendedresourcemode-l1-1-0!PsmErmExtInitialize` at `0x18001f531`
- `ext-ms-win-core-psm-extendedresourcemode-l1-1-0!PsmErmExtInitialize` at `0x18001f531`
- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtNotifyRmInitializationComplete` at `0x18001f490`
- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtNotifyRmInitializationComplete` at `0x18001f490`
- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtServerInitialize` at `0x18001f3b8`
- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtServerInitialize` at `0x18001f3b8`
- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtServerStart` at `0x18001f453`
- `ext-ms-win-core-psm-bi-l1-2-0!PsmBiExtServerStart` at `0x18001f453`

## pseudocode

```c
__int64 __fastcall PsmpInitialize(int a1)
{
  int v2; // edi
  int PolicyState; // ebx
  __int64 v4; // r8
  int v5; // r8d
  __int64 v6; // r9
  signed int v7; // eax
  char SystemInformation[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[20]; // [rsp+40h] [rbp-C0h] BYREF
  char v13[32]; // [rsp+E0h] [rbp-20h] BYREF
  int *v14; // [rsp+100h] [rbp+0h]
  __int64 v15; // [rsp+108h] [rbp+8h]
  int *v16; // [rsp+110h] [rbp+10h]
  __int64 v17; // [rsp+118h] [rbp+18h]

  memset_0(v12, 0, 0x98u);
  SystemInformation[0] = 0;
  PsmpInitProgress = a1;
  McGenEventRegister_EventRegister();
  qword_18003FEB0 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_PsmTrace;
  WPP_MAIN_CB = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  qword_18003FEB8 = 1;
  WppInitUm();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18003F048);
  PsmpRegisteredTlgProv = (int)TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18003F080) >= 0;
  PsmpInitializePolicy();
  SleepState = 0;
  qword_18003FB50 = 0;
  RtlInitializeSRWLock(&SleepState);
  if ( NtQuerySystemInformation(SystemMirrorMemoryInformation|0x80, SystemInformation, 1u, 0) >= 0 )
  {
    PsmpE3Enabled = SystemInformation[0];
    if ( SystemInformation[0] )
      _InterlockedCompareExchange16(&PsmpQueryUsageInfoEnabled, 1, 0);
  }
  PsmpInitializeHashTable(&PsmpUsageTable);
  v2 = a1 & 1;
  if ( !v2 )
  {
    v12[0] = PsmCompleteActivation;
    v12[1] = PsmDereferenceBrokeredExecution;
    v12[2] = PsmDereferenceWorkItemPause;
    v12[3] = PsmGetPackageDebugMode;
    v12[4] = PsmIsApplicationForeground;
    v12[5] = PsmQueryAppResourceUsage;
    v12[6] = PsmReferenceBrokeredExecution;
    v12[7] = PsmReferenceWorkItemPause;
    v12[8] = PsmResumeApplicationSandbox;
    v12[9] = PsmSuppressApplicationSandbox;
    v12[10] = PsmTerminateApplication;
    v12[11] = PsmTerminateApplicationHost;
    v12[12] = PsmTerminatePackage;
    v12[13] = PsmUpdateApplicationType;
    v12[14] = PsmpResourceAwareTimerCreate;
    v12[15] = PsmpResourceAwareTimerDelete;
    v12[16] = PsmpResourceAwareTimerSet;
    v12[17] = PsmpResourceAwareTimerReset;
    v12[18] = PsmpResourceAwareTimerRemainingTimeGetEx;
    byte_18003FED4 = IsPsmBiExtServerStartPresent();
    if ( byte_18003FED4 )
      PsmBiExtServerInitialize(v12);
  }
  PolicyState = PsmpAllocatePolicyState();
  if ( PolicyState < 0 )
  {
    v4 = 16;
LABEL_26:
    if ( (unsigned int)dword_18003F080 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003F080, 0x400000000003LL, v4) )
    {
      v15 = v6;
      v14 = &v10;
      v11 = v5;
      v16 = &v11;
      v17 = v6;
      v10 = PolicyState;
      tlgWriteTransfer_EventWriteTransfer(&dword_18003F080, qword_1800384A0, 0, 0, v6, v13);
    }
    return (unsigned int)PolicyState;
  }
  PolicyState = TpAllocWork(&PsmpFreeAppListWorker, PsmpFreeApplicationWorker, 0, 0);
  if ( PolicyState < 0 )
  {
    v4 = 32;
    goto LABEL_26;
  }
  PolicyState = PsmpStartPolicy();
  if ( PolicyState < 0 )
  {
    v4 = 48;
    goto LABEL_26;
  }
  PolicyState = PsmpStartServer();
  if ( PolicyState < 0 )
  {
    v4 = 64;
    goto LABEL_26;
  }
  PolicyState = PsmCrmStart();
  if ( PolicyState < 0 )
  {
    v4 = 80;
    goto LABEL_26;
  }
  if ( !v2 )
  {
    byte_18003FED5 = IsPsmBiExtServerStartPresent();
    if ( byte_18003FED5 )
    {
      PolicyState = PsmBiExtServerStart();
      if ( PolicyState < 0 )
      {
        v4 = 24576;
        goto LABEL_26;
      }
    }
    if ( (unsigned __int8)IsPsmInitializeServiceExtension4Present() )
      PsmInitializeServiceExtension4(&PsmRmExtFunctionTable);
    byte_18003FED6 = IsPsmBiExtServerStartPresent();
    if ( byte_18003FED6 )
    {
      PolicyState = PsmBiExtNotifyRmInitializationComplete();
      if ( PolicyState < 0 )
      {
        v4 = 0x8000;
        goto LABEL_26;
      }
    }
  }
  if ( (unsigned __int8)IsPsmErmExtInitializePresent() )
  {
    v7 = PsmErmExtInitialize(PsmpExtendedResourceModeChanged);
    if ( v7 < 0 )
      __fastfail(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f1b0  mov     [rsp-8+arg_0], rbx
0x18001f1b5  mov     [rsp-8+arg_8], rdi
0x18001f1ba  push    rbp
0x18001f1bb  lea     rbp, [rsp-30h]
0x18001f1c0  sub     rsp, 130h
0x18001f1c7  mov     rax, cs:__security_cookie
0x18001f1ce  xor     rax, rsp
0x18001f1d1  mov     [rbp+30h+var_10], rax
0x18001f1d5  mov     edi, ecx
0x18001f1d7  xor     edx, edx; Val
0x18001f1d9  lea     rcx, [rsp+130h+var_F0]; void *
0x18001f1de  mov     r8d, 98h; Size
0x18001f1e4  call    memset_0
0x18001f1e9  mov     [rsp+130h+SystemInformation], 0
0x18001f1ee  mov     cs:PsmpInitProgress, edi
0x18001f1f4  call    McGenEventRegister_EventRegister
0x18001f1f9  lea     rax, WPP_ThisDir_CTLGUID_PsmTrace
0x18001f200  mov     cs:qword_18003FEB0, 0
0x18001f20b  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001f212  mov     ebx, 1
0x18001f217  lea     rax, WPP_MAIN_CB
0x18001f21e  mov     cs:WPP_MAIN_CB, 0
0x18001f229  mov     cs:WPP_GLOBAL_Control, rax
0x18001f230  mov     cs:qword_18003FEB8, rbx
0x18001f237  call    WppInitUm
0x18001f23c  lea     rcx, dword_18003F048; CallbackContext
0x18001f243  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001f248  lea     rcx, dword_18003F080; CallbackContext
0x18001f24f  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001f254  shr     eax, 1Fh
0x18001f257  xor     al, bl
0x18001f259  mov     cs:PsmpRegisteredTlgProv, al
0x18001f25f  call    PsmpInitializePolicy
0x18001f264  xorps   xmm0, xmm0
0x18001f267  lea     rcx, SleepState
0x18001f26e  xor     eax, eax
0x18001f270  movups  cs:SleepState, xmm0
0x18001f277  mov     cs:qword_18003FB50, rax
0x18001f27e  call    cs:__imp_RtlInitializeSRWLock
0x18001f284  xor     r9d, r9d; ReturnLength
0x18001f287  lea     rdx, [rsp+130h+SystemInformation]; SystemInformation
0x18001f28c  mov     r8d, ebx; SystemInformationLength
0x18001f28f  mov     ecx, 9Eh; SystemInformationClass
0x18001f294  call    cs:__imp_NtQuerySystemInformation
0x18001f29a  test    eax, eax
0x18001f29c  js      short loc_18001F2B7
0x18001f29e  mov     al, [rsp+130h+SystemInformation]
0x18001f2a2  mov     cs:PsmpE3Enabled, al
0x18001f2a8  test    al, al
0x18001f2aa  jz      short loc_18001F2B7
0x18001f2ac  xor     eax, eax
0x18001f2ae  lock cmpxchg cs:PsmpQueryUsageInfoEnabled, bx
0x18001f2b7  lea     rcx, PsmpUsageTable
0x18001f2be  call    PsmpInitializeHashTable
0x18001f2c3  and     edi, ebx
0x18001f2c5  jnz     loc_18001F3BE
0x18001f2cb  lea     rax, PsmCompleteActivation
0x18001f2d2  mov     [rsp+130h+var_F0], rax
0x18001f2d7  lea     rax, PsmDereferenceBrokeredExecution
0x18001f2de  mov     [rsp+130h+var_E8], rax
0x18001f2e3  lea     rax, PsmDereferenceWorkItemPause
0x18001f2ea  mov     [rsp+130h+var_E0], rax
0x18001f2ef  lea     rax, PsmGetPackageDebugMode
0x18001f2f6  mov     [rsp+130h+var_D8], rax
0x18001f2fb  lea     rax, PsmIsApplicationForeground
0x18001f302  mov     [rsp+130h+var_D0], rax
0x18001f307  lea     rax, PsmQueryAppResourceUsage
0x18001f30e  mov     [rsp+130h+var_C8], rax
0x18001f313  lea     rax, PsmReferenceBrokeredExecution
0x18001f31a  mov     [rsp+130h+var_C0], rax
0x18001f31f  lea     rax, PsmReferenceWorkItemPause
0x18001f326  mov     [rsp+130h+var_B8], rax
0x18001f32b  lea     rax, PsmResumeApplicationSandbox
0x18001f332  mov     [rbp+30h+var_B0], rax
0x18001f336  lea     rax, PsmSuppressApplicationSandbox
0x18001f33d  mov     [rbp+30h+var_A8], rax
0x18001f341  lea     rax, PsmTerminateApplication
0x18001f348  mov     [rbp+30h+var_A0], rax
0x18001f34c  lea     rax, PsmTerminateApplicationHost
0x18001f353  mov     [rbp+30h+var_98], rax
0x18001f357  lea     rax, PsmTerminatePackage
0x18001f35e  mov     [rbp+30h+var_90], rax
0x18001f362  lea     rax, PsmUpdateApplicationType
0x18001f369  mov     [rbp+30h+var_88], rax
0x18001f36d  lea     rax, PsmpResourceAwareTimerCreate
0x18001f374  mov     [rbp+30h+var_80], rax
0x18001f378  lea     rax, PsmpResourceAwareTimerDelete
0x18001f37f  mov     [rbp+30h+var_78], rax
0x18001f383  lea     rax, PsmpResourceAwareTimerSet
0x18001f38a  mov     [rbp+30h+var_70], rax
0x18001f38e  lea     rax, PsmpResourceAwareTimerReset
0x18001f395  mov     [rbp+30h+var_68], rax
0x18001f399  lea     rax, PsmpResourceAwareTimerRemainingTimeGetEx
0x18001f3a0  mov     [rbp+30h+var_60], rax
0x18001f3a4  call    IsPsmBiExtServerStartPresent
0x18001f3a9  mov     cs:byte_18003FED4, al
0x18001f3af  test    al, al
0x18001f3b1  jz      short loc_18001F3BE
0x18001f3b3  lea     rcx, [rsp+130h+var_F0]
0x18001f3b8  call    cs:__imp_PsmBiExtServerInitialize
0x18001f3be  call    PsmpAllocatePolicyState
0x18001f3c3  mov     ebx, eax
0x18001f3c5  test    eax, eax
0x18001f3c7  jns     short loc_18001F3D4
0x18001f3c9  mov     r8d, 10h
0x18001f3cf  jmp     loc_18001F4A6
0x18001f3d4  xor     r9d, r9d
0x18001f3d7  lea     rdx, PsmpFreeApplicationWorker
0x18001f3de  xor     r8d, r8d
0x18001f3e1  lea     rcx, PsmpFreeAppListWorker
0x18001f3e8  call    cs:__imp_TpAllocWork
0x18001f3ee  mov     ebx, eax
0x18001f3f0  test    eax, eax
0x18001f3f2  jns     short loc_18001F3FF
0x18001f3f4  mov     r8d, 20h ; ' '
0x18001f3fa  jmp     loc_18001F4A6
0x18001f3ff  call    PsmpStartPolicy
0x18001f404  mov     ebx, eax
0x18001f406  test    eax, eax
0x18001f408  jns     short loc_18001F415
0x18001f40a  mov     r8d, 30h ; '0'
0x18001f410  jmp     loc_18001F4A6
0x18001f415  call    PsmpStartServer
0x18001f41a  mov     ebx, eax
0x18001f41c  test    eax, eax
0x18001f41e  jns     short loc_18001F428
0x18001f420  mov     r8d, 40h ; '@'
0x18001f426  jmp     short loc_18001F4A6
0x18001f428  call    cs:__imp_PsmCrmStart
0x18001f42e  mov     ebx, eax
0x18001f430  test    eax, eax
0x18001f432  jns     short loc_18001F43C
0x18001f434  mov     r8d, 50h ; 'P'
0x18001f43a  jmp     short loc_18001F4A6
0x18001f43c  test    edi, edi
0x18001f43e  jnz     loc_18001F521
0x18001f444  call    IsPsmBiExtServerStartPresent
0x18001f449  mov     cs:byte_18003FED5, al
0x18001f44f  test    al, al
0x18001f451  jz      short loc_18001F467
0x18001f453  call    cs:__imp_PsmBiExtServerStart
0x18001f459  mov     ebx, eax
0x18001f45b  test    eax, eax
0x18001f45d  jns     short loc_18001F467
0x18001f45f  mov     r8d, 6000h
0x18001f465  jmp     short loc_18001F4A6
0x18001f467  call    IsPsmInitializeServiceExtension4Present
0x18001f46c  test    al, al
0x18001f46e  jz      short loc_18001F47D
0x18001f470  lea     rcx, PsmRmExtFunctionTable
0x18001f477  call    cs:__imp_PsmInitializeServiceExtension4
0x18001f47d  call    IsPsmBiExtServerStartPresent
0x18001f482  mov     cs:byte_18003FED6, al
0x18001f488  test    al, al
0x18001f48a  jz      loc_18001F521
0x18001f490  call    cs:__imp_PsmBiExtNotifyRmInitializationComplete
0x18001f496  mov     ebx, eax
0x18001f498  test    eax, eax
0x18001f49a  jns     loc_18001F521
0x18001f4a0  mov     r8d, 8000h
0x18001f4a6  mov     eax, cs:dword_18003F080
0x18001f4ac  mov     r9d, 4
0x18001f4b2  cmp     eax, r9d
0x18001f4b5  jbe     loc_18001F541
0x18001f4bb  mov     rdx, 400000000003h
0x18001f4c5  lea     rcx, dword_18003F080
0x18001f4cc  call    _tlgKeywordOn
0x18001f4d1  test    al, al
0x18001f4d3  jz      short loc_18001F541
0x18001f4d5  lea     rax, [rsp+130h+var_FC]
0x18001f4da  mov     [rbp+30h+var_28], r9
0x18001f4de  mov     [rbp+30h+var_30], rax
0x18001f4e2  lea     rdx, qword_1800384A0
0x18001f4e9  lea     rax, [rsp+130h+var_F8]
0x18001f4ee  mov     [rsp+130h+var_F8], r8d
0x18001f4f3  mov     [rbp+30h+var_20], rax
0x18001f4f7  lea     rcx, dword_18003F080
0x18001f4fe  lea     rax, [rbp+30h+var_50]
0x18001f502  mov     [rbp+30h+var_18], r9
0x18001f506  mov     [rsp+130h+var_108], rax
0x18001f50b  xor     r8d, r8d
0x18001f50e  mov     [rsp+130h+var_110], r9d
0x18001f513  xor     r9d, r9d
0x18001f516  mov     [rsp+130h+var_FC], ebx
0x18001f51a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001f51f  jmp     short loc_18001F541
0x18001f521  call    IsPsmErmExtInitializePresent
0x18001f526  test    al, al
0x18001f528  jz      short loc_18001F53F
0x18001f52a  lea     rcx, PsmpExtendedResourceModeChanged
0x18001f531  call    cs:__imp_PsmErmExtInitialize
0x18001f537  test    eax, eax
0x18001f539  jns     short loc_18001F53F
0x18001f53b  mov     ecx, eax
0x18001f53d  int     29h; Win8: RtlFailFast(ecx)
0x18001f53f  xor     ebx, ebx
0x18001f541  mov     eax, ebx
0x18001f543  mov     rcx, [rbp+30h+var_10]
0x18001f547  xor     rcx, rsp; StackCookie
0x18001f54a  call    __security_check_cookie
0x18001f54f  lea     r11, [rsp+130h+var_s0]
0x18001f557  mov     rbx, [r11+10h]
0x18001f55b  mov     rdi, [r11+18h]
0x18001f55f  mov     rsp, r11
0x18001f562  pop     rbp
0x18001f563  retn
```
