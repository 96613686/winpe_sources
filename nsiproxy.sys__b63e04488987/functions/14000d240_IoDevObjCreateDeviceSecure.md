# IoDevObjCreateDeviceSecure

- ea: `0x14000d240`
- end: `0x14000d3cb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000d240`
- `0x14000d3d4`
- `0x14000d4cc`
- `0x14000e1c4`
- `0x14000e330`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000d388`
- `ntoskrnl!IoDeleteDevice` at `0x14000d388`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d3ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d3ac`
- `ntoskrnl!IoCreateDevice` at `0x14000d359`
- `ntoskrnl!IoCreateDevice` at `0x14000d359`

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
0x14000d240  mov     [rsp-38h+arg_18], r9d
0x14000d245  mov     [rsp-38h+DeviceExtensionSize], edx
0x14000d249  push    rbp
0x14000d24a  push    rbx
0x14000d24b  push    rdi
0x14000d24c  push    r12
0x14000d24e  push    r13
0x14000d250  push    r14
0x14000d252  push    r15
0x14000d254  mov     rbp, rsp
0x14000d257  sub     rsp, 70h
0x14000d25b  mov     r14, [rbp+arg_40]
0x14000d262  xor     ebx, ebx
0x14000d264  mov     r15d, [rbp+arg_20]
0x14000d268  xor     eax, eax
0x14000d26a  mov     [rbp+arg_10], rbx
0x14000d26e  xorps   xmm0, xmm0
0x14000d271  mov     qword ptr [rbp+var_20], rax
0x14000d275  mov     r13, r8
0x14000d278  mov     [r14], rbx
0x14000d27b  mov     r12, rcx
0x14000d27e  mov     [rbp+arg_40], rbx
0x14000d285  movups  xmmword ptr [rbp+DeviceType], xmm0
0x14000d289  test    r8, r8
0x14000d28c  jnz     short loc_14000D29D
0x14000d28e  test    r15b, r15b
0x14000d291  js      short loc_14000D29D
0x14000d293  mov     eax, 0C000000Dh
0x14000d298  jmp     loc_14000D3BA
0x14000d29d  cmp     [rbp+arg_38], rbx
0x14000d2a1  jz      short loc_14000D2BB
0x14000d2a3  mov     rcx, [rbp+arg_38]
0x14000d2a7  lea     r8, [rbp+DeviceType]
0x14000d2ab  mov     rdx, r12
0x14000d2ae  call    PpRegStateReadCreateClassCreationSettings
0x14000d2b3  test    eax, eax
0x14000d2b5  js      loc_14000D3BA
0x14000d2bb  mov     edi, [rbp+DeviceType]
0x14000d2be  test    dil, 2
0x14000d2c2  jnz     short loc_14000D316
0x14000d2c4  mov     rcx, [rbp+arg_30]
0x14000d2c8  lea     r8, [rbp+arg_10]
0x14000d2cc  call    SeSddlSecurityDescriptorFromSDDL
0x14000d2d1  xor     ecx, ecx
0x14000d2d3  mov     ebx, eax
0x14000d2d5  test    eax, eax
0x14000d2d7  js      loc_14000D3A0
0x14000d2dd  lea     edx, [rcx+2]
0x14000d2e0  mov     rax, [rbp+arg_10]
0x14000d2e4  mov     edi, edx
0x14000d2e6  mov     [rbp+DeviceType], edx
0x14000d2e9  mov     qword ptr [rbp+DeviceType+8], rax
0x14000d2ed  cmp     [rbp+arg_38], rcx
0x14000d2f1  jz      short loc_14000D316
0x14000d2f3  mov     [rbp+var_18], rdx
0x14000d2f7  lea     rdx, [rbp+var_18]
0x14000d2fb  mov     [rbp+var_8], rcx
0x14000d2ff  mov     rcx, [rbp+arg_38]
0x14000d303  mov     [rbp+var_10], rax
0x14000d307  call    PpRegStateUpdateStackCreationSettings
0x14000d30c  mov     ebx, eax
0x14000d30e  test    eax, eax
0x14000d310  js      loc_14000D3A0
0x14000d316  mov     r9d, [rbp+arg_18]
0x14000d31a  test    dil, 1
0x14000d31e  movzx   ecx, [rbp+arg_28]
0x14000d322  mov     r8, r13; DeviceName
0x14000d325  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14000d32a  test    dil, 4
0x14000d32e  movzx   eax, byte ptr [rbp+var_20+4]
0x14000d332  cmovnz  r15d, [rbp+var_20]
0x14000d337  test    dil, 8
0x14000d33b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14000d33e  cmovnz  ecx, eax
0x14000d341  lea     rax, [rbp+arg_40]
0x14000d348  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14000d34d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x14000d351  mov     rcx, r12; DriverObject
0x14000d354  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x14000d359  call    cs:__imp_IoCreateDevice
0x14000d360  nop     dword ptr [rax+rax+00h]
0x14000d365  mov     ebx, eax
0x14000d367  test    eax, eax
0x14000d369  js      short loc_14000D3A0
0x14000d36b  mov     rcx, [rbp+arg_40]; Object
0x14000d372  lea     rdx, [rbp+DeviceType]
0x14000d376  call    IopDevObjApplyPostCreationSettings
0x14000d37b  mov     ebx, eax
0x14000d37d  test    eax, eax
0x14000d37f  jns     short loc_14000D396
0x14000d381  mov     rcx, [rbp+arg_40]; DeviceObject
0x14000d388  call    cs:__imp_IoDeleteDevice
0x14000d38f  nop     dword ptr [rax+rax+00h]
0x14000d394  jmp     short loc_14000D3A0
0x14000d396  mov     rax, [rbp+arg_40]
0x14000d39d  mov     [r14], rax
0x14000d3a0  test    dil, 2
0x14000d3a4  jz      short loc_14000D3B8
0x14000d3a6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14000d3aa  xor     edx, edx; Tag
0x14000d3ac  call    cs:__imp_ExFreePoolWithTag
0x14000d3b3  nop     dword ptr [rax+rax+00h]
0x14000d3b8  mov     eax, ebx
0x14000d3ba  add     rsp, 70h
0x14000d3be  pop     r15
0x14000d3c0  pop     r14
0x14000d3c2  pop     r13
0x14000d3c4  pop     r12
0x14000d3c6  pop     rdi
0x14000d3c7  pop     rbx
0x14000d3c8  pop     rbp
0x14000d3c9  retn
```
