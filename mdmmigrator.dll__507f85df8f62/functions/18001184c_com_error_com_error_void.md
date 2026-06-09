# _com_error::~_com_error(void)

- ea: `0x18001184c`
- end: `0x18001188a`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001184c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001187d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001187d`

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
0x18001184c  push    rbx
0x18001184e  sub     rsp, 20h
0x180011852  mov     rbx, rcx
0x180011855  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001185c  mov     [rcx], rax
0x18001185f  mov     rcx, [rcx+10h]
0x180011863  test    rcx, rcx
0x180011866  jz      short loc_180011874
0x180011868  mov     rax, [rcx]
0x18001186b  mov     rax, [rax+10h]
0x18001186f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011874  mov     rcx, [rbx+18h]; hMem
0x180011878  test    rcx, rcx
0x18001187b  jz      short loc_180011884
0x18001187d  call    cs:__imp_LocalFree
0x180011883  nop
0x180011884  add     rsp, 20h
0x180011888  pop     rbx
0x180011889  retn
```
