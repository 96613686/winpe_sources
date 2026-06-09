# NdisRegisterDeviceEx

- ea: `0x140077420`
- end: `0x140077959`
- name: `NdisRegisterDeviceEx`
- size: `1337`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE NdisHandle, PNDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes, PDEVICE_OBJECT *pDeviceObject, PNDIS_HANDLE NdisDeviceHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x14003d920`
- `0x140077420`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x1401375d0`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400774c4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400774c4`
- `ntoskrnl!IoCreateDevice` at `0x140077563`
- `ntoskrnl!IoCreateDevice` at `0x140077563`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400775a4`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400775a4`
- `ntoskrnl!IoDeleteDevice` at `0x1400775be`
- `ntoskrnl!IoDeleteDevice` at `0x1400775be`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400778ce`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x1400778ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400778bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400778bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140077838`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140077882`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140077838`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140077882`

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
0x140077420  push    rbx
0x140077422  push    rbp
0x140077423  push    rdi
0x140077424  push    r12
0x140077426  push    r13
0x140077428  push    r14
0x14007742a  sub     rsp, 68h
0x14007742e  xor     ebp, ebp
0x140077430  mov     r12, r9
0x140077433  mov     [rsp+98h+arg_10], rbp
0x14007743b  mov     r13, r8
0x14007743e  mov     [rsp+98h+arg_18], rbp
0x140077446  mov     rdi, rdx
0x140077449  mov     r14, rcx
0x14007744c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140077453  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007745a  lea     rbx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140077461  jz      short loc_14007748B
0x140077463  mov     qword ptr [rsp+98h+Exclusive], rcx; char
0x140077468  mov     r9d, 71h ; 'q'; int
0x14007746e  mov     rcx, cs:WPP_GLOBAL_Control
0x140077475  mov     r8d, 1; int
0x14007747b  mov     dl, 4; int
0x14007747d  mov     qword ptr [rsp+98h+DeviceCharacteristics], rbx; struct _GUID *
0x140077482  mov     rcx, [rcx+40h]; int
0x140077486  call    WPP_RECORDER_SF_q
0x14007748b  mov     [r13+0], rbp
0x14007748f  mov     [r12], rbp
0x140077493  movzx   eax, byte ptr [r14]
0x140077497  mov     [rsp+98h+arg_8], rsi
0x14007749f  mov     [rsp+98h+var_38], r15
0x1400774a4  cmp     al, 2
0x1400774a6  jz      short loc_1400774F4
0x1400774a8  cmp     al, 4
0x1400774aa  jz      short loc_1400774E6
0x1400774ac  cmp     al, 11h
0x1400774ae  jz      short loc_1400774D9
0x1400774b0  cmp     al, 0AAh
0x1400774b2  jnz     loc_1400778FA
0x1400774b8  mov     rcx, [r14+8]
0x1400774bc  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x1400774c1  mov     rcx, [rcx]; DriverObject
0x1400774c4  call    cs:__imp_IoGetDriverObjectExtension
0x1400774cb  nop     dword ptr [rax+rax+00h]
0x1400774d0  mov     rbp, rax
0x1400774d3  mov     r15, [rax+28h]
0x1400774d7  jmp     short loc_1400774FB
0x1400774d9  mov     rbp, [r14+0EB0h]
0x1400774e0  mov     r15, [rbp+28h]
0x1400774e4  jmp     short loc_1400774FB
0x1400774e6  mov     r15, [r14+10h]
0x1400774ea  mov     [rsp+98h+arg_18], r14
0x1400774f2  jmp     short loc_1400774FB
0x1400774f4  mov     r15, [r14+28h]
0x1400774f8  mov     rbp, r14
0x1400774fb  test    r15, r15
0x1400774fe  jz      loc_1400778FA
0x140077504  mov     r8, [rdi+8]; DeviceName
0x140077508  lea     rcx, [rsp+98h+arg_10]
0x140077510  mov     rax, [rdi+10h]
0x140077514  mov     r9d, [rdi+20h]
0x140077518  mov     r10, [rdi+28h]
0x14007751c  inc     r9d
0x14007751f  movzx   edx, word ptr [r8]
0x140077523  and     r9d, 0FFFFFFFEh; DeviceType
0x140077527  movzx   eax, word ptr [rax]
0x14007752a  add     edx, 144h
0x140077530  add     eax, r9d
0x140077533  mov     [rsp+98h+var_48], r9d
0x140077538  add     eax, edx
0x14007753a  mov     dword ptr [rsp+98h+Size], eax
0x140077541  mov     edx, eax; DeviceExtensionSize
0x140077543  test    r10, r10
0x140077546  jnz     short loc_140077571
0x140077548  mov     [rsp+98h+DeviceObject], rcx; DeviceObject
0x14007754d  mov     r9d, 12h; DeviceType
0x140077553  mov     [rsp+98h+Exclusive], r10b; Exclusive
0x140077558  mov     rcx, r15; DriverObject
0x14007755b  mov     [rsp+98h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140077563  call    cs:__imp_IoCreateDevice
0x14007756a  nop     dword ptr [rax+rax+00h]
0x14007756f  jmp     short loc_140077583
0x140077571  mov     [rsp+98h+var_58], rcx; DeviceObject
0x140077576  mov     rcx, r15; DriverObject
0x140077579  mov     [rsp+98h+DeviceObject], r10; DefaultSDDLString
0x14007757e  call    WdmlibIoCreateDeviceSecure
0x140077583  mov     esi, eax
0x140077585  test    eax, eax
0x140077587  js      loc_1400778FF
0x14007758d  mov     rax, [rsp+98h+arg_10]
0x140077595  and     dword ptr [rax+30h], 0FFFFFF7Fh
0x14007759c  mov     rdx, [rdi+8]; DeviceName
0x1400775a0  mov     rcx, [rdi+10h]; SymbolicLinkName
0x1400775a4  call    cs:__imp_IoCreateSymbolicLink
0x1400775ab  nop     dword ptr [rax+rax+00h]
0x1400775b0  mov     esi, eax
0x1400775b2  test    eax, eax
0x1400775b4  jns     short loc_1400775CF
0x1400775b6  mov     rcx, [rsp+98h+arg_10]; DeviceObject
0x1400775be  call    cs:__imp_IoDeleteDevice
0x1400775c5  nop     dword ptr [rax+rax+00h]
0x1400775ca  jmp     loc_1400778FF
0x1400775cf  mov     rbx, [rsp+98h+arg_10]
0x1400775d7  xor     edx, edx; Val
0x1400775d9  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x1400775e1  mov     rbx, [rbx+40h]
0x1400775e5  mov     rcx, rbx; void *
0x1400775e8  call    memset
0x1400775ed  cmp     [rsp+98h+arg_18], 0
0x1400775f6  lea     rax, [rbx+140h]
0x1400775fd  mov     [rbx+28h], rax
0x140077601  lea     rax, [rbx+8]
0x140077605  mov     dword ptr [rbx], 1300109h
0x14007760b  mov     [rax+8], rax
0x14007760f  mov     [rax], rax
0x140077612  mov     [rbx+18h], r14
0x140077616  mov     rax, [rsp+98h+arg_10]
0x14007761e  mov     [rbx+20h], rax
0x140077622  mov     rax, [rdi+18h]
0x140077626  movups  xmm0, xmmword ptr [rax]
0x140077629  movups  xmmword ptr [rbx+30h], xmm0
0x14007762d  movups  xmm1, xmmword ptr [rax+10h]
0x140077631  movups  xmmword ptr [rbx+40h], xmm1
0x140077635  movups  xmm0, xmmword ptr [rax+20h]
0x140077639  movups  xmmword ptr [rbx+50h], xmm0
0x14007763d  movups  xmm1, xmmword ptr [rax+30h]
0x140077641  movups  xmmword ptr [rbx+60h], xmm1
0x140077645  movups  xmm0, xmmword ptr [rax+40h]
0x140077649  movups  xmmword ptr [rbx+70h], xmm0
0x14007764d  movups  xmm1, xmmword ptr [rax+50h]
0x140077651  movups  xmmword ptr [rbx+80h], xmm1
0x140077658  movups  xmm0, xmmword ptr [rax+60h]
0x14007765c  movups  xmmword ptr [rbx+90h], xmm0
0x140077663  movups  xmm1, xmmword ptr [rax+70h]
0x140077667  movups  xmmword ptr [rbx+0A0h], xmm1
0x14007766e  movups  xmm0, xmmword ptr [rax+80h]
0x140077675  movups  xmmword ptr [rbx+0B0h], xmm0
0x14007767c  movups  xmm1, xmmword ptr [rax+90h]
0x140077683  movups  xmmword ptr [rbx+0C0h], xmm1
0x14007768a  movups  xmm0, xmmword ptr [rax+0A0h]
0x140077691  movups  xmmword ptr [rbx+0D0h], xmm0
0x140077698  movups  xmm1, xmmword ptr [rax+0B0h]
0x14007769f  movups  xmmword ptr [rbx+0E0h], xmm1
0x1400776a6  movups  xmm0, xmmword ptr [rax+0C0h]
0x1400776ad  movups  xmmword ptr [rbx+0F0h], xmm0
0x1400776b4  mov     rax, [rax+0D0h]
0x1400776bb  mov     [rbx+100h], rax
0x1400776c2  jz      loc_14007778D
0x1400776c8  lea     rax, ?ndisDummyIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDummyIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1400776cf  mov     [r15+70h], rax
0x1400776d3  mov     [r15+78h], rax
0x1400776d7  mov     [r15+80h], rax
0x1400776de  mov     [r15+88h], rax
0x1400776e5  mov     [r15+90h], rax
0x1400776ec  mov     [r15+98h], rax
0x1400776f3  mov     [r15+0A0h], rax
0x1400776fa  mov     [r15+0A8h], rax
0x140077701  mov     [r15+0B0h], rax
0x140077708  mov     [r15+0B8h], rax
0x14007770f  mov     [r15+0C0h], rax
0x140077716  mov     [r15+0C8h], rax
0x14007771d  mov     [r15+0D0h], rax
0x140077724  mov     [r15+0D8h], rax
0x14007772b  mov     [r15+0E0h], rax
0x140077732  mov     [r15+0E8h], rax
0x140077739  mov     [r15+0F0h], rax
0x140077740  mov     [r15+0F8h], rax
0x140077747  mov     [r15+100h], rax
0x14007774e  mov     [r15+108h], rax
0x140077755  mov     [r15+110h], rax
0x14007775c  mov     [r15+118h], rax
0x140077763  mov     [r15+120h], rax
0x14007776a  mov     [r15+128h], rax
0x140077771  mov     [r15+130h], rax
0x140077778  mov     [r15+138h], rax
0x14007777f  mov     [r15+140h], rax
0x140077786  mov     [r15+148h], rax
0x14007778d  mov     ecx, [rsp+98h+var_48]
0x140077791  add     rcx, 140h
0x140077798  add     rcx, rbx; void *
0x14007779b  mov     [rbx+118h], rcx
0x1400777a2  mov     rax, [rdi+8]
0x1400777a6  movzx   edx, word ptr [rax]
0x1400777a9  mov     [rbx+110h], dx
0x1400777b0  mov     rax, [rdi+8]
0x1400777b4  movzx   edx, word ptr [rax]
0x1400777b7  add     dx, 2
0x1400777bb  mov     [rbx+112h], dx
0x1400777c2  mov     rdx, [rdi+8]
0x1400777c6  movzx   r8d, word ptr [rdx]; Size
0x1400777ca  mov     rdx, [rdx+8]; Src
0x1400777ce  call    memmove
0x1400777d3  movzx   ecx, word ptr [rbx+112h]
0x1400777da  add     rcx, [rbx+118h]; void *
0x1400777e1  mov     [rbx+128h], rcx
0x1400777e8  mov     rax, [rdi+10h]
0x1400777ec  movzx   edx, word ptr [rax]
0x1400777ef  mov     [rbx+120h], dx
0x1400777f6  mov     rax, [rdi+10h]
0x1400777fa  movzx   edx, word ptr [rax]
0x1400777fd  add     dx, 2
0x140077801  mov     [rbx+122h], dx
0x140077808  mov     rdx, [rdi+10h]
0x14007780c  movzx   r8d, word ptr [rdx]; Size
0x140077810  mov     rdx, [rdx+8]; Src
0x140077814  call    memmove
0x140077819  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140077820  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140077825  test    rbp, rbp
0x140077828  jz      short loc_14007786A
0x14007782a  lea     rdi, [rbp+188h]
0x140077831  mov     [rbx+18h], r14
0x140077835  mov     rcx, rdi; SpinLock
0x140077838  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007783f  nop     dword ptr [rax+rax+00h]
0x140077844  mov     rdx, [rbp+50h]
0x140077848  add     rbp, 50h ; 'P'
0x14007784c  cmp     [rdx+8], rbp
0x140077850  jnz     short loc_14007789C
0x140077852  lea     rcx, [rbx+8]
0x140077856  mov     [rcx], rdx
0x140077859  mov     [rcx+8], rbp
0x14007785d  mov     [rdx+8], rcx
0x140077861  mov     [rbp+0], rcx
0x140077865  mov     rcx, rdi
0x140077868  jmp     short loc_1400778B8
0x14007786a  mov     rdi, [rsp+98h+arg_18]
0x140077872  test    rdi, rdi
0x140077875  jz      short loc_1400778C7
0x140077877  lea     rbp, [rdi+28h]
0x14007787b  mov     [rbx+18h], rdi
0x14007787f  mov     rcx, rbp; SpinLock
0x140077882  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140077889  nop     dword ptr [rax+rax+00h]
0x14007788e  mov     rdx, [rdi+38h]
0x140077892  add     rdi, 38h ; '8'
0x140077896  cmp     [rdx+8], rdi
0x14007789a  jz      short loc_1400778A3
0x14007789c  mov     ecx, 3
0x1400778a1  int     29h; Win8: RtlFailFast(ecx)
0x1400778a3  lea     rcx, [rbx+8]
0x1400778a7  mov     [rcx], rdx
0x1400778aa  mov     [rcx+8], rdi
0x1400778ae  mov     [rdx+8], rcx
0x1400778b2  mov     [rdi], rcx
0x1400778b5  mov     rcx, rbp; SpinLock
0x1400778b8  movzx   edx, al; NewIrql
0x1400778bb  call    cs:__imp_KeReleaseSpinLock
0x1400778c2  nop     dword ptr [rax+rax+00h]
0x1400778c7  mov     rcx, cs:ImageSectionHandle; ImageSectionHandle
0x1400778ce  call    cs:__imp_MmUnlockPagableImageSection
0x1400778d5  nop     dword ptr [rax+rax+00h]
0x1400778da  lock dec cs:?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x1400778e1  mov     rax, [rsp+98h+arg_10]
0x1400778e9  mov     [r13+0], rax
0x1400778ed  mov     [r12], rbx
0x1400778f1  lea     rbx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x1400778f8  jmp     short loc_1400778FF
0x1400778fa  mov     esi, 0C00000BBh
0x1400778ff  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140077906  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007790d  jz      short loc_14007793B
0x14007790f  mov     rcx, cs:WPP_GLOBAL_Control
0x140077916  mov     r9d, 72h ; 'r'; int
0x14007791c  mov     dword ptr [rsp+98h+DeviceObject], esi; char
0x140077920  mov     r8d, 1; int
0x140077926  mov     qword ptr [rsp+98h+Exclusive], r14; char
0x14007792b  mov     dl, 4; int
0x14007792d  mov     qword ptr [rsp+98h+DeviceCharacteristics], rbx; struct _GUID *
0x140077932  mov     rcx, [rcx+40h]; int
0x140077936  call    WPP_RECORDER_SF_qL
0x14007793b  mov     r15, [rsp+98h+var_38]
0x140077940  mov     eax, esi
0x140077942  mov     rsi, [rsp+98h+arg_8]
0x14007794a  add     rsp, 68h
0x14007794e  pop     r14
0x140077950  pop     r13
0x140077952  pop     r12
0x140077954  pop     rdi
0x140077955  pop     rbp
0x140077956  pop     rbx
0x140077957  retn
```
