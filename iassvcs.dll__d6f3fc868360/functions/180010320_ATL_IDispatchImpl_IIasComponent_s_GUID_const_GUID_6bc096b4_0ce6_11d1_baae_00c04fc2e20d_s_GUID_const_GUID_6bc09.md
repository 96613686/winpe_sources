# ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x180010320`
- end: `0x180010334`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIIasComponent@@$1?_GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B$1?_GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010320`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x180010320  test    rdx, rdx
0x180010323  jnz     short loc_18001032B
0x180010325  mov     eax, 80004003h
0x18001032a  retn
0x18001032b  mov     dword ptr [rdx], 1
0x180010331  xor     eax, eax
0x180010333  retn
```
