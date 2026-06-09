# ATL::CComCriticalSection::Init(void)

- ea: `0x1800082fc`
- end: `0x18000831c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001190`
- `0x180001200`
- `0x180001240`
- `0x180008324`
- `0x18002cbf4`

## callees

- `0x1800082fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008300`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008300`

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
0x1800082fc  sub     rsp, 38h
0x180008300  call    cs:__imp_InitializeCriticalSection
0x180008306  xor     eax, eax
0x180008308  mov     [rsp+38h+var_18], eax
0x18000830c  jmp     short loc_180008317
0x18000830e  mov     eax, 8007000Eh
0x180008313  mov     [rsp+38h+var_18], eax
0x180008317  add     rsp, 38h
0x18000831b  retn
```
