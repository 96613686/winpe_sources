# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x14000c460`
- end: `0x14000c482`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003c200`

## callees

- `0x14000c460`
- `0x14000cea8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000c46d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000c46d`

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
0x14000c460  sub     rsp, 28h
0x14000c464  mov     edx, [rcx+8]; dwFlags
0x14000c467  xor     r8d, r8d; lpContext
0x14000c46a  mov     rcx, [rcx]; lpInitOnce
0x14000c46d  call    cs:__imp_InitOnceComplete
0x14000c473  test    eax, eax
0x14000c475  jz      short loc_14000C47C
0x14000c477  add     rsp, 28h
0x14000c47b  retn
0x14000c47c  call    __std_init_once_link_alternate_names_and_abort
```
