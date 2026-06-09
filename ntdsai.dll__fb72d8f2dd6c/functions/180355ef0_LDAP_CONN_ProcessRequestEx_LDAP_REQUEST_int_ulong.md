# LDAP_CONN::ProcessRequestEx(LDAP_REQUEST *,int *,ulong)

- ea: `0x180355ef0`
- end: `0x18035a7f4`
- name: `?ProcessRequestEx@LDAP_CONN@@AEAAXPEAVLDAP_REQUEST@@PEAHK@Z`
- size: `18692`
- prototype: `void __fastcall(LDAP_CONN *__hidden this, struct LDAP_REQUEST *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `76`
- tags: `loader_planting`

## callers

- `0x1803531a8`
- `0x180355ef0`

## callees

- `0x180006880`
- `0x18000b0b0`
- `0x18000baf0`
- `0x18000bb20`
- `0x18000ed84`
- `0x180010510`
- `0x18001ea60`
- `0x18002a0bc`
- `0x180036e3c`
- `0x18003e358`
- `0x18007cf4c`
- `0x18010e330`
- `0x18011a43c`
- `0x180166f10`
- `0x180168600`
- `0x180168aa4`
- `0x180169070`
- `0x18016ae88`
- `0x1801feafc`
- `0x18031f2a4`
- `0x18031f320`
- `0x1803218fc`
- `0x1803243f0`
- `0x1803248f8`
- `0x180324e10`
- `0x180324e3c`
- `0x180325988`
- `0x1803260bc`
- `0x180328870`
- `0x180350b3c`
- `0x1803513b0`
- `0x180351638`
- `0x180351b24`
- `0x1803523ac`
- `0x180352b98`
- `0x180354d64`
- `0x180354d98`
- `0x1803550bc`
- `0x18035522c`
- `0x180355360`
- `0x180355448`
- `0x180355650`
- `0x1803558e8`
- `0x180355ef0`
- `0x18035bd00`
- `0x18035bfa0`
- `0x18035c164`
- `0x18035c2b0`
- `0x18035c414`
- `0x18035c5dc`

## import_xrefs

- `NTDSATQ!AtqQosClassGetInstance` at `0x18035652f`
- `NTDSATQ!AtqQosClassGetInstance` at `0x18035652f`
- `NTDSATQ!AtqContextGetInfo` at `0x180356521`
- `NTDSATQ!AtqContextGetInfo` at `0x180356521`
- `NTDSATQ!AtqGetInfo` at `0x1803566b7`
- `NTDSATQ!AtqGetInfo` at `0x1803566b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803592af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803592af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180357098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180357b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180358340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18035a300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18035a688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180357098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180357b55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180358340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18035a300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18035a688`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180358916`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180358d03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803591de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803595e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803596da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18035a7e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180358916`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180358d03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803591de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803595e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803596da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18035a7e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803587f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358910`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358c4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035918c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803598e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035997c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473312`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18047333d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473368`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473393`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804733be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804733e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804734df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803587f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358910`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358c4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180358cb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035918c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803598e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035997c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473312`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18047333d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473368`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473393`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804733be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804733e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180473457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804734df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358879`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803588a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358bc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358c82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180359089`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803598bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180359967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1804734cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358879`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803588a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358bc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180358c82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180359089`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803598bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180359967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1804734cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180359438`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180359438`
- `ntdll!RtlReleaseSRWLockShared` at `0x1803579fb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1804732e7`
- `ntdll!RtlReleaseSRWLockShared` at `0x1803579fb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1804732e7`
- `ntdll!RtlAcquireSRWLockShared` at `0x18035765b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18035765b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180358aa3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180358aa3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18035893e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18035893e`

## pseudocode

```c

```
