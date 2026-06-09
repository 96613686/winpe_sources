# ATL::CComCriticalSection::Init(void)

- ea: `0x180015c68`
- end: `0x180015c92`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015ca0`

## callees

- `0x180015c68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015c70`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015c70`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x180015c68  push    rbx
0x180015c6a  sub     rsp, 20h
0x180015c6e  xor     ebx, ebx
0x180015c70  call    cs:__imp_InitializeCriticalSection
0x180015c76  jmp     short loc_180015C8A
0x180015c78  mov     ebx, 80004005h
0x180015c7d  mov     ecx, 8007000Eh
0x180015c82  cmp     eax, 0C0000017h
0x180015c87  cmovz   ebx, ecx
0x180015c8a  mov     eax, ebx
0x180015c8c  add     rsp, 20h
0x180015c90  pop     rbx
0x180015c91  retn
```
