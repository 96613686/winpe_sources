# ATL::CComCriticalSection::Init(void)

- ea: `0x18000303c`
- end: `0x18000305c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001800`
- `0x180001870`
- `0x180002d28`
- `0x180002e00`
- `0x1800034b0`
- `0x18000359c`
- `0x180004198`

## callees

- `0x18000303c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003040`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003040`

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
0x18000303c  sub     rsp, 38h
0x180003040  call    cs:__imp_InitializeCriticalSection
0x180003046  xor     eax, eax
0x180003048  mov     [rsp+38h+var_18], eax
0x18000304c  jmp     short loc_180003057
0x18000304e  mov     eax, 8007000Eh
0x180003053  mov     [rsp+38h+var_18], eax
0x180003057  add     rsp, 38h
0x18000305b  retn
```
