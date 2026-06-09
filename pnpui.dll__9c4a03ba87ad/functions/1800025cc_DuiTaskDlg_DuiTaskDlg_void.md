# DuiTaskDlg::~DuiTaskDlg(void)

- ea: `0x1800025cc`
- end: `0x180002617`
- name: `??1DuiTaskDlg@@UEAA@XZ`
- size: `75`
- prototype: `void __fastcall(DuiTaskDlg *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180002620`
- `0x180002d78`

## callees

- `0x180001294`
- `0x1800025cc`
- `0x180003788`

## pseudocode

```c
void __fastcall DuiTaskDlg::~DuiTaskDlg(DuiTaskDlg *this)
{
  CLoadDui *v1; // rdi

  v1 = (CLoadDui *)*((_QWORD *)this + 3);
  *(_QWORD *)this = &DuiTaskDlg::`vftable';
  *((_QWORD *)this + 2) = 0;
  if ( v1 )
  {
    CLoadDui::~CLoadDui(v1);
    operator delete(v1);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x1800025cc  mov     [rsp+arg_0], rbx
0x1800025d1  push    rdi
0x1800025d2  sub     rsp, 20h
0x1800025d6  mov     rdi, [rcx+18h]
0x1800025da  lea     rax, ??_7DuiTaskDlg@@6B@; const DuiTaskDlg::`vftable'
0x1800025e1  mov     [rcx], rax
0x1800025e4  mov     rbx, rcx
0x1800025e7  mov     qword ptr [rcx+10h], 0
0x1800025ef  test    rdi, rdi
0x1800025f2  jz      short loc_18000260C
0x1800025f4  mov     rcx, rdi; this
0x1800025f7  call    ??1CLoadDui@@QEAA@XZ; CLoadDui::~CLoadDui(void)
0x1800025fc  mov     rcx, rdi; Block
0x1800025ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002604  mov     qword ptr [rbx+18h], 0
0x18000260c  mov     rbx, [rsp+28h+arg_0]
0x180002611  add     rsp, 20h
0x180002615  pop     rdi
0x180002616  retn
```
