# LDAP_CONN::IoCompletion(void *,uchar *,ulong,ulong,_OVERLAPPED *,THREAD_STOPWATCH *)

- ea: `0x1803531a8`
- end: `0x180354d5c`
- name: `?IoCompletion@LDAP_CONN@@QEAAXPEAXPEAEKKPEAU_OVERLAPPED@@PEAVTHREAD_STOPWATCH@@@Z`
- size: `7092`
- prototype: `void __usercall(LDAP_CONN *__hidden this@<rcx>, void *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, struct _OVERLAPPED *, struct THREAD_STOPWATCH *)`
- caller_count: `2`
- callee_count: `32`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803300e0`
- `0x18033152c`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18003e358`
- `0x18007cf4c`
- `0x180168600`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1803513b0`
- `0x180351600`
- `0x180351638`
- `0x180351b24`
- `0x180352b54`
- `0x1803531a8`
- `0x180355044`
- `0x180355360`
- `0x180355ef0`
- `0x18035bfa0`
- `0x18035c164`
- `0x18035c2b0`
- `0x18035c544`
- `0x18035c8b0`
- `0x18035cbec`
- `0x18035cc84`
- `0x18035cf20`
- `0x180362e44`
- `0x180364c60`
- `0x180364e58`
- `0x1803651f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035397d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035397d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180353940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180353940`
- `ntdll!RtlReleaseSRWLockShared` at `0x180353520`
- `ntdll!RtlReleaseSRWLockShared` at `0x18035354b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180354234`
- `ntdll!RtlReleaseSRWLockShared` at `0x180473274`
- `ntdll!RtlReleaseSRWLockShared` at `0x180353520`
- `ntdll!RtlReleaseSRWLockShared` at `0x18035354b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180354234`
- `ntdll!RtlReleaseSRWLockShared` at `0x180473274`
- `ntdll!RtlAcquireSRWLockShared` at `0x18035350b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180353e9c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18035350b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180353e9c`

## pseudocode

```c

```
