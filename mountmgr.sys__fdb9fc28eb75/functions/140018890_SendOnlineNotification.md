# SendOnlineNotification

- ea: `0x140018890`
- end: `0x140018a10`
- name: `SendOnlineNotification`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001420`
- `0x140014fc0`

## callees

- `0x140001ae0`
- `0x140017bf0`
- `0x140018890`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400189e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400189f3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400189e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400189f3`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400188bd`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400188bd`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001890f`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001890f`

## pseudocode

```c
NTSTATUS __fastcall SendOnlineNotification(struct _UNICODE_STRING *a1, char a2)
{
  NTSTATUS result; // eax
  __int64 v4; // r8
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rax
  struct _DEVICE_OBJECT *v6; // r10
  NTSTATUS v7; // eax
  __int64 v8; // r8
  NTSTATUS v9; // eax
  __int64 v10; // r8
  PDEVICE_OBJECT DeviceObject; // [rsp+60h] [rbp+18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+68h] [rbp+20h] BYREF

  FileObject = 0;
  DeviceObject = 0;
  result = IoGetDeviceObjectPointer(a1, 0x80u, &FileObject, &DeviceObject);
  if ( result >= 0 )
  {
    AttachedDeviceReference = IoGetAttachedDeviceReference(FileObject->DeviceObject);
    DeviceObject = AttachedDeviceReference;
    v6 = AttachedDeviceReference;
    if ( a2 )
    {
      v7 = MountMgrSendDeviceControl(AttachedDeviceReference, 0x56C008u, 0, 0, 0, 0, FileObject);
      if ( v7 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xA6u, v8, v7);
      }
      v6 = DeviceObject;
    }
    v9 = MountMgrSendDeviceControl(v6, 0x56C064u, 0, 0, 0, 0, FileObject);
    if ( v9 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xA7u, v10, v9);
    }
    ObfDereferenceObject(DeviceObject);
    return ObfDereferenceObject(FileObject);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    return WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xA5u, v4, result);
  }
  return result;
}

```

## disassembly

```asm
0x140018890  mov     [rsp+arg_0], rbx
0x140018895  mov     [rsp+arg_8], rsi
0x14001889a  push    rdi
0x14001889b  sub     rsp, 40h
0x14001889f  movzx   ebx, dl
0x1400188a2  lea     r9, [rsp+48h+DeviceObject]; DeviceObject
0x1400188a7  xor     esi, esi
0x1400188a9  lea     r8, [rsp+48h+FileObject]; FileObject
0x1400188ae  mov     edx, 80h; DesiredAccess
0x1400188b3  mov     [rsp+48h+FileObject], rsi
0x1400188b8  mov     [rsp+48h+DeviceObject], rsi
0x1400188bd  call    cs:__imp_IoGetDeviceObjectPointer
0x1400188c4  nop     dword ptr [rax+rax+00h]
0x1400188c9  test    eax, eax
0x1400188cb  jns     short loc_140018906
0x1400188cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188d4  lea     rdi, WPP_GLOBAL_Control
0x1400188db  cmp     rcx, rdi
0x1400188de  jz      loc_1400189FF
0x1400188e4  mov     edx, [rcx+2Ch]
0x1400188e7  test    dl, 1
0x1400188ea  jz      loc_1400189FF
0x1400188f0  mov     rcx, [rcx+18h]
0x1400188f4  mov     edx, 0A5h
0x1400188f9  mov     r9d, eax
0x1400188fc  call    WPP_SF_L
0x140018901  jmp     loc_1400189FF
0x140018906  mov     rcx, [rsp+48h+FileObject]
0x14001890b  mov     rcx, [rcx+8]; DeviceObject
0x14001890f  call    cs:__imp_IoGetAttachedDeviceReference
0x140018916  nop     dword ptr [rax+rax+00h]
0x14001891b  mov     [rsp+48h+DeviceObject], rax
0x140018920  lea     rdi, WPP_GLOBAL_Control
0x140018927  mov     r10, rax
0x14001892a  test    bl, bl
0x14001892c  jz      short loc_140018988
0x14001892e  mov     rcx, [rsp+48h+FileObject]
0x140018933  xor     r9d, r9d; InputBufferLength
0x140018936  mov     [rsp+48h+var_18], rcx; __int64
0x14001893b  xor     r8d, r8d; InputBuffer
0x14001893e  mov     [rsp+48h+var_20], esi; ULONG
0x140018942  mov     rcx, rax; DeviceObject
0x140018945  mov     edx, 56C008h; IoControlCode
0x14001894a  mov     [rsp+48h+var_28], rsi; PVOID
0x14001894f  call    MountMgrSendDeviceControl
0x140018954  test    eax, eax
0x140018956  jns     short loc_140018983
0x140018958  mov     rcx, cs:WPP_GLOBAL_Control
0x14001895f  cmp     rcx, rdi
0x140018962  jz      short loc_140018983
0x140018964  mov     edx, [rcx+2Ch]
0x140018967  test    dl, 1
0x14001896a  jz      short loc_140018983
0x14001896c  cmp     byte ptr [rcx+29h], 1
0x140018970  jb      short loc_140018983
0x140018972  mov     rcx, [rcx+18h]
0x140018976  mov     edx, 0A6h
0x14001897b  mov     r9d, eax
0x14001897e  call    WPP_SF_L
0x140018983  mov     r10, [rsp+48h+DeviceObject]
0x140018988  mov     rax, [rsp+48h+FileObject]
0x14001898d  xor     r9d, r9d; InputBufferLength
0x140018990  mov     [rsp+48h+var_18], rax; __int64
0x140018995  xor     r8d, r8d; InputBuffer
0x140018998  mov     [rsp+48h+var_20], esi; ULONG
0x14001899c  mov     edx, 56C064h; IoControlCode
0x1400189a1  mov     rcx, r10; DeviceObject
0x1400189a4  mov     [rsp+48h+var_28], rsi; PVOID
0x1400189a9  call    MountMgrSendDeviceControl
0x1400189ae  test    eax, eax
0x1400189b0  jns     short loc_1400189DD
0x1400189b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400189b9  cmp     rcx, rdi
0x1400189bc  jz      short loc_1400189DD
0x1400189be  mov     edx, [rcx+2Ch]
0x1400189c1  test    dl, 1
0x1400189c4  jz      short loc_1400189DD
0x1400189c6  cmp     byte ptr [rcx+29h], 1
0x1400189ca  jb      short loc_1400189DD
0x1400189cc  mov     rcx, [rcx+18h]
0x1400189d0  mov     edx, 0A7h
0x1400189d5  mov     r9d, eax
0x1400189d8  call    WPP_SF_L
0x1400189dd  mov     rcx, [rsp+48h+DeviceObject]; Object
0x1400189e2  call    cs:__imp_ObfDereferenceObject
0x1400189e9  nop     dword ptr [rax+rax+00h]
0x1400189ee  mov     rcx, [rsp+48h+FileObject]; Object
0x1400189f3  call    cs:__imp_ObfDereferenceObject
0x1400189fa  nop     dword ptr [rax+rax+00h]
0x1400189ff  mov     rbx, [rsp+48h+arg_0]
0x140018a04  mov     rsi, [rsp+48h+arg_8]
0x140018a09  add     rsp, 40h
0x140018a0d  pop     rdi
0x140018a0e  retn
```
