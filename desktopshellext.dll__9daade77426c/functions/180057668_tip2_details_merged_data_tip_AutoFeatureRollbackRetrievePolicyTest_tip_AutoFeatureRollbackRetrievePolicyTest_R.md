# tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::Release(void)

- ea: `0x180057668`
- end: `0x1800576a0`
- name: `?Release@?$merged_data@U_tip_AutoFeatureRollbackRetrievePolicyTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800557dc`
- `0x180059194`
- `0x180059250`
- `0x18007ca54`

## callees

- `0x1800557f8`
- `0x180057668`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005768d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005768d`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 68);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::~merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180057668  mov     [rsp+arg_0], rbx
0x18005766d  push    rdi
0x18005766e  sub     rsp, 20h
0x180057672  mov     rdi, rcx
0x180057675  or      ebx, 0FFFFFFFFh
0x180057678  lock xadd [rcx+110h], ebx
0x180057680  sub     ebx, 1
0x180057683  jnz     short loc_180057693
0x180057685  call    ??1?$merged_data@U_tip_AutoFeatureRollbackRetrievePolicyTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::~merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>(void)
0x18005768a  mov     rcx, rdi; pv
0x18005768d  call    cs:__imp_CoTaskMemFree
0x180057693  mov     eax, ebx
0x180057695  mov     rbx, [rsp+28h+arg_0]
0x18005769a  add     rsp, 20h
0x18005769e  pop     rdi
0x18005769f  retn
```
