# ATL::CComCriticalSection::Init(void)

- ea: `0x180004fbc`
- end: `0x180004fdc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001bd0`
- `0x180001d60`
- `0x180001dc0`
- `0x18000617c`
- `0x1800063fc`
- `0x18001b350`

## callees

- `0x180004fbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004fc0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004fc0`

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
0x180004fbc  sub     rsp, 38h
0x180004fc0  call    cs:__imp_InitializeCriticalSection
0x180004fc6  xor     eax, eax
0x180004fc8  mov     [rsp+38h+var_18], eax
0x180004fcc  jmp     short loc_180004FD7
0x180004fce  mov     eax, 8007000Eh
0x180004fd3  mov     [rsp+38h+var_18], eax
0x180004fd7  add     rsp, 38h
0x180004fdb  retn
```
