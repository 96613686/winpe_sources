# IoDevObjCreateDeviceSecure

- ea: `0x140085040`
- end: `0x1400851cb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140085040`
- `0x1400851d4`
- `0x1400852cc`
- `0x140085fc4`
- `0x140086130`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140085188`
- `ntoskrnl!IoDeleteDevice` at `0x140085188`
- `ntoskrnl!IoCreateDevice` at `0x140085159`
- `ntoskrnl!IoCreateDevice` at `0x140085159`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400851ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400851ac`

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
0x140085040  mov     [rsp-38h+arg_18], r9d
0x140085045  mov     [rsp-38h+DeviceExtensionSize], edx
0x140085049  push    rbp
0x14008504a  push    rbx
0x14008504b  push    rdi
0x14008504c  push    r12
0x14008504e  push    r13
0x140085050  push    r14
0x140085052  push    r15
0x140085054  mov     rbp, rsp
0x140085057  sub     rsp, 70h
0x14008505b  mov     r14, [rbp+arg_40]
0x140085062  xor     ebx, ebx
0x140085064  mov     r15d, [rbp+arg_20]
0x140085068  xor     eax, eax
0x14008506a  mov     [rbp+arg_10], rbx
0x14008506e  xorps   xmm0, xmm0
0x140085071  mov     qword ptr [rbp+var_20], rax
0x140085075  mov     r13, r8
0x140085078  mov     [r14], rbx
0x14008507b  mov     r12, rcx
0x14008507e  mov     [rbp+arg_40], rbx
0x140085085  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140085089  test    r8, r8
0x14008508c  jnz     short loc_14008509D
0x14008508e  test    r15b, r15b
0x140085091  js      short loc_14008509D
0x140085093  mov     eax, 0C000000Dh
0x140085098  jmp     loc_1400851BA
0x14008509d  cmp     [rbp+arg_38], rbx
0x1400850a1  jz      short loc_1400850BB
0x1400850a3  mov     rcx, [rbp+arg_38]
0x1400850a7  lea     r8, [rbp+DeviceType]
0x1400850ab  mov     rdx, r12
0x1400850ae  call    PpRegStateReadCreateClassCreationSettings
0x1400850b3  test    eax, eax
0x1400850b5  js      loc_1400851BA
0x1400850bb  mov     edi, [rbp+DeviceType]
0x1400850be  test    dil, 2
0x1400850c2  jnz     short loc_140085116
0x1400850c4  mov     rcx, [rbp+arg_30]
0x1400850c8  lea     r8, [rbp+arg_10]
0x1400850cc  call    SeSddlSecurityDescriptorFromSDDL
0x1400850d1  xor     ecx, ecx
0x1400850d3  mov     ebx, eax
0x1400850d5  test    eax, eax
0x1400850d7  js      loc_1400851A0
0x1400850dd  lea     edx, [rcx+2]
0x1400850e0  mov     rax, [rbp+arg_10]
0x1400850e4  mov     edi, edx
0x1400850e6  mov     [rbp+DeviceType], edx
0x1400850e9  mov     qword ptr [rbp+DeviceType+8], rax
0x1400850ed  cmp     [rbp+arg_38], rcx
0x1400850f1  jz      short loc_140085116
0x1400850f3  mov     [rbp+var_18], rdx
0x1400850f7  lea     rdx, [rbp+var_18]
0x1400850fb  mov     [rbp+var_8], rcx
0x1400850ff  mov     rcx, [rbp+arg_38]
0x140085103  mov     [rbp+var_10], rax
0x140085107  call    PpRegStateUpdateStackCreationSettings
0x14008510c  mov     ebx, eax
0x14008510e  test    eax, eax
0x140085110  js      loc_1400851A0
0x140085116  mov     r9d, [rbp+arg_18]
0x14008511a  test    dil, 1
0x14008511e  movzx   ecx, [rbp+arg_28]
0x140085122  mov     r8, r13; DeviceName
0x140085125  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14008512a  test    dil, 4
0x14008512e  movzx   eax, byte ptr [rbp+var_20+4]
0x140085132  cmovnz  r15d, [rbp+var_20]
0x140085137  test    dil, 8
0x14008513b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14008513e  cmovnz  ecx, eax
0x140085141  lea     rax, [rbp+arg_40]
0x140085148  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14008514d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140085151  mov     rcx, r12; DriverObject
0x140085154  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140085159  call    cs:__imp_IoCreateDevice
0x140085160  nop     dword ptr [rax+rax+00h]
0x140085165  mov     ebx, eax
0x140085167  test    eax, eax
0x140085169  js      short loc_1400851A0
0x14008516b  mov     rcx, [rbp+arg_40]; Object
0x140085172  lea     rdx, [rbp+DeviceType]
0x140085176  call    IopDevObjApplyPostCreationSettings
0x14008517b  mov     ebx, eax
0x14008517d  test    eax, eax
0x14008517f  jns     short loc_140085196
0x140085181  mov     rcx, [rbp+arg_40]; DeviceObject
0x140085188  call    cs:__imp_IoDeleteDevice
0x14008518f  nop     dword ptr [rax+rax+00h]
0x140085194  jmp     short loc_1400851A0
0x140085196  mov     rax, [rbp+arg_40]
0x14008519d  mov     [r14], rax
0x1400851a0  test    dil, 2
0x1400851a4  jz      short loc_1400851B8
0x1400851a6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400851aa  xor     edx, edx; Tag
0x1400851ac  call    cs:__imp_ExFreePoolWithTag
0x1400851b3  nop     dword ptr [rax+rax+00h]
0x1400851b8  mov     eax, ebx
0x1400851ba  add     rsp, 70h
0x1400851be  pop     r15
0x1400851c0  pop     r14
0x1400851c2  pop     r13
0x1400851c4  pop     r12
0x1400851c6  pop     rdi
0x1400851c7  pop     rbx
0x1400851c8  pop     rbp
0x1400851c9  retn
```
