# _com_error::_com_error(_com_error const &)

- ea: `0x14000ce00`
- end: `0x14000ce43`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ce00`
- `0x140020010`

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
0x14000ce00  push    rbx
0x14000ce02  sub     rsp, 20h
0x14000ce06  mov     rbx, rcx
0x14000ce09  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000ce10  mov     [rcx], rax
0x14000ce13  mov     eax, [rdx+8]
0x14000ce16  mov     [rcx+8], eax
0x14000ce19  mov     rcx, [rdx+10h]
0x14000ce1d  mov     [rbx+10h], rcx
0x14000ce21  mov     qword ptr [rbx+18h], 0
0x14000ce29  test    rcx, rcx
0x14000ce2c  jz      short loc_14000CE3A
0x14000ce2e  mov     rax, [rcx]
0x14000ce31  mov     rax, [rax+8]
0x14000ce35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce3a  mov     rax, rbx
0x14000ce3d  add     rsp, 20h
0x14000ce41  pop     rbx
0x14000ce42  retn
```
