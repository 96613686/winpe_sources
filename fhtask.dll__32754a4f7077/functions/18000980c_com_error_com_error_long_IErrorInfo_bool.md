# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x18000980c`
- end: `0x18000982d`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `33`
- prototype: `_com_error *__fastcall(_com_error *this, int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800098e0`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, int a2, struct IErrorInfo *a3)
{
  _com_error *result; // rax

  *((_DWORD *)this + 2) = a2;
  *(_QWORD *)this = &_com_error::`vftable';
  result = this;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000980c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180009813  mov     [rcx+8], edx
0x180009816  mov     [rcx], rax
0x180009819  mov     rax, rcx
0x18000981c  mov     qword ptr [rcx+10h], 0
0x180009824  mov     qword ptr [rcx+18h], 0
0x18000982c  retn
```
