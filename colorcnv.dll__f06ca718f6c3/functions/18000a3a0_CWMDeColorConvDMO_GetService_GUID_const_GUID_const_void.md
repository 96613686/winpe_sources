# CWMDeColorConvDMO::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a3a0`
- end: `0x18000a3f0`
- name: `?GetService@CWMDeColorConvDMO@@MEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWMDeColorConvDMO *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a3a0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::GetService(
        __int64 (__fastcall ***this)(char *, const struct _GUID *, void **),
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rax

  if ( !a4 )
    return 2147500035LL;
  v5 = *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v5 = *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v5 )
    return (**(this - 51))((char *)this - 408, a3, a4);
  *a4 = 0;
  return 3222091450LL;
}

```

## disassembly

```asm
0x18000a3a0  mov     r10, r8
0x18000a3a3  test    r9, r9
0x18000a3a6  jnz     short loc_18000A3AF
0x18000a3a8  mov     eax, 80004003h
0x18000a3ad  jmp     short locret_18000A3EF
0x18000a3af  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x18000a3b6  sub     rax, [rdx]
0x18000a3b9  jnz     short loc_18000A3C6
0x18000a3bb  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x18000a3c2  sub     rax, [rdx+8]
0x18000a3c6  test    rax, rax
0x18000a3c9  jnz     short loc_18000A3E3
0x18000a3cb  add     rcx, 0FFFFFFFFFFFFFE68h
0x18000a3d2  mov     r8, r9
0x18000a3d5  mov     rdx, r10
0x18000a3d8  mov     rax, [rcx]
0x18000a3db  mov     rax, [rax]
0x18000a3de  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e3  mov     qword ptr [r9], 0
0x18000a3ea  mov     eax, 0C00D36BAh
0x18000a3ef  retn
```
