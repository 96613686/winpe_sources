# _com_error::_com_error(_com_error const &)

- ea: `0x18000cf10`
- end: `0x18000cf53`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000cf10`
- `0x180010010`

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
0x18000cf10  push    rbx
0x18000cf12  sub     rsp, 20h
0x18000cf16  mov     rbx, rcx
0x18000cf19  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000cf20  mov     [rcx], rax
0x18000cf23  mov     eax, [rdx+8]
0x18000cf26  mov     [rcx+8], eax
0x18000cf29  mov     rcx, [rdx+10h]
0x18000cf2d  mov     [rbx+10h], rcx
0x18000cf31  mov     qword ptr [rbx+18h], 0
0x18000cf39  test    rcx, rcx
0x18000cf3c  jz      short loc_18000CF4A
0x18000cf3e  mov     rax, [rcx]
0x18000cf41  mov     rax, [rax+8]
0x18000cf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf4a  mov     rax, rbx
0x18000cf4d  add     rsp, 20h
0x18000cf51  pop     rbx
0x18000cf52  retn
```
