# IoDevObjCreateDeviceSecure

- ea: `0x140042cc0`
- end: `0x140042e4b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140042cc0`
- `0x140042e54`
- `0x140042f4c`
- `0x140043c54`
- `0x140043dc0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140042e08`
- `ntoskrnl!IoDeleteDevice` at `0x140042e08`
- `ntoskrnl!IoCreateDevice` at `0x140042dd9`
- `ntoskrnl!IoCreateDevice` at `0x140042dd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042e2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042e2c`

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
0x140042cc0  mov     [rsp-38h+arg_18], r9d
0x140042cc5  mov     [rsp-38h+DeviceExtensionSize], edx
0x140042cc9  push    rbp
0x140042cca  push    rbx
0x140042ccb  push    rdi
0x140042ccc  push    r12
0x140042cce  push    r13
0x140042cd0  push    r14
0x140042cd2  push    r15
0x140042cd4  mov     rbp, rsp
0x140042cd7  sub     rsp, 70h
0x140042cdb  mov     r14, [rbp+arg_40]
0x140042ce2  xor     ebx, ebx
0x140042ce4  mov     r15d, [rbp+arg_20]
0x140042ce8  xor     eax, eax
0x140042cea  mov     [rbp+arg_10], rbx
0x140042cee  xorps   xmm0, xmm0
0x140042cf1  mov     qword ptr [rbp+var_20], rax
0x140042cf5  mov     r13, r8
0x140042cf8  mov     [r14], rbx
0x140042cfb  mov     r12, rcx
0x140042cfe  mov     [rbp+arg_40], rbx
0x140042d05  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140042d09  test    r8, r8
0x140042d0c  jnz     short loc_140042D1D
0x140042d0e  test    r15b, r15b
0x140042d11  js      short loc_140042D1D
0x140042d13  mov     eax, 0C000000Dh
0x140042d18  jmp     loc_140042E3A
0x140042d1d  cmp     [rbp+arg_38], rbx
0x140042d21  jz      short loc_140042D3B
0x140042d23  mov     rcx, [rbp+arg_38]
0x140042d27  lea     r8, [rbp+DeviceType]
0x140042d2b  mov     rdx, r12
0x140042d2e  call    PpRegStateReadCreateClassCreationSettings
0x140042d33  test    eax, eax
0x140042d35  js      loc_140042E3A
0x140042d3b  mov     edi, [rbp+DeviceType]
0x140042d3e  test    dil, 2
0x140042d42  jnz     short loc_140042D96
0x140042d44  mov     rcx, [rbp+arg_30]
0x140042d48  lea     r8, [rbp+arg_10]
0x140042d4c  call    SeSddlSecurityDescriptorFromSDDL
0x140042d51  xor     ecx, ecx
0x140042d53  mov     ebx, eax
0x140042d55  test    eax, eax
0x140042d57  js      loc_140042E20
0x140042d5d  lea     edx, [rcx+2]
0x140042d60  mov     rax, [rbp+arg_10]
0x140042d64  mov     edi, edx
0x140042d66  mov     [rbp+DeviceType], edx
0x140042d69  mov     qword ptr [rbp+DeviceType+8], rax
0x140042d6d  cmp     [rbp+arg_38], rcx
0x140042d71  jz      short loc_140042D96
0x140042d73  mov     [rbp+var_18], rdx
0x140042d77  lea     rdx, [rbp+var_18]
0x140042d7b  mov     [rbp+var_8], rcx
0x140042d7f  mov     rcx, [rbp+arg_38]
0x140042d83  mov     [rbp+var_10], rax
0x140042d87  call    PpRegStateUpdateStackCreationSettings
0x140042d8c  mov     ebx, eax
0x140042d8e  test    eax, eax
0x140042d90  js      loc_140042E20
0x140042d96  mov     r9d, [rbp+arg_18]
0x140042d9a  test    dil, 1
0x140042d9e  movzx   ecx, [rbp+arg_28]
0x140042da2  mov     r8, r13; DeviceName
0x140042da5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x140042daa  test    dil, 4
0x140042dae  movzx   eax, byte ptr [rbp+var_20+4]
0x140042db2  cmovnz  r15d, [rbp+var_20]
0x140042db7  test    dil, 8
0x140042dbb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x140042dbe  cmovnz  ecx, eax
0x140042dc1  lea     rax, [rbp+arg_40]
0x140042dc8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x140042dcd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140042dd1  mov     rcx, r12; DriverObject
0x140042dd4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140042dd9  call    cs:__imp_IoCreateDevice
0x140042de0  nop     dword ptr [rax+rax+00h]
0x140042de5  mov     ebx, eax
0x140042de7  test    eax, eax
0x140042de9  js      short loc_140042E20
0x140042deb  mov     rcx, [rbp+arg_40]; Object
0x140042df2  lea     rdx, [rbp+DeviceType]
0x140042df6  call    IopDevObjApplyPostCreationSettings
0x140042dfb  mov     ebx, eax
0x140042dfd  test    eax, eax
0x140042dff  jns     short loc_140042E16
0x140042e01  mov     rcx, [rbp+arg_40]; DeviceObject
0x140042e08  call    cs:__imp_IoDeleteDevice
0x140042e0f  nop     dword ptr [rax+rax+00h]
0x140042e14  jmp     short loc_140042E20
0x140042e16  mov     rax, [rbp+arg_40]
0x140042e1d  mov     [r14], rax
0x140042e20  test    dil, 2
0x140042e24  jz      short loc_140042E38
0x140042e26  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x140042e2a  xor     edx, edx; Tag
0x140042e2c  call    cs:__imp_ExFreePoolWithTag
0x140042e33  nop     dword ptr [rax+rax+00h]
0x140042e38  mov     eax, ebx
0x140042e3a  add     rsp, 70h
0x140042e3e  pop     r15
0x140042e40  pop     r14
0x140042e42  pop     r13
0x140042e44  pop     r12
0x140042e46  pop     rdi
0x140042e47  pop     rbx
0x140042e48  pop     rbp
0x140042e49  retn
```
