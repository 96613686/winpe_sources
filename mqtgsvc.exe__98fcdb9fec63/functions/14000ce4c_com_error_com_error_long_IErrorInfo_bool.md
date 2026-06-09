# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x14000ce4c`
- end: `0x14000ce69`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `29`
- prototype: `_com_error *__fastcall(_com_error *this, int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000ecd0`

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
0x14000ce4c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000ce53  mov     [rcx], rax
0x14000ce56  mov     [rcx+8], edx
0x14000ce59  mov     [rcx+10h], r8
0x14000ce5d  mov     qword ptr [rcx+18h], 0
0x14000ce65  mov     rax, rcx
0x14000ce68  retn
```
