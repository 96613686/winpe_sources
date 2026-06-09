# ATL::CComCriticalSection::Init(void)

- ea: `0x18000433c`
- end: `0x18000435c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x180001090`
- `0x1800010d0`
- `0x180003be4`
- `0x180003d18`
- `0x180003e20`
- `0x180003f78`
- `0x180005b1c`
- `0x180005e3c`

## callees

- `0x18000433c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004340`
- `KERNEL32!InitializeCriticalSection` at `0x180004340`

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
0x18000433c  sub     rsp, 38h
0x180004340  call    cs:__imp_InitializeCriticalSection
0x180004346  xor     eax, eax
0x180004348  mov     [rsp+38h+var_18], eax
0x18000434c  jmp     short loc_180004357
0x18000434e  mov     eax, 8007000Eh
0x180004353  mov     [rsp+38h+var_18], eax
0x180004357  add     rsp, 38h
0x18000435b  retn
```
