# CConfigServiceProvider2Impl::`vector deleting destructor'(uint)

- ea: `0x180008300`
- end: `0x180008337`
- name: `??_ECConfigServiceProvider2Impl@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(CConfigServiceProvider2Impl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x1800082b8`
- `0x180008300`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000831c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000831c`

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
0x180008300  mov     [rsp+arg_0], rbx
0x180008305  push    rdi
0x180008306  sub     rsp, 20h
0x18000830a  mov     ebx, edx
0x18000830c  mov     rdi, rcx
0x18000830f  call    ??1CConfigServiceProvider2Impl@@UEAA@XZ; CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)
0x180008314  test    bl, 1
0x180008317  jz      short loc_180008328
0x180008319  mov     rcx, rdi
0x18000831c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008323  nop     dword ptr [rax+rax+00h]
0x180008328  mov     rbx, [rsp+28h+arg_0]
0x18000832d  mov     rax, rdi
0x180008330  add     rsp, 20h
0x180008334  pop     rdi
0x180008335  retn
```
