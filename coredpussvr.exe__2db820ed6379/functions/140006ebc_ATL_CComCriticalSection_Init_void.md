# ATL::CComCriticalSection::Init(void)

- ea: `0x140006ebc`
- end: `0x140006ee3`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001120`
- `0x140001170`
- `0x1400011a0`
- `0x140006b40`
- `0x140008460`
- `0x14000878c`

## callees

- `0x140006ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140006ec0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140006ec0`

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
0x140006ebc  sub     rsp, 38h
0x140006ec0  call    cs:__imp_InitializeCriticalSection
0x140006ec7  nop     dword ptr [rax+rax+00h]
0x140006ecc  xor     eax, eax
0x140006ece  mov     [rsp+38h+var_18], eax
0x140006ed2  jmp     short loc_140006EDD
0x140006ed4  mov     eax, 8007000Eh
0x140006ed9  mov     [rsp+38h+var_18], eax
0x140006edd  add     rsp, 38h
0x140006ee1  retn
```
