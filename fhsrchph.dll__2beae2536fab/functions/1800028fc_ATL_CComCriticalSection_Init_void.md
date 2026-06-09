# ATL::CComCriticalSection::Init(void)

- ea: `0x1800028fc`
- end: `0x18000291c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010b0`
- `0x1800010f0`
- `0x180001130`
- `0x180004224`
- `0x180004350`
- `0x1800044dc`
- `0x180004628`
- `0x180004750`
- `0x18000487c`
- `0x180006164`

## callees

- `0x1800028fc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180002900`
- `KERNEL32!InitializeCriticalSection` at `0x180002900`

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
0x1800028fc  sub     rsp, 38h
0x180002900  call    cs:__imp_InitializeCriticalSection
0x180002906  xor     eax, eax
0x180002908  mov     [rsp+38h+var_18], eax
0x18000290c  jmp     short loc_180002917
0x18000290e  mov     eax, 8007000Eh
0x180002913  mov     [rsp+38h+var_18], eax
0x180002917  add     rsp, 38h
0x18000291b  retn
```
