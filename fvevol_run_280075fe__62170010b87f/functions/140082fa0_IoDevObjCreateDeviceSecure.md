# IoDevObjCreateDeviceSecure

- ea: `0x140082fa0`
- end: `0x14008312b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140082fa0`
- `0x140083134`
- `0x14008322c`
- `0x140083f24`
- `0x140084090`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400830e8`
- `ntoskrnl!IoDeleteDevice` at `0x1400830e8`
- `ntoskrnl!IoCreateDevice` at `0x1400830b9`
- `ntoskrnl!IoCreateDevice` at `0x1400830b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008310c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008310c`

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
0x140082fa0  mov     [rsp-38h+arg_18], r9d
0x140082fa5  mov     [rsp-38h+DeviceExtensionSize], edx
0x140082fa9  push    rbp
0x140082faa  push    rbx
0x140082fab  push    rdi
0x140082fac  push    r12
0x140082fae  push    r13
0x140082fb0  push    r14
0x140082fb2  push    r15
0x140082fb4  mov     rbp, rsp
0x140082fb7  sub     rsp, 70h
0x140082fbb  mov     r14, [rbp+arg_40]
0x140082fc2  xor     ebx, ebx
0x140082fc4  mov     r15d, [rbp+arg_20]
0x140082fc8  xor     eax, eax
0x140082fca  mov     [rbp+arg_10], rbx
0x140082fce  xorps   xmm0, xmm0
0x140082fd1  mov     qword ptr [rbp+var_20], rax
0x140082fd5  mov     r13, r8
0x140082fd8  mov     [r14], rbx
0x140082fdb  mov     r12, rcx
0x140082fde  mov     [rbp+arg_40], rbx
0x140082fe5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140082fe9  test    r8, r8
0x140082fec  jnz     short loc_140082FFD
0x140082fee  test    r15b, r15b
0x140082ff1  js      short loc_140082FFD
0x140082ff3  mov     eax, 0C000000Dh
0x140082ff8  jmp     loc_14008311A
0x140082ffd  cmp     [rbp+arg_38], rbx
0x140083001  jz      short loc_14008301B
0x140083003  mov     rcx, [rbp+arg_38]
0x140083007  lea     r8, [rbp+DeviceType]
0x14008300b  mov     rdx, r12
0x14008300e  call    PpRegStateReadCreateClassCreationSettings
0x140083013  test    eax, eax
0x140083015  js      loc_14008311A
0x14008301b  mov     edi, [rbp+DeviceType]
0x14008301e  test    dil, 2
0x140083022  jnz     short loc_140083076
0x140083024  mov     rcx, [rbp+arg_30]
0x140083028  lea     r8, [rbp+arg_10]
0x14008302c  call    SeSddlSecurityDescriptorFromSDDL
0x140083031  xor     ecx, ecx
0x140083033  mov     ebx, eax
0x140083035  test    eax, eax
0x140083037  js      loc_140083100
0x14008303d  lea     edx, [rcx+2]
0x140083040  mov     rax, [rbp+arg_10]
0x140083044  mov     edi, edx
0x140083046  mov     [rbp+DeviceType], edx
0x140083049  mov     qword ptr [rbp+DeviceType+8], rax
0x14008304d  cmp     [rbp+arg_38], rcx
0x140083051  jz      short loc_140083076
0x140083053  mov     [rbp+var_18], rdx
0x140083057  lea     rdx, [rbp+var_18]
0x14008305b  mov     [rbp+var_8], rcx
0x14008305f  mov     rcx, [rbp+arg_38]
0x140083063  mov     [rbp+var_10], rax
0x140083067  call    PpRegStateUpdateStackCreationSettings
0x14008306c  mov     ebx, eax
0x14008306e  test    eax, eax
0x140083070  js      loc_140083100
0x140083076  mov     r9d, [rbp+arg_18]
0x14008307a  test    dil, 1
0x14008307e  movzx   ecx, [rbp+arg_28]
0x140083082  mov     r8, r13; DeviceName
0x140083085  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14008308a  test    dil, 4
0x14008308e  movzx   eax, byte ptr [rbp+var_20+4]
0x140083092  cmovnz  r15d, [rbp+var_20]
0x140083097  test    dil, 8
0x14008309b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14008309e  cmovnz  ecx, eax
0x1400830a1  lea     rax, [rbp+arg_40]
0x1400830a8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400830ad  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400830b1  mov     rcx, r12; DriverObject
0x1400830b4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400830b9  call    cs:__imp_IoCreateDevice
0x1400830c0  nop     dword ptr [rax+rax+00h]
0x1400830c5  mov     ebx, eax
0x1400830c7  test    eax, eax
0x1400830c9  js      short loc_140083100
0x1400830cb  mov     rcx, [rbp+arg_40]; Object
0x1400830d2  lea     rdx, [rbp+DeviceType]
0x1400830d6  call    IopDevObjApplyPostCreationSettings
0x1400830db  mov     ebx, eax
0x1400830dd  test    eax, eax
0x1400830df  jns     short loc_1400830F6
0x1400830e1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400830e8  call    cs:__imp_IoDeleteDevice
0x1400830ef  nop     dword ptr [rax+rax+00h]
0x1400830f4  jmp     short loc_140083100
0x1400830f6  mov     rax, [rbp+arg_40]
0x1400830fd  mov     [r14], rax
0x140083100  test    dil, 2
0x140083104  jz      short loc_140083118
0x140083106  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14008310a  xor     edx, edx; Tag
0x14008310c  call    cs:__imp_ExFreePoolWithTag
0x140083113  nop     dword ptr [rax+rax+00h]
0x140083118  mov     eax, ebx
0x14008311a  add     rsp, 70h
0x14008311e  pop     r15
0x140083120  pop     r14
0x140083122  pop     r13
0x140083124  pop     r12
0x140083126  pop     rdi
0x140083127  pop     rbx
0x140083128  pop     rbp
0x140083129  retn
```
