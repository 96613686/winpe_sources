# _GetComponentPath(char const *,CMsiCustomActionManager *,char *,ulong *,int,char const *,bool,bool,ulong *,CRFSCachedSourceInfo &,int *)

- ea: `0x1800523b8`
- end: `0x180053569`
- name: `?_GetComponentPath@@YA?AW4tagINSTALLSTATE@@PEBDPEAVCMsiCustomActionManager@@PEADPEAKH0_N43AEAVCRFSCachedSourceInfo@@PEAH@Z`
- size: `4529`
- prototype: `enum tagINSTALLSTATE __fastcall(const char *, struct CMsiCustomActionManager *, char *, unsigned int *, int, LPCSTR lpString, bool, bool, unsigned int *, struct CRFSCachedSourceInfo *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800520f4`

## callees

- `0x18000a150`
- `0x180015950`
- `0x180019b60`
- `0x18001ba40`
- `0x180024f9c`
- `0x180025560`
- `0x180025a18`
- `0x180051d20`
- `0x1800523b8`
- `0x180053658`
- `0x180071094`
- `0x180071494`
- `0x180071b4c`
- `0x1800a99b0`
- `0x1800a9f70`
- `0x1801135a4`
- `0x18016941c`
- `0x1801932a0`
- `0x1801933c0`
- `0x18025ab12`
- `0x18025ab1e`
- `0x18025ab80`
- `0x18025ac10`
- `0x18025c010`

## import_xrefs

- `msvcrt!isdigit` at `0x18005298d`
- `msvcrt!isdigit` at `0x18005298d`
- `msvcrt!strtol` at `0x180052690`
- `msvcrt!strtol` at `0x180052690`
- `ADVAPI32!RegQueryValueExA` at `0x180053081`
- `ADVAPI32!RegQueryValueExA` at `0x180053081`
- `KERNEL32!InitializeCriticalSection` at `0x180052d76`
- `KERNEL32!InitializeCriticalSection` at `0x180052dac`
- `KERNEL32!InitializeCriticalSection` at `0x180052d76`
- `KERNEL32!InitializeCriticalSection` at `0x180052dac`
- `KERNEL32!GetLastError` at `0x18005341e`
- `KERNEL32!GetLastError` at `0x18005341e`
- `KERNEL32!lstrlenW` at `0x1800527eb`
- `KERNEL32!lstrlenW` at `0x1800527eb`
- `KERNEL32!WideCharToMultiByte` at `0x180053410`
- `KERNEL32!WideCharToMultiByte` at `0x18005344b`
- `KERNEL32!WideCharToMultiByte` at `0x180053410`
- `KERNEL32!WideCharToMultiByte` at `0x18005344b`
- `KERNEL32!lstrlenA` at `0x1800524c6`
- `KERNEL32!lstrlenA` at `0x180052975`
- `KERNEL32!lstrlenA` at `0x1800524c6`
- `KERNEL32!lstrlenA` at `0x180052975`
- `KERNEL32!GlobalFree` at `0x1800524f9`
- `KERNEL32!GlobalFree` at `0x1800525f7`
- `KERNEL32!GlobalFree` at `0x180052627`
- `KERNEL32!GlobalFree` at `0x180052719`
- `KERNEL32!GlobalFree` at `0x180052742`
- `KERNEL32!GlobalFree` at `0x18005276a`
- `KERNEL32!GlobalFree` at `0x18005279a`
- `KERNEL32!GlobalFree` at `0x180052844`
- `KERNEL32!GlobalFree` at `0x180052872`
- `KERNEL32!GlobalFree` at `0x18005289b`
- `KERNEL32!GlobalFree` at `0x1800528ff`
- `KERNEL32!GlobalFree` at `0x18005292c`
- `KERNEL32!GlobalFree` at `0x1800529fb`
- `KERNEL32!GlobalFree` at `0x180052a29`
- `KERNEL32!GlobalFree` at `0x180052a6f`
- `KERNEL32!GlobalFree` at `0x180052adb`
- `KERNEL32!GlobalFree` at `0x180052b08`
- `KERNEL32!GlobalFree` at `0x180052b1e`
- `KERNEL32!GlobalFree` at `0x180052b4e`
- `KERNEL32!GlobalFree` at `0x180052e90`
- `KERNEL32!GlobalFree` at `0x180052f50`
- `KERNEL32!GlobalFree` at `0x180052f77`
- `KERNEL32!GlobalFree` at `0x180052fa7`
- `KERNEL32!GlobalFree` at `0x18005304f`
- `KERNEL32!GlobalFree` at `0x1800530b9`
- `KERNEL32!GlobalFree` at `0x1800530d5`
- `KERNEL32!GlobalFree` at `0x180053120`
- `KERNEL32!GlobalFree` at `0x180053150`
- `KERNEL32!GlobalFree` at `0x1800531e5`
- `KERNEL32!GlobalFree` at `0x180053202`
- `KERNEL32!GlobalFree` at `0x180053233`
- `KERNEL32!GlobalFree` at `0x180053253`
- `KERNEL32!GlobalFree` at `0x180053320`
- `KERNEL32!GlobalFree` at `0x180053376`
- `KERNEL32!GlobalFree` at `0x18005339a`
- `KERNEL32!GlobalFree` at `0x1800533c7`
- `KERNEL32!GlobalFree` at `0x18005346e`
- `KERNEL32!GlobalFree` at `0x180053492`
- `KERNEL32!GlobalFree` at `0x1800534bf`
- `KERNEL32!GlobalFree` at `0x1800534e6`
- `KERNEL32!GlobalFree` at `0x18005350a`
- `KERNEL32!GlobalFree` at `0x180053537`
- `KERNEL32!GlobalFree` at `0x1800524f9`
- `KERNEL32!GlobalFree` at `0x1800525f7`
- `KERNEL32!GlobalFree` at `0x180052627`
- `KERNEL32!GlobalFree` at `0x180052719`
- `KERNEL32!GlobalFree` at `0x180052742`
- `KERNEL32!GlobalFree` at `0x18005276a`
- `KERNEL32!GlobalFree` at `0x18005279a`
- `KERNEL32!GlobalFree` at `0x180052844`
- `KERNEL32!GlobalFree` at `0x180052872`
- `KERNEL32!GlobalFree` at `0x18005289b`
- `KERNEL32!GlobalFree` at `0x1800528ff`
- `KERNEL32!GlobalFree` at `0x18005292c`
- `KERNEL32!GlobalFree` at `0x1800529fb`
- `KERNEL32!GlobalFree` at `0x180052a29`
- `KERNEL32!GlobalFree` at `0x180052a6f`
- `KERNEL32!GlobalFree` at `0x180052adb`
- `KERNEL32!GlobalFree` at `0x180052b08`
- `KERNEL32!GlobalFree` at `0x180052b1e`
- `KERNEL32!GlobalFree` at `0x180052b4e`
- `KERNEL32!GlobalFree` at `0x180052e90`
- `KERNEL32!GlobalFree` at `0x180052f50`
- `KERNEL32!GlobalFree` at `0x180052f77`
- `KERNEL32!GlobalFree` at `0x180052fa7`
- `KERNEL32!GlobalFree` at `0x18005304f`
- `KERNEL32!GlobalFree` at `0x1800530b9`
- `KERNEL32!GlobalFree` at `0x1800530d5`
- `KERNEL32!GlobalFree` at `0x180053120`
- `KERNEL32!GlobalFree` at `0x180053150`
- `KERNEL32!GlobalFree` at `0x1800531e5`
- `KERNEL32!GlobalFree` at `0x180053202`
- `KERNEL32!GlobalFree` at `0x180053233`
- `KERNEL32!GlobalFree` at `0x180053253`
- `KERNEL32!GlobalFree` at `0x180053320`
- `KERNEL32!GlobalFree` at `0x180053376`
- `KERNEL32!GlobalFree` at `0x18005339a`
- `KERNEL32!GlobalFree` at `0x1800533c7`
- `KERNEL32!GlobalFree` at `0x18005346e`
- `KERNEL32!GlobalFree` at `0x180053492`
- `KERNEL32!GlobalFree` at `0x1800534bf`
- `KERNEL32!GlobalFree` at `0x1800534e6`
- `KERNEL32!GlobalFree` at `0x18005350a`
- `KERNEL32!GlobalFree` at `0x180053537`
- `KERNEL32!SetErrorMode` at `0x180053170`
- `KERNEL32!SetErrorMode` at `0x1800531ed`
- `KERNEL32!SetErrorMode` at `0x180053170`
- `KERNEL32!SetErrorMode` at `0x1800531ed`
- `USER32!CharNextA` at `0x180052cfd`
- `USER32!CharNextA` at `0x180052d36`
- `USER32!CharNextA` at `0x180052cfd`
- `USER32!CharNextA` at `0x180052d36`

## pseudocode

```c

```
