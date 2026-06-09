# ClasspMpdevRemoveDevice

- ea: `0x14003b148`
- end: `0x14003b35e`
- name: `ClasspMpdevRemoveDevice`
- size: `534`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003a790`

## callees

- `0x14002249c`
- `0x140022668`
- `0x140027870`
- `0x14003b148`
- `0x14003e430`
- `0x14003e470`
- `0x140055ae0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003b310`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b310`
- `ntoskrnl!IofCallDriver` at `0x14003b2f6`
- `ntoskrnl!IofCallDriver` at `0x14003b2f6`
- `ntoskrnl!IoDetachDevice` at `0x14003b323`
- `ntoskrnl!IoDetachDevice` at `0x14003b323`
- `ntoskrnl!IoDeleteDevice` at `0x14003b332`
- `ntoskrnl!IoDeleteDevice` at `0x14003b332`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003b2a4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003b2a4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003b17e`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003b17e`

## pseudocode

```c
__int64 __fastcall ClasspMpdevRemoveDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  void *DeviceExtension; // rbx
  volatile signed __int32 *DriverObjectExtension; // rax
  NTSTATUS v6; // eax
  __int64 v7; // r8
  bool v8; // zf
  void (__fastcall *v9)(_QWORD, PDEVICE_OBJECT, __int64); // rax
  int v10; // ecx
  NTSTATUS v11; // eax
  void *v12; // rcx
  unsigned int v13; // edi
  __int128 v15; // [rsp+30h] [rbp-28h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  DriverObjectExtension = (volatile signed __int32 *)IoGetDriverObjectExtension(
                                                       *((PDRIVER_OBJECT *)DeviceExtension + 64),
                                                       ClassInitialize);
  if ( *((_BYTE *)DeviceExtension + 580) != 1 )
    _InterlockedDecrement(DriverObjectExtension + 102);
  v6 = ClassClaimDevice(DeviceObject, 1u);
  v7 = (unsigned int)v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
        DeviceObject,
        *((_QWORD *)DeviceExtension + 65),
        v6);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
      DeviceObject,
      *((_QWORD *)DeviceExtension + 65));
  }
  Irp->IoStatus.Status = 0;
  v8 = *((_BYTE *)DeviceExtension + 583) == 0;
  *((_BYTE *)DeviceExtension + 581) = *((_BYTE *)DeviceExtension + 580);
  *((_BYTE *)DeviceExtension + 580) = 2;
  *((_BYTE *)DeviceExtension + 582) = 2;
  if ( !v8 )
  {
    if ( *((_DWORD *)DeviceExtension + 136) )
    {
      v9 = (void (__fastcall *)(_QWORD, PDEVICE_OBJECT, __int64))*((_QWORD *)DeviceExtension + 70);
      if ( v9 )
      {
        LOBYTE(v7) = 2;
        v9(*((_QWORD *)DeviceExtension + 67), DeviceObject, v7);
      }
    }
  }
  if ( ClassPnPETWEnabled )
  {
    v15 = 0;
    if ( (int)IoGetActivityIdIrp(Irp, &v15) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        v10,
        (unsigned int)EventPnpRequestComplete,
        (unsigned int)&v15,
        *((_DWORD *)DeviceExtension + 144),
        (char)Irp,
        Irp->IoStatus.Status);
  }
  ++Irp->CurrentLocation;
  ++Irp->Tail.Overlay.CurrentStackLocation;
  v11 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 65), Irp);
  v12 = (void *)*((_QWORD *)DeviceExtension + 71);
  v13 = v11;
  if ( v12 )
    ObfDereferenceObject(v12);
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 65));
  IoDeleteDevice(DeviceObject);
  return v13;
}

```

## disassembly

```asm
0x14003b148  mov     [rsp+arg_10], rbx
0x14003b14d  mov     [rsp+arg_18], rsi
0x14003b152  push    rdi
0x14003b153  sub     rsp, 50h
0x14003b157  mov     rax, cs:__security_cookie
0x14003b15e  xor     rax, rsp
0x14003b161  mov     [rsp+58h+var_18], rax
0x14003b166  mov     rbx, [rcx+40h]
0x14003b16a  mov     rdi, rdx
0x14003b16d  mov     rsi, rcx
0x14003b170  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14003b177  mov     rcx, [rbx+200h]; DriverObject
0x14003b17e  call    cs:__imp_IoGetDriverObjectExtension
0x14003b185  nop     dword ptr [rax+rax+00h]
0x14003b18a  cmp     byte ptr [rbx+244h], 1
0x14003b191  jz      short loc_14003B19A
0x14003b193  lock dec dword ptr [rax+198h]
0x14003b19a  mov     dl, 1; Release
0x14003b19c  mov     rcx, rsi; LowerDeviceObject
0x14003b19f  call    ClassClaimDevice
0x14003b1a4  mov     r8d, eax
0x14003b1a7  test    eax, eax
0x14003b1a9  js      short loc_14003B1F1
0x14003b1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1b2  lea     rax, WPP_GLOBAL_Control
0x14003b1b9  cmp     rcx, rax
0x14003b1bc  jz      short loc_14003B23A
0x14003b1be  mov     eax, [rcx+2Ch]
0x14003b1c1  test    al, 2
0x14003b1c3  jz      short loc_14003B23A
0x14003b1c5  cmp     byte ptr [rcx+29h], 4
0x14003b1c9  jb      short loc_14003B23A
0x14003b1cb  mov     rax, [rbx+208h]
0x14003b1d2  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003b1d9  mov     rcx, [rcx+18h]
0x14003b1dd  mov     edx, 1Ah
0x14003b1e2  mov     r9, rsi
0x14003b1e5  mov     [rsp+58h+var_38], rax
0x14003b1ea  call    WPP_SF_qq
0x14003b1ef  jmp     short loc_14003B23A
0x14003b1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b1f8  lea     rax, WPP_GLOBAL_Control
0x14003b1ff  cmp     rcx, rax
0x14003b202  jz      short loc_14003B23A
0x14003b204  mov     eax, [rcx+2Ch]
0x14003b207  test    al, 2
0x14003b209  jz      short loc_14003B23A
0x14003b20b  cmp     byte ptr [rcx+29h], 4
0x14003b20f  jb      short loc_14003B23A
0x14003b211  mov     rax, [rbx+208h]
0x14003b218  mov     edx, 1Bh
0x14003b21d  mov     rcx, [rcx+18h]
0x14003b221  mov     r9, rsi
0x14003b224  mov     [rsp+58h+var_30], r8d
0x14003b229  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003b230  mov     [rsp+58h+var_38], rax
0x14003b235  call    WPP_SF_qqD
0x14003b23a  mov     dword ptr [rdi+30h], 0
0x14003b241  cmp     byte ptr [rbx+247h], 0
0x14003b248  mov     al, [rbx+244h]
0x14003b24e  mov     [rbx+245h], al
0x14003b254  mov     byte ptr [rbx+244h], 2
0x14003b25b  mov     byte ptr [rbx+246h], 2
0x14003b262  jz      short loc_14003B28B
0x14003b264  cmp     dword ptr [rbx+220h], 0
0x14003b26b  jz      short loc_14003B28B
0x14003b26d  mov     rax, [rbx+230h]
0x14003b274  test    rax, rax
0x14003b277  jz      short loc_14003B28B
0x14003b279  mov     rcx, [rbx+218h]
0x14003b280  mov     r8b, 2
0x14003b283  mov     rdx, rsi
0x14003b286  call    _guard_dispatch_icall
0x14003b28b  cmp     cs:ClassPnPETWEnabled, 0
0x14003b292  jz      short loc_14003B2E1
0x14003b294  xorps   xmm0, xmm0
0x14003b297  lea     rdx, [rsp+58h+var_28]
0x14003b29c  mov     rcx, rdi
0x14003b29f  movups  [rsp+58h+var_28], xmm0
0x14003b2a4  call    cs:__imp_IoGetActivityIdIrp
0x14003b2ab  nop     dword ptr [rax+rax+00h]
0x14003b2b0  test    eax, eax
0x14003b2b2  js      short loc_14003B2E1
0x14003b2b4  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003b2bb  jz      short loc_14003B2E1
0x14003b2bd  mov     eax, [rdi+30h]
0x14003b2c0  lea     r8, [rsp+58h+var_28]
0x14003b2c5  mov     r9d, [rbx+240h]
0x14003b2cc  lea     rdx, EventPnpRequestComplete
0x14003b2d3  mov     [rsp+58h+var_30], eax
0x14003b2d7  mov     [rsp+58h+var_38], rdi
0x14003b2dc  call    McTemplateK0qpd_EtwWriteTransfer
0x14003b2e1  inc     byte ptr [rdi+43h]
0x14003b2e4  mov     rdx, rdi; Irp
0x14003b2e7  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14003b2ef  mov     rcx, [rbx+208h]; DeviceObject
0x14003b2f6  call    cs:__imp_IofCallDriver
0x14003b2fd  nop     dword ptr [rax+rax+00h]
0x14003b302  mov     rcx, [rbx+238h]; Object
0x14003b309  mov     edi, eax
0x14003b30b  test    rcx, rcx
0x14003b30e  jz      short loc_14003B31C
0x14003b310  call    cs:__imp_ObfDereferenceObject
0x14003b317  nop     dword ptr [rax+rax+00h]
0x14003b31c  mov     rcx, [rbx+208h]; TargetDevice
0x14003b323  call    cs:__imp_IoDetachDevice
0x14003b32a  nop     dword ptr [rax+rax+00h]
0x14003b32f  mov     rcx, rsi; DeviceObject
0x14003b332  call    cs:__imp_IoDeleteDevice
0x14003b339  nop     dword ptr [rax+rax+00h]
0x14003b33e  mov     eax, edi
0x14003b340  mov     rcx, [rsp+58h+var_18]
0x14003b345  xor     rcx, rsp; StackCookie
0x14003b348  call    __security_check_cookie
0x14003b34d  mov     rbx, [rsp+58h+arg_10]
0x14003b352  mov     rsi, [rsp+58h+arg_18]
0x14003b357  add     rsp, 50h
0x14003b35b  pop     rdi
0x14003b35c  retn
```
