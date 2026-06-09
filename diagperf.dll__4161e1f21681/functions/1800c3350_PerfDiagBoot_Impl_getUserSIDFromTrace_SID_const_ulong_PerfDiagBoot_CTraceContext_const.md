# PerfDiagBoot::Impl::getUserSIDFromTrace(_SID const * &,ulong,PerfDiagBoot::CTraceContext const &)

- ea: `0x1800c3350`
- end: `0x1800c34b7`
- name: `?getUserSIDFromTrace@Impl@PerfDiagBoot@@YAJAEAPEBU_SID@@KAEBVCTraceContext@2@@Z`
- size: `359`
- prototype: `__int64 __fastcall(PerfDiagBoot::Impl *this, const struct _SID **, __int64, const struct PerfDiagBoot::CTraceContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800279d8`

## callees

- `0x180042948`
- `0x180056c14`
- `0x1800c3350`
- `0x1800d6010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c346d`
- `msvcrt!_wcsicmp` at `0x1800c346d`

## pseudocode

```c

```
