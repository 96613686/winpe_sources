# IoDevObjCreateDeviceSecure

- ea: `0x1400091b0`
- end: `0x14000933b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400091b0`
- `0x140009344`
- `0x14000943c`
- `0x14000a134`
- `0x14000a2a0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400092f8`
- `ntoskrnl!IoDeleteDevice` at `0x1400092f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000931c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000931c`
- `ntoskrnl!IoCreateDevice` at `0x1400092c9`
- `ntoskrnl!IoCreateDevice` at `0x1400092c9`

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
0x1400091b0  mov     [rsp-38h+arg_18], r9d
0x1400091b5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400091b9  push    rbp
0x1400091ba  push    rbx
0x1400091bb  push    rdi
0x1400091bc  push    r12
0x1400091be  push    r13
0x1400091c0  push    r14
0x1400091c2  push    r15
0x1400091c4  mov     rbp, rsp
0x1400091c7  sub     rsp, 70h
0x1400091cb  mov     r14, [rbp+arg_40]
0x1400091d2  xor     ebx, ebx
0x1400091d4  mov     r15d, [rbp+arg_20]
0x1400091d8  xor     eax, eax
0x1400091da  mov     [rbp+arg_10], rbx
0x1400091de  xorps   xmm0, xmm0
0x1400091e1  mov     qword ptr [rbp+var_20], rax
0x1400091e5  mov     r13, r8
0x1400091e8  mov     [r14], rbx
0x1400091eb  mov     r12, rcx
0x1400091ee  mov     [rbp+arg_40], rbx
0x1400091f5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400091f9  test    r8, r8
0x1400091fc  jnz     short loc_14000920D
0x1400091fe  test    r15b, r15b
0x140009201  js      short loc_14000920D
0x140009203  mov     eax, 0C000000Dh
0x140009208  jmp     loc_14000932A
0x14000920d  cmp     [rbp+arg_38], rbx
0x140009211  jz      short loc_14000922B
0x140009213  mov     rcx, [rbp+arg_38]
0x140009217  lea     r8, [rbp+DeviceType]
0x14000921b  mov     rdx, r12
0x14000921e  call    PpRegStateReadCreateClassCreationSettings
0x140009223  test    eax, eax
0x140009225  js      loc_14000932A
0x14000922b  mov     edi, [rbp+DeviceType]
0x14000922e  test    dil, 2
0x140009232  jnz     short loc_140009286
0x140009234  mov     rcx, [rbp+arg_30]
0x140009238  lea     r8, [rbp+arg_10]
0x14000923c  call    SeSddlSecurityDescriptorFromSDDL
0x140009241  xor     ecx, ecx
0x140009243  mov     ebx, eax
0x140009245  test    eax, eax
0x140009247  js      loc_140009310
0x14000924d  lea     edx, [rcx+2]
0x140009250  mov     rax, [rbp+arg_10]
0x140009254  mov     edi, edx
0x140009256  mov     [rbp+DeviceType], edx
0x140009259  mov     qword ptr [rbp+DeviceType+8], rax
0x14000925d  cmp     [rbp+arg_38], rcx
0x140009261  jz      short loc_140009286
0x140009263  mov     [rbp+var_18], rdx
0x140009267  lea     rdx, [rbp+var_18]
0x14000926b  mov     [rbp+var_8], rcx
0x14000926f  mov     rcx, [rbp+arg_38]
0x140009273  mov     [rbp+var_10], rax
0x140009277  call    PpRegStateUpdateStackCreationSettings
0x14000927c  mov     ebx, eax
0x14000927e  test    eax, eax
0x140009280  js      loc_140009310
0x140009286  mov     r9d, [rbp+arg_18]
0x14000928a  test    dil, 1
0x14000928e  movzx   ecx, [rbp+arg_28]
0x140009292  mov     r8, r13; DeviceName
0x140009295  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14000929a  test    dil, 4
0x14000929e  movzx   eax, byte ptr [rbp+var_20+4]
0x1400092a2  cmovnz  r15d, [rbp+var_20]
0x1400092a7  test    dil, 8
0x1400092ab  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400092ae  cmovnz  ecx, eax
0x1400092b1  lea     rax, [rbp+arg_40]
0x1400092b8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400092bd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400092c1  mov     rcx, r12; DriverObject
0x1400092c4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400092c9  call    cs:__imp_IoCreateDevice
0x1400092d0  nop     dword ptr [rax+rax+00h]
0x1400092d5  mov     ebx, eax
0x1400092d7  test    eax, eax
0x1400092d9  js      short loc_140009310
0x1400092db  mov     rcx, [rbp+arg_40]; Object
0x1400092e2  lea     rdx, [rbp+DeviceType]
0x1400092e6  call    IopDevObjApplyPostCreationSettings
0x1400092eb  mov     ebx, eax
0x1400092ed  test    eax, eax
0x1400092ef  jns     short loc_140009306
0x1400092f1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400092f8  call    cs:__imp_IoDeleteDevice
0x1400092ff  nop     dword ptr [rax+rax+00h]
0x140009304  jmp     short loc_140009310
0x140009306  mov     rax, [rbp+arg_40]
0x14000930d  mov     [r14], rax
0x140009310  test    dil, 2
0x140009314  jz      short loc_140009328
0x140009316  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14000931a  xor     edx, edx; Tag
0x14000931c  call    cs:__imp_ExFreePoolWithTag
0x140009323  nop     dword ptr [rax+rax+00h]
0x140009328  mov     eax, ebx
0x14000932a  add     rsp, 70h
0x14000932e  pop     r15
0x140009330  pop     r14
0x140009332  pop     r13
0x140009334  pop     r12
0x140009336  pop     rdi
0x140009337  pop     rbx
0x140009338  pop     rbp
0x140009339  retn
```
