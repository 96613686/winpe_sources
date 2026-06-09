# DiskReregWorker

- ea: `0x140011010`
- end: `0x140011112`
- name: `DiskReregWorker`
- size: `258`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400040a8`
- `0x140011010`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140011083`
- `ntoskrnl!IoFreeIrp` at `0x140011083`
- `ntoskrnl!ExInterlockedPopEntryList` at `0x14001102c`
- `ntoskrnl!ExInterlockedPopEntryList` at `0x14001102c`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140011050`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140011050`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011094`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011094`
- `ntoskrnl!IoFreeWorkItem` at `0x1400110fa`
- `ntoskrnl!IoFreeWorkItem` at `0x1400110fa`
- `ntoskrnl!IoFreeMdl` at `0x140011074`
- `ntoskrnl!IoFreeMdl` at `0x140011074`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140011064`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140011064`

## pseudocode

```c
void __fastcall DiskReregWorker(PDEVICE_OBJECT DeviceObject, struct _IO_WORKITEM *Context)
{
  PSINGLE_LIST_ENTRY v3; // rax
  PSINGLE_LIST_ENTRY v4; // rsi
  struct _DEVICE_OBJECT *Next; // rbx
  IRP *v6; // rdi
  NTSTATUS v7; // ebp

  do
  {
    v3 = ExInterlockedPopEntryList(&DiskReregHead, &DiskReregSpinlock);
    v4 = v3;
    if ( v3 )
    {
      Next = (struct _DEVICE_OBJECT *)v3[1].Next;
      v6 = (IRP *)v3[2].Next;
      v7 = IoWMIRegistrationControl(Next, 4u);
      ClassReleaseRemoveLock(Next, v6);
      IoFreeMdl(v6->MdlAddress);
      IoFreeIrp(v6);
      ExFreePoolWithTag(v4, 0);
      if ( v7 >= 0 )
        continue;
    }
    else
    {
      v7 = -1073741595;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_a9711c54c416383df697b4e008bb3725_Traceguids,
        (unsigned int)v7);
    }
  }
  while ( _InterlockedExchangeAdd(&DiskReregWorkItems, 0xFFFFFFFF) != 1 );
  IoFreeWorkItem(Context);
}

```

## disassembly

```asm
0x140011010  push    rbx
0x140011012  push    rbp
0x140011013  push    rsi
0x140011014  push    rdi
0x140011015  push    r14
0x140011017  sub     rsp, 20h
0x14001101b  mov     r14, rdx
0x14001101e  lea     rdx, DiskReregSpinlock; Lock
0x140011025  lea     rcx, DiskReregHead; ListHead
0x14001102c  call    cs:__imp_ExInterlockedPopEntryList
0x140011033  nop     dword ptr [rax+rax+00h]
0x140011038  mov     rsi, rax
0x14001103b  test    rax, rax
0x14001103e  jz      short loc_1400110A6
0x140011040  mov     rbx, [rax+8]
0x140011044  mov     edx, 4; Action
0x140011049  mov     rdi, [rax+10h]
0x14001104d  mov     rcx, rbx; DeviceObject
0x140011050  call    cs:__imp_IoWMIRegistrationControl
0x140011057  nop     dword ptr [rax+rax+00h]
0x14001105c  mov     rdx, rdi; Tag
0x14001105f  mov     rcx, rbx; DeviceObject
0x140011062  mov     ebp, eax
0x140011064  call    cs:__imp_ClassReleaseRemoveLock
0x14001106b  nop     dword ptr [rax+rax+00h]
0x140011070  mov     rcx, [rdi+8]; Mdl
0x140011074  call    cs:__imp_IoFreeMdl
0x14001107b  nop     dword ptr [rax+rax+00h]
0x140011080  mov     rcx, rdi; Irp
0x140011083  call    cs:__imp_IoFreeIrp
0x14001108a  nop     dword ptr [rax+rax+00h]
0x14001108f  xor     edx, edx; Tag
0x140011091  mov     rcx, rsi; P
0x140011094  call    cs:__imp_ExFreePoolWithTag
0x14001109b  nop     dword ptr [rax+rax+00h]
0x1400110a0  test    ebp, ebp
0x1400110a2  jns     short loc_1400110E3
0x1400110a4  jmp     short loc_1400110AB
0x1400110a6  mov     ebp, 0C00000E5h
0x1400110ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110b2  lea     rax, WPP_GLOBAL_Control
0x1400110b9  cmp     rcx, rax
0x1400110bc  jz      short loc_1400110E3
0x1400110be  mov     eax, [rcx+2Ch]
0x1400110c1  test    al, 1
0x1400110c3  jz      short loc_1400110E3
0x1400110c5  cmp     byte ptr [rcx+29h], 2
0x1400110c9  jb      short loc_1400110E3
0x1400110cb  mov     rcx, [rcx+18h]
0x1400110cf  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x1400110d6  mov     edx, 11h
0x1400110db  mov     r9d, ebp
0x1400110de  call    WPP_SF_D
0x1400110e3  or      eax, 0FFFFFFFFh
0x1400110e6  lock xadd cs:DiskReregWorkItems, eax
0x1400110ee  cmp     eax, 1
0x1400110f1  jnz     loc_14001101E
0x1400110f7  mov     rcx, r14; IoWorkItem
0x1400110fa  call    cs:__imp_IoFreeWorkItem
0x140011101  nop     dword ptr [rax+rax+00h]
0x140011106  add     rsp, 20h
0x14001110a  pop     r14
0x14001110c  pop     rdi
0x14001110d  pop     rsi
0x14001110e  pop     rbp
0x14001110f  pop     rbx
0x140011110  retn
```
