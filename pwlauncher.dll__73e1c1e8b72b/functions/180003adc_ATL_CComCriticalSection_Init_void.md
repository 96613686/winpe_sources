# ATL::CComCriticalSection::Init(void)

- ea: `0x180003adc`
- end: `0x180003afc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001130`
- `0x1800013e0`
- `0x180001420`
- `0x180001460`
- `0x180004d04`
- `0x18000beb0`

## callees

- `0x180003adc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180003ae0`
- `KERNEL32!InitializeCriticalSection` at `0x180003ae0`

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
0x180003adc  sub     rsp, 38h
0x180003ae0  call    cs:__imp_InitializeCriticalSection
0x180003ae6  xor     eax, eax
0x180003ae8  mov     [rsp+38h+var_18], eax
0x180003aec  jmp     short loc_180003AF7
0x180003aee  mov     eax, 8007000Eh
0x180003af3  mov     [rsp+38h+var_18], eax
0x180003af7  add     rsp, 38h
0x180003afb  retn
```
