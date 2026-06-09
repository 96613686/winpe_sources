# CMyUpdateList::`scalar deleting destructor'(uint)

- ea: `0x1800107a0`
- end: `0x1800107e0`
- name: `??_GCMyUpdateList@@UEAAPEAXI@Z`
- size: `64`
- prototype: `void *__fastcall(CMyUpdateList *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180001144`
- `0x1800107a0`
- `0x1800109d0`

## pseudocode

```c
CMyUpdateList *__fastcall CMyUpdateList::`scalar deleting destructor'(CMyUpdateList *this, char a2)
{
  bool v2; // zf

  v2 = *((_DWORD *)this + 3) == 0;
  *(_QWORD *)this = &CMyUpdateList::`vftable';
  if ( !v2 )
    CMyUpdateList::RemoveAll(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800107a0  mov     [rsp+arg_0], rbx
0x1800107a5  push    rdi
0x1800107a6  sub     rsp, 20h
0x1800107aa  cmp     dword ptr [rcx+0Ch], 0
0x1800107ae  lea     rax, ??_7CMyUpdateList@@6B@; const CMyUpdateList::`vftable'
0x1800107b5  mov     [rcx], rax
0x1800107b8  mov     edi, edx
0x1800107ba  mov     rbx, rcx
0x1800107bd  jz      short loc_1800107C4
0x1800107bf  call    ?RemoveAll@CMyUpdateList@@QEAAEXZ; CMyUpdateList::RemoveAll(void)
0x1800107c4  test    dil, 1
0x1800107c8  jz      short loc_1800107D2
0x1800107ca  mov     rcx, rbx; Block
0x1800107cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800107d2  mov     rax, rbx
0x1800107d5  mov     rbx, [rsp+28h+arg_0]
0x1800107da  add     rsp, 20h
0x1800107de  pop     rdi
0x1800107df  retn
```
