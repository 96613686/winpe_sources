# IoDevObjCreateDeviceSecure

- ea: `0x1400177c0`
- end: `0x14001794b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400177c0`
- `0x140017954`
- `0x140017a4c`
- `0x140018734`
- `0x1400188a0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140017908`
- `ntoskrnl!IoDeleteDevice` at `0x140017908`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001792c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001792c`
- `ntoskrnl!IoCreateDevice` at `0x1400178d9`
- `ntoskrnl!IoCreateDevice` at `0x1400178d9`

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
0x1400177c0  mov     [rsp-38h+arg_18], r9d
0x1400177c5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400177c9  push    rbp
0x1400177ca  push    rbx
0x1400177cb  push    rdi
0x1400177cc  push    r12
0x1400177ce  push    r13
0x1400177d0  push    r14
0x1400177d2  push    r15
0x1400177d4  mov     rbp, rsp
0x1400177d7  sub     rsp, 70h
0x1400177db  mov     r14, [rbp+arg_40]
0x1400177e2  xor     ebx, ebx
0x1400177e4  mov     r15d, [rbp+arg_20]
0x1400177e8  xor     eax, eax
0x1400177ea  mov     [rbp+arg_10], rbx
0x1400177ee  xorps   xmm0, xmm0
0x1400177f1  mov     qword ptr [rbp+var_20], rax
0x1400177f5  mov     r13, r8
0x1400177f8  mov     [r14], rbx
0x1400177fb  mov     r12, rcx
0x1400177fe  mov     [rbp+arg_40], rbx
0x140017805  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140017809  test    r8, r8
0x14001780c  jnz     short loc_14001781D
0x14001780e  test    r15b, r15b
0x140017811  js      short loc_14001781D
0x140017813  mov     eax, 0C000000Dh
0x140017818  jmp     loc_14001793A
0x14001781d  cmp     [rbp+arg_38], rbx
0x140017821  jz      short loc_14001783B
0x140017823  mov     rcx, [rbp+arg_38]
0x140017827  lea     r8, [rbp+DeviceType]
0x14001782b  mov     rdx, r12
0x14001782e  call    PpRegStateReadCreateClassCreationSettings
0x140017833  test    eax, eax
0x140017835  js      loc_14001793A
0x14001783b  mov     edi, [rbp+DeviceType]
0x14001783e  test    dil, 2
0x140017842  jnz     short loc_140017896
0x140017844  mov     rcx, [rbp+arg_30]
0x140017848  lea     r8, [rbp+arg_10]
0x14001784c  call    SeSddlSecurityDescriptorFromSDDL
0x140017851  xor     ecx, ecx
0x140017853  mov     ebx, eax
0x140017855  test    eax, eax
0x140017857  js      loc_140017920
0x14001785d  lea     edx, [rcx+2]
0x140017860  mov     rax, [rbp+arg_10]
0x140017864  mov     edi, edx
0x140017866  mov     [rbp+DeviceType], edx
0x140017869  mov     qword ptr [rbp+DeviceType+8], rax
0x14001786d  cmp     [rbp+arg_38], rcx
0x140017871  jz      short loc_140017896
0x140017873  mov     [rbp+var_18], rdx
0x140017877  lea     rdx, [rbp+var_18]
0x14001787b  mov     [rbp+var_8], rcx
0x14001787f  mov     rcx, [rbp+arg_38]
0x140017883  mov     [rbp+var_10], rax
0x140017887  call    PpRegStateUpdateStackCreationSettings
0x14001788c  mov     ebx, eax
0x14001788e  test    eax, eax
0x140017890  js      loc_140017920
0x140017896  mov     r9d, [rbp+arg_18]
0x14001789a  test    dil, 1
0x14001789e  movzx   ecx, [rbp+arg_28]
0x1400178a2  mov     r8, r13; DeviceName
0x1400178a5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x1400178aa  test    dil, 4
0x1400178ae  movzx   eax, byte ptr [rbp+var_20+4]
0x1400178b2  cmovnz  r15d, [rbp+var_20]
0x1400178b7  test    dil, 8
0x1400178bb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400178be  cmovnz  ecx, eax
0x1400178c1  lea     rax, [rbp+arg_40]
0x1400178c8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400178cd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400178d1  mov     rcx, r12; DriverObject
0x1400178d4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400178d9  call    cs:__imp_IoCreateDevice
0x1400178e0  nop     dword ptr [rax+rax+00h]
0x1400178e5  mov     ebx, eax
0x1400178e7  test    eax, eax
0x1400178e9  js      short loc_140017920
0x1400178eb  mov     rcx, [rbp+arg_40]; Object
0x1400178f2  lea     rdx, [rbp+DeviceType]
0x1400178f6  call    IopDevObjApplyPostCreationSettings
0x1400178fb  mov     ebx, eax
0x1400178fd  test    eax, eax
0x1400178ff  jns     short loc_140017916
0x140017901  mov     rcx, [rbp+arg_40]; DeviceObject
0x140017908  call    cs:__imp_IoDeleteDevice
0x14001790f  nop     dword ptr [rax+rax+00h]
0x140017914  jmp     short loc_140017920
0x140017916  mov     rax, [rbp+arg_40]
0x14001791d  mov     [r14], rax
0x140017920  test    dil, 2
0x140017924  jz      short loc_140017938
0x140017926  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14001792a  xor     edx, edx; Tag
0x14001792c  call    cs:__imp_ExFreePoolWithTag
0x140017933  nop     dword ptr [rax+rax+00h]
0x140017938  mov     eax, ebx
0x14001793a  add     rsp, 70h
0x14001793e  pop     r15
0x140017940  pop     r14
0x140017942  pop     r13
0x140017944  pop     r12
0x140017946  pop     rdi
0x140017947  pop     rbx
0x140017948  pop     rbp
0x140017949  retn
```
