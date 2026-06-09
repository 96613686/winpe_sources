# Dfdll::CShortcutFile::`vector deleting destructor'(uint)

- ea: `0x1800092d0`
- end: `0x180009304`
- name: `??_ECShortcutFile@Dfdll@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Dfdll::CShortcutFile *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180008c6c`
- `0x1800092d0`
- `0x180012b30`

## pseudocode

```c
Dfdll::CShortcutFile *__fastcall Dfdll::CShortcutFile::`vector deleting destructor'(
        Dfdll::CShortcutFile *this,
        const struct std::nothrow_t *a2)
{
  char v2; // bl

  v2 = (char)a2;
  Dfdll::CShortcutFile::~CShortcutFile(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x88);
  return this;
}

```

## disassembly

```asm
0x1800092d0  mov     [rsp+arg_0], rbx
0x1800092d5  push    rdi
0x1800092d6  sub     rsp, 20h
0x1800092da  mov     ebx, edx
0x1800092dc  mov     rdi, rcx
0x1800092df  call    ??1CShortcutFile@Dfdll@@UEAA@XZ
0x1800092e4  test    bl, 1
0x1800092e7  jz      short loc_1800092F6
0x1800092e9  mov     edx, 88h; struct std::nothrow_t *
0x1800092ee  mov     rcx, rdi; void *
0x1800092f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800092f6  mov     rbx, [rsp+28h+arg_0]
0x1800092fb  mov     rax, rdi
0x1800092fe  add     rsp, 20h
0x180009302  pop     rdi
0x180009303  retn
```
