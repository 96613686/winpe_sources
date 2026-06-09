# _com_error::_com_error(_com_error const &)

- ea: `0x180017030`
- end: `0x180017073`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180017030`
- `0x180019010`

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
0x180017030  push    rbx
0x180017032  sub     rsp, 20h
0x180017036  mov     rbx, rcx
0x180017039  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180017040  mov     [rcx], rax
0x180017043  mov     eax, [rdx+8]
0x180017046  mov     [rcx+8], eax
0x180017049  mov     rcx, [rdx+10h]
0x18001704d  mov     [rbx+10h], rcx
0x180017051  mov     qword ptr [rbx+18h], 0
0x180017059  test    rcx, rcx
0x18001705c  jz      short loc_18001706A
0x18001705e  mov     rax, [rcx]
0x180017061  mov     rax, [rax+8]
0x180017065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001706a  mov     rax, rbx
0x18001706d  add     rsp, 20h
0x180017071  pop     rbx
0x180017072  retn
```
