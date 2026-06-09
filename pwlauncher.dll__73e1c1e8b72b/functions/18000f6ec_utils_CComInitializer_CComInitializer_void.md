# utils::CComInitializer::~CComInitializer(void)

- ea: `0x18000f6ec`
- end: `0x18000f6fd`
- name: `??1CComInitializer@utils@@UEAA@XZ`
- size: `17`
- prototype: `void __fastcall(utils::CComInitializer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010990`

## import_xrefs

- `ole32!CoUninitialize` at `0x18000f6f6`

## pseudocode

```c
void __fastcall utils::CComInitializer::~CComInitializer(utils::CComInitializer *this)
{
  *(_QWORD *)this = &utils::CComInitializer::`vftable';
  CoUninitialize();
}

```

## disassembly

```asm
0x18000f6ec  lea     rax, ??_7CComInitializer@utils@@6B@; const utils::CComInitializer::`vftable'
0x18000f6f3  mov     [rcx], rax
0x18000f6f6  jmp     cs:__imp_CoUninitialize
```
