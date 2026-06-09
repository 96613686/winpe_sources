# PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)

- ea: `0x140023aa0`
- end: `0x140023c6e`
- name: `?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z`
- size: `462`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int, ULONG, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400261fc`

## callees

- `0x140010f20`
- `0x140023aa0`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140023bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023c60`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023c3e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023c3e`
- `ntoskrnl!IofCallDriver` at `0x140023b65`
- `ntoskrnl!IofCallDriver` at `0x140023b65`
- `ntoskrnl!KeInitializeEvent` at `0x140023b04`
- `ntoskrnl!KeInitializeEvent` at `0x140023b04`
- `ntoskrnl!ExAllocatePool2` at `0x140023b96`
- `ntoskrnl!ExAllocatePool2` at `0x140023b96`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140023b4a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140023b4a`

## pseudocode

```c
__int64 __fastcall PmQueryStorageProperty(struct _DEVICE_EXTENSION *a1, unsigned int a2, ULONG a3, void **a4)
{
  struct _DEVICE_OBJECT *v4; // rbx
  IRP *v9; // rax
  NTSTATUS Status; // ebx
  _DWORD *Pool2; // rax
  _DWORD *v12; // rdi
  struct _DEVICE_OBJECT *v13; // rcx
  ULONG OutputBuffer[2]; // [rsp+50h] [rbp-29h] BYREF
  struct _KEVENT Event; // [rsp+58h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _BYTE InputBuffer[12]; // [rsp+80h] [rbp+7h] BYREF

  v4 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 2);
  *(_DWORD *)InputBuffer = a2;
  *(_QWORD *)OutputBuffer = 0;
  *(_QWORD *)&InputBuffer[4] = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v9 = IoBuildDeviceIoControlRequest(0x2D1400u, v4, InputBuffer, 0xCu, OutputBuffer, 8u, 0, &Event, &IoStatusBlock);
  if ( !v9 )
    return (unsigned int)-1073741670;
  Status = IofCallDriver(v4, v9);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( Status >= 0 )
  {
    if ( OutputBuffer[1] > a3 )
      a3 = OutputBuffer[1];
    Pool2 = (_DWORD *)ExAllocatePool2(64, a3, 1112108368);
    v12 = Pool2;
    if ( Pool2 )
    {
      v13 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 2);
      *(_QWORD *)InputBuffer = a2;
      Status = PmSendDeviceControl(v13, 0x2D1400u, InputBuffer, 0xCu, Pool2, a3, 0);
      if ( Status >= 0 )
      {
        if ( v12[1] != a3 )
          v12[1] = a3;
        if ( *a4 )
          ExFreePoolWithTag(*a4, 0);
        *a4 = v12;
      }
      else
      {
        ExFreePoolWithTag(v12, 0);
      }
      return (unsigned int)Status;
    }
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140023aa0  push    rbp
0x140023aa2  push    rbx
0x140023aa3  push    rsi
0x140023aa4  push    rdi
0x140023aa5  push    r12
0x140023aa7  push    r14
0x140023aa9  push    r15
0x140023aab  lea     rbp, [rsp-27h]
0x140023ab0  sub     rsp, 0A0h
0x140023ab7  mov     rax, cs:__security_cookie
0x140023abe  xor     rax, rsp
0x140023ac1  mov     [rbp+57h+var_40], rax
0x140023ac5  mov     rbx, [rcx+10h]
0x140023ac9  xor     eax, eax
0x140023acb  mov     [rbp+57h+InputBuffer], rax
0x140023acf  xorps   xmm0, xmm0
0x140023ad2  mov     dword ptr [rbp+57h+InputBuffer], edx
0x140023ad5  mov     esi, r8d
0x140023ad8  mov     r12d, edx
0x140023adb  mov     qword ptr [rbp+57h+var_80], 0
0x140023ae3  mov     r15, rcx
0x140023ae6  mov     [rbp+57h+InputBuffer+4], rax
0x140023aea  xor     edx, edx; Type
0x140023aec  mov     dword ptr [rbp+57h+Event.Header], eax
0x140023aef  xor     r8d, r8d; State
0x140023af2  mov     dword ptr [rbp+57h+Event.Header.WaitListHead.Blink+4], eax
0x140023af5  lea     rcx, [rbp+57h+Event]; Event
0x140023af9  mov     r14, r9
0x140023afc  movups  xmmword ptr [rbp+57h+Event.Header.SignalState], xmm0
0x140023b00  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x140023b04  call    cs:__imp_KeInitializeEvent
0x140023b0b  nop     dword ptr [rax+rax+00h]
0x140023b10  lea     rax, [rbp+57h+var_60]
0x140023b14  mov     r9d, 0Ch; InputBufferLength
0x140023b1a  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x140023b1f  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x140023b23  lea     rax, [rbp+57h+Event]
0x140023b27  mov     rdx, rbx; DeviceObject
0x140023b2a  mov     [rsp+0D0h+var_98], rax; Event
0x140023b2f  mov     ecx, 2D1400h; IoControlCode
0x140023b34  mov     [rsp+0D0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140023b39  lea     rax, [rbp+57h+var_80]
0x140023b3d  mov     [rsp+0D0h+OutputBufferLength], 8; OutputBufferLength
0x140023b45  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x140023b4a  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140023b51  nop     dword ptr [rax+rax+00h]
0x140023b56  test    rax, rax
0x140023b59  jz      loc_140023C52
0x140023b5f  mov     rdx, rax; Irp
0x140023b62  mov     rcx, rbx; DeviceObject
0x140023b65  call    cs:__imp_IofCallDriver
0x140023b6c  nop     dword ptr [rax+rax+00h]
0x140023b71  mov     ebx, eax
0x140023b73  cmp     eax, 103h
0x140023b78  jz      loc_140023C29
0x140023b7e  test    ebx, ebx
0x140023b80  js      short loc_140023BF6
0x140023b82  cmp     [rbp+57h+var_80+4], esi
0x140023b85  mov     ecx, 40h ; '@'
0x140023b8a  mov     r8d, 42496D50h
0x140023b90  cmova   esi, [rbp+57h+var_80+4]
0x140023b94  mov     edx, esi
0x140023b96  call    cs:__imp_ExAllocatePool2
0x140023b9d  nop     dword ptr [rax+rax+00h]
0x140023ba2  mov     rdi, rax
0x140023ba5  test    rax, rax
0x140023ba8  jz      loc_140023C52
0x140023bae  mov     rcx, [r15+10h]; DeviceObject
0x140023bb2  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x140023bb6  mov     [rsp+0D0h+InternalDeviceIoControl], 0; BOOLEAN
0x140023bbb  mov     r9d, 0Ch; InputBufferLength
0x140023bc1  mov     [rsp+0D0h+OutputBufferLength], esi; ULONG
0x140023bc5  mov     edx, 2D1400h; IoControlCode
0x140023bca  mov     [rsp+0D0h+OutputBuffer], rax; PVOID
0x140023bcf  mov     dword ptr [rbp+57h+InputBuffer], r12d
0x140023bd3  mov     dword ptr [rbp+57h+InputBuffer+4], 0
0x140023bda  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140023bdf  mov     ebx, eax
0x140023be1  test    eax, eax
0x140023be3  jns     short loc_140023C17
0x140023be5  xor     edx, edx; Tag
0x140023be7  mov     rcx, rdi; P
0x140023bea  call    cs:__imp_ExFreePoolWithTag
0x140023bf1  nop     dword ptr [rax+rax+00h]
0x140023bf6  mov     eax, ebx
0x140023bf8  mov     rcx, [rbp+57h+var_40]
0x140023bfc  xor     rcx, rsp; StackCookie
0x140023bff  call    __security_check_cookie
0x140023c04  add     rsp, 0A0h
0x140023c0b  pop     r15
0x140023c0d  pop     r14
0x140023c0f  pop     r12
0x140023c11  pop     rdi
0x140023c12  pop     rsi
0x140023c13  pop     rbx
0x140023c14  pop     rbp
0x140023c15  retn
0x140023c17  cmp     [rdi+4], esi
0x140023c1a  jnz     short loc_140023C59
0x140023c1c  mov     rcx, [r14]; P
0x140023c1f  test    rcx, rcx
0x140023c22  jnz     short loc_140023C5E
0x140023c24  mov     [r14], rdi
0x140023c27  jmp     short loc_140023BF6
0x140023c29  xor     r9d, r9d; Alertable
0x140023c2c  mov     [rsp+0D0h+OutputBuffer], 0; Timeout
0x140023c35  xor     r8d, r8d; WaitMode
0x140023c38  lea     rcx, [rbp+57h+Event]; Object
0x140023c3c  xor     edx, edx; WaitReason
0x140023c3e  call    cs:__imp_KeWaitForSingleObject
0x140023c45  nop     dword ptr [rax+rax+00h]
0x140023c4a  mov     ebx, dword ptr [rbp+57h+var_60]
0x140023c4d  jmp     loc_140023B7E
0x140023c52  mov     ebx, 0C000009Ah
0x140023c57  jmp     short loc_140023BF6
0x140023c59  mov     [rdi+4], esi
0x140023c5c  jmp     short loc_140023C1C
0x140023c5e  xor     edx, edx; Tag
0x140023c60  call    cs:__imp_ExFreePoolWithTag
0x140023c67  nop     dword ptr [rax+rax+00h]
0x140023c6c  jmp     short loc_140023C24
```
