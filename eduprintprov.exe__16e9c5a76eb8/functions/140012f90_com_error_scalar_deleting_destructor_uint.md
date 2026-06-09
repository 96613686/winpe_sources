# _com_error::`scalar deleting destructor'(uint)

- ea: `0x140012f90`
- end: `0x140012fef`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `95`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140002624`
- `0x140012f90`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012fc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012fc7`

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
0x140012f90  mov     [rsp+arg_0], rbx
0x140012f95  push    rdi
0x140012f96  sub     rsp, 20h
0x140012f9a  mov     edi, edx
0x140012f9c  mov     rbx, rcx
0x140012f9f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140012fa6  mov     [rcx], rax
0x140012fa9  mov     rcx, [rcx+10h]
0x140012fad  test    rcx, rcx
0x140012fb0  jz      short loc_140012FBE
0x140012fb2  mov     rax, [rcx]
0x140012fb5  mov     rax, [rax+10h]
0x140012fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fbe  mov     rcx, [rbx+18h]; hMem
0x140012fc2  test    rcx, rcx
0x140012fc5  jz      short loc_140012FCE
0x140012fc7  call    cs:__imp_LocalFree
0x140012fcd  nop
0x140012fce  test    dil, 1
0x140012fd2  jz      short loc_140012FE1
0x140012fd4  mov     edx, 20h ; ' '; unsigned __int64
0x140012fd9  mov     rcx, rbx; void *
0x140012fdc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012fe1  mov     rax, rbx
0x140012fe4  mov     rbx, [rsp+28h+arg_0]
0x140012fe9  add     rsp, 20h
0x140012fed  pop     rdi
0x140012fee  retn
```
