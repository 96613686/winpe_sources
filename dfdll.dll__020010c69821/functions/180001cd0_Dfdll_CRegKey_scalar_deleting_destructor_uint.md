# Dfdll::CRegKey::`scalar deleting destructor'(uint)

- ea: `0x180001cd0`
- end: `0x180001d04`
- name: `??_GCRegKey@Dfdll@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Dfdll::CRegKey *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x1800019f8`
- `0x180001cd0`
- `0x180012b30`

## pseudocode

```c
Dfdll::CRegKey *__fastcall Dfdll::CRegKey::`scalar deleting destructor'(
        Dfdll::CRegKey *this,
        const struct std::nothrow_t *a2)
{
  char v2; // bl

  v2 = (char)a2;
  Dfdll::CRegKey::~CRegKey(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x38);
  return this;
}

```

## disassembly

```asm
0x180001cd0  mov     [rsp+arg_0], rbx
0x180001cd5  push    rdi
0x180001cd6  sub     rsp, 20h
0x180001cda  mov     ebx, edx
0x180001cdc  mov     rdi, rcx
0x180001cdf  call    ??1CRegKey@Dfdll@@UEAA@XZ
0x180001ce4  test    bl, 1
0x180001ce7  jz      short loc_180001CF6
0x180001ce9  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x180001cee  mov     rcx, rdi; void *
0x180001cf1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180001cf6  mov     rbx, [rsp+28h+arg_0]
0x180001cfb  mov     rax, rdi
0x180001cfe  add     rsp, 20h
0x180001d02  pop     rdi
0x180001d03  retn
```
