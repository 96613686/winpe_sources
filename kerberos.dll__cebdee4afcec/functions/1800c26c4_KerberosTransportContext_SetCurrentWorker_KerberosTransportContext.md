# KerberosTransportContext::SetCurrentWorker(KerberosTransportContext *)

- ea: `0x1800c26c4`
- end: `0x1800c2766`
- name: `?SetCurrentWorker@KerberosTransportContext@@CAXPEAV1@@Z`
- size: `162`
- prototype: `void __fastcall(PVOID lpFlsData)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c1590`
- `0x1800c1914`
- `0x1800c2408`
- `0x1800c8ce0`
- `0x1800d0678`

## callees

- `0x18008b70c`
- `0x1800c15e0`
- `0x1800c26c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c2714`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c2714`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c26f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c26f0`
- `api-ms-win-core-fibers-l1-1-0!FlsAlloc` at `0x1800c2701`
- `api-ms-win-core-fibers-l1-1-0!FlsAlloc` at `0x1800c2701`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x1800c275a`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x1800c275a`
- `api-ms-win-core-fibers-l1-1-1!IsThreadAFiber` at `0x1800c2729`
- `api-ms-win-core-fibers-l1-1-1!IsThreadAFiber` at `0x1800c2729`

## pseudocode

```c

```
