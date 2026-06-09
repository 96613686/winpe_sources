# std::default_delete<TenantRestrictions>::operator()(TenantRestrictions *)

- ea: `0x18000ac74`
- end: `0x18000ac9c`
- name: `??R?$default_delete@VTenantRestrictions@@@std@@QEBAXPEAVTenantRestrictions@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, HANDLE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a848`
- `0x18000ca48`

## callees

- `0x180001a74`
- `0x18000a93c`
- `0x18000ac74`

## pseudocode

```c
void __fastcall std::default_delete<TenantRestrictions>::operator()(__int64 a1, HANDLE *a2)
{
  if ( a2 )
  {
    TenantRestrictions::~TenantRestrictions(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000ac74  test    rdx, rdx
0x18000ac77  jz      short locret_18000AC9B
0x18000ac79  push    rbx
0x18000ac7a  sub     rsp, 20h
0x18000ac7e  mov     rcx, rdx; this
0x18000ac81  mov     rbx, rdx
0x18000ac84  call    ??1TenantRestrictions@@QEAA@XZ; TenantRestrictions::~TenantRestrictions(void)
0x18000ac89  mov     edx, 0D8h; unsigned __int64
0x18000ac8e  mov     rcx, rbx; void *
0x18000ac91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac96  add     rsp, 20h
0x18000ac9a  pop     rbx
0x18000ac9b  retn
```
