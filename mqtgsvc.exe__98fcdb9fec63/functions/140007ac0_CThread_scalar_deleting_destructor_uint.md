# CThread::`scalar deleting destructor'(uint)

- ea: `0x140007ac0`
- end: `0x140007af1`
- name: `??_GCThread@@UEAAPEAXI@Z`
- size: `49`
- prototype: `CThread *__fastcall(CThread *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000799c`
- `0x140007ac0`

## import_xrefs

- `msvcrt!free` at `0x140007adc`
- `msvcrt!free` at `0x140007adc`

## pseudocode

```c
CThread *__fastcall CThread::`scalar deleting destructor'(CThread *this, char a2)
{
  CThread::~CThread(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x140007ac0  mov     [rsp+arg_0], rbx
0x140007ac5  push    rdi
0x140007ac6  sub     rsp, 20h
0x140007aca  mov     ebx, edx
0x140007acc  mov     rdi, rcx
0x140007acf  call    ??1CThread@@UEAA@XZ; CThread::~CThread(void)
0x140007ad4  test    bl, 1
0x140007ad7  jz      short loc_140007AE3
0x140007ad9  mov     rcx, rdi; Block
0x140007adc  call    cs:__imp_free
0x140007ae2  nop
0x140007ae3  mov     rax, rdi
0x140007ae6  mov     rbx, [rsp+28h+arg_0]
0x140007aeb  add     rsp, 20h
0x140007aef  pop     rdi
0x140007af0  retn
```
