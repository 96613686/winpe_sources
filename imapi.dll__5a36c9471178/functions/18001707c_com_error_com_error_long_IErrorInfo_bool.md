# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x18001707c`
- end: `0x1800170a1`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `37`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, int, struct IErrorInfo *, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180017150`

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
0x18001707c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180017083  mov     dword ptr [rcx+8], 8007000Eh
0x18001708a  mov     [rcx], rax
0x18001708d  mov     rax, rcx
0x180017090  mov     qword ptr [rcx+10h], 0
0x180017098  mov     qword ptr [rcx+18h], 0
0x1800170a0  retn
```
