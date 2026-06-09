# _com_error::_com_error(_com_error const &)

- ea: `0x18000a248`
- end: `0x18000a28b`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a248`
- `0x18000b010`

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
0x18000a248  push    rbx
0x18000a24a  sub     rsp, 20h
0x18000a24e  mov     rbx, rcx
0x18000a251  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a258  mov     [rcx], rax
0x18000a25b  mov     eax, [rdx+8]
0x18000a25e  mov     [rcx+8], eax
0x18000a261  mov     rcx, [rdx+10h]
0x18000a265  mov     [rbx+10h], rcx
0x18000a269  mov     qword ptr [rbx+18h], 0
0x18000a271  test    rcx, rcx
0x18000a274  jz      short loc_18000A282
0x18000a276  mov     rax, [rcx]
0x18000a279  mov     rax, [rax+8]
0x18000a27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a282  mov     rax, rbx
0x18000a285  add     rsp, 20h
0x18000a289  pop     rbx
0x18000a28a  retn
```
