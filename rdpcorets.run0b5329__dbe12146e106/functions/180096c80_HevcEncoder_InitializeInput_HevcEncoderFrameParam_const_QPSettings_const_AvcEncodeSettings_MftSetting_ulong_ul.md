# HevcEncoder::InitializeInput(HevcEncoderFrameParam const &,QPSettings const &,AvcEncodeSettings::MftSetting &,ulong,ulong,int,int,int,ComPlainSmartPtr<CMFApi>,ComPlainSmartPtr<ID3D11Texture2D>,IUnknown *)

- ea: `0x180096c80`
- end: `0x18009794f`
- name: `?InitializeInput@HevcEncoder@@UEAAJAEBUHevcEncoderFrameParam@@AEBUQPSettings@@AEAW4MftSetting@AvcEncodeSettings@@KKHHHV?$ComPlainSmartPtr@VCMFApi@@@@V?$ComPlainSmartPtr@UID3D11Texture2D@@@@PEAUIUnknown@@@Z`
- size: `3279`
- prototype: `__int64 __usercall@<rax>(HevcEncoder *this@<rcx>, int, int, int, int, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180002510`
- `0x180002d8c`
- `0x180009628`
- `0x18000ee00`
- `0x180013bf0`
- `0x18002e600`
- `0x180033964`
- `0x1800348d4`
- `0x180034970`
- `0x1800598d0`
- `0x180084ba0`
- `0x180094fb8`
- `0x180096c80`
- `0x180097960`
- `0x180097b9c`
- `0x1800dc100`
- `0x1800e0fc0`
- `0x1800e3c50`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180096e40`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180096f06`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009701e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800972ae`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097342`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097388`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800974fc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097572`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097742`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800977b9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097801`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009784a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097885`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800978c0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180096e40`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180096f06`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009701e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800972ae`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097342`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097388`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800974fc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097572`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097742`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800977b9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097801`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009784a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180097885`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800978c0`
- `OLEAUT32!__imp_VariantInit` at `0x180096cc7`
- `OLEAUT32!__imp_VariantInit` at `0x180096cc7`
- `OLEAUT32!__imp_VariantClear` at `0x1800978e6`
- `OLEAUT32!__imp_VariantClear` at `0x1800978e6`

## string_xrefs

- `0x1800972b9`: `create and initialize hardware encoder failed, and it is required`
- `0x1800978cb`: `No QP settings given to HEVC codec, or QP outside of HEVC spec range given.`

## pseudocode

```c

```
