# ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x180002000`
- end: `0x180002014`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002000`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
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
0x180002000  test    rdx, rdx
0x180002003  jnz     short loc_18000200B
0x180002005  mov     eax, 80070057h
0x18000200a  retn
0x18000200b  mov     dword ptr [rdx], 1
0x180002011  xor     eax, eax
0x180002013  retn
```
