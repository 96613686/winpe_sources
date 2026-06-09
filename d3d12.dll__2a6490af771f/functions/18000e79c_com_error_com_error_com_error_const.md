# _com_error::_com_error(_com_error const &)

- ea: `0x18000e79c`
- end: `0x18000e7df`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e79c`
- `0x180015010`

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
0x18000e79c  push    rbx
0x18000e79e  sub     rsp, 20h
0x18000e7a2  mov     rbx, rcx
0x18000e7a5  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000e7ac  mov     [rcx], rax
0x18000e7af  mov     eax, [rdx+8]
0x18000e7b2  mov     [rcx+8], eax
0x18000e7b5  mov     rcx, [rdx+10h]
0x18000e7b9  mov     [rbx+10h], rcx
0x18000e7bd  mov     qword ptr [rbx+18h], 0
0x18000e7c5  test    rcx, rcx
0x18000e7c8  jz      short loc_18000E7D6
0x18000e7ca  mov     rax, [rcx]
0x18000e7cd  mov     rax, [rax+8]
0x18000e7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d6  mov     rax, rbx
0x18000e7d9  add     rsp, 20h
0x18000e7dd  pop     rbx
0x18000e7de  retn
```
