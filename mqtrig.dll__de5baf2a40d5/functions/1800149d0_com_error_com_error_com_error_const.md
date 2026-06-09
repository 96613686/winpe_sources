# _com_error::_com_error(_com_error const &)

- ea: `0x1800149d0`
- end: `0x180014a13`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800149d0`
- `0x180022010`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, const struct _com_error *a2)
{
  __int64 v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v3 = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 2) = v3;
  *((_QWORD *)this + 3) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return this;
}

```

## disassembly

```asm
0x1800149d0  push    rbx
0x1800149d2  sub     rsp, 20h
0x1800149d6  mov     rbx, rcx
0x1800149d9  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800149e0  mov     [rcx], rax
0x1800149e3  mov     eax, [rdx+8]
0x1800149e6  mov     [rcx+8], eax
0x1800149e9  mov     rcx, [rdx+10h]
0x1800149ed  mov     [rbx+10h], rcx
0x1800149f1  mov     qword ptr [rbx+18h], 0
0x1800149f9  test    rcx, rcx
0x1800149fc  jz      short loc_180014A0A
0x1800149fe  mov     rax, [rcx]
0x180014a01  mov     rax, [rax+8]
0x180014a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0a  mov     rax, rbx
0x180014a0d  add     rsp, 20h
0x180014a11  pop     rbx
0x180014a12  retn
```
