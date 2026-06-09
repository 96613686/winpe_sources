# ATL::CComCriticalSection::Init(void)

- ea: `0x180004a4c`
- end: `0x180004a6c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001820`
- `0x1800018b0`
- `0x1800018f0`
- `0x1800036b4`
- `0x1800037e8`
- `0x180003910`
- `0x180007c80`

## callees

- `0x180004a4c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004a50`
- `KERNEL32!InitializeCriticalSection` at `0x180004a50`

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
0x180004a4c  sub     rsp, 38h
0x180004a50  call    cs:__imp_InitializeCriticalSection
0x180004a56  xor     eax, eax
0x180004a58  mov     [rsp+38h+var_18], eax
0x180004a5c  jmp     short loc_180004A67
0x180004a5e  mov     eax, 8007000Eh
0x180004a63  mov     [rsp+38h+var_18], eax
0x180004a67  add     rsp, 38h
0x180004a6b  retn
```
