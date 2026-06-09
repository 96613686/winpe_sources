# DriverEntry

- ea: `0x140018080`
- end: `0x14001821f`
- name: `DriverEntry`
- size: `415`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140018010`

## callees

- `0x140002240`
- `0x14000b008`
- `0x14001655c`
- `0x140018080`
- `0x140018228`
- `0x14001841c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400180bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400180bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400181fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400181fb`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1400181e4`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1400181e4`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  struct _FAST_IO_DISPATCH *Pool2; // rax
  struct _FAST_IO_DISPATCH *v5; // rdi
  int v6; // ebx
  PDEVICE_OBJECT v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  NpReadParameters();
  result = NpInitializeAliases();
  if ( result >= 0 )
  {
    Pool2 = (struct _FAST_IO_DISPATCH *)ExAllocatePool2(64, 224, 1936093262);
    v5 = Pool2;
    if ( !Pool2 )
    {
      v6 = -1073741670;
LABEL_7:
      NpUninitializeAliases();
      return v6;
    }
    memset(Pool2, 0, sizeof(struct _FAST_IO_DISPATCH));
    v5->SizeOfFastIoDispatch = 224;
    v5->FastIoRead = (PFAST_IO_READ)NpFastRead;
    NpfsDriverObject = DriverObject;
    v5->FastIoWrite = (PFAST_IO_WRITE)NpFastWrite;
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)NpFsdCreate;
    DriverObject->MajorFunction[1] = (PDRIVER_DISPATCH)NpFsdCreateNamedPipe;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)NpFsdClose;
    DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)NpFsdRead;
    DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)NpFsdWrite;
    DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)NpFsdQueryInformation;
    DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)NpFsdSetInformation;
    DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)&NpFsdQueryVolumeInformation;
    DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&NpFsdCleanup;
    DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)&NpFsdFlushBuffers;
    DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)NpFsdDirectoryControl;
    DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)NpFsdFileSystemControl;
    DriverObject->MajorFunction[20] = (PDRIVER_DISPATCH)NpFsdQuerySecurityInfo;
    DriverObject->MajorFunction[21] = (PDRIVER_DISPATCH)NpFsdSetSecurityInfo;
    v6 = NpCreateDevice(&v7);
    if ( v6 < 0
      || (DriverObject->FastIoDispatch = v5, result = PsAllocSiloContextSlot(0, &NpSiloSlot), v6 = result, result < 0) )
    {
      ExFreePoolWithTag(v5, 0);
      goto LABEL_7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018080  mov     [rsp+arg_0], rbx
0x140018085  mov     [rsp+arg_8], rsi
0x14001808a  push    rdi
0x14001808b  sub     rsp, 20h
0x14001808f  mov     rsi, rcx
0x140018092  mov     [rsp+28h+arg_10], 0
0x14001809b  call    NpReadParameters
0x1400180a0  call    NpInitializeAliases
0x1400180a5  test    eax, eax
0x1400180a7  js      loc_14001820E
0x1400180ad  mov     ebx, 0E0h
0x1400180b2  mov     r8d, 7366704Eh
0x1400180b8  mov     edx, ebx
0x1400180ba  mov     ecx, 40h ; '@'
0x1400180bf  call    cs:__imp_ExAllocatePool2
0x1400180c6  nop     dword ptr [rax+rax+00h]
0x1400180cb  mov     rdi, rax
0x1400180ce  test    rax, rax
0x1400180d1  jnz     short loc_1400180DD
0x1400180d3  mov     ebx, 0C000009Ah
0x1400180d8  jmp     loc_140018207
0x1400180dd  mov     r8, rbx; Size
0x1400180e0  xor     edx, edx; Val
0x1400180e2  mov     rcx, rdi; void *
0x1400180e5  call    memset
0x1400180ea  mov     [rdi], ebx
0x1400180ec  lea     rax, NpFastRead
0x1400180f3  mov     [rdi+10h], rax
0x1400180f7  lea     rcx, [rsp+28h+arg_10]
0x1400180fc  lea     rax, NpFastWrite
0x140018103  mov     cs:NpfsDriverObject, rsi
0x14001810a  mov     [rdi+18h], rax
0x14001810e  lea     rax, NpFsdCreate
0x140018115  mov     [rsi+70h], rax
0x140018119  lea     rax, NpFsdCreateNamedPipe
0x140018120  mov     [rsi+78h], rax
0x140018124  lea     rax, NpFsdClose
0x14001812b  mov     [rsi+80h], rax
0x140018132  lea     rax, NpFsdRead
0x140018139  mov     [rsi+88h], rax
0x140018140  lea     rax, NpFsdWrite
0x140018147  mov     [rsi+90h], rax
0x14001814e  lea     rax, NpFsdQueryInformation
0x140018155  mov     [rsi+98h], rax
0x14001815c  lea     rax, NpFsdSetInformation
0x140018163  mov     [rsi+0A0h], rax
0x14001816a  lea     rax, NpFsdQueryVolumeInformation
0x140018171  mov     [rsi+0C0h], rax
0x140018178  lea     rax, NpFsdCleanup
0x14001817f  mov     [rsi+100h], rax
0x140018186  lea     rax, NpFsdFlushBuffers
0x14001818d  mov     [rsi+0B8h], rax
0x140018194  lea     rax, NpFsdDirectoryControl
0x14001819b  mov     [rsi+0D0h], rax
0x1400181a2  lea     rax, NpFsdFileSystemControl
0x1400181a9  mov     [rsi+0D8h], rax
0x1400181b0  lea     rax, NpFsdQuerySecurityInfo
0x1400181b7  mov     [rsi+110h], rax
0x1400181be  lea     rax, NpFsdSetSecurityInfo
0x1400181c5  mov     [rsi+118h], rax
0x1400181cc  call    NpCreateDevice
0x1400181d1  mov     ebx, eax
0x1400181d3  test    eax, eax
0x1400181d5  js      short loc_1400181F6
0x1400181d7  lea     rdx, NpSiloSlot
0x1400181de  mov     [rsi+50h], rdi
0x1400181e2  xor     ecx, ecx
0x1400181e4  call    cs:__imp_PsAllocSiloContextSlot
0x1400181eb  nop     dword ptr [rax+rax+00h]
0x1400181f0  mov     ebx, eax
0x1400181f2  test    eax, eax
0x1400181f4  jns     short loc_14001820E
0x1400181f6  xor     edx, edx; Tag
0x1400181f8  mov     rcx, rdi; P
0x1400181fb  call    cs:__imp_ExFreePoolWithTag
0x140018202  nop     dword ptr [rax+rax+00h]
0x140018207  call    NpUninitializeAliases
0x14001820c  mov     eax, ebx
0x14001820e  mov     rbx, [rsp+28h+arg_0]
0x140018213  mov     rsi, [rsp+28h+arg_8]
0x140018218  add     rsp, 20h
0x14001821c  pop     rdi
0x14001821d  retn
```
