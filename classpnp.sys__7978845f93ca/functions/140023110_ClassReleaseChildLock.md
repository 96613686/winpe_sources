# ClassReleaseChildLock

- ea: `0x140023110`
- end: `0x140023146`
- name: `ClassReleaseChildLock`
- size: `54`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400228d4`
- `0x14002314c`
- `0x1400231f0`
- `0x140057890`
- `0x140058b98`

## callees

- `0x140023110`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140023134`
- `ntoskrnl!KeSetEvent` at `0x140023134`

## pseudocode

```c
void __stdcall ClassReleaseChildLock(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  if ( FdoExtension->ChildLockAcquisitionCount-- == 1 )
  {
    FdoExtension->ChildLockOwner = 0;
    KeSetEvent(&FdoExtension->ChildLock, 0, 0);
  }
}

```

## disassembly

```asm
0x140023110  sub     rsp, 28h
0x140023114  add     dword ptr [rcx+368h], 0FFFFFFFFh
0x14002311b  jnz     short loc_140023140
0x14002311d  mov     qword ptr [rcx+360h], 0
0x140023128  xor     r8d, r8d; Wait
0x14002312b  add     rcx, 348h; Event
0x140023132  xor     edx, edx; Increment
0x140023134  call    cs:__imp_KeSetEvent
0x14002313b  nop     dword ptr [rax+rax+00h]
0x140023140  add     rsp, 28h
0x140023144  retn
```
