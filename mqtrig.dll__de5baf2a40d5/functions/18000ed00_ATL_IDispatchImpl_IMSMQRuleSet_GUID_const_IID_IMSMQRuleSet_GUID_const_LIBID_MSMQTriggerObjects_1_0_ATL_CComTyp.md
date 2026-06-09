# ATL::IDispatchImpl<IMSMQRuleSet,&_GUID const IID_IMSMQRuleSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x18000ed00`
- end: `0x18000ed14`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIMSMQRuleSet@@$1?IID_IMSMQRuleSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ed00`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMSMQRuleSet,&_GUID const IID_IMSMQRuleSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000ed00  test    rdx, rdx
0x18000ed03  jnz     short loc_18000ED0B
0x18000ed05  mov     eax, 80070057h
0x18000ed0a  retn
0x18000ed0b  mov     dword ptr [rdx], 1
0x18000ed11  xor     eax, eax
0x18000ed13  retn
```
