# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x180002500`
- end: `0x180002521`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `33`
- prototype: `_com_error *__fastcall(_com_error *this, int, struct IErrorInfo *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002280`
- `0x18000236c`
- `0x1800137c0`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, int a2, struct IErrorInfo *a3)
{
  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  return this;
}

```

## disassembly

```asm
0x180002500  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002507  mov     [rcx], rax
0x18000250a  mov     [rcx+8], edx
0x18000250d  mov     qword ptr [rcx+10h], 0
0x180002515  mov     qword ptr [rcx+18h], 0
0x18000251d  mov     rax, rcx
0x180002520  retn
```
