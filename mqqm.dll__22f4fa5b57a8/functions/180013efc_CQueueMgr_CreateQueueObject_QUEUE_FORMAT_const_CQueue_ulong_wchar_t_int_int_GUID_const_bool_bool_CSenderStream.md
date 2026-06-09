# CQueueMgr::CreateQueueObject(QUEUE_FORMAT const *,CQueue * *,ulong,wchar_t * *,int *,int,_GUID const *,bool,bool,CSenderStream const *,bool)

- ea: `0x180013efc`
- end: `0x180014742`
- name: `?CreateQueueObject@CQueueMgr@@AEAAJPEBUQUEUE_FORMAT@@PEAPEAVCQueue@@KPEAPEA_WPEAHHPEBU_GUID@@_N5PEBVCSenderStream@@5@Z`
- size: `2118`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, const struct QUEUE_FORMAT *@<rdx>, struct CQueue **@<r8>, unsigned int@<r9d>, wchar_t **, int *, int, const struct _GUID *, bool, bool, const struct CSenderStream *, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x180015f40`
- `0x1800170a4`

## callees

- `0x180009924`
- `0x18000bb04`
- `0x18000f35c`
- `0x18000f430`
- `0x1800106e8`
- `0x180013634`
- `0x180013a00`
- `0x180013efc`
- `0x180016590`
- `0x1800166ac`
- `0x180017cb4`
- `0x180017e5c`
- `0x18001d94c`
- `0x18001f388`
- `0x18002c61c`
- `0x18009bd1c`
- `0x1800cff88`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180014077`
- `msvcrt!free` at `0x180014081`
- `msvcrt!free` at `0x180014090`
- `msvcrt!free` at `0x1800140f6`
- `msvcrt!free` at `0x180014100`
- `msvcrt!free` at `0x18001410f`
- `msvcrt!free` at `0x18001419f`
- `msvcrt!free` at `0x1800141a8`
- `msvcrt!free` at `0x1800141b7`
- `msvcrt!free` at `0x180014203`
- `msvcrt!free` at `0x18001420d`
- `msvcrt!free` at `0x18001421c`
- `msvcrt!free` at `0x180014275`
- `msvcrt!free` at `0x18001427f`
- `msvcrt!free` at `0x18001428e`
- `msvcrt!free` at `0x180014321`
- `msvcrt!free` at `0x18001432a`
- `msvcrt!free` at `0x180014339`
- `msvcrt!free` at `0x1800143ac`
- `msvcrt!free` at `0x1800143b5`
- `msvcrt!free` at `0x1800143c4`
- `msvcrt!free` at `0x180014461`
- `msvcrt!free` at `0x18001446a`
- `msvcrt!free` at `0x180014479`
- `msvcrt!free` at `0x180014519`
- `msvcrt!free` at `0x180014522`
- `msvcrt!free` at `0x180014531`
- `msvcrt!free` at `0x180014628`
- `msvcrt!free` at `0x180014631`
- `msvcrt!free` at `0x180014640`
- `msvcrt!free` at `0x180014681`
- `msvcrt!free` at `0x18001468a`
- `msvcrt!free` at `0x180014699`
- `msvcrt!free` at `0x1800146bd`
- `msvcrt!free` at `0x1800146c6`
- `msvcrt!free` at `0x1800146d5`
- `msvcrt!free` at `0x1800146fb`
- `msvcrt!free` at `0x180014704`
- `msvcrt!free` at `0x180014713`
- `msvcrt!free` at `0x180014077`
- `msvcrt!free` at `0x180014081`
- `msvcrt!free` at `0x180014090`
- `msvcrt!free` at `0x1800140f6`
- `msvcrt!free` at `0x180014100`
- `msvcrt!free` at `0x18001410f`
- `msvcrt!free` at `0x18001419f`
- `msvcrt!free` at `0x1800141a8`
- `msvcrt!free` at `0x1800141b7`
- `msvcrt!free` at `0x180014203`
- `msvcrt!free` at `0x18001420d`
- `msvcrt!free` at `0x18001421c`
- `msvcrt!free` at `0x180014275`
- `msvcrt!free` at `0x18001427f`
- `msvcrt!free` at `0x18001428e`
- `msvcrt!free` at `0x180014321`
- `msvcrt!free` at `0x18001432a`
- `msvcrt!free` at `0x180014339`
- `msvcrt!free` at `0x1800143ac`
- `msvcrt!free` at `0x1800143b5`
- `msvcrt!free` at `0x1800143c4`
- `msvcrt!free` at `0x180014461`
- `msvcrt!free` at `0x18001446a`
- `msvcrt!free` at `0x180014479`
- `msvcrt!free` at `0x180014519`
- `msvcrt!free` at `0x180014522`
- `msvcrt!free` at `0x180014531`
- `msvcrt!free` at `0x180014628`
- `msvcrt!free` at `0x180014631`
- `msvcrt!free` at `0x180014640`
- `msvcrt!free` at `0x180014681`
- `msvcrt!free` at `0x18001468a`
- `msvcrt!free` at `0x180014699`
- `msvcrt!free` at `0x1800146bd`
- `msvcrt!free` at `0x1800146c6`
- `msvcrt!free` at `0x1800146d5`
- `msvcrt!free` at `0x1800146fb`
- `msvcrt!free` at `0x180014704`
- `msvcrt!free` at `0x180014713`
- `KERNEL32!LeaveCriticalSection` at `0x18001439a`
- `KERNEL32!LeaveCriticalSection` at `0x18001444f`
- `KERNEL32!LeaveCriticalSection` at `0x180014507`
- `KERNEL32!LeaveCriticalSection` at `0x180014616`
- `KERNEL32!LeaveCriticalSection` at `0x180014670`
- `KERNEL32!LeaveCriticalSection` at `0x1800146a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800146e7`
- `KERNEL32!LeaveCriticalSection` at `0x18001439a`
- `KERNEL32!LeaveCriticalSection` at `0x18001444f`
- `KERNEL32!LeaveCriticalSection` at `0x180014507`
- `KERNEL32!LeaveCriticalSection` at `0x180014616`
- `KERNEL32!LeaveCriticalSection` at `0x180014670`
- `KERNEL32!LeaveCriticalSection` at `0x1800146a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800146e7`
- `KERNEL32!DuplicateHandle` at `0x18001442a`
- `KERNEL32!DuplicateHandle` at `0x18001442a`
- `KERNEL32!GetCurrentProcess` at `0x1800143ee`
- `KERNEL32!GetCurrentProcess` at `0x1800143fe`
- `KERNEL32!GetCurrentProcess` at `0x1800143ee`
- `KERNEL32!GetCurrentProcess` at `0x1800143fe`

## pseudocode

```c

```
