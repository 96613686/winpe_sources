# ATL::CComCriticalSection::Init(void)

- ea: `0x180006664`
- end: `0x180006684`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001290`
- `0x1800012d0`
- `0x180001300`
- `0x180005140`
- `0x18000a7ac`
- `0x18000aacc`

## callees

- `0x180006664`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006668`
- `KERNEL32!InitializeCriticalSection` at `0x180006668`

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
0x180006664  sub     rsp, 38h
0x180006668  call    cs:__imp_InitializeCriticalSection
0x18000666e  xor     eax, eax
0x180006670  mov     [rsp+38h+var_18], eax
0x180006674  jmp     short loc_18000667F
0x180006676  mov     eax, 8007000Eh
0x18000667b  mov     [rsp+38h+var_18], eax
0x18000667f  add     rsp, 38h
0x180006683  retn
0x180018916  push    rbp
0x180018918  sub     rsp, 20h
0x18001891c  mov     rbp, rdx
0x18001891f  mov     rax, [rcx]
0x180018922  xor     ecx, ecx
0x180018924  cmp     dword ptr [rax], 0C0000017h
0x18001892a  setz    cl
0x18001892d  mov     eax, ecx
0x18001892f  add     rsp, 20h
0x180018933  pop     rbp
0x180018934  retn
```
