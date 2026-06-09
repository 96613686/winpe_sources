# WaitForThreadToDieAndCloseIt

- ea: `0x14001ae5c`
- end: `0x14001af0c`
- name: `WaitForThreadToDieAndCloseIt`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a7bc`
- `0x14001af90`

## callees

- `0x14001ae5c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001aeb7`
- `ntoskrnl!KeSetEvent` at `0x14001aeb7`
- `ntoskrnl!ObfDereferenceObject` at `0x14001aeea`
- `ntoskrnl!ObfDereferenceObject` at `0x14001aeea`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ae9b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ae9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001aed9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001aed9`
- `ntoskrnl!ZwClose` at `0x14001aef9`
- `ntoskrnl!ZwClose` at `0x14001aef9`

## pseudocode

```c
void WaitForThreadToDieAndCloseIt()
{
  HANDLE v0; // rbx
  PVOID Object; // [rsp+48h] [rbp+10h] BYREF

  v0 = hPassiveThread;
  Object = 0;
  if ( hPassiveThread )
  {
    if ( !ObReferenceObjectByHandle(hPassiveThread, 0, 0, 0, &Object, 0) )
    {
      KeSetEvent(&EventKillThread, 0, 0);
      KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      ObfDereferenceObject(Object);
    }
    ZwClose(v0);
  }
}

```

## disassembly

```asm
0x14001ae5c  mov     r11, rsp
0x14001ae5f  mov     [r11+10h], rdx
0x14001ae63  push    rbx
0x14001ae64  sub     rsp, 30h
0x14001ae68  mov     rbx, cs:hPassiveThread
0x14001ae6f  mov     qword ptr [r11+10h], 0
0x14001ae77  test    rbx, rbx
0x14001ae7a  jz      loc_14001AF05
0x14001ae80  lea     rax, [r11+10h]
0x14001ae84  mov     qword ptr [r11-10h], 0
0x14001ae8c  xor     r9d, r9d; AccessMode
0x14001ae8f  mov     [r11-18h], rax
0x14001ae93  xor     r8d, r8d; ObjectType
0x14001ae96  xor     edx, edx; DesiredAccess
0x14001ae98  mov     rcx, rbx; Handle
0x14001ae9b  call    cs:__imp_ObReferenceObjectByHandle
0x14001aea2  nop     dword ptr [rax+rax+00h]
0x14001aea7  test    eax, eax
0x14001aea9  jnz     short loc_14001AEF6
0x14001aeab  xor     r8d, r8d; Wait
0x14001aeae  lea     rcx, EventKillThread; Event
0x14001aeb5  xor     edx, edx; Increment
0x14001aeb7  call    cs:__imp_KeSetEvent
0x14001aebe  nop     dword ptr [rax+rax+00h]
0x14001aec3  mov     rcx, [rsp+38h+Object]; Object
0x14001aec8  xor     r9d, r9d; Alertable
0x14001aecb  xor     r8d, r8d; WaitMode
0x14001aece  mov     [rsp+38h+Timeout], 0; Timeout
0x14001aed7  xor     edx, edx; WaitReason
0x14001aed9  call    cs:__imp_KeWaitForSingleObject
0x14001aee0  nop     dword ptr [rax+rax+00h]
0x14001aee5  mov     rcx, [rsp+38h+Object]; Object
0x14001aeea  call    cs:__imp_ObfDereferenceObject
0x14001aef1  nop     dword ptr [rax+rax+00h]
0x14001aef6  mov     rcx, rbx; Handle
0x14001aef9  call    cs:__imp_ZwClose
0x14001af00  nop     dword ptr [rax+rax+00h]
0x14001af05  add     rsp, 30h
0x14001af09  pop     rbx
0x14001af0a  retn
```
