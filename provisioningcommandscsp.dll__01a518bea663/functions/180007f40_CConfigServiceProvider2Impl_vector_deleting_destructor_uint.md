# CConfigServiceProvider2Impl::`vector deleting destructor'(uint)

- ea: `0x180007f40`
- end: `0x180007f70`
- name: `??_ECConfigServiceProvider2Impl@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CConfigServiceProvider2Impl *__fastcall(CConfigServiceProvider2Impl *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180007f04`
- `0x180007f40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007f5c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f5c`

## pseudocode

```c
CConfigServiceProvider2Impl *__fastcall CConfigServiceProvider2Impl::`vector deleting destructor'(
        CConfigServiceProvider2Impl *this,
        char a2)
{
  CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007f40  mov     [rsp+arg_0], rbx
0x180007f45  push    rdi
0x180007f46  sub     rsp, 20h
0x180007f4a  mov     ebx, edx
0x180007f4c  mov     rdi, rcx
0x180007f4f  call    ??1CConfigServiceProvider2Impl@@UEAA@XZ; CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)
0x180007f54  test    bl, 1
0x180007f57  jz      short loc_180007F62
0x180007f59  mov     rcx, rdi
0x180007f5c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f62  mov     rbx, [rsp+28h+arg_0]
0x180007f67  mov     rax, rdi
0x180007f6a  add     rsp, 20h
0x180007f6e  pop     rdi
0x180007f6f  retn
```
