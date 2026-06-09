# ATL::CComCriticalSection::Init(void)

- ea: `0x1800042bc`
- end: `0x1800042dc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x180001110`
- `0x180001150`
- `0x180001190`
- `0x180005620`
- `0x180006368`
- `0x180006490`
- `0x180009b28`

## callees

- `0x1800042bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800042c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800042c0`

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
0x1800042bc  sub     rsp, 38h
0x1800042c0  call    cs:__imp_InitializeCriticalSection
0x1800042c6  xor     eax, eax
0x1800042c8  mov     [rsp+38h+var_18], eax
0x1800042cc  jmp     short loc_1800042D7
0x1800042ce  mov     eax, 8007000Eh
0x1800042d3  mov     [rsp+38h+var_18], eax
0x1800042d7  add     rsp, 38h
0x1800042db  retn
```
