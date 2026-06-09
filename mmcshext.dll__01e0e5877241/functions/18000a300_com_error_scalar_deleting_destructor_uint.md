# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18000a300`
- end: `0x18000a35a`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `90`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a300`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a346`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a346`
- `KERNEL32!LocalFree` at `0x18000a337`
- `KERNEL32!LocalFree` at `0x18000a337`

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
0x18000a300  mov     [rsp+arg_0], rbx
0x18000a305  push    rdi
0x18000a306  sub     rsp, 20h
0x18000a30a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a311  mov     rbx, rcx
0x18000a314  mov     [rcx], rax
0x18000a317  mov     edi, edx
0x18000a319  mov     rcx, [rcx+10h]
0x18000a31d  test    rcx, rcx
0x18000a320  jz      short loc_18000A32E
0x18000a322  mov     rax, [rcx]
0x18000a325  mov     rax, [rax+10h]
0x18000a329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32e  mov     rcx, [rbx+18h]; hMem
0x18000a332  test    rcx, rcx
0x18000a335  jz      short loc_18000A33D
0x18000a337  call    cs:__imp_LocalFree
0x18000a33d  test    dil, 1
0x18000a341  jz      short loc_18000A34C
0x18000a343  mov     rcx, rbx
0x18000a346  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a34c  mov     rax, rbx
0x18000a34f  mov     rbx, [rsp+28h+arg_0]
0x18000a354  add     rsp, 20h
0x18000a358  pop     rdi
0x18000a359  retn
```
