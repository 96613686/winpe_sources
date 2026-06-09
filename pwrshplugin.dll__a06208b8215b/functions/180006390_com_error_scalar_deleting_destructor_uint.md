# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180006390`
- end: `0x1800063ea`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `90`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006390`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800063d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800063d6`
- `KERNEL32!LocalFree` at `0x1800063c7`
- `KERNEL32!LocalFree` at `0x1800063c7`

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
0x180006390  mov     [rsp+arg_0], rbx
0x180006395  push    rdi
0x180006396  sub     rsp, 20h
0x18000639a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800063a1  mov     rbx, rcx
0x1800063a4  mov     [rcx], rax
0x1800063a7  mov     edi, edx
0x1800063a9  mov     rcx, [rcx+10h]
0x1800063ad  test    rcx, rcx
0x1800063b0  jz      short loc_1800063BE
0x1800063b2  mov     rax, [rcx]
0x1800063b5  mov     rax, [rax+10h]
0x1800063b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063be  mov     rcx, [rbx+18h]; hMem
0x1800063c2  test    rcx, rcx
0x1800063c5  jz      short loc_1800063CD
0x1800063c7  call    cs:__imp_LocalFree
0x1800063cd  test    dil, 1
0x1800063d1  jz      short loc_1800063DC
0x1800063d3  mov     rcx, rbx
0x1800063d6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800063dc  mov     rax, rbx
0x1800063df  mov     rbx, [rsp+28h+arg_0]
0x1800063e4  add     rsp, 20h
0x1800063e8  pop     rdi
0x1800063e9  retn
```
