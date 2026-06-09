# NdisRegisterDeviceEx

- ea: `0x14007cb80`
- end: `0x14007d0b9`
- name: `NdisRegisterDeviceEx`
- size: `1337`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisHandle, PNDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes, PDEVICE_OBJECT *pDeviceObject, PNDIS_HANDLE NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x1400400d0`
- `0x14007cb80`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x14013e5d0`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x14007cc24`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14007cc24`
- `ntoskrnl!IoCreateDevice` at `0x14007ccc3`
- `ntoskrnl!IoCreateDevice` at `0x14007ccc3`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14007cd04`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14007cd04`
- `ntoskrnl!IoDeleteDevice` at `0x14007cd1e`
- `ntoskrnl!IoDeleteDevice` at `0x14007cd1e`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007d02e`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007d02e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007d01b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007d01b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007cf98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007cfe2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007cf98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007cfe2`

## pseudocode

```c
NDIS_STATUS __stdcall NdisRegisterDeviceEx(
        NDIS_HANDLE NdisHandle,
        PNDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes,
        PDEVICE_OBJECT *pDeviceObject,
        PNDIS_HANDLE NdisDeviceHandle)
{
  _QWORD *DriverObjectExtension; // rbp
  PNDIS_DEVICE_OBJECT_ATTRIBUTES v7; // rdi
  char v9; // al
  struct _DRIVER_OBJECT *v10; // r15
  struct _UNICODE_STRING *DeviceName; // r8
  const UNICODE_STRING *DefaultSDDLString; // r10
  ULONG v13; // r9d
  NTSTATUS v14; // eax
  NTSTATUS SymbolicLink; // esi
  _DWORD *DeviceExtension; // rbx
  bool v17; // zf
  int (__fastcall **MajorFunctions)(_DEVICE_OBJECT *, _IRP *); // rax
  char *v19; // rcx
  void *v20; // rcx
  KSPIN_LOCK *v21; // rdi
  KIRQL v22; // al
  __int64 v23; // rdx
  _QWORD *v24; // rbp
  KSPIN_LOCK *v25; // rcx
  KSPIN_LOCK *v26; // rdi
  KSPIN_LOCK *v27; // rbp
  KSPIN_LOCK v28; // rdx
  _QWORD *v29; // rdi
  ULONG DeviceCharacteristics; // [rsp+20h] [rbp-78h]
  BOOLEAN Exclusive; // [rsp+28h] [rbp-70h]
  const GUID *v33; // [rsp+38h] [rbp-60h]
  ULONG v34; // [rsp+50h] [rbp-48h]
  ULONG Size; // [rsp+A0h] [rbp+8h]
  PDEVICE_OBJECT DeviceObject; // [rsp+B0h] [rbp+18h] BYREF
  KSPIN_LOCK *v37; // [rsp+B8h] [rbp+20h]

  DriverObjectExtension = 0;
  DeviceObject = 0;
  v37 = 0;
  v7 = DeviceObjectAttributes;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(DeviceObjectAttributes) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)DeviceObjectAttributes,
      1,
      113,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)NdisHandle);
  }
  *pDeviceObject = 0;
  *NdisDeviceHandle = 0;
  v9 = *(_BYTE *)NdisHandle;
  if ( *(_BYTE *)NdisHandle == 2 )
  {
    v10 = (struct _DRIVER_OBJECT *)*((_QWORD *)NdisHandle + 5);
    DriverObjectExtension = NdisHandle;
  }
  else
  {
    switch ( v9 )
    {
      case 4:
        v10 = (struct _DRIVER_OBJECT *)*((_QWORD *)NdisHandle + 2);
        v37 = (KSPIN_LOCK *)NdisHandle;
        break;
      case 17:
        DriverObjectExtension = (_QWORD *)*((_QWORD *)NdisHandle + 470);
        v10 = (struct _DRIVER_OBJECT *)DriverObjectExtension[5];
        break;
      case -86:
        DriverObjectExtension = IoGetDriverObjectExtension(**((PDRIVER_OBJECT **)NdisHandle + 1), (PVOID)0x4E4D4944);
        v10 = (struct _DRIVER_OBJECT *)DriverObjectExtension[5];
        break;
      default:
        goto LABEL_29;
    }
  }
  if ( v10 )
  {
    DeviceName = v7->DeviceName;
    DefaultSDDLString = v7->DefaultSDDLString;
    v13 = (v7->ExtensionSize + 1) & 0xFFFFFFFE;
    v34 = v13;
    Size = DeviceName->Length + 324 + v13 + v7->SymbolicName->Length;
    if ( DefaultSDDLString )
      v14 = WdmlibIoCreateDeviceSecure(
              v10,
              Size,
              DeviceName,
              v13,
              DeviceCharacteristics,
              Exclusive,
              DefaultSDDLString,
              v33,
              &DeviceObject);
    else
      v14 = IoCreateDevice(v10, Size, DeviceName, 0x12u, 0x100u, 0, &DeviceObject);
    SymbolicLink = v14;
    if ( v14 < 0 )
      goto LABEL_30;
    DeviceObject->Flags &= ~0x80u;
    SymbolicLink = IoCreateSymbolicLink(v7->SymbolicName, v7->DeviceName);
    if ( SymbolicLink < 0 )
    {
      IoDeleteDevice(DeviceObject);
      goto LABEL_30;
    }
    DeviceExtension = DeviceObject->DeviceExtension;
    memset(DeviceExtension, 0, Size);
    v17 = v37 == 0;
    *((_QWORD *)DeviceExtension + 5) = DeviceExtension + 80;
    *DeviceExtension = 19923209;
    *((_QWORD *)DeviceExtension + 2) = DeviceExtension + 2;
    *((_QWORD *)DeviceExtension + 1) = DeviceExtension + 2;
    *((_QWORD *)DeviceExtension + 3) = NdisHandle;
    *((_QWORD *)DeviceExtension + 4) = DeviceObject;
    MajorFunctions = v7->MajorFunctions;
    *((_OWORD *)DeviceExtension + 3) = *(_OWORD *)MajorFunctions;
    *((_OWORD *)DeviceExtension + 4) = *((_OWORD *)MajorFunctions + 1);
    *((_OWORD *)DeviceExtension + 5) = *((_OWORD *)MajorFunctions + 2);
    *((_OWORD *)DeviceExtension + 6) = *((_OWORD *)MajorFunctions + 3);
    *((_OWORD *)DeviceExtension + 7) = *((_OWORD *)MajorFunctions + 4);
    *((_OWORD *)DeviceExtension + 8) = *((_OWORD *)MajorFunctions + 5);
    *((_OWORD *)DeviceExtension + 9) = *((_OWORD *)MajorFunctions + 6);
    *((_OWORD *)DeviceExtension + 10) = *((_OWORD *)MajorFunctions + 7);
    *((_OWORD *)DeviceExtension + 11) = *((_OWORD *)MajorFunctions + 8);
    *((_OWORD *)DeviceExtension + 12) = *((_OWORD *)MajorFunctions + 9);
    *((_OWORD *)DeviceExtension + 13) = *((_OWORD *)MajorFunctions + 10);
    *((_OWORD *)DeviceExtension + 14) = *((_OWORD *)MajorFunctions + 11);
    *((_OWORD *)DeviceExtension + 15) = *((_OWORD *)MajorFunctions + 12);
    *((_QWORD *)DeviceExtension + 32) = MajorFunctions[26];
    if ( !v17 )
    {
      v10->MajorFunction[0] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[1] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[3] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[4] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[5] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[6] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[7] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[8] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[9] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[10] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[11] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[12] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[13] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[14] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[15] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[16] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[17] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[18] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[19] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[20] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[21] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[22] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[23] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[24] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[25] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[26] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      v10->MajorFunction[27] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
    }
    v19 = (char *)DeviceExtension + v34 + 320;
    *((_QWORD *)DeviceExtension + 35) = v19;
    *((_WORD *)DeviceExtension + 136) = v7->DeviceName->Length;
    *((_WORD *)DeviceExtension + 137) = v7->DeviceName->Length + 2;
    memmove(v19, v7->DeviceName->Buffer, v7->DeviceName->Length);
    v20 = (void *)(*((_QWORD *)DeviceExtension + 35) + *((unsigned __int16 *)DeviceExtension + 137));
    *((_QWORD *)DeviceExtension + 37) = v20;
    *((_WORD *)DeviceExtension + 144) = v7->SymbolicName->Length;
    *((_WORD *)DeviceExtension + 145) = v7->SymbolicName->Length + 2;
    memmove(v20, v7->SymbolicName->Buffer, v7->SymbolicName->Length);
    ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
    if ( DriverObjectExtension )
    {
      v21 = DriverObjectExtension + 49;
      *((_QWORD *)DeviceExtension + 3) = NdisHandle;
      v22 = KeAcquireSpinLockRaiseToDpc(DriverObjectExtension + 49);
      v23 = DriverObjectExtension[10];
      v24 = DriverObjectExtension + 10;
      if ( *(_QWORD **)(v23 + 8) == v24 )
      {
        *((_QWORD *)DeviceExtension + 1) = v23;
        *((_QWORD *)DeviceExtension + 2) = v24;
        *(_QWORD *)(v23 + 8) = DeviceExtension + 2;
        *v24 = DeviceExtension + 2;
        v25 = v21;
LABEL_27:
        KeReleaseSpinLock(v25, v22);
        goto LABEL_28;
      }
    }
    else
    {
      v26 = v37;
      if ( !v37 )
      {
LABEL_28:
        MmUnlockPagableImageSection(ImageSectionHandle);
        _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
        *pDeviceObject = DeviceObject;
        *NdisDeviceHandle = DeviceExtension;
        goto LABEL_30;
      }
      v27 = v37 + 5;
      *((_QWORD *)DeviceExtension + 3) = v37;
      v22 = KeAcquireSpinLockRaiseToDpc(v26 + 5);
      v28 = v26[7];
      v29 = v26 + 7;
      if ( *(_QWORD **)(v28 + 8) == v29 )
      {
        *((_QWORD *)DeviceExtension + 1) = v28;
        *((_QWORD *)DeviceExtension + 2) = v29;
        *(_QWORD *)(v28 + 8) = DeviceExtension + 2;
        *v29 = DeviceExtension + 2;
        v25 = v27;
        goto LABEL_27;
      }
    }
    __fastfail(3u);
  }
LABEL_29:
  SymbolicLink = -1073741637;
LABEL_30:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(DeviceObjectAttributes) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)DeviceObjectAttributes,
      1,
      114,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)NdisHandle,
      SymbolicLink);
  }
  return SymbolicLink;
}

```

## disassembly

```asm
0x14007cb80  push    rbx
0x14007cb82  push    rbp
0x14007cb83  push    rdi
0x14007cb84  push    r12
0x14007cb86  push    r13
0x14007cb88  push    r14
0x14007cb8a  sub     rsp, 68h
0x14007cb8e  xor     ebp, ebp
0x14007cb90  mov     r12, r9
0x14007cb93  mov     [rsp+98h+arg_10], rbp
0x14007cb9b  mov     r13, r8
0x14007cb9e  mov     [rsp+98h+arg_18], rbp
0x14007cba6  mov     rdi, rdx
0x14007cba9  mov     r14, rcx
0x14007cbac  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007cbb3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007cbba  lea     rbx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007cbc1  jz      short loc_14007CBEB
0x14007cbc3  mov     qword ptr [rsp+98h+Exclusive], rcx; char
0x14007cbc8  mov     r9d, 71h ; 'q'; int
0x14007cbce  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cbd5  mov     r8d, 1; int
0x14007cbdb  mov     dl, 4; int
0x14007cbdd  mov     qword ptr [rsp+98h+DeviceCharacteristics], rbx; struct _GUID *
0x14007cbe2  mov     rcx, [rcx+40h]; int
0x14007cbe6  call    WPP_RECORDER_SF_q
0x14007cbeb  mov     [r13+0], rbp
0x14007cbef  mov     [r12], rbp
0x14007cbf3  movzx   eax, byte ptr [r14]
0x14007cbf7  mov     [rsp+98h+arg_8], rsi
0x14007cbff  mov     [rsp+98h+var_38], r15
0x14007cc04  cmp     al, 2
0x14007cc06  jz      short loc_14007CC54
0x14007cc08  cmp     al, 4
0x14007cc0a  jz      short loc_14007CC46
0x14007cc0c  cmp     al, 11h
0x14007cc0e  jz      short loc_14007CC39
0x14007cc10  cmp     al, 0AAh
0x14007cc12  jnz     loc_14007D05A
0x14007cc18  mov     rcx, [r14+8]
0x14007cc1c  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x14007cc21  mov     rcx, [rcx]; DriverObject
0x14007cc24  call    cs:__imp_IoGetDriverObjectExtension
0x14007cc2b  nop     dword ptr [rax+rax+00h]
0x14007cc30  mov     rbp, rax
0x14007cc33  mov     r15, [rax+28h]
0x14007cc37  jmp     short loc_14007CC5B
0x14007cc39  mov     rbp, [r14+0EB0h]
0x14007cc40  mov     r15, [rbp+28h]
0x14007cc44  jmp     short loc_14007CC5B
0x14007cc46  mov     r15, [r14+10h]
0x14007cc4a  mov     [rsp+98h+arg_18], r14
0x14007cc52  jmp     short loc_14007CC5B
0x14007cc54  mov     r15, [r14+28h]
0x14007cc58  mov     rbp, r14
0x14007cc5b  test    r15, r15
0x14007cc5e  jz      loc_14007D05A
0x14007cc64  mov     r8, [rdi+8]; DeviceName
0x14007cc68  lea     rcx, [rsp+98h+arg_10]
0x14007cc70  mov     rax, [rdi+10h]
0x14007cc74  mov     r9d, [rdi+20h]
0x14007cc78  mov     r10, [rdi+28h]
0x14007cc7c  inc     r9d
0x14007cc7f  movzx   edx, word ptr [r8]
0x14007cc83  and     r9d, 0FFFFFFFEh; DeviceType
0x14007cc87  movzx   eax, word ptr [rax]
0x14007cc8a  add     edx, 144h
0x14007cc90  add     eax, r9d
0x14007cc93  mov     [rsp+98h+var_48], r9d
0x14007cc98  add     eax, edx
0x14007cc9a  mov     dword ptr [rsp+98h+Size], eax
0x14007cca1  mov     edx, eax; DeviceExtensionSize
0x14007cca3  test    r10, r10
0x14007cca6  jnz     short loc_14007CCD1
0x14007cca8  mov     [rsp+98h+DeviceObject], rcx; DeviceObject
0x14007ccad  mov     r9d, 12h; DeviceType
0x14007ccb3  mov     [rsp+98h+Exclusive], r10b; Exclusive
0x14007ccb8  mov     rcx, r15; DriverObject
0x14007ccbb  mov     [rsp+98h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14007ccc3  call    cs:__imp_IoCreateDevice
0x14007ccca  nop     dword ptr [rax+rax+00h]
0x14007cccf  jmp     short loc_14007CCE3
0x14007ccd1  mov     [rsp+98h+var_58], rcx; DeviceObject
0x14007ccd6  mov     rcx, r15; DriverObject
0x14007ccd9  mov     [rsp+98h+DeviceObject], r10; DefaultSDDLString
0x14007ccde  call    WdmlibIoCreateDeviceSecure
0x14007cce3  mov     esi, eax
0x14007cce5  test    eax, eax
0x14007cce7  js      loc_14007D05F
0x14007cced  mov     rax, [rsp+98h+arg_10]
0x14007ccf5  and     dword ptr [rax+30h], 0FFFFFF7Fh
0x14007ccfc  mov     rdx, [rdi+8]; DeviceName
0x14007cd00  mov     rcx, [rdi+10h]; SymbolicLinkName
0x14007cd04  call    cs:__imp_IoCreateSymbolicLink
0x14007cd0b  nop     dword ptr [rax+rax+00h]
0x14007cd10  mov     esi, eax
0x14007cd12  test    eax, eax
0x14007cd14  jns     short loc_14007CD2F
0x14007cd16  mov     rcx, [rsp+98h+arg_10]; DeviceObject
0x14007cd1e  call    cs:__imp_IoDeleteDevice
0x14007cd25  nop     dword ptr [rax+rax+00h]
0x14007cd2a  jmp     loc_14007D05F
0x14007cd2f  mov     rbx, [rsp+98h+arg_10]
0x14007cd37  xor     edx, edx; Val
0x14007cd39  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x14007cd41  mov     rbx, [rbx+40h]
0x14007cd45  mov     rcx, rbx; void *
0x14007cd48  call    memset
0x14007cd4d  cmp     [rsp+98h+arg_18], 0
0x14007cd56  lea     rax, [rbx+140h]
0x14007cd5d  mov     [rbx+28h], rax
0x14007cd61  lea     rax, [rbx+8]
0x14007cd65  mov     dword ptr [rbx], 1300109h
0x14007cd6b  mov     [rax+8], rax
0x14007cd6f  mov     [rax], rax
0x14007cd72  mov     [rbx+18h], r14
0x14007cd76  mov     rax, [rsp+98h+arg_10]
0x14007cd7e  mov     [rbx+20h], rax
0x14007cd82  mov     rax, [rdi+18h]
0x14007cd86  movups  xmm0, xmmword ptr [rax]
0x14007cd89  movups  xmmword ptr [rbx+30h], xmm0
0x14007cd8d  movups  xmm1, xmmword ptr [rax+10h]
0x14007cd91  movups  xmmword ptr [rbx+40h], xmm1
0x14007cd95  movups  xmm0, xmmword ptr [rax+20h]
0x14007cd99  movups  xmmword ptr [rbx+50h], xmm0
0x14007cd9d  movups  xmm1, xmmword ptr [rax+30h]
0x14007cda1  movups  xmmword ptr [rbx+60h], xmm1
0x14007cda5  movups  xmm0, xmmword ptr [rax+40h]
0x14007cda9  movups  xmmword ptr [rbx+70h], xmm0
0x14007cdad  movups  xmm1, xmmword ptr [rax+50h]
0x14007cdb1  movups  xmmword ptr [rbx+80h], xmm1
0x14007cdb8  movups  xmm0, xmmword ptr [rax+60h]
0x14007cdbc  movups  xmmword ptr [rbx+90h], xmm0
0x14007cdc3  movups  xmm1, xmmword ptr [rax+70h]
0x14007cdc7  movups  xmmword ptr [rbx+0A0h], xmm1
0x14007cdce  movups  xmm0, xmmword ptr [rax+80h]
0x14007cdd5  movups  xmmword ptr [rbx+0B0h], xmm0
0x14007cddc  movups  xmm1, xmmword ptr [rax+90h]
0x14007cde3  movups  xmmword ptr [rbx+0C0h], xmm1
0x14007cdea  movups  xmm0, xmmword ptr [rax+0A0h]
0x14007cdf1  movups  xmmword ptr [rbx+0D0h], xmm0
0x14007cdf8  movups  xmm1, xmmword ptr [rax+0B0h]
0x14007cdff  movups  xmmword ptr [rbx+0E0h], xmm1
0x14007ce06  movups  xmm0, xmmword ptr [rax+0C0h]
0x14007ce0d  movups  xmmword ptr [rbx+0F0h], xmm0
0x14007ce14  mov     rax, [rax+0D0h]
0x14007ce1b  mov     [rbx+100h], rax
0x14007ce22  jz      loc_14007CEED
0x14007ce28  lea     rax, ?ndisDummyIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDummyIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007ce2f  mov     [r15+70h], rax
0x14007ce33  mov     [r15+78h], rax
0x14007ce37  mov     [r15+80h], rax
0x14007ce3e  mov     [r15+88h], rax
0x14007ce45  mov     [r15+90h], rax
0x14007ce4c  mov     [r15+98h], rax
0x14007ce53  mov     [r15+0A0h], rax
0x14007ce5a  mov     [r15+0A8h], rax
0x14007ce61  mov     [r15+0B0h], rax
0x14007ce68  mov     [r15+0B8h], rax
0x14007ce6f  mov     [r15+0C0h], rax
0x14007ce76  mov     [r15+0C8h], rax
0x14007ce7d  mov     [r15+0D0h], rax
0x14007ce84  mov     [r15+0D8h], rax
0x14007ce8b  mov     [r15+0E0h], rax
0x14007ce92  mov     [r15+0E8h], rax
0x14007ce99  mov     [r15+0F0h], rax
0x14007cea0  mov     [r15+0F8h], rax
0x14007cea7  mov     [r15+100h], rax
0x14007ceae  mov     [r15+108h], rax
0x14007ceb5  mov     [r15+110h], rax
0x14007cebc  mov     [r15+118h], rax
0x14007cec3  mov     [r15+120h], rax
0x14007ceca  mov     [r15+128h], rax
0x14007ced1  mov     [r15+130h], rax
0x14007ced8  mov     [r15+138h], rax
0x14007cedf  mov     [r15+140h], rax
0x14007cee6  mov     [r15+148h], rax
0x14007ceed  mov     ecx, [rsp+98h+var_48]
0x14007cef1  add     rcx, 140h
0x14007cef8  add     rcx, rbx; void *
0x14007cefb  mov     [rbx+118h], rcx
0x14007cf02  mov     rax, [rdi+8]
0x14007cf06  movzx   edx, word ptr [rax]
0x14007cf09  mov     [rbx+110h], dx
0x14007cf10  mov     rax, [rdi+8]
0x14007cf14  movzx   edx, word ptr [rax]
0x14007cf17  add     dx, 2
0x14007cf1b  mov     [rbx+112h], dx
0x14007cf22  mov     rdx, [rdi+8]
0x14007cf26  movzx   r8d, word ptr [rdx]; Size
0x14007cf2a  mov     rdx, [rdx+8]; Src
0x14007cf2e  call    memmove
0x14007cf33  movzx   ecx, word ptr [rbx+112h]
0x14007cf3a  add     rcx, [rbx+118h]; void *
0x14007cf41  mov     [rbx+128h], rcx
0x14007cf48  mov     rax, [rdi+10h]
0x14007cf4c  movzx   edx, word ptr [rax]
0x14007cf4f  mov     [rbx+120h], dx
0x14007cf56  mov     rax, [rdi+10h]
0x14007cf5a  movzx   edx, word ptr [rax]
0x14007cf5d  add     dx, 2
0x14007cf61  mov     [rbx+122h], dx
0x14007cf68  mov     rdx, [rdi+10h]
0x14007cf6c  movzx   r8d, word ptr [rdx]; Size
0x14007cf70  mov     rdx, [rdx+8]; Src
0x14007cf74  call    memmove
0x14007cf79  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14007cf80  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14007cf85  test    rbp, rbp
0x14007cf88  jz      short loc_14007CFCA
0x14007cf8a  lea     rdi, [rbp+188h]
0x14007cf91  mov     [rbx+18h], r14
0x14007cf95  mov     rcx, rdi; SpinLock
0x14007cf98  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007cf9f  nop     dword ptr [rax+rax+00h]
0x14007cfa4  mov     rdx, [rbp+50h]
0x14007cfa8  add     rbp, 50h ; 'P'
0x14007cfac  cmp     [rdx+8], rbp
0x14007cfb0  jnz     short loc_14007CFFC
0x14007cfb2  lea     rcx, [rbx+8]
0x14007cfb6  mov     [rcx], rdx
0x14007cfb9  mov     [rcx+8], rbp
0x14007cfbd  mov     [rdx+8], rcx
0x14007cfc1  mov     [rbp+0], rcx
0x14007cfc5  mov     rcx, rdi
0x14007cfc8  jmp     short loc_14007D018
0x14007cfca  mov     rdi, [rsp+98h+arg_18]
0x14007cfd2  test    rdi, rdi
0x14007cfd5  jz      short loc_14007D027
0x14007cfd7  lea     rbp, [rdi+28h]
0x14007cfdb  mov     [rbx+18h], rdi
0x14007cfdf  mov     rcx, rbp; SpinLock
0x14007cfe2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007cfe9  nop     dword ptr [rax+rax+00h]
0x14007cfee  mov     rdx, [rdi+38h]
0x14007cff2  add     rdi, 38h ; '8'
0x14007cff6  cmp     [rdx+8], rdi
0x14007cffa  jz      short loc_14007D003
0x14007cffc  mov     ecx, 3
0x14007d001  int     29h; Win8: RtlFailFast(ecx)
0x14007d003  lea     rcx, [rbx+8]
0x14007d007  mov     [rcx], rdx
0x14007d00a  mov     [rcx+8], rdi
0x14007d00e  mov     [rdx+8], rcx
0x14007d012  mov     [rdi], rcx
0x14007d015  mov     rcx, rbp; SpinLock
0x14007d018  movzx   edx, al; NewIrql
0x14007d01b  call    cs:__imp_KeReleaseSpinLock
0x14007d022  nop     dword ptr [rax+rax+00h]
0x14007d027  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x14007d02e  call    cs:__imp_MmUnlockPagableImageSection
0x14007d035  nop     dword ptr [rax+rax+00h]
0x14007d03a  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x14007d041  mov     rax, [rsp+98h+arg_10]
0x14007d049  mov     [r13+0], rax
0x14007d04d  mov     [r12], rbx
0x14007d051  lea     rbx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007d058  jmp     short loc_14007D05F
0x14007d05a  mov     esi, 0C00000BBh
0x14007d05f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007d066  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007d06d  jz      short loc_14007D09B
0x14007d06f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d076  mov     r9d, 72h ; 'r'; int
0x14007d07c  mov     dword ptr [rsp+98h+DeviceObject], esi; char
0x14007d080  mov     r8d, 1; int
0x14007d086  mov     qword ptr [rsp+98h+Exclusive], r14; char
0x14007d08b  mov     dl, 4; int
0x14007d08d  mov     qword ptr [rsp+98h+DeviceCharacteristics], rbx; struct _GUID *
0x14007d092  mov     rcx, [rcx+40h]; int
0x14007d096  call    WPP_RECORDER_SF_qL
0x14007d09b  mov     r15, [rsp+98h+var_38]
0x14007d0a0  mov     eax, esi
0x14007d0a2  mov     rsi, [rsp+98h+arg_8]
0x14007d0aa  add     rsp, 68h
0x14007d0ae  pop     r14
0x14007d0b0  pop     r13
0x14007d0b2  pop     r12
0x14007d0b4  pop     rdi
0x14007d0b5  pop     rbp
0x14007d0b6  pop     rbx
0x14007d0b7  retn
```
