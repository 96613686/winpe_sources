# CActiveDirectoryProvider::`scalar deleting destructor'(uint)

- ea: `0x18001d980`
- end: `0x18001d9b1`
- name: `??_GCActiveDirectoryProvider@@UEAAPEAXI@Z`
- size: `49`
- prototype: `void *__fastcall(CActiveDirectoryProvider *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001d91c`
- `0x18001d980`

## import_xrefs

- `msvcrt!free` at `0x18001d99c`
- `msvcrt!free` at `0x18001d99c`

## pseudocode

```c
CActiveDirectoryProvider *__fastcall CActiveDirectoryProvider::`scalar deleting destructor'(
        CActiveDirectoryProvider *this,
        char a2)
{
  CActiveDirectoryProvider::~CActiveDirectoryProvider(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x18001d980  mov     [rsp+arg_0], rbx
0x18001d985  push    rdi
0x18001d986  sub     rsp, 20h
0x18001d98a  mov     ebx, edx
0x18001d98c  mov     rdi, rcx
0x18001d98f  call    ??1CActiveDirectoryProvider@@UEAA@XZ; CActiveDirectoryProvider::~CActiveDirectoryProvider(void)
0x18001d994  test    bl, 1
0x18001d997  jz      short loc_18001D9A3
0x18001d999  mov     rcx, rdi; Block
0x18001d99c  call    cs:__imp_free
0x18001d9a2  nop
0x18001d9a3  mov     rax, rdi
0x18001d9a6  mov     rbx, [rsp+28h+arg_0]
0x18001d9ab  add     rsp, 20h
0x18001d9af  pop     rdi
0x18001d9b0  retn
```
