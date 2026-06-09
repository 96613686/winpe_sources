# MinComObject<CSDKConfigurationController>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ee90`
- end: `0x18000eea2`
- name: `?QueryInterface@?$MinComObject@VCSDKConfigurationController@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001f30`

## pseudocode

```c
__int64 __fastcall MinComObject<CSDKConfigurationController>::QueryInterface(
        void *a1,
        const struct _GUID *a2,
        void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CSDKConfigurationController::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000ee90  mov     r9, r8; void **
0x18000ee93  mov     r8, rdx; struct _GUID *
0x18000ee96  lea     rdx, ?_entries@?1??_GetEntries@CSDKConfigurationController@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000ee9d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
