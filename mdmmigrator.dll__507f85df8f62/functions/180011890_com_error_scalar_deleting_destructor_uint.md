# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180011890`
- end: `0x1800118ef`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `95`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800026b0`
- `0x180011890`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800118c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800118c7`

## pseudocode

```c
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
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x180011890  mov     [rsp+arg_0], rbx
0x180011895  push    rdi
0x180011896  sub     rsp, 20h
0x18001189a  mov     edi, edx
0x18001189c  mov     rbx, rcx
0x18001189f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800118a6  mov     [rcx], rax
0x1800118a9  mov     rcx, [rcx+10h]
0x1800118ad  test    rcx, rcx
0x1800118b0  jz      short loc_1800118BE
0x1800118b2  mov     rax, [rcx]
0x1800118b5  mov     rax, [rax+10h]
0x1800118b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118be  mov     rcx, [rbx+18h]; hMem
0x1800118c2  test    rcx, rcx
0x1800118c5  jz      short loc_1800118CE
0x1800118c7  call    cs:__imp_LocalFree
0x1800118cd  nop
0x1800118ce  test    dil, 1
0x1800118d2  jz      short loc_1800118E1
0x1800118d4  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800118d9  mov     rcx, rbx; void *
0x1800118dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800118e1  mov     rax, rbx
0x1800118e4  mov     rbx, [rsp+28h+arg_0]
0x1800118e9  add     rsp, 20h
0x1800118ed  pop     rdi
0x1800118ee  retn
```
