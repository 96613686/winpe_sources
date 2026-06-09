# FatFsdDirectoryControl

- ea: `0x14002ea00`
- end: `0x14002eab1`
- name: `FatFsdDirectoryControl`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140005288`
- `0x14002e9ac`
- `0x14002ea00`
- `0x140039550`
- `0x14003960c`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002ea1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002ea1b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002ea8b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002ea8b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ea97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ea97`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14002ea39`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14002ea39`

## pseudocode

```c
__int64 __fastcall FatFsdDirectoryControl(__int64 a1, IRP *a2)
{
  BOOLEAN IsOperationSynchronous; // al
  unsigned int v4; // ebx
  _DWORD *Entry; // [rsp+28h] [rbp-10h]
  char IsIrpTopLevel; // [rsp+50h] [rbp+18h]

  KeEnterCriticalRegion();
  IsIrpTopLevel = FatIsIrpTopLevel(a2);
  IsOperationSynchronous = IoIsOperationSynchronous(a2);
  Entry = FatCreateIrpContext(a2, IsOperationSynchronous);
  v4 = FatCommonDirectoryControl(Entry, a2);
  if ( IsIrpTopLevel )
    IoSetTopLevelIrp(0);
  KeLeaveCriticalRegion();
  return v4;
}

```

## disassembly

```asm
0x14002ea00  mov     [rsp+arg_0], rbx
0x14002ea05  mov     [rsp+Irp], rdx
0x14002ea0a  push    rdi
0x14002ea0b  sub     rsp, 30h
0x14002ea0f  mov     rbx, rdx
0x14002ea12  mov     [rsp+38h+Entry], 0
0x14002ea1b  call    cs:__imp_KeEnterCriticalRegion
0x14002ea22  nop     dword ptr [rax+rax+00h]
0x14002ea27  mov     rcx, rbx; Irp
0x14002ea2a  call    FatIsIrpTopLevel
0x14002ea2f  mov     dil, al
0x14002ea32  mov     [rsp+38h+arg_10], al
0x14002ea36  mov     rcx, rbx; Irp
0x14002ea39  call    cs:__imp_IoIsOperationSynchronous
0x14002ea40  nop     dword ptr [rax+rax+00h]
0x14002ea45  mov     dl, al
0x14002ea47  mov     rcx, rbx
0x14002ea4a  call    FatCreateIrpContext
0x14002ea4f  mov     [rsp+38h+Entry], rax
0x14002ea54  mov     rdx, rbx
0x14002ea57  mov     rcx, rax
0x14002ea5a  call    FatCommonDirectoryControl
0x14002ea5f  mov     ebx, eax
0x14002ea61  mov     [rsp+38h+var_18], eax
0x14002ea65  jmp     short loc_14002EA84
0x14002ea67  mov     r8d, eax
0x14002ea6a  mov     rdx, [rsp+38h+Irp]; Irp
0x14002ea6f  mov     rcx, [rsp+38h+Entry]; Entry
0x14002ea74  call    FatProcessException
0x14002ea79  mov     ebx, eax
0x14002ea7b  mov     [rsp+38h+var_18], eax
0x14002ea7f  mov     dil, [rsp+38h+arg_10]
0x14002ea84  test    dil, dil
0x14002ea87  jz      short loc_14002EA97
0x14002ea89  xor     ecx, ecx; Irp
0x14002ea8b  call    cs:__imp_IoSetTopLevelIrp
0x14002ea92  nop     dword ptr [rax+rax+00h]
0x14002ea97  call    cs:__imp_KeLeaveCriticalRegion
0x14002ea9e  nop     dword ptr [rax+rax+00h]
0x14002eaa3  mov     eax, ebx
0x14002eaa5  mov     rbx, [rsp+38h+arg_0]
0x14002eaaa  add     rsp, 30h
0x14002eaae  pop     rdi
0x14002eaaf  retn
0x14005b9b6  push    rbp
0x14005b9b8  sub     rsp, 20h
0x14005b9bc  mov     rbp, rdx
0x14005b9bf  mov     rdx, rcx
0x14005b9c2  mov     rcx, [rbp+28h]
0x14005b9c6  call    FatExceptionFilter
0x14005b9cb  nop
0x14005b9cc  add     rsp, 20h
0x14005b9d0  pop     rbp
0x14005b9d1  retn
```
