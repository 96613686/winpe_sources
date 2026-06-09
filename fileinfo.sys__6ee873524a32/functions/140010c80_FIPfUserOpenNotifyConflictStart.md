# FIPfUserOpenNotifyConflictStart

- ea: `0x140010c80`
- end: `0x140010cc9`
- name: `FIPfUserOpenNotifyConflictStart`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140010c99`
- `ntoskrnl!KeSetEvent` at `0x140010c99`

## pseudocode

```c
__int64 __fastcall FIPfUserOpenNotifyConflictStart(__int64 a1, __int64 a2, void (**a3)())
{
  __int64 result; // rax

  KeSetEvent(*(PRKEVENT *)(a1 + 88), 0, 0);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 96));
  *a3 = FIPfUserOpenNotifyConflictEnd;
  result = 0;
  a3[1] = 0;
  return result;
}

```

## disassembly

```asm
0x140010c80  mov     [rsp+arg_0], rbx
0x140010c85  push    rdi
0x140010c86  sub     rsp, 20h
0x140010c8a  mov     rdi, r8
0x140010c8d  mov     rbx, rcx
0x140010c90  mov     rcx, [rcx+58h]; Event
0x140010c94  xor     r8d, r8d; Wait
0x140010c97  xor     edx, edx; Increment
0x140010c99  call    cs:__imp_KeSetEvent
0x140010ca0  nop     dword ptr [rax+rax+00h]
0x140010ca5  lock inc dword ptr [rbx+60h]
0x140010ca9  mov     rbx, [rsp+28h+arg_0]
0x140010cae  lea     rax, FIPfUserOpenNotifyConflictEnd
0x140010cb5  mov     [rdi], rax
0x140010cb8  xor     eax, eax
0x140010cba  mov     qword ptr [rdi+8], 0
0x140010cc2  add     rsp, 20h
0x140010cc6  pop     rdi
0x140010cc7  retn
```
