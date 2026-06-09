# ATL::CComCriticalSection::Init(void)

- ea: `0x180015510`
- end: `0x180015530`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800026b0`
- `0x180002830`
- `0x180002870`
- `0x1800155b4`
- `0x1800293e0`

## callees

- `0x180015510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015514`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015514`

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
0x180015510  sub     rsp, 38h
0x180015514  call    cs:__imp_InitializeCriticalSection
0x18001551a  xor     eax, eax
0x18001551c  mov     [rsp+38h+var_18], eax
0x180015520  jmp     short loc_18001552B
0x180015522  mov     eax, 8007000Eh
0x180015527  mov     [rsp+38h+var_18], eax
0x18001552b  add     rsp, 38h
0x18001552f  retn
```
