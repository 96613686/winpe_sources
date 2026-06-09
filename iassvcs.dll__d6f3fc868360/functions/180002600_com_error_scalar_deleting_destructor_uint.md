# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180002600`
- end: `0x18000265b`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `91`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002600`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x180002647`
- `msvcrt!free` at `0x180002647`
- `KERNEL32!LocalFree` at `0x180002637`
- `KERNEL32!LocalFree` at `0x180002637`

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
    free(this);
  return this;
}

```

## disassembly

```asm
0x180002600  mov     [rsp+arg_0], rbx
0x180002605  push    rdi
0x180002606  sub     rsp, 20h
0x18000260a  mov     edi, edx
0x18000260c  mov     rbx, rcx
0x18000260f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002616  mov     [rcx], rax
0x180002619  mov     rcx, [rcx+10h]
0x18000261d  test    rcx, rcx
0x180002620  jz      short loc_18000262E
0x180002622  mov     rax, [rcx]
0x180002625  mov     rax, [rax+10h]
0x180002629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000262e  mov     rcx, [rbx+18h]; hMem
0x180002632  test    rcx, rcx
0x180002635  jz      short loc_18000263E
0x180002637  call    cs:__imp_LocalFree
0x18000263d  nop
0x18000263e  test    dil, 1
0x180002642  jz      short loc_18000264D
0x180002644  mov     rcx, rbx; Block
0x180002647  call    cs:__imp_free
0x18000264d  mov     rax, rbx
0x180002650  mov     rbx, [rsp+28h+arg_0]
0x180002655  add     rsp, 20h
0x180002659  pop     rdi
0x18000265a  retn
```
