# _com_error::~_com_error(void)

- ea: `0x140014074`
- end: `0x1400140b2`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400140c0`

## callees

- `0x140014074`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400140a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400140a5`

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
0x140014074  push    rbx
0x140014076  sub     rsp, 20h
0x14001407a  mov     rbx, rcx
0x14001407d  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140014084  mov     [rcx], rax
0x140014087  mov     rcx, [rcx+10h]
0x14001408b  test    rcx, rcx
0x14001408e  jz      short loc_14001409C
0x140014090  mov     rax, [rcx]
0x140014093  mov     rax, [rax+10h]
0x140014097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001409c  mov     rcx, [rbx+18h]; hMem
0x1400140a0  test    rcx, rcx
0x1400140a3  jz      short loc_1400140AC
0x1400140a5  call    cs:__imp_LocalFree
0x1400140ab  nop
0x1400140ac  add     rsp, 20h
0x1400140b0  pop     rbx
0x1400140b1  retn
```
