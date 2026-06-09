# ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x140002310`
- end: `0x140002324`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIIisServiceControl@@$1?IID_IIisServiceControl@@3U_GUID@@B$1?LIBID_IISRSTALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140002310`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x140002310  test    rdx, rdx
0x140002313  jnz     short loc_14000231B
0x140002315  mov     eax, 80070057h
0x14000231a  retn
0x14000231b  mov     dword ptr [rdx], 1
0x140002321  xor     eax, eax
0x140002323  retn
```
