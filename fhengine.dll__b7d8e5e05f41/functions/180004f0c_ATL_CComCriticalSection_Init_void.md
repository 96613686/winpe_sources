# ATL::CComCriticalSection::Init(void)

- ea: `0x180004f0c`
- end: `0x180004f2c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800016d0`
- `0x1800017c0`
- `0x180001800`
- `0x180004f34`
- `0x1800266c0`

## callees

- `0x180004f0c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004f10`
- `KERNEL32!InitializeCriticalSection` at `0x180004f10`

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
0x180004f0c  sub     rsp, 38h
0x180004f10  call    cs:__imp_InitializeCriticalSection
0x180004f16  xor     eax, eax
0x180004f18  mov     [rsp+38h+var_18], eax
0x180004f1c  jmp     short loc_180004F27
0x180004f1e  mov     eax, 8007000Eh
0x180004f23  mov     [rsp+38h+var_18], eax
0x180004f27  add     rsp, 38h
0x180004f2b  retn
```
