# CUMRDPConnection::GetDiagnosticsCodeForAuthorizationFailure(RdpServerConnectionDiagnosticCode &)

- ea: `0x18004833c`
- end: `0x180048418`
- name: `?GetDiagnosticsCodeForAuthorizationFailure@CUMRDPConnection@@IEBAXAEAW4RdpServerConnectionDiagnosticCode@@@Z`
- size: `220`
- prototype: `void __fastcall(CUMRDPConnection *__hidden this, enum RdpServerConnectionDiagnosticCode *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004c178`

## callees

- `0x18004833c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800483e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800483e4`
- `OLEAUT32!__imp_VariantInit` at `0x180048365`
- `OLEAUT32!__imp_VariantInit` at `0x18004837c`
- `OLEAUT32!__imp_VariantInit` at `0x180048365`
- `OLEAUT32!__imp_VariantInit` at `0x18004837c`
- `OLEAUT32!__imp_VariantClear` at `0x1800483f8`
- `OLEAUT32!__imp_VariantClear` at `0x180048402`
- `OLEAUT32!__imp_VariantClear` at `0x1800483f8`
- `OLEAUT32!__imp_VariantClear` at `0x180048402`

## string_xrefs

- `0x18004838d`: `ExpectedUserSid`
- `0x1800483b1`: `ActualUserSid`

## pseudocode

```c

```
