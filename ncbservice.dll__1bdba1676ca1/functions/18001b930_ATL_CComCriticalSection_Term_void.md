# ATL::CComCriticalSection::Term(void)

- ea: `0x18001b930`
- end: `0x18001b941`
- name: `?Term@CComCriticalSection@ATL@@QEAAJXZ`
- size: `17`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180032990`
- `0x180032a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b934`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b934`

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
0x18001b930  sub     rsp, 28h
0x18001b934  call    cs:__imp_DeleteCriticalSection
0x18001b93a  xor     eax, eax
0x18001b93c  add     rsp, 28h
0x18001b940  retn
```
