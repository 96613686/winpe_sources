# CDlg::`vector deleting destructor'(uint)

- ea: `0x140001870`
- end: `0x140001896`
- name: `??_ECDlg@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(CDlg *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140001008`
- `0x140001870`

## pseudocode

```c
CDlg *__fastcall CDlg::`vector deleting destructor'(CDlg *this, char a2)
{
  *(_QWORD *)this = &CDlg::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140001870  push    rbx
0x140001872  sub     rsp, 20h
0x140001876  lea     rax, ??_7CDlg@@6B@; const CDlg::`vftable'
0x14000187d  mov     rbx, rcx
0x140001880  mov     [rcx], rax
0x140001883  test    dl, 1
0x140001886  jz      short loc_14000188D
0x140001888  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000188d  mov     rax, rbx
0x140001890  add     rsp, 20h
0x140001894  pop     rbx
0x140001895  retn
```
