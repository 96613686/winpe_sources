# _com_error::~_com_error(void)

- ea: `0x14000ceb4`
- end: `0x14000cef2`
- name: `??1_com_error@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(_com_error *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cf00`

## callees

- `0x14000ceb4`
- `0x140020010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000cee5`
- `KERNEL32!LocalFree` at `0x14000cee5`

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
0x14000ceb4  push    rbx
0x14000ceb6  sub     rsp, 20h
0x14000ceba  mov     rbx, rcx
0x14000cebd  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000cec4  mov     [rcx], rax
0x14000cec7  mov     rcx, [rcx+10h]
0x14000cecb  test    rcx, rcx
0x14000cece  jz      short loc_14000CEDC
0x14000ced0  mov     rax, [rcx]
0x14000ced3  mov     rax, [rax+10h]
0x14000ced7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cedc  mov     rcx, [rbx+18h]; hMem
0x14000cee0  test    rcx, rcx
0x14000cee3  jz      short loc_14000CEEC
0x14000cee5  call    cs:__imp_LocalFree
0x14000ceeb  nop
0x14000ceec  add     rsp, 20h
0x14000cef0  pop     rbx
0x14000cef1  retn
```
