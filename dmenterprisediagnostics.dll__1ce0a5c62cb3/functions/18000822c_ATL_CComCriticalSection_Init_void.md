# ATL::CComCriticalSection::Init(void)

- ea: `0x18000822c`
- end: `0x18000824c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001140`
- `0x180001230`
- `0x1800012f0`
- `0x180024090`

## callees

- `0x18000822c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008230`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008230`

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
0x18000822c  sub     rsp, 38h
0x180008230  call    cs:__imp_InitializeCriticalSection
0x180008236  xor     eax, eax
0x180008238  mov     [rsp+38h+var_18], eax
0x18000823c  jmp     short loc_180008247
0x18000823e  mov     eax, 8007000Eh
0x180008243  mov     [rsp+38h+var_18], eax
0x180008247  add     rsp, 38h
0x18000824b  retn
```
