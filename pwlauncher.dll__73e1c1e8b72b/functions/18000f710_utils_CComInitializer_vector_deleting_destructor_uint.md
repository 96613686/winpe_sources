# utils::CComInitializer::`vector deleting destructor'(uint)

- ea: `0x18000f710`
- end: `0x18000f74b`
- name: `??_ECComInitializer@utils@@UEAAPEAXI@Z`
- size: `59`
- prototype: `utils::CComInitializer *__fastcall(utils::CComInitializer *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000f710`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f737`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f737`
- `ole32!CoUninitialize` at `0x18000f729`
- `ole32!CoUninitialize` at `0x18000f729`

## pseudocode

```c
utils::CComInitializer *__fastcall utils::CComInitializer::`vector deleting destructor'(
        utils::CComInitializer *this,
        char a2)
{
  *(_QWORD *)this = &utils::CComInitializer::`vftable';
  CoUninitialize();
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000f710  mov     [rsp+arg_0], rbx
0x18000f715  push    rdi
0x18000f716  sub     rsp, 20h
0x18000f71a  lea     rax, ??_7CComInitializer@utils@@6B@; const utils::CComInitializer::`vftable'
0x18000f721  mov     ebx, edx
0x18000f723  mov     [rcx], rax
0x18000f726  mov     rdi, rcx
0x18000f729  call    cs:__imp_CoUninitialize
0x18000f72f  test    bl, 1
0x18000f732  jz      short loc_18000F73D
0x18000f734  mov     rcx, rdi
0x18000f737  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f73d  mov     rbx, [rsp+28h+arg_0]
0x18000f742  mov     rax, rdi
0x18000f745  add     rsp, 20h
0x18000f749  pop     rdi
0x18000f74a  retn
```
