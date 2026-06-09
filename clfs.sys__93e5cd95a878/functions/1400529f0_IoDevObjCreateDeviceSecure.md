# IoDevObjCreateDeviceSecure

- ea: `0x1400529f0`
- end: `0x140052b7b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400529f0`
- `0x140052b84`
- `0x140052c7c`
- `0x140053974`
- `0x140053ae0`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x140052b09`
- `ntoskrnl!IoCreateDevice` at `0x140052b09`
- `ntoskrnl!IoDeleteDevice` at `0x140052b38`
- `ntoskrnl!IoDeleteDevice` at `0x140052b38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052b5c`

## pseudocode

```c
__int64 __fastcall IoDevObjCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        __int64 a2,
        UNICODE_STRING *a3,
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
0x1400529f0  mov     [rsp-38h+arg_18], r9d
0x1400529f5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400529f9  push    rbp
0x1400529fa  push    rbx
0x1400529fb  push    rdi
0x1400529fc  push    r12
0x1400529fe  push    r13
0x140052a00  push    r14
0x140052a02  push    r15
0x140052a04  mov     rbp, rsp
0x140052a07  sub     rsp, 70h
0x140052a0b  mov     r14, [rbp+arg_40]
0x140052a12  xor     ebx, ebx
0x140052a14  mov     r15d, [rbp+arg_20]
0x140052a18  xor     eax, eax
0x140052a1a  mov     [rbp+arg_10], rbx
0x140052a1e  xorps   xmm0, xmm0
0x140052a21  mov     qword ptr [rbp+var_20], rax
0x140052a25  mov     r13, r8
0x140052a28  mov     [r14], rbx
0x140052a2b  mov     r12, rcx
0x140052a2e  mov     [rbp+arg_40], rbx
0x140052a35  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140052a39  test    r8, r8
0x140052a3c  jnz     short loc_140052A4D
0x140052a3e  test    r15b, r15b
0x140052a41  js      short loc_140052A4D
0x140052a43  mov     eax, 0C000000Dh
0x140052a48  jmp     loc_140052B6A
0x140052a4d  cmp     [rbp+arg_38], rbx
0x140052a51  jz      short loc_140052A6B
0x140052a53  mov     rcx, [rbp+arg_38]
0x140052a57  lea     r8, [rbp+DeviceType]
0x140052a5b  mov     rdx, r12
0x140052a5e  call    PpRegStateReadCreateClassCreationSettings
0x140052a63  test    eax, eax
0x140052a65  js      loc_140052B6A
0x140052a6b  mov     edi, [rbp+DeviceType]
0x140052a6e  test    dil, 2
0x140052a72  jnz     short loc_140052AC6
0x140052a74  mov     rcx, [rbp+arg_30]
0x140052a78  lea     r8, [rbp+arg_10]
0x140052a7c  call    SeSddlSecurityDescriptorFromSDDL
0x140052a81  xor     ecx, ecx
0x140052a83  mov     ebx, eax
0x140052a85  test    eax, eax
0x140052a87  js      loc_140052B50
0x140052a8d  lea     edx, [rcx+2]
0x140052a90  mov     rax, [rbp+arg_10]
0x140052a94  mov     edi, edx
0x140052a96  mov     [rbp+DeviceType], edx
0x140052a99  mov     qword ptr [rbp+DeviceType+8], rax
0x140052a9d  cmp     [rbp+arg_38], rcx
0x140052aa1  jz      short loc_140052AC6
0x140052aa3  mov     [rbp+var_18], rdx
0x140052aa7  lea     rdx, [rbp+var_18]
0x140052aab  mov     [rbp+var_8], rcx
0x140052aaf  mov     rcx, [rbp+arg_38]
0x140052ab3  mov     [rbp+var_10], rax
0x140052ab7  call    PpRegStateUpdateStackCreationSettings
0x140052abc  mov     ebx, eax
0x140052abe  test    eax, eax
0x140052ac0  js      loc_140052B50
0x140052ac6  mov     r9d, [rbp+arg_18]
0x140052aca  test    dil, 1
0x140052ace  movzx   ecx, [rbp+arg_28]
0x140052ad2  mov     r8, r13; DeviceName
0x140052ad5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x140052ada  test    dil, 4
0x140052ade  movzx   eax, byte ptr [rbp+var_20+4]
0x140052ae2  cmovnz  r15d, [rbp+var_20]
0x140052ae7  test    dil, 8
0x140052aeb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x140052aee  cmovnz  ecx, eax
0x140052af1  lea     rax, [rbp+arg_40]
0x140052af8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x140052afd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140052b01  mov     rcx, r12; DriverObject
0x140052b04  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140052b09  call    cs:__imp_IoCreateDevice
0x140052b10  nop     dword ptr [rax+rax+00h]
0x140052b15  mov     ebx, eax
0x140052b17  test    eax, eax
0x140052b19  js      short loc_140052B50
0x140052b1b  mov     rcx, [rbp+arg_40]; Object
0x140052b22  lea     rdx, [rbp+DeviceType]
0x140052b26  call    IopDevObjApplyPostCreationSettings
0x140052b2b  mov     ebx, eax
0x140052b2d  test    eax, eax
0x140052b2f  jns     short loc_140052B46
0x140052b31  mov     rcx, [rbp+arg_40]; DeviceObject
0x140052b38  call    cs:__imp_IoDeleteDevice
0x140052b3f  nop     dword ptr [rax+rax+00h]
0x140052b44  jmp     short loc_140052B50
0x140052b46  mov     rax, [rbp+arg_40]
0x140052b4d  mov     [r14], rax
0x140052b50  test    dil, 2
0x140052b54  jz      short loc_140052B68
0x140052b56  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x140052b5a  xor     edx, edx; Tag
0x140052b5c  call    cs:__imp_ExFreePoolWithTag
0x140052b63  nop     dword ptr [rax+rax+00h]
0x140052b68  mov     eax, ebx
0x140052b6a  add     rsp, 70h
0x140052b6e  pop     r15
0x140052b70  pop     r14
0x140052b72  pop     r13
0x140052b74  pop     r12
0x140052b76  pop     rdi
0x140052b77  pop     rbx
0x140052b78  pop     rbp
0x140052b79  retn
```
