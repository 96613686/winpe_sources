# _com_error::~_com_error(void)

- ea: `0x18000a2bc`
- end: `0x18000a2f9`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a2bc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000a2ed`
- `KERNEL32!LocalFree` at `0x18000a2ed`

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
0x18000a2bc  push    rbx
0x18000a2be  sub     rsp, 20h
0x18000a2c2  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000a2c9  mov     rbx, rcx
0x18000a2cc  mov     [rcx], rax
0x18000a2cf  mov     rcx, [rcx+10h]
0x18000a2d3  test    rcx, rcx
0x18000a2d6  jz      short loc_18000A2E4
0x18000a2d8  mov     rax, [rcx]
0x18000a2db  mov     rax, [rax+10h]
0x18000a2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e4  mov     rcx, [rbx+18h]; hMem
0x18000a2e8  test    rcx, rcx
0x18000a2eb  jz      short loc_18000A2F3
0x18000a2ed  call    cs:__imp_LocalFree
0x18000a2f3  add     rsp, 20h
0x18000a2f7  pop     rbx
0x18000a2f8  retn
```
