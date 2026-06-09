# ClasspInitializeGesn

- ea: `0x14005479c`
- end: `0x140054e4f`
- name: `ClasspInitializeGesn`
- size: `1715`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140054e58`

## callees

- `0x140008360`
- `0x14000f630`
- `0x1400134a0`
- `0x14001fc38`
- `0x14001feac`
- `0x14002001c`
- `0x140021c78`
- `0x140022614`
- `0x14005479c`
- `0x14005bef0`
- `0x14005f690`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005487d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005487d`
- `ntoskrnl!IoAllocateMdl` at `0x140054861`
- `ntoskrnl!IoAllocateMdl` at `0x140054861`
- `ntoskrnl!ExAllocatePool2` at `0x140054822`
- `ntoskrnl!ExAllocatePool2` at `0x140054822`
- `ntoskrnl!IoFreeMdl` at `0x140054844`
- `ntoskrnl!IoFreeMdl` at `0x140054dfa`
- `ntoskrnl!IoFreeMdl` at `0x140054844`
- `ntoskrnl!IoFreeMdl` at `0x140054dfa`
- `ntoskrnl!IofCallDriver` at `0x14005490a`
- `ntoskrnl!IofCallDriver` at `0x14005490a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054e15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054e15`
- `ntoskrnl!KeInitializeEvent` at `0x1400548d9`
- `ntoskrnl!KeInitializeEvent` at `0x1400548d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054931`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054931`

## pseudocode

```c
__int64 __fastcall ClasspInitializeGesn(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, __int64 a2)
{
  __int64 Pool2; // rax
  struct _MDL *v5; // rcx
  struct _MDL *Mdl; // rax
  __int64 v7; // r8
  char v8; // al
  int v9; // r15d
  _STORAGE_DEVICE_DESCRIPTOR *DeviceDescriptor; // r12
  unsigned int v11; // r14d
  IRP *v12; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 v14; // r9
  __int64 v15; // rsi
  char v16; // cl
  int v17; // edx
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 result; // rax
  struct _MDL *v22; // rcx
  void *v23; // rcx
  ULONG ParameterValue; // [rsp+40h] [rbp-20h] BYREF
  struct _KEVENT Event; // [rsp+48h] [rbp-18h] BYREF
  char v26; // [rsp+B0h] [rbp+50h] BYREF
  int v27; // [rsp+B8h] [rbp+58h] BYREF

  v27 = -1073741637;
  ParameterValue = 0;
  v26 = 0;
  memset(&Event, 0, sizeof(Event));
  ClassGetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"MMCDetectionState", &ParameterValue);
  if ( ParameterValue != 1 )
  {
    if ( (FdoExtension->PrivateFdoData->HackFlags & 2) != 0 )
    {
LABEL_93:
      ClassSetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"MMCDetectionState", 1u);
    }
    else
    {
      if ( !*(_QWORD *)(a2 + 80) )
      {
        Pool2 = ExAllocatePool2(72, 8, 1061118803);
        *(_QWORD *)(a2 + 80) = Pool2;
        if ( !Pool2 )
          goto LABEL_92;
      }
      v5 = *(struct _MDL **)(a2 + 88);
      if ( v5 )
        IoFreeMdl(v5);
      Mdl = IoAllocateMdl(*(PVOID *)(a2 + 80), 8u, 0, 0, 0);
      *(_QWORD *)(a2 + 88) = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        v8 = 1;
        *(_DWORD *)(a2 + 96) = 8;
        *(_BYTE *)(a2 + 74) = 0;
        v9 = 0;
        DeviceDescriptor = FdoExtension->DeviceDescriptor;
        v11 = 0;
        v26 = 1;
        while ( v11 < 0x10 && v8 == 1 )
        {
          LOBYTE(v7) = 1;
          v12 = (IRP *)ClasspPrepareMcnIrp(FdoExtension, a2, v7);
          if ( !v12 )
            goto LABEL_92;
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          CurrentStackLocation = v12->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClassSignalCompletion;
          CurrentStackLocation[-1].Context = &Event;
          CurrentStackLocation[-1].Control = -32;
          v27 = IofCallDriver(FdoExtension->CommonExtension.LowerDeviceObject, v12);
          if ( v27 == 259 )
            v27 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          ClassReleaseRemoveLock(FdoExtension->DeviceObject, v12);
          if ( (*(_BYTE *)(a2 + 123) & 0x3F) != 1 )
          {
            LOBYTE(v14) = 15;
            InterpretSenseInfoWithoutHistory(FdoExtension->DeviceObject, v12, a2 + 120, v14, 0, 0, &v27, 0);
          }
          if ( DeviceDescriptor->BusType == BusTypeAtapi && *(_BYTE *)(a2 + 123) == 14 && (unsigned int)++v9 >= 4 )
          {
            v27 = -1073741435;
            goto LABEL_94;
          }
          if ( v27 == -1073741764 )
            v27 = 0;
          if ( v27 == -1073741808 || v27 == 258 || v27 == -1073741435 || v27 == -1073741643 )
          {
            ClassSetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"MMCDetectionState", 1u);
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              goto LABEL_98;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              v20 = 57;
LABEL_80:
              v19 = (unsigned int)v27;
LABEL_81:
              WPP_SF_Dq(
                v18->AttachedDevice,
                v20,
                WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
                v19,
                FdoExtension->DeviceObject);
              goto LABEL_94;
            }
            goto LABEL_94;
          }
          if ( v27 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              goto LABEL_98;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              v20 = 58;
              goto LABEL_80;
            }
            goto LABEL_94;
          }
          v15 = *(_QWORD *)(a2 + 80);
          if ( v11 )
          {
            v27 = ClasspInterpretGesnData(FdoExtension, *(unsigned __int8 **)(a2 + 80), &v26);
            if ( v27 < 0 )
              goto LABEL_93;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                59,
                WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
                FdoExtension->DeviceObject,
                *(unsigned __int8 *)(v15 + 3));
            }
            if ( (*(_BYTE *)(v15 + 3) & 0x10) != 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
            }
            if ( (*(_BYTE *)(v15 + 3) & 0x40) != 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
            }
            if ( (*(_BYTE *)(v15 + 3) & 2) != 0 )
            {
              if ( (FdoExtension->PrivateFdoData->HackFlags & 0x10) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
                }
                *(_BYTE *)(v15 + 3) &= ~2u;
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
              }
            }
            v16 = *(_BYTE *)(v15 + 3) & 0x5A;
            *(_BYTE *)(a2 + 74) = v16;
            if ( !v16 )
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                goto LABEL_98;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v19 = *(unsigned __int8 *)(v15 + 3);
                v20 = 64;
                goto LABEL_81;
              }
              goto LABEL_94;
            }
            v17 = 0;
            do
            {
              ++v17;
              v16 &= v16 - 1;
            }
            while ( v16 );
            if ( v17 == 1 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  65,
                  WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
                  FdoExtension->DeviceObject);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  66,
                  WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
                  FdoExtension->DeviceObject);
              }
              *(_BYTE *)(a2 + 73) = 1;
            }
          }
          v8 = v26;
          ++v11;
        }
        if ( (*(_BYTE *)(a2 + 74) & 0x10) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              67,
              WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
              FdoExtension->DeviceObject);
          }
          *(_BYTE *)(a2 + 72) = 1;
          ClassSetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"MMCDetectionState", 2u);
          return 0;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_98;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            68,
            WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
            FdoExtension->DeviceObject);
      }
      else
      {
LABEL_92:
        v27 = -1073741670;
      }
    }
  }
LABEL_94:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      69,
      WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
      FdoExtension->DeviceObject,
      v27);
  }
LABEL_98:
  v22 = *(struct _MDL **)(a2 + 88);
  if ( v22 )
  {
    IoFreeMdl(v22);
    *(_QWORD *)(a2 + 88) = 0;
  }
  v23 = *(void **)(a2 + 80);
  if ( v23 )
  {
    ExFreePoolWithTag(v23, 0);
    *(_QWORD *)(a2 + 80) = 0;
  }
  *(_BYTE *)(a2 + 72) = 0;
  result = 3221225659LL;
  *(_BYTE *)(a2 + 74) = 0;
  *(_DWORD *)(a2 + 96) = 0;
  return result;
}

```

## disassembly

```asm
0x14005479c  mov     [rsp-38h+arg_0], rbx
0x1400547a1  push    rbp
0x1400547a2  push    rsi
0x1400547a3  push    rdi
0x1400547a4  push    r12
0x1400547a6  push    r13
0x1400547a8  push    r14
0x1400547aa  push    r15
0x1400547ac  mov     rbp, rsp
0x1400547af  sub     rsp, 60h
0x1400547b3  mov     rbx, rdx
0x1400547b6  mov     [rbp+arg_18], 0C00000BBh
0x1400547bd  xor     r13d, r13d
0x1400547c0  lea     rdx, SubkeyName; "Classpnp"
0x1400547c7  xorps   xmm0, xmm0
0x1400547ca  mov     [rbp+ParameterValue], r13d
0x1400547ce  xor     eax, eax
0x1400547d0  mov     [rbp+arg_10], r13b
0x1400547d4  lea     r9, [rbp+ParameterValue]; ParameterValue
0x1400547d8  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1400547dc  lea     r8, aMmcdetectionst; "MMCDetectionState"
0x1400547e3  mov     rdi, rcx
0x1400547e6  movups  xmmword ptr [rbp+Event.Header.___u0], xmm0
0x1400547ea  call    ClassGetDeviceParameter
0x1400547ef  cmp     [rbp+ParameterValue], 1
0x1400547f3  jz      loc_140054DAF
0x1400547f9  mov     rax, [rdi+478h]
0x140054800  test    byte ptr [rax+528h], 2
0x140054807  jnz     loc_140054D93
0x14005480d  lea     esi, [r13+8]
0x140054811  cmp     [rbx+50h], r13
0x140054815  jnz     short loc_14005483B
0x140054817  mov     r8d, 3F3F6353h
0x14005481d  lea     ecx, [rsi+40h]
0x140054820  mov     edx, esi
0x140054822  call    cs:__imp_ExAllocatePool2
0x140054829  nop     dword ptr [rax+rax+00h]
0x14005482e  mov     [rbx+50h], rax
0x140054832  test    rax, rax
0x140054835  jz      loc_140054D8A
0x14005483b  mov     rcx, [rbx+58h]; Mdl
0x14005483f  test    rcx, rcx
0x140054842  jz      short loc_140054850
0x140054844  call    cs:__imp_IoFreeMdl
0x14005484b  nop     dword ptr [rax+rax+00h]
0x140054850  mov     rcx, [rbx+50h]; VirtualAddress
0x140054854  xor     r9d, r9d; ChargeQuota
0x140054857  xor     r8d, r8d; SecondaryBuffer
0x14005485a  mov     [rsp+60h+Irp], r13; Irp
0x14005485f  mov     edx, esi; Length
0x140054861  call    cs:__imp_IoAllocateMdl
0x140054868  nop     dword ptr [rax+rax+00h]
0x14005486d  mov     [rbx+58h], rax
0x140054871  test    rax, rax
0x140054874  jz      loc_140054D8A
0x14005487a  mov     rcx, rax; MemoryDescriptorList
0x14005487d  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140054884  nop     dword ptr [rax+rax+00h]
0x140054889  mov     al, 1
0x14005488b  mov     [rbx+60h], esi
0x14005488e  mov     [rbx+4Ah], r13b
0x140054892  mov     r15d, r13d
0x140054895  mov     r12, [rdi+208h]
0x14005489c  mov     r14d, r13d
0x14005489f  mov     [rbp+arg_10], al
0x1400548a2  cmp     r14d, 10h
0x1400548a6  jnb     loc_140054CE1
0x1400548ac  cmp     al, 1
0x1400548ae  jnz     loc_140054CE1
0x1400548b4  mov     r8b, al
0x1400548b7  mov     rdx, rbx
0x1400548ba  mov     rcx, rdi
0x1400548bd  call    ClasspPrepareMcnIrp
0x1400548c2  mov     rsi, rax
0x1400548c5  test    rax, rax
0x1400548c8  jz      loc_140054D8A
0x1400548ce  xor     r8d, r8d; State
0x1400548d1  lea     rcx, [rbp+Event]; Event
0x1400548d5  lea     edx, [r8+1]; Type
0x1400548d9  call    cs:__imp_KeInitializeEvent
0x1400548e0  nop     dword ptr [rax+rax+00h]
0x1400548e5  mov     rcx, [rsi+0B8h]
0x1400548ec  lea     rax, ClassSignalCompletion
0x1400548f3  mov     rdx, rsi; Irp
0x1400548f6  mov     [rcx-10h], rax
0x1400548fa  lea     rax, [rbp+Event]
0x1400548fe  mov     [rcx-8], rax
0x140054902  mov     byte ptr [rcx-45h], 0E0h
0x140054906  mov     rcx, [rdi+10h]; DeviceObject
0x14005490a  call    cs:__imp_IofCallDriver
0x140054911  nop     dword ptr [rax+rax+00h]
0x140054916  mov     [rbp+arg_18], eax
0x140054919  cmp     eax, 103h
0x14005491e  jnz     short loc_140054940
0x140054920  xor     r9d, r9d; Alertable
0x140054923  mov     [rsp+60h+Irp], r13; Timeout
0x140054928  xor     r8d, r8d; WaitMode
0x14005492b  lea     rcx, [rbp+Event]; Object
0x14005492f  xor     edx, edx; WaitReason
0x140054931  call    cs:__imp_KeWaitForSingleObject
0x140054938  nop     dword ptr [rax+rax+00h]
0x14005493d  mov     [rbp+arg_18], eax
0x140054940  mov     rcx, [rdi+8]; DeviceObject
0x140054944  mov     rdx, rsi; Tag
0x140054947  call    ClassReleaseRemoveLock
0x14005494c  mov     al, [rbx+7Bh]
0x14005494f  and     al, 3Fh
0x140054951  cmp     al, 1
0x140054953  jz      short loc_140054980
0x140054955  mov     rcx, [rdi+8]
0x140054959  lea     rax, [rbp+arg_18]
0x14005495d  mov     [rsp+60h+var_28], r13
0x140054962  lea     r8, [rbx+78h]
0x140054966  mov     [rsp+60h+var_30], rax
0x14005496b  mov     r9b, 0Fh
0x14005496e  mov     [rsp+60h+var_38], r13d
0x140054973  mov     rdx, rsi
0x140054976  mov     dword ptr [rsp+60h+Irp], r13d
0x14005497b  call    InterpretSenseInfoWithoutHistory
0x140054980  cmp     dword ptr [r12+1Ch], 2
0x140054986  jnz     short loc_14005499B
0x140054988  cmp     byte ptr [rbx+7Bh], 0Eh
0x14005498c  jnz     short loc_14005499B
0x14005498e  inc     r15d
0x140054991  cmp     r15d, 4
0x140054995  jnb     loc_140054BF2
0x14005499b  cmp     [rbp+arg_18], 0C000003Ch
0x1400549a2  jnz     short loc_1400549A8
0x1400549a4  mov     [rbp+arg_18], r13d
0x1400549a8  mov     eax, [rbp+arg_18]
0x1400549ab  cmp     eax, 0C0000010h
0x1400549b0  jz      loc_140054C70
0x1400549b6  cmp     eax, 102h
0x1400549bb  jz      loc_140054C70
0x1400549c1  cmp     eax, 0C0000185h
0x1400549c6  jz      loc_140054C70
0x1400549cc  cmp     eax, 0C00000B5h
0x1400549d1  jz      loc_140054C70
0x1400549d7  test    eax, eax
0x1400549d9  js      loc_140054C3B
0x1400549df  mov     rsi, [rbx+50h]
0x1400549e3  test    r14d, r14d
0x1400549e6  jnz     loc_140054BCD
0x1400549ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400549f3  lea     rdx, WPP_GLOBAL_Control
0x1400549fa  cmp     rcx, rdx
0x1400549fd  jz      short loc_140054A35
0x1400549ff  test    dword ptr [rcx+2Ch], 1000h
0x140054a06  jz      short loc_140054A35
0x140054a08  cmp     byte ptr [rcx+29h], 4
0x140054a0c  jb      short loc_140054A35
0x140054a0e  movzx   eax, byte ptr [rsi+3]
0x140054a12  lea     edx, [r14+3Bh]
0x140054a16  mov     r9, [rdi+8]
0x140054a1a  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054a21  mov     rcx, [rcx+18h]
0x140054a25  mov     dword ptr [rsp+60h+Irp], eax
0x140054a29  call    WPP_SF_qD
0x140054a2e  lea     rdx, WPP_GLOBAL_Control
0x140054a35  test    byte ptr [rsi+3], 10h
0x140054a39  jz      short loc_140054A6B
0x140054a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054a42  cmp     rcx, rdx
0x140054a45  jz      short loc_140054A6B
0x140054a47  test    dword ptr [rcx+2Ch], 1000h
0x140054a4e  jz      short loc_140054A6B
0x140054a50  cmp     byte ptr [rcx+29h], 4
0x140054a54  jb      short loc_140054A6B
0x140054a56  mov     rcx, [rcx+18h]
0x140054a5a  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054a61  mov     edx, 3Ch ; '<'
0x140054a66  call    WPP_SF_
0x140054a6b  test    byte ptr [rsi+3], 40h
0x140054a6f  jz      short loc_140054AA8
0x140054a71  mov     rcx, cs:WPP_GLOBAL_Control
0x140054a78  lea     rdx, WPP_GLOBAL_Control
0x140054a7f  cmp     rcx, rdx
0x140054a82  jz      short loc_140054AAF
0x140054a84  test    dword ptr [rcx+2Ch], 1000h
0x140054a8b  jz      short loc_140054AAF
0x140054a8d  cmp     byte ptr [rcx+29h], 4
0x140054a91  jb      short loc_140054AAF
0x140054a93  mov     rcx, [rcx+18h]
0x140054a97  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054a9e  mov     edx, 3Dh ; '='
0x140054aa3  call    WPP_SF_
0x140054aa8  lea     rdx, WPP_GLOBAL_Control
0x140054aaf  test    byte ptr [rsi+3], 2
0x140054ab3  jz      short loc_140054B2B
0x140054ab5  mov     rax, [rdi+478h]
0x140054abc  test    byte ptr [rax+528h], 10h
0x140054ac3  jz      short loc_140054AFB
0x140054ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140054acc  cmp     rcx, rdx
0x140054acf  jz      short loc_140054AF5
0x140054ad1  test    dword ptr [rcx+2Ch], 1000h
0x140054ad8  jz      short loc_140054AF5
0x140054ada  cmp     byte ptr [rcx+29h], 4
0x140054ade  jb      short loc_140054AF5
0x140054ae0  mov     rcx, [rcx+18h]
0x140054ae4  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054aeb  mov     edx, 3Eh ; '>'
0x140054af0  call    WPP_SF_
0x140054af5  and     byte ptr [rsi+3], 0FDh
0x140054af9  jmp     short loc_140054B2B
0x140054afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b02  cmp     rcx, rdx
0x140054b05  jz      short loc_140054B2B
0x140054b07  test    dword ptr [rcx+2Ch], 1000h
0x140054b0e  jz      short loc_140054B2B
0x140054b10  cmp     byte ptr [rcx+29h], 4
0x140054b14  jb      short loc_140054B2B
0x140054b16  mov     rcx, [rcx+18h]
0x140054b1a  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054b21  mov     edx, 3Fh ; '?'
0x140054b26  call    WPP_SF_
0x140054b2b  mov     cl, [rsi+3]
0x140054b2e  and     cl, 5Ah
0x140054b31  mov     [rbx+4Ah], cl
0x140054b34  jz      loc_140054BFE
0x140054b3a  mov     edx, r13d
0x140054b3d  lea     eax, [rcx-1]
0x140054b40  inc     edx
0x140054b42  and     cl, al
0x140054b44  jnz     short loc_140054B3D
0x140054b46  cmp     edx, 1
0x140054b49  jnz     short loc_140054B8C
0x140054b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b52  lea     rax, WPP_GLOBAL_Control
0x140054b59  cmp     rcx, rax
0x140054b5c  jz      loc_140054BE7
0x140054b62  test    dword ptr [rcx+2Ch], 1000h
0x140054b69  jz      short loc_140054BE7
0x140054b6b  cmp     byte ptr [rcx+29h], 4
0x140054b6f  jb      short loc_140054BE7
0x140054b71  mov     r9, [rdi+8]
0x140054b75  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054b7c  mov     rcx, [rcx+18h]
0x140054b80  mov     edx, 41h ; 'A'
0x140054b85  call    WPP_SF_q
0x140054b8a  jmp     short loc_140054BE7
0x140054b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b93  lea     rax, WPP_GLOBAL_Control
0x140054b9a  cmp     rcx, rax
0x140054b9d  jz      short loc_140054BC7
0x140054b9f  test    dword ptr [rcx+2Ch], 1000h
0x140054ba6  jz      short loc_140054BC7
0x140054ba8  cmp     byte ptr [rcx+29h], 4
0x140054bac  jb      short loc_140054BC7
0x140054bae  mov     r9, [rdi+8]
0x140054bb2  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140054bb9  mov     rcx, [rcx+18h]
0x140054bbd  mov     edx, 42h ; 'B'
0x140054bc2  call    WPP_SF_q
0x140054bc7  mov     byte ptr [rbx+49h], 1
0x140054bcb  jmp     short loc_140054BE7
0x140054bcd  lea     r8, [rbp+arg_10]
0x140054bd1  mov     rdx, rsi
0x140054bd4  mov     rcx, rdi; FdoExtension
0x140054bd7  call    ClasspInterpretGesnData
0x140054bdc  mov     [rbp+arg_18], eax
0x140054bdf  test    eax, eax
0x140054be1  js      loc_140054D93
0x140054be7  mov     al, [rbp+arg_10]
0x140054bea  inc     r14d
0x140054bed  jmp     loc_1400548A2
0x140054bf2  mov     [rbp+arg_18], 0C0000185h
0x140054bf9  jmp     loc_140054DAF
0x140054bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140054c05  lea     rax, WPP_GLOBAL_Control
0x140054c0c  cmp     rcx, rax
0x140054c0f  jz      loc_140054DF1
0x140054c15  test    dword ptr [rcx+2Ch], 1000h
0x140054c1c  jz      loc_140054DAF
0x140054c22  cmp     byte ptr [rcx+29h], 4
0x140054c26  jb      loc_140054DAF
0x140054c2c  movzx   r9d, byte ptr [rsi+3]
0x140054c31  mov     edx, 40h ; '@'
0x140054c36  jmp     loc_140054CC3
0x140054c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054c42  lea     rax, WPP_GLOBAL_Control
0x140054c49  cmp     rcx, rax
0x140054c4c  jz      loc_140054DF1
0x140054c52  test    dword ptr [rcx+2Ch], 1000h
0x140054c59  jz      loc_140054DAF
0x140054c5f  cmp     byte ptr [rcx+29h], 3
0x140054c63  jb      loc_140054DAF
0x140054c69  mov     edx, 3Ah ; ':'
0x140054c6e  jmp     short loc_140054CBF
0x140054c70  mov     r9d, 1; ParameterValue
0x140054c76  lea     r8, aMmcdetectionst; "MMCDetectionState"
0x140054c7d  lea     rdx, SubkeyName; "Classpnp"
0x140054c84  mov     rcx, rdi; FdoExtension
0x140054c87  call    ClassSetDeviceParameter
0x140054c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140054c93  lea     rax, WPP_GLOBAL_Control
0x140054c9a  cmp     rcx, rax
0x140054c9d  jz      loc_140054DF1
0x140054ca3  test    dword ptr [rcx+2Ch], 1000h
0x140054caa  jz      loc_140054DAF
  ... truncated ...
```
