# ATL::CComCriticalSection::Init(void)

- ea: `0x18000a660`
- end: `0x18000a680`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002650`
- `0x1800026a0`
- `0x18000a530`
- `0x18000a630`
- `0x18000dfc8`
- `0x18000e128`

## callees

- `0x18000a660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a664`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a664`

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
0x18000a660  sub     rsp, 38h
0x18000a664  call    cs:__imp_InitializeCriticalSection
0x18000a66a  xor     eax, eax
0x18000a66c  mov     [rsp+38h+var_18], eax
0x18000a670  jmp     short loc_18000A67B
0x18000a672  mov     eax, 8007000Eh
0x18000a677  mov     [rsp+38h+var_18], eax
0x18000a67b  add     rsp, 38h
0x18000a67f  retn
```
