# ux::CLauncherErrorTaskDialog::`vector deleting destructor'(uint)

- ea: `0x180009ba0`
- end: `0x180009bd0`
- name: `??_ECLauncherErrorTaskDialog@ux@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ux::CLauncherErrorTaskDialog *__fastcall(ux::CLauncherErrorTaskDialog *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180009974`
- `0x180009ba0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009bbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009bbc`

## pseudocode

```c
ux::CLauncherErrorTaskDialog *__fastcall ux::CLauncherErrorTaskDialog::`vector deleting destructor'(
        ux::CLauncherErrorTaskDialog *this,
        char a2)
{
  ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009ba0  mov     [rsp+arg_0], rbx
0x180009ba5  push    rdi
0x180009ba6  sub     rsp, 20h
0x180009baa  mov     ebx, edx
0x180009bac  mov     rdi, rcx
0x180009baf  call    ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
0x180009bb4  test    bl, 1
0x180009bb7  jz      short loc_180009BC2
0x180009bb9  mov     rcx, rdi
0x180009bbc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009bc2  mov     rbx, [rsp+28h+arg_0]
0x180009bc7  mov     rax, rdi
0x180009bca  add     rsp, 20h
0x180009bce  pop     rdi
0x180009bcf  retn
```
