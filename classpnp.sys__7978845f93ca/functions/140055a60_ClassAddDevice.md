# ClassAddDevice

- ea: `0x140055a60`
- end: `0x140055ada`
- name: `ClassAddDevice`
- size: `122`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140025074`
- `0x14003a2cc`
- `0x14003e470`
- `0x140055a60`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140055a7c`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140055a7c`

## pseudocode

```c
__int64 __fastcall ClassAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  __int64 (__fastcall **DriverObjectExtension)(PDRIVER_OBJECT, PDEVICE_OBJECT); // rsi
  __int64 result; // rax
  int v6; // eax
  unsigned int v7; // ebx

  DriverObjectExtension = (__int64 (__fastcall **)(PDRIVER_OBJECT, PDEVICE_OBJECT))IoGetDriverObjectExtension(
                                                                                     DriverObject,
                                                                                     ClassInitialize);
  result = ClassMpdevAddDevice(DriverObject, TargetDevice);
  if ( (int)result < 0 )
  {
    v6 = DriverObjectExtension[45](DriverObject, TargetDevice);
    v7 = v6;
    if ( v6 < 0 && !BootCompleted )
      ClasspLogBootError(1, (unsigned int)v6);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140055a60  mov     [rsp+arg_0], rbx
0x140055a65  mov     [rsp+arg_8], rsi
0x140055a6a  push    rdi
0x140055a6b  sub     rsp, 20h
0x140055a6f  mov     rdi, rdx
0x140055a72  mov     rbx, rcx
0x140055a75  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140055a7c  call    cs:__imp_IoGetDriverObjectExtension
0x140055a83  nop     dword ptr [rax+rax+00h]
0x140055a88  mov     rdx, rdi; TargetDevice
0x140055a8b  mov     rcx, rbx; DriverObject
0x140055a8e  mov     rsi, rax
0x140055a91  call    ClassMpdevAddDevice
0x140055a96  test    eax, eax
0x140055a98  jns     short loc_140055AC9
0x140055a9a  mov     rax, [rsi+168h]
0x140055aa1  mov     rdx, rdi
0x140055aa4  mov     rcx, rbx
0x140055aa7  call    _guard_dispatch_icall
0x140055aac  mov     ebx, eax
0x140055aae  test    eax, eax
0x140055ab0  jns     short loc_140055AC7
0x140055ab2  cmp     cs:BootCompleted, 0
0x140055ab9  jnz     short loc_140055AC7
0x140055abb  mov     edx, eax
0x140055abd  mov     ecx, 1
0x140055ac2  call    ClasspLogBootError
0x140055ac7  mov     eax, ebx
0x140055ac9  mov     rbx, [rsp+28h+arg_0]
0x140055ace  mov     rsi, [rsp+28h+arg_8]
0x140055ad3  add     rsp, 20h
0x140055ad7  pop     rdi
0x140055ad8  retn
```
