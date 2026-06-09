# CKernelFilterDriver::AddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x14000b0b0`
- end: `0x14000b1b6`
- name: `?AddDevice@CKernelFilterDriver@@CAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400041f0`
- `0x14000b0b0`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x14000b148`
- `ntoskrnl!IoCreateDevice` at `0x14000b148`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14000b0d1`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14000b0d1`

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
0x14000b0b0  mov     [rsp+arg_0], rbx
0x14000b0b5  mov     [rsp+arg_8], rsi
0x14000b0ba  push    rdi
0x14000b0bb  sub     rsp, 40h
0x14000b0bf  mov     rdi, rdx
0x14000b0c2  mov     [rsp+48h+arg_10], 0
0x14000b0ca  lea     rdx, ?AddDevice@CKernelFilterDriver@@CAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ClientIdentificationAddress
0x14000b0d1  call    cs:__imp_IoGetDriverObjectExtension
0x14000b0d8  nop     dword ptr [rax+rax+00h]
0x14000b0dd  mov     rbx, rax
0x14000b0e0  test    rax, rax
0x14000b0e3  jz      loc_14000B1A0
0x14000b0e9  mov     rcx, [rax]
0x14000b0ec  mov     rdx, rdi
0x14000b0ef  mov     r8, [rcx]
0x14000b0f2  mov     rax, [r8+8]
0x14000b0f6  lea     r8, [rsp+48h+arg_10]
0x14000b0fb  call    _guard_dispatch_icall
0x14000b100  test    al, al
0x14000b102  jz      loc_14000B19A
0x14000b108  mov     rcx, [rbx]
0x14000b10b  mov     rdx, rdi
0x14000b10e  mov     rax, [rcx]
0x14000b111  mov     rax, [rax]
0x14000b114  call    _guard_dispatch_icall
0x14000b119  mov     rbx, rax
0x14000b11c  test    rax, rax
0x14000b11f  jz      short loc_14000B1A0
0x14000b121  mov     rcx, [rax+20h]; DriverObject
0x14000b125  lea     rsi, [rax+28h]
0x14000b129  mov     r9d, 22h ; '"'; DeviceType
0x14000b12f  mov     [rsp+48h+DeviceObject], rsi; DeviceObject
0x14000b134  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14000b139  xor     r8d, r8d; DeviceName
0x14000b13c  mov     [rsp+48h+DeviceCharacteristics], 80h; DeviceCharacteristics
0x14000b144  lea     edx, [r9-1Ah]; DeviceExtensionSize
0x14000b148  call    cs:__imp_IoCreateDevice
0x14000b14f  nop     dword ptr [rax+rax+00h]
0x14000b154  test    eax, eax
0x14000b156  js      short loc_14000B182
0x14000b158  mov     rcx, [rsi]
0x14000b15b  mov     rdx, [rcx+40h]
0x14000b15f  mov     rcx, rbx
0x14000b162  mov     [rdx], rbx
0x14000b165  mov     rdx, rdi
0x14000b168  mov     [rsp+48h+arg_10], eax
0x14000b16c  mov     rax, [rbx]
0x14000b16f  mov     rax, [rax+50h]
0x14000b173  call    _guard_dispatch_icall
0x14000b178  mov     [rsp+48h+arg_10], eax
0x14000b17c  test    eax, eax
0x14000b17e  jns     short loc_14000B1A5
0x14000b180  jmp     short loc_14000B186
0x14000b182  mov     [rsp+48h+arg_10], eax
0x14000b186  mov     rax, [rbx]
0x14000b189  mov     edx, 1
0x14000b18e  mov     rcx, rbx
0x14000b191  mov     rax, [rax+48h]
0x14000b195  call    _guard_dispatch_icall
0x14000b19a  mov     eax, [rsp+48h+arg_10]
0x14000b19e  jmp     short loc_14000B1A5
0x14000b1a0  mov     eax, 0C0000001h
0x14000b1a5  mov     rbx, [rsp+48h+arg_0]
0x14000b1aa  mov     rsi, [rsp+48h+arg_8]
0x14000b1af  add     rsp, 40h
0x14000b1b3  pop     rdi
0x14000b1b4  retn
```
