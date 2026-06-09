# ClassCreateDeviceObject

- ea: `0x140055c70`
- end: `0x1400561b8`
- name: `ClassCreateDeviceObject`
- size: `1352`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PCCHAR ObjectNameBuffer, PDEVICE_OBJECT LowerDeviceObject, BOOLEAN IsFdo, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callees

- `0x1400157d0`
- `0x14001fbf4`
- `0x14001feac`
- `0x140022748`
- `0x1400228d4`
- `0x140028e34`
- `0x140028ec0`
- `0x14003e940`
- `0x140055c70`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140056117`
- `ntoskrnl!ObfDereferenceObject` at `0x140056117`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055ce5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055e46`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055f3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055ce5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055e46`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055f3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055f28`
- `ntoskrnl!KeInitializeEvent` at `0x140055f79`
- `ntoskrnl!KeInitializeEvent` at `0x140056075`
- `ntoskrnl!KeInitializeEvent` at `0x14005608e`
- `ntoskrnl!KeInitializeEvent` at `0x140056136`
- `ntoskrnl!KeInitializeEvent` at `0x140055f79`
- `ntoskrnl!KeInitializeEvent` at `0x140056075`
- `ntoskrnl!KeInitializeEvent` at `0x14005608e`
- `ntoskrnl!KeInitializeEvent` at `0x140056136`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140056104`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140056104`
- `ntoskrnl!IoSetStartIoAttributes` at `0x140056186`
- `ntoskrnl!IoSetStartIoAttributes` at `0x140056186`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x140055cab`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x140055cab`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400560a9`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400560a9`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140055cc5`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140055cc5`
- `ntoskrnl!RtlInitString` at `0x140055d9c`
- `ntoskrnl!RtlInitString` at `0x140055d9c`
- `ntoskrnl!IoCreateDevice` at `0x140055e8b`
- `ntoskrnl!IoCreateDevice` at `0x140055e8b`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x140055fab`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x140055fab`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140055db3`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140055db3`

## pseudocode

```c
NTSTATUS __stdcall ClassCreateDeviceObject(
        PDRIVER_OBJECT DriverObject,
        PCCHAR ObjectNameBuffer,
        PDEVICE_OBJECT LowerDeviceObject,
        BOOLEAN IsFdo,
        PDEVICE_OBJECT *DeviceObject)
{
  _QWORD *DriverObjectExtension; // r13
  unsigned int *v9; // r14
  ULONG DeviceCharacteristics; // edi
  int v11; // esi
  int v12; // eax
  ULONG v13; // ebx
  NTSTATUS v14; // eax
  wchar_t *Buffer; // rcx
  _DWORD *DeviceExtension; // rdi
  char *v17; // rcx
  int v18; // eax
  KSPIN_LOCK *v19; // rbx
  char *v20; // rbx
  struct _DEVICE_OBJECT *v21; // r14
  struct _FUNCTIONAL_DEVICE_EXTENSION *v22; // rcx
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  struct _UNICODE_STRING v24; // xmm0
  __int64 v25; // rax
  SIZE_T RunRefSize; // [rsp+40h] [rbp-30h]
  __int64 v28; // [rsp+48h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-20h] BYREF
  struct _STRING SourceString; // [rsp+60h] [rbp-10h] BYREF
  PDEVICE_OBJECT v31; // [rsp+B8h] [rbp+48h] BYREF
  PDEVICE_OBJECT v32; // [rsp+C0h] [rbp+50h]

  v32 = LowerDeviceObject;
  v31 = 0;
  SourceString = 0;
  DestinationString = 0;
  RunRefSize = ExSizeOfRundownProtectionCacheAware();
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, ClassInitialize);
  *DeviceObject = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
  }
  v28 = DriverObjectExtension[46];
  v9 = (unsigned int *)((char *)DriverObjectExtension + (-(__int64)(IsFdo != 0) & 0xFFFFFFFFFFFFFF58uLL) + 192);
  DeviceCharacteristics = v9[3];
  if ( ObjectNameBuffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_s(
        WPP_GLOBAL_Control->AttachedDevice,
        164,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        ObjectNameBuffer);
    }
    RtlInitString(&SourceString, ObjectNameBuffer);
    v11 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_s(
          WPP_GLOBAL_Control->AttachedDevice,
          165,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          ObjectNameBuffer);
      }
      return v11;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    RtlInitUnicodeString(&DestinationString, 0);
    v12 = DeviceCharacteristics | 0x80;
    if ( IsFdo )
      v12 = DeviceCharacteristics;
    DeviceCharacteristics = v12;
  }
  v13 = RunRefSize + 8 + *v9;
  v14 = IoCreateDevice(DriverObject, v13, &DestinationString, v9[1], DeviceCharacteristics, 0, &v31);
  v11 = v14;
  if ( v14 >= 0 )
  {
    DeviceExtension = v31->DeviceExtension;
    memset(DeviceExtension, 0, v13);
    *DeviceExtension = 3;
    DeviceExtension[27] = 0;
    KeInitializeEvent((PRKEVENT)DeviceExtension + 2, SynchronizationEvent, 0);
    ClasspInitializeRemoveTracking(v31);
    v17 = (char *)v31->DeviceExtension + *v9;
    *((_QWORD *)DeviceExtension + 55) = v17;
    ExInitializeRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v17 + 8), RunRefSize);
    **((_DWORD **)DeviceExtension + 55) = 0;
    ClassAcquireRemoveLockEx(v31, v31, "minkernel\\storage\\classpnp\\class.c", 0x2E3Au);
    *((_QWORD *)DeviceExtension + 4) = DriverObjectExtension;
    *((_QWORD *)DeviceExtension + 20) = v9;
    *((_QWORD *)DeviceExtension + 1) = v31;
    *((_QWORD *)DeviceExtension + 56) = DriverObjectExtension + 55;
    *((_QWORD *)DeviceExtension + 2) = 0;
    if ( IsFdo )
    {
      *((_QWORD *)DeviceExtension + 3) = v31->DeviceExtension;
      v31->Flags |= 0x2000u;
      v31->Flags |= 0x1000000u;
      *((_QWORD *)DeviceExtension + 16) = 0;
      *((_QWORD *)DeviceExtension + 12) = (char *)v31->DeviceExtension + 1216;
      if ( v28 || v9[1] == 7 )
        v18 = 0;
      else
        v18 = -1;
      DeviceExtension[34] = v18;
      DeviceExtension[134] = 1;
      KeInitializeEvent((PRKEVENT)(DeviceExtension + 154), SynchronizationEvent, 1u);
      KeInitializeEvent((PRKEVENT)DeviceExtension + 35, SynchronizationEvent, 1u);
      v19 = (KSPIN_LOCK *)v31->DeviceExtension;
      KeInitializeSpinLock(v19 + 89);
      *((_WORD *)v19 + 408) = 0;
      v11 = 0;
      *((_BYTE *)v19 + 818) = 0;
      v19[90] = 0;
      *((_WORD *)v19 + 364) = 88;
    }
    else
    {
      v20 = (char *)v31->DeviceExtension;
      v21 = v32;
      v22 = (struct _FUNCTIONAL_DEVICE_EXTENSION *)v32->DeviceExtension;
      v31->Flags |= 0x2000u;
      *((_QWORD *)DeviceExtension + 3) = v22;
      ClassAddChild(v22);
      *((_QWORD *)DeviceExtension + 12) = v20 + 576;
      AttachedDeviceReference = IoGetAttachedDeviceReference(v21);
      *((_QWORD *)DeviceExtension + 2) = AttachedDeviceReference;
      ObfDereferenceObject(AttachedDeviceReference);
    }
    KeInitializeEvent((PRKEVENT)(DeviceExtension + 46), SynchronizationEvent, 1u);
    *((_BYTE *)DeviceExtension + 104) ^= (IsFdo ^ *((_BYTE *)DeviceExtension + 104)) & 1;
    v24 = DestinationString;
    *((_BYTE *)DeviceExtension + 105) = -1;
    *((struct _UNICODE_STRING *)DeviceExtension + 7) = v24;
    InitializeDictionary(DeviceExtension + 104);
    v25 = *((_QWORD *)DeviceExtension + 4);
    *((_BYTE *)DeviceExtension + 106) = 4;
    if ( *(_QWORD *)(v25 + 384) )
      IoSetStartIoAttributes(v31, 1u, 1u);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        167,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        (unsigned int)v14);
    }
    Buffer = DestinationString.Buffer;
    if ( DestinationString.Buffer )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 168, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        Buffer = DestinationString.Buffer;
      }
      if ( Buffer )
      {
        ExFreePoolWithTag(Buffer, 0);
        DestinationString.Buffer = 0;
      }
      RtlInitUnicodeString(&DestinationString, 0);
    }
  }
  *DeviceObject = v31;
  return v11;
}

```

## disassembly

```asm
0x140055c70  mov     [rsp-38h+arg_0], rbx
0x140055c75  mov     [rsp-38h+arg_10], r8
0x140055c7a  push    rbp
0x140055c7b  push    rsi
0x140055c7c  push    rdi
0x140055c7d  push    r12
0x140055c7f  push    r13
0x140055c81  push    r14
0x140055c83  push    r15
0x140055c85  mov     rbp, rsp
0x140055c88  sub     rsp, 70h
0x140055c8c  xorps   xmm0, xmm0
0x140055c8f  mov     [rbp+arg_8], 0
0x140055c97  xorps   xmm1, xmm1
0x140055c9a  mov     r15b, r9b
0x140055c9d  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x140055ca1  mov     rbx, rdx
0x140055ca4  mov     r12, rcx
0x140055ca7  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140055cab  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x140055cb2  nop     dword ptr [rax+rax+00h]
0x140055cb7  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140055cbe  mov     rcx, r12; DriverObject
0x140055cc1  mov     [rbp+RunRefSize], rax
0x140055cc5  call    cs:__imp_IoGetDriverObjectExtension
0x140055ccc  nop     dword ptr [rax+rax+00h]
0x140055cd1  xor     edx, edx; SourceString
0x140055cd3  lea     rcx, [rbp+DestinationString]; DestinationString
0x140055cd7  mov     r13, rax
0x140055cda  mov     rax, [rbp+DeviceObject]
0x140055cde  mov     qword ptr [rax], 0
0x140055ce5  call    cs:__imp_RtlInitUnicodeString
0x140055cec  nop     dword ptr [rax+rax+00h]
0x140055cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140055cf8  lea     r8, WPP_GLOBAL_Control
0x140055cff  mov     edx, 100h
0x140055d04  cmp     rcx, r8
0x140055d07  jz      short loc_140055D35
0x140055d09  test    [rcx+2Ch], edx
0x140055d0c  jz      short loc_140055D35
0x140055d0e  cmp     byte ptr [rcx+29h], 4
0x140055d12  jb      short loc_140055D35
0x140055d14  mov     rcx, [rcx+18h]
0x140055d18  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140055d1f  mov     edx, 0A3h
0x140055d24  call    WPP_SF_
0x140055d29  mov     edx, 100h
0x140055d2e  lea     r8, WPP_GLOBAL_Control
0x140055d35  mov     rax, [r13+170h]
0x140055d3c  mov     [rbp+var_28], rax
0x140055d40  mov     al, r15b
0x140055d43  neg     al
0x140055d45  sbb     rcx, rcx
0x140055d48  and     rcx, 0FFFFFFFFFFFFFF58h
0x140055d4f  lea     r14, [rcx+0C0h]
0x140055d56  add     r14, r13
0x140055d59  mov     edi, [r14+0Ch]
0x140055d5d  test    rbx, rbx
0x140055d60  jz      loc_140055E14
0x140055d66  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d6d  cmp     rcx, r8
0x140055d70  jz      short loc_140055D95
0x140055d72  test    [rcx+2Ch], edx
0x140055d75  jz      short loc_140055D95
0x140055d77  cmp     byte ptr [rcx+29h], 4
0x140055d7b  jb      short loc_140055D95
0x140055d7d  mov     rcx, [rcx+18h]
0x140055d81  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140055d88  mov     edx, 0A4h
0x140055d8d  mov     r9, rbx
0x140055d90  call    WPP_SF_s
0x140055d95  mov     rdx, rbx; SourceString
0x140055d98  lea     rcx, [rbp+SourceString]; DestinationString
0x140055d9c  call    cs:__imp_RtlInitString
0x140055da3  nop     dword ptr [rax+rax+00h]
0x140055da8  mov     r8b, 1; AllocateDestinationString
0x140055dab  lea     rdx, [rbp+SourceString]; SourceString
0x140055daf  lea     rcx, [rbp+DestinationString]; DestinationString
0x140055db3  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140055dba  nop     dword ptr [rax+rax+00h]
0x140055dbf  mov     esi, eax
0x140055dc1  test    eax, eax
0x140055dc3  jns     loc_140055E60
0x140055dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140055dd0  lea     rdi, WPP_GLOBAL_Control
0x140055dd7  cmp     rcx, rdi
0x140055dda  jz      loc_14005619D
0x140055de0  test    dword ptr [rcx+2Ch], 100h
0x140055de7  jz      loc_14005619D
0x140055ded  cmp     byte ptr [rcx+29h], 3
0x140055df1  jb      loc_14005619D
0x140055df7  mov     rcx, [rcx+18h]
0x140055dfb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140055e02  mov     edx, 0A5h
0x140055e07  mov     r9, rbx
0x140055e0a  call    WPP_SF_s
0x140055e0f  jmp     loc_14005619D
0x140055e14  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e1b  cmp     rcx, r8
0x140055e1e  jz      short loc_140055E40
0x140055e20  test    [rcx+2Ch], edx
0x140055e23  jz      short loc_140055E40
0x140055e25  cmp     byte ptr [rcx+29h], 4
0x140055e29  jb      short loc_140055E40
0x140055e2b  mov     rcx, [rcx+18h]
0x140055e2f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140055e36  mov     edx, 0A6h
0x140055e3b  call    WPP_SF_
0x140055e40  xor     edx, edx; SourceString
0x140055e42  lea     rcx, [rbp+DestinationString]; DestinationString
0x140055e46  call    cs:__imp_RtlInitUnicodeString
0x140055e4d  nop     dword ptr [rax+rax+00h]
0x140055e52  mov     eax, edi
0x140055e54  bts     eax, 7
0x140055e58  test    r15b, r15b
0x140055e5b  cmovnz  eax, edi
0x140055e5e  mov     edi, eax
0x140055e60  mov     rcx, [rbp+RunRefSize]
0x140055e64  lea     rax, [rbp+arg_8]
0x140055e68  mov     ebx, [r14]
0x140055e6b  lea     r8, [rbp+DestinationString]; DeviceName
0x140055e6f  mov     r9d, [r14+4]; DeviceType
0x140055e73  add     ecx, 8
0x140055e76  add     ebx, ecx
0x140055e78  mov     [rsp+70h+var_40], rax; DeviceObject
0x140055e7d  mov     edx, ebx; DeviceExtensionSize
0x140055e7f  mov     [rsp+70h+Exclusive], 0; Exclusive
0x140055e84  mov     rcx, r12; DriverObject
0x140055e87  mov     [rsp+70h+DeviceCharacteristics], edi; DeviceCharacteristics
0x140055e8b  call    cs:__imp_IoCreateDevice
0x140055e92  nop     dword ptr [rax+rax+00h]
0x140055e97  xor     r12d, r12d
0x140055e9a  mov     esi, eax
0x140055e9c  test    eax, eax
0x140055e9e  jns     loc_140055F4F
0x140055ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140055eab  lea     rdi, WPP_GLOBAL_Control
0x140055eb2  cmp     rcx, rdi
0x140055eb5  jz      short loc_140055EDE
0x140055eb7  test    dword ptr [rcx+2Ch], 100h
0x140055ebe  jz      short loc_140055EDE
0x140055ec0  cmp     byte ptr [rcx+29h], 2
0x140055ec4  jb      short loc_140055EDE
0x140055ec6  mov     rcx, [rcx+18h]
0x140055eca  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140055ed1  mov     edx, 0A7h
0x140055ed6  mov     r9d, eax
0x140055ed9  call    WPP_SF_d
0x140055ede  mov     rcx, [rbp+DestinationString.Buffer]
0x140055ee2  test    rcx, rcx
0x140055ee5  jz      loc_140056192
0x140055eeb  mov     r9, cs:WPP_GLOBAL_Control
0x140055ef2  cmp     r9, rdi
0x140055ef5  jz      short loc_140055F21
0x140055ef7  test    dword ptr [r9+2Ch], 100h
0x140055eff  jz      short loc_140055F21
0x140055f01  cmp     byte ptr [r9+29h], 3
0x140055f06  jb      short loc_140055F21
0x140055f08  mov     rcx, [r9+18h]
0x140055f0c  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140055f13  mov     edx, 0A8h
0x140055f18  call    WPP_SF_
0x140055f1d  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140055f21  test    rcx, rcx
0x140055f24  jz      short loc_140055F38
0x140055f26  xor     edx, edx; Tag
0x140055f28  call    cs:__imp_ExFreePoolWithTag
0x140055f2f  nop     dword ptr [rax+rax+00h]
0x140055f34  mov     [rbp+DestinationString.Buffer], r12
0x140055f38  xor     edx, edx; SourceString
0x140055f3a  lea     rcx, [rbp+DestinationString]; DestinationString
0x140055f3e  call    cs:__imp_RtlInitUnicodeString
0x140055f45  nop     dword ptr [rax+rax+00h]
0x140055f4a  jmp     loc_140056192
0x140055f4f  mov     rax, [rbp+arg_8]
0x140055f53  xor     edx, edx; Val
0x140055f55  mov     r8d, ebx; Size
0x140055f58  mov     rdi, [rax+40h]
0x140055f5c  mov     rcx, rdi; void *
0x140055f5f  call    memset
0x140055f64  xor     r8d, r8d; State
0x140055f67  mov     dword ptr [rdi], 3
0x140055f6d  lea     rcx, [rdi+30h]; Event
0x140055f71  mov     [rdi+6Ch], r12d
0x140055f75  lea     edx, [r8+1]; Type
0x140055f79  call    cs:__imp_KeInitializeEvent
0x140055f80  nop     dword ptr [rax+rax+00h]
0x140055f85  mov     rcx, [rbp+arg_8]
0x140055f89  call    ClasspInitializeRemoveTracking
0x140055f8e  mov     edx, [r14]
0x140055f91  mov     rax, [rbp+arg_8]
0x140055f95  mov     rcx, [rax+40h]
0x140055f99  add     rcx, rdx
0x140055f9c  mov     rdx, [rbp+RunRefSize]; RunRefSize
0x140055fa0  mov     [rdi+1B8h], rcx
0x140055fa7  add     rcx, 8; RunRefCacheAware
0x140055fab  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x140055fb2  nop     dword ptr [rax+rax+00h]
0x140055fb7  mov     rax, [rdi+1B8h]
0x140055fbe  lea     r8, File; "minkernel\\storage\\classpnp\\class.c"
0x140055fc5  mov     r9d, 2E3Ah; Line
0x140055fcb  mov     [rax], r12d
0x140055fce  mov     rcx, [rbp+arg_8]; DeviceObject
0x140055fd2  mov     rdx, rcx; Tag
0x140055fd5  call    ClassAcquireRemoveLockEx
0x140055fda  mov     [rdi+20h], r13
0x140055fde  mov     [rdi+0A0h], r14
0x140055fe5  mov     rax, [rbp+arg_8]
0x140055fe9  mov     [rdi+8], rax
0x140055fed  lea     rax, [r13+1B8h]
0x140055ff4  mov     [rdi+1C0h], rax
0x140055ffb  mov     [rdi+10h], r12
0x140055fff  mov     rax, [rbp+arg_8]
0x140056003  test    r15b, r15b
0x140056006  jz      loc_1400560D9
0x14005600c  mov     rcx, [rax+40h]
0x140056010  mov     [rdi+18h], rcx
0x140056014  mov     rax, [rbp+arg_8]
0x140056018  bts     dword ptr [rax+30h], 0Dh
0x14005601d  mov     rax, [rbp+arg_8]
0x140056021  bts     dword ptr [rax+30h], 18h
0x140056026  mov     [rdi+80h], r12
0x14005602d  mov     rax, [rbp+arg_8]
0x140056031  mov     rcx, [rax+40h]
0x140056035  add     rcx, 4C0h
0x14005603c  mov     [rdi+60h], rcx
0x140056040  cmp     [rbp+var_28], r12
0x140056044  jnz     short loc_140056052
0x140056046  cmp     dword ptr [r14+4], 7
0x14005604b  jz      short loc_140056052
0x14005604d  or      eax, 0FFFFFFFFh
0x140056050  jmp     short loc_140056055
0x140056052  mov     eax, r12d
0x140056055  mov     r14d, 1
0x14005605b  mov     [rdi+88h], eax
0x140056061  mov     r8b, r14b; State
0x140056064  mov     [rdi+218h], r14d
0x14005606b  mov     edx, r14d; Type
0x14005606e  lea     rcx, [rdi+268h]; Event
0x140056075  call    cs:__imp_KeInitializeEvent
0x14005607c  nop     dword ptr [rax+rax+00h]
0x140056081  lea     rcx, [rdi+348h]; Event
0x140056088  mov     r8b, r14b; State
0x14005608b  mov     edx, r14d; Type
0x14005608e  call    cs:__imp_KeInitializeEvent
0x140056095  nop     dword ptr [rax+rax+00h]
0x14005609a  mov     rax, [rbp+arg_8]
0x14005609e  mov     rbx, [rax+40h]
0x1400560a2  lea     rcx, [rbx+2C8h]; SpinLock
0x1400560a9  call    cs:__imp_KeInitializeSpinLock
0x1400560b0  nop     dword ptr [rax+rax+00h]
0x1400560b5  mov     [rbx+330h], r12w
0x1400560bd  mov     esi, r12d
0x1400560c0  mov     [rbx+332h], r12b
0x1400560c7  mov     [rbx+2D0h], r12
0x1400560ce  mov     word ptr [rbx+2D8h], 58h ; 'X'
0x1400560d7  jmp     short loc_140056129
0x1400560d9  mov     rbx, [rax+40h]
0x1400560dd  mov     r14, [rbp+arg_10]
0x1400560e1  mov     rdx, rbx
0x1400560e4  mov     rcx, [r14+40h]; FdoExtension
0x1400560e8  bts     dword ptr [rax+30h], 0Dh
0x1400560ed  mov     [rdi+18h], rcx
0x1400560f1  call    ClassAddChild
0x1400560f6  lea     rax, [rbx+240h]
0x1400560fd  mov     rcx, r14; DeviceObject
0x140056100  mov     [rdi+60h], rax
0x140056104  call    cs:__imp_IoGetAttachedDeviceReference
0x14005610b  nop     dword ptr [rax+rax+00h]
0x140056110  mov     rcx, rax; Object
0x140056113  mov     [rdi+10h], rax
0x140056117  call    cs:__imp_ObfDereferenceObject
0x14005611e  nop     dword ptr [rax+rax+00h]
0x140056123  mov     r14d, 1
0x140056129  lea     rcx, [rdi+0B8h]; Event
0x140056130  mov     r8b, r14b; State
0x140056133  mov     edx, r14d; Type
0x140056136  call    cs:__imp_KeInitializeEvent
0x14005613d  nop     dword ptr [rax+rax+00h]
0x140056142  mov     al, [rdi+68h]
0x140056145  mov     cl, al
0x140056147  xor     cl, r15b
0x14005614a  and     cl, r14b
0x14005614d  xor     cl, al
0x14005614f  mov     [rdi+68h], cl
0x140056152  lea     rcx, [rdi+1A0h]
0x140056159  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x14005615d  mov     byte ptr [rdi+69h], 0FFh
0x140056161  movdqu  xmmword ptr [rdi+70h], xmm0
0x140056166  call    InitializeDictionary
0x14005616b  mov     rax, [rdi+20h]
0x14005616f  mov     byte ptr [rdi+6Ah], 4
0x140056173  cmp     [rax+180h], r12
0x14005617a  jz      short loc_140056192
0x14005617c  mov     rcx, [rbp+arg_8]; DeviceObject
0x140056180  mov     r8b, r14b; NonCancelable
0x140056183  mov     dl, r14b; DeferredStartIo
0x140056186  call    cs:__imp_IoSetStartIoAttributes
0x14005618d  nop     dword ptr [rax+rax+00h]
0x140056192  mov     rcx, [rbp+DeviceObject]
  ... truncated ...
```
