# _com_error::~_com_error(void)

- ea: `0x1800025b0`
- end: `0x1800025ee`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800025b0`
- `0x180019010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800025e1`
- `KERNEL32!LocalFree` at `0x1800025e1`

## pseudocode

```c
void __fastcall _com_error::~_com_error(_com_error *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x1800025b0  push    rbx
0x1800025b2  sub     rsp, 20h
0x1800025b6  mov     rbx, rcx
0x1800025b9  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800025c0  mov     [rcx], rax
0x1800025c3  mov     rcx, [rcx+10h]
0x1800025c7  test    rcx, rcx
0x1800025ca  jz      short loc_1800025D8
0x1800025cc  mov     rax, [rcx]
0x1800025cf  mov     rax, [rax+10h]
0x1800025d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d8  mov     rcx, [rbx+18h]; hMem
0x1800025dc  test    rcx, rcx
0x1800025df  jz      short loc_1800025E8
0x1800025e1  call    cs:__imp_LocalFree
0x1800025e7  nop
0x1800025e8  add     rsp, 20h
0x1800025ec  pop     rbx
0x1800025ed  retn
```
