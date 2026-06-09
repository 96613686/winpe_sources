# ATL::CComCriticalSection::Init(void)

- ea: `0x1800079f0`
- end: `0x180007a17`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001110`
- `0x1800011b0`
- `0x1800011f0`
- `0x1800012a0`
- `0x180006a6c`
- `0x180006b84`
- `0x180006c9c`
- `0x180006d90`
- `0x180009c78`

## callees

- `0x1800079f0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800079f4`
- `KERNEL32!InitializeCriticalSection` at `0x1800079f4`

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
0x1800079f0  sub     rsp, 38h
0x1800079f4  call    cs:__imp_InitializeCriticalSection
0x1800079fb  nop     dword ptr [rax+rax+00h]
0x180007a00  xor     eax, eax
0x180007a02  mov     [rsp+38h+var_18], eax
0x180007a06  jmp     short loc_180007A11
0x180007a08  mov     eax, 8007000Eh
0x180007a0d  mov     [rsp+38h+var_18], eax
0x180007a11  add     rsp, 38h
0x180007a15  retn
```
