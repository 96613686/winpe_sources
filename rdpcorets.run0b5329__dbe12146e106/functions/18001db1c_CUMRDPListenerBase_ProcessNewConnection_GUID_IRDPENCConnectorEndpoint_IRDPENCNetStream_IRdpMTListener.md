# CUMRDPListenerBase::ProcessNewConnection(_GUID,IRDPENCConnectorEndpoint *,IRDPENCNetStream *,IRdpMTListener *)

- ea: `0x18001db1c`
- end: `0x18001e16c`
- name: `?ProcessNewConnection@CUMRDPListenerBase@@IEAAJU_GUID@@PEAUIRDPENCConnectorEndpoint@@PEAUIRDPENCNetStream@@PEAUIRdpMTListener@@@Z`
- size: `1616`
- prototype: `__int64 __fastcall(CUMRDPListenerBase *this, struct _GUID *, struct IRDPENCConnectorEndpoint *, struct IRDPENCNetStream *, struct IRdpMTListener *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x18001d6e0`
- `0x18003f970`
- `0x180064830`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x18001047c`
- `0x180010908`
- `0x180012200`
- `0x180017db4`
- `0x18001bec8`
- `0x18001c164`
- `0x18001db1c`
- `0x180033da0`
- `0x180034970`
- `0x18014c31c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e12f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001e12f`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001db7d`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001e01a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001db7d`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001e01a`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18001dbbf`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18001dbbf`
- `WS2_32!__imp_closesocket` at `0x18001dfe9`
- `WS2_32!__imp_closesocket` at `0x18001dfe9`

## string_xrefs

- `0x18001ddc9`: `UserConfiguredTransportMode`
- `0x18001dea2`: `Failed to create the UMRDP connection object`

## pseudocode

```c

```
