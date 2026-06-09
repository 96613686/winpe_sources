# ATL::CComCriticalSection::Init(void)

- ea: `0x1800039cc`
- end: `0x1800039ec`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010b0`
- `0x1800010f0`
- `0x180001130`
- `0x180003214`
- `0x180003358`
- `0x18000349c`
- `0x180003600`
- `0x180003750`
- `0x180005074`

## callees

- `0x1800039cc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800039d0`
- `KERNEL32!InitializeCriticalSection` at `0x1800039d0`

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
0x1800039cc  sub     rsp, 38h
0x1800039d0  call    cs:__imp_InitializeCriticalSection
0x1800039d6  xor     eax, eax
0x1800039d8  mov     [rsp+38h+var_18], eax
0x1800039dc  jmp     short loc_1800039E7
0x1800039de  mov     eax, 8007000Eh
0x1800039e3  mov     [rsp+38h+var_18], eax
0x1800039e7  add     rsp, 38h
0x1800039eb  retn
```
