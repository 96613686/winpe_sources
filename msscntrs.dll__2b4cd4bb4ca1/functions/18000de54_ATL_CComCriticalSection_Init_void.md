# ATL::CComCriticalSection::Init(void)

- ea: `0x18000de54`
- end: `0x18000de74`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001fe0`
- `0x180002030`
- `0x180002060`
- `0x18000ffec`
- `0x180010314`

## callees

- `0x18000de54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000de58`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000de58`

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
0x18000de54  sub     rsp, 38h
0x18000de58  call    cs:__imp_InitializeCriticalSection
0x18000de5e  xor     eax, eax
0x18000de60  mov     [rsp+38h+var_18], eax
0x18000de64  jmp     short loc_18000DE6F
0x18000de66  mov     eax, 8007000Eh
0x18000de6b  mov     [rsp+38h+var_18], eax
0x18000de6f  add     rsp, 38h
0x18000de73  retn
```
