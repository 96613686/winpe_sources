# OpenDevice

- ea: `0x140017fc0`
- end: `0x14001805a`
- name: `OpenDevice`
- size: `154`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, PFILE_OBJECT *, PDEVICE_OBJECT *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9a0`
- `0x14000fdb8`
- `0x140017a20`

## callees

- `0x140017fc0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001804c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001804c`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140017ff6`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140017ff6`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140018018`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140018018`

## pseudocode

```c
__int64 __fastcall OpenDevice(struct _UNICODE_STRING *a1, PFILE_OBJECT *a2, PDEVICE_OBJECT *a3)
{
  NTSTATUS DeviceObjectPointer; // ebx
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp+10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  *a2 = 0;
  DeviceObject = 0;
  FileObject = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(a1, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer >= 0 )
  {
    if ( !FileObject->FileName.Length )
    {
      *a3 = IoGetAttachedDeviceReference(FileObject->DeviceObject);
      *a2 = FileObject;
      return (unsigned int)DeviceObjectPointer;
    }
    DeviceObjectPointer = -1073741772;
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x140017fc0  mov     [rsp+arg_0], rbx
0x140017fc5  mov     [rsp+arg_18], rsi
0x140017fca  push    rdi
0x140017fcb  sub     rsp, 20h
0x140017fcf  xor     eax, eax
0x140017fd1  lea     r9, [rsp+28h+DeviceObject]; DeviceObject
0x140017fd6  mov     [r8], rax
0x140017fd9  mov     rdi, r8
0x140017fdc  mov     [rdx], rax
0x140017fdf  lea     r8, [rsp+28h+FileObject]; FileObject
0x140017fe4  mov     rsi, rdx
0x140017fe7  mov     [rsp+28h+DeviceObject], rax
0x140017fec  mov     edx, 80h; DesiredAccess
0x140017ff1  mov     [rsp+28h+FileObject], rax
0x140017ff6  call    cs:__imp_IoGetDeviceObjectPointer
0x140017ffd  nop     dword ptr [rax+rax+00h]
0x140018002  mov     rcx, [rsp+28h+FileObject]; Object
0x140018007  mov     ebx, eax
0x140018009  test    eax, eax
0x14001800b  js      short loc_140018047
0x14001800d  cmp     word ptr [rcx+58h], 0
0x140018012  jnz     short loc_140018042
0x140018014  mov     rcx, [rcx+8]; DeviceObject
0x140018018  call    cs:__imp_IoGetAttachedDeviceReference
0x14001801f  nop     dword ptr [rax+rax+00h]
0x140018024  mov     [rdi], rax
0x140018027  mov     rax, [rsp+28h+FileObject]
0x14001802c  mov     [rsi], rax
0x14001802f  mov     rsi, [rsp+28h+arg_18]
0x140018034  mov     eax, ebx
0x140018036  mov     rbx, [rsp+28h+arg_0]
0x14001803b  add     rsp, 20h
0x14001803f  pop     rdi
0x140018040  retn
0x140018042  mov     ebx, 0C0000034h
0x140018047  test    rcx, rcx
0x14001804a  jz      short loc_14001802F
0x14001804c  call    cs:__imp_ObfDereferenceObject
0x140018053  nop     dword ptr [rax+rax+00h]
0x140018058  jmp     short loc_14001802F
```
