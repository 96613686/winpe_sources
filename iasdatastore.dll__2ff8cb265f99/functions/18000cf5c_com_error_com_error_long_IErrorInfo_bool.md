# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x18000cf5c`
- end: `0x18000cf79`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `29`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, int, struct IErrorInfo *, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000dc14`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, int a2, struct IErrorInfo *a3)
{
  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = a2;
  *((_QWORD *)this + 2) = a3;
  *((_QWORD *)this + 3) = 0;
  return this;
}

```

## disassembly

```asm
0x18000cf5c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000cf63  mov     [rcx], rax
0x18000cf66  mov     [rcx+8], edx
0x18000cf69  mov     [rcx+10h], r8
0x18000cf6d  mov     qword ptr [rcx+18h], 0
0x18000cf75  mov     rax, rcx
0x18000cf78  retn
```
