# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x180011828`
- end: `0x180011845`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `29`
- prototype: `_com_error *__fastcall(_com_error *this, int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800118f8`

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
0x180011828  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001182f  mov     [rcx], rax
0x180011832  mov     [rcx+8], edx
0x180011835  mov     [rcx+10h], r8
0x180011839  mov     qword ptr [rcx+18h], 0
0x180011841  mov     rax, rcx
0x180011844  retn
```
