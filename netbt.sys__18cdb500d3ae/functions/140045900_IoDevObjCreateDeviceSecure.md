# IoDevObjCreateDeviceSecure

- ea: `0x140045900`
- end: `0x140045a8b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140045900`
- `0x140045a94`
- `0x140045b8c`
- `0x140046884`
- `0x1400469f0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140045a48`
- `ntoskrnl!IoDeleteDevice` at `0x140045a48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045a6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045a6c`
- `ntoskrnl!IoCreateDevice` at `0x140045a19`
- `ntoskrnl!IoCreateDevice` at `0x140045a19`

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
0x140045900  mov     [rsp-38h+arg_18], r9d
0x140045905  mov     [rsp-38h+DeviceExtensionSize], edx
0x140045909  push    rbp
0x14004590a  push    rbx
0x14004590b  push    rdi
0x14004590c  push    r12
0x14004590e  push    r13
0x140045910  push    r14
0x140045912  push    r15
0x140045914  mov     rbp, rsp
0x140045917  sub     rsp, 70h
0x14004591b  mov     r14, [rbp+arg_40]
0x140045922  xor     ebx, ebx
0x140045924  mov     r15d, [rbp+arg_20]
0x140045928  xor     eax, eax
0x14004592a  mov     [rbp+arg_10], rbx
0x14004592e  xorps   xmm0, xmm0
0x140045931  mov     qword ptr [rbp+var_20], rax
0x140045935  mov     r13, r8
0x140045938  mov     [r14], rbx
0x14004593b  mov     r12, rcx
0x14004593e  mov     [rbp+arg_40], rbx
0x140045945  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140045949  test    r8, r8
0x14004594c  jnz     short loc_14004595D
0x14004594e  test    r15b, r15b
0x140045951  js      short loc_14004595D
0x140045953  mov     eax, 0C000000Dh
0x140045958  jmp     loc_140045A7A
0x14004595d  cmp     [rbp+arg_38], rbx
0x140045961  jz      short loc_14004597B
0x140045963  mov     rcx, [rbp+arg_38]
0x140045967  lea     r8, [rbp+DeviceType]
0x14004596b  mov     rdx, r12
0x14004596e  call    PpRegStateReadCreateClassCreationSettings
0x140045973  test    eax, eax
0x140045975  js      loc_140045A7A
0x14004597b  mov     edi, [rbp+DeviceType]
0x14004597e  test    dil, 2
0x140045982  jnz     short loc_1400459D6
0x140045984  mov     rcx, [rbp+arg_30]
0x140045988  lea     r8, [rbp+arg_10]
0x14004598c  call    SeSddlSecurityDescriptorFromSDDL
0x140045991  xor     ecx, ecx
0x140045993  mov     ebx, eax
0x140045995  test    eax, eax
0x140045997  js      loc_140045A60
0x14004599d  lea     edx, [rcx+2]
0x1400459a0  mov     rax, [rbp+arg_10]
0x1400459a4  mov     edi, edx
0x1400459a6  mov     [rbp+DeviceType], edx
0x1400459a9  mov     qword ptr [rbp+DeviceType+8], rax
0x1400459ad  cmp     [rbp+arg_38], rcx
0x1400459b1  jz      short loc_1400459D6
0x1400459b3  mov     [rbp+var_18], rdx
0x1400459b7  lea     rdx, [rbp+var_18]
0x1400459bb  mov     [rbp+var_8], rcx
0x1400459bf  mov     rcx, [rbp+arg_38]
0x1400459c3  mov     [rbp+var_10], rax
0x1400459c7  call    PpRegStateUpdateStackCreationSettings
0x1400459cc  mov     ebx, eax
0x1400459ce  test    eax, eax
0x1400459d0  js      loc_140045A60
0x1400459d6  mov     r9d, [rbp+arg_18]
0x1400459da  test    dil, 1
0x1400459de  movzx   ecx, [rbp+arg_28]
0x1400459e2  mov     r8, r13; DeviceName
0x1400459e5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x1400459ea  test    dil, 4
0x1400459ee  movzx   eax, byte ptr [rbp+var_20+4]
0x1400459f2  cmovnz  r15d, [rbp+var_20]
0x1400459f7  test    dil, 8
0x1400459fb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400459fe  cmovnz  ecx, eax
0x140045a01  lea     rax, [rbp+arg_40]
0x140045a08  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x140045a0d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140045a11  mov     rcx, r12; DriverObject
0x140045a14  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140045a19  call    cs:__imp_IoCreateDevice
0x140045a20  nop     dword ptr [rax+rax+00h]
0x140045a25  mov     ebx, eax
0x140045a27  test    eax, eax
0x140045a29  js      short loc_140045A60
0x140045a2b  mov     rcx, [rbp+arg_40]; Object
0x140045a32  lea     rdx, [rbp+DeviceType]
0x140045a36  call    IopDevObjApplyPostCreationSettings
0x140045a3b  mov     ebx, eax
0x140045a3d  test    eax, eax
0x140045a3f  jns     short loc_140045A56
0x140045a41  mov     rcx, [rbp+arg_40]; DeviceObject
0x140045a48  call    cs:__imp_IoDeleteDevice
0x140045a4f  nop     dword ptr [rax+rax+00h]
0x140045a54  jmp     short loc_140045A60
0x140045a56  mov     rax, [rbp+arg_40]
0x140045a5d  mov     [r14], rax
0x140045a60  test    dil, 2
0x140045a64  jz      short loc_140045A78
0x140045a66  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x140045a6a  xor     edx, edx; Tag
0x140045a6c  call    cs:__imp_ExFreePoolWithTag
0x140045a73  nop     dword ptr [rax+rax+00h]
0x140045a78  mov     eax, ebx
0x140045a7a  add     rsp, 70h
0x140045a7e  pop     r15
0x140045a80  pop     r14
0x140045a82  pop     r13
0x140045a84  pop     r12
0x140045a86  pop     rdi
0x140045a87  pop     rbx
0x140045a88  pop     rbp
0x140045a89  retn
```
