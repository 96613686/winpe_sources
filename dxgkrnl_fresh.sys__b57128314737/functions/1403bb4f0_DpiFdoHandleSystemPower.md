# DpiFdoHandleSystemPower

- ea: `0x1403bb4f0`
- end: `0x1403bbd03`
- name: `DpiFdoHandleSystemPower`
- size: `2067`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Context)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1403bab80`

## callees

- `0x140022434`
- `0x140035f90`
- `0x140041db4`
- `0x140055744`
- `0x140062304`
- `0x1400a1000`
- `0x1402b738c`
- `0x1402bf6fc`
- `0x1402bff24`
- `0x1402bfff4`
- `0x140365dac`
- `0x140366eb0`
- `0x140367720`
- `0x140367750`
- `0x1403bb4f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bb887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bbb79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bb887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bbb79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bbbb3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bbc2e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bbbb3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bbc2e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bb8ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bbb92`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bb8ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bbb92`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bbba7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bbc22`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bbba7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bbc22`
- `ntoskrnl!KeInitializeEvent` at `0x1403bb5a0`
- `ntoskrnl!KeInitializeEvent` at `0x1403bb5a0`
- `ntoskrnl!InbvNotifyDisplayOwnershipChange` at `0x1403bbb21`
- `ntoskrnl!InbvNotifyDisplayOwnershipChange` at `0x1403bbb21`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403bb99b`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403bb99b`
- `ntoskrnl!IofCompleteRequest` at `0x1403bbc56`
- `ntoskrnl!IofCompleteRequest` at `0x1403bbc56`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bb61d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bb7eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bb859`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bb61d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bb7eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bb859`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1403bb9f1`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1403bb9f1`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1403bb58a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1403bb58a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403bbc6f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403bbc6f`
- `ntoskrnl!PoRequestPowerIrp` at `0x1403bbcc3`
- `ntoskrnl!PoRequestPowerIrp` at `0x1403bbcc3`
- `ntoskrnl!PoCallDriver` at `0x1403bb600`
- `ntoskrnl!PoCallDriver` at `0x1403bb758`
- `ntoskrnl!PoCallDriver` at `0x1403bb600`
- `ntoskrnl!PoCallDriver` at `0x1403bb758`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1403bbc42`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1403bbc42`
- `watchdog!WdLogSingleEntry1` at `0x1403bb640`
- `watchdog!WdLogSingleEntry1` at `0x1403bb71b`
- `watchdog!WdLogSingleEntry1` at `0x1403bb77e`
- `watchdog!WdLogSingleEntry1` at `0x1403bb805`
- `watchdog!WdLogSingleEntry1` at `0x1403bb829`
- `watchdog!WdLogSingleEntry1` at `0x1403bb871`
- `watchdog!WdLogSingleEntry1` at `0x1403bb9b9`
- `watchdog!WdLogSingleEntry1` at `0x1403bbce4`
- `watchdog!WdLogSingleEntry1` at `0x1403bb640`
- `watchdog!WdLogSingleEntry1` at `0x1403bb71b`
- `watchdog!WdLogSingleEntry1` at `0x1403bb77e`
- `watchdog!WdLogSingleEntry1` at `0x1403bb805`
- `watchdog!WdLogSingleEntry1` at `0x1403bb829`
- `watchdog!WdLogSingleEntry1` at `0x1403bb871`
- `watchdog!WdLogSingleEntry1` at `0x1403bb9b9`
- `watchdog!WdLogSingleEntry1` at `0x1403bbce4`

## pseudocode

```c
NTSTATUS __fastcall DpiFdoHandleSystemPower(PDEVICE_OBJECT DeviceObject, IRP *Context)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  bool v3; // al
  char *DeviceExtension; // rsi
  __int64 v7; // rdx
  struct _IO_STACK_LOCATION *v8; // rax
  struct _IO_STACK_LOCATION *v9; // rax
  NTSTATUS v10; // eax
  int v11; // r15d
  int *v12; // rbx
  int v13; // ecx
  bool v14; // dl
  char *v15; // r8
  int v16; // ebx
  int v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  unsigned int LowPart; // eax
  __int64 v22; // rdx
  POWER_STATE v23; // ebx
  ULONG EaLength; // ecx
  char v25; // al
  struct _IO_WORKITEM *WorkItem; // rcx
  __int64 v27; // rcx
  struct _IO_STACK_LOCATION *v28; // rax
  NTSTATUS v29; // eax
  char v30[8]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v31; // [rsp+40h] [rbp-28h]
  struct _KEVENT Event; // [rsp+48h] [rbp-20h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+B8h] [rbp+50h] BYREF
  char v35; // [rsp+C0h] [rbp+58h]
  ULONG v36; // [rsp+C8h] [rbp+60h]

  CurrentStackLocation = Context->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  memset(&Event, 0, sizeof(Event));
  v7 = (unsigned int)CurrentStackLocation->MinorFunction - 2;
  if ( CurrentStackLocation->MinorFunction != 2 )
  {
    if ( CurrentStackLocation->MinorFunction == 3 )
    {
      if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
      {
        Timeout.QuadPart = -300000000;
        LOBYTE(v7) = 1;
        DpiFdoStopMiracastSession(DeviceObject, v7, &Timeout, 131);
      }
LABEL_5:
      v35 = 0;
      IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Context, File, 1u, 0x20u);
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      v8 = Context->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v8[-1].MajorFunction = *(_OWORD *)&v8->MajorFunction;
      *(_OWORD *)&v8[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v8->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v8[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v8->Parameters.SetQuota + 6);
      v8[-1].FileObject = v8->FileObject;
      v8[-1].Control = 0;
      v9 = Context->Tail.Overlay.CurrentStackLocation;
      v9[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&DpiFdoPowerCompletionRoutine;
      v9[-1].Context = &Event;
      v9[-1].Control = -32;
      PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), Context);
      v10 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v11 = v10;
      v12 = (int *)&Context->IoStatus.0;
      if ( v10 )
      {
        WdLogSingleEntry1(2, v10);
        WdLogGlobalForLineNumber = 1246;
      }
      else
      {
        v11 = *v12;
        if ( *v12 < 0 )
        {
          WdLogSingleEntry1(3, CurrentStackLocation->MinorFunction);
          WdLogGlobalForLineNumber = 1274;
          goto LABEL_74;
        }
        if ( CurrentStackLocation->MinorFunction == 2
          && DeviceExtension[1158]
          && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1
          && *((_DWORD *)DeviceExtension + 71) != 1 )
        {
          Timeout.QuadPart = -150000000;
          v19 = KeWaitForSingleObject(DeviceExtension + 1240, Executive, 0, 0, &Timeout);
          if ( v19 == 258 )
          {
            WdLogSingleEntry1(2, 258);
            WdLogGlobalForLineNumber = 1311;
          }
          else if ( v19 >= 0 )
          {
            v20 = KeWaitForSingleObject(DeviceExtension + 1264, Executive, 0, 0, 0);
            if ( v20 < 0 )
            {
              WdLogSingleEntry1(2, v20);
              WdLogGlobalForLineNumber = 1337;
            }
          }
          else
          {
            WdLogSingleEntry1(2, v19);
            WdLogGlobalForLineNumber = 1318;
          }
        }
        KeEnterCriticalRegion();
        if ( DeviceExtension[484] )
          DpiCheckForOutstandingD3Requests(DeviceExtension);
        ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
        if ( CurrentStackLocation->MinorFunction == 2 )
        {
          LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
          if ( LowPart > 1 )
            *((_DWORD *)DeviceExtension + 70) = LowPart;
        }
        if ( !DeviceExtension[1158] )
        {
          v22 = (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
          v23.SystemState = *(SYSTEM_POWER_STATE *)&DeviceExtension[4 * v22 + 1336];
          if ( DeviceExtension[480] )
          {
            v11 = 0;
            if ( DeviceExtension
              && *((_DWORD *)DeviceExtension + 4) == 1953656900
              && *((_DWORD *)DeviceExtension + 5) == 2
              && *((_DWORD *)DeviceExtension + 59) == 2
              && CurrentStackLocation->MinorFunction == 2 )
            {
              EaLength = CurrentStackLocation->Parameters.Create.EaLength;
              v36 = EaLength;
              v25 = (unsigned int)(dword_140163250 - 4) <= 1;
              LOBYTE(Timeout.LowPart) = v25;
              if ( v23.SystemState == PowerSystemWorking )
              {
                v36 = DpiCorrectPowerAction(DeviceObject, v22, EaLength);
                v25 = Timeout.LowPart;
              }
              if ( DeviceExtension[1153] && v23.SystemState < *((_DWORD *)DeviceExtension + 71) )
              {
                if ( qword_140163100 )
                {
                  if ( v25 )
                  {
                    WorkItem = IoAllocateWorkItem(g_pDriverObject);
                    if ( WorkItem )
                    {
                      _InterlockedCompareExchange(&dword_140163250, 5, 4);
                      IoQueueWorkItemEx(WorkItem, DpiDisableMsBddFallbackDriverWorkItem, DelayedWorkQueue, 0);
                    }
                    else
                    {
                      WdLogSingleEntry1(6, -1073741670);
                      WdLogGlobalForLineNumber = 1440;
                    }
                  }
                }
                else if ( byte_140163270 )
                {
                  LOBYTE(v22) = 1;
                  DpiAcquirePostDisplayInfoFromBgfx(&xmmword_140163108, v22, 0);
                  if ( LOBYTE(Timeout.LowPart) )
                  {
                    byte_140163270 = 0;
                    dword_14016329C = 1;
                    xmmword_1401631B0 = xmmword_140163108;
                    xmmword_1401631C0 = xmmword_140163118;
                    xmmword_1401631D0 = xmmword_140163128;
                    xmmword_1401631E0 = xmmword_140163138;
                    xmmword_1401631F0 = xmmword_140163148;
                    xmmword_140163200 = xmmword_140163158;
                    xmmword_140163210 = xmmword_140163168;
                    xmmword_140163220 = xmmword_140163178;
                    xmmword_140163230 = xmmword_140163188;
                    xmmword_140163240 = xmmword_140163198;
                    qword_140163258 = (__int64)KeGetCurrentThread();
                    qword_140163260 = (__int64)DeviceObject;
                  }
                }
              }
              ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))DpiDxgkDdiSetPowerState)(
                *((_QWORD *)DeviceExtension + 5),
                *((_QWORD *)DeviceExtension + 6),
                -1,
                (POWER_STATE)v23.SystemState,
                v36);
              if ( DeviceExtension[1153] && LOBYTE(Timeout.LowPart) )
              {
                if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5 )
                {
                  byte_140163270 = 1;
                  LOBYTE(v27) = 1;
                  InbvNotifyDisplayOwnershipChange(v27, DpiEnterSystemDisplay);
                }
                else if ( v23.SystemState < *((_DWORD *)DeviceExtension + 71) )
                {
                  xmmword_1401631C0 = 0;
                  DWORD2(xmmword_1401631C0) = -1;
                  xmmword_1401631B0 = 0;
                  memset(&xmmword_1401631D0, 0, 0x80u);
                  qword_140163260 = 0;
                  qword_140163258 = (__int64)KeGetCurrentThread();
                }
              }
              KeEnterCriticalRegion();
              ExAcquireResourceExclusiveLite((PERESOURCE)(DeviceExtension + 3928), 1u);
              *((POWER_STATE *)DeviceExtension + 71) = v23;
              ExReleaseResourceLite((PERESOURCE)(DeviceExtension + 3928));
              KeLeaveCriticalRegion();
              if ( v23.SystemState == PowerSystemWorking )
              {
                v30[0] = 0;
                CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v30, 0, 0xBu, 0);
                DpiFdoInvalidateChildRelations(DeviceObject, 6, v31);
                CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v30);
              }
            }
            v12 = (int *)&Context->IoStatus.0;
            *((_DWORD *)DeviceExtension + 70) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
          }
          else
          {
            v28 = Context->Tail.Overlay.CurrentStackLocation;
            v35 = 1;
            v28->Control |= 1u;
            v29 = PoRequestPowerIrp(
                    DeviceObject,
                    CurrentStackLocation->MinorFunction,
                    v23,
                    DpiFdoDevicePowerCompletionCallback,
                    Context,
                    0);
            v11 = v29;
            if ( v29 != 259 )
            {
              WdLogSingleEntry1(2, v29);
              WdLogGlobalForLineNumber = 1599;
            }
            v12 = (int *)&Context->IoStatus.0;
          }
        }
        if ( DeviceExtension[484] )
          DpiEnableD3Requests(*((_QWORD *)DeviceExtension + 3));
        ExReleaseResourceLite(*((PERESOURCE *)DeviceExtension + 21));
        KeLeaveCriticalRegion();
      }
      if ( v11 == 259 )
        return v11;
LABEL_74:
      PoStartNextPowerIrp(Context);
      *v12 = v11;
      IofCompleteRequest(Context, 0);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Context, 0x20u);
      if ( v35 )
        return 259;
      return v11;
    }
LABEL_24:
    ++Context->CurrentLocation;
    ++Context->Tail.Overlay.CurrentStackLocation;
    return PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), Context);
  }
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
  {
    v15 = DeviceExtension;
    v3 = (*((_DWORD *)DeviceExtension + 1398) & 2) != 0;
    v14 = DeviceExtension[5144] != 0;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 6 || !HIBYTE(word_1401633F8) )
  {
LABEL_23:
    if ( v13 != -1073741637 )
      goto LABEL_5;
    goto LABEL_24;
  }
  if ( v14 )
  {
    if ( byte_140163410 )
    {
      if ( v3 )
      {
        Timeout.LowPart = 0;
        v18 = DpiDxgkDdiSaveMemoryForHotUpdate(v15, &Timeout);
        v13 = v18;
        if ( v18 < 0 )
        {
          WdLogSingleEntry1(2, v18);
          WdLogGlobalForLineNumber = 1174;
          goto LABEL_5;
        }
      }
    }
    goto LABEL_23;
  }
  v16 = DpiKsrStopAdapter(DeviceObject, Context, v15);
  if ( v16 == -1073741637 )
    goto LABEL_5;
  if ( (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(DeviceObject) && (unsigned int)(dword_140163250 - 1) <= 1 )
    DpiKsrSetBootGraphicsInformation();
  return v16;
}

```

## disassembly

```asm
0x1403bb4f0  mov     [rsp-40h+arg_0], rcx
0x1403bb4f5  push    rbp
0x1403bb4f6  push    rbx
0x1403bb4f7  push    rsi
0x1403bb4f8  push    rdi
0x1403bb4f9  push    r12
0x1403bb4fb  push    r13
0x1403bb4fd  push    r14
0x1403bb4ff  push    r15
0x1403bb501  mov     rbp, rsp
0x1403bb504  sub     rsp, 68h
0x1403bb508  mov     r12, [rdx+0B8h]
0x1403bb50f  xor     eax, eax
0x1403bb511  mov     rsi, [rcx+40h]
0x1403bb515  mov     r13, rdx
0x1403bb518  xorps   xmm0, xmm0
0x1403bb51b  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1403bb51f  movups  xmmword ptr [rbp+Event.Header], xmm0
0x1403bb523  movzx   edx, byte ptr [r12+1]
0x1403bb529  lea     r14d, [rax+1]
0x1403bb52d  xor     r15d, r15d
0x1403bb530  mov     rdi, rcx
0x1403bb533  sub     edx, 2
0x1403bb536  jz      loc_1403BB660
0x1403bb53c  cmp     edx, r14d
0x1403bb53f  jnz     loc_1403BB742
0x1403bb545  cmp     [r12+18h], r14d
0x1403bb54a  jz      short loc_1403BB566
0x1403bb54c  mov     r9d, 83h
0x1403bb552  mov     qword ptr [rbp+Timeout], 0FFFFFFFFEE1E5D00h
0x1403bb55a  lea     r8, [rbp+Timeout]
0x1403bb55e  mov     dl, r14b
0x1403bb561  call    DpiFdoStopMiracastSession
0x1403bb566  lea     rax, [rsi+40h]
0x1403bb56a  mov     [rbp+arg_10], r15b
0x1403bb56e  mov     rcx, rax; RemoveLock
0x1403bb571  mov     [rbp+RemoveLock], rax
0x1403bb575  mov     r9d, r14d; Line
0x1403bb578  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x1403bb580  lea     r8, File; File
0x1403bb587  mov     rdx, r13; Tag
0x1403bb58a  call    cs:__imp_IoAcquireRemoveLockEx
0x1403bb591  nop     dword ptr [rax+rax+00h]
0x1403bb596  xor     r8d, r8d; State
0x1403bb599  lea     rcx, [rbp+Event]; Event
0x1403bb59d  mov     edx, r14d; Type
0x1403bb5a0  call    cs:__imp_KeInitializeEvent
0x1403bb5a7  nop     dword ptr [rax+rax+00h]
0x1403bb5ac  mov     rax, [r13+0B8h]
0x1403bb5b3  lea     rcx, DpiFdoPowerCompletionRoutine
0x1403bb5ba  mov     rdx, r13; Irp
0x1403bb5bd  movups  xmm0, xmmword ptr [rax]
0x1403bb5c0  movups  xmmword ptr [rax-48h], xmm0
0x1403bb5c4  movups  xmm1, xmmword ptr [rax+10h]
0x1403bb5c8  movups  xmmword ptr [rax-38h], xmm1
0x1403bb5cc  movups  xmm0, xmmword ptr [rax+20h]
0x1403bb5d0  movups  xmmword ptr [rax-28h], xmm0
0x1403bb5d4  movsd   xmm1, qword ptr [rax+30h]
0x1403bb5d9  movsd   qword ptr [rax-18h], xmm1
0x1403bb5de  mov     [rax-45h], r15b
0x1403bb5e2  mov     rax, [r13+0B8h]
0x1403bb5e9  mov     [rax-10h], rcx
0x1403bb5ed  lea     rcx, [rbp+Event]
0x1403bb5f1  mov     [rax-8], rcx
0x1403bb5f5  mov     byte ptr [rax-45h], 0E0h
0x1403bb5f9  mov     rcx, [rsi+0A0h]; DeviceObject
0x1403bb600  call    cs:__imp_PoCallDriver
0x1403bb607  nop     dword ptr [rax+rax+00h]
0x1403bb60c  xor     r9d, r9d; Alertable
0x1403bb60f  mov     qword ptr [rsp+68h+RemlockSize], r15; Timeout
0x1403bb614  xor     r8d, r8d; WaitMode
0x1403bb617  lea     rcx, [rbp+Event]; Object
0x1403bb61b  xor     edx, edx; WaitReason
0x1403bb61d  call    cs:__imp_KeWaitForSingleObject
0x1403bb624  nop     dword ptr [rax+rax+00h]
0x1403bb629  movsxd  r15, eax
0x1403bb62c  lea     rbx, [r13+30h]
0x1403bb630  test    eax, eax
0x1403bb632  jz      loc_1403BB769
0x1403bb638  mov     rdx, r15
0x1403bb63b  mov     ecx, 2
0x1403bb640  call    cs:__imp_WdLogSingleEntry1
0x1403bb647  nop     dword ptr [rax+rax+00h]
0x1403bb64c  mov     cs:WdLogGlobalForLineNumber, 4DEh
0x1403bb656  mov     edi, 103h
0x1403bb65b  jmp     loc_1403BBC3A
0x1403bb660  mov     ecx, r15d
0x1403bb663  mov     dl, r15b
0x1403bb666  mov     r8, r15
0x1403bb669  test    rsi, rsi
0x1403bb66c  jz      short loc_1403BB695
0x1403bb66e  cmp     dword ptr [rsi+10h], 74727044h
0x1403bb675  jnz     short loc_1403BB695
0x1403bb677  cmp     dword ptr [rsi+14h], 2
0x1403bb67b  jnz     short loc_1403BB695
0x1403bb67d  mov     eax, [rsi+15D8h]
0x1403bb683  mov     r8, rsi
0x1403bb686  shr     eax, 1
0x1403bb688  and     al, r14b
0x1403bb68b  cmp     [rsi+1418h], r15b
0x1403bb692  setnz   dl
0x1403bb695  cmp     dword ptr [r12+18h], 6
0x1403bb69b  jnz     loc_1403BB736
0x1403bb6a1  cmp     byte ptr cs:word_1401633F8+1, r15b
0x1403bb6a8  jz      loc_1403BB736
0x1403bb6ae  test    dl, dl
0x1403bb6b0  jnz     short loc_1403BB6EF
0x1403bb6b2  mov     rdx, r13
0x1403bb6b5  mov     rcx, rdi
0x1403bb6b8  call    DpiKsrStopAdapter
0x1403bb6bd  mov     ebx, eax
0x1403bb6bf  cmp     eax, 0C00000BBh
0x1403bb6c4  jz      loc_1403BB566
0x1403bb6ca  mov     rcx, rdi
0x1403bb6cd  call    DpiFdoIsMsBddAnchoredDevice
0x1403bb6d2  test    al, al
0x1403bb6d4  jz      short loc_1403BB6E8
0x1403bb6d6  mov     eax, cs:dword_140163250
0x1403bb6dc  dec     eax
0x1403bb6de  cmp     eax, r14d
0x1403bb6e1  ja      short loc_1403BB6E8
0x1403bb6e3  call    DpiKsrSetBootGraphicsInformation
0x1403bb6e8  mov     eax, ebx
0x1403bb6ea  jmp     loc_1403BBC86
0x1403bb6ef  cmp     cs:byte_140163410, r15b
0x1403bb6f6  jz      short loc_1403BB736
0x1403bb6f8  test    al, al
0x1403bb6fa  jz      short loc_1403BB736
0x1403bb6fc  lea     rdx, [rbp+Timeout]
0x1403bb700  mov     dword ptr [rbp+Timeout], r15d
0x1403bb704  mov     rcx, r8
0x1403bb707  call    DpiDxgkDdiSaveMemoryForHotUpdate
0x1403bb70c  movsxd  rcx, eax
0x1403bb70f  test    eax, eax
0x1403bb711  jns     short loc_1403BB736
0x1403bb713  mov     rdx, rcx
0x1403bb716  mov     ecx, 2
0x1403bb71b  call    cs:__imp_WdLogSingleEntry1
0x1403bb722  nop     dword ptr [rax+rax+00h]
0x1403bb727  mov     cs:WdLogGlobalForLineNumber, 496h
0x1403bb731  jmp     loc_1403BB566
0x1403bb736  cmp     ecx, 0C00000BBh
0x1403bb73c  jnz     loc_1403BB566
0x1403bb742  add     [r13+43h], r14b
0x1403bb746  mov     rdx, r13; Irp
0x1403bb749  add     qword ptr [r13+0B8h], 48h ; 'H'
0x1403bb751  mov     rcx, [rsi+0A0h]; DeviceObject
0x1403bb758  call    cs:__imp_PoCallDriver
0x1403bb75f  nop     dword ptr [rax+rax+00h]
0x1403bb764  jmp     loc_1403BBC86
0x1403bb769  mov     r15d, [rbx]
0x1403bb76c  movzx   eax, byte ptr [r12+1]
0x1403bb772  test    r15d, r15d
0x1403bb775  jns     short loc_1403BB79E
0x1403bb777  mov     edx, eax
0x1403bb779  mov     ecx, 3
0x1403bb77e  call    cs:__imp_WdLogSingleEntry1
0x1403bb785  nop     dword ptr [rax+rax+00h]
0x1403bb78a  mov     cs:WdLogGlobalForLineNumber, 4FAh
0x1403bb794  mov     edi, 103h
0x1403bb799  jmp     loc_1403BBC3F
0x1403bb79e  cmp     al, 2
0x1403bb7a0  jnz     loc_1403BB887
0x1403bb7a6  cmp     byte ptr [rsi+486h], 0
0x1403bb7ad  jz      loc_1403BB887
0x1403bb7b3  cmp     [r12+18h], r14d
0x1403bb7b8  jnz     loc_1403BB887
0x1403bb7be  cmp     [rsi+11Ch], r14d
0x1403bb7c5  jz      loc_1403BB887
0x1403bb7cb  lea     rax, [rbp+Timeout]
0x1403bb7cf  mov     qword ptr [rbp+Timeout], 0FFFFFFFFF70F2E80h
0x1403bb7d7  lea     rcx, [rsi+4D8h]; Object
0x1403bb7de  mov     qword ptr [rsp+68h+RemlockSize], rax; Timeout
0x1403bb7e3  xor     r9d, r9d; Alertable
0x1403bb7e6  xor     r8d, r8d; WaitMode
0x1403bb7e9  xor     edx, edx; WaitReason
0x1403bb7eb  call    cs:__imp_KeWaitForSingleObject
0x1403bb7f2  nop     dword ptr [rax+rax+00h]
0x1403bb7f7  mov     edx, 102h
0x1403bb7fc  cmp     eax, edx
0x1403bb7fe  jnz     short loc_1403BB81D
0x1403bb800  mov     ecx, 2
0x1403bb805  call    cs:__imp_WdLogSingleEntry1
0x1403bb80c  nop     dword ptr [rax+rax+00h]
0x1403bb811  mov     cs:WdLogGlobalForLineNumber, 51Fh
0x1403bb81b  jmp     short loc_1403BB887
0x1403bb81d  test    eax, eax
0x1403bb81f  jns     short loc_1403BB841
0x1403bb821  movsxd  rdx, eax
0x1403bb824  mov     ecx, 2
0x1403bb829  call    cs:__imp_WdLogSingleEntry1
0x1403bb830  nop     dword ptr [rax+rax+00h]
0x1403bb835  mov     cs:WdLogGlobalForLineNumber, 526h
0x1403bb83f  jmp     short loc_1403BB887
0x1403bb841  lea     rcx, [rsi+4F0h]; Object
0x1403bb848  mov     qword ptr [rsp+68h+RemlockSize], 0; Timeout
0x1403bb851  xor     r9d, r9d; Alertable
0x1403bb854  xor     r8d, r8d; WaitMode
0x1403bb857  xor     edx, edx; WaitReason
0x1403bb859  call    cs:__imp_KeWaitForSingleObject
0x1403bb860  nop     dword ptr [rax+rax+00h]
0x1403bb865  test    eax, eax
0x1403bb867  jns     short loc_1403BB887
0x1403bb869  movsxd  rdx, eax
0x1403bb86c  mov     ecx, 2
0x1403bb871  call    cs:__imp_WdLogSingleEntry1
0x1403bb878  nop     dword ptr [rax+rax+00h]
0x1403bb87d  mov     cs:WdLogGlobalForLineNumber, 539h
0x1403bb887  call    cs:__imp_KeEnterCriticalRegion
0x1403bb88e  nop     dword ptr [rax+rax+00h]
0x1403bb893  cmp     byte ptr [rsi+1E4h], 0
0x1403bb89a  jz      short loc_1403BB8A4
0x1403bb89c  mov     rcx, rsi
0x1403bb89f  call    DpiCheckForOutstandingD3Requests
0x1403bb8a4  mov     rcx, [rsi+0A8h]; Resource
0x1403bb8ab  mov     dl, r14b; Wait
0x1403bb8ae  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403bb8b5  nop     dword ptr [rax+rax+00h]
0x1403bb8ba  cmp     byte ptr [r12+1], 2
0x1403bb8c0  jnz     short loc_1403BB8D2
0x1403bb8c2  mov     eax, [r12+18h]
0x1403bb8c7  cmp     eax, r14d
0x1403bb8ca  jbe     short loc_1403BB8D2
0x1403bb8cc  mov     [rsi+118h], eax
0x1403bb8d2  xor     r8d, r8d
0x1403bb8d5  cmp     [rsi+486h], r8b
0x1403bb8dc  jnz     loc_1403BBC04
0x1403bb8e2  movsxd  rdx, dword ptr [r12+18h]
0x1403bb8e7  mov     ebx, [rsi+rdx*4+538h]
0x1403bb8ee  cmp     [rsi+1E0h], r8b
0x1403bb8f5  jz      loc_1403BBC98
0x1403bb8fb  mov     r15d, r8d
0x1403bb8fe  test    rsi, rsi
0x1403bb901  jz      loc_1403BBBF5
0x1403bb907  cmp     dword ptr [rsi+10h], 74727044h
0x1403bb90e  jnz     loc_1403BBBF5
0x1403bb914  cmp     dword ptr [rsi+14h], 2
0x1403bb918  jnz     loc_1403BBBF5
0x1403bb91e  cmp     dword ptr [rsi+0ECh], 2
0x1403bb925  jnz     loc_1403BBBF5
0x1403bb92b  cmp     byte ptr [r12+1], 2
0x1403bb931  jnz     loc_1403BBBF5
0x1403bb937  mov     eax, cs:dword_140163250
0x1403bb93d  mov     ecx, [r12+20h]
0x1403bb942  add     eax, 0FFFFFFFCh
0x1403bb945  cmp     eax, r14d
0x1403bb948  mov     [rbp+arg_18], ecx
0x1403bb94b  setbe   al
0x1403bb94e  mov     byte ptr [rbp+Timeout], al
0x1403bb951  cmp     ebx, r14d
0x1403bb954  jnz     short loc_1403BB96A
0x1403bb956  mov     r8d, ecx
0x1403bb959  mov     rcx, rdi
0x1403bb95c  call    DpiCorrectPowerAction
0x1403bb961  mov     [rbp+arg_18], eax
0x1403bb964  xor     r8d, r8d
0x1403bb967  mov     al, byte ptr [rbp+Timeout]
0x1403bb96a  cmp     [rsi+481h], r8b
0x1403bb971  jz      loc_1403BBADC
0x1403bb977  cmp     ebx, [rsi+11Ch]
0x1403bb97d  jge     loc_1403BBADC
0x1403bb983  cmp     cs:qword_140163100, r8
0x1403bb98a  jz      short loc_1403BBA02
0x1403bb98c  test    al, al
0x1403bb98e  jz      loc_1403BBADC
0x1403bb994  mov     rcx, cs:?g_pDriverObject@@3PEAU_DRIVER_OBJECT@@EA; DeviceObject
0x1403bb99b  call    cs:__imp_IoAllocateWorkItem
0x1403bb9a2  nop     dword ptr [rax+rax+00h]
0x1403bb9a7  mov     rcx, rax; IoWorkItem
0x1403bb9aa  test    rax, rax
0x1403bb9ad  jnz     short loc_1403BB9D4
0x1403bb9af  mov     rdx, 0FFFFFFFFC000009Ah
0x1403bb9b6  lea     ecx, [rax+6]
0x1403bb9b9  call    cs:__imp_WdLogSingleEntry1
0x1403bb9c0  nop     dword ptr [rax+rax+00h]
0x1403bb9c5  mov     cs:WdLogGlobalForLineNumber, 5A0h
0x1403bb9cf  jmp     loc_1403BBADC
0x1403bb9d4  mov     eax, 4
0x1403bb9d9  lea     edx, [rax+1]
0x1403bb9dc  lock cmpxchg cs:dword_140163250, edx
0x1403bb9e4  xor     r9d, r9d; Context
0x1403bb9e7  lea     rdx, DpiDisableMsBddFallbackDriverWorkItem; WorkerRoutine
0x1403bb9ee  mov     r8d, r14d; QueueType
0x1403bb9f1  call    cs:__imp_IoQueueWorkItemEx
0x1403bb9f8  nop     dword ptr [rax+rax+00h]
0x1403bb9fd  jmp     loc_1403BBADC
0x1403bba02  cmp     cs:byte_140163270, r8b
0x1403bba09  jz      loc_1403BBADC
0x1403bba0f  xor     r8d, r8d
0x1403bba12  lea     rcx, xmmword_140163108
0x1403bba19  mov     dl, r14b
0x1403bba1c  call    DpiAcquirePostDisplayInfoFromBgfx
0x1403bba21  cmp     byte ptr [rbp+Timeout], r15b
0x1403bba25  jz      loc_1403BBADC
0x1403bba2b  movups  xmm0, cs:xmmword_140163108
0x1403bba32  mov     cs:byte_140163270, r15b
0x1403bba39  movups  xmm1, cs:xmmword_140163118
0x1403bba40  mov     cs:dword_14016329C, r14d
0x1403bba47  movups  cs:xmmword_1401631B0, xmm0
0x1403bba4e  movups  xmm0, cs:xmmword_140163128
  ... truncated ...
```
