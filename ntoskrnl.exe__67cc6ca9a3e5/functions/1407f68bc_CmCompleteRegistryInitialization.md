# CmCompleteRegistryInitialization

- ea: `0x1407f68bc`
- end: `0x1407f6a85`
- name: `CmCompleteRegistryInitialization`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1407f7380`

## callees

- `0x140223fb0`
- `0x14025ffd0`
- `0x140309b40`
- `0x14041b950`
- `0x14044fd64`
- `0x140498150`
- `0x14053a530`
- `0x1406daa70`
- `0x140756160`
- `0x14075c53c`
- `0x140785e84`
- `0x14078637c`
- `0x1407abe84`
- `0x1407d4e80`
- `0x1407e0d40`
- `0x1407e2458`
- `0x1407f4cb4`
- `0x1407f68bc`
- `0x1407fbd80`
- `0x1407fe1e8`
- `0x14093f0e0`
- `0x140aa9c30`
- `0x140af49c8`
- `0x140bf7950`

## import_xrefs

- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmCompleteInitMachineConfig` at `0x1407f690f`
- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmCompleteInitMachineConfig` at `0x1407f690f`

## pseudocode

```c
__int64 __fastcall CmCompleteRegistryInitialization(__int16 a1)
{
  bool v2; // bl
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // bl
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF

  memset(&Event, 0, sizeof(Event));
  Handle = 0;
  v2 = a1 == 1;
  if ( !_InterlockedExchange((_DWORD *)&ExpPlatformBinaryLock.Header.WaitListHead.Blink + 1, 0) )
    return 3221225506LL;
  EtwInitialize(3);
  CmCompleteInitMachineConfig(&IopAutoReboot);
  if ( !LODWORD(WheapPfaLock.StateSaveArea) )
    CmpInitializeSystemHivesLoad();
  CmpLockRegistryExclusive(v5, v4, v6, v7);
  LOBYTE(v8) = v2;
  CmpCmdInit(v8);
  CmpUnlockRegistry(v9);
  if ( a1 != 1 && !LODWORD(WheapPfaLock.StateSaveArea) )
  {
    LOBYTE(WheapPfaLock.StackBase) = 1;
    v10 = LOBYTE(WheapPfaLock.CycleTime) || CmpForceSynchronousMachineHiveLoad;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v12 = CmpCreateRegistryThread(&Handle, v11, CmpFinishSystemHivesLoad, (unsigned __int64)&Event & -(__int64)v10);
    if ( v12 < 0 )
      KeBugCheckEx(0x74u, 2u, 3u, 3u, v12);
    if ( v10 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    ZwClose(Handle);
    Handle = 0;
  }
  if ( !CmFastBoot )
  {
    ExpRefreshSystemTime();
    PsBootPhaseComplete(v14, v13, v15);
  }
  RtlLockBootStatusData(0);
  PnpBootPhaseComplete();
  PoInitHiberServices();
  PoClearTransitionMarker();
  PopAcquireRwLockExclusive(&PopBlackBoxLock.Timer.Header.WaitListHead.Blink, v16, v17);
  BYTE4(PopBlackBoxLock.Timer.TimerListEntry.Flink) = 1;
  PopReleaseRwLock((struct _KTHREAD *)&PopBlackBoxLock.Timer.Header.WaitListHead.Blink);
  PopQueueWorkItem(&PopBlackBoxLock.WaitBlockList, 1);
  PopCancelIgnoreBatteryStatusChange();
  *(_QWORD *)(*(_QWORD *)(PsGetCurrentServerSiloGlobals(v19, v18) + 1032) + 8LL) = 1;
  ExNotifyPlatformBinaryExecuted();
  RtlpBootStatHandleLock.ApcStateFill[8] = 1;
  if ( a1 != 1 )
    IopCopyBootLogRegistryToFile();
  return 0;
}

```

## disassembly

```asm
0x1407f68bc  mov     r11, rsp
0x1407f68bf  mov     [r11+8], rbx
0x1407f68c3  mov     [r11+18h], rbp
0x1407f68c7  push    rdi
0x1407f68c8  sub     rsp, 50h
0x1407f68cc  xor     eax, eax
0x1407f68ce  xorps   xmm0, xmm0
0x1407f68d1  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1407f68d6  mov     [r11-18h], rax
0x1407f68da  movzx   edi, cx
0x1407f68dd  mov     [r11+10h], rax
0x1407f68e1  lea     ebp, [rax+1]
0x1407f68e4  xchg    eax, dword ptr cs:ExpPlatformBinaryLock.Header.WaitListHead.Blink+4
0x1407f68ea  cmp     cx, bp
0x1407f68ed  setz    bl
0x1407f68f0  test    eax, eax
0x1407f68f2  jnz     short loc_1407F68FE
0x1407f68f4  mov     eax, 0C0000022h
0x1407f68f9  jmp     loc_1407F6A74
0x1407f68fe  xor     edx, edx
0x1407f6900  lea     ecx, [rdx+3]
0x1407f6903  call    EtwInitialize
0x1407f6908  lea     rcx, IopAutoReboot
0x1407f690f  call    cs:__imp_CmCompleteInitMachineConfig
0x1407f6916  nop     dword ptr [rax+rax+00h]
0x1407f691b  cmp     dword ptr cs:WheapPfaLock.StateSaveArea, 0
0x1407f6922  jnz     short loc_1407F6929
0x1407f6924  call    CmpInitializeSystemHivesLoad
0x1407f6929  call    CmpLockRegistryExclusive
0x1407f692e  mov     cl, bl
0x1407f6930  call    CmpCmdInit
0x1407f6935  call    CmpUnlockRegistry
0x1407f693a  cmp     di, bp
0x1407f693d  jz      loc_1407F69F1
0x1407f6943  cmp     dword ptr cs:WheapPfaLock.StateSaveArea, 0
0x1407f694a  jnz     loc_1407F69F1
0x1407f6950  cmp     byte ptr cs:WheapPfaLock.CycleTime, 0
0x1407f6957  mov     byte ptr cs:WheapPfaLock.StackBase, bpl
0x1407f695e  jnz     short loc_1407F696D
0x1407f6960  cmp     cs:CmpForceSynchronousMachineHiveLoad, 0
0x1407f6967  jnz     short loc_1407F696D
0x1407f6969  xor     bl, bl
0x1407f696b  jmp     short loc_1407F6970
0x1407f696d  mov     bl, bpl
0x1407f6970  xor     r8d, r8d; State
0x1407f6973  lea     rcx, [rsp+58h+Event]; Event
0x1407f6978  xor     edx, edx; Type
0x1407f697a  call    KeInitializeEvent
0x1407f697f  mov     al, bl
0x1407f6981  lea     r8, CmpFinishSystemHivesLoad
0x1407f6988  neg     al
0x1407f698a  lea     rcx, [rsp+58h+Handle]
0x1407f698f  lea     rax, [rsp+58h+Event]
0x1407f6994  sbb     r9, r9
0x1407f6997  and     r9, rax
0x1407f699a  call    CmpCreateRegistryThread
0x1407f699f  test    eax, eax
0x1407f69a1  jns     short loc_1407F69BF
0x1407f69a3  mov     edx, 2; BugCheckParameter1
0x1407f69a8  cdqe
0x1407f69aa  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1407f69af  lea     r9d, [rdx+1]; BugCheckParameter3
0x1407f69b3  mov     r8d, r9d; BugCheckParameter2
0x1407f69b6  lea     ecx, [rdx+72h]; BugCheckCode
0x1407f69b9  call    KeBugCheckEx
0x1407f69bf  test    bl, bl
0x1407f69c1  jz      short loc_1407F69DE
0x1407f69c3  xor     r9d, r9d; Alertable
0x1407f69c6  mov     [rsp+58h+BugCheckParameter4], 0; Timeout
0x1407f69cf  xor     r8d, r8d; WaitMode
0x1407f69d2  lea     rcx, [rsp+58h+Event]; Object
0x1407f69d7  xor     edx, edx; WaitReason
0x1407f69d9  call    KeWaitForSingleObject
0x1407f69de  mov     rcx, [rsp+58h+Handle]; Handle
0x1407f69e3  call    ZwClose
0x1407f69e8  mov     [rsp+58h+Handle], 0
0x1407f69f1  cmp     cs:CmFastBoot, 0
0x1407f69f8  jnz     short loc_1407F6A04
0x1407f69fa  call    ExpRefreshSystemTime
0x1407f69ff  call    PsBootPhaseComplete
0x1407f6a04  xor     ecx, ecx
0x1407f6a06  call    RtlLockBootStatusData
0x1407f6a0b  call    PnpBootPhaseComplete
0x1407f6a10  call    PoInitHiberServices
0x1407f6a15  call    PoClearTransitionMarker
0x1407f6a1a  lea     rcx, PopBlackBoxLock.Timer.Header.WaitListHead.Blink
0x1407f6a21  call    PopAcquireRwLockExclusive
0x1407f6a26  lea     rcx, PopBlackBoxLock.Timer.Header.WaitListHead.Blink
0x1407f6a2d  mov     byte ptr cs:PopBlackBoxLock.Timer.TimerListEntry.Flink+4, bpl
0x1407f6a34  call    PopReleaseRwLock
0x1407f6a39  mov     edx, ebp
0x1407f6a3b  lea     rcx, PopBlackBoxLock.WaitBlockList
0x1407f6a42  call    PopQueueWorkItem
0x1407f6a47  call    PopCancelIgnoreBatteryStatusChange
0x1407f6a4c  call    PsGetCurrentServerSiloGlobals
0x1407f6a51  mov     rcx, [rax+408h]
0x1407f6a58  mov     [rcx+8], rbp
0x1407f6a5c  call    ExNotifyPlatformBinaryExecuted
0x1407f6a61  mov     byte ptr cs:RtlpBootStatHandleLock.___u25+8, bpl
0x1407f6a68  cmp     di, bp
0x1407f6a6b  jz      short loc_1407F6A72
0x1407f6a6d  call    IopCopyBootLogRegistryToFile
0x1407f6a72  xor     eax, eax
0x1407f6a74  mov     rbx, [rsp+58h+arg_0]
0x1407f6a79  mov     rbp, [rsp+58h+arg_10]
0x1407f6a7e  add     rsp, 50h
0x1407f6a82  pop     rdi
0x1407f6a83  retn
```
