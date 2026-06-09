# DpiFdoHandleSystemPower

- ea: `0x1403bc1d0`
- end: `0x1403bc9e3`
- name: `DpiFdoHandleSystemPower`
- size: `2067`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Context)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1403bb860`

## callees

- `0x140022264`
- `0x140035dc0`
- `0x140041b54`
- `0x1400554d4`
- `0x140061f54`
- `0x1400a0540`
- `0x1402b09dc`
- `0x1402b8cac`
- `0x1402b94d4`
- `0x1402b95a4`
- `0x140365d6c`
- `0x140366e70`
- `0x1403676e0`
- `0x140367710`
- `0x1403bc1d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bc567`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bc859`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bc567`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403bc859`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bc893`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bc90e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bc893`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403bc90e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bc58e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bc872`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bc58e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403bc872`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bc887`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bc902`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bc887`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403bc902`
- `ntoskrnl!KeInitializeEvent` at `0x1403bc280`
- `ntoskrnl!KeInitializeEvent` at `0x1403bc280`
- `ntoskrnl!InbvNotifyDisplayOwnershipChange` at `0x1403bc801`
- `ntoskrnl!InbvNotifyDisplayOwnershipChange` at `0x1403bc801`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403bc67b`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403bc67b`
- `ntoskrnl!IofCompleteRequest` at `0x1403bc936`
- `ntoskrnl!IofCompleteRequest` at `0x1403bc936`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bc2fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bc4cb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bc539`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bc2fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bc4cb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403bc539`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1403bc6d1`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1403bc6d1`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1403bc26a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1403bc26a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403bc94f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1403bc94f`
- `ntoskrnl!PoRequestPowerIrp` at `0x1403bc9a3`
- `ntoskrnl!PoRequestPowerIrp` at `0x1403bc9a3`
- `ntoskrnl!PoCallDriver` at `0x1403bc2e0`
- `ntoskrnl!PoCallDriver` at `0x1403bc438`
- `ntoskrnl!PoCallDriver` at `0x1403bc2e0`
- `ntoskrnl!PoCallDriver` at `0x1403bc438`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1403bc922`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1403bc922`
- `watchdog!WdLogSingleEntry1` at `0x1403bc320`
- `watchdog!WdLogSingleEntry1` at `0x1403bc3fb`
- `watchdog!WdLogSingleEntry1` at `0x1403bc45e`
- `watchdog!WdLogSingleEntry1` at `0x1403bc4e5`
- `watchdog!WdLogSingleEntry1` at `0x1403bc509`
- `watchdog!WdLogSingleEntry1` at `0x1403bc551`
- `watchdog!WdLogSingleEntry1` at `0x1403bc699`
- `watchdog!WdLogSingleEntry1` at `0x1403bc9c4`
- `watchdog!WdLogSingleEntry1` at `0x1403bc320`
- `watchdog!WdLogSingleEntry1` at `0x1403bc3fb`
- `watchdog!WdLogSingleEntry1` at `0x1403bc45e`
- `watchdog!WdLogSingleEntry1` at `0x1403bc4e5`
- `watchdog!WdLogSingleEntry1` at `0x1403bc509`
- `watchdog!WdLogSingleEntry1` at `0x1403bc551`
- `watchdog!WdLogSingleEntry1` at `0x1403bc699`
- `watchdog!WdLogSingleEntry1` at `0x1403bc9c4`

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
  NTSTATUS v10; // r15d
  NTSTATUS *v11; // rbx
  bool v12; // dl
  char *v13; // r8
  int v14; // ebx
  NTSTATUS v16; // eax
  unsigned int LowPart; // eax
  __int64 v18; // rdx
  POWER_STATE v19; // ebx
  ULONG EaLength; // ecx
  char v21; // al
  struct _IO_WORKITEM *WorkItem; // rcx
  __int64 v23; // rcx
  struct _IO_STACK_LOCATION *v24; // rax
  char v25[8]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v26; // [rsp+40h] [rbp-28h]
  struct _KEVENT Event; // [rsp+48h] [rbp-20h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+B8h] [rbp+50h] BYREF
  char v30; // [rsp+C0h] [rbp+58h]
  ULONG v31; // [rsp+C8h] [rbp+60h]

  CurrentStackLocation = Context->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  memset(&Event, 0, sizeof(Event));
  v7 = (unsigned int)CurrentStackLocation->MinorFunction - 2;
  if ( CurrentStackLocation->MinorFunction != 2 )
  {
    if ( CurrentStackLocation->MinorFunction != 3 )
    {
      ++Context->CurrentLocation;
      ++Context->Tail.Overlay.CurrentStackLocation;
      return PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), Context);
    }
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
    {
      Timeout.QuadPart = -300000000;
      LOBYTE(v7) = 1;
      DpiFdoStopMiracastSession(DeviceObject, v7, &Timeout, 131);
    }
LABEL_5:
    v30 = 0;
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
    v11 = (NTSTATUS *)&Context->IoStatus.0;
    if ( v10 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1246;
    }
    else
    {
      v10 = *v11;
      if ( *v11 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1274;
        goto LABEL_74;
      }
      if ( CurrentStackLocation->MinorFunction == 2
        && DeviceExtension[1158]
        && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1
        && *((_DWORD *)DeviceExtension + 71) != 1 )
      {
        Timeout.QuadPart = -150000000;
        v16 = KeWaitForSingleObject(DeviceExtension + 1240, Executive, 0, 0, &Timeout);
        if ( v16 == 258 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1311;
        }
        else if ( v16 >= 0 )
        {
          if ( KeWaitForSingleObject(DeviceExtension + 1264, Executive, 0, 0, 0) < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1337;
          }
        }
        else
        {
          WdLogSingleEntry1(2);
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
        v18 = (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        v19.SystemState = *(SYSTEM_POWER_STATE *)&DeviceExtension[4 * v18 + 1336];
        if ( DeviceExtension[480] )
        {
          v10 = 0;
          if ( DeviceExtension
            && *((_DWORD *)DeviceExtension + 4) == 1953656900
            && *((_DWORD *)DeviceExtension + 5) == 2
            && *((_DWORD *)DeviceExtension + 59) == 2
            && CurrentStackLocation->MinorFunction == 2 )
          {
            EaLength = CurrentStackLocation->Parameters.Create.EaLength;
            v31 = EaLength;
            v21 = (unsigned int)(dword_14015F1D0 - 4) <= 1;
            LOBYTE(Timeout.LowPart) = v21;
            if ( v19.SystemState == PowerSystemWorking )
            {
              v31 = DpiCorrectPowerAction(DeviceObject, v18, EaLength);
              v21 = Timeout.LowPart;
            }
            if ( DeviceExtension[1153] && v19.SystemState < *((_DWORD *)DeviceExtension + 71) )
            {
              if ( qword_14015F080 )
              {
                if ( v21 )
                {
                  WorkItem = IoAllocateWorkItem(g_pDriverObject);
                  if ( WorkItem )
                  {
                    _InterlockedCompareExchange(&dword_14015F1D0, 5, 4);
                    IoQueueWorkItemEx(WorkItem, DpiDisableMsBddFallbackDriverWorkItem, DelayedWorkQueue, 0);
                  }
                  else
                  {
                    WdLogSingleEntry1(6);
                    WdLogGlobalForLineNumber = 1440;
                  }
                }
              }
              else if ( byte_14015F1F0 )
              {
                LOBYTE(v18) = 1;
                DpiAcquirePostDisplayInfoFromBgfx(&xmmword_14015F088, v18, 0);
                if ( LOBYTE(Timeout.LowPart) )
                {
                  byte_14015F1F0 = 0;
                  dword_14015F21C = 1;
                  xmmword_14015F130 = xmmword_14015F088;
                  xmmword_14015F140 = xmmword_14015F098;
                  xmmword_14015F150 = xmmword_14015F0A8;
                  xmmword_14015F160 = xmmword_14015F0B8;
                  xmmword_14015F170 = xmmword_14015F0C8;
                  xmmword_14015F180 = xmmword_14015F0D8;
                  xmmword_14015F190 = xmmword_14015F0E8;
                  xmmword_14015F1A0 = xmmword_14015F0F8;
                  xmmword_14015F1B0 = xmmword_14015F108;
                  xmmword_14015F1C0 = xmmword_14015F118;
                  qword_14015F1D8 = (__int64)KeGetCurrentThread();
                  qword_14015F1E0 = (__int64)DeviceObject;
                }
              }
            }
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD))DpiDxgkDdiSetPowerState)(
              *((_QWORD *)DeviceExtension + 5),
              *((_QWORD *)DeviceExtension + 6),
              -1,
              (POWER_STATE)v19.SystemState,
              v31);
            if ( DeviceExtension[1153] && LOBYTE(Timeout.LowPart) )
            {
              if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5 )
              {
                byte_14015F1F0 = 1;
                LOBYTE(v23) = 1;
                InbvNotifyDisplayOwnershipChange(v23, DpiEnterSystemDisplay);
              }
              else if ( v19.SystemState < *((_DWORD *)DeviceExtension + 71) )
              {
                xmmword_14015F140 = 0;
                DWORD2(xmmword_14015F140) = -1;
                xmmword_14015F130 = 0;
                memset(&xmmword_14015F150, 0, 0x80u);
                qword_14015F1E0 = 0;
                qword_14015F1D8 = (__int64)KeGetCurrentThread();
              }
            }
            KeEnterCriticalRegion();
            ExAcquireResourceExclusiveLite((PERESOURCE)(DeviceExtension + 3928), 1u);
            *((POWER_STATE *)DeviceExtension + 71) = v19;
            ExReleaseResourceLite((PERESOURCE)(DeviceExtension + 3928));
            KeLeaveCriticalRegion();
            if ( v19.SystemState == PowerSystemWorking )
            {
              v25[0] = 0;
              CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v25, 0, 0xBu, 0);
              DpiFdoInvalidateChildRelations(DeviceObject, 6, v26);
              CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v25);
            }
          }
          v11 = (NTSTATUS *)&Context->IoStatus.0;
          *((_DWORD *)DeviceExtension + 70) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        }
        else
        {
          v24 = Context->Tail.Overlay.CurrentStackLocation;
          v30 = 1;
          v24->Control |= 1u;
          v10 = PoRequestPowerIrp(
                  DeviceObject,
                  CurrentStackLocation->MinorFunction,
                  v19,
                  DpiFdoDevicePowerCompletionCallback,
                  Context,
                  0);
          if ( v10 != 259 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1599;
          }
          v11 = (NTSTATUS *)&Context->IoStatus.0;
        }
      }
      if ( DeviceExtension[484] )
        DpiEnableD3Requests(*((_QWORD *)DeviceExtension + 3));
      ExReleaseResourceLite(*((PERESOURCE *)DeviceExtension + 21));
      KeLeaveCriticalRegion();
    }
    if ( v10 == 259 )
      return v10;
LABEL_74:
    PoStartNextPowerIrp(Context);
    *v11 = v10;
    IofCompleteRequest(Context, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Context, 0x20u);
    if ( v30 )
      return 259;
    return v10;
  }
  v12 = 0;
  v13 = 0;
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
  {
    v13 = DeviceExtension;
    v3 = (*((_DWORD *)DeviceExtension + 1398) & 2) != 0;
    v12 = DeviceExtension[5144] != 0;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 6 || !HIBYTE(word_14015F378) )
    goto LABEL_5;
  if ( v12 )
  {
    if ( byte_14015F390 )
    {
      if ( v3 )
      {
        Timeout.LowPart = 0;
        if ( (int)DpiDxgkDdiSaveMemoryForHotUpdate(v13, &Timeout) < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1174;
        }
      }
    }
    goto LABEL_5;
  }
  v14 = DpiKsrStopAdapter(DeviceObject, Context, v13);
  if ( v14 == -1073741637 )
    goto LABEL_5;
  if ( (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(DeviceObject) && (unsigned int)(dword_14015F1D0 - 1) <= 1 )
    DpiKsrSetBootGraphicsInformation();
  return v14;
}

```

## disassembly

```asm
0x1403bc1d0  mov     [rsp-40h+arg_0], rcx
0x1403bc1d5  push    rbp
0x1403bc1d6  push    rbx
0x1403bc1d7  push    rsi
0x1403bc1d8  push    rdi
0x1403bc1d9  push    r12
0x1403bc1db  push    r13
0x1403bc1dd  push    r14
0x1403bc1df  push    r15
0x1403bc1e1  mov     rbp, rsp
0x1403bc1e4  sub     rsp, 68h
0x1403bc1e8  mov     r12, [rdx+0B8h]
0x1403bc1ef  xor     eax, eax
0x1403bc1f1  mov     rsi, [rcx+40h]
0x1403bc1f5  mov     r13, rdx
0x1403bc1f8  xorps   xmm0, xmm0
0x1403bc1fb  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1403bc1ff  movups  xmmword ptr [rbp+Event.Header], xmm0
0x1403bc203  movzx   edx, byte ptr [r12+1]
0x1403bc209  lea     r14d, [rax+1]
0x1403bc20d  xor     r15d, r15d
0x1403bc210  mov     rdi, rcx
0x1403bc213  sub     edx, 2
0x1403bc216  jz      loc_1403BC340
0x1403bc21c  cmp     edx, r14d
0x1403bc21f  jnz     loc_1403BC422
0x1403bc225  cmp     [r12+18h], r14d
0x1403bc22a  jz      short loc_1403BC246
0x1403bc22c  mov     r9d, 83h
0x1403bc232  mov     qword ptr [rbp+Timeout], 0FFFFFFFFEE1E5D00h
0x1403bc23a  lea     r8, [rbp+Timeout]
0x1403bc23e  mov     dl, r14b
0x1403bc241  call    DpiFdoStopMiracastSession
0x1403bc246  lea     rax, [rsi+40h]
0x1403bc24a  mov     [rbp+arg_10], r15b
0x1403bc24e  mov     rcx, rax; RemoveLock
0x1403bc251  mov     [rbp+RemoveLock], rax
0x1403bc255  mov     r9d, r14d; Line
0x1403bc258  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x1403bc260  lea     r8, File; File
0x1403bc267  mov     rdx, r13; Tag
0x1403bc26a  call    cs:__imp_IoAcquireRemoveLockEx
0x1403bc271  nop     dword ptr [rax+rax+00h]
0x1403bc276  xor     r8d, r8d; State
0x1403bc279  lea     rcx, [rbp+Event]; Event
0x1403bc27d  mov     edx, r14d; Type
0x1403bc280  call    cs:__imp_KeInitializeEvent
0x1403bc287  nop     dword ptr [rax+rax+00h]
0x1403bc28c  mov     rax, [r13+0B8h]
0x1403bc293  lea     rcx, DpiFdoPowerCompletionRoutine
0x1403bc29a  mov     rdx, r13; Irp
0x1403bc29d  movups  xmm0, xmmword ptr [rax]
0x1403bc2a0  movups  xmmword ptr [rax-48h], xmm0
0x1403bc2a4  movups  xmm1, xmmword ptr [rax+10h]
0x1403bc2a8  movups  xmmword ptr [rax-38h], xmm1
0x1403bc2ac  movups  xmm0, xmmword ptr [rax+20h]
0x1403bc2b0  movups  xmmword ptr [rax-28h], xmm0
0x1403bc2b4  movsd   xmm1, qword ptr [rax+30h]
0x1403bc2b9  movsd   qword ptr [rax-18h], xmm1
0x1403bc2be  mov     [rax-45h], r15b
0x1403bc2c2  mov     rax, [r13+0B8h]
0x1403bc2c9  mov     [rax-10h], rcx
0x1403bc2cd  lea     rcx, [rbp+Event]
0x1403bc2d1  mov     [rax-8], rcx
0x1403bc2d5  mov     byte ptr [rax-45h], 0E0h
0x1403bc2d9  mov     rcx, [rsi+0A0h]; DeviceObject
0x1403bc2e0  call    cs:__imp_PoCallDriver
0x1403bc2e7  nop     dword ptr [rax+rax+00h]
0x1403bc2ec  xor     r9d, r9d; Alertable
0x1403bc2ef  mov     qword ptr [rsp+68h+RemlockSize], r15; Timeout
0x1403bc2f4  xor     r8d, r8d; WaitMode
0x1403bc2f7  lea     rcx, [rbp+Event]; Object
0x1403bc2fb  xor     edx, edx; WaitReason
0x1403bc2fd  call    cs:__imp_KeWaitForSingleObject
0x1403bc304  nop     dword ptr [rax+rax+00h]
0x1403bc309  movsxd  r15, eax
0x1403bc30c  lea     rbx, [r13+30h]
0x1403bc310  test    eax, eax
0x1403bc312  jz      loc_1403BC449
0x1403bc318  mov     rdx, r15
0x1403bc31b  mov     ecx, 2
0x1403bc320  call    cs:__imp_WdLogSingleEntry1
0x1403bc327  nop     dword ptr [rax+rax+00h]
0x1403bc32c  mov     cs:WdLogGlobalForLineNumber, 4DEh
0x1403bc336  mov     edi, 103h
0x1403bc33b  jmp     loc_1403BC91A
0x1403bc340  mov     ecx, r15d
0x1403bc343  mov     dl, r15b
0x1403bc346  mov     r8, r15
0x1403bc349  test    rsi, rsi
0x1403bc34c  jz      short loc_1403BC375
0x1403bc34e  cmp     dword ptr [rsi+10h], 74727044h
0x1403bc355  jnz     short loc_1403BC375
0x1403bc357  cmp     dword ptr [rsi+14h], 2
0x1403bc35b  jnz     short loc_1403BC375
0x1403bc35d  mov     eax, [rsi+15D8h]
0x1403bc363  mov     r8, rsi
0x1403bc366  shr     eax, 1
0x1403bc368  and     al, r14b
0x1403bc36b  cmp     [rsi+1418h], r15b
0x1403bc372  setnz   dl
0x1403bc375  cmp     dword ptr [r12+18h], 6
0x1403bc37b  jnz     loc_1403BC416
0x1403bc381  cmp     byte ptr cs:word_14015F378+1, r15b
0x1403bc388  jz      loc_1403BC416
0x1403bc38e  test    dl, dl
0x1403bc390  jnz     short loc_1403BC3CF
0x1403bc392  mov     rdx, r13
0x1403bc395  mov     rcx, rdi
0x1403bc398  call    DpiKsrStopAdapter
0x1403bc39d  mov     ebx, eax
0x1403bc39f  cmp     eax, 0C00000BBh
0x1403bc3a4  jz      loc_1403BC246
0x1403bc3aa  mov     rcx, rdi
0x1403bc3ad  call    DpiFdoIsMsBddAnchoredDevice
0x1403bc3b2  test    al, al
0x1403bc3b4  jz      short loc_1403BC3C8
0x1403bc3b6  mov     eax, cs:dword_14015F1D0
0x1403bc3bc  dec     eax
0x1403bc3be  cmp     eax, r14d
0x1403bc3c1  ja      short loc_1403BC3C8
0x1403bc3c3  call    DpiKsrSetBootGraphicsInformation
0x1403bc3c8  mov     eax, ebx
0x1403bc3ca  jmp     loc_1403BC966
0x1403bc3cf  cmp     cs:byte_14015F390, r15b
0x1403bc3d6  jz      short loc_1403BC416
0x1403bc3d8  test    al, al
0x1403bc3da  jz      short loc_1403BC416
0x1403bc3dc  lea     rdx, [rbp+Timeout]
0x1403bc3e0  mov     dword ptr [rbp+Timeout], r15d
0x1403bc3e4  mov     rcx, r8
0x1403bc3e7  call    DpiDxgkDdiSaveMemoryForHotUpdate
0x1403bc3ec  movsxd  rcx, eax
0x1403bc3ef  test    eax, eax
0x1403bc3f1  jns     short loc_1403BC416
0x1403bc3f3  mov     rdx, rcx
0x1403bc3f6  mov     ecx, 2
0x1403bc3fb  call    cs:__imp_WdLogSingleEntry1
0x1403bc402  nop     dword ptr [rax+rax+00h]
0x1403bc407  mov     cs:WdLogGlobalForLineNumber, 496h
0x1403bc411  jmp     loc_1403BC246
0x1403bc416  cmp     ecx, 0C00000BBh
0x1403bc41c  jnz     loc_1403BC246
0x1403bc422  add     [r13+43h], r14b
0x1403bc426  mov     rdx, r13; Irp
0x1403bc429  add     qword ptr [r13+0B8h], 48h ; 'H'
0x1403bc431  mov     rcx, [rsi+0A0h]; DeviceObject
0x1403bc438  call    cs:__imp_PoCallDriver
0x1403bc43f  nop     dword ptr [rax+rax+00h]
0x1403bc444  jmp     loc_1403BC966
0x1403bc449  mov     r15d, [rbx]
0x1403bc44c  movzx   eax, byte ptr [r12+1]
0x1403bc452  test    r15d, r15d
0x1403bc455  jns     short loc_1403BC47E
0x1403bc457  mov     edx, eax
0x1403bc459  mov     ecx, 3
0x1403bc45e  call    cs:__imp_WdLogSingleEntry1
0x1403bc465  nop     dword ptr [rax+rax+00h]
0x1403bc46a  mov     cs:WdLogGlobalForLineNumber, 4FAh
0x1403bc474  mov     edi, 103h
0x1403bc479  jmp     loc_1403BC91F
0x1403bc47e  cmp     al, 2
0x1403bc480  jnz     loc_1403BC567
0x1403bc486  cmp     byte ptr [rsi+486h], 0
0x1403bc48d  jz      loc_1403BC567
0x1403bc493  cmp     [r12+18h], r14d
0x1403bc498  jnz     loc_1403BC567
0x1403bc49e  cmp     [rsi+11Ch], r14d
0x1403bc4a5  jz      loc_1403BC567
0x1403bc4ab  lea     rax, [rbp+Timeout]
0x1403bc4af  mov     qword ptr [rbp+Timeout], 0FFFFFFFFF70F2E80h
0x1403bc4b7  lea     rcx, [rsi+4D8h]; Object
0x1403bc4be  mov     qword ptr [rsp+68h+RemlockSize], rax; Timeout
0x1403bc4c3  xor     r9d, r9d; Alertable
0x1403bc4c6  xor     r8d, r8d; WaitMode
0x1403bc4c9  xor     edx, edx; WaitReason
0x1403bc4cb  call    cs:__imp_KeWaitForSingleObject
0x1403bc4d2  nop     dword ptr [rax+rax+00h]
0x1403bc4d7  mov     edx, 102h
0x1403bc4dc  cmp     eax, edx
0x1403bc4de  jnz     short loc_1403BC4FD
0x1403bc4e0  mov     ecx, 2
0x1403bc4e5  call    cs:__imp_WdLogSingleEntry1
0x1403bc4ec  nop     dword ptr [rax+rax+00h]
0x1403bc4f1  mov     cs:WdLogGlobalForLineNumber, 51Fh
0x1403bc4fb  jmp     short loc_1403BC567
0x1403bc4fd  test    eax, eax
0x1403bc4ff  jns     short loc_1403BC521
0x1403bc501  movsxd  rdx, eax
0x1403bc504  mov     ecx, 2
0x1403bc509  call    cs:__imp_WdLogSingleEntry1
0x1403bc510  nop     dword ptr [rax+rax+00h]
0x1403bc515  mov     cs:WdLogGlobalForLineNumber, 526h
0x1403bc51f  jmp     short loc_1403BC567
0x1403bc521  lea     rcx, [rsi+4F0h]; Object
0x1403bc528  mov     qword ptr [rsp+68h+RemlockSize], 0; Timeout
0x1403bc531  xor     r9d, r9d; Alertable
0x1403bc534  xor     r8d, r8d; WaitMode
0x1403bc537  xor     edx, edx; WaitReason
0x1403bc539  call    cs:__imp_KeWaitForSingleObject
0x1403bc540  nop     dword ptr [rax+rax+00h]
0x1403bc545  test    eax, eax
0x1403bc547  jns     short loc_1403BC567
0x1403bc549  movsxd  rdx, eax
0x1403bc54c  mov     ecx, 2
0x1403bc551  call    cs:__imp_WdLogSingleEntry1
0x1403bc558  nop     dword ptr [rax+rax+00h]
0x1403bc55d  mov     cs:WdLogGlobalForLineNumber, 539h
0x1403bc567  call    cs:__imp_KeEnterCriticalRegion
0x1403bc56e  nop     dword ptr [rax+rax+00h]
0x1403bc573  cmp     byte ptr [rsi+1E4h], 0
0x1403bc57a  jz      short loc_1403BC584
0x1403bc57c  mov     rcx, rsi
0x1403bc57f  call    DpiCheckForOutstandingD3Requests
0x1403bc584  mov     rcx, [rsi+0A8h]; Resource
0x1403bc58b  mov     dl, r14b; Wait
0x1403bc58e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403bc595  nop     dword ptr [rax+rax+00h]
0x1403bc59a  cmp     byte ptr [r12+1], 2
0x1403bc5a0  jnz     short loc_1403BC5B2
0x1403bc5a2  mov     eax, [r12+18h]
0x1403bc5a7  cmp     eax, r14d
0x1403bc5aa  jbe     short loc_1403BC5B2
0x1403bc5ac  mov     [rsi+118h], eax
0x1403bc5b2  xor     r8d, r8d
0x1403bc5b5  cmp     [rsi+486h], r8b
0x1403bc5bc  jnz     loc_1403BC8E4
0x1403bc5c2  movsxd  rdx, dword ptr [r12+18h]
0x1403bc5c7  mov     ebx, [rsi+rdx*4+538h]
0x1403bc5ce  cmp     [rsi+1E0h], r8b
0x1403bc5d5  jz      loc_1403BC978
0x1403bc5db  mov     r15d, r8d
0x1403bc5de  test    rsi, rsi
0x1403bc5e1  jz      loc_1403BC8D5
0x1403bc5e7  cmp     dword ptr [rsi+10h], 74727044h
0x1403bc5ee  jnz     loc_1403BC8D5
0x1403bc5f4  cmp     dword ptr [rsi+14h], 2
0x1403bc5f8  jnz     loc_1403BC8D5
0x1403bc5fe  cmp     dword ptr [rsi+0ECh], 2
0x1403bc605  jnz     loc_1403BC8D5
0x1403bc60b  cmp     byte ptr [r12+1], 2
0x1403bc611  jnz     loc_1403BC8D5
0x1403bc617  mov     eax, cs:dword_14015F1D0
0x1403bc61d  mov     ecx, [r12+20h]
0x1403bc622  add     eax, 0FFFFFFFCh
0x1403bc625  cmp     eax, r14d
0x1403bc628  mov     [rbp+arg_18], ecx
0x1403bc62b  setbe   al
0x1403bc62e  mov     byte ptr [rbp+Timeout], al
0x1403bc631  cmp     ebx, r14d
0x1403bc634  jnz     short loc_1403BC64A
0x1403bc636  mov     r8d, ecx
0x1403bc639  mov     rcx, rdi
0x1403bc63c  call    DpiCorrectPowerAction
0x1403bc641  mov     [rbp+arg_18], eax
0x1403bc644  xor     r8d, r8d
0x1403bc647  mov     al, byte ptr [rbp+Timeout]
0x1403bc64a  cmp     [rsi+481h], r8b
0x1403bc651  jz      loc_1403BC7BC
0x1403bc657  cmp     ebx, [rsi+11Ch]
0x1403bc65d  jge     loc_1403BC7BC
0x1403bc663  cmp     cs:qword_14015F080, r8
0x1403bc66a  jz      short loc_1403BC6E2
0x1403bc66c  test    al, al
0x1403bc66e  jz      loc_1403BC7BC
0x1403bc674  mov     rcx, cs:?g_pDriverObject@@3PEAU_DRIVER_OBJECT@@EA; DeviceObject
0x1403bc67b  call    cs:__imp_IoAllocateWorkItem
0x1403bc682  nop     dword ptr [rax+rax+00h]
0x1403bc687  mov     rcx, rax; IoWorkItem
0x1403bc68a  test    rax, rax
0x1403bc68d  jnz     short loc_1403BC6B4
0x1403bc68f  mov     rdx, 0FFFFFFFFC000009Ah
0x1403bc696  lea     ecx, [rax+6]
0x1403bc699  call    cs:__imp_WdLogSingleEntry1
0x1403bc6a0  nop     dword ptr [rax+rax+00h]
0x1403bc6a5  mov     cs:WdLogGlobalForLineNumber, 5A0h
0x1403bc6af  jmp     loc_1403BC7BC
0x1403bc6b4  mov     eax, 4
0x1403bc6b9  lea     edx, [rax+1]
0x1403bc6bc  lock cmpxchg cs:dword_14015F1D0, edx
0x1403bc6c4  xor     r9d, r9d; Context
0x1403bc6c7  lea     rdx, DpiDisableMsBddFallbackDriverWorkItem; WorkerRoutine
0x1403bc6ce  mov     r8d, r14d; QueueType
0x1403bc6d1  call    cs:__imp_IoQueueWorkItemEx
0x1403bc6d8  nop     dword ptr [rax+rax+00h]
0x1403bc6dd  jmp     loc_1403BC7BC
0x1403bc6e2  cmp     cs:byte_14015F1F0, r8b
0x1403bc6e9  jz      loc_1403BC7BC
0x1403bc6ef  xor     r8d, r8d
0x1403bc6f2  lea     rcx, xmmword_14015F088
0x1403bc6f9  mov     dl, r14b
0x1403bc6fc  call    DpiAcquirePostDisplayInfoFromBgfx
0x1403bc701  cmp     byte ptr [rbp+Timeout], r15b
0x1403bc705  jz      loc_1403BC7BC
0x1403bc70b  movups  xmm0, cs:xmmword_14015F088
0x1403bc712  mov     cs:byte_14015F1F0, r15b
0x1403bc719  movups  xmm1, cs:xmmword_14015F098
0x1403bc720  mov     cs:dword_14015F21C, r14d
0x1403bc727  movups  cs:xmmword_14015F130, xmm0
0x1403bc72e  movups  xmm0, cs:xmmword_14015F0A8
  ... truncated ...
```
