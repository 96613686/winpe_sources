# KbdHid_SetLedIndicatorsComplete

- ea: `0x140003f60`
- end: `0x140003ff3`
- name: `KbdHid_SetLedIndicatorsComplete`
- size: `147`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003f60`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140003f8e`
- `ntoskrnl!IoFreeMdl` at `0x140003f8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003fa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003fb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003fa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003fb8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003fd4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003fd4`

## pseudocode

```c
__int64 __fastcall KbdHid_SetLedIndicatorsComplete(PDEVICE_OBJECT DeviceObject, PIRP Irp, PVOID Context)
{
  char *DeviceExtension; // rsi

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  if ( Irp->PendingReturned )
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoFreeMdl(Irp->MdlAddress);
  Irp->MdlAddress = (PMDL)*((_QWORD *)Context + 1);
  ExFreePoolWithTag(*(PVOID *)Context, 0);
  ExFreePoolWithTag(Context, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 152), Irp, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x140003f60  mov     [rsp+arg_0], rbx
0x140003f65  mov     [rsp+arg_8], rsi
0x140003f6a  push    rdi
0x140003f6b  sub     rsp, 20h
0x140003f6f  cmp     byte ptr [rdx+41h], 0
0x140003f73  mov     rdi, r8
0x140003f76  mov     rsi, [rcx+40h]
0x140003f7a  mov     rbx, rdx
0x140003f7d  jz      short loc_140003F8A
0x140003f7f  mov     rax, [rdx+0B8h]
0x140003f86  or      byte ptr [rax+3], 1
0x140003f8a  mov     rcx, [rdx+8]; Mdl
0x140003f8e  call    cs:__imp_IoFreeMdl
0x140003f95  nop     dword ptr [rax+rax+00h]
0x140003f9a  mov     rax, [rdi+8]
0x140003f9e  xor     edx, edx; Tag
0x140003fa0  mov     [rbx+8], rax
0x140003fa4  mov     rcx, [rdi]; P
0x140003fa7  call    cs:__imp_ExFreePoolWithTag
0x140003fae  nop     dword ptr [rax+rax+00h]
0x140003fb3  xor     edx, edx; Tag
0x140003fb5  mov     rcx, rdi; P
0x140003fb8  call    cs:__imp_ExFreePoolWithTag
0x140003fbf  nop     dword ptr [rax+rax+00h]
0x140003fc4  lea     rcx, [rsi+98h]; RemoveLock
0x140003fcb  mov     r8d, 20h ; ' '; RemlockSize
0x140003fd1  mov     rdx, rbx; Tag
0x140003fd4  call    cs:__imp_IoReleaseRemoveLockEx
0x140003fdb  nop     dword ptr [rax+rax+00h]
0x140003fe0  mov     rbx, [rsp+28h+arg_0]
0x140003fe5  xor     eax, eax
0x140003fe7  mov     rsi, [rsp+28h+arg_8]
0x140003fec  add     rsp, 20h
0x140003ff0  pop     rdi
0x140003ff1  retn
```
