# FltpCreateControlDeviceObject

- ea: `0x18004f284`
- end: `0x18004f403`
- name: `FltpCreateControlDeviceObject`
- size: `383`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, const UNICODE_STRING *, __int64, PDEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800674b0`

## callees

- `0x180009f20`
- `0x180020180`
- `0x18004f284`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f35f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f38f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f35f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004f38f`
- `ntoskrnl!IoCreateDevice` at `0x18004f2d9`
- `ntoskrnl!IoCreateDevice` at `0x18004f2d9`
- `ntoskrnl!IoDeleteDevice` at `0x18004f3d2`
- `ntoskrnl!IoDeleteDevice` at `0x18004f3d2`

## string_xrefs

- `0x18004f312`: `FltpCreateControlDeviceObject`

## pseudocode

```c
__int64 __fastcall FltpCreateControlDeviceObject(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        __int64 a4,
        PDEVICE_OBJECT *a5)
{
  ULONG DeviceCharacteristics; // eax
  ULONG v8; // r9d
  ULONG v10; // edx
  unsigned int v11; // edi
  __int64 v12; // rcx
  UNICODE_STRING *DeviceExtension; // rbx
  unsigned __int16 Length; // ax
  unsigned __int16 v15; // r9
  __int64 v16; // r8
  PDEVICE_OBJECT DeviceObject; // [rsp+60h] [rbp+8h] BYREF

  DeviceCharacteristics = *(_DWORD *)(a1 + 52);
  v8 = *(_DWORD *)(a1 + 72);
  v10 = a2->Length + 80 + a3->Length;
  DeviceObject = 0;
  v11 = IoCreateDevice((PDRIVER_OBJECT)DriverObject, v10, 0, v8, DeviceCharacteristics, 0, &DeviceObject);
  if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 1836, 0) >= 0 )
  {
    DeviceExtension = (UNICODE_STRING *)DeviceObject->DeviceExtension;
    *(_DWORD *)&DeviceExtension->Length = 5304582;
    *(_QWORD *)&DeviceExtension[1].Length = a4;
    DeviceExtension[2].Buffer = (wchar_t *)DeviceObject;
    Length = a2->Length;
    DeviceExtension[3] = 0;
    DeviceExtension[3].MaximumLength = Length;
    DeviceExtension[3].Buffer = &DeviceExtension[5].Length;
    RtlCopyUnicodeString(DeviceExtension + 3, a2);
    v15 = a3->Length;
    v16 = (__int64)&DeviceExtension[5] + a2->Length;
    DeviceExtension[4] = 0;
    DeviceExtension[4].Buffer = (wchar_t *)v16;
    DeviceExtension[4].MaximumLength = v15;
    RtlCopyUnicodeString(DeviceExtension + 4, a3);
  }
  else if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 0x10) != 0 )
  {
    McTemplateU0sd_EtwWriteTransfer(v12, AttachDetachSup_c1838, "FltpCreateControlDeviceObject", v11);
  }
  if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 1886, 0) < 0 )
  {
    if ( DeviceObject )
      IoDeleteDevice(DeviceObject);
    *a5 = 0;
  }
  else
  {
    *a5 = DeviceObject;
  }
  return v11;
}

```

## disassembly

```asm
0x18004f284  mov     r11, rsp
0x18004f287  mov     [r11+10h], rbx
0x18004f28b  mov     [r11+18h], rbp
0x18004f28f  push    rsi
0x18004f290  push    rdi
0x18004f291  push    r14
0x18004f293  sub     rsp, 40h
0x18004f297  movzx   r10d, word ptr [rdx]
0x18004f29b  lea     rax, [r11+8]
0x18004f29f  mov     [r11-28h], rax
0x18004f2a3  mov     rsi, rdx
0x18004f2a6  movzx   edx, word ptr [r8]
0x18004f2aa  add     r10d, 50h ; 'P'
0x18004f2ae  mov     eax, [rcx+34h]
0x18004f2b1  mov     rbp, r9
0x18004f2b4  mov     r9d, [rcx+48h]; DeviceType
0x18004f2b8  mov     r14, r8
0x18004f2bb  mov     rcx, cs:DriverObject; DriverObject
0x18004f2c2  add     edx, r10d; DeviceExtensionSize
0x18004f2c5  mov     [rsp+58h+Exclusive], 0; Exclusive
0x18004f2ca  xor     r8d, r8d; DeviceName
0x18004f2cd  mov     qword ptr [r11+8], 0
0x18004f2d5  mov     [rsp+58h+DeviceCharacteristics], eax; DeviceCharacteristics
0x18004f2d9  call    cs:__imp_IoCreateDevice
0x18004f2e0  nop     dword ptr [rax+rax+00h]
0x18004f2e5  mov     r8d, 72Ch
0x18004f2eb  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x18004f2f2  mov     ecx, eax
0x18004f2f4  xor     r9d, r9d
0x18004f2f7  mov     edi, eax
0x18004f2f9  call    FltpDbgStatus
0x18004f2fe  test    eax, eax
0x18004f300  jns     short loc_18004F327
0x18004f302  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 10h
0x18004f309  jz      loc_18004F39B
0x18004f30f  mov     r9d, edi
0x18004f312  lea     r8, aFltpcreatecont; "FltpCreateControlDeviceObject"
0x18004f319  lea     rdx, AttachDetachSup_c1838
0x18004f320  call    McTemplateU0sd_EtwWriteTransfer
0x18004f325  jmp     short loc_18004F39B
0x18004f327  mov     rax, [rsp+58h+DeviceObject]
0x18004f32c  xorps   xmm0, xmm0
0x18004f32f  mov     rdx, rsi; SourceString
0x18004f332  mov     rbx, [rax+40h]
0x18004f336  mov     dword ptr [rbx], 50F106h
0x18004f33c  lea     rcx, [rbx+30h]; DestinationString
0x18004f340  mov     [rbx+10h], rbp
0x18004f344  mov     rax, [rsp+58h+DeviceObject]
0x18004f349  mov     [rbx+28h], rax
0x18004f34d  movzx   eax, word ptr [rsi]
0x18004f350  movups  xmmword ptr [rcx], xmm0
0x18004f353  mov     [rcx+2], ax
0x18004f357  lea     rax, [rbx+50h]
0x18004f35b  mov     [rcx+8], rax
0x18004f35f  call    cs:__imp_RtlCopyUnicodeString
0x18004f366  nop     dword ptr [rax+rax+00h]
0x18004f36b  movzx   eax, word ptr [rsi]
0x18004f36e  lea     rcx, [rbx+40h]; DestinationString
0x18004f372  movzx   r9d, word ptr [r14]
0x18004f376  lea     r8, [rbx+50h]
0x18004f37a  xorps   xmm0, xmm0
0x18004f37d  add     r8, rax
0x18004f380  movups  xmmword ptr [rcx], xmm0
0x18004f383  mov     rdx, r14; SourceString
0x18004f386  mov     [rcx+8], r8
0x18004f38a  mov     [rcx+2], r9w
0x18004f38f  call    cs:__imp_RtlCopyUnicodeString
0x18004f396  nop     dword ptr [rax+rax+00h]
0x18004f39b  mov     r8d, 75Eh
0x18004f3a1  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x18004f3a8  xor     r9d, r9d
0x18004f3ab  mov     ecx, edi
0x18004f3ad  call    FltpDbgStatus
0x18004f3b2  test    eax, eax
0x18004f3b4  js      short loc_18004F3C8
0x18004f3b6  mov     rcx, [rsp+58h+arg_20]
0x18004f3be  mov     rax, [rsp+58h+DeviceObject]
0x18004f3c3  mov     [rcx], rax
0x18004f3c6  jmp     short loc_18004F3ED
0x18004f3c8  mov     rcx, [rsp+58h+DeviceObject]; DeviceObject
0x18004f3cd  test    rcx, rcx
0x18004f3d0  jz      short loc_18004F3DE
0x18004f3d2  call    cs:__imp_IoDeleteDevice
0x18004f3d9  nop     dword ptr [rax+rax+00h]
0x18004f3de  mov     rax, [rsp+58h+arg_20]
0x18004f3e6  mov     qword ptr [rax], 0
0x18004f3ed  mov     rbx, [rsp+58h+arg_8]
0x18004f3f2  mov     eax, edi
0x18004f3f4  mov     rbp, [rsp+58h+arg_10]
0x18004f3f9  add     rsp, 40h
0x18004f3fd  pop     r14
0x18004f3ff  pop     rdi
0x18004f400  pop     rsi
0x18004f401  retn
```
