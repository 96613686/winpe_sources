# ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180007080`
- end: `0x18000708c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004328`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180007080  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180007087  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)
```
