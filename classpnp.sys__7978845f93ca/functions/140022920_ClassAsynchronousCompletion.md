# ClassAsynchronousCompletion

- ea: `0x140022920`
- end: `0x1400229f2`
- name: `ClassAsynchronousCompletion`
- size: `210`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400134a0`
- `0x140016320`
- `0x1400176f8`
- `0x140022920`
- `0x140026640`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400229d7`
- `ntoskrnl!IoFreeIrp` at `0x1400229d7`
- `ntoskrnl!IoFreeMdl` at `0x1400229a4`
- `ntoskrnl!IoFreeMdl` at `0x1400229a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229c8`
- `ntoskrnl!MmUnlockPages` at `0x140022994`
- `ntoskrnl!MmUnlockPages` at `0x140022994`

## pseudocode

```c
NTSTATUS __stdcall ClassAsynchronousCompletion(PDEVICE_OBJECT DeviceObject, PIRP Irp, PVOID Context)
{
  PDEVICE_OBJECT v5; // rsi
  int v7; // eax
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rcx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v9; // rcx
  struct _MDL *MdlAddress; // rcx

  v5 = DeviceObject;
  if ( !Context )
    return -1073741811;
  if ( !DeviceObject )
    v5 = *(PDEVICE_OBJECT *)Context;
  v7 = *((unsigned __int8 *)Context + 10);
  if ( (_BYTE)v7 == 40 )
    v7 = *((_DWORD *)Context + 7);
  if ( !v7 && (*((_BYTE *)Context + 11) & 0x40) != 0 )
    ClasspReleaseQueue(*(_QWORD *)Context, 0);
  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)v5->DeviceExtension;
  if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0
    && PORT_ALLOCATED_SENSE(DeviceExtension, (PSCSI_REQUEST_BLOCK)((char *)Context + 8)) )
  {
    FREE_PORT_ALLOCATED_SENSE_BUFFER(v9, (PSCSI_REQUEST_BLOCK)((char *)Context + 8));
  }
  MdlAddress = Irp->MdlAddress;
  if ( MdlAddress )
  {
    MmUnlockPages(MdlAddress);
    IoFreeMdl(Irp->MdlAddress);
    Irp->MdlAddress = 0;
  }
  ClassReleaseRemoveLock(v5, Irp);
  ExFreePoolWithTag(Context, 0);
  IoFreeIrp(Irp);
  return -1073741802;
}

```

## disassembly

```asm
0x140022920  push    rbx
0x140022922  push    rbp
0x140022923  push    rsi
0x140022924  push    rdi
0x140022925  sub     rsp, 28h
0x140022929  mov     rdi, r8
0x14002292c  mov     rbp, rdx
0x14002292f  mov     rsi, rcx
0x140022932  test    r8, r8
0x140022935  jnz     short loc_140022941
0x140022937  mov     eax, 0C000000Dh
0x14002293c  jmp     loc_1400229E8
0x140022941  test    rcx, rcx
0x140022944  jnz     short loc_140022949
0x140022946  mov     rsi, [r8]
0x140022949  movzx   eax, byte ptr [r8+0Ah]
0x14002294e  cmp     al, 28h ; '('
0x140022950  jnz     short loc_140022956
0x140022952  mov     eax, [r8+1Ch]
0x140022956  test    eax, eax
0x140022958  jnz     short loc_14002296B
0x14002295a  test    byte ptr [r8+0Bh], 40h
0x14002295f  jz      short loc_14002296B
0x140022961  mov     rcx, [r8]; BugCheckParameter2
0x140022964  xor     edx, edx; Irp
0x140022966  call    ClasspReleaseQueue
0x14002296b  mov     rcx, [rsi+40h]; FdoExtension
0x14002296f  test    byte ptr [rcx+68h], 1
0x140022973  jz      short loc_14002298B
0x140022975  lea     rdx, [rdi+8]; Srb
0x140022979  call    PORT_ALLOCATED_SENSE
0x14002297e  test    al, al
0x140022980  jz      short loc_14002298B
0x140022982  lea     rdx, [rdi+8]; Srb
0x140022986  call    FREE_PORT_ALLOCATED_SENSE_BUFFER
0x14002298b  mov     rcx, [rbp+8]; MemoryDescriptorList
0x14002298f  test    rcx, rcx
0x140022992  jz      short loc_1400229B8
0x140022994  call    cs:__imp_MmUnlockPages
0x14002299b  nop     dword ptr [rax+rax+00h]
0x1400229a0  mov     rcx, [rbp+8]; Mdl
0x1400229a4  call    cs:__imp_IoFreeMdl
0x1400229ab  nop     dword ptr [rax+rax+00h]
0x1400229b0  mov     qword ptr [rbp+8], 0
0x1400229b8  mov     rdx, rbp; Tag
0x1400229bb  mov     rcx, rsi; DeviceObject
0x1400229be  call    ClassReleaseRemoveLock
0x1400229c3  xor     edx, edx; Tag
0x1400229c5  mov     rcx, rdi; P
0x1400229c8  call    cs:__imp_ExFreePoolWithTag
0x1400229cf  nop     dword ptr [rax+rax+00h]
0x1400229d4  mov     rcx, rbp; Irp
0x1400229d7  call    cs:__imp_IoFreeIrp
0x1400229de  nop     dword ptr [rax+rax+00h]
0x1400229e3  mov     eax, 0C0000016h
0x1400229e8  add     rsp, 28h
0x1400229ec  pop     rdi
0x1400229ed  pop     rsi
0x1400229ee  pop     rbp
0x1400229ef  pop     rbx
0x1400229f0  retn
```
