# PerfDiagSecondaryLogons::CTraceContext::GetUserSIDFromTrace(_SID const * &,ulong)

- ea: `0x1800c676c`
- end: `0x1800c68d0`
- name: `?GetUserSIDFromTrace@CTraceContext@PerfDiagSecondaryLogons@@QEAAJAEAPEBU_SID@@K@Z`
- size: `356`
- prototype: `__int64 __fastcall(PerfDiagSecondaryLogons::CTraceContext *__hidden this, const struct _SID **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180031aec`

## callees

- `0x180042948`
- `0x180056c14`
- `0x1800c676c`
- `0x1800d6010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c6886`
- `msvcrt!_wcsicmp` at `0x1800c6886`

## pseudocode

```c

```
