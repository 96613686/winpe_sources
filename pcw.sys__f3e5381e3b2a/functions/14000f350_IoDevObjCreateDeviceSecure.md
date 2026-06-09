# IoDevObjCreateDeviceSecure

- ea: `0x14000f350`
- end: `0x14000f4db`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000f350`
- `0x14000f4e4`
- `0x14000f5dc`
- `0x1400102e4`
- `0x140010450`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4bc`
- `ntoskrnl!IoDeleteDevice` at `0x14000f498`
- `ntoskrnl!IoDeleteDevice` at `0x14000f498`
- `ntoskrnl!IoCreateDevice` at `0x14000f469`
- `ntoskrnl!IoCreateDevice` at `0x14000f469`

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
0x14000f350  mov     [rsp-38h+arg_18], r9d
0x14000f355  mov     [rsp-38h+DeviceExtensionSize], edx
0x14000f359  push    rbp
0x14000f35a  push    rbx
0x14000f35b  push    rdi
0x14000f35c  push    r12
0x14000f35e  push    r13
0x14000f360  push    r14
0x14000f362  push    r15
0x14000f364  mov     rbp, rsp
0x14000f367  sub     rsp, 70h
0x14000f36b  mov     r14, [rbp+arg_40]
0x14000f372  xor     ebx, ebx
0x14000f374  mov     r15d, [rbp+arg_20]
0x14000f378  xor     eax, eax
0x14000f37a  mov     [rbp+arg_10], rbx
0x14000f37e  xorps   xmm0, xmm0
0x14000f381  mov     qword ptr [rbp+var_20], rax
0x14000f385  mov     r13, r8
0x14000f388  mov     [r14], rbx
0x14000f38b  mov     r12, rcx
0x14000f38e  mov     [rbp+arg_40], rbx
0x14000f395  movups  xmmword ptr [rbp+DeviceType], xmm0
0x14000f399  test    r8, r8
0x14000f39c  jnz     short loc_14000F3AD
0x14000f39e  test    r15b, r15b
0x14000f3a1  js      short loc_14000F3AD
0x14000f3a3  mov     eax, 0C000000Dh
0x14000f3a8  jmp     loc_14000F4CA
0x14000f3ad  cmp     [rbp+arg_38], rbx
0x14000f3b1  jz      short loc_14000F3CB
0x14000f3b3  mov     rcx, [rbp+arg_38]
0x14000f3b7  lea     r8, [rbp+DeviceType]
0x14000f3bb  mov     rdx, r12
0x14000f3be  call    PpRegStateReadCreateClassCreationSettings
0x14000f3c3  test    eax, eax
0x14000f3c5  js      loc_14000F4CA
0x14000f3cb  mov     edi, [rbp+DeviceType]
0x14000f3ce  test    dil, 2
0x14000f3d2  jnz     short loc_14000F426
0x14000f3d4  mov     rcx, [rbp+arg_30]
0x14000f3d8  lea     r8, [rbp+arg_10]
0x14000f3dc  call    SeSddlSecurityDescriptorFromSDDL
0x14000f3e1  xor     ecx, ecx
0x14000f3e3  mov     ebx, eax
0x14000f3e5  test    eax, eax
0x14000f3e7  js      loc_14000F4B0
0x14000f3ed  lea     edx, [rcx+2]
0x14000f3f0  mov     rax, [rbp+arg_10]
0x14000f3f4  mov     edi, edx
0x14000f3f6  mov     [rbp+DeviceType], edx
0x14000f3f9  mov     qword ptr [rbp+DeviceType+8], rax
0x14000f3fd  cmp     [rbp+arg_38], rcx
0x14000f401  jz      short loc_14000F426
0x14000f403  mov     [rbp+var_18], rdx
0x14000f407  lea     rdx, [rbp+var_18]
0x14000f40b  mov     [rbp+var_8], rcx
0x14000f40f  mov     rcx, [rbp+arg_38]
0x14000f413  mov     [rbp+var_10], rax
0x14000f417  call    PpRegStateUpdateStackCreationSettings
0x14000f41c  mov     ebx, eax
0x14000f41e  test    eax, eax
0x14000f420  js      loc_14000F4B0
0x14000f426  mov     r9d, [rbp+arg_18]
0x14000f42a  test    dil, 1
0x14000f42e  movzx   ecx, [rbp+arg_28]
0x14000f432  mov     r8, r13; DeviceName
0x14000f435  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14000f43a  test    dil, 4
0x14000f43e  movzx   eax, byte ptr [rbp+var_20+4]
0x14000f442  cmovnz  r15d, [rbp+var_20]
0x14000f447  test    dil, 8
0x14000f44b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14000f44e  cmovnz  ecx, eax
0x14000f451  lea     rax, [rbp+arg_40]
0x14000f458  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14000f45d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x14000f461  mov     rcx, r12; DriverObject
0x14000f464  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x14000f469  call    cs:__imp_IoCreateDevice
0x14000f470  nop     dword ptr [rax+rax+00h]
0x14000f475  mov     ebx, eax
0x14000f477  test    eax, eax
0x14000f479  js      short loc_14000F4B0
0x14000f47b  mov     rcx, [rbp+arg_40]; Object
0x14000f482  lea     rdx, [rbp+DeviceType]
0x14000f486  call    IopDevObjApplyPostCreationSettings
0x14000f48b  mov     ebx, eax
0x14000f48d  test    eax, eax
0x14000f48f  jns     short loc_14000F4A6
0x14000f491  mov     rcx, [rbp+arg_40]; DeviceObject
0x14000f498  call    cs:__imp_IoDeleteDevice
0x14000f49f  nop     dword ptr [rax+rax+00h]
0x14000f4a4  jmp     short loc_14000F4B0
0x14000f4a6  mov     rax, [rbp+arg_40]
0x14000f4ad  mov     [r14], rax
0x14000f4b0  test    dil, 2
0x14000f4b4  jz      short loc_14000F4C8
0x14000f4b6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14000f4ba  xor     edx, edx; Tag
0x14000f4bc  call    cs:__imp_ExFreePoolWithTag
0x14000f4c3  nop     dword ptr [rax+rax+00h]
0x14000f4c8  mov     eax, ebx
0x14000f4ca  add     rsp, 70h
0x14000f4ce  pop     r15
0x14000f4d0  pop     r14
0x14000f4d2  pop     r13
0x14000f4d4  pop     r12
0x14000f4d6  pop     rdi
0x14000f4d7  pop     rbx
0x14000f4d8  pop     rbp
0x14000f4d9  retn
```
