# IoDevObjCreateDeviceSecure

- ea: `0x140010f90`
- end: `0x14001111b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010f90`
- `0x140011124`
- `0x14001121c`
- `0x140011f14`
- `0x140012080`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x1400110a9`
- `ntoskrnl!IoCreateDevice` at `0x1400110a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400110fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400110fc`
- `ntoskrnl!IoDeleteDevice` at `0x1400110d8`
- `ntoskrnl!IoDeleteDevice` at `0x1400110d8`

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
0x140010f90  mov     [rsp-38h+arg_18], r9d
0x140010f95  mov     [rsp-38h+DeviceExtensionSize], edx
0x140010f99  push    rbp
0x140010f9a  push    rbx
0x140010f9b  push    rdi
0x140010f9c  push    r12
0x140010f9e  push    r13
0x140010fa0  push    r14
0x140010fa2  push    r15
0x140010fa4  mov     rbp, rsp
0x140010fa7  sub     rsp, 70h
0x140010fab  mov     r14, [rbp+arg_40]
0x140010fb2  xor     ebx, ebx
0x140010fb4  mov     r15d, [rbp+arg_20]
0x140010fb8  xor     eax, eax
0x140010fba  mov     [rbp+arg_10], rbx
0x140010fbe  xorps   xmm0, xmm0
0x140010fc1  mov     qword ptr [rbp+var_20], rax
0x140010fc5  mov     r13, r8
0x140010fc8  mov     [r14], rbx
0x140010fcb  mov     r12, rcx
0x140010fce  mov     [rbp+arg_40], rbx
0x140010fd5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140010fd9  test    r8, r8
0x140010fdc  jnz     short loc_140010FED
0x140010fde  test    r15b, r15b
0x140010fe1  js      short loc_140010FED
0x140010fe3  mov     eax, 0C000000Dh
0x140010fe8  jmp     loc_14001110A
0x140010fed  cmp     [rbp+arg_38], rbx
0x140010ff1  jz      short loc_14001100B
0x140010ff3  mov     rcx, [rbp+arg_38]
0x140010ff7  lea     r8, [rbp+DeviceType]
0x140010ffb  mov     rdx, r12
0x140010ffe  call    PpRegStateReadCreateClassCreationSettings
0x140011003  test    eax, eax
0x140011005  js      loc_14001110A
0x14001100b  mov     edi, [rbp+DeviceType]
0x14001100e  test    dil, 2
0x140011012  jnz     short loc_140011066
0x140011014  mov     rcx, [rbp+arg_30]
0x140011018  lea     r8, [rbp+arg_10]
0x14001101c  call    SeSddlSecurityDescriptorFromSDDL
0x140011021  xor     ecx, ecx
0x140011023  mov     ebx, eax
0x140011025  test    eax, eax
0x140011027  js      loc_1400110F0
0x14001102d  lea     edx, [rcx+2]
0x140011030  mov     rax, [rbp+arg_10]
0x140011034  mov     edi, edx
0x140011036  mov     [rbp+DeviceType], edx
0x140011039  mov     qword ptr [rbp+DeviceType+8], rax
0x14001103d  cmp     [rbp+arg_38], rcx
0x140011041  jz      short loc_140011066
0x140011043  mov     [rbp+var_18], rdx
0x140011047  lea     rdx, [rbp+var_18]
0x14001104b  mov     [rbp+var_8], rcx
0x14001104f  mov     rcx, [rbp+arg_38]
0x140011053  mov     [rbp+var_10], rax
0x140011057  call    PpRegStateUpdateStackCreationSettings
0x14001105c  mov     ebx, eax
0x14001105e  test    eax, eax
0x140011060  js      loc_1400110F0
0x140011066  mov     r9d, [rbp+arg_18]
0x14001106a  test    dil, 1
0x14001106e  movzx   ecx, [rbp+arg_28]
0x140011072  mov     r8, r13; DeviceName
0x140011075  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14001107a  test    dil, 4
0x14001107e  movzx   eax, byte ptr [rbp+var_20+4]
0x140011082  cmovnz  r15d, [rbp+var_20]
0x140011087  test    dil, 8
0x14001108b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14001108e  cmovnz  ecx, eax
0x140011091  lea     rax, [rbp+arg_40]
0x140011098  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14001109d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400110a1  mov     rcx, r12; DriverObject
0x1400110a4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400110a9  call    cs:__imp_IoCreateDevice
0x1400110b0  nop     dword ptr [rax+rax+00h]
0x1400110b5  mov     ebx, eax
0x1400110b7  test    eax, eax
0x1400110b9  js      short loc_1400110F0
0x1400110bb  mov     rcx, [rbp+arg_40]; Object
0x1400110c2  lea     rdx, [rbp+DeviceType]
0x1400110c6  call    IopDevObjApplyPostCreationSettings
0x1400110cb  mov     ebx, eax
0x1400110cd  test    eax, eax
0x1400110cf  jns     short loc_1400110E6
0x1400110d1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400110d8  call    cs:__imp_IoDeleteDevice
0x1400110df  nop     dword ptr [rax+rax+00h]
0x1400110e4  jmp     short loc_1400110F0
0x1400110e6  mov     rax, [rbp+arg_40]
0x1400110ed  mov     [r14], rax
0x1400110f0  test    dil, 2
0x1400110f4  jz      short loc_140011108
0x1400110f6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400110fa  xor     edx, edx; Tag
0x1400110fc  call    cs:__imp_ExFreePoolWithTag
0x140011103  nop     dword ptr [rax+rax+00h]
0x140011108  mov     eax, ebx
0x14001110a  add     rsp, 70h
0x14001110e  pop     r15
0x140011110  pop     r14
0x140011112  pop     r13
0x140011114  pop     r12
0x140011116  pop     rdi
0x140011117  pop     rbx
0x140011118  pop     rbp
0x140011119  retn
```
