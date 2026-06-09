# CKsDevice::DispatchPower(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180047030`
- end: `0x180047582`
- name: `?DispatchPower@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1362`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800481d0`

## callees

- `0x18000b7bc`
- `0x18000c4c8`
- `0x18000c630`
- `0x180019c60`
- `0x1800332f4`
- `0x180047030`
- `0x180047588`
- `0x18004793c`
- `0x180047d80`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x1800472a5`
- `ntoskrnl!PoCallDriver` at `0x180047530`
- `ntoskrnl!PoCallDriver` at `0x1800472a5`
- `ntoskrnl!PoCallDriver` at `0x180047530`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047286`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047380`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047450`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047286`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047380`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047450`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800470cd`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800470cd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180047187`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180047187`
- `ntoskrnl!IofCompleteRequest` at `0x180047230`
- `ntoskrnl!IofCompleteRequest` at `0x180047230`

## pseudocode

```c
__int64 __fastcall CKsDevice::DispatchPower(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  PIRP v2; // rbx
  int v3; // ebp
  __int64 Notification; // rax
  int v6; // edx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // r15
  int v9; // edx
  unsigned int v10; // edi
  __int64 v11; // r14
  volatile signed __int32 *v12; // rdi
  int v13; // edx
  int v14; // eax
  int v15; // edx
  PDEVICE_OBJECT v17; // rcx
  NTSTATUS PowerIrp; // eax
  int v19; // r9d
  ULONG Options; // ecx
  int v21; // eax
  int v22; // edx
  struct _IO_STACK_LOCATION *v23; // rax
  struct _IO_STACK_LOCATION *v24; // rax
  int v25; // [rsp+80h] [rbp+8h] BYREF

  v2 = Irp;
  v3 = 1;
  v25 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      1,
      109,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  Notification = KspGetNotification();
  if ( Notification )
    (*(void (__fastcall **)(__int64, PIRP))(*(_QWORD *)Notification + 64LL))(Notification, v2);
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  if ( *(_DWORD *)a1->DeviceExtension == 1146114891 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        110,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v10 = -1073741637;
    if ( CurrentStackLocation->MinorFunction == 2 || CurrentStackLocation->MinorFunction == 3 )
    {
      Options = CurrentStackLocation->Parameters.Create.Options;
      if ( Options )
      {
        if ( Options == 1 )
        {
          v21 = 0;
          if ( (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart >= 5 )
            v21 = -1073741637;
          v10 = v21;
        }
      }
      else if ( (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart < 7 )
      {
        v10 = 0;
      }
    }
    PoStartNextPowerIrp(v2);
    goto LABEL_25;
  }
  DeviceHeader = CKsDevice::GetDeviceHeaderEx(a1);
  v10 = IoAcquireRemoveLockEx(&DeviceHeader->RemoveLock, v2, File, 1u, 0x20u);
  if ( v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        111,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
        v10);
    }
LABEL_25:
    v2->IoStatus.Status = v10;
    IofCompleteRequest(v2, 0);
    return v10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      112,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  v11 = *(_QWORD *)(*(_QWORD *)a1->DeviceExtension + 360LL);
  v12 = (volatile signed __int32 *)(v11 - 200);
  if ( CurrentStackLocation->MinorFunction )
  {
    v13 = CurrentStackLocation->MinorFunction - 2;
    if ( CurrentStackLocation->MinorFunction == 2 )
    {
      if ( CurrentStackLocation->Parameters.Create.Options )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v13) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            116,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        v14 = CKsDevice::DispatchDeviceSetPowerIrp((CKsDevice *)(v11 - 200), v2, &v25);
        v3 = v25;
        v10 = v14;
        goto LABEL_16;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_30;
      v17 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_30;
      v19 = 115;
    }
    else
    {
      if ( CurrentStackLocation->MinorFunction != 3 )
      {
        PoStartNextPowerIrp(v2);
        ++v2->CurrentLocation;
        ++v2->Tail.Overlay.CurrentStackLocation;
        PowerIrp = PoCallDriver(*(PDEVICE_OBJECT *)(v11 + 40), v2);
        goto LABEL_31;
      }
      if ( CurrentStackLocation->Parameters.Create.Options )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v13) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            114,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        PowerIrp = CKsDevice::DispatchDeviceQueryPowerIrp((CKsDevice *)(v11 - 200), v2);
        goto LABEL_31;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (v17 = WPP_GLOBAL_Control, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
LABEL_30:
        PowerIrp = CKsDevice::DispatchSystemPowerIrp((CKsDevice *)(v11 - 200), v2);
LABEL_31:
        v10 = PowerIrp;
        goto LABEL_17;
      }
      v19 = 113;
    }
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_(v17->DeviceExtension, v13, 1, v19, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    goto LABEL_30;
  }
  PoStartNextPowerIrp(v2);
  v23 = v2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v23[-1].MajorFunction = *(_OWORD *)&v23->MajorFunction;
  *(_OWORD *)&v23[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v23->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v23[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v23->Parameters.SetQuota + 6);
  v23[-1].FileObject = v23->FileObject;
  v23[-1].Control = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v22) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      1,
      117,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  if ( _InterlockedCompareExchange(v12 + 245, 0, 0) )
  {
    v24 = v2->Tail.Overlay.CurrentStackLocation;
    v3 = 0;
    v24[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKsDevice::WaitWakeCompletion;
    v24[-1].Context = (PVOID)v12;
    v24[-1].Control = -32;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v22) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v22,
          1,
          118,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
  }
  v10 = PoCallDriver(*(PDEVICE_OBJECT *)(v11 + 40), v2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v15) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      1,
      119,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
LABEL_16:
  if ( v3 )
LABEL_17:
    IoReleaseRemoveLockEx(&DeviceHeader->RemoveLock, v2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v15) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      1,
      120,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180047030  mov     rax, rsp
0x180047033  push    rbx
0x180047034  push    rbp
0x180047035  push    rsi
0x180047036  push    rdi
0x180047037  push    r12
0x180047039  push    r13
0x18004703b  push    r14
0x18004703d  push    r15
0x18004703f  sub     rsp, 38h
0x180047043  mov     r13d, 1
0x180047049  mov     rbx, rdx
0x18004704c  mov     ebp, r13d
0x18004704f  mov     [rax+8], r13d
0x180047053  mov     r14, rcx
0x180047056  lea     rdi, WPP_RECORDER_INITIALIZED
0x18004705d  xor     r12d, r12d
0x180047060  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180047067  lea     r15, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18004706e  jnz     loc_1800471B0
0x180047074  call    KspGetNotification
0x180047079  mov     r8, rax
0x18004707c  test    rax, rax
0x18004707f  jz      short loc_180047093
0x180047081  mov     rcx, [rax]
0x180047084  mov     rdx, rbx
0x180047087  mov     rax, [rcx+40h]
0x18004708b  mov     rcx, r8
0x18004708e  call    _guard_dispatch_icall
0x180047093  mov     rax, [r14+40h]
0x180047097  mov     rsi, [rbx+0B8h]
0x18004709e  cmp     dword ptr [rax], 4450534Bh
0x1800470a4  jz      loc_18004731A
0x1800470aa  mov     rcx, r14; struct _DEVICE_OBJECT *
0x1800470ad  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x1800470b2  mov     rcx, rax; RemoveLock
0x1800470b5  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1800470bd  mov     r9d, r13d; Line
0x1800470c0  lea     r8, File; File
0x1800470c7  mov     rdx, rbx; Tag
0x1800470ca  mov     r15, rax
0x1800470cd  call    cs:__imp_IoAcquireRemoveLockEx
0x1800470d4  nop     dword ptr [rax+rax+00h]
0x1800470d9  mov     edi, eax
0x1800470db  test    eax, eax
0x1800470dd  jnz     loc_180047214
0x1800470e3  lea     r8, WPP_RECORDER_INITIALIZED
0x1800470ea  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1800470f1  jz      short loc_180047105
0x1800470f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470fa  cmp     [rcx+48h], r12w
0x1800470ff  jnz     loc_1800473CC
0x180047105  mov     rax, [r14+40h]
0x180047109  movzx   edx, byte ptr [rsi+1]
0x18004710d  mov     rcx, [rax]
0x180047110  mov     r14, [rcx+168h]
0x180047117  lea     rdi, [r14-0C8h]
0x18004711e  test    edx, edx
0x180047120  jz      loc_18004744D
0x180047126  sub     edx, 2
0x180047129  jnz     loc_180047241
0x18004712f  cmp     [rsi+10h], r12d
0x180047133  jz      loc_1800472B3
0x180047139  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x180047140  jz      short loc_180047154
0x180047142  mov     rcx, cs:WPP_GLOBAL_Control
0x180047149  cmp     [rcx+48h], r12w
0x18004714e  jnz     loc_180047428
0x180047154  lea     r8, [rsp+78h+arg_0]; int *
0x18004715c  mov     rdx, rbx; struct _IRP *
0x18004715f  mov     rcx, rdi; this
0x180047162  call    ?DispatchDeviceSetPowerIrp@CKsDevice@@AEAAJPEAU_IRP@@PEAH@Z; CKsDevice::DispatchDeviceSetPowerIrp(_IRP *,int *)
0x180047167  mov     ebp, [rsp+78h+arg_0]
0x18004716e  lea     rsi, WPP_RECORDER_INITIALIZED
0x180047175  mov     edi, eax
0x180047177  test    ebp, ebp
0x180047179  jz      short loc_180047193
0x18004717b  mov     r8d, 20h ; ' '; RemlockSize
0x180047181  mov     rdx, rbx; Tag
0x180047184  mov     rcx, r15; RemoveLock
0x180047187  call    cs:__imp_IoReleaseRemoveLockEx
0x18004718e  nop     dword ptr [rax+rax+00h]
0x180047193  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18004719a  jnz     short loc_1800471E0
0x18004719c  mov     eax, edi
0x18004719e  add     rsp, 38h
0x1800471a2  pop     r15
0x1800471a4  pop     r14
0x1800471a6  pop     r13
0x1800471a8  pop     r12
0x1800471aa  pop     rdi
0x1800471ab  pop     rsi
0x1800471ac  pop     rbp
0x1800471ad  pop     rbx
0x1800471ae  retn
0x1800471b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471b7  cmp     [rcx+48h], r12w
0x1800471bc  jz      loc_180047074
0x1800471c2  mov     rcx, [rcx+40h]
0x1800471c6  mov     r9d, 6Dh ; 'm'
0x1800471cc  mov     r8d, r13d
0x1800471cf  mov     qword ptr [rsp+78h+RemlockSize], r15
0x1800471d4  mov     dl, 5
0x1800471d6  call    WPP_RECORDER_SF_
0x1800471db  jmp     loc_180047074
0x1800471e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471e7  cmp     [rcx+48h], r12w
0x1800471ec  jz      short loc_18004719C
0x1800471ee  mov     rcx, [rcx+40h]
0x1800471f2  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800471f9  mov     r9d, 78h ; 'x'
0x1800471ff  mov     [rsp+78h+var_50], edi
0x180047203  mov     r8d, r13d
0x180047206  mov     qword ptr [rsp+78h+RemlockSize], rax
0x18004720b  mov     dl, 5
0x18004720d  call    WPP_RECORDER_SF_D
0x180047212  jmp     short loc_18004719C
0x180047214  lea     rsi, WPP_RECORDER_INITIALIZED
0x18004721b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180047222  jnz     loc_180047391
0x180047228  xor     edx, edx; PriorityBoost
0x18004722a  mov     [rbx+30h], edi
0x18004722d  mov     rcx, rbx; Irp
0x180047230  call    cs:__imp_IofCompleteRequest
0x180047237  nop     dword ptr [rax+rax+00h]
0x18004723c  jmp     loc_18004719C
0x180047241  cmp     edx, ebp
0x180047243  jnz     short loc_180047283
0x180047245  cmp     [rsi+10h], r12d
0x180047249  jnz     loc_1800472EF
0x18004724f  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x180047256  jz      short loc_18004726A
0x180047258  mov     rcx, cs:WPP_GLOBAL_Control
0x18004725f  cmp     [rcx+48h], r12w
0x180047264  jnz     loc_1800473F8
0x18004726a  mov     rdx, rbx; Irp
0x18004726d  mov     rcx, rdi; this
0x180047270  call    ?DispatchSystemPowerIrp@CKsDevice@@AEAAJPEAU_IRP@@@Z; CKsDevice::DispatchSystemPowerIrp(_IRP *)
0x180047275  mov     edi, eax
0x180047277  lea     rsi, WPP_RECORDER_INITIALIZED
0x18004727e  jmp     loc_18004717B
0x180047283  mov     rcx, rbx; Irp
0x180047286  call    cs:__imp_PoStartNextPowerIrp
0x18004728d  nop     dword ptr [rax+rax+00h]
0x180047292  add     [rbx+43h], r13b
0x180047296  mov     rdx, rbx; Irp
0x180047299  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x1800472a1  mov     rcx, [r14+28h]; DeviceObject
0x1800472a5  call    cs:__imp_PoCallDriver
0x1800472ac  nop     dword ptr [rax+rax+00h]
0x1800472b1  jmp     short loc_180047275
0x1800472b3  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1800472ba  jz      short loc_18004726A
0x1800472bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472c3  cmp     [rcx+48h], r12w
0x1800472c8  jz      short loc_18004726A
0x1800472ca  mov     r9d, 73h ; 's'
0x1800472d0  mov     rcx, [rcx+40h]
0x1800472d4  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800472db  mov     r8d, r13d
0x1800472de  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1800472e3  mov     dl, 5
0x1800472e5  call    WPP_RECORDER_SF_
0x1800472ea  jmp     loc_18004726A
0x1800472ef  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1800472f6  jz      short loc_18004730A
0x1800472f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472ff  cmp     [rcx+48h], r12w
0x180047304  jnz     loc_180047403
0x18004730a  mov     rdx, rbx; struct _IRP *
0x18004730d  mov     rcx, rdi; this
0x180047310  call    ?DispatchDeviceQueryPowerIrp@CKsDevice@@AEAAJPEAU_IRP@@@Z; CKsDevice::DispatchDeviceQueryPowerIrp(_IRP *)
0x180047315  jmp     loc_180047275
0x18004731a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180047321  jz      short loc_18004734A
0x180047323  mov     rcx, cs:WPP_GLOBAL_Control
0x18004732a  cmp     [rcx+48h], r12w
0x18004732f  jz      short loc_18004734A
0x180047331  mov     rcx, [rcx+40h]
0x180047335  mov     r9d, 6Eh ; 'n'
0x18004733b  mov     r8d, r13d
0x18004733e  mov     qword ptr [rsp+78h+RemlockSize], r15
0x180047343  mov     dl, 5
0x180047345  call    WPP_RECORDER_SF_
0x18004734a  movzx   ecx, byte ptr [rsi+1]
0x18004734e  mov     edi, 0C00000BBh
0x180047353  sub     ecx, 2
0x180047356  jz      short loc_18004735C
0x180047358  cmp     ecx, ebp
0x18004735a  jnz     short loc_18004737D
0x18004735c  mov     ecx, [rsi+10h]
0x18004735f  test    ecx, ecx
0x180047361  jz      short loc_180047375
0x180047363  cmp     ecx, ebp
0x180047365  jnz     short loc_18004737D
0x180047367  cmp     dword ptr [rsi+18h], 5
0x18004736b  mov     eax, r12d
0x18004736e  cmovge  eax, edi
0x180047371  mov     edi, eax
0x180047373  jmp     short loc_18004737D
0x180047375  cmp     dword ptr [rsi+18h], 7
0x180047379  cmovl   edi, r12d
0x18004737d  mov     rcx, rbx; Irp
0x180047380  call    cs:__imp_PoStartNextPowerIrp
0x180047387  nop     dword ptr [rax+rax+00h]
0x18004738c  jmp     loc_180047228
0x180047391  mov     rcx, cs:WPP_GLOBAL_Control
0x180047398  cmp     [rcx+48h], r12w
0x18004739d  jz      loc_180047228
0x1800473a3  mov     rcx, [rcx+40h]
0x1800473a7  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800473ae  mov     r9d, 6Fh ; 'o'
0x1800473b4  mov     [rsp+78h+var_50], edi
0x1800473b8  mov     r8d, r13d
0x1800473bb  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1800473c0  mov     dl, 5
0x1800473c2  call    WPP_RECORDER_SF_D
0x1800473c7  jmp     loc_180047228
0x1800473cc  mov     rcx, [rcx+40h]
0x1800473d0  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800473d7  mov     r9d, 70h ; 'p'
0x1800473dd  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1800473e2  mov     r8d, r13d
0x1800473e5  mov     dl, 5
0x1800473e7  call    WPP_RECORDER_SF_
0x1800473ec  lea     r8, WPP_RECORDER_INITIALIZED
0x1800473f3  jmp     loc_180047105
0x1800473f8  mov     r9d, 71h ; 'q'
0x1800473fe  jmp     loc_1800472D0
0x180047403  mov     rcx, [rcx+40h]
0x180047407  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18004740e  mov     r9d, 72h ; 'r'
0x180047414  mov     qword ptr [rsp+78h+RemlockSize], rax
0x180047419  mov     r8d, r13d
0x18004741c  mov     dl, 5
0x18004741e  call    WPP_RECORDER_SF_
0x180047423  jmp     loc_18004730A
0x180047428  mov     rcx, [rcx+40h]
0x18004742c  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180047433  mov     r9d, 74h ; 't'
0x180047439  mov     qword ptr [rsp+78h+RemlockSize], rax
0x18004743e  mov     r8d, r13d
0x180047441  mov     dl, 5
0x180047443  call    WPP_RECORDER_SF_
0x180047448  jmp     loc_180047154
0x18004744d  mov     rcx, rbx; Irp
0x180047450  call    cs:__imp_PoStartNextPowerIrp
0x180047457  nop     dword ptr [rax+rax+00h]
0x18004745c  mov     rax, [rbx+0B8h]
0x180047463  movups  xmm0, xmmword ptr [rax]
0x180047466  movups  xmmword ptr [rax-48h], xmm0
0x18004746a  movups  xmm1, xmmword ptr [rax+10h]
0x18004746e  movups  xmmword ptr [rax-38h], xmm1
0x180047472  movups  xmm0, xmmword ptr [rax+20h]
0x180047476  movups  xmmword ptr [rax-28h], xmm0
0x18004747a  movsd   xmm1, qword ptr [rax+30h]
0x18004747f  movsd   qword ptr [rax-18h], xmm1
0x180047484  mov     [rax-45h], r12b
0x180047488  lea     rsi, WPP_RECORDER_INITIALIZED
0x18004748f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180047496  jz      short loc_1800474C6
0x180047498  mov     rcx, cs:WPP_GLOBAL_Control
0x18004749f  cmp     [rcx+48h], r12w
0x1800474a4  jz      short loc_1800474C6
0x1800474a6  mov     rcx, [rcx+40h]
0x1800474aa  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800474b1  mov     r9d, 75h ; 'u'
0x1800474b7  mov     qword ptr [rsp+78h+RemlockSize], rax
0x1800474bc  mov     r8d, r13d
0x1800474bf  mov     dl, 5
0x1800474c1  call    WPP_RECORDER_SF_
0x1800474c6  mov     ecx, r12d
0x1800474c9  xor     eax, eax
0x1800474cb  lock cmpxchg [rdi+3D4h], ecx
0x1800474d3  jz      short loc_180047529
0x1800474d5  mov     rax, [rbx+0B8h]
0x1800474dc  lea     rcx, ?WaitWakeCompletion@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z; CKsDevice::WaitWakeCompletion(_DEVICE_OBJECT *,_IRP *,CKsDevice *)
0x1800474e3  mov     ebp, r12d
0x1800474e6  mov     [rax-10h], rcx
0x1800474ea  mov     [rax-8], rdi
0x1800474ee  mov     byte ptr [rax-45h], 0E0h
0x1800474f2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800474f9  jz      short loc_180047529
0x1800474fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180047502  cmp     [rcx+48h], r12w
0x180047507  jz      short loc_180047529
0x180047509  mov     rcx, [rcx+40h]
0x18004750d  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180047514  mov     r9d, 76h ; 'v'
0x18004751a  mov     qword ptr [rsp+78h+RemlockSize], rax
0x18004751f  mov     r8d, r13d
0x180047522  mov     dl, 5
0x180047524  call    WPP_RECORDER_SF_
0x180047529  mov     rcx, [r14+28h]; DeviceObject
0x18004752d  mov     rdx, rbx; Irp
0x180047530  call    cs:__imp_PoCallDriver
0x180047537  nop     dword ptr [rax+rax+00h]
0x18004753c  mov     edi, eax
0x18004753e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180047545  jz      loc_180047177
  ... truncated ...
```
