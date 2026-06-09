# ATL::CComCriticalSection::Init(void)

- ea: `0x18001033c`
- end: `0x18001035c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800010a0`
- `0x1800010f0`
- `0x180001120`
- `0x180001160`
- `0x18000f538`
- `0x18000f6c0`
- `0x18000f828`
- `0x18000f960`
- `0x18000fac0`
- `0x18000fbec`
- `0x18001217c`
- `0x18001249c`

## callees

- `0x18001033c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180010340`
- `KERNEL32!InitializeCriticalSection` at `0x180010340`

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
0x18001033c  sub     rsp, 38h
0x180010340  call    cs:__imp_InitializeCriticalSection
0x180010346  xor     eax, eax
0x180010348  mov     [rsp+38h+var_18], eax
0x18001034c  jmp     short loc_180010357
0x18001034e  mov     eax, 8007000Eh
0x180010353  mov     [rsp+38h+var_18], eax
0x180010357  add     rsp, 38h
0x18001035b  retn
```
