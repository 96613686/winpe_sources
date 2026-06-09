# ATL::CComCriticalSection::Init(void)

- ea: `0x180005598`
- end: `0x1800055b8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `23`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001210`
- `0x180001340`
- `0x180001380`
- `0x180001400`
- `0x180028804`
- `0x180029418`
- `0x180029534`
- `0x18002964c`
- `0x180029730`
- `0x180029d80`
- `0x18002c084`
- `0x18002c154`
- `0x18003b2e4`
- `0x18003d79c`
- `0x18003d844`
- `0x18003d954`
- `0x18003da70`
- `0x180054834`
- `0x180054944`
- `0x180054a64`
- `0x180054b74`
- `0x180056e20`
- `0x18005c380`

## callees

- `0x180005598`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000559c`
- `KERNEL32!InitializeCriticalSection` at `0x18000559c`

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
0x180005598  sub     rsp, 38h
0x18000559c  call    cs:__imp_InitializeCriticalSection
0x1800055a2  xor     eax, eax
0x1800055a4  mov     [rsp+38h+var_18], eax
0x1800055a8  jmp     short loc_1800055B3
0x1800055aa  mov     eax, 8007000Eh
0x1800055af  mov     [rsp+38h+var_18], eax
0x1800055b3  add     rsp, 38h
0x1800055b7  retn
```
