# IoDevObjCreateDeviceSecure

- ea: `0x140020f00`
- end: `0x14002108b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140020f00`
- `0x140021094`
- `0x14002118c`
- `0x140021e6c`
- `0x140021fd8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002106c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002106c`
- `ntoskrnl!IoCreateDevice` at `0x140021019`
- `ntoskrnl!IoCreateDevice` at `0x140021019`
- `ntoskrnl!IoDeleteDevice` at `0x140021048`
- `ntoskrnl!IoDeleteDevice` at `0x140021048`

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
0x140020f00  mov     [rsp-38h+arg_18], r9d
0x140020f05  mov     [rsp-38h+DeviceExtensionSize], edx
0x140020f09  push    rbp
0x140020f0a  push    rbx
0x140020f0b  push    rdi
0x140020f0c  push    r12
0x140020f0e  push    r13
0x140020f10  push    r14
0x140020f12  push    r15
0x140020f14  mov     rbp, rsp
0x140020f17  sub     rsp, 70h
0x140020f1b  mov     r14, [rbp+arg_40]
0x140020f22  xor     ebx, ebx
0x140020f24  mov     r15d, [rbp+arg_20]
0x140020f28  xor     eax, eax
0x140020f2a  mov     [rbp+arg_10], rbx
0x140020f2e  xorps   xmm0, xmm0
0x140020f31  mov     qword ptr [rbp+var_20], rax
0x140020f35  mov     r13, r8
0x140020f38  mov     [r14], rbx
0x140020f3b  mov     r12, rcx
0x140020f3e  mov     [rbp+arg_40], rbx
0x140020f45  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140020f49  test    r8, r8
0x140020f4c  jnz     short loc_140020F5D
0x140020f4e  test    r15b, r15b
0x140020f51  js      short loc_140020F5D
0x140020f53  mov     eax, 0C000000Dh
0x140020f58  jmp     loc_14002107A
0x140020f5d  cmp     [rbp+arg_38], rbx
0x140020f61  jz      short loc_140020F7B
0x140020f63  mov     rcx, [rbp+arg_38]
0x140020f67  lea     r8, [rbp+DeviceType]
0x140020f6b  mov     rdx, r12
0x140020f6e  call    PpRegStateReadCreateClassCreationSettings
0x140020f73  test    eax, eax
0x140020f75  js      loc_14002107A
0x140020f7b  mov     edi, [rbp+DeviceType]
0x140020f7e  test    dil, 2
0x140020f82  jnz     short loc_140020FD6
0x140020f84  mov     rcx, [rbp+arg_30]
0x140020f88  lea     r8, [rbp+arg_10]
0x140020f8c  call    SeSddlSecurityDescriptorFromSDDL
0x140020f91  xor     ecx, ecx
0x140020f93  mov     ebx, eax
0x140020f95  test    eax, eax
0x140020f97  js      loc_140021060
0x140020f9d  lea     edx, [rcx+2]
0x140020fa0  mov     rax, [rbp+arg_10]
0x140020fa4  mov     edi, edx
0x140020fa6  mov     [rbp+DeviceType], edx
0x140020fa9  mov     qword ptr [rbp+DeviceType+8], rax
0x140020fad  cmp     [rbp+arg_38], rcx
0x140020fb1  jz      short loc_140020FD6
0x140020fb3  mov     [rbp+var_18], rdx
0x140020fb7  lea     rdx, [rbp+var_18]
0x140020fbb  mov     [rbp+var_8], rcx
0x140020fbf  mov     rcx, [rbp+arg_38]
0x140020fc3  mov     [rbp+var_10], rax
0x140020fc7  call    PpRegStateUpdateStackCreationSettings
0x140020fcc  mov     ebx, eax
0x140020fce  test    eax, eax
0x140020fd0  js      loc_140021060
0x140020fd6  mov     r9d, [rbp+arg_18]
0x140020fda  test    dil, 1
0x140020fde  movzx   ecx, [rbp+arg_28]
0x140020fe2  mov     r8, r13; DeviceName
0x140020fe5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x140020fea  test    dil, 4
0x140020fee  movzx   eax, byte ptr [rbp+var_20+4]
0x140020ff2  cmovnz  r15d, [rbp+var_20]
0x140020ff7  test    dil, 8
0x140020ffb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x140020ffe  cmovnz  ecx, eax
0x140021001  lea     rax, [rbp+arg_40]
0x140021008  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14002100d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140021011  mov     rcx, r12; DriverObject
0x140021014  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140021019  call    cs:__imp_IoCreateDevice
0x140021020  nop     dword ptr [rax+rax+00h]
0x140021025  mov     ebx, eax
0x140021027  test    eax, eax
0x140021029  js      short loc_140021060
0x14002102b  mov     rcx, [rbp+arg_40]; Object
0x140021032  lea     rdx, [rbp+DeviceType]
0x140021036  call    IopDevObjApplyPostCreationSettings
0x14002103b  mov     ebx, eax
0x14002103d  test    eax, eax
0x14002103f  jns     short loc_140021056
0x140021041  mov     rcx, [rbp+arg_40]; DeviceObject
0x140021048  call    cs:__imp_IoDeleteDevice
0x14002104f  nop     dword ptr [rax+rax+00h]
0x140021054  jmp     short loc_140021060
0x140021056  mov     rax, [rbp+arg_40]
0x14002105d  mov     [r14], rax
0x140021060  test    dil, 2
0x140021064  jz      short loc_140021078
0x140021066  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14002106a  xor     edx, edx; Tag
0x14002106c  call    cs:__imp_ExFreePoolWithTag
0x140021073  nop     dword ptr [rax+rax+00h]
0x140021078  mov     eax, ebx
0x14002107a  add     rsp, 70h
0x14002107e  pop     r15
0x140021080  pop     r14
0x140021082  pop     r13
0x140021084  pop     r12
0x140021086  pop     rdi
0x140021087  pop     rbx
0x140021088  pop     rbp
0x140021089  retn
```
