# IoDevObjCreateDeviceSecure

- ea: `0x140043640`
- end: `0x1400437cb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140043640`
- `0x1400437d4`
- `0x1400438cc`
- `0x1400445c4`
- `0x140044730`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400437ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400437ac`
- `ntoskrnl!IoDeleteDevice` at `0x140043788`
- `ntoskrnl!IoDeleteDevice` at `0x140043788`
- `ntoskrnl!IoCreateDevice` at `0x140043759`
- `ntoskrnl!IoCreateDevice` at `0x140043759`

## pseudocode

```c
__int64 __fastcall IoDevObjCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        ULONG a4,
        ULONG a5,
        BOOLEAN a6,
        __int64 a7,
        __int64 a8,
        PDEVICE_OBJECT DeviceObject)
{
  PDEVICE_OBJECT v9; // r14
  ULONG DeviceCharacteristics; // r15d
  __int64 result; // rax
  char v14; // di
  int updated; // ebx
  ULONG v16; // r9d
  BOOLEAN Exclusive; // cl
  ULONG DeviceType[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG v19[2]; // [rsp+50h] [rbp-20h]
  _QWORD v20[3]; // [rsp+58h] [rbp-18h] BYREF
  ULONG DeviceExtensionSize; // [rsp+B8h] [rbp+48h]
  __int64 v22; // [rsp+C0h] [rbp+50h] BYREF
  ULONG v23; // [rsp+C8h] [rbp+58h]

  v23 = a4;
  DeviceExtensionSize = a2;
  v9 = DeviceObject;
  DeviceCharacteristics = a5;
  v22 = 0;
  *(_QWORD *)v19 = 0;
  *(_QWORD *)&DeviceObject->Type = 0;
  DeviceObject = 0;
  *(_OWORD *)DeviceType = 0;
  if ( !a3 && (DeviceCharacteristics & 0x80u) == 0 )
    return 3221225485LL;
  if ( !a8 || (result = PpRegStateReadCreateClassCreationSettings(a8, DriverObject, DeviceType), (int)result >= 0) )
  {
    v14 = DeviceType[0];
    if ( (DeviceType[0] & 2) != 0 )
      goto LABEL_10;
    updated = SeSddlSecurityDescriptorFromSDDL(a7, a2, &v22);
    if ( updated >= 0 )
    {
      v14 = 2;
      DeviceType[0] = 2;
      *(_QWORD *)&DeviceType[2] = v22;
      if ( !a8
        || (v20[0] = 2,
            v20[2] = 0,
            v20[1] = v22,
            updated = PpRegStateUpdateStackCreationSettings(a8, (__int64)v20),
            updated >= 0) )
      {
LABEL_10:
        v16 = v23;
        Exclusive = a6;
        if ( (v14 & 1) != 0 )
          v16 = DeviceType[1];
        if ( (v14 & 4) != 0 )
          DeviceCharacteristics = v19[0];
        if ( (v14 & 8) != 0 )
          Exclusive = v19[1];
        updated = IoCreateDevice(
                    DriverObject,
                    DeviceExtensionSize,
                    a3,
                    v16,
                    DeviceCharacteristics,
                    Exclusive,
                    &DeviceObject);
        if ( updated >= 0 )
        {
          updated = IopDevObjApplyPostCreationSettings(DeviceObject);
          if ( updated >= 0 )
            *(_QWORD *)&v9->Type = DeviceObject;
          else
            IoDeleteDevice(DeviceObject);
        }
      }
    }
    if ( (v14 & 2) != 0 )
      ExFreePoolWithTag(*(PVOID *)&DeviceType[2], 0);
    return (unsigned int)updated;
  }
  return result;
}

```

## disassembly

```asm
0x140043640  mov     [rsp-38h+arg_18], r9d
0x140043645  mov     [rsp-38h+DeviceExtensionSize], edx
0x140043649  push    rbp
0x14004364a  push    rbx
0x14004364b  push    rdi
0x14004364c  push    r12
0x14004364e  push    r13
0x140043650  push    r14
0x140043652  push    r15
0x140043654  mov     rbp, rsp
0x140043657  sub     rsp, 70h
0x14004365b  mov     r14, [rbp+arg_40]
0x140043662  xor     ebx, ebx
0x140043664  mov     r15d, [rbp+arg_20]
0x140043668  xor     eax, eax
0x14004366a  mov     [rbp+arg_10], rbx
0x14004366e  xorps   xmm0, xmm0
0x140043671  mov     qword ptr [rbp+var_20], rax
0x140043675  mov     r13, r8
0x140043678  mov     [r14], rbx
0x14004367b  mov     r12, rcx
0x14004367e  mov     [rbp+arg_40], rbx
0x140043685  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140043689  test    r8, r8
0x14004368c  jnz     short loc_14004369D
0x14004368e  test    r15b, r15b
0x140043691  js      short loc_14004369D
0x140043693  mov     eax, 0C000000Dh
0x140043698  jmp     loc_1400437BA
0x14004369d  cmp     [rbp+arg_38], rbx
0x1400436a1  jz      short loc_1400436BB
0x1400436a3  mov     rcx, [rbp+arg_38]
0x1400436a7  lea     r8, [rbp+DeviceType]
0x1400436ab  mov     rdx, r12
0x1400436ae  call    PpRegStateReadCreateClassCreationSettings
0x1400436b3  test    eax, eax
0x1400436b5  js      loc_1400437BA
0x1400436bb  mov     edi, [rbp+DeviceType]
0x1400436be  test    dil, 2
0x1400436c2  jnz     short loc_140043716
0x1400436c4  mov     rcx, [rbp+arg_30]
0x1400436c8  lea     r8, [rbp+arg_10]
0x1400436cc  call    SeSddlSecurityDescriptorFromSDDL
0x1400436d1  xor     ecx, ecx
0x1400436d3  mov     ebx, eax
0x1400436d5  test    eax, eax
0x1400436d7  js      loc_1400437A0
0x1400436dd  lea     edx, [rcx+2]
0x1400436e0  mov     rax, [rbp+arg_10]
0x1400436e4  mov     edi, edx
0x1400436e6  mov     [rbp+DeviceType], edx
0x1400436e9  mov     qword ptr [rbp+DeviceType+8], rax
0x1400436ed  cmp     [rbp+arg_38], rcx
0x1400436f1  jz      short loc_140043716
0x1400436f3  mov     [rbp+var_18], rdx
0x1400436f7  lea     rdx, [rbp+var_18]
0x1400436fb  mov     [rbp+var_8], rcx
0x1400436ff  mov     rcx, [rbp+arg_38]
0x140043703  mov     [rbp+var_10], rax
0x140043707  call    PpRegStateUpdateStackCreationSettings
0x14004370c  mov     ebx, eax
0x14004370e  test    eax, eax
0x140043710  js      loc_1400437A0
0x140043716  mov     r9d, [rbp+arg_18]
0x14004371a  test    dil, 1
0x14004371e  movzx   ecx, [rbp+arg_28]
0x140043722  mov     r8, r13; DeviceName
0x140043725  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14004372a  test    dil, 4
0x14004372e  movzx   eax, byte ptr [rbp+var_20+4]
0x140043732  cmovnz  r15d, [rbp+var_20]
0x140043737  test    dil, 8
0x14004373b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14004373e  cmovnz  ecx, eax
0x140043741  lea     rax, [rbp+arg_40]
0x140043748  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14004374d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140043751  mov     rcx, r12; DriverObject
0x140043754  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140043759  call    cs:__imp_IoCreateDevice
0x140043760  nop     dword ptr [rax+rax+00h]
0x140043765  mov     ebx, eax
0x140043767  test    eax, eax
0x140043769  js      short loc_1400437A0
0x14004376b  mov     rcx, [rbp+arg_40]; Object
0x140043772  lea     rdx, [rbp+DeviceType]
0x140043776  call    IopDevObjApplyPostCreationSettings
0x14004377b  mov     ebx, eax
0x14004377d  test    eax, eax
0x14004377f  jns     short loc_140043796
0x140043781  mov     rcx, [rbp+arg_40]; DeviceObject
0x140043788  call    cs:__imp_IoDeleteDevice
0x14004378f  nop     dword ptr [rax+rax+00h]
0x140043794  jmp     short loc_1400437A0
0x140043796  mov     rax, [rbp+arg_40]
0x14004379d  mov     [r14], rax
0x1400437a0  test    dil, 2
0x1400437a4  jz      short loc_1400437B8
0x1400437a6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400437aa  xor     edx, edx; Tag
0x1400437ac  call    cs:__imp_ExFreePoolWithTag
0x1400437b3  nop     dword ptr [rax+rax+00h]
0x1400437b8  mov     eax, ebx
0x1400437ba  add     rsp, 70h
0x1400437be  pop     r15
0x1400437c0  pop     r14
0x1400437c2  pop     r13
0x1400437c4  pop     r12
0x1400437c6  pop     rdi
0x1400437c7  pop     rbx
0x1400437c8  pop     rbp
0x1400437c9  retn
```
