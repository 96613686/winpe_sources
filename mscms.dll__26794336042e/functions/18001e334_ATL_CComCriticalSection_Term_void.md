# ATL::CComCriticalSection::Term(void)

- ea: `0x18001e334`
- end: `0x18001e345`
- name: `?Term@CComCriticalSection@ATL@@QEAAJXZ`
- size: `17`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001e2bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e338`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e338`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Term(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x18001e334  sub     rsp, 28h
0x18001e338  call    cs:__imp_DeleteCriticalSection
0x18001e33e  xor     eax, eax
0x18001e340  add     rsp, 28h
0x18001e344  retn
```
