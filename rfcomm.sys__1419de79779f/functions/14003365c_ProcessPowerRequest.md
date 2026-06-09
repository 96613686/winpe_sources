# ProcessPowerRequest

- ea: `0x14003365c`
- end: `0x140033a69`
- name: `ProcessPowerRequest`
- size: `1037`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000256c`

## callees

- `0x140004a68`
- `0x140004b4c`
- `0x14003365c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400336c2`
- `ntoskrnl!IofCompleteRequest` at `0x14003394d`
- `ntoskrnl!IofCompleteRequest` at `0x140033a01`
- `ntoskrnl!IofCompleteRequest` at `0x1400336c2`
- `ntoskrnl!IofCompleteRequest` at `0x14003394d`
- `ntoskrnl!IofCompleteRequest` at `0x140033a01`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14003392a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140033962`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140033a4d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14003392a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140033962`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140033a4d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140033691`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14003379a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140033884`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14003398d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140033691`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14003379a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140033884`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14003398d`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400336a6`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140033939`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400339f0`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140033a18`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400336a6`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140033939`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400339f0`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140033a18`
- `ntoskrnl!PoSetPowerState` at `0x140033725`
- `ntoskrnl!PoSetPowerState` at `0x140033725`
- `ntoskrnl!PoCallDriver` at `0x140033851`
- `ntoskrnl!PoCallDriver` at `0x140033a36`
- `ntoskrnl!PoCallDriver` at `0x140033851`
- `ntoskrnl!PoCallDriver` at `0x140033a36`
- `ntoskrnl!PoRequestPowerIrp` at `0x14003390b`
- `ntoskrnl!PoRequestPowerIrp` at `0x14003390b`

## string_xrefs

- `0x14003366d`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\power.c`

## pseudocode

```c
__int64 __fastcall ProcessPowerRequest(__int64 a1, IRP *a2)
{
  __int64 v2; // rbp
  NTSTATUS v4; // ebx
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int Options; // r8d
  int Status; // ecx
  POWER_STATE v9; // ebx
  int v10; // edx
  int v11; // edx
  NTSTATUS v12; // esi
  int (__fastcall *v13)(_DEVICE_OBJECT *, _IRP *, void *); // rcx
  _IO_STACK_LOCATION *v14; // rax
  _IO_STACK_LOCATION *v15; // rax
  int v16; // edx
  NTSTATUS v17; // ebx
  int v18; // edx

  v2 = *(_QWORD *)(a1 + 64);
  v4 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(v2 + 40),
         a2,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\power.c",
         0x66u,
         0x20u);
  if ( v4 < 0 )
  {
    PoStartNextPowerIrp(a2);
    a2->IoStatus.Status = v4;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    return (unsigned int)v4;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !CurrentStackLocation->MinorFunction || CurrentStackLocation->MinorFunction != 2 )
  {
    Status = a2->IoStatus.Status;
    goto LABEL_31;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  Status = 0;
  v9.SystemState = (_SYSTEM_POWER_STATE)CurrentStackLocation->Parameters.Power.State;
  if ( !Options )
  {
    if ( *(_DWORD *)(v2 + 108) >= v9.SystemState )
    {
      if ( *(_DWORD *)(v2 + 108) <= v9.SystemState )
        goto LABEL_31;
      v12 = IoAcquireRemoveLockEx(
              (PIO_REMOVE_LOCK)(v2 + 40),
              a2,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\power.c",
              0x118u,
              0x20u);
      if ( v12 >= 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            3,
            13,
            (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
            *(_QWORD *)(v2 + 80));
        v13 = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&SystemPowerUpComplete;
        goto LABEL_16;
      }
    }
    else
    {
      v12 = IoAcquireRemoveLockEx(
              (PIO_REMOVE_LOCK)(v2 + 40),
              a2,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\power.c",
              0xD3u,
              0x20u);
      if ( v12 >= 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            3,
            12,
            (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
            *(_QWORD *)(v2 + 80),
            LOBYTE(v9.SystemState) - 1);
        a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        v17 = PoRequestPowerIrp(*(PDEVICE_OBJECT *)(v2 + 80), 2u, (POWER_STATE)4, DevicePowerDownRequestComplete, a2, 0);
        if ( v17 < 0 )
        {
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 40), a2, 0x20u);
          PoStartNextPowerIrp(a2);
          a2->IoStatus.Status = v17;
          IofCompleteRequest(a2, 0);
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 40), a2, 0x20u);
        }
        goto LABEL_17;
      }
    }
LABEL_29:
    a2->IoStatus.Status = v12;
    PoStartNextPowerIrp(a2);
    IofCompleteRequest(a2, 0);
    goto LABEL_32;
  }
  if ( Options != 1 )
    goto LABEL_31;
  if ( *(_DWORD *)(v2 + 104) < v9.SystemState )
  {
    PoSetPowerState(*(PDEVICE_OBJECT *)(v2 + 80), DevicePowerState, v9);
    *(POWER_STATE *)(v2 + 104) = v9;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        10,
        (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
        *(_QWORD *)(v2 + 80),
        LOBYTE(v9.SystemState) - 1);
    Status = 0;
    goto LABEL_31;
  }
  if ( *(_DWORD *)(v2 + 104) <= v9.SystemState )
  {
LABEL_31:
    a2->IoStatus.Status = Status;
    PoStartNextPowerIrp(a2);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v12 = PoCallDriver(*(PDEVICE_OBJECT *)(v2 + 88), a2);
    goto LABEL_32;
  }
  v12 = IoAcquireRemoveLockEx(
          (PIO_REMOVE_LOCK)(v2 + 40),
          a2,
          "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\power.c",
          0x96u,
          0x20u);
  if ( v12 < 0 )
    goto LABEL_29;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      3,
      11,
      (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
      *(_QWORD *)(v2 + 80),
      LOBYTE(v9.SystemState) - 1);
  v13 = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&DevicePowerUpComplete;
LABEL_16:
  v14 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v14[-1].MajorFunction = *(_OWORD *)&v14->MajorFunction;
  *(_OWORD *)&v14[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v14->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v14[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v14->Parameters.SetQuota + 6);
  v14[-1].FileObject = v14->FileObject;
  v14[-1].Control = 0;
  v15 = a2->Tail.Overlay.CurrentStackLocation;
  v15[-1].CompletionRoutine = v13;
  v15[-1].Context = 0;
  v15[-1].Control = -32;
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  PoCallDriver(*(PDEVICE_OBJECT *)(v2 + 88), a2);
LABEL_17:
  v12 = 259;
LABEL_32:
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 40), a2, 0x20u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14003365c  push    rbx
0x14003365e  push    rbp
0x14003365f  push    rsi
0x140033660  push    rdi
0x140033661  push    r12
0x140033663  push    r14
0x140033665  sub     rsp, 48h
0x140033669  mov     rbp, [rcx+40h]
0x14003366d  lea     rsi, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140033674  mov     r12d, 20h ; ' '
0x14003367a  mov     r8, rsi; File
0x14003367d  mov     rdi, rdx
0x140033680  mov     [rsp+78h+RemlockSize], r12d; RemlockSize
0x140033685  lea     r14, [rbp+28h]
0x140033689  mov     rcx, r14; RemoveLock
0x14003368c  lea     r9d, [r12+46h]; Line
0x140033691  call    cs:__imp_IoAcquireRemoveLockEx
0x140033698  nop     dword ptr [rax+rax+00h]
0x14003369d  mov     ebx, eax
0x14003369f  test    eax, eax
0x1400336a1  jns     short loc_1400336D5
0x1400336a3  mov     rcx, rdi; Irp
0x1400336a6  call    cs:__imp_PoStartNextPowerIrp
0x1400336ad  nop     dword ptr [rax+rax+00h]
0x1400336b2  xor     edx, edx; PriorityBoost
0x1400336b4  mov     [rdi+30h], ebx
0x1400336b7  mov     rcx, rdi; Irp
0x1400336ba  mov     qword ptr [rdi+38h], 0
0x1400336c2  call    cs:__imp_IofCompleteRequest
0x1400336c9  nop     dword ptr [rax+rax+00h]
0x1400336ce  mov     eax, ebx
0x1400336d0  jmp     loc_140033A5B
0x1400336d5  mov     rdx, [rdi+0B8h]
0x1400336dc  movzx   ecx, byte ptr [rdx+1]
0x1400336e0  test    ecx, ecx
0x1400336e2  jz      loc_140033A0F
0x1400336e8  sub     ecx, 1
0x1400336eb  jz      loc_140033A0F
0x1400336f1  cmp     ecx, 1
0x1400336f4  jnz     loc_140033A0F
0x1400336fa  mov     r8d, [rdx+10h]
0x1400336fe  xor     ecx, ecx
0x140033700  mov     ebx, [rdx+18h]
0x140033703  test    r8d, r8d
0x140033706  jz      loc_140033867
0x14003370c  cmp     r8d, 1
0x140033710  jnz     loc_140033A12
0x140033716  cmp     [rbp+68h], ebx
0x140033719  jge     short loc_140033780
0x14003371b  lea     edx, [rcx+1]; Type
0x14003371e  mov     r8d, ebx; State
0x140033721  mov     rcx, [rbp+50h]; DeviceObject
0x140033725  call    cs:__imp_PoSetPowerState
0x14003372c  nop     dword ptr [rax+rax+00h]
0x140033731  mov     [rbp+68h], ebx
0x140033734  lea     rax, WPP_RECORDER_INITIALIZED
0x14003373b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033742  jz      short loc_140033779
0x140033744  mov     rax, [rbp+50h]
0x140033748  dec     ebx
0x14003374a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033751  mov     r9d, 0Ah
0x140033757  mov     [rsp+78h+var_48], ebx
0x14003375b  mov     [rsp+78h+Irp], rax
0x140033760  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x140033767  mov     qword ptr [rsp+78h+RemlockSize], rax
0x14003376c  mov     rcx, [rcx+40h]
0x140033770  lea     r8d, [r9-7]
0x140033774  call    WPP_RECORDER_SF_qD
0x140033779  xor     ecx, ecx
0x14003377b  jmp     loc_140033A12
0x140033780  jle     loc_140033A12
0x140033786  mov     r9d, 96h; Line
0x14003378c  mov     [rsp+78h+RemlockSize], r12d; RemlockSize
0x140033791  mov     r8, rsi; File
0x140033794  mov     rdx, rdi; Tag
0x140033797  mov     rcx, r14; RemoveLock
0x14003379a  call    cs:__imp_IoAcquireRemoveLockEx
0x1400337a1  nop     dword ptr [rax+rax+00h]
0x1400337a6  mov     esi, eax
0x1400337a8  test    eax, eax
0x1400337aa  js      loc_1400339EA
0x1400337b0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400337b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400337be  jz      short loc_1400337F5
0x1400337c0  mov     rax, [rbp+50h]
0x1400337c4  dec     ebx
0x1400337c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400337cd  mov     r9d, 0Bh
0x1400337d3  mov     [rsp+78h+var_48], ebx
0x1400337d7  mov     [rsp+78h+Irp], rax
0x1400337dc  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x1400337e3  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1400337e8  mov     rcx, [rcx+40h]
0x1400337ec  lea     r8d, [r9-8]
0x1400337f0  call    WPP_RECORDER_SF_qD
0x1400337f5  lea     rcx, DevicePowerUpComplete
0x1400337fc  mov     rax, [rdi+0B8h]
0x140033803  mov     rdx, rdi; Irp
0x140033806  movups  xmm0, xmmword ptr [rax]
0x140033809  movups  xmmword ptr [rax-48h], xmm0
0x14003380d  movups  xmm1, xmmword ptr [rax+10h]
0x140033811  movups  xmmword ptr [rax-38h], xmm1
0x140033815  movups  xmm0, xmmword ptr [rax+20h]
0x140033819  movups  xmmword ptr [rax-28h], xmm0
0x14003381d  movsd   xmm1, qword ptr [rax+30h]
0x140033822  movsd   qword ptr [rax-18h], xmm1
0x140033827  mov     byte ptr [rax-45h], 0
0x14003382b  mov     rax, [rdi+0B8h]
0x140033832  mov     [rax-10h], rcx
0x140033836  mov     qword ptr [rax-8], 0
0x14003383e  mov     byte ptr [rax-45h], 0E0h
0x140033842  mov     rax, [rdi+0B8h]
0x140033849  or      byte ptr [rax+3], 1
0x14003384d  mov     rcx, [rbp+58h]; DeviceObject
0x140033851  call    cs:__imp_PoCallDriver
0x140033858  nop     dword ptr [rax+rax+00h]
0x14003385d  mov     esi, 103h
0x140033862  jmp     loc_140033A44
0x140033867  cmp     [rbp+6Ch], ebx
0x14003386a  jge     loc_140033973
0x140033870  mov     r9d, 0D3h; Line
0x140033876  mov     [rsp+78h+RemlockSize], r12d; RemlockSize
0x14003387b  mov     r8, rsi; File
0x14003387e  mov     rdx, rdi; Tag
0x140033881  mov     rcx, r14; RemoveLock
0x140033884  call    cs:__imp_IoAcquireRemoveLockEx
0x14003388b  nop     dword ptr [rax+rax+00h]
0x140033890  mov     esi, eax
0x140033892  test    eax, eax
0x140033894  js      loc_1400339EA
0x14003389a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400338a1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400338a8  jz      short loc_1400338DF
0x1400338aa  mov     rax, [rbp+50h]
0x1400338ae  dec     ebx
0x1400338b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400338b7  mov     r9d, 0Ch
0x1400338bd  mov     [rsp+78h+var_48], ebx
0x1400338c1  mov     [rsp+78h+Irp], rax
0x1400338c6  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x1400338cd  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1400338d2  mov     rcx, [rcx+40h]
0x1400338d6  lea     r8d, [r9-9]
0x1400338da  call    WPP_RECORDER_SF_qD
0x1400338df  mov     rax, [rdi+0B8h]
0x1400338e6  lea     r9, DevicePowerDownRequestComplete; CompletionFunction
0x1400338ed  mov     [rsp+78h+Irp], 0; Irp
0x1400338f6  mov     r8d, 4; PowerState
0x1400338fc  mov     dl, 2; MinorFunction
0x1400338fe  mov     qword ptr [rsp+78h+RemlockSize], rdi; Context
0x140033903  or      byte ptr [rax+3], 1
0x140033907  mov     rcx, [rbp+50h]; DeviceObject
0x14003390b  call    cs:__imp_PoRequestPowerIrp
0x140033912  nop     dword ptr [rax+rax+00h]
0x140033917  mov     ebx, eax
0x140033919  test    eax, eax
0x14003391b  jns     loc_14003385D
0x140033921  mov     r8d, r12d; RemlockSize
0x140033924  mov     rdx, rdi; Tag
0x140033927  mov     rcx, r14; RemoveLock
0x14003392a  call    cs:__imp_IoReleaseRemoveLockEx
0x140033931  nop     dword ptr [rax+rax+00h]
0x140033936  mov     rcx, rdi; Irp
0x140033939  call    cs:__imp_PoStartNextPowerIrp
0x140033940  nop     dword ptr [rax+rax+00h]
0x140033945  xor     edx, edx; PriorityBoost
0x140033947  mov     [rdi+30h], ebx
0x14003394a  mov     rcx, rdi; Irp
0x14003394d  call    cs:__imp_IofCompleteRequest
0x140033954  nop     dword ptr [rax+rax+00h]
0x140033959  mov     r8d, r12d; RemlockSize
0x14003395c  mov     rdx, rdi; Tag
0x14003395f  mov     rcx, r14; RemoveLock
0x140033962  call    cs:__imp_IoReleaseRemoveLockEx
0x140033969  nop     dword ptr [rax+rax+00h]
0x14003396e  jmp     loc_14003385D
0x140033973  jle     loc_140033A12
0x140033979  mov     r9d, 118h; Line
0x14003397f  mov     [rsp+78h+RemlockSize], r12d; RemlockSize
0x140033984  mov     r8, rsi; File
0x140033987  mov     rdx, rdi; Tag
0x14003398a  mov     rcx, r14; RemoveLock
0x14003398d  call    cs:__imp_IoAcquireRemoveLockEx
0x140033994  nop     dword ptr [rax+rax+00h]
0x140033999  mov     esi, eax
0x14003399b  test    eax, eax
0x14003399d  js      short loc_1400339EA
0x14003399f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400339a6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400339ad  jz      short loc_1400339DE
0x1400339af  mov     rax, [rbp+50h]
0x1400339b3  mov     r9d, 0Dh
0x1400339b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400339c0  mov     [rsp+78h+Irp], rax
0x1400339c5  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x1400339cc  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1400339d1  lea     r8d, [r9-0Ah]
0x1400339d5  mov     rcx, [rcx+40h]
0x1400339d9  call    WPP_RECORDER_SF_q
0x1400339de  lea     rcx, SystemPowerUpComplete
0x1400339e5  jmp     loc_1400337FC
0x1400339ea  mov     rcx, rdi; Irp
0x1400339ed  mov     [rdi+30h], esi
0x1400339f0  call    cs:__imp_PoStartNextPowerIrp
0x1400339f7  nop     dword ptr [rax+rax+00h]
0x1400339fc  xor     edx, edx; PriorityBoost
0x1400339fe  mov     rcx, rdi; Irp
0x140033a01  call    cs:__imp_IofCompleteRequest
0x140033a08  nop     dword ptr [rax+rax+00h]
0x140033a0d  jmp     short loc_140033A44
0x140033a0f  mov     ecx, [rdi+30h]
0x140033a12  mov     [rdi+30h], ecx
0x140033a15  mov     rcx, rdi; Irp
0x140033a18  call    cs:__imp_PoStartNextPowerIrp
0x140033a1f  nop     dword ptr [rax+rax+00h]
0x140033a24  inc     byte ptr [rdi+43h]
0x140033a27  mov     rdx, rdi; Irp
0x140033a2a  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140033a32  mov     rcx, [rbp+58h]; DeviceObject
0x140033a36  call    cs:__imp_PoCallDriver
0x140033a3d  nop     dword ptr [rax+rax+00h]
0x140033a42  mov     esi, eax
0x140033a44  mov     r8d, r12d; RemlockSize
0x140033a47  mov     rdx, rdi; Tag
0x140033a4a  mov     rcx, r14; RemoveLock
0x140033a4d  call    cs:__imp_IoReleaseRemoveLockEx
0x140033a54  nop     dword ptr [rax+rax+00h]
0x140033a59  mov     eax, esi
0x140033a5b  add     rsp, 48h
0x140033a5f  pop     r14
0x140033a61  pop     r12
0x140033a63  pop     rdi
0x140033a64  pop     rsi
0x140033a65  pop     rbp
0x140033a66  pop     rbx
0x140033a67  retn
```
