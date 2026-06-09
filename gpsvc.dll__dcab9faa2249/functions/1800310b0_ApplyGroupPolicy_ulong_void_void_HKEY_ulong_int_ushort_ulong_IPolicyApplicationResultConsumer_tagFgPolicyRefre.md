# ApplyGroupPolicy(ulong,void *,void *,HKEY__ *,ulong (*)(int,ushort *),ulong *,IPolicyApplicationResultConsumer *,_tagFgPolicyRefreshReason)

- ea: `0x1800310b0`
- end: `0x180033136`
- name: `?ApplyGroupPolicy@@YAPEAXKPEAX0PEAUHKEY__@@P6AKHPEAG@ZPEAKPEAVIPolicyApplicationResultConsumer@@W4_tagFgPolicyRefreshReason@@@Z`
- size: `8326`
- prototype: `_QWORD *__fastcall(unsigned int, void *, void *, void *, unsigned int (*)(int, unsigned __int16 *), _DWORD *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031050`

## callees

- `0x180006af0`
- `0x18000a504`
- `0x18001ae60`
- `0x180030944`
- `0x180030a10`
- `0x180030bcc`
- `0x180030ec0`
- `0x1800310b0`
- `0x180033140`
- `0x180037470`
- `0x180056278`
- `0x18005ce5c`
- `0x1800672b0`
- `0x180067560`
- `0x180067748`
- `0x18006f470`
- `0x180072a08`
- `0x180073984`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d770`
- `0x18009445c`
- `0x1800b5e10`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003141a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031908`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031a9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003141a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031908`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031a9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003179c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800317c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031f0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003179c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800317c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031f0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031435`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031ab2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031435`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031ab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003139b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031994`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031b13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003139b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031994`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003114c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003226d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003260b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003263c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003289b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003296b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003114c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800312be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003226d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003260b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003263c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003289b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003296b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003147c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003147c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800318ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800318ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800312af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800312af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031296`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031296`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800318fb`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800318fb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180032ed7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180032ed7`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180032186`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800322f2`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800323a7`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180032186`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800322f2`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800323a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800325e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003307d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003308c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800325e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003307d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003308c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800314ac`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003153d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031ff2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800314ac`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003153d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031ff2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031129`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800312f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031445`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031733`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003186a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031886`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031129`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800312f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031445`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031733`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003186a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031886`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180031a25`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180031a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003178c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003198b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031a5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032292`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033016`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003310f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031392`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003178c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003198b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800319ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031a5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b0a`

## string_xrefs

- `0x180031caa`: `AddAdministrators: Failed to initialize sid.  Error = %d`
- `0x1800320c0`: `AddSid: Not initialised or failure.`
- `0x1800320e0`: `AddSid: Not a vaild Sid.`
- `0x1800320f2`: `AddSid: Couldn't allocate memory. Error %d`
- `0x1800315f1`: `AddLocalSystem: Failed to initialize sid.  Error = %d`
- `0x1800325a1`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x1800325d4`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x180032614`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x180032642`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x1800328ec`: `ApplyGroupPolicy: Failed to open current process handle with error (%d).`
- `0x18003291c`: `ApplyGroupPolicy: Failed to open current process handle with error (%d).`
- `0x18003292b`: `ApplyGroupPolicy: Failed to open duplicate token handle with error (%d).`
- `0x18003294a`: `ApplyGroupPolicy: Failed to open duplicate token handle with error (%d).`
- `0x180031fbf`: `ApplyGroupPolicy: Failed to open duplicate event handle with error (%d).`
- `0x180032a64`: `ApplyGroupPolicy: Failed to open duplicate event handle with error (%d).`
- `0x180032031`: `ApplyGroupPolicy: Failed to open duplicate key handle with error (%d).`
- `0x180032aa4`: `ApplyGroupPolicy: Failed to open duplicate key handle with error (%d).`
- `0x180032b41`: `ApplyGroupPolicy: Failed to find user Sid %d`
- `0x180032b74`: `ApplyGroupPolicy: Failed to find user Sid %d`
- `0x180032f2e`: `ApplyGroupPolicy: Failed to create trigger event with %d`
- `0x180032f6c`: `ApplyGroupPolicy: Failed to create trigger event with %d`
- `0x180032c14`: `ApplyGroupPolicy: Failed to create force trigger event with %d`
- `0x180032c47`: `ApplyGroupPolicy: Failed to create force trigger event with %d`
- `0x180031f42`: `ApplyGroupPolicy: Failed to create RR trigger event with %d but continuing...`
- `0x180032cae`: `ApplyGroupPolicy: Failed to create RR trigger event with %d but continuing...`
- `0x180032cc9`: `ApplyGroupPolicy: Setting up GP_BACKGROUND_THREAD`
- `0x180032cfe`: `ApplyGroupPolicy: Setting up GP_BACKGROUND_THREAD`
- `0x180032da7`: `ApplyGroupPolicy: Failed to LocalAlloc GPOTHREADINFO.`
- `0x180032dd9`: `ApplyGroupPolicy: Failed to LocalAlloc GPOTHREADINFO.`
- `0x180032e00`: `ApplyGroupPolicy: Getting ready to create background thread GPOThread.`
- `0x180032e32`: `ApplyGroupPolicy: Getting ready to create background thread GPOThread.`
- `0x180032e76`: `ApplyGroupPolicy: Failed to create background thread (%d).`
- `0x180032eb4`: `ApplyGroupPolicy: Failed to create background thread (%d).`
- `0x1800324da`: `Failed to create a unique activity id with error 0x%x`
- `0x180032512`: `Failed to create a unique activity id with error 0x%x`
- `0x180031c88`: `Failed to impersonate the user with 0x%x`
- `0x180032681`: `Failed to impersonate the user with 0x%x`
- `0x180032bc4`: `AddSid: Couldn't copy Sid. Error %d`

## pseudocode

```c
_QWORD *__fastcall ApplyGroupPolicy(
        unsigned int a1,
        void *a2,
        void *a3,
        void *a4,
        unsigned int (*a5)(int, unsigned __int16 *),
        _DWORD *a6,
        __int64 a7,
        unsigned int a8)
{
  unsigned int v9; // r14d
  char *v10; // rsi
  DWORD LastError; // edi
  HRESULT v12; // eax
  int v13; // ebx
  __int64 v14; // rcx
  BOOL v15; // r15d
  int v16; // r12d
  int v17; // r13d
  unsigned int v18; // eax
  unsigned int v19; // eax
  UUID *v20; // rdx
  DWORD v21; // r15d
  int v22; // r12d
  HANDLE CurrentThread; // rax
  DWORD v24; // eax
  WCHAR *v25; // rbx
  HLOCAL v26; // rcx
  unsigned int v27; // eax
  _DWORD *v28; // rbx
  _QWORD *v29; // r12
  HLOCAL v30; // r13
  char *v31; // rax
  char *v32; // r15
  HANDLE CurrentProcess; // rax
  void *v34; // r13
  _QWORD *v35; // rbx
  unsigned __int64 v36; // rax
  int v37; // r13d
  unsigned int (__fastcall *v38)(int, unsigned __int16 *); // rax
  DWORD v39; // eax
  PSID v40; // rcx
  DWORD v41; // ebx
  PSID v42; // rdx
  __int64 v43; // rcx
  PSID v44; // rcx
  void *UserSid; // rax
  void *v46; // rbx
  HLOCAL v47; // rax
  HLOCAL v48; // r13
  DWORD v49; // edx
  __int64 v50; // rcx
  unsigned int v51; // r13d
  HANDLE EventW; // rax
  HANDLE v53; // rax
  void (*v54)(unsigned int, const unsigned __int16 *, ...); // rbx
  int v55; // eax
  char v56; // cl
  int v57; // r13d
  int v58; // ecx
  _QWORD *v59; // rax
  void *v60; // rbx
  HANDLE v61; // rax
  void *v62; // rbx
  WCHAR *v64; // rax
  DWORD v65; // ebx
  PSID v66; // rdx
  __int64 v67; // rcx
  __int64 k; // rbx
  char *v69; // rax
  void *v70; // rcx
  void (*v71)(unsigned int, const unsigned __int16 *, ...); // r15
  DWORD v72; // eax
  DWORD v73; // eax
  unsigned int i; // ebx
  char *v75; // rax
  void *v76; // rcx
  int v77; // eax
  HANDLE v78; // rax
  DWORD v79; // eax
  void (*v80)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v81; // eax
  void (*v82)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v83; // eax
  DWORD v84; // eax
  unsigned int v85; // r13d
  int *v86; // r8
  void (*v87)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v88; // eax
  unsigned int j; // r13d
  unsigned int v90; // r13d
  int *v91; // r8
  unsigned int v92; // r13d
  int *v93; // r8
  void (*v94)(unsigned int, const unsigned __int16 *, ...); // r15
  DWORD v95; // eax
  DWORD v96; // eax
  DWORD v97; // eax
  void (*v98)(unsigned int, const unsigned __int16 *, ...); // r15
  int v99; // ebx
  DWORD TickCount; // eax
  int v101; // ebx
  DWORD v102; // eax
  void (*v103)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v104; // eax
  DWORD v105; // eax
  void (*v106)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v107; // eax
  DWORD v108; // eax
  DWORD v109; // eax
  DWORD v110; // eax
  void (*v111)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v112; // eax
  DWORD v113; // eax
  DWORD v114; // eax
  void (*v115)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v116; // eax
  DWORD v117; // eax
  DWORD v118; // eax
  void (*v119)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v120; // eax
  DWORD v121; // eax
  DWORD v122; // eax
  void (*v123)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v124; // eax
  DWORD v125; // eax
  void (*v126)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v127; // eax
  DWORD v128; // eax
  void (*v129)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v130; // eax
  DWORD v131; // eax
  HLOCAL *v132; // r13
  __int64 v133; // rax
  unsigned int v134; // edx
  void *v135; // rcx
  void *v136; // rcx
  HKEY v137; // rcx
  void *v138; // rcx
  void *v139; // rcx
  const WCHAR *v140; // rcx
  void *v141; // rcx
  void *v142; // rcx
  CGPPolicyEventReporting *v143; // rcx
  int v144; // eax
  PDWORD pdwReturnedProductType; // [rsp+20h] [rbp-E0h]
  PDWORD pdwReturnedProductTypea; // [rsp+20h] [rbp-E0h]
  __int64 bInheritHandle; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  int v149; // [rsp+64h] [rbp-9Ch]
  ULONG nSize[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v151; // [rsp+70h] [rbp-90h]
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v153; // [rsp+80h] [rbp-80h]
  HANDLE v154; // [rsp+88h] [rbp-78h] BYREF
  char *v155; // [rsp+90h] [rbp-70h] BYREF
  DWORD v156; // [rsp+98h] [rbp-68h]
  __int64 v157; // [rsp+9Ch] [rbp-64h]
  int v158; // [rsp+A4h] [rbp-5Ch]
  HLOCAL v159[2]; // [rsp+A8h] [rbp-58h]
  int v160; // [rsp+B8h] [rbp-48h]
  HANDLE hToken; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v162; // [rsp+C8h] [rbp-38h]
  DWORD v163; // [rsp+D0h] [rbp-30h] BYREF
  DWORD ThreadId; // [rsp+D4h] [rbp-2Ch] BYREF
  HANDLE hSourceHandle; // [rsp+D8h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority[2]; // [rsp+E0h] [rbp-20h] BYREF
  void **v167; // [rsp+F0h] [rbp-10h] BYREF
  HLOCAL v168; // [rsp+F8h] [rbp-8h]
  __int64 v169; // [rsp+100h] [rbp+0h]
  __int64 v170; // [rsp+108h] [rbp+8h]
  __int64 v171; // [rsp+110h] [rbp+10h]
  __int64 v172; // [rsp+118h] [rbp+18h]
  BOOL v173; // [rsp+120h] [rbp+20h]
  HLOCAL v174; // [rsp+128h] [rbp+28h]
  UUID Uuid; // [rsp+134h] [rbp+34h] BYREF
  unsigned __int64 v176; // [rsp+144h] [rbp+44h]
  unsigned __int64 v177; // [rsp+14Ch] [rbp+4Ch]
  unsigned __int64 v178; // [rsp+154h] [rbp+54h]
  __int64 v179; // [rsp+15Ch] [rbp+5Ch]
  void **v180; // [rsp+170h] [rbp+70h] BYREF
  HLOCAL hMem; // [rsp+178h] [rbp+78h]
  __int64 v182; // [rsp+180h] [rbp+80h]
  __int64 *v183; // [rsp+188h] [rbp+88h]
  __int64 v184; // [rsp+190h] [rbp+90h]
  const char *v185; // [rsp+198h] [rbp+98h]
  int v186; // [rsp+1A4h] [rbp+A4h]
  int v187; // [rsp+1A8h] [rbp+A8h]
  int v188; // [rsp+1C8h] [rbp+C8h]
  __int64 v189; // [rsp+1E8h] [rbp+E8h]

  v154 = a4;
  hSourceHandle = a3;
  hToken = a2;
  v151 = a1;
  v162 = a6;
  ThreadId = 0;
  cbData = 0;
  v156 = 0;
  v9 = 0;
  v157 = 0;
  v158 = 0;
  *(_OWORD *)v159 = 0;
  v10 = (char *)LocalAlloc(0x40u, 0xF0u);
  v155 = v10;
  if ( v10 )
  {
    v9 = 10;
    v157 = 0x10000000ALL;
  }
  LastError = GetLastError();
  v149 = LastError;
  InitDebugSupport(0);
  v12 = CoInitializeEx(0, 0);
  if ( v12 < 0 )
  {
    v160 = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ApplyGroupPolicy: CoInitializeEx failed with 0x%x.", (unsigned int)v12);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: CoInitializeEx failed with 0x%x.", (unsigned int)v12);
      }
    }
  }
  else
  {
    v160 = 1;
  }
  v13 = a1 & 1;
  v14 = 40LL * !(a1 & 1);
  v168 = 0;
  v169 = 0;
  v170 = *(__int64 *)((char *)&off_1801280F0 + v14);
  v171 = 0;
  v172 = *(__int64 *)((char *)&off_180128100 + v14);
  v167 = &CGPPolicyApplicationScenarioEvent::`vftable';
  v173 = !(a1 & 1);
  v174 = 0;
  v176 = 0;
  v177 = 0;
  v178 = 0;
  v179 = 0;
  Uuid = 0;
  v15 = (a1 & 0x200000) != 0;
  v16 = a1 & 8;
  if ( (a1 & 0x200000) != 0 )
    v16 = 0;
  v17 = (a1 >> 2) & 1;
  v18 = UuidCreate(&Uuid);
  if ( v18 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"Failed to create a unique activity id with error 0x%x", v18);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"Failed to create a unique activity id with error 0x%x", v18);
    }
  }
  v19 = EtwEventActivityIdControl(2, &Uuid);
  if ( v19 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to set the activity id with error 0x%x", v19);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to set the activity id with error 0x%x", v19);
      }
    }
  }
  else
  {
    v20 = (UUID *)*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v20[1] = Uuid;
    v20->Data4[0] = 1;
  }
  v176 = __PAIR64__(v17, v13);
  v177 = __PAIR64__(v16, v15);
  v178 = __PAIR64__(a8, v15);
  v21 = 0;
  TokenHandle = 0;
  v22 = 0;
  if ( v13 )
    goto LABEL_15;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    TokenHandle = 0;
    v24 = GetLastError();
    if ( v24 != 1008 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", v24);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", v24);
        }
      }
      goto LABEL_141;
    }
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v94 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v95 = GetLastError();
        v94(4u, L"ImpersonateUser: Failed to impersonate user with %d.", v95);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v96 = GetLastError();
        RedirectDebugMsg(4u, L"ImpersonateUser: Failed to impersonate user with %d.", v96);
      }
    }
LABEL_141:
    v25 = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v71 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v72 = GetLastError();
        v71(2u, L"Failed to impersonate the user with 0x%x", v72);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v97 = GetLastError();
        RedirectDebugMsg(2u, L"Failed to impersonate the user with 0x%x", v97);
      }
    }
    goto LABEL_22;
  }
  v22 = 1;
LABEL_15:
  nSize[0] = 75;
  v25 = (WCHAR *)LocalAlloc(0x40u, 0x96u);
  if ( !v25 )
  {
    v21 = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", v21);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", v21);
      }
    }
    goto LABEL_20;
  }
  *(_DWORD *)pIdentifierAuthority[0].Value = 0;
  while ( 1 )
  {
    hMem = 0;
    v182 = 0;
    v183 = API_CALL_TRACING_END_SUCCESS;
    v184 = 0;
    v185 = "i\x1B";
    v180 = &CAPICallScenarioEvent::`vftable';
    v186 = 0;
    v187 = 4117;
    v188 = 4118;
    v189 = 0;
    if ( GetUserNameExW(NameSamCompatible, v25, nSize) )
    {
      v26 = hMem;
      if ( !hMem )
        goto LABEL_20;
      goto LABEL_19;
    }
    v21 = GetLastError();
    if ( nSize[0] )
    {
      if ( v21 == 122 || v21 == 234 )
        break;
    }
    switch ( v21 )
    {
      case 0x534u:
        goto LABEL_203;
      case 0x4CFu:
        goto LABEL_203;
      case 0x54Bu:
        goto LABEL_203;
    }
    if ( ++*(_DWORD *)pIdentifierAuthority[0].Value > 3u )
      goto LABEL_203;
    Sleep(0x1F4u);
LABEL_102:
    v21 = 0;
    if ( hMem )
      LocalFree(hMem);
  }
  v64 = (WCHAR *)LocalReAlloc(v25, 2LL * nSize[0], 2u);
  if ( v64 )
  {
    v25 = v64;
    goto LABEL_102;
  }
  v21 = GetLastError();
LABEL_203:
  LocalFree(v25);
  v25 = 0;
  v26 = hMem;
  if ( hMem )
LABEL_19:
    LocalFree(v26);
LABEL_20:
  SetLastError(v21);
  if ( v22 )
    RevertToUser(&TokenHandle);
LABEL_22:
  v174 = v25;
  v27 = v151;
  if ( (v151 & 0x10) == 0 )
  {
    CGPPolicyApplicationScenarioEvent::ReportStartEvent((CGPPolicyApplicationScenarioEvent *)&v167);
    v27 = v151;
  }
  if ( a8 == 1 )
    v151 = v27 | 0x1000000;
  v163 = 0;
  if ( GetProductInfo(0xAu, 0, 0, 0, &v163) && v163 == 119 )
  {
LABEL_106:
    EnterCriticalSection(&g_StatusCallbackCS);
    g_pStatusMessageCallback = 0;
    LeaveCriticalSection(&g_StatusCallbackCS);
    if ( (v151 & 0x10) == 0 )
      CGPPolicyApplicationScenarioEvent::ReportEndEvent((CGPPolicyApplicationScenarioEvent *)&v167, LastError);
    if ( v160 )
      CoUninitialize();
    v167 = &CGPPolicyApplicationScenarioEvent::`vftable';
    if ( v174 )
      LocalFree(v174);
    *(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) = 0;
    if ( v168 )
      LocalFree(v168);
    SetLastError(LastError);
    if ( v10 )
    {
      for ( i = 0; i < v9; ++i )
      {
        v75 = &v10[24 * i];
        v76 = *(void **)v75;
        if ( *(_QWORD *)v75 )
        {
          if ( *((_DWORD *)v75 + 3) )
            LocalFree(v76);
          else
            FreeSid(v76);
        }
      }
    }
    if ( v159[1] )
      LocalFree(v159[1]);
    if ( v159[0] )
      LocalFree(v159[0]);
    if ( v10 )
      LocalFree(v10);
    return 0;
  }
  v28 = v162;
  if ( !v162 )
  {
    LastError = 87;
    v149 = 87;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ApplyGroupPolicy: pdwResumeTick was NULL.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: pdwResumeTick was NULL.");
      }
    }
    goto LABEL_106;
  }
  v29 = 0;
  v30 = 0;
  v153 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v98 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v99 = *v162;
      TickCount = GetTickCount();
      LODWORD(pdwReturnedProductType) = v99;
      v98(4u, L"ApplyGroupPolicy: flags=0x%x, Tick=%d., ResumeTick=%d.", v151, TickCount, pdwReturnedProductType);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_29;
      v101 = *v162;
      v102 = GetTickCount();
      LODWORD(pdwReturnedProductType) = v101;
      RedirectDebugMsg(
        4u,
        L"ApplyGroupPolicy: flags=0x%x, Tick=%d., ResumeTick=%d.",
        v151,
        v102,
        pdwReturnedProductType);
    }
    v28 = v162;
  }
LABEL_29:
  EnterCriticalSection(&g_StatusCallbackCS);
  g_pStatusMessageCallback = a5;
  LeaveCriticalSection(&g_StatusCallbackCS);
  v31 = (char *)LocalAlloc(0x40u, 0x140u);
  v32 = v31;
  if ( !v31 )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v103 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v104 = GetLastError();
        v103(2u, L"ApplyGroupPolicy: Failed to alloc lpGPOInfo (%d).", v104);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v105 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to alloc lpGPOInfo (%d).", v105);
      }
    }
    goto LABEL_127;
  }
  *(_DWORD *)v31 = v151;
  *((_QWORD *)v31 + 36) = v28;
  *((_QWORD *)v31 + 29) = 0;
  *((_QWORD *)v31 + 31) = a7;
  CurrentProcess = GetCurrentProcess();
  v34 = CurrentProcess;
  if ( !CurrentProcess )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v106 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v107 = GetLastError();
        v106(2u, L"ApplyGroupPolicy: Failed to open current process handle with error (%d).", v107);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v108 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to open current process handle with error (%d).", v108);
      }
    }
    goto LABEL_292;
  }
  if ( !DuplicateHandle(CurrentProcess, hToken, CurrentProcess, (LPHANDLE)v32 + 1, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v111 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v110 = GetLastError();
        v111(2u, L"ApplyGroupPolicy: Failed to open duplicate token handle with error (%d).", v110);
      }
      else if ( g_lpDebugMsgContextInstance && (char *)g_lpDebugMsgContext != (char *)g_lpDebugMsg )
      {
        v109 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to open duplicate token handle with error (%d).", v109);
      }
    }
LABEL_292:
    v30 = 0;
    goto LABEL_127;
  }
  v35 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)pIdentifierAuthority[0].Value = v35;
  if ( v35 )
  {
    TokenHandle = (void *)*((_QWORD *)v32 + 1);
    v36 = CGPServiceEventReporting::s_pEventProviderHandle;
    v162 = (_DWORD *)CGPServiceEventReporting::s_pEventProviderHandle;
    if ( !CGPServiceEventReporting::s_pEventProviderHandle && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Provider handle is NULL, Will NOT be able to publish events.");
        goto LABEL_304;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Provider handle is NULL, Will NOT be able to publish events.");
LABEL_304:
        v36 = (unsigned __int64)v162;
      }
    }
    *v35 = v36;
    v35[1] = TokenHandle;
    v35[3] = 0;
    *((_DWORD *)v35 + 5) = 0;
  }
  else
  {
    v35 = 0;
  }
  *((_QWORD *)v32 + 34) = v35;
  if ( !v35 )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v87 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v88 = GetLastError();
        v87(2u, L"ApplyGroupPolicy: Failed to alloc CGPPolicyEventReporting (%d).", v88);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v112 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to alloc CGPPolicyEventReporting (%d).", v112);
      }
    }
    goto LABEL_126;
  }
  if ( !DuplicateHandle(v34, hSourceHandle, v34, (LPHANDLE)v32 + 4, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v80 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v81 = GetLastError();
        v80(2u, L"ApplyGroupPolicy: Failed to open duplicate event handle with error (%d).", v81);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v113 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to open duplicate event handle with error (%d).", v113);
      }
    }
LABEL_126:
    v30 = v153;
LABEL_127:
    if ( v32 )
    {
      v132 = (HLOCAL *)(v32 + 232);
      v133 = *((_QWORD *)v32 + 29);
      if ( v133 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v133 + 12), 0xFFFFFFFF) == 1 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                4u,
                L"ApplyGroupPolicy: lpGPOInfo->lpGPInfoHandle->dwExtnCount is %d.",
                *((unsigned int *)*v132 + 3));
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"ApplyGroupPolicy: lpGPOInfo->lpGPInfoHandle->dwExtnCount is %d.",
                *((unsigned int *)*v132 + 3));
            }
          }
          LocalFree(*v132);
          *v132 = 0;
        }
        else
        {
          *((_DWORD *)*v132 + 2) = 0;
        }
      }
      SignalPolicyForegroundProcessingDone(v32, 1);
      v135 = (void *)*((_QWORD *)v32 + 1);
      if ( v135 )
        CloseHandle(v135);
      v136 = (void *)*((_QWORD *)v32 + 4);
      if ( v136 )
        CloseHandle(v136);
      v137 = (HKEY)*((_QWORD *)v32 + 5);
      if ( v137 && v137 != HKEY_LOCAL_MACHINE )
        RegCloseKey(v137);
      v138 = (void *)*((_QWORD *)v32 + 10);
      if ( v138 )
        CloseHandle(v138);
      v139 = (void *)*((_QWORD *)v32 + 11);
      if ( v139 )
        CloseHandle(v139);
      v140 = (const WCHAR *)*((_QWORD *)v32 + 9);
      if ( v140 )
        DeleteSidString(v140);
      v141 = (void *)*((_QWORD *)v32 + 25);
      if ( v141 )
        LocalFree(v141);
      v142 = (void *)*((_QWORD *)v32 + 26);
      if ( v142 )
        LocalFree(v142);
      v143 = (CGPPolicyEventReporting *)*((_QWORD *)v32 + 34);
      if ( v143 )
        CGPPolicyEventReporting::`scalar deleting destructor'(v143, v134);
      if ( (v151 & 0x200000) != 0 )
        v144 = 0;
      else
        v144 = *(_DWORD *)v32 & 8;
      HIDWORD(v177) = v144;
      LocalFree(v32);
      v30 = v153;
    }
    if ( v30 )
      LocalFree(v30);
    if ( v29 )
      LocalFree(v29);
    goto LABEL_106;
  }
  if ( v154 == (HANDLE)-2147483646LL )
  {
    *((_QWORD *)v32 + 5) = -2147483646;
    goto LABEL_39;
  }
  if ( !DuplicateHandle(v34, v154, v34, (LPHANDLE)v32 + 5, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v82 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v83 = GetLastError();
        v82(2u, L"ApplyGroupPolicy: Failed to open duplicate key handle with error (%d).", v83);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v114 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to open duplicate key handle with error (%d).", v114);
      }
    }
    goto LABEL_126;
  }
LABEL_39:
  v37 = v151 & 1;
  v38 = MachinePolicyCallback;
  if ( (v151 & 1) == 0 )
    v38 = UserPolicyCallback;
  *((_QWORD *)v32 + 18) = v38;
  *(_DWORD *)pIdentifierAuthority[0].Value = 0;
  *(_WORD *)&pIdentifierAuthority[0].Value[4] = 1280;
  *(_QWORD *)nSize = 0;
  if ( !HIDWORD(v157) || v158 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddLocalSystem: Not initialised or failure.");
    v40 = *(PSID *)nSize;
    if ( *(_QWORD *)nSize )
      goto LABEL_186;
    goto LABEL_45;
  }
  v158 = 1;
  if ( AllocateAndInitializeSid(pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, (PSID *)nSize) )
  {
    v65 = cbData;
    if ( cbData == v9 )
    {
      if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v155) )
      {
        if ( *(_QWORD *)nSize )
          FreeSid(*(PSID *)nSize);
        v9 = v157;
        v41 = v156;
        cbData = v156;
        v10 = v155;
        goto LABEL_46;
      }
      v9 = v157;
      v65 = v156;
      v10 = v155;
    }
    v66 = *(PSID *)nSize;
    *(_QWORD *)nSize = 0;
    v67 = 3LL * v65;
    *(_QWORD *)&v10[8 * v67] = v66;
    *(_DWORD *)&v10[8 * v67 + 8] = 0x10000000;
    *(_DWORD *)&v10[8 * v67 + 16] = 0;
    v41 = v65 + 1;
    cbData = v41;
    v156 = v41;
    v158 = 0;
    if ( *(_QWORD *)nSize )
      FreeSid(*(PSID *)nSize);
    goto LABEL_46;
  }
  v39 = GetLastError();
  CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddLocalSystem: Failed to initialize sid.  Error = %d", v39);
  v40 = *(PSID *)nSize;
  if ( !*(_QWORD *)nSize )
    goto LABEL_45;
LABEL_186:
  FreeSid(v40);
LABEL_45:
  v41 = cbData;
LABEL_46:
  *(_DWORD *)pIdentifierAuthority[0].Value = 0;
  *(_WORD *)&pIdentifierAuthority[0].Value[4] = 1280;
  *(_QWORD *)nSize = 0;
  if ( !HIDWORD(v157) || v158 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAdministrators: Not initialised or failure.");
    v44 = *(PSID *)nSize;
    if ( !*(_QWORD *)nSize )
      goto LABEL_51;
    goto LABEL_145;
  }
  v158 = 1;
  if ( !AllocateAndInitializeSid(pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)nSize) )
  {
    v73 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAdministrators: Failed to initialize sid.  Error = %d", v73);
    v44 = *(PSID *)nSize;
    if ( !*(_QWORD *)nSize )
      goto LABEL_51;
    goto LABEL_145;
  }
  if ( v41 != v9 )
    goto LABEL_50;
  if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v155) )
  {
    if ( *(_QWORD *)nSize )
      FreeSid(*(PSID *)nSize);
    v9 = v157;
    cbData = v156;
    v10 = v155;
    goto LABEL_51;
  }
  v9 = v157;
  v41 = v156;
  v10 = v155;
LABEL_50:
  v42 = *(PSID *)nSize;
  *(_QWORD *)nSize = 0;
  v43 = 3LL * v41;
  *(_QWORD *)&v10[8 * v43] = v42;
  *(_DWORD *)&v10[8 * v43 + 8] = 0x10000000;
  *(_DWORD *)&v10[8 * v43 + 16] = 0;
  cbData = v41 + 1;
  v156 = v41 + 1;
  v158 = 0;
  v44 = *(PSID *)nSize;
  if ( *(_QWORD *)nSize )
LABEL_145:
    FreeSid(v44);
LABEL_51:
  if ( v37 )
  {
    v51 = 0;
    nSize[0] = 0;
    TokenHandle = 0;
    *(_DWORD *)pIdentifierAuthority[0].Value = 0;
    cbData = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            0,
            0x20019u,
            (PHKEY)&TokenHandle) )
    {
      cbData = 4;
      RegQueryValueExW(
        (HKEY)TokenHandle,
        L"DenyUsersFromMachGP",
        0,
        (LPDWORD)pIdentifierAuthority[0].Value,
        (LPBYTE)nSize,
        &cbData);
      RegCloseKey((HKEY)TokenHandle);
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\System",
            0,
            0x20019u,
            (PHKEY)&TokenHandle) )
    {
      cbData = 4;
      RegQueryValueExW(
        (HKEY)TokenHandle,
        L"DenyUsersFromMachGP",
        0,
        (LPDWORD)pIdentifierAuthority[0].Value,
        (LPBYTE)nSize,
        &cbData);
      RegCloseKey((HKEY)TokenHandle);
    }
    if ( !nSize[0] )
    {
      CSecDesc::AddAuthUsers((CSecDesc *)&v155, 131075);
      v9 = v157;
      v10 = v155;
    }
    goto LABEL_60;
  }
  UserSid = GetUserSid(hToken);
  v46 = UserSid;
  hSourceHandle = UserSid;
  if ( !UserSid )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v115 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v116 = GetLastError();
        v115(2u, L"ApplyGroupPolicy: Failed to find user Sid %d", v116);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v117 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to find user Sid %d", v117);
      }
    }
    *(_DWORD *)pIdentifierAuthority[0].Value = ((*v32 & 8) != 0) + 1;
    for ( j = 0; ; ++j )
    {
      if ( j >= 6 )
      {
        v90 = -1;
        goto LABEL_209;
      }
      v154 = (HANDLE)(16LL * j);
      if ( FindNLSString(
             0x7Fu,
             0x200001u,
             L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp",
             -1,
             *(LPCWSTR *)((char *)&GPSourceFileNameIdTable + (_QWORD)v154),
             -1,
             0) != -1 )
        break;
    }
    v90 = *(int *)((char *)&dword_180128228 + (_QWORD)v154);
LABEL_209:
    LODWORD(bInheritHandle) = 0;
    LODWORD(pdwReturnedProductTypea) = *(_DWORD *)pIdentifierAuthority[0].Value;
    CGPAdminEventInitFailure::CGPAdminEventInitFailure(
      (CGPAdminEventInitFailure *)&v180,
      (__int64)&gpEvent_INTERNAL_SYSTEM_ERROR,
      v90,
      1071,
      (__int64)pdwReturnedProductTypea,
      bInheritHandle,
      LastError);
    CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v32 + 34), (struct CGPEventInfo *)&v180, v91);
    CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)&v180);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&hSourceHandle);
    goto LABEL_126;
  }
  if ( !HIDWORD(v157) || v158 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Not initialised or failure.");
    goto LABEL_188;
  }
  v158 = 1;
  if ( !IsValidSid(UserSid) )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Not a vaild Sid.");
    goto LABEL_188;
  }
  *(_DWORD *)pIdentifierAuthority[0].Value = GetLengthSid(v46);
  v47 = LocalAlloc(0x40u, *(unsigned int *)pIdentifierAuthority[0].Value);
  v48 = v47;
  v154 = v47;
  if ( v47 )
  {
    if ( CopySid(*(DWORD *)pIdentifierAuthority[0].Value, v47, v46) )
    {
      v49 = cbData;
      v50 = 3LL * cbData;
      *(_QWORD *)&v10[8 * v50] = v48;
      *(_DWORD *)&v10[8 * v50 + 8] = 131075;
      *(_QWORD *)&v10[8 * v50 + 12] = 1;
      v51 = 0;
      v156 = v49 + 1;
      v158 = 0;
      goto LABEL_59;
    }
    v118 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Couldn't copy Sid. Error %d", v118);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v154);
LABEL_188:
    v51 = 0;
  }
  else
  {
    v84 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Couldn't allocate memory. Error %d", v84);
    v51 = 0;
  }
LABEL_59:
  LocalFree(v46);
LABEL_60:
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v32 + 10) = EventW;
  if ( !EventW || (*(_WORD *)&CGPServiceEventReporting::s_dwTestFlags & 0x200) != 0 )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v129 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v130 = GetLastError();
        v129(2u, L"ApplyGroupPolicy: Failed to create trigger event with %d", v130);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v131 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to create trigger event with %d", v131);
      }
    }
    *(_DWORD *)pIdentifierAuthority[0].Value = ((*v32 & 8) != 0) + 1;
    while ( 1 )
    {
      if ( v51 >= 6 )
      {
        v85 = -1;
        goto LABEL_197;
      }
      v154 = (HANDLE)(16LL * v51);
      if ( FindNLSString(
             0x7Fu,
             0x200001u,
             L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp",
             -1,
             *(LPCWSTR *)((char *)&GPSourceFileNameIdTable + (_QWORD)v154),
             -1,
             0) != -1 )
        break;
      ++v51;
    }
    v85 = *(int *)((char *)&dword_180128228 + (_QWORD)v154);
LABEL_197:
    CGPEventBase::CGPEventBase((CGPEventBase *)&v180, &gpEvent_INTERNAL_SYSTEM_ERROR, 6u);
    v180 = &CProcessingAdminEvent::`vftable';
    CProcessingAdminEvent::Initialize(&v180, v85, 1142, *(unsigned int *)pIdentifierAuthority[0].Value, 0);
    v180 = &CGPAdminEventInitFailure::`vftable';
    CGPAdminEventInitFailure::Initialize((CGPAdminEventInitFailure *)&v180, LastError, 0);
    CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v32 + 34), (struct CGPEventInfo *)&v180, v86);
    CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)&v180);
    goto LABEL_126;
  }
  v53 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v32 + 11) = v53;
  if ( !v53 )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v119 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v120 = GetLastError();
        v119(2u, L"ApplyGroupPolicy: Failed to create force trigger event with %d", v120);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v121 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to create force trigger event with %d", v121);
      }
    }
    *(_DWORD *)pIdentifierAuthority[0].Value = ((*v32 & 8) != 0) + 1;
    while ( 1 )
    {
      if ( v51 >= 6 )
      {
        v92 = -1;
        goto LABEL_214;
      }
      v154 = (HANDLE)(16LL * v51);
      if ( FindNLSString(
             0x7Fu,
             0x200001u,
             L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpt.cpp",
             -1,
             *(LPCWSTR *)((char *)&GPSourceFileNameIdTable + (_QWORD)v154),
             -1,
             0) != -1 )
        break;
      ++v51;
    }
    v92 = *(int *)((char *)&dword_180128228 + (_QWORD)v154);
LABEL_214:
    LODWORD(bInheritHandle) = 0;
    LODWORD(pdwReturnedProductTypea) = *(_DWORD *)pIdentifierAuthority[0].Value;
    CGPAdminEventInitFailure::CGPAdminEventInitFailure(
      (CGPAdminEventInitFailure *)&v180,
      (__int64)&gpEvent_INTERNAL_SYSTEM_ERROR,
      v92,
      1160,
      (__int64)pdwReturnedProductTypea,
      bInheritHandle,
      LastError);
    CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v32 + 34), (struct CGPEventInfo *)&v180, v93);
    CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)&v180);
    goto LABEL_126;
  }
  *(_DWORD *)pIdentifierAuthority[0].Value = 0;
  if ( !CConnectivityManager::s_pInstance
    || *((_DWORD *)CConnectivityManager::s_pInstance + 9)
    || (v78 = CreateEventW(0, 0, 0, 0), (*((_QWORD *)v32 + 12) = v78) != 0)
    || !*(_DWORD *)&g_dwDebugLevel )
  {
LABEL_65:
    v54 = g_lpDebugMsg;
  }
  else
  {
    v54 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v79 = GetLastError();
      v54(2u, L"ApplyGroupPolicy: Failed to create RR trigger event with %d but continuing...", v79);
      goto LABEL_65;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v122 = GetLastError();
      RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to create RR trigger event with %d but continuing...", v122);
      goto LABEL_65;
    }
  }
  *((_DWORD *)v32 + 60) = 0;
  v55 = *(_DWORD *)v32;
  if ( (*(_DWORD *)v32 & 0x200008) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( v54 )
      {
        v54(2u, L"ApplyGroupPolicy: Setting up GP_BACKGROUND_THREAD");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Setting up GP_BACKGROUND_THREAD");
      }
    }
    *(_DWORD *)v32 |= 0x10000u;
    v55 = *(_DWORD *)v32;
  }
  v56 = v151;
  if ( (v151 & 0x20) != 0 )
    *(_DWORD *)v32 = v55 | 0x400000;
  v57 = v56 & 0x10;
  if ( (v56 & 0x10) == 0 && !(unsigned int)ProcessGPOs((struct _GPOINFO *)v32) )
  {
    *(_DWORD *)pIdentifierAuthority[0].Value = GetLastError();
    LODWORD(v179) = *((_DWORD *)v32 + 61);
  }
  v58 = *(_DWORD *)v32;
  if ( (*(_DWORD *)v32 & 8) != 0 )
  {
    v58 &= 0xFFFEFFF7;
    *(_DWORD *)v32 = v58;
  }
  if ( (v58 & 0x200000) != 0 )
    *(_DWORD *)v32 = v58 & 0xFFDEFFFF;
  nSize[0] = *((_DWORD *)v32 + 61);
  v29 = LocalAlloc(0x40u, 0x18u);
  if ( !v29 )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v123 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v124 = GetLastError();
        v123(2u, L"ApplyGroupPolicy: Failed to alloc pPolicyInfo (%d).", v124);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v125 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to alloc pPolicyInfo (%d).", v125);
      }
    }
    goto LABEL_126;
  }
  v59 = LocalAlloc(0x40u, 0x10u);
  v60 = v59;
  v153 = v59;
  if ( !v59 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ApplyGroupPolicy: Failed to LocalAlloc GPOTHREADINFO.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to LocalAlloc GPOTHREADINFO.");
      }
    }
    goto LABEL_126;
  }
  *v59 = v32;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ApplyGroupPolicy: Getting ready to create background thread GPOThread.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ApplyGroupPolicy: Getting ready to create background thread GPOThread.");
    }
  }
  v61 = CreateThread(0, 0x10000u, GPOThread, v60, 4u, &ThreadId);
  v62 = v61;
  if ( !v61 )
  {
    LastError = GetLastError();
    v149 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v126 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v127 = GetLastError();
        v126(2u, L"ApplyGroupPolicy: Failed to create background thread (%d).", v127);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v128 = GetLastError();
        RedirectDebugMsg(2u, L"ApplyGroupPolicy: Failed to create background thread (%d).", v128);
      }
    }
    goto LABEL_126;
  }
  if ( (*(_DWORD *)v32 & 0x10000) != 0 )
    SetThreadPriority(v61, -15);
  *((_QWORD *)v32 + 18) = 0;
  ResumeThread(v62);
  EnterCriticalSection(&g_StatusCallbackCS);
  g_pStatusMessageCallback = 0;
  LeaveCriticalSection(&g_StatusCallbackCS);
  if ( v57 )
  {
    *v29 = v32;
    v29[1] = v62;
    *((_DWORD *)v29 + 4) = nSize[0];
  }
  else
  {
    if ( (v151 & 0x200000) != 0 )
      v77 = 0;
    else
      v77 = *(_DWORD *)v32 & 8;
    HIDWORD(v177) = v77;
    ((void (__fastcall *)(void ***, _QWORD, _QWORD))v167[1])(
      &v167,
      *(_DWORD *)pIdentifierAuthority[0].Value != 0 ? 2 : 0,
      *(unsigned int *)pIdentifierAuthority[0].Value);
    *v29 = v32;
    v29[1] = v62;
    *((_DWORD *)v29 + 4) = nSize[0];
    hToken = 0;
    *(_DWORD *)pIdentifierAuthority[0].Value = 0;
    if ( !RegOpenKeyExW(
            *((HKEY *)v32 + 5),
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\PolicyApplicationState",
            0,
            0x2001Bu,
            (PHKEY)&hToken) )
    {
      *(_DWORD *)pIdentifierAuthority[0].Value = 2;
      RegSetValueExW((HKEY)hToken, L"PolicyState", 0, 4u, pIdentifierAuthority[0].Value, 4u);
    }
    if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
      && (unsigned __int64)hToken + 0x80000000 > 6
      && hToken != (HANDLE)-2147483568LL
      && hToken != (HANDLE)-2147483552LL )
    {
      RegCloseKey((HKEY)hToken);
    }
  }
  if ( v160 )
    CoUninitialize();
  v167 = &CGPPolicyApplicationScenarioEvent::`vftable';
  if ( v174 )
    LocalFree(v174);
  *(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) = 0;
  if ( v168 )
    LocalFree(v168);
  SetLastError(LastError);
  if ( v10 )
  {
    for ( k = 0; (unsigned int)k < v9; k = (unsigned int)(k + 1) )
    {
      v69 = &v10[24 * k];
      v70 = *(void **)v69;
      if ( *(_QWORD *)v69 )
      {
        if ( *((_DWORD *)v69 + 3) )
          LocalFree(v70);
        else
          FreeSid(v70);
      }
    }
  }
  if ( v159[1] )
    LocalFree(v159[1]);
  if ( v159[0] )
    LocalFree(v159[0]);
  if ( v10 )
    LocalFree(v10);
  return v29;
}

```

## disassembly

```asm
0x1800310b0  push    rbp
0x1800310b2  push    rbx
0x1800310b3  push    rsi
0x1800310b4  push    rdi
0x1800310b5  push    r12
0x1800310b7  push    r13
0x1800310b9  push    r14
0x1800310bb  push    r15
0x1800310bd  lea     rbp, [rsp-108h]
0x1800310c5  sub     rsp, 208h
0x1800310cc  mov     rax, cs:__security_cookie
0x1800310d3  xor     rax, rsp
0x1800310d6  mov     [rbp+140h+var_50], rax
0x1800310dd  mov     [rbp+140h+var_1B8], r9
0x1800310e1  mov     [rbp+140h+hSourceHandle], r8
0x1800310e5  mov     [rbp+140h+hToken], rdx
0x1800310e9  mov     r13d, ecx
0x1800310ec  mov     [rsp+240h+var_1D0], ecx
0x1800310f0  mov     rax, [rbp+140h+arg_28]
0x1800310f7  mov     [rbp+140h+var_178], rax
0x1800310fb  xor     r12d, r12d
0x1800310fe  mov     [rbp+140h+ThreadId], r12d
0x180031102  mov     eax, r12d
0x180031105  mov     [rsp+240h+cbData], eax
0x180031109  mov     [rbp+140h+var_1A8], eax
0x18003110c  mov     r14d, r12d
0x18003110f  mov     [rbp+140h+var_1A4], r12
0x180031113  mov     [rbp+140h+var_19C], r12d
0x180031117  xorps   xmm0, xmm0
0x18003111a  movdqu  xmmword ptr [rbp+140h+var_198], xmm0
0x18003111f  mov     edx, 0F0h; uBytes
0x180031124  mov     ecx, 40h ; '@'; uFlags
0x180031129  call    cs:__imp_LocalAlloc
0x18003112f  mov     rsi, rax
0x180031132  mov     [rbp+140h+var_1B0], rax
0x180031136  test    rax, rax
0x180031139  jz      short loc_18003114C
0x18003113b  mov     r14d, 0Ah
0x180031141  mov     dword ptr [rbp+140h+var_1A4], r14d
0x180031145  mov     dword ptr [rbp+140h+var_1A4+4], 1
0x18003114c  call    cs:__imp_GetLastError
0x180031152  mov     edi, eax
0x180031154  mov     [rsp+240h+var_1DC], eax
0x180031158  xor     ecx, ecx
0x18003115a  call    InitDebugSupport
0x18003115f  xor     edx, edx; dwCoInit
0x180031161  xor     ecx, ecx; pvReserved
0x180031163  call    cs:__imp_CoInitializeEx
0x180031169  test    eax, eax
0x18003116b  js      loc_180032450
0x180031171  mov     [rbp+140h+var_188], 1
0x180031178  mov     ebx, r13d
0x18003117b  and     ebx, 1
0x18003117e  mov     eax, ebx
0x180031180  xor     eax, 1
0x180031183  mov     edx, eax
0x180031185  lea     rax, [rax+rax*4]
0x180031189  lea     rcx, ds:0[rax*8]
0x180031191  mov     [rbp+140h+var_148], r12
0x180031195  mov     [rbp+140h+var_140], r12
0x180031199  lea     r8, __ImageBase
0x1800311a0  mov     rax, [rcx+r8+1280F0h]
0x1800311a8  mov     [rbp+140h+var_138], rax
0x1800311ac  mov     [rbp+140h+var_130], r12
0x1800311b0  mov     rax, [rcx+r8+128100h]
0x1800311b8  mov     [rbp+140h+var_128], rax
0x1800311bc  lea     rax, ??_7CGPPolicyApplicationScenarioEvent@@6B@; const CGPPolicyApplicationScenarioEvent::`vftable'
0x1800311c3  mov     [rbp+140h+var_150], rax
0x1800311c7  mov     [rbp+140h+var_120], edx
0x1800311ca  mov     [rbp+140h+var_118], r12
0x1800311ce  mov     [rbp+140h+var_FC], r12
0x1800311d2  mov     [rbp+140h+var_F4], r12
0x1800311d6  mov     [rbp+140h+var_EC], r12
0x1800311da  mov     [rbp+140h+var_E4], r12
0x1800311de  xorps   xmm0, xmm0
0x1800311e1  movups  xmmword ptr [rbp+140h+Uuid.Data1], xmm0
0x1800311e5  bt      r13d, 15h
0x1800311ea  mov     r15d, r12d
0x1800311ed  setb    r15b
0x1800311f1  mov     eax, r12d
0x1800311f4  mov     r12d, r13d
0x1800311f7  and     r12d, 8
0x1800311fb  bt      r13d, 15h
0x180031200  cmovb   r12d, eax
0x180031204  shr     r13d, 2
0x180031208  and     r13d, 1
0x18003120c  lea     rcx, [rbp+140h+Uuid]; Uuid
0x180031210  call    cs:__imp_UuidCreate
0x180031216  test    eax, eax
0x180031218  jnz     loc_1800324BE
0x18003121e  lea     rdx, [rbp+140h+Uuid]
0x180031222  mov     ecx, 2
0x180031227  call    cs:__imp_EtwEventActivityIdControl
0x18003122d  mov     r8d, 8
0x180031233  mov     ecx, cs:_tls_index
0x180031239  test    eax, eax
0x18003123b  jnz     loc_180032528
0x180031241  mov     rax, gs:58h
0x18003124a  mov     rdx, [rax+rcx*8]
0x18003124e  mov     ecx, 10h
0x180031253  mov     rax, qword ptr [rbp+140h+Uuid.Data1]
0x180031257  mov     [rcx+rdx], rax
0x18003125b  mov     rax, qword ptr [rbp+140h+Uuid.Data4]
0x18003125f  mov     [rcx+rdx+8], rax
0x180031264  mov     byte ptr [r8+rdx], 1
0x180031269  mov     dword ptr [rbp+140h+var_FC], ebx
0x18003126c  mov     dword ptr [rbp+140h+var_FC+4], r13d
0x180031270  mov     dword ptr [rbp+140h+var_F4], r15d
0x180031274  mov     dword ptr [rbp+140h+var_F4+4], r12d
0x180031278  mov     dword ptr [rbp+140h+var_EC], r15d
0x18003127c  mov     r13d, [rbp+140h+arg_38]
0x180031283  mov     dword ptr [rbp+140h+var_EC+4], r13d
0x180031287  xor     r15d, r15d
0x18003128a  mov     [rsp+240h+TokenHandle], r15
0x18003128f  mov     r12d, r15d
0x180031292  test    ebx, ebx
0x180031294  jnz     short loc_1800312E7
0x180031296  call    cs:__imp_GetCurrentThread
0x18003129c  mov     rcx, rax; ThreadHandle
0x18003129f  lea     r9, [rsp+240h+TokenHandle]; TokenHandle
0x1800312a4  mov     edx, 2000Ch; DesiredAccess
0x1800312a9  mov     r8d, 1; OpenAsSelf
0x1800312af  call    cs:__imp_OpenThreadToken
0x1800312b5  test    eax, eax
0x1800312b7  jnz     short loc_1800312CF
0x1800312b9  mov     [rsp+240h+TokenHandle], r15
0x1800312be  call    cs:__imp_GetLastError
0x1800312c4  cmp     eax, 3F0h
0x1800312c9  jnz     loc_180031C52
0x1800312cf  mov     rcx, [rbp+140h+hToken]; hToken
0x1800312d3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800312d9  test    eax, eax
0x1800312db  jz      loc_1800325DD
0x1800312e1  mov     r12d, 1
0x1800312e7  mov     [rsp+240h+nSize], 4Bh ; 'K'
0x1800312ef  mov     edx, 96h; uBytes
0x1800312f4  mov     ecx, 40h ; '@'; uFlags
0x1800312f9  call    cs:__imp_LocalAlloc
0x1800312ff  mov     rbx, rax
0x180031302  test    rax, rax
0x180031305  jz      loc_180031D24
0x18003130b  mov     dword ptr [rbp+140h+pIdentifierAuthority.Value], r15d
0x18003130f  lea     r8, ??_7CAPICallScenarioEvent@@6B@; const CAPICallScenarioEvent::`vftable'
0x180031316  lea     rdx, API_CALL_TRACING_END_FAILURE; "i\x1B"
0x18003131d  lea     rax, API_CALL_TRACING_END_SUCCESS
0x180031324  mov     [rbp+140h+hMem], r15
0x180031328  mov     [rbp+140h+var_C0], 0
0x180031333  mov     [rbp+140h+var_B8], rax
0x18003133a  mov     [rbp+140h+var_B0], r15
0x180031341  mov     [rbp+140h+var_A8], rdx
0x180031348  mov     [rbp+140h+var_D0], r8
0x18003134c  mov     [rbp+140h+var_9C], r15d
0x180031353  mov     [rbp+140h+var_98], 1015h
0x18003135d  mov     [rbp+140h+var_78], 1016h
0x180031367  mov     [rbp+140h+var_58], r15
0x18003136e  lea     r8, [rsp+240h+nSize]; nSize
0x180031373  mov     rdx, rbx; lpNameBuffer
0x180031376  mov     ecx, 2; NameFormat
0x18003137b  call    cs:__imp_GetUserNameExW
0x180031381  test    al, al
0x180031383  jz      loc_1800319F6
0x180031389  mov     rcx, [rbp+140h+hMem]; hMem
0x18003138d  test    rcx, rcx
0x180031390  jz      short loc_180031398
0x180031392  call    cs:__imp_LocalFree
0x180031398  mov     ecx, r15d; dwErrCode
0x18003139b  call    cs:__imp_SetLastError
0x1800313a1  test    r12d, r12d
0x1800313a4  jnz     loc_18003272F
0x1800313aa  xor     r15d, r15d
0x1800313ad  mov     [rbp+140h+var_118], rbx
0x1800313b1  mov     eax, [rsp+240h+var_1D0]
0x1800313b5  test    al, 10h
0x1800313b7  jz      loc_18003273E
0x1800313bd  cmp     r13d, 1
0x1800313c1  jz      loc_180032750
0x1800313c7  mov     [rbp+140h+var_170], r15d
0x1800313cb  lea     rax, [rbp+140h+var_170]
0x1800313cf  mov     [rsp+240h+pdwReturnedProductType], rax; pdwReturnedProductType
0x1800313d4  xor     r9d, r9d; dwSpMinorVersion
0x1800313d7  xor     r8d, r8d; dwSpMajorVersion
0x1800313da  xor     edx, edx; dwOSMinorVersion
0x1800313dc  mov     ecx, 0Ah; dwOSMajorVersion
0x1800313e1  call    cs:__imp_GetProductInfo
0x1800313e7  test    eax, eax
0x1800313e9  jnz     loc_180031A8D
0x1800313ef  mov     rbx, [rbp+140h+var_178]
0x1800313f3  test    rbx, rbx
0x1800313f6  jz      loc_18003275D
0x1800313fc  mov     r12, r15
0x1800313ff  mov     r13, r15
0x180031402  mov     [rbp+140h+var_1C0], r15
0x180031406  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18003140d  jnz     loc_1800327C7
0x180031413  lea     rcx, ?g_StatusCallbackCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003141a  call    cs:__imp_EnterCriticalSection
0x180031420  mov     rax, [rbp+140h+arg_20]
0x180031427  mov     cs:?g_pStatusMessageCallback@@3P6AKHPEAG@ZEA, rax; ulong (*g_pStatusMessageCallback)(int,ushort *)
0x18003142e  lea     rcx, ?g_StatusCallbackCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031435  call    cs:__imp_LeaveCriticalSection
0x18003143b  mov     edx, 140h; uBytes
0x180031440  mov     ecx, 40h ; '@'; uFlags
0x180031445  call    cs:__imp_LocalAlloc
0x18003144b  mov     r15, rax
0x18003144e  test    rax, rax
0x180031451  jz      loc_180032847
0x180031457  mov     eax, [rsp+240h+var_1D0]
0x18003145b  mov     [r15], eax
0x18003145e  mov     [r15+120h], rbx
0x180031465  xor     ebx, ebx
0x180031467  mov     [r15+0E8h], rbx
0x18003146e  mov     rax, [rbp+140h+arg_30]
0x180031475  mov     [r15+0F8h], rax
0x18003147c  call    cs:__imp_GetCurrentProcess
0x180031482  mov     r13, rax
0x180031485  test    rax, rax
0x180031488  jz      loc_1800328BF
0x18003148e  lea     r9, [r15+8]; lpTargetHandle
0x180031492  mov     [rsp+240h+dwOptions], 2; dwOptions
0x18003149a  mov     [rsp+240h+bInheritHandle], ebx; bInheritHandle
0x18003149e  mov     dword ptr [rsp+240h+pdwReturnedProductType], ebx; dwDesiredAccess
0x1800314a2  mov     r8, rax; hTargetProcessHandle
0x1800314a5  mov     rdx, [rbp+140h+hToken]; hSourceHandle
0x1800314a9  mov     rcx, rax; hSourceProcessHandle
0x1800314ac  call    cs:__imp_DuplicateHandle
0x1800314b2  test    eax, eax
0x1800314b4  jz      loc_18003296B
0x1800314ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800314c1  mov     ecx, 20h ; ' '; unsigned __int64
0x1800314c6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800314cb  mov     rbx, rax
0x1800314ce  mov     qword ptr [rbp+140h+pIdentifierAuthority.Value], rax
0x1800314d2  test    rax, rax
0x1800314d5  jz      loc_180031A6A
0x1800314db  mov     rax, [r15+8]
0x1800314df  mov     [rsp+240h+TokenHandle], rax
0x1800314e4  mov     rax, cs:?s_pEventProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pEventProviderHandle
0x1800314eb  mov     [rbp+140h+var_178], rax
0x1800314ef  test    rax, rax
0x1800314f2  jz      loc_18003299F
0x1800314f8  mov     [rbx], rax
0x1800314fb  mov     rax, [rsp+240h+TokenHandle]
0x180031500  mov     [rbx+8], rax
0x180031504  xor     eax, eax
0x180031506  mov     [rbx+18h], rax
0x18003150a  mov     [rbx+14h], eax
0x18003150d  mov     [r15+110h], rbx
0x180031514  test    rbx, rbx
0x180031517  jz      loc_180032244
0x18003151d  lea     r9, [r15+20h]; lpTargetHandle
0x180031521  mov     [rsp+240h+dwOptions], 2; dwOptions
0x180031529  xor     ebx, ebx
0x18003152b  mov     [rsp+240h+bInheritHandle], ebx; bInheritHandle
0x18003152f  mov     dword ptr [rsp+240h+pdwReturnedProductType], ebx; dwDesiredAccess
0x180031533  mov     r8, r13; hTargetProcessHandle
0x180031536  mov     rdx, [rbp+140h+hSourceHandle]; hSourceHandle
0x18003153a  mov     rcx, r13; hSourceProcessHandle
0x18003153d  call    cs:__imp_DuplicateHandle
0x180031543  test    eax, eax
0x180031545  jz      loc_180031F8E
0x18003154b  mov     rdx, [rbp+140h+var_1B8]; hSourceHandle
0x18003154f  cmp     rdx, 0FFFFFFFF80000002h
0x180031556  jnz     loc_180031FD8
0x18003155c  mov     [r15+28h], rdx
0x180031560  mov     r13d, [rsp+240h+var_1D0]
0x180031565  and     r13d, 1
0x180031569  lea     rax, ?MachinePolicyCallback@@YAKHPEAG@Z; MachinePolicyCallback(int,ushort *)
0x180031570  lea     rcx, ?UserPolicyCallback@@YAKHPEAG@Z; UserPolicyCallback(int,ushort *)
0x180031577  cmovz   rax, rcx
0x18003157b  mov     [r15+90h], rax
0x180031582  mov     dword ptr [rbp+140h+pIdentifierAuthority.Value], ebx
0x180031585  mov     word ptr [rbp+140h+pIdentifierAuthority.Value+4], 500h
0x18003158b  mov     qword ptr [rsp+240h+nSize], rbx
0x180031590  cmp     dword ptr [rbp+140h+var_1A4+4], ebx
0x180031593  jz      loc_18003208F
0x180031599  cmp     [rbp+140h+var_19C], ebx
0x18003159c  jnz     loc_18003208F
0x1800315a2  mov     [rbp+140h+var_19C], 1
0x1800315a9  lea     rax, [rsp+240h+nSize]
0x1800315ae  mov     [rsp+240h+pSid], rax; pSid
0x1800315b3  mov     [rsp+240h+nSubAuthority7], ebx; nSubAuthority7
0x1800315b7  mov     [rsp+240h+nSubAuthority6], ebx; nSubAuthority6
0x1800315bb  mov     [rsp+240h+nSubAuthority5], ebx; nSubAuthority5
0x1800315bf  mov     [rsp+240h+dwOptions], ebx; nSubAuthority4
0x1800315c3  mov     [rsp+240h+bInheritHandle], ebx; nSubAuthority3
0x1800315c7  mov     dword ptr [rsp+240h+pdwReturnedProductType], ebx; nSubAuthority2
0x1800315cb  xor     r9d, r9d; nSubAuthority1
0x1800315ce  mov     r8d, 12h; nSubAuthority0
0x1800315d4  mov     dl, 1; nSubAuthorityCount
0x1800315d6  lea     rcx, [rbp+140h+pIdentifierAuthority]; pIdentifierAuthority
0x1800315da  call    cs:__imp_AllocateAndInitializeSid
0x1800315e0  test    eax, eax
0x1800315e2  jnz     loc_180031B56
0x1800315e8  call    cs:__imp_GetLastError
0x1800315ee  mov     r9d, eax
0x1800315f1  lea     r8, aAddlocalsystem_0; "AddLocalSystem: Failed to initialize si"...
0x1800315f8  mov     edx, 2; unsigned int
0x1800315fd  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x180031604  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180031609  mov     rcx, qword ptr [rsp+240h+nSize]
  ... truncated ...
```
