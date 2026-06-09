# CPopupCommand::`scalar deleting destructor'(uint)

- ea: `0x180001e20`
- end: `0x180001e79`
- name: `??_GCPopupCommand@@EEAAPEAXI@Z`
- size: `89`
- prototype: `CPopupCommand *__fastcall(CPopupCommand *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001070`
- `0x180001e20`
- `0x180004010`

## pseudocode

```c
CPopupCommand *__fastcall CPopupCommand::`scalar deleting destructor'(CPopupCommand *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CPopupCommand::`vftable';
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    *((_QWORD *)this + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001e20  mov     [rsp+arg_0], rbx
0x180001e25  push    rdi
0x180001e26  sub     rsp, 20h
0x180001e2a  lea     rax, ??_7CPopupCommand@@6B@; const CPopupCommand::`vftable'
0x180001e31  mov     rbx, rcx
0x180001e34  mov     [rcx], rax
0x180001e37  mov     edi, edx
0x180001e39  mov     rcx, [rcx+18h]
0x180001e3d  test    rcx, rcx
0x180001e40  jz      short loc_180001E56
0x180001e42  mov     qword ptr [rbx+18h], 0
0x180001e4a  mov     rax, [rcx]
0x180001e4d  mov     rax, [rax+10h]
0x180001e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e56  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180001e5d  test    dil, 1
0x180001e61  jz      short loc_180001E6B
0x180001e63  mov     rcx, rbx; Block
0x180001e66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e6b  mov     rax, rbx
0x180001e6e  mov     rbx, [rsp+28h+arg_0]
0x180001e73  add     rsp, 20h
0x180001e77  pop     rdi
0x180001e78  retn
```
