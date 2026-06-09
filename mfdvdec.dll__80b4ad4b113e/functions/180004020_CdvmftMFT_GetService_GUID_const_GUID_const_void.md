# CdvmftMFT::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x180004020`
- end: `0x180004057`
- name: `?GetService@CdvmftMFT@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `55`
- prototype: `__int64 __fastcall(CdvmftMFT *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180004020`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CdvmftMFT::GetService(CdvmftMFT *this, const struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  if ( *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4 == *(_QWORD *)a2->Data4 )
  {
    return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this - 14))(
             *((_QWORD *)this - 14),
             a3,
             a4);
  }
  else
  {
    return 3222091450LL;
  }
}

```

## disassembly

```asm
0x180004020  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x180004027  mov     r10, r8
0x18000402a  cmp     rax, [rdx]
0x18000402d  jnz     short loc_180004051
0x18000402f  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x180004036  cmp     rax, [rdx+8]
0x18000403a  jnz     short loc_180004051
0x18000403c  mov     rcx, [rcx-70h]
0x180004040  mov     r8, r9
0x180004043  mov     rdx, r10
0x180004046  mov     rax, [rcx]
0x180004049  mov     rax, [rax]
0x18000404c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004051  mov     eax, 0C00D36BAh
0x180004056  retn
```
