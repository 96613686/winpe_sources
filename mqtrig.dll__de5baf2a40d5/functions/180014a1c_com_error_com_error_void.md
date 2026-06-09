# _com_error::~_com_error(void)

- ea: `0x180014a1c`
- end: `0x180014a59`
- name: `??1_com_error@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014a60`

## callees

- `0x180014a1c`
- `0x180022010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180014a4d`
- `KERNEL32!LocalFree` at `0x180014a4d`

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
0x180014a1c  push    rbx
0x180014a1e  sub     rsp, 20h
0x180014a22  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180014a29  mov     rbx, rcx
0x180014a2c  mov     [rcx], rax
0x180014a2f  mov     rcx, [rcx+10h]
0x180014a33  test    rcx, rcx
0x180014a36  jz      short loc_180014A44
0x180014a38  mov     rax, [rcx]
0x180014a3b  mov     rax, [rax+10h]
0x180014a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a44  mov     rcx, [rbx+18h]; hMem
0x180014a48  test    rcx, rcx
0x180014a4b  jz      short loc_180014A53
0x180014a4d  call    cs:__imp_LocalFree
0x180014a53  add     rsp, 20h
0x180014a57  pop     rbx
0x180014a58  retn
```
