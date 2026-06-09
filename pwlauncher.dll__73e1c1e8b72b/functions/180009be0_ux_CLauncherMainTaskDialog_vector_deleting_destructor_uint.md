# ux::CLauncherMainTaskDialog::`vector deleting destructor'(uint)

- ea: `0x180009be0`
- end: `0x180009c10`
- name: `??_ECLauncherMainTaskDialog@ux@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ux::CLauncherMainTaskDialog *__fastcall(ux::CLauncherMainTaskDialog *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x1800099bc`
- `0x180009be0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009bfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009bfc`

## pseudocode

```c
ux::CLauncherMainTaskDialog *__fastcall ux::CLauncherMainTaskDialog::`vector deleting destructor'(
        ux::CLauncherMainTaskDialog *this,
        char a2)
{
  ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009be0  mov     [rsp+arg_0], rbx
0x180009be5  push    rdi
0x180009be6  sub     rsp, 20h
0x180009bea  mov     ebx, edx
0x180009bec  mov     rdi, rcx
0x180009bef  call    ??1CLauncherMainTaskDialog@ux@@UEAA@XZ; ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog(void)
0x180009bf4  test    bl, 1
0x180009bf7  jz      short loc_180009C02
0x180009bf9  mov     rcx, rdi
0x180009bfc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009c02  mov     rbx, [rsp+28h+arg_0]
0x180009c07  mov     rax, rdi
0x180009c0a  add     rsp, 20h
0x180009c0e  pop     rdi
0x180009c0f  retn
```
