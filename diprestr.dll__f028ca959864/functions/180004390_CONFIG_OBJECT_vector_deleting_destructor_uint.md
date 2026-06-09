# CONFIG_OBJECT::`vector deleting destructor'(uint)

- ea: `0x180004390`
- end: `0x1800043bf`
- name: `??_ECONFIG_OBJECT@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CONFIG_OBJECT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180001048`
- `0x180004108`
- `0x180004390`

## pseudocode

```c
CONFIG_OBJECT *__fastcall CONFIG_OBJECT::`vector deleting destructor'(CONFIG_OBJECT *this, char a2)
{
  CONFIG_OBJECT::~CONFIG_OBJECT(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004390  mov     [rsp+arg_0], rbx
0x180004395  push    rdi
0x180004396  sub     rsp, 20h
0x18000439a  mov     ebx, edx
0x18000439c  mov     rdi, rcx
0x18000439f  call    ??1CONFIG_OBJECT@@UEAA@XZ; CONFIG_OBJECT::~CONFIG_OBJECT(void)
0x1800043a4  test    bl, 1
0x1800043a7  jz      short loc_1800043B1
0x1800043a9  mov     rcx, rdi; Block
0x1800043ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043b1  mov     rbx, [rsp+28h+arg_0]
0x1800043b6  mov     rax, rdi
0x1800043b9  add     rsp, 20h
0x1800043bd  pop     rdi
0x1800043be  retn
```
