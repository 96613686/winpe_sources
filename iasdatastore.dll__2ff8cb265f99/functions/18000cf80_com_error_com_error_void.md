# _com_error::~_com_error(void)

- ea: `0x18000cf80`
- end: `0x18000cfbe`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000cf80`
- `0x180010010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000cfb1`
- `KERNEL32!LocalFree` at `0x18000cfb1`

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
0x18000cf80  push    rbx
0x18000cf82  sub     rsp, 20h
0x18000cf86  mov     rbx, rcx
0x18000cf89  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000cf90  mov     [rcx], rax
0x18000cf93  mov     rcx, [rcx+10h]
0x18000cf97  test    rcx, rcx
0x18000cf9a  jz      short loc_18000CFA8
0x18000cf9c  mov     rax, [rcx]
0x18000cf9f  mov     rax, [rax+10h]
0x18000cfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa8  mov     rcx, [rbx+18h]; hMem
0x18000cfac  test    rcx, rcx
0x18000cfaf  jz      short loc_18000CFB8
0x18000cfb1  call    cs:__imp_LocalFree
0x18000cfb7  nop
0x18000cfb8  add     rsp, 20h
0x18000cfbc  pop     rbx
0x18000cfbd  retn
```
