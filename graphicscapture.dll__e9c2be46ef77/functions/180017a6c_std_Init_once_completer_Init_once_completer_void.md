# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180017a6c`
- end: `0x180017a8e`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016870`
- `0x180018ef0`
- `0x180026872`

## callees

- `0x1800020f8`
- `0x180017a6c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017a79`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017a79`

## pseudocode

```c
void __fastcall std::_Init_once_completer::~_Init_once_completer(std::_Init_once_completer *this)
{
  if ( !InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0) )
    _std_init_once_link_alternate_names_and_abort();
}

```

## disassembly

```asm
0x180017a6c  sub     rsp, 28h
0x180017a70  mov     edx, [rcx+8]; dwFlags
0x180017a73  xor     r8d, r8d; lpContext
0x180017a76  mov     rcx, [rcx]; lpInitOnce
0x180017a79  call    cs:__imp_InitOnceComplete
0x180017a7f  test    eax, eax
0x180017a81  jz      short loc_180017A88
0x180017a83  add     rsp, 28h
0x180017a87  retn
0x180017a88  call    __std_init_once_link_alternate_names_and_abort
```
