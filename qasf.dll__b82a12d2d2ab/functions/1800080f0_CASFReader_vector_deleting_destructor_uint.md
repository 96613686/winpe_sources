# CASFReader::`vector deleting destructor'(uint)

- ea: `0x1800080f0`
- end: `0x180008124`
- name: `??_ECASFReader@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CASFReader *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180007f08`
- `0x1800080f0`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CASFReader::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int64 a2)
{
  char v2; // bl

  v2 = a2;
  CASFReader::~CASFReader(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800080f0  mov     [rsp+arg_0], rbx
0x1800080f5  push    rdi
0x1800080f6  sub     rsp, 20h
0x1800080fa  mov     ebx, edx
0x1800080fc  mov     rdi, rcx
0x1800080ff  call    ??1CASFReader@@UEAA@XZ; CASFReader::~CASFReader(void)
0x180008104  test    bl, 1
0x180008107  jz      short loc_180008116
0x180008109  mov     edx, 1F0h; unsigned __int64
0x18000810e  mov     rcx, rdi; void *
0x180008111  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008116  mov     rbx, [rsp+28h+arg_0]
0x18000811b  mov     rax, rdi
0x18000811e  add     rsp, 20h
0x180008122  pop     rdi
0x180008123  retn
```
