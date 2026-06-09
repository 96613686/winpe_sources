# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x180006318`
- end: `0x18000633d`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `37`
- prototype: `_com_error *__fastcall(_com_error *this, __int64, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800063f0`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, __int64 a2, struct IErrorInfo *a3)
{
  _com_error *result; // rax

  *((_DWORD *)this + 2) = -2147024882;
  *(_QWORD *)this = &_com_error::`vftable';
  result = this;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x180006318  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000631f  mov     dword ptr [rcx+8], 8007000Eh
0x180006326  mov     [rcx], rax
0x180006329  mov     rax, rcx
0x18000632c  mov     qword ptr [rcx+10h], 0
0x180006334  mov     qword ptr [rcx+18h], 0
0x18000633c  retn
```
