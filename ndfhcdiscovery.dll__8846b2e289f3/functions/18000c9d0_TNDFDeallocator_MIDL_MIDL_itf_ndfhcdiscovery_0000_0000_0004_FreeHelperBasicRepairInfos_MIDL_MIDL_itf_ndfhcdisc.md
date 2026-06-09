# TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&FreeHelperBasicRepairInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)>::~TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&FreeHelperBasicRepairInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)>(void)

- ea: `0x18000c9d0`
- end: `0x18000c9ef`
- name: `??1?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$1?FreeHelperBasicRepairInfos@@YAXPEAU1@KH@Z@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180013f83`

## callees

- `0x18000c9d0`
- `0x18000d5d8`

## pseudocode

```c
void __fastcall TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&void FreeHelperBasicRepairInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,unsigned long,int)>::~TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&void FreeHelperBasicRepairInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,unsigned long,int)>(
        __int64 a1)
{
  if ( *(_QWORD *)a1 )
    FreeHelperBasicRootCauseInfos(*(LPVOID **)a1, *(_DWORD *)(a1 + 8), *(_DWORD *)(a1 + 12));
}

```

## disassembly

```asm
0x18000c9d0  sub     rsp, 28h
0x18000c9d4  cmp     qword ptr [rcx], 0
0x18000c9d8  jz      short loc_18000C9E9
0x18000c9da  mov     r8d, [rcx+0Ch]; int
0x18000c9de  mov     edx, [rcx+8]; unsigned int
0x18000c9e1  mov     rcx, [rcx]; pv
0x18000c9e4  call    ?FreeHelperBasicRootCauseInfos@@YAXPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@KH@Z; FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)
0x18000c9e9  add     rsp, 28h
0x18000c9ed  retn
```
