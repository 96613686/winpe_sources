# _com_error::~_com_error(void)

- ea: `0x18001b2b4`
- end: `0x18001b2f1`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b300`

## callees

- `0x18001b2b4`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001b2e5`
- `KERNEL32!LocalFree` at `0x18001b2e5`

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
0x18001b2b4  push    rbx
0x18001b2b6  sub     rsp, 20h
0x18001b2ba  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001b2c1  mov     rbx, rcx
0x18001b2c4  mov     [rcx], rax
0x18001b2c7  mov     rcx, [rcx+10h]
0x18001b2cb  test    rcx, rcx
0x18001b2ce  jz      short loc_18001B2DC
0x18001b2d0  mov     rax, [rcx]
0x18001b2d3  mov     rax, [rax+10h]
0x18001b2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2dc  mov     rcx, [rbx+18h]; hMem
0x18001b2e0  test    rcx, rcx
0x18001b2e3  jz      short loc_18001B2EB
0x18001b2e5  call    cs:__imp_LocalFree
0x18001b2eb  add     rsp, 20h
0x18001b2ef  pop     rbx
0x18001b2f0  retn
```
