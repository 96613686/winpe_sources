# SecCreateDeviceObject

- ea: `0x1400450ec`
- end: `0x1400451de`
- name: `SecCreateDeviceObject`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, installer_update`

## callers

- `0x140045000`

## callees

- `0x140011650`
- `0x14002b374`
- `0x1400450ec`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400451bc`
- `ntoskrnl!IoDeleteDevice` at `0x1400451bc`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140045174`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140045174`
- `ntoskrnl!IoCreateDevice` at `0x140045154`
- `ntoskrnl!IoCreateDevice` at `0x140045154`

## pseudocode

```c
__int64 __fastcall SecCreateDeviceObject(struct _DRIVER_OBJECT *a1)
{
  NTSTATUS SymbolicLink; // ebx
  int v2; // eax
  struct _DEVICE_OBJECT *v3; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-18h] BYREF

  DeviceObject = 0;
  a1->DriverUnload = (PDRIVER_UNLOAD)SecDriverUnload;
  a1->MajorFunction[0] = (PDRIVER_DISPATCH)&SecDeviceOpen;
  a1->MajorFunction[14] = (PDRIVER_DISPATCH)&SecDeviceIoControl;
  SymbolicLink = IoCreateDevice(a1, 0, (PUNICODE_STRING)&DeviceName, 0x22u, 0x100u, 0, &DeviceObject);
  if ( SymbolicLink < 0
    || (SymbolicLink = IoCreateSymbolicLink((PUNICODE_STRING)&SymbolicLinkName, (PUNICODE_STRING)&DeviceName),
        SymbolicLink < 0) )
  {
    v3 = DeviceObject;
  }
  else
  {
    v2 = SecSetSymbolicLinkProtection(&SymbolicLinkName);
    SymbolicLink = 0;
    *((_QWORD *)SecData + 2) = DeviceObject;
    v3 = 0;
    DeviceObject = 0;
    if ( v2 >= 0 )
      SymbolicLink = v2;
  }
  if ( v3 )
    IoDeleteDevice(v3);
  return (unsigned int)SymbolicLink;
}

```

## disassembly

```asm
0x1400450ec  push    rbx
0x1400450ee  sub     rsp, 50h
0x1400450f2  mov     rax, cs:__security_cookie
0x1400450f9  xor     rax, rsp
0x1400450fc  mov     [rsp+58h+var_10], rax
0x140045101  lea     rax, SecDriverUnload
0x140045108  mov     [rsp+58h+var_18], 0
0x140045111  mov     [rcx+68h], rax
0x140045115  lea     r8, DeviceName; DeviceName
0x14004511c  lea     rax, SecDeviceOpen
0x140045123  mov     r9d, 22h ; '"'; DeviceType
0x140045129  mov     [rcx+70h], rax
0x14004512d  xor     edx, edx; DeviceExtensionSize
0x14004512f  lea     rax, SecDeviceIoControl
0x140045136  mov     [rcx+0E0h], rax
0x14004513d  lea     rax, [rsp+58h+var_18]
0x140045142  mov     [rsp+58h+DeviceObject], rax; DeviceObject
0x140045147  mov     [rsp+58h+Exclusive], 0; Exclusive
0x14004514c  mov     [rsp+58h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140045154  call    cs:__imp_IoCreateDevice
0x14004515b  nop     dword ptr [rax+rax+00h]
0x140045160  mov     ebx, eax
0x140045162  test    eax, eax
0x140045164  js      short loc_1400451B2
0x140045166  lea     rdx, DeviceName; DeviceName
0x14004516d  lea     rcx, SymbolicLinkName; SymbolicLinkName
0x140045174  call    cs:__imp_IoCreateSymbolicLink
0x14004517b  nop     dword ptr [rax+rax+00h]
0x140045180  mov     ebx, eax
0x140045182  test    eax, eax
0x140045184  js      short loc_1400451B2
0x140045186  lea     rcx, SymbolicLinkName
0x14004518d  call    SecSetSymbolicLinkProtection
0x140045192  mov     rcx, cs:SecData
0x140045199  xor     ebx, ebx
0x14004519b  mov     rdx, [rsp+58h+var_18]
0x1400451a0  mov     [rcx+10h], rdx
0x1400451a4  xor     ecx, ecx
0x1400451a6  test    eax, eax
0x1400451a8  mov     [rsp+58h+var_18], rcx
0x1400451ad  cmovns  ebx, eax
0x1400451b0  jmp     short loc_1400451B7
0x1400451b2  mov     rcx, [rsp+58h+var_18]; DeviceObject
0x1400451b7  test    rcx, rcx
0x1400451ba  jz      short loc_1400451C8
0x1400451bc  call    cs:__imp_IoDeleteDevice
0x1400451c3  nop     dword ptr [rax+rax+00h]
0x1400451c8  mov     eax, ebx
0x1400451ca  mov     rcx, [rsp+58h+var_10]
0x1400451cf  xor     rcx, rsp; StackCookie
0x1400451d2  call    __security_check_cookie
0x1400451d7  add     rsp, 50h
0x1400451db  pop     rbx
0x1400451dc  retn
```
