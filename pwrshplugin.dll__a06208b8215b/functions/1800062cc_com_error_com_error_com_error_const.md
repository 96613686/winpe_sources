# _com_error::_com_error(_com_error const &)

- ea: `0x1800062cc`
- end: `0x18000630f`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800062cc`
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
0x1800062cc  push    rbx
0x1800062ce  sub     rsp, 20h
0x1800062d2  mov     rbx, rcx
0x1800062d5  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800062dc  mov     [rcx], rax
0x1800062df  mov     eax, [rdx+8]
0x1800062e2  mov     [rcx+8], eax
0x1800062e5  mov     rcx, [rdx+10h]
0x1800062e9  mov     [rbx+10h], rcx
0x1800062ed  mov     qword ptr [rbx+18h], 0
0x1800062f5  test    rcx, rcx
0x1800062f8  jz      short loc_180006306
0x1800062fa  mov     rax, [rcx]
0x1800062fd  mov     rax, [rax+8]
0x180006301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006306  mov     rax, rbx
0x180006309  add     rsp, 20h
0x18000630d  pop     rbx
0x18000630e  retn
```
