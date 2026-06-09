# STRING_QUEUE::~STRING_QUEUE(void)

- ea: `0x180004d40`
- end: `0x180004d60`
- name: `??1STRING_QUEUE@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(STRING_QUEUE *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004d70`
- `0x180008120`

## callees

- `0x180004d40`
- `0x180005160`
- `0x180005190`

## pseudocode

```c
void __fastcall STRING_QUEUE::~STRING_QUEUE(STRING_QUEUE *this)
{
  STRING_QUEUE_ITEM *v2; // rax
  unsigned int v3; // edx

  while ( 1 )
  {
    v2 = STRING_QUEUE::RemoveHead(this);
    if ( !v2 )
      break;
    STRING_QUEUE_ITEM::`scalar deleting destructor'(v2, v3);
  }
}

```

## disassembly

```asm
0x180004d40  push    rbx
0x180004d42  sub     rsp, 20h
0x180004d46  mov     rbx, rcx
0x180004d49  mov     rcx, rbx; this
0x180004d4c  call    ?RemoveHead@STRING_QUEUE@@QEAAPEAVSTRING_QUEUE_ITEM@@XZ; STRING_QUEUE::RemoveHead(void)
0x180004d51  test    rax, rax
0x180004d54  jnz     loc_1800073FA
0x180004d5a  add     rsp, 20h
0x180004d5e  pop     rbx
0x180004d5f  retn
0x1800073fa  mov     rcx, rax; this
0x1800073fd  call    ??_GSTRING_QUEUE_ITEM@@QEAAPEAXI@Z; STRING_QUEUE_ITEM::`scalar deleting destructor'(uint)
0x180007402  nop
0x180007403  jmp     loc_180004D49
```
