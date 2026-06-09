# ClassAcquireChildLock

- ea: `0x1400559f0`
- end: `0x140055a4c`
- name: `ClassAcquireChildLock`
- size: `92`
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

- `0x1400559f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140055a23`
- `ntoskrnl!KeWaitForSingleObject` at `0x140055a23`

## pseudocode

```c
void __stdcall ClassAcquireChildLock(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  if ( FdoExtension->ChildLockOwner != KeGetCurrentThread() )
  {
    KeWaitForSingleObject(&FdoExtension->ChildLock, Executive, 0, 0, 0);
    FdoExtension->ChildLockOwner = KeGetCurrentThread();
  }
  ++FdoExtension->ChildLockAcquisitionCount;
}

```

## disassembly

```asm
0x1400559f0  push    rbx
0x1400559f2  sub     rsp, 30h
0x1400559f6  mov     rax, gs:188h
0x1400559ff  mov     rbx, rcx
0x140055a02  cmp     [rcx+360h], rax
0x140055a09  jz      short loc_140055A3F
0x140055a0b  add     rcx, 348h; Object
0x140055a12  mov     [rsp+38h+Timeout], 0; Timeout
0x140055a1b  xor     r9d, r9d; Alertable
0x140055a1e  xor     r8d, r8d; WaitMode
0x140055a21  xor     edx, edx; WaitReason
0x140055a23  call    cs:__imp_KeWaitForSingleObject
0x140055a2a  nop     dword ptr [rax+rax+00h]
0x140055a2f  mov     rax, gs:188h
0x140055a38  mov     [rbx+360h], rax
0x140055a3f  inc     dword ptr [rbx+368h]
0x140055a45  add     rsp, 30h
0x140055a49  pop     rbx
0x140055a4a  retn
```
