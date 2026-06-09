# ATL::CComCriticalSection::Init(void)

- ea: `0x14000353c`
- end: `0x14000355c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001120`
- `0x140001160`
- `0x1400011a0`
- `0x140002ed0`

## callees

- `0x14000353c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140003540`
- `KERNEL32!InitializeCriticalSection` at `0x140003540`

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
0x14000353c  sub     rsp, 38h
0x140003540  call    cs:__imp_InitializeCriticalSection
0x140003546  xor     eax, eax
0x140003548  mov     [rsp+38h+var_18], eax
0x14000354c  jmp     short loc_140003557
0x14000354e  mov     eax, 8007000Eh
0x140003553  mov     [rsp+38h+var_18], eax
0x140003557  add     rsp, 38h
0x14000355b  retn
0x140006776  push    rbp
0x140006778  sub     rsp, 20h
0x14000677c  mov     rbp, rdx
0x14000677f  mov     rax, [rcx]
0x140006782  xor     ecx, ecx
0x140006784  cmp     dword ptr [rax], 0C0000017h
0x14000678a  setz    cl
0x14000678d  mov     eax, ecx
0x14000678f  add     rsp, 20h
0x140006793  pop     rbp
0x140006794  retn
```
