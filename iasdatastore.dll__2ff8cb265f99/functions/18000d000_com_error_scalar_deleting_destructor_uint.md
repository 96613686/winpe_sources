# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18000d000`
- end: `0x18000d05b`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `91`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d000`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x18000d047`
- `msvcrt!free` at `0x18000d047`
- `KERNEL32!LocalFree` at `0x18000d037`
- `KERNEL32!LocalFree` at `0x18000d037`

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
    free(this);
  return this;
}

```

## disassembly

```asm
0x18000d000  mov     [rsp+arg_0], rbx
0x18000d005  push    rdi
0x18000d006  sub     rsp, 20h
0x18000d00a  mov     edi, edx
0x18000d00c  mov     rbx, rcx
0x18000d00f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000d016  mov     [rcx], rax
0x18000d019  mov     rcx, [rcx+10h]
0x18000d01d  test    rcx, rcx
0x18000d020  jz      short loc_18000D02E
0x18000d022  mov     rax, [rcx]
0x18000d025  mov     rax, [rax+10h]
0x18000d029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02e  mov     rcx, [rbx+18h]; hMem
0x18000d032  test    rcx, rcx
0x18000d035  jz      short loc_18000D03E
0x18000d037  call    cs:__imp_LocalFree
0x18000d03d  nop
0x18000d03e  test    dil, 1
0x18000d042  jz      short loc_18000D04D
0x18000d044  mov     rcx, rbx; Block
0x18000d047  call    cs:__imp_free
0x18000d04d  mov     rax, rbx
0x18000d050  mov     rbx, [rsp+28h+arg_0]
0x18000d055  add     rsp, 20h
0x18000d059  pop     rdi
0x18000d05a  retn
```
