# _com_error::_com_error(_com_error const &)

- ea: `0x1800024b4`
- end: `0x1800024f7`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800024b4`
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
0x1800024b4  push    rbx
0x1800024b6  sub     rsp, 20h
0x1800024ba  mov     rbx, rcx
0x1800024bd  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800024c4  mov     [rcx], rax
0x1800024c7  mov     eax, [rdx+8]
0x1800024ca  mov     [rcx+8], eax
0x1800024cd  mov     rcx, [rdx+10h]
0x1800024d1  mov     [rbx+10h], rcx
0x1800024d5  mov     qword ptr [rbx+18h], 0
0x1800024dd  test    rcx, rcx
0x1800024e0  jz      short loc_1800024EE
0x1800024e2  mov     rax, [rcx]
0x1800024e5  mov     rax, [rax+8]
0x1800024e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ee  mov     rax, rbx
0x1800024f1  add     rsp, 20h
0x1800024f5  pop     rbx
0x1800024f6  retn
```
