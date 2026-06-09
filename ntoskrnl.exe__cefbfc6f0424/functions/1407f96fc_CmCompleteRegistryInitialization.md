# CmCompleteRegistryInitialization

- ea: `0x1407f96fc`
- end: `0x1407f98c5`
- name: `CmCompleteRegistryInitialization`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1407fa180`

## callees

- `0x140213b40`
- `0x1403111a0`
- `0x140311208`
- `0x1403729e0`
- `0x140433b50`
- `0x1404a5ee0`
- `0x140541bf0`
- `0x1406dd5c0`
- `0x14075a5e0`
- `0x1407609ac`
- `0x14078a2e4`
- `0x14078a79c`
- `0x1407af3d4`
- `0x1407d7b40`
- `0x1407e3a00`
- `0x1407e5118`
- `0x1407f7af4`
- `0x1407f96fc`
- `0x1407feb80`
- `0x140800f90`
- `0x1408994e0`
- `0x140aaf8c0`
- `0x140afb310`
- `0x140bfa950`

## import_xrefs

- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmCompleteInitMachineConfig` at `0x1407f974f`
- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmCompleteInitMachineConfig` at `0x1407f974f`

## pseudocode

```c
__int64 __fastcall CmCompleteRegistryInitialization(__int16 a1)
{
  bool v2; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  bool v7; // bl
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF

  memset(&Event, 0, sizeof(Event));
  Handle = 0;
  v2 = a1 == 1;
  if ( !_InterlockedExchange(&CmFirstTime, 0) )
    return 3221225506LL;
  EtwInitialize(3);
  CmCompleteInitMachineConfig(&IopAutoReboot);
  if ( !CmNtSkipRegistryInit )
    CmpInitializeSystemHivesLoad();
  CmpLockRegistryExclusive(v4);
  LOBYTE(v5) = v2;
  CmpCmdInit(v5);
  CmpUnlockRegistry(v6);
  if ( a1 != 1 && !CmNtSkipRegistryInit )
  {
    CmpLoadingSystemHivesActive = 1;
    v7 = CmpInitRmLogOnLoad || CmpForceSynchronousMachineHiveLoad;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v9 = CmpCreateRegistryThread(&Handle, v8, CmpFinishSystemHivesLoad, (unsigned __int64)&Event & -(__int64)v7);
    if ( v9 < 0 )
      KeBugCheckEx(0x74u, 2u, 3u, 3u, v9);
    if ( v7 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    ZwClose(Handle);
    Handle = 0;
  }
  if ( !CmFastBoot )
  {
    ExpRefreshSystemTime();
    PsBootPhaseComplete(v11, v10, v12);
  }
  RtlLockBootStatusData(0);
  PnpBootPhaseComplete();
  PoInitHiberServices();
  PoClearTransitionMarker();
  PopAcquireRwLockExclusive(&PopThermalStateTransitionContext);
  byte_140EF9A74 = 1;
  PopReleaseRwLock((ULONG_PTR)&PopThermalStateTransitionContext);
  PopQueueWorkItem(PopThermalStateTransitionWorkItem, 1);
  PopCancelIgnoreBatteryStatusChange();
  *(_QWORD *)(*(_QWORD *)(PsGetCurrentServerSiloGlobals(v14, v13, v15, v16) + 1032) + 8LL) = 1;
  ExNotifyPlatformBinaryExecuted();
  byte_140E4DE08 = 1;
  if ( a1 != 1 )
    IopCopyBootLogRegistryToFile();
  return 0;
}

```

## disassembly

```asm
0x1407f96fc  mov     r11, rsp
0x1407f96ff  mov     [r11+8], rbx
0x1407f9703  mov     [r11+18h], rbp
0x1407f9707  push    rdi
0x1407f9708  sub     rsp, 50h
0x1407f970c  xor     eax, eax
0x1407f970e  xorps   xmm0, xmm0
0x1407f9711  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1407f9716  mov     [r11-18h], rax
0x1407f971a  movzx   edi, cx
0x1407f971d  mov     [r11+10h], rax
0x1407f9721  lea     ebp, [rax+1]
0x1407f9724  xchg    eax, cs:CmFirstTime
0x1407f972a  cmp     cx, bp
0x1407f972d  setz    bl
0x1407f9730  test    eax, eax
0x1407f9732  jnz     short loc_1407F973E
0x1407f9734  mov     eax, 0C0000022h
0x1407f9739  jmp     loc_1407F98B4
0x1407f973e  xor     edx, edx
0x1407f9740  lea     ecx, [rdx+3]
0x1407f9743  call    EtwInitialize
0x1407f9748  lea     rcx, IopAutoReboot
0x1407f974f  call    cs:__imp_CmCompleteInitMachineConfig
0x1407f9756  nop     dword ptr [rax+rax+00h]
0x1407f975b  cmp     cs:CmNtSkipRegistryInit, 0
0x1407f9762  jnz     short loc_1407F9769
0x1407f9764  call    CmpInitializeSystemHivesLoad
0x1407f9769  call    CmpLockRegistryExclusive
0x1407f976e  mov     cl, bl
0x1407f9770  call    CmpCmdInit
0x1407f9775  call    CmpUnlockRegistry
0x1407f977a  cmp     di, bp
0x1407f977d  jz      loc_1407F9831
0x1407f9783  cmp     cs:CmNtSkipRegistryInit, 0
0x1407f978a  jnz     loc_1407F9831
0x1407f9790  cmp     cs:CmpInitRmLogOnLoad, 0
0x1407f9797  mov     cs:CmpLoadingSystemHivesActive, bpl
0x1407f979e  jnz     short loc_1407F97AD
0x1407f97a0  cmp     cs:CmpForceSynchronousMachineHiveLoad, 0
0x1407f97a7  jnz     short loc_1407F97AD
0x1407f97a9  xor     bl, bl
0x1407f97ab  jmp     short loc_1407F97B0
0x1407f97ad  mov     bl, bpl
0x1407f97b0  xor     r8d, r8d; State
0x1407f97b3  lea     rcx, [rsp+58h+Event]; Event
0x1407f97b8  xor     edx, edx; Type
0x1407f97ba  call    KeInitializeEvent
0x1407f97bf  mov     al, bl
0x1407f97c1  lea     r8, CmpFinishSystemHivesLoad
0x1407f97c8  neg     al
0x1407f97ca  lea     rcx, [rsp+58h+Handle]
0x1407f97cf  lea     rax, [rsp+58h+Event]
0x1407f97d4  sbb     r9, r9
0x1407f97d7  and     r9, rax
0x1407f97da  call    CmpCreateRegistryThread
0x1407f97df  test    eax, eax
0x1407f97e1  jns     short loc_1407F97FF
0x1407f97e3  mov     edx, 2; BugCheckParameter1
0x1407f97e8  cdqe
0x1407f97ea  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1407f97ef  lea     r9d, [rdx+1]; BugCheckParameter3
0x1407f97f3  mov     r8d, r9d; BugCheckParameter2
0x1407f97f6  lea     ecx, [rdx+72h]; BugCheckCode
0x1407f97f9  call    KeBugCheckEx
0x1407f97ff  test    bl, bl
0x1407f9801  jz      short loc_1407F981E
0x1407f9803  xor     r9d, r9d; Alertable
0x1407f9806  mov     [rsp+58h+BugCheckParameter4], 0; Timeout
0x1407f980f  xor     r8d, r8d; WaitMode
0x1407f9812  lea     rcx, [rsp+58h+Event]; Object
0x1407f9817  xor     edx, edx; WaitReason
0x1407f9819  call    KeWaitForSingleObject
0x1407f981e  mov     rcx, [rsp+58h+Handle]; Handle
0x1407f9823  call    ZwClose
0x1407f9828  mov     [rsp+58h+Handle], 0
0x1407f9831  cmp     cs:CmFastBoot, 0
0x1407f9838  jnz     short loc_1407F9844
0x1407f983a  call    ExpRefreshSystemTime
0x1407f983f  call    PsBootPhaseComplete
0x1407f9844  xor     ecx, ecx
0x1407f9846  call    RtlLockBootStatusData
0x1407f984b  call    PnpBootPhaseComplete
0x1407f9850  call    PoInitHiberServices
0x1407f9855  call    PoClearTransitionMarker
0x1407f985a  lea     rcx, PopThermalStateTransitionContext
0x1407f9861  call    PopAcquireRwLockExclusive
0x1407f9866  lea     rcx, PopThermalStateTransitionContext; BugCheckParameter2
0x1407f986d  mov     cs:byte_140EF9A74, bpl
0x1407f9874  call    PopReleaseRwLock
0x1407f9879  mov     edx, ebp
0x1407f987b  lea     rcx, PopThermalStateTransitionWorkItem
0x1407f9882  call    PopQueueWorkItem
0x1407f9887  call    PopCancelIgnoreBatteryStatusChange
0x1407f988c  call    PsGetCurrentServerSiloGlobals
0x1407f9891  mov     rcx, [rax+408h]
0x1407f9898  mov     [rcx+8], rbp
0x1407f989c  call    ExNotifyPlatformBinaryExecuted
0x1407f98a1  mov     cs:byte_140E4DE08, bpl
0x1407f98a8  cmp     di, bp
0x1407f98ab  jz      short loc_1407F98B2
0x1407f98ad  call    IopCopyBootLogRegistryToFile
0x1407f98b2  xor     eax, eax
0x1407f98b4  mov     rbx, [rsp+58h+arg_0]
0x1407f98b9  mov     rbp, [rsp+58h+arg_10]
0x1407f98be  add     rsp, 50h
0x1407f98c2  pop     rdi
0x1407f98c3  retn
```
