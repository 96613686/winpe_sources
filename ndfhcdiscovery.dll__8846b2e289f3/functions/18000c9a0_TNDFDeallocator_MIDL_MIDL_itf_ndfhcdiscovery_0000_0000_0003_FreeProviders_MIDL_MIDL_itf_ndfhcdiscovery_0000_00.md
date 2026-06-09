# TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,&FreeProviders(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,ulong,int)>::~TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,&FreeProviders(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,ulong,int)>(void)

- ea: `0x18000c9a0`
- end: `0x18000c9c7`
- name: `??1?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@$1?FreeProviders@@YAXPEAU1@KH@Z@@QEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013f71`

## callees

- `0x18000c9a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c9b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c9b5`

## pseudocode

```c
void __fastcall TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,&void FreeProviders(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,unsigned long,int)>::~TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,&void FreeProviders(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,unsigned long,int)>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    if ( *(_DWORD *)(a1 + 12) )
      CoTaskMemFree(v2);
  }
}

```

## disassembly

```asm
0x18000c9a0  sub     rsp, 28h
0x18000c9a4  mov     rax, rcx
0x18000c9a7  mov     rcx, [rcx]; pv
0x18000c9aa  test    rcx, rcx
0x18000c9ad  jz      short loc_18000C9C1
0x18000c9af  cmp     dword ptr [rax+0Ch], 0
0x18000c9b3  jz      short loc_18000C9C1
0x18000c9b5  call    cs:__imp_CoTaskMemFree
0x18000c9bc  nop     dword ptr [rax+rax+00h]
0x18000c9c1  add     rsp, 28h
0x18000c9c5  retn
```
