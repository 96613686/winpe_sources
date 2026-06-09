# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180009880`
- end: `0x1800098da`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `90`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009880`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800098c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800098c6`
- `KERNEL32!LocalFree` at `0x1800098b7`
- `KERNEL32!LocalFree` at `0x1800098b7`

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
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009880  mov     [rsp+arg_0], rbx
0x180009885  push    rdi
0x180009886  sub     rsp, 20h
0x18000988a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180009891  mov     rbx, rcx
0x180009894  mov     [rcx], rax
0x180009897  mov     edi, edx
0x180009899  mov     rcx, [rcx+10h]
0x18000989d  test    rcx, rcx
0x1800098a0  jz      short loc_1800098AE
0x1800098a2  mov     rax, [rcx]
0x1800098a5  mov     rax, [rax+10h]
0x1800098a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ae  mov     rcx, [rbx+18h]; hMem
0x1800098b2  test    rcx, rcx
0x1800098b5  jz      short loc_1800098BD
0x1800098b7  call    cs:__imp_LocalFree
0x1800098bd  test    dil, 1
0x1800098c1  jz      short loc_1800098CC
0x1800098c3  mov     rcx, rbx
0x1800098c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800098cc  mov     rax, rbx
0x1800098cf  mov     rbx, [rsp+28h+arg_0]
0x1800098d4  add     rsp, 20h
0x1800098d8  pop     rdi
0x1800098d9  retn
```
