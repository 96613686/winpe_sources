# ATL::CComCriticalSection::Init(void)

- ea: `0x180010418`
- end: `0x180010438`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001260`
- `0x180001330`
- `0x180001370`
- `0x1800104bc`
- `0x18001ce54`

## callees

- `0x180010418`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001041c`
- `KERNEL32!InitializeCriticalSection` at `0x18001041c`

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
0x180010418  sub     rsp, 38h
0x18001041c  call    cs:__imp_InitializeCriticalSection
0x180010422  xor     eax, eax
0x180010424  mov     [rsp+38h+var_18], eax
0x180010428  jmp     short loc_180010433
0x18001042a  mov     eax, 8007000Eh
0x18001042f  mov     [rsp+38h+var_18], eax
0x180010433  add     rsp, 38h
0x180010437  retn
```
