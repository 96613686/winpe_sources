# _com_error::~_com_error(void)

- ea: `0x180006344`
- end: `0x180006381`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006344`
- `0x18000b010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180006375`
- `KERNEL32!LocalFree` at `0x180006375`

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
0x180006344  push    rbx
0x180006346  sub     rsp, 20h
0x18000634a  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180006351  mov     rbx, rcx
0x180006354  mov     [rcx], rax
0x180006357  mov     rcx, [rcx+10h]
0x18000635b  test    rcx, rcx
0x18000635e  jz      short loc_18000636C
0x180006360  mov     rax, [rcx]
0x180006363  mov     rax, [rax+10h]
0x180006367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636c  mov     rcx, [rbx+18h]; hMem
0x180006370  test    rcx, rcx
0x180006373  jz      short loc_18000637B
0x180006375  call    cs:__imp_LocalFree
0x18000637b  add     rsp, 20h
0x18000637f  pop     rbx
0x180006380  retn
```
