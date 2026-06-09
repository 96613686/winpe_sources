# ATL::CComCriticalSection::Init(void)

- ea: `0x180006c30`
- end: `0x180006c50`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x1800010e0`
- `0x180001120`
- `0x180006cd4`
- `0x18000c54c`

## callees

- `0x180006c30`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006c34`
- `KERNEL32!InitializeCriticalSection` at `0x180006c34`

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
0x180006c30  sub     rsp, 38h
0x180006c34  call    cs:__imp_InitializeCriticalSection
0x180006c3a  xor     eax, eax
0x180006c3c  mov     [rsp+38h+var_18], eax
0x180006c40  jmp     short loc_180006C4B
0x180006c42  mov     eax, 8007000Eh
0x180006c47  mov     [rsp+38h+var_18], eax
0x180006c4b  add     rsp, 38h
0x180006c4f  retn
```
