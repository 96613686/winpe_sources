# SdpDisconnect

- ea: `0x14001ad08`
- end: `0x14001ade2`
- name: `SdpDisconnect`
- size: `218`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b090`
- `0x14001b420`
- `0x14001b5b0`
- `0x14001b7a0`
- `0x14001b970`

## callees

- `0x14001a3a8`
- `0x14001ad08`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001add4`
- `ntoskrnl!IofCallDriver` at `0x14001add4`
- `ntoskrnl!ExAllocatePool2` at `0x14001ad2f`
- `ntoskrnl!ExAllocatePool2` at `0x14001ad2f`
- `ntoskrnl!ExFreePool` at `0x14001ad9a`
- `ntoskrnl!ExFreePool` at `0x14001ad9a`

## pseudocode

```c
__int64 __fastcall SdpDisconnect(
        PDEVICE_OBJECT DeviceObject,
        struct _DEVICE_OBJECT *a2,
        __int64 a3,
        _LIST_ENTRY *a4,
        _IRP *a5)
{
  _IRP *Pool2; // rax
  __int64 v10; // r9
  _IRP *v11; // rbx
  IRP *v12; // rax

  Pool2 = (_IRP *)ExAllocatePool2(64, 40, 1146311746);
  v11 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)&Pool2->Type = a3;
    Pool2->ThreadListEntry.Flink = a4;
    Pool2->AssociatedIrp.MasterIrp = a5;
    v12 = IrpBuildIoctlEx(
            (__int64)DeviceObject,
            a2,
            0,
            v10,
            0x410204u,
            Pool2,
            8u,
            0,
            (IO_COMPLETION_ROUTINE *)SdppDisconnectCompletionRoutine,
            Pool2);
    if ( v12 )
    {
      IofCallDriver(DeviceObject, v12);
      return 259;
    }
    ExFreePool(v11);
  }
  if ( a4 )
    ((void (__fastcall *)(_IRP *, __int64))a4)(a5, 3221225626LL);
  return 259;
}

```

## disassembly

```asm
0x14001ad08  push    rbx
0x14001ad0a  push    rbp
0x14001ad0b  push    rsi
0x14001ad0c  push    rdi
0x14001ad0d  push    r14
0x14001ad0f  push    r15
0x14001ad11  sub     rsp, 58h
0x14001ad15  mov     r15, rdx
0x14001ad18  mov     r14, r8
0x14001ad1b  mov     edx, 28h ; '('
0x14001ad20  mov     rsi, rcx
0x14001ad23  mov     r8d, 44535442h
0x14001ad29  mov     rdi, r9
0x14001ad2c  lea     ecx, [rdx+18h]
0x14001ad2f  call    cs:__imp_ExAllocatePool2
0x14001ad36  nop     dword ptr [rax+rax+00h]
0x14001ad3b  mov     rbp, [rsp+88h+arg_20]
0x14001ad43  mov     rbx, rax
0x14001ad46  test    rax, rax
0x14001ad49  jz      short loc_14001ADA6
0x14001ad4b  mov     [rsp+88h+var_40], rax
0x14001ad50  xor     r8d, r8d
0x14001ad53  mov     [rax], r14
0x14001ad56  mov     rdx, r15
0x14001ad59  mov     [rax+20h], rdi
0x14001ad5d  mov     rcx, rsi
0x14001ad60  mov     [rax+18h], rbp
0x14001ad64  lea     rax, SdppDisconnectCompletionRoutine
0x14001ad6b  mov     [rsp+88h+var_48], rax
0x14001ad70  mov     [rsp+88h+var_50], 0
0x14001ad78  mov     [rsp+88h+var_58], 8
0x14001ad80  mov     [rsp+88h+var_60], rbx
0x14001ad85  mov     [rsp+88h+var_68], 410204h
0x14001ad8d  call    IrpBuildIoctlEx
0x14001ad92  test    rax, rax
0x14001ad95  jnz     short loc_14001ADCE
0x14001ad97  mov     rcx, rbx; P
0x14001ad9a  call    cs:__imp_ExFreePool
0x14001ada1  nop     dword ptr [rax+rax+00h]
0x14001ada6  test    rdi, rdi
0x14001ada9  jz      short loc_14001ADBB
0x14001adab  mov     edx, 0C000009Ah
0x14001adb0  mov     rcx, rbp
0x14001adb3  mov     rax, rdi
0x14001adb6  call    _guard_dispatch_icall
0x14001adbb  mov     eax, 103h
0x14001adc0  add     rsp, 58h
0x14001adc4  pop     r15
0x14001adc6  pop     r14
0x14001adc8  pop     rdi
0x14001adc9  pop     rsi
0x14001adca  pop     rbp
0x14001adcb  pop     rbx
0x14001adcc  retn
0x14001adce  mov     rdx, rax; Irp
0x14001add1  mov     rcx, rsi; DeviceObject
0x14001add4  call    cs:__imp_IofCallDriver
0x14001addb  nop     dword ptr [rax+rax+00h]
0x14001ade0  jmp     short loc_14001ADBB
```
