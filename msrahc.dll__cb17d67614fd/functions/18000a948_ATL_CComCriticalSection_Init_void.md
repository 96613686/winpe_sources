# ATL::CComCriticalSection::Init(void)

- ea: `0x18000a948`
- end: `0x18000a968`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001230`
- `0x1800012a0`
- `0x1800012e0`
- `0x18000a970`
- `0x180014320`

## callees

- `0x18000a948`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000a94c`
- `KERNEL32!InitializeCriticalSection` at `0x18000a94c`

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
0x18000a948  sub     rsp, 38h
0x18000a94c  call    cs:__imp_InitializeCriticalSection
0x18000a952  xor     eax, eax
0x18000a954  mov     [rsp+38h+var_18], eax
0x18000a958  jmp     short loc_18000A963
0x18000a95a  mov     eax, 8007000Eh
0x18000a95f  mov     [rsp+38h+var_18], eax
0x18000a963  add     rsp, 38h
0x18000a967  retn
```
