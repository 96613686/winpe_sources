# ATL::CComCriticalSection::Init(void)

- ea: `0x18000465c`
- end: `0x18000467c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001980`
- `0x1800019d0`
- `0x180001a00`
- `0x180001a40`
- `0x180003ff4`
- `0x180004120`
- `0x180004240`
- `0x180005d2c`
- `0x180006054`

## callees

- `0x18000465c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004660`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004660`

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
0x18000465c  sub     rsp, 38h
0x180004660  call    cs:__imp_InitializeCriticalSection
0x180004666  xor     eax, eax
0x180004668  mov     [rsp+38h+var_18], eax
0x18000466c  jmp     short loc_180004677
0x18000466e  mov     eax, 8007000Eh
0x180004673  mov     [rsp+38h+var_18], eax
0x180004677  add     rsp, 38h
0x18000467b  retn
```
