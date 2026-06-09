# RdpNamedPipeHandler::OnNamedPipeMessageReceived(ushort,unsigned __int64,void const *)

- ea: `0x1400135b0`
- end: `0x140013959`
- name: `?OnNamedPipeMessageReceived@RdpNamedPipeHandler@@UEAAXG_KPEBX@Z`
- size: `937`
- prototype: `void __fastcall(RdpNamedPipeHandler **this, unsigned __int16, rsize_t, const void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x1400028b4`
- `0x1400028f4`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x1400081d0`
- `0x14000cae0`
- `0x14000d350`
- `0x14000efb8`
- `0x1400110fc`
- `0x140011eb4`
- `0x1400135b0`
- `0x14006b010`

## import_xrefs

- `msvcrt!_errno` at `0x140013804`
- `msvcrt!_errno` at `0x140013804`
- `msvcrt!memcpy_s` at `0x1400137d6`
- `msvcrt!memcpy_s` at `0x1400137d6`

## string_xrefs

- `0x1400138b9`: `IWTSVirtualChannel::Write failed`

## pseudocode

```c

```
