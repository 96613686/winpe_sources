# CGhostThread::CGhostThread(void)

- ea: `0x1800082bc`
- end: `0x18000830b`
- name: `??0CGhostThread@@QEAA@XZ`
- size: `79`
- prototype: `CGhostThread *__fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007d0c`

## callees

- `0x1800032d8`
- `0x1800059f4`
- `0x180009f30`

## pseudocode

```c
CGhostThread *__fastcall CGhostThread::CGhostThread(CGhostThread *this)
{
  CCountedObject::CCountedObject(this);
  *(_QWORD *)this = &CGhostThread::`vftable';
  CLock::CLock((CGhostThread *)((char *)this + 16));
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  CDynamicCountedObjectArray::CDynamicCountedObjectArray((CGhostThread *)((char *)this + 112));
  return this;
}

```

## disassembly

```asm
0x1800082bc  push    rbx
0x1800082be  sub     rsp, 20h
0x1800082c2  mov     rbx, rcx
0x1800082c5  call    ??0CCountedObject@@IEAA@XZ; CCountedObject::CCountedObject(void)
0x1800082ca  lea     rcx, ??_7CGhostThread@@6B@; const CGhostThread::`vftable'
0x1800082d1  mov     [rbx], rcx
0x1800082d4  lea     rcx, [rbx+10h]; this
0x1800082d8  call    ??0CLock@@QEAA@XZ; CLock::CLock(void)
0x1800082dd  xor     eax, eax
0x1800082df  lea     rcx, [rbx+70h]; this
0x1800082e3  mov     [rbx+38h], eax
0x1800082e6  mov     [rbx+40h], rax
0x1800082ea  mov     [rbx+48h], rax
0x1800082ee  mov     [rbx+50h], rax
0x1800082f2  mov     [rbx+58h], rax
0x1800082f6  mov     [rbx+60h], rax
0x1800082fa  mov     [rbx+68h], eax
0x1800082fd  call    ??0CDynamicCountedObjectArray@@QEAA@XZ; CDynamicCountedObjectArray::CDynamicCountedObjectArray(void)
0x180008302  mov     rax, rbx
0x180008305  add     rsp, 20h
0x180008309  pop     rbx
0x18000830a  retn
```
