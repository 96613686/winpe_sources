# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x18000a294`
- end: `0x18000a2b5`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `33`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, int, struct IErrorInfo *, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a360`

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
0x18000a294  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a29b  mov     [rcx+8], edx
0x18000a29e  mov     [rcx], rax
0x18000a2a1  mov     rax, rcx
0x18000a2a4  mov     qword ptr [rcx+10h], 0
0x18000a2ac  mov     qword ptr [rcx+18h], 0
0x18000a2b4  retn
```
