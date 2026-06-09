# CMessageDlg::`scalar deleting destructor'(uint)

- ea: `0x140001a80`
- end: `0x140001ad3`
- name: `??_GCMessageDlg@@UEAAPEAXI@Z`
- size: `83`
- prototype: `void *__fastcall(CMessageDlg *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140001008`
- `0x140001a80`

## pseudocode

```c
void **__fastcall CMessageDlg::`scalar deleting destructor'(void **this, char a2)
{
  *this = &CMessageDlg::`vftable';
  operator delete(this[4]);
  operator delete(this[78]);
  *this = &CDlg::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140001a80  mov     [rsp+arg_0], rbx
0x140001a85  push    rdi
0x140001a86  sub     rsp, 20h
0x140001a8a  lea     rax, ??_7CMessageDlg@@6B@; const CMessageDlg::`vftable'
0x140001a91  mov     rdi, rcx
0x140001a94  mov     [rcx], rax
0x140001a97  mov     ebx, edx
0x140001a99  mov     rcx, [rcx+20h]; Block
0x140001a9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001aa2  mov     rcx, [rdi+270h]; Block
0x140001aa9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001aae  lea     rax, ??_7CDlg@@6B@; const CDlg::`vftable'
0x140001ab5  mov     [rdi], rax
0x140001ab8  test    bl, 1
0x140001abb  jz      short loc_140001AC5
0x140001abd  mov     rcx, rdi; Block
0x140001ac0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001ac5  mov     rbx, [rsp+28h+arg_0]
0x140001aca  mov     rax, rdi
0x140001acd  add     rsp, 20h
0x140001ad1  pop     rdi
0x140001ad2  retn
```
