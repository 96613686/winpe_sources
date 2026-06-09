# CODBCLOG::~CODBCLOG(void)

- ea: `0x18000a774`
- end: `0x18000a7a6`
- name: `??1CODBCLOG@@IEAA@XZ`
- size: `50`
- prototype: `void __fastcall(CODBCLOG *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c20`
- `0x18000a2b0`
- `0x18000a410`

## callees

- `0x18000bdc0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000a790`
- `KERNEL32!DeleteCriticalSection` at `0x18000a790`
- `KERNEL32!DeleteCriticalSection` at `0x18000a79f`

## pseudocode

```c
void __fastcall CODBCLOG::~CODBCLOG(CODBCLOG *this)
{
  *(_QWORD *)this = &CODBCLOG::`vftable';
  CODBCLOG::TerminateLog(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000a774  push    rbx
0x18000a776  sub     rsp, 20h
0x18000a77a  lea     rax, ??_7CODBCLOG@@6B@; const CODBCLOG::`vftable'
0x18000a781  mov     rbx, rcx
0x18000a784  mov     [rcx], rax
0x18000a787  call    ?TerminateLog@CODBCLOG@@UEAAJXZ; CODBCLOG::TerminateLog(void)
0x18000a78c  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000a790  call    cs:__imp_DeleteCriticalSection
0x18000a796  lea     rcx, [rbx+10h]
0x18000a79a  add     rsp, 20h
0x18000a79e  pop     rbx
0x18000a79f  jmp     cs:__imp_DeleteCriticalSection
```
