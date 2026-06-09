# DriverEntry

- ea: `0x14000f078`
- end: `0x14000f0cc`
- name: `DriverEntry`
- size: `84`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f010`

## callees

- `0x140005320`
- `0x14000f078`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000f0b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f0b7`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx

  DriverObject->DriverUnload = (PDRIVER_UNLOAD)NsippUnload;
  result = NsippCreateDevice(DriverObject);
  v3 = result;
  if ( result >= 0 )
  {
    _InterlockedIncrement(&DrvpReferenceCount);
    qword_14000A2A8 = (__int64)&NsippNotificationHandleList;
    NsippNotificationHandleList = &NsippNotificationHandleList;
    KeInitializeSpinLock(&NsippNotificationHandleListLock);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x14000f078  push    rbx
0x14000f07a  sub     rsp, 20h
0x14000f07e  lea     rax, NsippUnload
0x14000f085  mov     [rcx+68h], rax
0x14000f089  call    NsippCreateDevice
0x14000f08e  mov     ebx, eax
0x14000f090  test    eax, eax
0x14000f092  js      short loc_14000F0C5
0x14000f094  lock inc cs:DrvpReferenceCount
0x14000f09b  lea     rax, NsippNotificationHandleList
0x14000f0a2  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x14000f0a9  mov     cs:qword_14000A2A8, rax
0x14000f0b0  mov     cs:NsippNotificationHandleList, rax
0x14000f0b7  call    cs:__imp_KeInitializeSpinLock
0x14000f0be  nop     dword ptr [rax+rax+00h]
0x14000f0c3  mov     eax, ebx
0x14000f0c5  add     rsp, 20h
0x14000f0c9  pop     rbx
0x14000f0ca  retn
```
