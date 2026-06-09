# ATL::CComCriticalSection::Init(void)

- ea: `0x180003edc`
- end: `0x180003efc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x1800010a0`
- `0x1800010d0`
- `0x180003b08`
- `0x180003c00`
- `0x18000547c`
- `0x18000579c`

## callees

- `0x180003edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003ee0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003ee0`

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
0x180003edc  sub     rsp, 38h
0x180003ee0  call    cs:__imp_InitializeCriticalSection
0x180003ee6  xor     eax, eax
0x180003ee8  mov     [rsp+38h+var_18], eax
0x180003eec  jmp     short loc_180003EF7
0x180003eee  mov     eax, 8007000Eh
0x180003ef3  mov     [rsp+38h+var_18], eax
0x180003ef7  add     rsp, 38h
0x180003efb  retn
0x180006416  push    rbp
0x180006418  sub     rsp, 20h
0x18000641c  mov     rbp, rdx
0x18000641f  mov     rax, [rcx]
0x180006422  xor     ecx, ecx
0x180006424  cmp     dword ptr [rax], 0C0000017h
0x18000642a  setz    cl
0x18000642d  mov     eax, ecx
0x18000642f  add     rsp, 20h
0x180006433  pop     rbp
0x180006434  retn
```
