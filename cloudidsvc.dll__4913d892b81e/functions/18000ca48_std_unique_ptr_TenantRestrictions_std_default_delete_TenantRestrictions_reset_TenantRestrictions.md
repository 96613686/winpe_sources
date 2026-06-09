# std::unique_ptr<TenantRestrictions,std::default_delete<TenantRestrictions>>::reset(TenantRestrictions *)

- ea: `0x18000ca48`
- end: `0x18000ca6c`
- name: `?reset@?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@QEAAXPEAVTenantRestrictions@@@Z`
- size: `36`
- prototype: `void __fastcall(__int64, TenantRestrictions *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f7c`
- `0x18000b080`

## callees

- `0x18000ac74`
- `0x18000ca48`

## pseudocode

```c
void __fastcall std::unique_ptr<TenantRestrictions>::reset(__int64 a1, TenantRestrictions *a2)
{
  HANDLE *v2; // rax

  v2 = (HANDLE *)g_trGlobals;
  g_trGlobals = a2;
  if ( v2 )
    std::default_delete<TenantRestrictions>::operator()(a1, v2);
}

```

## disassembly

```asm
0x18000ca48  sub     rsp, 28h
0x18000ca4c  mov     rax, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000ca53  mov     cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A, rdx; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000ca5a  test    rax, rax
0x18000ca5d  jz      short loc_18000CA67
0x18000ca5f  mov     rdx, rax
0x18000ca62  call    ??R?$default_delete@VTenantRestrictions@@@std@@QEBAXPEAVTenantRestrictions@@@Z; std::default_delete<TenantRestrictions>::operator()(TenantRestrictions *)
0x18000ca67  add     rsp, 28h
0x18000ca6b  retn
```
