# ATL::CComCriticalSection::Init(void)

- ea: `0x14000623c`
- end: `0x14000625c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001af0`
- `0x140001b40`
- `0x140001b70`
- `0x140001bb0`
- `0x140004948`
- `0x140004a44`
- `0x14000a904`
- `0x14000e20c`
- `0x14000e534`

## callees

- `0x14000623c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140006240`
- `KERNEL32!InitializeCriticalSection` at `0x140006240`

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
0x14000623c  sub     rsp, 38h
0x140006240  call    cs:__imp_InitializeCriticalSection
0x140006246  xor     eax, eax
0x140006248  mov     [rsp+38h+var_18], eax
0x14000624c  jmp     short loc_140006257
0x14000624e  mov     eax, 8007000Eh
0x140006253  mov     [rsp+38h+var_18], eax
0x140006257  add     rsp, 38h
0x14000625b  retn
0x14000f7fe  push    rbp
0x14000f800  sub     rsp, 20h
0x14000f804  mov     rbp, rdx
0x14000f807  mov     rax, [rcx]
0x14000f80a  xor     ecx, ecx
0x14000f80c  cmp     dword ptr [rax], 0C0000017h
0x14000f812  setz    cl
0x14000f815  mov     eax, ecx
0x14000f817  add     rsp, 20h
0x14000f81b  pop     rbp
0x14000f81c  retn
```
