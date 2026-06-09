# ATL::CComCriticalSection::Init(void)

- ea: `0x180002d1c`
- end: `0x180002d3c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010e0`
- `0x180001120`
- `0x180002d44`
- `0x18000c1a0`

## callees

- `0x180002d1c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002d20`
- `KERNEL32!InitializeCriticalSection` at `0x180002d20`

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
0x180002d1c  sub     rsp, 38h
0x180002d20  call    cs:__imp_InitializeCriticalSection
0x180002d26  xor     eax, eax
0x180002d28  mov     [rsp+38h+var_18], eax
0x180002d2c  jmp     short loc_180002D37
0x180002d2e  mov     eax, 8007000Eh
0x180002d33  mov     [rsp+38h+var_18], eax
0x180002d37  add     rsp, 38h
0x180002d3b  retn
```
