# CUMRDPConnection::PrepareForAccept(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x1800506b0`
- end: `0x180050a58`
- name: `?PrepareForAccept@CUMRDPConnection@@UEAAJPEAEK0K0K@Z`
- size: `936`
- prototype: `__int64 __fastcall(CUMRDPConnection *this, unsigned __int8 *, int, const CHAR *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x180012200`
- `0x1800172d0`
- `0x180033da0`
- `0x180046c88`
- `0x1800506b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005070d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050a1f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005070d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180050a1f`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180050724`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005073b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180050724`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005073b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180050959`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180050959`

## string_xrefs

- `0x1800508de`: `CUMRDPSecurityStreamCallback::CreateInstance failed`
- `0x18005098c`: `Failed to allocate Monitor Config`

## pseudocode

```c

```
