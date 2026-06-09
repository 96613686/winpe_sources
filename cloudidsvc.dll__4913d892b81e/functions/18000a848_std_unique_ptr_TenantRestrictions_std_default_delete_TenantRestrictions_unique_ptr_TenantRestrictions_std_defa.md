# std::unique_ptr<TenantRestrictions,std::default_delete<TenantRestrictions>>::~unique_ptr<TenantRestrictions,std::default_delete<TenantRestrictions>>(void)

- ea: `0x18000a848`
- end: `0x18000a85e`
- name: `??1?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800115c0`

## callees

- `0x18000a848`
- `0x18000ac74`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<TenantRestrictions>::~unique_ptr<TenantRestrictions>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<TenantRestrictions>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000a848  sub     rsp, 28h
0x18000a84c  mov     rdx, [rcx]
0x18000a84f  test    rdx, rdx
0x18000a852  jz      short loc_18000A859
0x18000a854  call    ??R?$default_delete@VTenantRestrictions@@@std@@QEBAXPEAVTenantRestrictions@@@Z; std::default_delete<TenantRestrictions>::operator()(TenantRestrictions *)
0x18000a859  add     rsp, 28h
0x18000a85d  retn
```
