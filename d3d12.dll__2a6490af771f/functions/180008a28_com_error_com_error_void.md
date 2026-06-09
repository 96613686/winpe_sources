# _com_error::~_com_error(void)

- ea: `0x180008a28`
- end: `0x180008a6d`
- name: `??1_com_error@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e840`

## callees

- `0x180008a28`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a66`

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
0x180008a28  push    rbx
0x180008a2a  sub     rsp, 20h
0x180008a2e  mov     rbx, rcx
0x180008a31  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180008a38  mov     [rcx], rax
0x180008a3b  mov     rcx, [rcx+10h]
0x180008a3f  test    rcx, rcx
0x180008a42  jnz     short loc_180008A53
0x180008a44  mov     rcx, [rbx+18h]
0x180008a48  test    rcx, rcx
0x180008a4b  jnz     short loc_180008A61
0x180008a4d  add     rsp, 20h
0x180008a51  pop     rbx
0x180008a52  retn
0x180008a53  mov     rax, [rcx]
0x180008a56  mov     rax, [rax+10h]
0x180008a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a5f  jmp     short loc_180008A44
0x180008a61  add     rsp, 20h
0x180008a65  pop     rbx
0x180008a66  jmp     cs:__imp_LocalFree
```
