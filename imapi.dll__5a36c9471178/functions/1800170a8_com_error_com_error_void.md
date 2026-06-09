# _com_error::~_com_error(void)

- ea: `0x1800170a8`
- end: `0x1800170e5`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800170a8`
- `0x180019010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800170d9`
- `KERNEL32!LocalFree` at `0x1800170d9`

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
0x1800170a8  push    rbx
0x1800170aa  sub     rsp, 20h
0x1800170ae  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800170b5  mov     rbx, rcx
0x1800170b8  mov     [rcx], rax
0x1800170bb  mov     rcx, [rcx+10h]
0x1800170bf  test    rcx, rcx
0x1800170c2  jz      short loc_1800170D0
0x1800170c4  mov     rax, [rcx]
0x1800170c7  mov     rax, [rax+10h]
0x1800170cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170d0  mov     rcx, [rbx+18h]; hMem
0x1800170d4  test    rcx, rcx
0x1800170d7  jz      short loc_1800170DF
0x1800170d9  call    cs:__imp_LocalFree
0x1800170df  add     rsp, 20h
0x1800170e3  pop     rbx
0x1800170e4  retn
```
