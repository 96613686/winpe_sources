# CTrace::NewSession(HKEY__ *,unsigned __int64 *)

- ea: `0x180020fcc`
- end: `0x18002134a`
- name: `?NewSession@CTrace@@AEAAJPEAUHKEY__@@PEA_K@Z`
- size: `894`
- prototype: `int(CTrace *__hidden this, HKEY, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800984f8`

## callees

- `0x1800063b0`
- `0x180008a50`
- `0x18000fb90`
- `0x18001641c`
- `0x18001f66c`
- `0x180020fcc`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800b83ee`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180021233`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180021233`
- `ADVAPI32!QueryTraceW` at `0x180021099`
- `ADVAPI32!QueryTraceW` at `0x18002124b`
- `ADVAPI32!QueryTraceW` at `0x180021099`
- `ADVAPI32!QueryTraceW` at `0x18002124b`

## string_xrefs

- `0x180020fea`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`

## pseudocode

```c

```
