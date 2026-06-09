# CKernelFilterDriver::AddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x14000a0b0`
- end: `0x14000a1b6`
- name: `?AddDevice@CKernelFilterDriver@@CAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140003770`
- `0x14000a0b0`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x14000a148`
- `ntoskrnl!IoCreateDevice` at `0x14000a148`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14000a0d1`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14000a0d1`

## pseudocode

```c
__int64 __fastcall CKernelFilterDriver::AddDevice(struct _DRIVER_OBJECT *a1, struct _DEVICE_OBJECT *a2)
{
  _QWORD *DriverObjectExtension; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rsi
  NTSTATUS Device; // eax
  __int64 result; // rax
  unsigned int v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  DriverObjectExtension = IoGetDriverObjectExtension(a1, CKernelFilterDriver::AddDevice);
  v4 = DriverObjectExtension;
  if ( DriverObjectExtension )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, struct _DEVICE_OBJECT *, unsigned int *))(*(_QWORD *)*DriverObjectExtension
                                                                                             + 8LL))(
            *DriverObjectExtension,
            a2,
            &v10) )
      return v10;
    v5 = (**(__int64 (__fastcall ***)(_QWORD, struct _DEVICE_OBJECT *))*v4)(*v4, a2);
    v6 = v5;
    if ( v5 )
    {
      v7 = v5 + 40;
      Device = IoCreateDevice(*(PDRIVER_OBJECT *)(v5 + 32), 8u, 0, 0x22u, 0x80u, 0, (PDEVICE_OBJECT *)(v5 + 40));
      if ( Device < 0 )
      {
        v10 = Device;
      }
      else
      {
        **(_QWORD **)(*(_QWORD *)v7 + 64LL) = v6;
        v10 = Device;
        result = (*(__int64 (__fastcall **)(__int64, struct _DEVICE_OBJECT *))(*(_QWORD *)v6 + 80LL))(v6, a2);
        v10 = result;
        if ( (int)result >= 0 )
          return result;
      }
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 72LL))(v6, 1);
      return v10;
    }
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14000a0b0  mov     [rsp+arg_0], rbx
0x14000a0b5  mov     [rsp+arg_8], rsi
0x14000a0ba  push    rdi
0x14000a0bb  sub     rsp, 40h
0x14000a0bf  mov     rdi, rdx
0x14000a0c2  mov     [rsp+48h+arg_10], 0
0x14000a0ca  lea     rdx, ?AddDevice@CKernelFilterDriver@@CAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ClientIdentificationAddress
0x14000a0d1  call    cs:__imp_IoGetDriverObjectExtension
0x14000a0d8  nop     dword ptr [rax+rax+00h]
0x14000a0dd  mov     rbx, rax
0x14000a0e0  test    rax, rax
0x14000a0e3  jz      loc_14000A1A0
0x14000a0e9  mov     rcx, [rax]
0x14000a0ec  mov     rdx, rdi
0x14000a0ef  mov     r8, [rcx]
0x14000a0f2  mov     rax, [r8+8]
0x14000a0f6  lea     r8, [rsp+48h+arg_10]
0x14000a0fb  call    _guard_dispatch_icall
0x14000a100  test    al, al
0x14000a102  jz      loc_14000A19A
0x14000a108  mov     rcx, [rbx]
0x14000a10b  mov     rdx, rdi
0x14000a10e  mov     rax, [rcx]
0x14000a111  mov     rax, [rax]
0x14000a114  call    _guard_dispatch_icall
0x14000a119  mov     rbx, rax
0x14000a11c  test    rax, rax
0x14000a11f  jz      short loc_14000A1A0
0x14000a121  mov     rcx, [rax+20h]; DriverObject
0x14000a125  lea     rsi, [rax+28h]
0x14000a129  mov     r9d, 22h ; '"'; DeviceType
0x14000a12f  mov     [rsp+48h+DeviceObject], rsi; DeviceObject
0x14000a134  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14000a139  xor     r8d, r8d; DeviceName
0x14000a13c  mov     [rsp+48h+DeviceCharacteristics], 80h; DeviceCharacteristics
0x14000a144  lea     edx, [r9-1Ah]; DeviceExtensionSize
0x14000a148  call    cs:__imp_IoCreateDevice
0x14000a14f  nop     dword ptr [rax+rax+00h]
0x14000a154  test    eax, eax
0x14000a156  js      short loc_14000A182
0x14000a158  mov     rcx, [rsi]
0x14000a15b  mov     rdx, [rcx+40h]
0x14000a15f  mov     rcx, rbx
0x14000a162  mov     [rdx], rbx
0x14000a165  mov     rdx, rdi
0x14000a168  mov     [rsp+48h+arg_10], eax
0x14000a16c  mov     rax, [rbx]
0x14000a16f  mov     rax, [rax+50h]
0x14000a173  call    _guard_dispatch_icall
0x14000a178  mov     [rsp+48h+arg_10], eax
0x14000a17c  test    eax, eax
0x14000a17e  jns     short loc_14000A1A5
0x14000a180  jmp     short loc_14000A186
0x14000a182  mov     [rsp+48h+arg_10], eax
0x14000a186  mov     rax, [rbx]
0x14000a189  mov     edx, 1
0x14000a18e  mov     rcx, rbx
0x14000a191  mov     rax, [rax+48h]
0x14000a195  call    _guard_dispatch_icall
0x14000a19a  mov     eax, [rsp+48h+arg_10]
0x14000a19e  jmp     short loc_14000A1A5
0x14000a1a0  mov     eax, 0C0000001h
0x14000a1a5  mov     rbx, [rsp+48h+arg_0]
0x14000a1aa  mov     rsi, [rsp+48h+arg_8]
0x14000a1af  add     rsp, 40h
0x14000a1b3  pop     rdi
0x14000a1b4  retn
```
