# DuiTaskDlg::`scalar deleting destructor'(uint)

- ea: `0x180002620`
- end: `0x18000264f`
- name: `??_GDuiTaskDlg@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(DuiTaskDlg *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001294`
- `0x1800025cc`
- `0x180002620`

## pseudocode

```c
DuiTaskDlg *__fastcall DuiTaskDlg::`scalar deleting destructor'(DuiTaskDlg *this, char a2)
{
  DuiTaskDlg::~DuiTaskDlg(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002620  mov     [rsp+arg_0], rbx
0x180002625  push    rdi
0x180002626  sub     rsp, 20h
0x18000262a  mov     ebx, edx
0x18000262c  mov     rdi, rcx
0x18000262f  call    ??1DuiTaskDlg@@UEAA@XZ; DuiTaskDlg::~DuiTaskDlg(void)
0x180002634  test    bl, 1
0x180002637  jz      short loc_180002641
0x180002639  mov     rcx, rdi; Block
0x18000263c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002641  mov     rbx, [rsp+28h+arg_0]
0x180002646  mov     rax, rdi
0x180002649  add     rsp, 20h
0x18000264d  pop     rdi
0x18000264e  retn
```
