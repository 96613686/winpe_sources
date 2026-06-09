# CWin32ComputerSystem::GetCompSysInfo(CInstance *)

- ea: `0x1800236c0`
- end: `0x180024bef`
- name: `?GetCompSysInfo@CWin32ComputerSystem@@QEAAJPEAVCInstance@@@Z`
- size: `5423`
- prototype: `__int64 __fastcall(CWin32ComputerSystem *__hidden this, struct CInstance *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023240`
- `0x18009acd0`

## callees

- `0x180015f48`
- `0x1800236c0`
- `0x180024bf8`
- `0x180024dd4`
- `0x1800253c0`
- `0x18002540c`
- `0x18008bb9c`
- `0x18008c0ac`
- `0x1800fc902`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!free` at `0x180024236`
- `msvcrt!free` at `0x180024501`
- `msvcrt!free` at `0x1800248ba`
- `msvcrt!free` at `0x180024236`
- `msvcrt!free` at `0x180024501`
- `msvcrt!free` at `0x1800248ba`
- `msvcrt!malloc` at `0x180023b60`
- `msvcrt!malloc` at `0x180024478`
- `msvcrt!malloc` at `0x180023b60`
- `msvcrt!malloc` at `0x180024478`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800239b1`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800239b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180023b3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180023b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180023b3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180023b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180023afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180023afb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024ac1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024b73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024ac1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024b73`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024af6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024ba4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024af6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024ba4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023964`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024bcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024be3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023964`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024bcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024be3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002390d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002390d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002498f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002498f`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x180023bbb`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x180023bbb`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x1800241c2`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x1800241c2`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1800239ea`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1800239ea`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x180024713`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x180024741`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x18002476f`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x18002479d`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800247cb`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800247f9`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x18002471a`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180024748`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180024776`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800247a4`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800247d2`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180024800`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x18002471a`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180024748`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180024776`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800247a4`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x1800247d2`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180024800`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002396e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002397a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180023986`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180023a4e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180023b06`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002396e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18002397a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180023986`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180023a4e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180023b06`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023726`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18002373c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023752`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023768`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023af1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023bb0`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023bce`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023fe6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180024003`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180024020`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180024039`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800241b7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800241d5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800249d3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800249ef`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023726`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18002373c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023752`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023768`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023af1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023bb0`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023bce`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180023fe6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180024003`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180024020`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180024039`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800241b7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800241d5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800249d3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800249ef`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180023852`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180023be3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180023852`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180023be3`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180023865`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800238b7`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180023955`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180023a8a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180024220`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800248af`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180023865`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800238b7`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180023955`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180023a8a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180024220`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800248af`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180023a42`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180023a42`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180023aa4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180023aa4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180023836`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180023836`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800241e5`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800241fd`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180024b13`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180024b3e`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800241e5`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800241fd`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180024b13`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180024b3e`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x18002383f`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x18002383f`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180023b25`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180023b25`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z` at `0x180023710`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z` at `0x1800239c9`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z` at `0x180024a46`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z` at `0x180023710`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z` at `0x1800239c9`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z` at `0x180024a46`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002387c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023cf1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023d73`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023e2c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023eac`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002413e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002487d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180024b2e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180024bbf`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002387c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023cf1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023d73`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023e2c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180023eac`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002413e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002487d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180024b2e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180024bbf`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800237bc`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800237d7`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800237f6`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180023810`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180023a2d`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x18002489c`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180024a0d`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180024a2b`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800237bc`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800237d7`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x1800237f6`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180023810`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180023a2d`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x18002489c`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180024a0d`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180024a2b`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180024532`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x1800246c5`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180024532`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x1800246c5`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002377b`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002378e`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x1800237a1`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180023d98`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180024824`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180024839`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002484e`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002377b`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002378e`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x1800237a1`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180023d98`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180024824`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180024839`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002484e`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x180023a6f`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x180023a6f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180023a96`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180024242`

## string_xrefs

- `0x180023825`: `Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWin32ComputerSystem::GetCompSysInfo(CWin32ComputerSystem *this, struct CInstance *a2)
{
  const struct CHString *LocalComputerName; // rax
  BYTE *v5; // rax
  int v6; // ecx
  int v7; // edx
  CWin32ComputerSystem *v8; // rcx
  int v9; // r15d
  DWORD v10; // ebx
  __int16 Bias; // ax
  bool v12; // r8
  unsigned int v13; // edi
  IRecordInfo *DeviceInfoList; // rax
  IRecordInfo *v15; // rbx
  signed int LastError; // eax
  unsigned int v17; // ebx
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v18; // rax
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v19; // rsi
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v20; // rdx
  DWORD v21; // r9d
  unsigned int i; // r8d
  DWORD ActiveProcessorCount; // eax
  int v24; // edx
  int v25; // r9d
  _QWORD *v26; // rdx
  _QWORD *v27; // r8
  _BYTE **v28; // rax
  unsigned __int8 **v29; // rax
  unsigned __int8 *v30; // rbx
  unsigned int v31; // edx
  unsigned __int8 *v32; // rcx
  unsigned int v33; // r10d
  struct _tagSHF *v34; // r11
  unsigned __int8 *v35; // r9
  OLECHAR *v36; // r8
  unsigned int j; // eax
  int k; // edx
  OLECHAR v39; // ax
  unsigned __int8 *v40; // rcx
  unsigned __int8 *v41; // r9
  OLECHAR *v42; // r8
  unsigned int m; // eax
  int n; // edx
  OLECHAR v45; // ax
  unsigned __int8 v46; // r8
  unsigned __int8 *v47; // rcx
  unsigned __int8 *v48; // r9
  OLECHAR *v49; // r8
  unsigned int ii; // eax
  int jj; // edx
  OLECHAR v52; // ax
  unsigned __int8 *v53; // rcx
  unsigned __int8 *v54; // r9
  OLECHAR *v55; // r8
  unsigned int kk; // eax
  int mm; // edx
  OLECHAR v58; // ax
  int v59; // r9d
  _QWORD *v60; // rdx
  _QWORD *v61; // r8
  _BYTE **v62; // rax
  __int64 *v63; // rax
  int v64; // r9d
  _QWORD *v65; // rdx
  _QWORD *v66; // r8
  _BYTE **v67; // rax
  __int64 *v68; // rbx
  int v69; // r9d
  _QWORD *v70; // rdx
  _QWORD *v71; // r8
  _BYTE **v72; // rax
  __int64 *v73; // rbx
  __int64 v74; // rbx
  int v75; // r9d
  _QWORD *v76; // rdx
  _QWORD *v77; // r8
  _BYTE **v78; // rax
  _QWORD *v79; // rbx
  _BYTE *v80; // rbx
  char *v81; // rcx
  char *v82; // rdx
  OLECHAR *v83; // r8
  unsigned int i2; // eax
  OLECHAR v85; // ax
  int v86; // r9d
  _QWORD *v87; // rax
  _QWORD *v88; // r8
  _BYTE **v89; // rcx
  __int64 *v90; // rbx
  POWER_PLATFORM_ROLE v91; // eax
  unsigned int v92; // eax
  int HypervisorPresent; // eax
  unsigned int CompSysInfoNT; // ebx
  __int64 v96; // rdi
  LONG v97; // ecx
  unsigned int v98; // r8d
  char *v99; // rcx
  char *v100; // rdx
  OLECHAR *v101; // r9
  unsigned int nn; // eax
  int i1; // r8d
  OLECHAR v104; // ax
  HKEY v105; // rax
  SAFEARRAYBOUND v106; // rbx
  BSTR v107; // rax
  struct IErrorInfo *v108; // rdx
  void *v109; // rcx
  HRESULT v110; // eax
  struct IErrorInfo *v111; // rdx
  __int64 v112; // rbx
  SAFEARRAY *parray; // rax
  LONG v114; // ecx
  __int64 Size; // rax
  int SystemMetrics; // eax
  const unsigned __int16 *v117; // r8
  bool v118; // r8
  int v119; // eax
  signed int v120; // eax
  __int64 v121; // rbx
  __int16 pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  LONG pExceptionObject; // [rsp+44h] [rbp-BCh] BYREF
  char v124[8]; // [rsp+48h] [rbp-B8h] BYREF
  SAFEARRAYBOUND v125; // [rsp+50h] [rbp-B0h] BYREF
  int v126; // [rsp+58h] [rbp-A8h]
  DWORD ReturnedLength; // [rsp+5Ch] [rbp-A4h] BYREF
  LONG rgIndices; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  char v130[8]; // [rsp+70h] [rbp-90h] BYREF
  char v131[8]; // [rsp+78h] [rbp-88h] BYREF
  char v132[8]; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v136; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v138; // [rsp+D0h] [rbp-30h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v140; // [rsp+108h] [rbp+8h]
  __int128 v141; // [rsp+118h] [rbp+18h]
  _OWORD v142[3]; // [rsp+128h] [rbp+28h] BYREF
  struct _MEMORYSTATUSEX Buffer; // [rsp+160h] [rbp+60h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Name[304]; // [rsp+250h] [rbp+150h] BYREF
  OLECHAR psz[72]; // [rsp+4B0h] [rbp+3B0h] BYREF
  BYTE Data[48]; // [rsp+540h] [rbp+440h] BYREF

  v126 = 0;
  CInstance::SetWBEMINT64(a2, L"PauseAfterReset", -1);
  CInstance::SetDWORD(a2, L"PowerOnPasswordStatus", 3u);
  CInstance::SetDWORD(a2, L"KeyboardPasswordStatus", 3u);
  CInstance::SetDWORD(a2, L"AdminPasswordStatus", 3u);
  CInstance::SetDWORD(a2, L"FrontPanelResetStatus", 3u);
  CInstance::SetByte(a2, L"ChassisBootupState", 2u);
  CInstance::SetByte(a2, L"PowerSupplyState", 2u);
  CInstance::SetByte(a2, L"ThermalState", 2u);
  pv[0] = -1;
  CInstance::SetWBEMINT16(a2, L"ResetCount", pv);
  pv[0] = -1;
  CInstance::SetWBEMINT16(a2, L"ResetLimit", pv);
  pv[0] = 1;
  CInstance::SetWBEMINT16(a2, L"ResetCapability", pv);
  pv[0] = 0;
  CInstance::SetWBEMINT16(a2, L"PowerState", pv);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  CInstance::SetCharSplat(a2, L"CreationClassName", L"Win32_ComputerSystem");
  LocalComputerName = Provider::GetLocalComputerName(this);
  CInstance::SetCHString(a2, L"Caption", LocalComputerName);
  CInstance::Setbool(a2, L"BootROMSupported", 1);
  CInstance::SetCHString(a2, L"Status", L"OK");
  v140 = *(_OWORD *)L"?:\\pagefile.sys";
  v141 = *(_OWORD *)L"ile.sys";
  hKey = 0;
  cbData = 44;
  *(_WORD *)Data = 0;
  CInstance::Setbool(a2, L"AutomaticManagedPagefile", 0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
          0,
          0x20019u,
          &hKey)
    && !RegQueryValueExW(hKey, L"PagingFiles", 0, 0, Data, &cbData) )
  {
    v5 = Data;
    do
    {
      v6 = *((unsigned __int16 *)v5 - 540);
      v7 = *(unsigned __int16 *)v5 - v6;
      if ( v7 )
        break;
      v5 += 2;
    }
    while ( v6 );
    if ( !v7 )
      CInstance::Setbool(a2, L"AutomaticManagedPagefile", 1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  CHString::CHString((CHString *)v132);
  CHString::CHString((CHString *)v131);
  CHString::CHString((CHString *)v130);
  CWin32ComputerSystem::SetUserName(v8, a2);
  v9 = 64;
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
    CInstance::SetWBEMINT64(a2, L"TotalPhysicalMemory", Buffer.ullTotalPhys);
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  v10 = GetTimeZoneInformation(&TimeZoneInformation);
  if ( v10 != -1 )
  {
    Bias = TimeZoneInformation.Bias;
    if ( v10 == 2 )
    {
      TimeZoneInformation.Bias += TimeZoneInformation.DaylightBias;
      pv[0] = -(__int16)(LOWORD(TimeZoneInformation.DaylightBias) + Bias);
      CInstance::SetWBEMINT16(a2, L"CurrentTimeZone", pv);
      v118 = 1;
    }
    else
    {
      TimeZoneInformation.Bias += TimeZoneInformation.StandardBias;
      pv[0] = -(__int16)(LOWORD(TimeZoneInformation.StandardBias) + Bias);
      CInstance::SetWBEMINT16(a2, L"CurrentTimeZone", pv);
      if ( !v10 )
      {
LABEL_15:
        CRegistry::CRegistry((CRegistry *)Name);
        CHString::CHString((CHString *)&v125);
        v12 = CRegistry::OpenLocalMachineKeyAndReadValue(
                (CRegistry *)Name,
                L"System\\CurrentControlSet\\Control\\TimeZoneInformation",
                L"DisableAutoDaylightTimeSet",
                (struct CHString *)&v125) != 0;
        CInstance::Setbool(a2, L"EnableDaylightSavingsTime", v12);
        CHString::~CHString((CHString *)&v125);
        CRegistry::~CRegistry((CRegistry *)Name);
        goto LABEL_16;
      }
      v118 = 0;
    }
    CInstance::Setbool(a2, L"DaylightInEffect", v118);
    goto LABEL_15;
  }
LABEL_16:
  v13 = 0;
  memset(v142, 0, sizeof(v142));
  LODWORD(v142[0]) = 48;
  DeviceInfoList = (IRecordInfo *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v15 = DeviceInfoList;
  if ( DeviceInfoList != (IRecordInfo *)-1LL )
  {
    LOBYTE(v136.vt) = 0;
    v136.llVal = DevObjDestroyDeviceInfoList;
    v136.pRecInfo = DeviceInfoList;
    v126 = 1;
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_INFRARED, 0, 2, 0, 0) )
      v13 = DevObjEnumDeviceInfo(v15, 0, v142) != 0;
    v126 = 0;
    ((void (__fastcall *)(IRecordInfo *))DevObjDestroyDeviceInfoList)(v15);
  }
  CInstance::SetDWORD(a2, L"InfraredSupported", v13);
  GetSystemInfo(&SystemInfo);
  CHString::CHString((CHString *)v124);
  if ( SystemInfo.wProcessorArchitecture )
  {
    switch ( SystemInfo.wProcessorArchitecture )
    {
      case 5u:
        CHString::operator=(v124, L"ARM-based PC");
        break;
      case 6u:
        CHString::operator=(v124, L"Itanium (TM) -based System");
        break;
      case 9u:
        CHString::operator=(v124, L"x64-based PC");
        break;
      case 0xCu:
        CHString::operator=(v124, L"ARM64-based PC");
        break;
      default:
        CHString::operator=(v124, L"Unknown");
        break;
    }
  }
  else
  {
    CHString::operator=(v124, L"X86-based PC");
  }
  ReturnedLength = 0;
  if ( GetLogicalProcessorInformationEx(RelationProcessorPackage, 0, &ReturnedLength) )
  {
    CHString::~CHString((CHString *)v124);
    CHString::~CHString((CHString *)v130);
    CHString::~CHString((CHString *)v131);
    CHString::~CHString((CHString *)v132);
    return 2147749889LL;
  }
  LastError = GetLastError();
  v17 = LastError;
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    CHString::~CHString((CHString *)v124);
    CHString::~CHString((CHString *)v130);
    CHString::~CHString((CHString *)v131);
    CHString::~CHString((CHString *)v132);
    return v17;
  }
  v18 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)malloc(ReturnedLength);
  v19 = v18;
  if ( !v18 )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  v138 = v18;
  if ( !GetLogicalProcessorInformationEx(RelationProcessorPackage, v18, &ReturnedLength) )
  {
    v120 = GetLastError();
    CompSysInfoNT = v120;
    if ( v120 > 0 )
      CompSysInfoNT = (unsigned __int16)v120 | 0x80070000;
    goto LABEL_149;
  }
  v20 = v19;
  v21 = 0;
  for ( i = 0; v21 < ReturnedLength; v20 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)((char *)v20 + Size) )
  {
    ++i;
    Size = v20->Size;
    v21 += Size;
  }
  CInstance::SetDWORD(a2, L"NumberOfProcessors", i);
  ActiveProcessorCount = GetActiveProcessorCount(0xFFFFu);
  CInstance::SetDWORD(a2, L"NumberOfLogicalProcessors", ActiveProcessorCount);
  CInstance::SetCHString(a2, L"SystemType", (const struct CHString *)v124);
  if ( !(unsigned __int8)IsGetSystemMetricsPresent() )
    goto LABEL_25;
  SystemMetrics = GetSystemMetrics(67);
  if ( SystemMetrics )
  {
    v119 = SystemMetrics - 1;
    if ( v119 )
    {
      if ( v119 != 1 )
        goto LABEL_25;
      v117 = L"Fail-safe with network boot";
    }
    else
    {
      v117 = L"Fail-safe boot";
    }
  }
  else
  {
    v117 = L"Normal boot";
  }
  CInstance::SetCHString(a2, L"BootupState", v117);
LABEL_25:
  pExceptionObject = 0;
  if ( !(unsigned int)CSMBios::Init((CSMBios *)&pExceptionObject, v24) )
    goto LABEL_146;
  rgIndices = 0;
  v25 = 0;
  v26 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_220;
  while ( 1 )
  {
    v27 = v26;
    v28 = (_BYTE **)v26[2];
    if ( **v28 )
      break;
    v26 = (_QWORD *)v26[1];
LABEL_29:
    if ( !v26 )
      goto LABEL_34;
  }
  if ( **v28 > 1u )
  {
    v26 = (_QWORD *)*v26;
    goto LABEL_29;
  }
  v25 = 1;
LABEL_34:
  if ( !v25 )
    v27 = 0;
  if ( !v27 )
  {
LABEL_220:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    goto LABEL_73;
  }
  v29 = (unsigned __int8 **)v27[2];
  if ( v29 )
  {
    v30 = *v29;
    v31 = (*v29)[4];
    v32 = &(*v29)[(*v29)[1]];
    v33 = CSMBios::m_Size;
    v34 = CSMBios::m_pTable;
    v35 = (unsigned __int8 *)CSMBios::m_pTable + CSMBios::m_Size;
    v36 = psz;
    for ( j = 1; v32 < v35; ++v32 )
    {
      if ( v31 <= j || !*v32 )
        break;
      do
      {
        if ( !*v32 )
          break;
        ++v32;
      }
      while ( v32 < v35 );
      ++j;
    }
    if ( v31 )
    {
      for ( k = 64; v32 < v35; --k )
      {
        v39 = *v32;
        if ( (unsigned __int8)v39 <= 0xFu )
          break;
        if ( !k )
          break;
        ++v32;
        *v36++ = v39;
      }
    }
    *v36 = 0;
    if ( psz[0] )
    {
      CInstance::SetCHString(a2, L"Manufacturer", psz);
      v34 = CSMBios::m_pTable;
      v33 = CSMBios::m_Size;
    }
    v40 = &v30[v30[1]];
    v41 = (unsigned __int8 *)v34 + v33;
    v42 = psz;
    for ( m = 1; v40 < v41; ++v40 )
    {
      if ( v30[5] <= m || !*v40 )
        break;
      do
      {
        if ( !*v40 )
          break;
        ++v40;
      }
      while ( v40 < v41 );
      ++m;
    }
    if ( v30[5] )
    {
      for ( n = 64; v40 < v41; --n )
      {
        v45 = *v40;
        if ( (unsigned __int8)v45 <= 0xFu )
          break;
        if ( !n )
          break;
        ++v40;
        *v42++ = v45;
      }
    }
    *v42 = 0;
    if ( psz[0] )
      CInstance::SetCHString(a2, L"Model", psz);
    if ( CSMBios::m_Version <= 0x20000 )
      v46 = 2;
    else
      v46 = v30[24];
    CInstance::SetByte(a2, L"WakeUpType", v46);
    if ( CSMBios::m_Version >= 0x20004 )
    {
      v47 = &v30[v30[1]];
      v48 = (unsigned __int8 *)CSMBios::m_pTable + CSMBios::m_Size;
      v49 = psz;
      for ( ii = 1; v47 < v48; ++v47 )
      {
        if ( v30[25] <= ii || !*v47 )
          break;
        do
        {
          if ( !*v47 )
            break;
          ++v47;
        }
        while ( v47 < v48 );
        ++ii;
      }
      if ( v30[25] )
      {
        for ( jj = 64; v47 < v48; --jj )
        {
          v52 = *v47;
          if ( (unsigned __int8)v52 <= 0xFu )
            break;
          if ( !jj )
            break;
          ++v47;
          *v49++ = v52;
        }
      }
      *v49 = 0;
      if ( psz[0] )
        CInstance::SetCHString(a2, L"SystemSKUNumber", psz);
      v53 = &v30[v30[1]];
      v54 = (unsigned __int8 *)CSMBios::m_pTable + CSMBios::m_Size;
      v55 = psz;
      for ( kk = 1; v53 < v54; ++v53 )
      {
        if ( v30[26] <= kk || !*v53 )
          break;
        do
        {
          if ( !*v53 )
            break;
          ++v53;
        }
        while ( v53 < v54 );
        ++kk;
      }
      if ( v30[26] )
      {
        for ( mm = 64; v53 < v54; --mm )
        {
          v58 = *v53;
          if ( (unsigned __int8)v58 <= 0xFu )
            break;
          if ( !mm )
            break;
          ++v53;
          *v55++ = v58;
        }
      }
      *v55 = 0;
      if ( psz[0] )
        CInstance::SetCHString(a2, L"SystemFamily", psz);
    }
  }
LABEL_73:
  v59 = 0;
  v60 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
  {
LABEL_221:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    goto LABEL_85;
  }
  while ( 2 )
  {
    v61 = v60;
    v62 = (_BYTE **)v60[2];
    if ( **v62 < 0xBu )
    {
      v60 = (_QWORD *)v60[1];
      goto LABEL_76;
    }
    if ( **v62 > 0xBu )
    {
      v60 = (_QWORD *)*v60;
LABEL_76:
      if ( !v60 )
        goto LABEL_81;
      continue;
    }
    break;
  }
  v59 = 1;
LABEL_81:
  if ( !v59 )
    v61 = 0;
  if ( !v61 )
    goto LABEL_221;
  v63 = (__int64 *)v61[2];
  if ( v63 )
  {
    v96 = *v63;
    rgsabound = 0;
    VariantInit(&pvarg);
    rgsabound.lLbound = 0;
    rgsabound.cElements = *(unsigned __int8 *)(v96 + 4);
    pvarg.llVal = (LONGLONG)SafeArrayCreate(8u, 1u, &rgsabound);
    if ( !pvarg.llVal )
    {
      pExceptionObject = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    pvarg.vt = 8200;
    rgIndices = 0;
    if ( *(_BYTE *)(v96 + 4) )
    {
      v97 = 0;
      do
      {
        v98 = v97 + 1;
        v99 = (char *)(v96 + *(unsigned __int8 *)(v96 + 1));
        v100 = (char *)CSMBios::m_pTable + CSMBios::m_Size;
        v101 = psz;
        for ( nn = 1; v99 < v100; ++v99 )
        {
          if ( v98 <= nn || !*v99 )
            break;
          do
          {
            if ( !*v99 )
              break;
            ++v99;
          }
          while ( v99 < v100 );
          ++nn;
        }
        if ( v98 )
        {
          for ( i1 = 64; v99 < v100; --i1 )
          {
            v104 = (unsigned __int8)*v99;
            if ( (unsigned __int8)v104 <= 0xFu )
              break;
            if ( !i1 )
              break;
            ++v99;
            *v101++ = v104;
          }
        }
        *v101 = 0;
        v105 = (HKEY)malloc(0x18u);
        v106 = (SAFEARRAYBOUND)v105;
        if ( !v105 )
        {
          pExceptionObject = 0;
          throw (CHeap_Exception *)&pExceptionObject;
        }
        phkResult = v105;
        *((_QWORD *)v105 + 1) = 0;
        *((_DWORD *)v105 + 4) = 1;
        v107 = SysAllocString(psz);
        **(_QWORD **)&v106 = v107;
        if ( !v107 )
          _com_raise_error(-2147024882, v108);
        v125 = v106;
        SafeArrayPutElement(pvarg.parray, &rgIndices, **(void ***)&v106);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v106 + 16LL), 0xFFFFFFFF) == 1 )
        {
          if ( **(_QWORD **)&v106 )
          {
            SysFreeString(**(BSTR **)&v106);
            **(_QWORD **)&v106 = 0;
          }
          v109 = *(void **)(*(_QWORD *)&v106 + 8LL);
          if ( v109 )
          {
            free(v109);
            *(_QWORD *)(*(_QWORD *)&v106 + 8LL) = 0;
          }
          free(*(void **)&v106);
        }
        v125 = 0;
        v97 = rgIndices + 1;
        rgIndices = v97;
      }
      while ( v97 < *(unsigned __int8 *)(v96 + 4) );
    }
    CInstance::SetVariant(a2, L"OEMStringArray", &pvarg);
    v110 = VariantClear(&pvarg);
    if ( v110 < 0 )
      _com_raise_error(v110, v111);
  }
LABEL_85:
  v64 = 0;
  v65 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_222;
  while ( 2 )
  {
    v66 = v65;
    v67 = (_BYTE **)v65[2];
    if ( **v67 < 0x17u )
    {
      v65 = (_QWORD *)v65[1];
      goto LABEL_88;
    }
    if ( **v67 > 0x17u )
    {
      v65 = (_QWORD *)*v65;
LABEL_88:
      if ( !v65 )
        goto LABEL_93;
      continue;
    }
    break;
  }
  v64 = 1;
LABEL_93:
  if ( !v64 )
    v66 = 0;
  if ( !v66 )
  {
LABEL_222:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    goto LABEL_98;
  }
  v68 = (__int64 *)v66[2];
  if ( v68 )
  {
    v121 = *v68;
    CInstance::SetDWORD(a2, L"BootOptionOnLimit", (*(unsigned __int8 *)(v121 + 4) >> 3) & 3);
    CInstance::SetDWORD(a2, L"BootOptionOnWatchDog", (*(unsigned __int8 *)(v121 + 4) >> 1) & 3);
    pv[0] = *(_WORD *)(v121 + 5);
    CInstance::SetWBEMINT16(a2, L"ResetCount", pv);
    pv[0] = *(_WORD *)(v121 + 7);
    CInstance::SetWBEMINT16(a2, L"ResetLimit", pv);
    CInstance::SetWBEMINT64(a2, L"PauseAfterReset", 60000LL * *(unsigned __int16 *)(v121 + 11));
  }
LABEL_98:
  v69 = 0;
  v70 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_223;
  while ( 2 )
  {
    v71 = v70;
    v72 = (_BYTE **)v70[2];
    if ( **v72 < 0x18u )
    {
      v70 = (_QWORD *)v70[1];
      goto LABEL_101;
    }
    if ( **v72 > 0x18u )
    {
      v70 = (_QWORD *)*v70;
LABEL_101:
      if ( !v70 )
        goto LABEL_106;
      continue;
    }
    break;
  }
  v69 = 1;
LABEL_106:
  if ( !v69 )
    v71 = 0;
  if ( !v71 )
  {
LABEL_223:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    goto LABEL_111;
  }
  v73 = (__int64 *)v71[2];
  if ( v73 )
  {
    v74 = *v73;
    CInstance::SetDWORD(a2, L"PowerOnPasswordStatus", *(unsigned __int8 *)(v74 + 4) >> 6);
    CInstance::SetDWORD(a2, L"KeyboardPasswordStatus", (*(unsigned __int8 *)(v74 + 4) >> 4) & 3);
    CInstance::SetDWORD(a2, L"AdminPasswordStatus", (*(unsigned __int8 *)(v74 + 4) >> 2) & 3);
    CInstance::SetDWORD(a2, L"FrontPanelResetStatus", *(_BYTE *)(v74 + 4) & 3);
  }
LABEL_111:
  v75 = 0;
  v76 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_224;
  while ( 2 )
  {
    v77 = v76;
    v78 = (_BYTE **)v76[2];
    if ( **v78 < 3u )
    {
      v76 = (_QWORD *)v76[1];
      goto LABEL_114;
    }
    if ( **v78 > 3u )
    {
      v76 = (_QWORD *)*v76;
LABEL_114:
      if ( !v76 )
        goto LABEL_119;
      continue;
    }
    break;
  }
  v75 = 1;
LABEL_119:
  if ( !v75 )
    v77 = 0;
  if ( !v77 )
  {
LABEL_224:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    goto LABEL_133;
  }
  v79 = (_QWORD *)v77[2];
  if ( v79 )
  {
    v80 = (_BYTE *)*v79;
    if ( CSMBios::m_Version > 0x20000 && v80[1] >= 0xDu )
    {
      CInstance::SetByte(a2, L"ChassisBootupState", v80[9]);
      CInstance::SetByte(a2, L"PowerSupplyState", v80[10]);
      CInstance::SetByte(a2, L"ThermalState", v80[11]);
    }
    if ( CSMBios::m_Version >= 0x20007 )
    {
      v81 = &v80[(unsigned __int8)v80[1]];
      v82 = (char *)CSMBios::m_pTable + CSMBios::m_Size;
      v83 = psz;
      for ( i2 = 1; v81 < v82; ++v81 )
      {
        if ( (unsigned __int8)v80[21] <= i2 || !*v81 )
          break;
        do
        {
          if ( !*v81 )
            break;
          ++v81;
        }
        while ( v81 < v82 );
        ++i2;
      }
      if ( v80[21] && v81 < v82 )
      {
        do
        {
          v85 = (unsigned __int8)*v81;
          if ( (unsigned __int8)v85 <= 0xFu )
            break;
          if ( !v9 )
            break;
          ++v81;
          *v83++ = v85;
          --v9;
        }
        while ( v81 < v82 );
      }
      *v83 = 0;
      if ( psz[0] )
        CInstance::SetCHString(a2, L"ChassisSKUNumber", psz);
    }
  }
LABEL_133:
  v86 = 0;
  v87 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_225;
  while ( 2 )
  {
    v88 = v87;
    v89 = (_BYTE **)v87[2];
    if ( **v89 < 0x20u )
    {
      v87 = (_QWORD *)v87[1];
      goto LABEL_136;
    }
    if ( **v89 > 0x20u )
    {
      v87 = (_QWORD *)*v87;
LABEL_136:
      if ( !v87 )
        goto LABEL_141;
      continue;
    }
    break;
  }
  v86 = 1;
LABEL_141:
  if ( !v86 )
    v88 = 0;
  if ( !v88 )
  {
LABEL_225:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    goto LABEL_145;
  }
  v90 = (__int64 *)v88[2];
  if ( v90 )
  {
    v112 = *v90;
    memset(&v136, 0, sizeof(v136));
    VariantInit(&v136);
    v125 = (SAFEARRAYBOUND)10LL;
    parray = SafeArrayCreate(0x11u, 1u, &v125);
    v136.llVal = (LONGLONG)parray;
    v136.vt = 8209;
    pExceptionObject = 0;
    v114 = 0;
    while ( 1 )
    {
      LOBYTE(pv[0]) = *(_BYTE *)(v114 + v112 + 10);
      SafeArrayPutElement(parray, &pExceptionObject, pv);
      v114 = pExceptionObject + 1;
      pExceptionObject = v114;
      if ( v114 >= 10 )
        break;
      parray = v136.parray;
    }
    CInstance::SetVariant(a2, L"BootStatus", &v136);
  }
LABEL_145:
  v91 = PowerDeterminePlatformRole();
  CInstance::SetDWORD(a2, L"PCSystemType", v91);
  v92 = PowerDeterminePlatformRoleEx(2);
  CInstance::SetDWORD(a2, L"PCSystemTypeEx", v92);
LABEL_146:
  if ( CInstance::IsNull(a2, L"Manufacturer") || CInstance::IsNull(a2, L"Model") )
  {
    phkResult = 0;
    pExceptionObject = 65;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Hardware\\ACPI\\DSDT", 0, 0x2000000u, &phkResult)
      && !RegEnumKeyExW(phkResult, 0, Name, (LPDWORD)&pExceptionObject, 0, 0, 0, 0) )
    {
      v125 = 0;
      if ( CInstance::IsNull(a2, L"Manufacturer") )
        CInstance::SetCHString(a2, L"Manufacturer", Name);
      if ( CInstance::IsNull(a2, L"Model") )
      {
        pExceptionObject = 65;
        if ( !RegOpenKeyExW(phkResult, Name, 0, 0x2000000u, (PHKEY)&v125)
          && !RegEnumKeyExW(*(HKEY *)&v125, 0, (LPWSTR)&TimeZoneInformation, (LPDWORD)&pExceptionObject, 0, 0, 0, 0) )
        {
          CInstance::SetCHString(a2, L"Model", (const unsigned __int16 *)&TimeZoneInformation);
        }
        if ( v125 )
          RegCloseKey(*(HKEY *)&v125);
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  HypervisorPresent = GetHypervisorPresent();
  CInstance::Setbool(a2, L"HypervisorPresent", HypervisorPresent != 0);
  CompSysInfoNT = CWin32ComputerSystem::GetCompSysInfoNT(this, a2);
LABEL_149:
  free(v19);
  CHString::~CHString((CHString *)v124);
  CHString::~CHString((CHString *)v130);
  CHString::~CHString((CHString *)v131);
  CHString::~CHString((CHString *)v132);
  return CompSysInfoNT;
}

```

## disassembly

```asm
0x1800236c0  mov     [rsp-8+arg_10], rbx
0x1800236c5  push    rbp
0x1800236c6  push    rsi
0x1800236c7  push    rdi
0x1800236c8  push    r12
0x1800236ca  push    r13
0x1800236cc  push    r14
0x1800236ce  push    r15
0x1800236d0  lea     rbp, [rsp-480h]
0x1800236d8  sub     rsp, 580h
0x1800236df  mov     rax, cs:__security_cookie
0x1800236e6  xor     rax, rsp
0x1800236e9  mov     [rbp+4B0h+var_40], rax
0x1800236f0  mov     r12, rdx
0x1800236f3  mov     r13, rcx
0x1800236f6  xor     esi, esi
0x1800236f8  mov     [rsp+5B0h+var_558], esi
0x1800236fc  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180023703  mov     r8, r14
0x180023706  lea     rdx, aPauseafterrese; "PauseAfterReset"
0x18002370d  mov     rcx, r12
0x180023710  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z; CInstance::SetWBEMINT64(ushort const *,__int64)
0x180023716  mov     r8d, 3
0x18002371c  lea     rdx, aPoweronpasswor; "PowerOnPasswordStatus"
0x180023723  mov     rcx, r12
0x180023726  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18002372c  mov     r8d, 3
0x180023732  lea     rdx, aKeyboardpasswo; "KeyboardPasswordStatus"
0x180023739  mov     rcx, r12
0x18002373c  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180023742  mov     r8d, 3
0x180023748  lea     rdx, aAdminpasswords; "AdminPasswordStatus"
0x18002374f  mov     rcx, r12
0x180023752  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180023758  mov     r8d, 3
0x18002375e  lea     rdx, aFrontpanelrese; "FrontPanelResetStatus"
0x180023765  mov     rcx, r12
0x180023768  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18002376e  mov     r8b, 2
0x180023771  lea     rdx, aChassisbootups; "ChassisBootupState"
0x180023778  mov     rcx, r12
0x18002377b  call    cs:__imp_?SetByte@CInstance@@QEAA_NPEBGE@Z; CInstance::SetByte(ushort const *,uchar)
0x180023781  mov     r8b, 2
0x180023784  lea     rdx, aPowersupplysta; "PowerSupplyState"
0x18002378b  mov     rcx, r12
0x18002378e  call    cs:__imp_?SetByte@CInstance@@QEAA_NPEBGE@Z; CInstance::SetByte(ushort const *,uchar)
0x180023794  mov     r8b, 2
0x180023797  lea     rdx, aThermalstate; "ThermalState"
0x18002379e  mov     rcx, r12
0x1800237a1  call    cs:__imp_?SetByte@CInstance@@QEAA_NPEBGE@Z; CInstance::SetByte(ushort const *,uchar)
0x1800237a7  mov     [rsp+5B0h+pv], r14w
0x1800237ad  lea     r8, [rsp+5B0h+pv]
0x1800237b2  lea     rdx, aResetcount; "ResetCount"
0x1800237b9  mov     rcx, r12
0x1800237bc  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800237c2  mov     [rsp+5B0h+pv], r14w
0x1800237c8  lea     r8, [rsp+5B0h+pv]
0x1800237cd  lea     rdx, aResetlimit; "ResetLimit"
0x1800237d4  mov     rcx, r12
0x1800237d7  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800237dd  mov     eax, 1
0x1800237e2  mov     [rsp+5B0h+pv], ax
0x1800237e7  lea     r8, [rsp+5B0h+pv]
0x1800237ec  lea     rdx, aResetcapabilit; "ResetCapability"
0x1800237f3  mov     rcx, r12
0x1800237f6  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x1800237fc  mov     [rsp+5B0h+pv], si
0x180023801  lea     r8, [rsp+5B0h+pv]
0x180023806  lea     rdx, aPowerstate; "PowerState"
0x18002380d  mov     rcx, r12
0x180023810  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x180023816  xorps   xmm0, xmm0
0x180023819  movups  xmmword ptr [rbp+4B0h+SystemInfo], xmm0
0x18002381d  movups  xmmword ptr [rbp+4B0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180023821  movups  xmmword ptr [rbp+4B0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180023825  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x18002382c  lea     rdx, aCreationclassn; "CreationClassName"
0x180023833  mov     rcx, r12
0x180023836  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18002383c  mov     rcx, r13
0x18002383f  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x180023845  mov     r8, rax
0x180023848  lea     rdx, aCaption; "Caption"
0x18002384f  mov     rcx, r12
0x180023852  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180023858  mov     r8b, 1
0x18002385b  lea     rdx, aBootromsupport; "BootROMSupported"
0x180023862  mov     rcx, r12
0x180023865  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18002386b  lea     r8, aOk; "OK"
0x180023872  lea     rdx, aStatus; "Status"
0x180023879  mov     rcx, r12
0x18002387c  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180023882  movups  xmm0, xmmword ptr cs:aPagefileSys_1; "?:\\pagefile.sys"
0x180023889  movups  [rbp+4B0h+var_4A8], xmm0
0x18002388d  movups  xmm1, xmmword ptr cs:aPagefileSys_1+10h; "ile.sys"
0x180023894  movups  [rbp+4B0h+var_498], xmm1
0x180023898  mov     [rbp+4B0h+hKey], rsi
0x18002389c  mov     [rbp+4B0h+cbData], 2Ch ; ','
0x1800238a3  mov     word ptr [rbp+4B0h+Data], si
0x1800238aa  xor     r8d, r8d
0x1800238ad  lea     rdx, aAutomaticmanag; "AutomaticManagedPagefile"
0x1800238b4  mov     rcx, r12
0x1800238b7  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800238bd  lea     rax, [rbp+4B0h+hKey]
0x1800238c1  mov     [rsp+5B0h+phkResult], rax; phkResult
0x1800238c6  mov     r9d, 20019h; samDesired
0x1800238cc  xor     r8d, r8d; ulOptions
0x1800238cf  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x1800238d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800238dd  call    cs:__imp_RegOpenKeyExW
0x1800238e3  test    eax, eax
0x1800238e5  jnz     short loc_18002395B
0x1800238e7  lea     rax, [rbp+4B0h+cbData]
0x1800238eb  mov     [rsp+5B0h+lpcbData], rax; lpcbData
0x1800238f0  lea     rax, [rbp+4B0h+Data]
0x1800238f7  mov     [rsp+5B0h+phkResult], rax; lpData
0x1800238fc  xor     r9d, r9d; lpType
0x1800238ff  xor     r8d, r8d; lpReserved
0x180023902  lea     rdx, aPagingfiles; "PagingFiles"
0x180023909  mov     rcx, [rbp+4B0h+hKey]; hKey
0x18002390d  call    cs:__imp_RegQueryValueExW
0x180023913  test    eax, eax
0x180023915  jnz     short loc_18002395B
0x180023917  lea     rax, [rbp+4B0h+Data]
0x18002391e  lea     r8, [rbp+4B0h+var_4A8]
0x180023922  sub     r8, rax
0x180023925  nop     word ptr [rax+rax+00000000h]
0x180023930  movzx   edx, word ptr [rax]
0x180023933  movzx   ecx, word ptr [rax+r8]
0x180023938  sub     edx, ecx
0x18002393a  jnz     short loc_180023944
0x18002393c  add     rax, 2
0x180023940  test    ecx, ecx
0x180023942  jnz     short loc_180023930
0x180023944  test    edx, edx
0x180023946  jnz     short loc_18002395B
0x180023948  mov     r8b, 1
0x18002394b  lea     rdx, aAutomaticmanag; "AutomaticManagedPagefile"
0x180023952  mov     rcx, r12
0x180023955  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18002395b  mov     rcx, [rbp+4B0h+hKey]; hKey
0x18002395f  test    rcx, rcx
0x180023962  jz      short loc_18002396A
0x180023964  call    cs:__imp_RegCloseKey
0x18002396a  lea     rcx, [rbp+4B0h+var_530]
0x18002396e  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180023974  nop
0x180023975  lea     rcx, [rsp+5B0h+var_538]
0x18002397a  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180023980  nop
0x180023981  lea     rcx, [rsp+5B0h+var_540]
0x180023986  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18002398c  nop
0x18002398d  mov     rdx, r12; struct CInstance *
0x180023990  call    ?SetUserName@CWin32ComputerSystem@@QEAAXPEAVCInstance@@@Z; CWin32ComputerSystem::SetUserName(CInstance *)
0x180023995  mov     r15d, 40h ; '@'
0x18002399b  mov     r8d, r15d; Size
0x18002399e  xor     edx, edx; Val
0x1800239a0  lea     rcx, [rbp+4B0h+Buffer]; void *
0x1800239a4  call    memset_0
0x1800239a9  mov     [rbp+4B0h+Buffer.dwLength], r15d
0x1800239ad  lea     rcx, [rbp+4B0h+Buffer]; lpBuffer
0x1800239b1  call    cs:__imp_GlobalMemoryStatusEx
0x1800239b7  test    eax, eax
0x1800239b9  jz      short loc_1800239CF
0x1800239bb  mov     r8, [rbp+4B0h+Buffer.ullTotalPhys]
0x1800239bf  lea     rdx, aTotalphysicalm; "TotalPhysicalMemory"
0x1800239c6  mov     rcx, r12
0x1800239c9  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_J@Z; CInstance::SetWBEMINT64(ushort const *,__int64)
0x1800239cf  xor     edx, edx; Val
0x1800239d1  mov     r8d, 0ACh; Size
0x1800239d7  lea     rcx, [rbp+4B0h+TimeZoneInformation]; void *
0x1800239de  call    memset_0
0x1800239e3  lea     rcx, [rbp+4B0h+TimeZoneInformation]; lpTimeZoneInformation
0x1800239ea  call    cs:__imp_GetTimeZoneInformation
0x1800239f0  mov     ebx, eax
0x1800239f2  cmp     eax, 0FFFFFFFFh
0x1800239f5  jz      loc_180023AAA
0x1800239fb  mov     eax, [rbp+4B0h+TimeZoneInformation.Bias]
0x180023a01  lea     r8, [rsp+5B0h+pv]
0x180023a06  lea     rdx, aCurrenttimezon; "CurrentTimeZone"
0x180023a0d  mov     rcx, r12
0x180023a10  cmp     ebx, 2
0x180023a13  jz      loc_180024888
0x180023a19  add     eax, [rbp+4B0h+TimeZoneInformation.StandardBias]
0x180023a1f  mov     [rbp+4B0h+TimeZoneInformation.Bias], eax
0x180023a25  neg     ax
0x180023a28  mov     [rsp+5B0h+pv], ax
0x180023a2d  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x180023a33  test    ebx, ebx
0x180023a35  jnz     loc_1800248CD
0x180023a3b  lea     rcx, [rbp+4B0h+Name]
0x180023a42  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180023a48  nop
0x180023a49  lea     rcx, [rsp+5B0h+var_560]
0x180023a4e  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180023a54  nop
0x180023a55  lea     r9, [rsp+5B0h+var_560]
0x180023a5a  lea     r8, aDisableautoday; "DisableAutoDaylightTimeSet"
0x180023a61  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Tim"...
0x180023a68  lea     rcx, [rbp+4B0h+Name]
0x180023a6f  call    cs:__imp_?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z; CRegistry::OpenLocalMachineKeyAndReadValue(ushort const *,ushort const *,CHString &)
0x180023a75  lea     rdx, aEnabledaylight; "EnableDaylightSavingsTime"
0x180023a7c  mov     rcx, r12
0x180023a7f  test    eax, eax
0x180023a81  jz      loc_1800248FC
0x180023a87  mov     r8b, 1
0x180023a8a  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180023a90  nop
0x180023a91  lea     rcx, [rsp+5B0h+var_560]
0x180023a96  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180023a9c  nop
0x180023a9d  lea     rcx, [rbp+4B0h+Name]
0x180023aa4  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180023aaa  mov     edi, esi
0x180023aac  xorps   xmm0, xmm0
0x180023aaf  movups  [rbp+4B0h+var_488], xmm0
0x180023ab3  movups  [rbp+4B0h+var_478], xmm0
0x180023ab7  movups  [rbp+4B0h+var_468], xmm0
0x180023abb  mov     dword ptr [rbp+4B0h+var_488], 30h ; '0'
0x180023ac2  mov     [rsp+5B0h+phkResult], rsi
0x180023ac7  xor     r9d, r9d
0x180023aca  xor     r8d, r8d
0x180023acd  xor     edx, edx
0x180023acf  xor     ecx, ecx
0x180023ad1  call    cs:__imp_DevObjCreateDeviceInfoList
0x180023ad7  mov     rbx, rax
0x180023ada  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023ade  jnz     loc_180024580
0x180023ae4  mov     r8d, edi
0x180023ae7  lea     rdx, aInfraredsuppor; "InfraredSupported"
0x180023aee  mov     rcx, r12
0x180023af1  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180023af7  lea     rcx, [rbp+4B0h+SystemInfo]; lpSystemInfo
0x180023afb  call    cs:__imp_GetSystemInfo
0x180023b01  lea     rcx, [rsp+5B0h+var_568]
0x180023b06  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180023b0c  nop
0x180023b0d  movzx   ecx, word ptr [rbp+4B0h+SystemInfo]
0x180023b11  test    ecx, ecx
0x180023b13  jnz     loc_1800246D0
0x180023b19  lea     rdx, aX86BasedPc; "X86-based PC"
0x180023b20  lea     rcx, [rsp+5B0h+var_568]
0x180023b25  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180023b2b  xor     edi, edi
0x180023b2d  mov     [rsp+5B0h+ReturnedLength], edi
0x180023b31  lea     r8, [rsp+5B0h+ReturnedLength]; ReturnedLength
0x180023b36  xor     edx, edx; Buffer
0x180023b38  mov     ecx, 3; RelationshipType
0x180023b3d  call    cs:__imp_GetLogicalProcessorInformationEx
0x180023b43  test    eax, eax
0x180023b45  jnz     loc_18002437E
0x180023b4b  call    cs:__imp_GetLastError
0x180023b51  mov     ebx, eax
0x180023b53  cmp     eax, 7Ah ; 'z'
0x180023b56  jnz     loc_180024A51
0x180023b5c  mov     ecx, [rsp+5B0h+ReturnedLength]; Size
0x180023b60  call    cs:__imp_malloc
0x180023b66  mov     rsi, rax
0x180023b69  test    rax, rax
0x180023b6c  jz      loc_180024925
0x180023b72  mov     [rbp+4B0h+var_4E0], rax
0x180023b76  lea     r8, [rsp+5B0h+ReturnedLength]; ReturnedLength
0x180023b7b  mov     rdx, rax; Buffer
0x180023b7e  mov     ecx, 3; RelationshipType
0x180023b83  call    cs:__imp_GetLogicalProcessorInformationEx
0x180023b89  test    eax, eax
0x180023b8b  jz      loc_18002498F
0x180023b91  mov     rdx, rsi
0x180023b94  mov     r9d, edi
0x180023b97  mov     r8d, edi
0x180023b9a  mov     ecx, [rsp+5B0h+ReturnedLength]
0x180023b9e  test    ecx, ecx
0x180023ba0  jnz     loc_1800246A0
0x180023ba6  lea     rdx, aNumberofproces_0; "NumberOfProcessors"
0x180023bad  mov     rcx, r12
0x180023bb0  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180023bb6  mov     ecx, 0FFFFh; GroupNumber
0x180023bbb  call    cs:__imp_GetActiveProcessorCount
0x180023bc1  mov     r8d, eax
0x180023bc4  lea     rdx, aNumberoflogica; "NumberOfLogicalProcessors"
0x180023bcb  mov     rcx, r12
0x180023bce  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180023bd4  lea     r8, [rsp+5B0h+var_568]
0x180023bd9  lea     rdx, aSystemtype; "SystemType"
0x180023be0  mov     rcx, r12
0x180023be3  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180023be9  call    IsGetSystemMetricsPresent
0x180023bee  test    al, al
0x180023bf0  jnz     loc_180024859
0x180023bf6  mov     [rsp+5B0h+pExceptionObject], edi
0x180023bfa  lea     rcx, [rsp+5B0h+pExceptionObject]; this
0x180023bff  call    ?Init@CSMBios@@QEAAHH@Z; CSMBios::Init(int)
0x180023c04  test    eax, eax
0x180023c06  jz      loc_1800241DB
0x180023c0c  mov     [rsp+5B0h+rgIndices], edi
0x180023c10  mov     r9d, edi
0x180023c13  mov     rdx, cs:?m_pSTTree@CSMBios@@0PEAXEA; void * CSMBios::m_pSTTree
0x180023c1a  test    rdx, rdx
  ... truncated ...
```
