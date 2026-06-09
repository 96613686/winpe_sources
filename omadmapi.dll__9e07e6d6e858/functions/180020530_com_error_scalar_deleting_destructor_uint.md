# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180020530`
- end: `0x180020596`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `102`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800031d4`
- `0x180020530`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020567`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020567`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    LocalFree(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180020530  mov     [rsp+arg_0], rbx
0x180020535  push    rdi
0x180020536  sub     rsp, 20h
0x18002053a  mov     edi, edx
0x18002053c  mov     rbx, rcx
0x18002053f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180020546  mov     [rcx], rax
0x180020549  mov     rcx, [rcx+10h]
0x18002054d  test    rcx, rcx
0x180020550  jz      short loc_18002055E
0x180020552  mov     rax, [rcx]
0x180020555  mov     rax, [rax+10h]
0x180020559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002055e  mov     rcx, [rbx+18h]; hMem
0x180020562  test    rcx, rcx
0x180020565  jz      short loc_180020574
0x180020567  call    cs:__imp_LocalFree
0x18002056e  nop     dword ptr [rax+rax+00h]
0x180020573  nop
0x180020574  test    dil, 1
0x180020578  jz      short loc_180020587
0x18002057a  mov     edx, 20h ; ' '; unsigned __int64
0x18002057f  mov     rcx, rbx; void *
0x180020582  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020587  mov     rax, rbx
0x18002058a  mov     rbx, [rsp+28h+arg_0]
0x18002058f  add     rsp, 20h
0x180020593  pop     rdi
0x180020594  retn
```
