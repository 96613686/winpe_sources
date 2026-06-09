# _com_error::_com_error(_com_error const &)

- ea: `0x1800097c0`
- end: `0x180009803`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800097c0`
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
0x1800097c0  push    rbx
0x1800097c2  sub     rsp, 20h
0x1800097c6  mov     rbx, rcx
0x1800097c9  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800097d0  mov     [rcx], rax
0x1800097d3  mov     eax, [rdx+8]
0x1800097d6  mov     [rcx+8], eax
0x1800097d9  mov     rcx, [rdx+10h]
0x1800097dd  mov     [rbx+10h], rcx
0x1800097e1  mov     qword ptr [rbx+18h], 0
0x1800097e9  test    rcx, rcx
0x1800097ec  jz      short loc_1800097FA
0x1800097ee  mov     rax, [rcx]
0x1800097f1  mov     rax, [rax+8]
0x1800097f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fa  mov     rax, rbx
0x1800097fd  add     rsp, 20h
0x180009801  pop     rbx
0x180009802  retn
```
