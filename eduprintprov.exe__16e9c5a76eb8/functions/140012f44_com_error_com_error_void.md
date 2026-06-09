# _com_error::~_com_error(void)

- ea: `0x140012f44`
- end: `0x140012f82`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140012f44`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012f75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012f75`

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
0x140012f44  push    rbx
0x140012f46  sub     rsp, 20h
0x140012f4a  mov     rbx, rcx
0x140012f4d  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140012f54  mov     [rcx], rax
0x140012f57  mov     rcx, [rcx+10h]
0x140012f5b  test    rcx, rcx
0x140012f5e  jz      short loc_140012F6C
0x140012f60  mov     rax, [rcx]
0x140012f63  mov     rax, [rax+10h]
0x140012f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f6c  mov     rcx, [rbx+18h]; hMem
0x140012f70  test    rcx, rcx
0x140012f73  jz      short loc_140012F7C
0x140012f75  call    cs:__imp_LocalFree
0x140012f7b  nop
0x140012f7c  add     rsp, 20h
0x140012f80  pop     rbx
0x140012f81  retn
```
