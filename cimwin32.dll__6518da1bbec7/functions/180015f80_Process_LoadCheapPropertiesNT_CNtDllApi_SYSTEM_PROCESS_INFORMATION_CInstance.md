# Process::LoadCheapPropertiesNT(CNtDllApi &,_SYSTEM_PROCESS_INFORMATION *,CInstance *)

- ea: `0x180015f80`
- end: `0x1800168f6`
- name: `?LoadCheapPropertiesNT@Process@@QEAAHAEAVCNtDllApi@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAVCInstance@@@Z`
- size: `2422`
- prototype: `int(Process *__hidden this, struct CNtDllApi *, struct _SYSTEM_PROCESS_INFORMATION *, struct CInstance *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015cb0`
- `0x180048cd0`

## callees

- `0x180015f80`
- `0x180016900`
- `0x180016990`
- `0x1800169d0`
- `0x180016bd0`
- `0x180041b84`
- `0x180041cfc`
- `0x1800fc902`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800167de`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800167de`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800160ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800160ca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016499`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180016499`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164b5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180016528`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001655a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180016595`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180016528`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001655a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180016595`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016151`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800160b2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800164c8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180016681`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800160b2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800164c8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180016681`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800165b9`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800166a1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800165b9`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800166a1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180015fd1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016188`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800161bc`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016207`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001623b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001626f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800162a3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800162d7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001630b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001631f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163c2`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163d6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163ea`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163fe`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016642`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016676`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180015fd1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016188`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800161bc`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016207`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001623b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001626f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800162a3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800162d7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001630b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001631f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163c2`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163d6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163ea`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800163fe`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016642`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180016676`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180016049`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180016171`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180016049`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180016171`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800167c0`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800167c0`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800167a4`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800167a4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18001684d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18001684d`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18001681c`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18001683f`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18001681c`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18001683f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800166b4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800166b4`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180016347`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180016347`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180015fee`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016002`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016016`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001602d`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001607c`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016093`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001611d`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800165cc`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001673c`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016753`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016873`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001688a`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800168ad`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800168c4`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180015fee`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016002`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016016`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001602d`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001607c`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016093`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001611d`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800165cc`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001673c`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016753`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180016873`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001688a`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800168ad`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800168c4`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180015fbd`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180015fbd`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180016036`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180016036`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800161d3`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001635b`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001636f`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016386`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001639a`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800163ae`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016415`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001642c`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016443`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001645a`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016471`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016488`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800161d3`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001635b`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001636f`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016386`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001639a`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800163ae`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016415`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001642c`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016443`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18001645a`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016471`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x180016488`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180016334`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180016334`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180016140`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180016140`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x180016808`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x18001682b`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x180016808`
- `framedynos!??YCHString@@QEAAAEBV0@D@Z` at `0x18001682b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166c0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166cc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166e8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166f4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800167cc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800168db`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166c0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166cc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166e8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800166f4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800167cc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800168db`

## string_xrefs

- `0x180015fc7`: `ProcessID`
- `0x1800163cc`: `ParentProcessId`
- `0x18001601c`: `Win32_ComputerSystem`
- `0x180016422`: `WriteOperationCount`
- `0x18001640b`: `ReadOperationCount`
- `0x180016450`: `ReadTransferCount`
- `0x1800163b8`: `ThreadCount`
- `0x180016467`: `WriteTransferCount`
- `0x1800166aa`: `CommandLine`
- `0x1800165c2`: `ExecutablePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Process::LoadCheapPropertiesNT(
        Process *this,
        struct CNtDllApi *a2,
        struct _SYSTEM_PROCESS_INFORMATION *a3,
        struct CInstance *a4)
{
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // r8
  const struct CHString *LocalComputerName; // rax
  __int64 v11; // rcx
  SIZE_T PeakWorkingSetSize; // r8
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  SIZE_T v15; // r8
  SIZE_T QuotaPeakPagedPoolUsage; // r8
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  SIZE_T v19; // r8
  SIZE_T QuotaPagedPoolUsage; // r8
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  SIZE_T v23; // r8
  SIZE_T QuotaPeakNonPagedPoolUsage; // r8
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  SIZE_T v27; // r8
  SIZE_T QuotaNonPagedPoolUsage; // r8
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rax
  SIZE_T v31; // r8
  SIZE_T PagefileUsage; // r8
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rax
  SIZE_T v35; // r8
  SIZE_T PeakPagefileUsage; // r8
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rax
  SIZE_T v39; // r8
  const struct WBEMTime *v40; // rax
  char *v41; // rdi
  __int64 v42; // r15
  __int64 v43; // r14
  const unsigned __int16 *v44; // rax
  unsigned __int64 v45; // r8
  __int64 v46; // r8
  const unsigned __int16 *v47; // rax
  int UniqueProcessId; // eax
  __int64 v50; // rcx
  __int64 KeyName; // rax
  CSystemName *v52; // rcx
  unsigned int v53; // r9d
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // [rsp+30h] [rbp-D0h] BYREF
  char v57[8]; // [rsp+38h] [rbp-C8h] BYREF
  char v58[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-B8h] BYREF
  char v60[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v61[16]; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_CRITICAL_SECTION *v62; // [rsp+68h] [rbp-98h]
  char *v63; // [rsp+70h] [rbp-90h]
  _OWORD v64[3]; // [rsp+78h] [rbp-88h] BYREF
  _LDR_DATA_TABLE_ENTRY v65; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v66; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v67; // [rsp+200h] [rbp+100h]
  __int128 v68; // [rsp+210h] [rbp+110h]
  _OSVERSIONINFOW VersionInformation; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v70[608]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR v71; // [rsp+5A0h] [rbp+4A0h] BYREF
  char v72[526]; // [rsp+5A2h] [rbp+4A2h] BYREF
  unsigned __int16 v73; // [rsp+7B0h] [rbp+6B0h] BYREF
  char v74[526]; // [rsp+7B2h] [rbp+6B2h] BYREF
  unsigned __int16 v75[264]; // [rsp+9C0h] [rbp+8C0h] BYREF
  unsigned __int16 v76[264]; // [rsp+BD0h] [rbp+AD0h] BYREF

  Provider::SetCreationClassName(this, a4);
  CInstance::SetDWORD(a4, L"ProcessID", (unsigned int)a3->UniqueProcessId);
  v8 = a3->ImageName.Buffer;
  if ( v8 )
  {
    CInstance::SetWCHARSplat(a4, L"Name", v8);
    CInstance::SetWCHARSplat(a4, L"Caption", a3->ImageName.Buffer);
    v9 = a3->ImageName.Buffer;
  }
  else
  {
    UniqueProcessId = (int)a3->UniqueProcessId;
    if ( UniqueProcessId )
    {
      if ( UniqueProcessId == 2 || UniqueProcessId == 8 )
      {
        CInstance::SetWCHARSplat(a4, L"Name", L"System");
        CInstance::SetWCHARSplat(a4, L"Caption", L"System");
        v9 = L"System";
      }
      else
      {
        CInstance::SetWCHARSplat(a4, L"Name", L"UNKNOWN");
        CInstance::SetWCHARSplat(a4, L"Caption", L"UNKNOWN");
        v9 = L"UNKNOWN";
      }
    }
    else
    {
      CInstance::SetWCHARSplat(a4, L"Name", L"System Idle Process");
      CInstance::SetWCHARSplat(a4, L"Caption", L"System Idle Process");
      v9 = L"System Idle Process";
    }
  }
  CInstance::SetWCHARSplat(a4, L"Description", v9);
  CInstance::SetWCHARSplat(a4, L"CSCreationClassName", L"Win32_ComputerSystem");
  LocalComputerName = Provider::GetLocalComputerName(this);
  CInstance::SetCHString(a4, L"CSName", LocalComputerName);
  StringCbPrintfW(v75, 0x208u, L"%lu", LODWORD(a3->UniqueProcessId));
  CInstance::SetWCHARSplat(a4, L"Handle", v75);
  CInstance::SetWCHARSplat(a4, L"OSCreationClassName", L"Win32_OperatingSystem");
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  CHString::CHString((CHString *)v61);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) )
  {
    StringCbPrintfW(
      v76,
      0x208u,
      L"%d.%d.%hu",
      VersionInformation.dwMajorVersion,
      VersionInformation.dwMinorVersion,
      LOWORD(VersionInformation.dwBuildNumber));
    CInstance::SetWCHARSplat(a4, L"WindowsVersion", v76);
    v62 = &g_csSystemName;
    EnterCriticalSection(&g_csSystemName);
    if ( CHString::IsEmpty((CHString *)&CSystemName::s_sKeyName) )
    {
      v71 = 0;
      memset_0(v72, 0, 0x206u);
      v73 = 0;
      memset_0(v74, 0, 0x206u);
      CRegistry::CRegistry((CRegistry *)v70);
      KeyName = CSystemName::GetKeyName(v50, &v56);
      CHString::operator=(&CSystemName::s_sKeyName, KeyName);
      CHString::~CHString((CHString *)&v56);
      if ( !GetWindowsDirectoryW(&v71, 0x104u) )
        v71 = 0;
      CSystemName::GetVolumeManagedName(v52, &v71, &v73, v53);
      LOBYTE(v54) = 124;
      CHString::operator+=(&CSystemName::s_sKeyName, v54);
      CHString::operator+=(&CSystemName::s_sKeyName, &v71);
      LOBYTE(v55) = 124;
      CHString::operator+=(&CSystemName::s_sKeyName, v55);
      CHString::operator+=(&CSystemName::s_sKeyName, &v73);
      CRegistry::~CRegistry((CRegistry *)v70);
    }
    LeaveCriticalSection(&g_csSystemName);
    CSystemName::GetLongKeyName(v11, v60);
    CInstance::SetCHString(a4, L"OSName", (const struct CHString *)v60);
    CInstance::SetDWORD(a4, L"PageFaults", a3->PageFaultCount);
    PeakWorkingSetSize = a3->PeakWorkingSetSize;
    v13 = PeakWorkingSetSize + 1023;
    v14 = (PeakWorkingSetSize + 1023) >> 10;
    v15 = PeakWorkingSetSize >> 10;
    if ( v13 >= 0x3FF )
      LODWORD(v15) = v14;
    CInstance::SetDWORD(a4, L"PeakWorkingSetSize", v15);
    CInstance::SetWBEMINT64(a4, L"WorkingSetSize", a3->WorkingSetSize);
    QuotaPeakPagedPoolUsage = a3->QuotaPeakPagedPoolUsage;
    v17 = QuotaPeakPagedPoolUsage + 1023;
    v18 = (QuotaPeakPagedPoolUsage + 1023) >> 10;
    v19 = QuotaPeakPagedPoolUsage >> 10;
    if ( v17 >= 0x3FF )
      LODWORD(v19) = v18;
    CInstance::SetDWORD(a4, L"QuotaPeakPagedPoolUsage", v19);
    QuotaPagedPoolUsage = a3->QuotaPagedPoolUsage;
    v21 = QuotaPagedPoolUsage + 1023;
    v22 = (QuotaPagedPoolUsage + 1023) >> 10;
    v23 = QuotaPagedPoolUsage >> 10;
    if ( v21 >= 0x3FF )
      LODWORD(v23) = v22;
    CInstance::SetDWORD(a4, L"QuotaPagedPoolUsage", v23);
    QuotaPeakNonPagedPoolUsage = a3->QuotaPeakNonPagedPoolUsage;
    v25 = QuotaPeakNonPagedPoolUsage + 1023;
    v26 = (QuotaPeakNonPagedPoolUsage + 1023) >> 10;
    v27 = QuotaPeakNonPagedPoolUsage >> 10;
    if ( v25 >= 0x3FF )
      LODWORD(v27) = v26;
    CInstance::SetDWORD(a4, L"QuotaPeakNonPagedPoolUsage", v27);
    QuotaNonPagedPoolUsage = a3->QuotaNonPagedPoolUsage;
    v29 = QuotaNonPagedPoolUsage + 1023;
    v30 = (QuotaNonPagedPoolUsage + 1023) >> 10;
    v31 = QuotaNonPagedPoolUsage >> 10;
    if ( v29 >= 0x3FF )
      LODWORD(v31) = v30;
    CInstance::SetDWORD(a4, L"QuotaNonPagedPoolUsage", v31);
    PagefileUsage = a3->PagefileUsage;
    v33 = PagefileUsage + 1023;
    v34 = (PagefileUsage + 1023) >> 10;
    v35 = PagefileUsage >> 10;
    if ( v33 >= 0x3FF )
      LODWORD(v35) = v34;
    CInstance::SetDWORD(a4, L"PageFileUsage", v35);
    PeakPagefileUsage = a3->PeakPagefileUsage;
    v37 = PeakPagefileUsage + 1023;
    v38 = (PeakPagefileUsage + 1023) >> 10;
    v39 = PeakPagefileUsage >> 10;
    if ( v37 >= 0x3FF )
      LODWORD(v39) = v38;
    CInstance::SetDWORD(a4, L"PeakPageFileUsage", v39);
    CInstance::SetDWORD(a4, L"Priority", a3->BasePriority);
    if ( a3->CreateTime.HighPart > 0 )
    {
      v40 = WBEMTime::WBEMTime((WBEMTime *)&v56, (const struct _FILETIME *)&a3->CreateTime);
      CInstance::SetDateTime(a4, L"CreationDate", v40);
    }
    CInstance::SetWBEMINT64(a4, L"KernelModeTime", a3->KernelTime.QuadPart);
    CInstance::SetWBEMINT64(a4, L"UserModeTime", a3->UserTime.QuadPart);
    CInstance::SetWBEMINT64(a4, L"PrivatePageCount", a3->PrivatePageCount);
    CInstance::SetWBEMINT64(a4, L"PeakVirtualSize", a3->PeakVirtualSize);
    CInstance::SetWBEMINT64(a4, L"VirtualSize", a3->VirtualSize);
    CInstance::SetDWORD(a4, L"ThreadCount", a3->NumberOfThreads);
    CInstance::SetDWORD(a4, L"ParentProcessId", (unsigned int)a3->InheritedFromUniqueProcessId);
    CInstance::SetDWORD(a4, L"HandleCount", a3->HandleCount);
    CInstance::SetDWORD(a4, L"SessionId", a3->SessionId);
    CInstance::SetWBEMINT64(a4, L"ReadOperationCount", a3->ReadOperationCount.QuadPart);
    CInstance::SetWBEMINT64(a4, L"WriteOperationCount", a3->WriteOperationCount.QuadPart);
    CInstance::SetWBEMINT64(a4, L"OtherOperationCount", a3->OtherOperationCount.QuadPart);
    CInstance::SetWBEMINT64(a4, L"ReadTransferCount", a3->ReadTransferCount.QuadPart);
    CInstance::SetWBEMINT64(a4, L"WriteTransferCount", a3->WriteTransferCount.QuadPart);
    CInstance::SetWBEMINT64(a4, L"OtherTransferCount", a3->OtherTransferCount.QuadPart);
    v41 = (char *)OpenProcess(0x410u, 0, (DWORD)a3->UniqueProcessId);
    v63 = v41;
    if ( (unsigned __int64)(v41 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !GetLastError() )
    {
      CHString::CHString((CHString *)v58);
      memset(v64, 0, sizeof(v64));
      if ( (*((int (__fastcall **)(char *, _QWORD, _OWORD *, __int64, _QWORD))a2 + 16))(v41, 0, v64, 48, 0) >= 0 )
      {
        Buffer = 0;
        if ( ReadProcessMemory(v41, (LPCVOID)(*((_QWORD *)&v64[0] + 1) + 24LL), &Buffer, 8u, 0) )
        {
          v42 = Buffer + 32;
          v56 = 0;
          if ( ReadProcessMemory(v41, (LPCVOID)(Buffer + 32), &v56, 8u, 0) )
          {
            v43 = v56;
            if ( v56 != v42 )
            {
              memset_0(&v65, 0, 0x138u);
              if ( ReadProcessMemory(v41, (LPCVOID)(v43 - 16), &v65, 0x138u, 0) )
              {
                if ( (unsigned int)Process::GetModuleName(v41, &v65, (struct CHString *)v58) )
                {
                  v44 = (const unsigned __int16 *)CHString::operator unsigned short const *(v58);
                  CInstance::SetWCHARSplat(a4, L"ExecutablePath", v44);
                }
              }
            }
          }
        }
      }
      v66 = 0;
      v67 = 0;
      v68 = 0;
      if ( (*((int (__fastcall **)(char *, __int64, __int128 *, __int64, _QWORD))a2 + 16))(v41, 1, &v66, 48, 0) >= 0 )
      {
        v45 = (unsigned __int64)v67 >> 10;
        if ( (unsigned __int64)v67 < 0xFFFFFFFFFFFFFC01uLL )
          LODWORD(v45) = (unsigned __int64)(v67 + 1023) >> 10;
        CInstance::SetDWORD(a4, L"MinimumWorkingSetSize", v45);
        v46 = *((_QWORD *)&v67 + 1) >> 10;
        if ( *((_QWORD *)&v67 + 1) < 0xFFFFFFFFFFFFFC01uLL )
          LODWORD(v46) = (unsigned __int64)(*((_QWORD *)&v67 + 1) + 1023LL) >> 10;
        CInstance::SetDWORD(a4, L"MaximumWorkingSetSize", v46);
      }
      CHString::CHString((CHString *)v57);
      if ( Process::GetProcessParameters(a2, v41, (struct CHString *)v57) )
      {
        v47 = (const unsigned __int16 *)CHString::operator unsigned short const *(v57);
        CInstance::SetCharSplat(a4, L"CommandLine", v47);
      }
      CHString::~CHString((CHString *)v57);
      CHString::~CHString((CHString *)v58);
    }
    if ( v41 != (char *)-1LL )
      CloseHandle(v41);
    CHString::~CHString((CHString *)v60);
    CHString::~CHString((CHString *)v61);
    return 1;
  }
  else
  {
    CHString::~CHString((CHString *)v61);
    return 0;
  }
}

```

## disassembly

```asm
0x180015f80  push    rbp
0x180015f82  push    rbx
0x180015f83  push    rsi
0x180015f84  push    rdi
0x180015f85  push    r12
0x180015f87  push    r14
0x180015f89  push    r15
0x180015f8b  lea     rbp, [rsp-0CF0h]
0x180015f93  sub     rsp, 0DF0h
0x180015f9a  mov     rax, cs:__security_cookie
0x180015fa1  xor     rax, rsp
0x180015fa4  mov     [rbp+0D20h+var_40], rax
0x180015fab  mov     rbx, r9
0x180015fae  mov     rdi, r8
0x180015fb1  mov     rsi, rdx
0x180015fb4  mov     r14, rcx
0x180015fb7  xor     r12d, r12d
0x180015fba  mov     rdx, r9
0x180015fbd  call    cs:__imp_?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z; Provider::SetCreationClassName(CInstance *)
0x180015fc3  mov     r8d, [rdi+50h]
0x180015fc7  lea     rdx, aProcessid_0; "ProcessID"
0x180015fce  mov     rcx, rbx
0x180015fd1  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180015fd7  mov     r8, [rdi+40h]
0x180015fdb  test    r8, r8
0x180015fde  jz      loc_180016720
0x180015fe4  lea     rdx, aName; "Name"
0x180015feb  mov     rcx, rbx
0x180015fee  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180015ff4  mov     r8, [rdi+40h]
0x180015ff8  lea     rdx, aCaption; "Caption"
0x180015fff  mov     rcx, rbx
0x180016002  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180016008  mov     r8, [rdi+40h]
0x18001600c  lea     rdx, aDescription; "Description"
0x180016013  mov     rcx, rbx
0x180016016  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x18001601c  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180016023  lea     rdx, aCscreationclas; "CSCreationClassName"
0x18001602a  mov     rcx, rbx
0x18001602d  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180016033  mov     rcx, r14
0x180016036  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x18001603c  mov     r8, rax
0x18001603f  lea     rdx, aCsname; "CSName"
0x180016046  mov     rcx, rbx
0x180016049  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18001604f  mov     r9d, [rdi+50h]
0x180016053  lea     r8, Format; "%lu"
0x18001605a  mov     edx, 208h; unsigned __int64
0x18001605f  lea     rcx, [rbp+0D20h+var_460]; unsigned __int16 *
0x180016066  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001606b  lea     r8, [rbp+0D20h+var_460]
0x180016072  lea     rdx, aHandle; "Handle"
0x180016079  mov     rcx, rbx
0x18001607c  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180016082  lea     r8, aWin32Operating_0; "Win32_OperatingSystem"
0x180016089  lea     rdx, aOscreationclas; "OSCreationClassName"
0x180016090  mov     rcx, rbx
0x180016093  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180016099  xor     edx, edx; Val
0x18001609b  mov     r8d, 114h; Size
0x1800160a1  lea     rcx, [rbp+0D20h+VersionInformation]; void *
0x1800160a8  call    memset_0
0x1800160ad  lea     rcx, [rsp+0E20h+var_DC8]
0x1800160b2  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800160b8  nop
0x1800160b9  mov     [rbp+0D20h+VersionInformation.dwOSVersionInfoSize], 114h
0x1800160c3  lea     rcx, [rbp+0D20h+VersionInformation]; lpVersionInformation
0x1800160ca  call    cs:__imp_GetVersionExW
0x1800160d0  test    eax, eax
0x1800160d2  jz      loc_1800168D6
0x1800160d8  movzx   eax, word ptr [rbp+0D20h+VersionInformation.dwBuildNumber]
0x1800160df  mov     [rsp+0E20h+var_DF8], eax
0x1800160e3  mov     eax, [rbp+0D20h+VersionInformation.dwMinorVersion]
0x1800160e9  mov     dword ptr [rsp+0E20h+lpNumberOfBytesRead], eax
0x1800160ed  mov     r9d, [rbp+0D20h+VersionInformation.dwMajorVersion]
0x1800160f4  lea     r8, aDDHu; "%d.%d.%hu"
0x1800160fb  mov     edx, 208h; unsigned __int64
0x180016100  lea     rcx, [rbp+0D20h+var_250]; unsigned __int16 *
0x180016107  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001610c  lea     r8, [rbp+0D20h+var_250]
0x180016113  lea     rdx, aWindowsversion; "WindowsVersion"
0x18001611a  mov     rcx, rbx
0x18001611d  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180016123  lea     r14, ?g_csSystemName@@3VCCritSec@@A; CCritSec g_csSystemName
0x18001612a  mov     [rsp+0E20h+var_DB8], r14
0x18001612f  mov     rcx, r14; lpCriticalSection
0x180016132  call    cs:__imp_EnterCriticalSection
0x180016138  nop
0x180016139  lea     rcx, ?s_sKeyName@CSystemName@@1VCHString@@A; CHString CSystemName::s_sKeyName
0x180016140  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x180016146  test    eax, eax
0x180016148  jnz     loc_180016765
0x18001614e  mov     rcx, r14; lpCriticalSection
0x180016151  call    cs:__imp_LeaveCriticalSection
0x180016157  lea     rdx, [rsp+0E20h+var_DD0]
0x18001615c  call    ?GetLongKeyName@CSystemName@@QEAA?AVCHString@@XZ; CSystemName::GetLongKeyName(void)
0x180016161  nop
0x180016162  lea     r8, [rsp+0E20h+var_DD0]
0x180016167  lea     rdx, aOsname; "OSName"
0x18001616e  mov     rcx, rbx
0x180016171  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180016177  mov     r8d, [rdi+80h]
0x18001617e  lea     rdx, aPagefaults; "PageFaults"
0x180016185  mov     rcx, rbx
0x180016188  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001618e  mov     r8, [rdi+88h]
0x180016195  lea     rcx, [r8+3FFh]
0x18001619c  mov     rax, rcx
0x18001619f  shr     rax, 0Ah
0x1800161a3  shr     r8, 0Ah
0x1800161a7  cmp     rcx, 3FFh
0x1800161ae  cmovnb  r8d, eax
0x1800161b2  lea     rdx, aPeakworkingset; "PeakWorkingSetSize"
0x1800161b9  mov     rcx, rbx
0x1800161bc  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800161c2  mov     r8, [rdi+90h]
0x1800161c9  lea     rdx, aWorkingsetsize; "WorkingSetSize"
0x1800161d0  mov     rcx, rbx
0x1800161d3  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x1800161d9  mov     r8, [rdi+98h]
0x1800161e0  lea     rcx, [r8+3FFh]
0x1800161e7  mov     rax, rcx
0x1800161ea  shr     rax, 0Ah
0x1800161ee  shr     r8, 0Ah
0x1800161f2  cmp     rcx, 3FFh
0x1800161f9  cmovnb  r8d, eax
0x1800161fd  lea     rdx, aQuotapeakpaged; "QuotaPeakPagedPoolUsage"
0x180016204  mov     rcx, rbx
0x180016207  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001620d  mov     r8, [rdi+0A0h]
0x180016214  lea     rcx, [r8+3FFh]
0x18001621b  mov     rax, rcx
0x18001621e  shr     rax, 0Ah
0x180016222  shr     r8, 0Ah
0x180016226  cmp     rcx, 3FFh
0x18001622d  cmovnb  r8d, eax
0x180016231  lea     rdx, aQuotapagedpool; "QuotaPagedPoolUsage"
0x180016238  mov     rcx, rbx
0x18001623b  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180016241  mov     r8, [rdi+0A8h]
0x180016248  lea     rcx, [r8+3FFh]
0x18001624f  mov     rax, rcx
0x180016252  shr     rax, 0Ah
0x180016256  shr     r8, 0Ah
0x18001625a  cmp     rcx, 3FFh
0x180016261  cmovnb  r8d, eax
0x180016265  lea     rdx, aQuotapeaknonpa; "QuotaPeakNonPagedPoolUsage"
0x18001626c  mov     rcx, rbx
0x18001626f  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180016275  mov     r8, [rdi+0B0h]
0x18001627c  lea     rcx, [r8+3FFh]
0x180016283  mov     rax, rcx
0x180016286  shr     rax, 0Ah
0x18001628a  shr     r8, 0Ah
0x18001628e  cmp     rcx, 3FFh
0x180016295  cmovnb  r8d, eax
0x180016299  lea     rdx, aQuotanonpagedp; "QuotaNonPagedPoolUsage"
0x1800162a0  mov     rcx, rbx
0x1800162a3  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800162a9  mov     r8, [rdi+0B8h]
0x1800162b0  lea     rcx, [r8+3FFh]
0x1800162b7  mov     rax, rcx
0x1800162ba  shr     rax, 0Ah
0x1800162be  shr     r8, 0Ah
0x1800162c2  cmp     rcx, 3FFh
0x1800162c9  cmovnb  r8d, eax
0x1800162cd  lea     rdx, aPagefileusage; "PageFileUsage"
0x1800162d4  mov     rcx, rbx
0x1800162d7  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800162dd  mov     r8, [rdi+0C0h]
0x1800162e4  lea     rcx, [r8+3FFh]
0x1800162eb  mov     rax, rcx
0x1800162ee  shr     rax, 0Ah
0x1800162f2  shr     r8, 0Ah
0x1800162f6  cmp     rcx, 3FFh
0x1800162fd  cmovnb  r8d, eax
0x180016301  lea     rdx, aPeakpagefileus; "PeakPageFileUsage"
0x180016308  mov     rcx, rbx
0x18001630b  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180016311  mov     r8d, [rdi+48h]
0x180016315  lea     rdx, aPriority; "Priority"
0x18001631c  mov     rcx, rbx
0x18001631f  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180016325  lea     rdx, [rdi+20h]
0x180016329  cmp     dword ptr [rdx+4], 0
0x18001632d  jle     short loc_18001634D
0x18001632f  lea     rcx, [rsp+0E20h+var_DF0]
0x180016334  call    cs:__imp_??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z; WBEMTime::WBEMTime(_FILETIME const &)
0x18001633a  mov     r8, rax
0x18001633d  lea     rdx, aCreationdate; "CreationDate"
0x180016344  mov     rcx, rbx
0x180016347  call    cs:__imp_?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z; CInstance::SetDateTime(ushort const *,WBEMTime const &)
0x18001634d  mov     r8, [rdi+30h]
0x180016351  lea     rdx, aKernelmodetime; "KernelModeTime"
0x180016358  mov     rcx, rbx
0x18001635b  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x180016361  mov     r8, [rdi+28h]
0x180016365  lea     rdx, aUsermodetime; "UserModeTime"
0x18001636c  mov     rcx, rbx
0x18001636f  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x180016375  mov     r8, [rdi+0C8h]
0x18001637c  lea     rdx, aPrivatepagecou; "PrivatePageCount"
0x180016383  mov     rcx, rbx
0x180016386  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x18001638c  mov     r8, [rdi+70h]
0x180016390  lea     rdx, aPeakvirtualsiz; "PeakVirtualSize"
0x180016397  mov     rcx, rbx
0x18001639a  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x1800163a0  mov     r8, [rdi+78h]
0x1800163a4  lea     rdx, aVirtualsize; "VirtualSize"
0x1800163ab  mov     rcx, rbx
0x1800163ae  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x1800163b4  mov     r8d, [rdi+4]
0x1800163b8  lea     rdx, aThreadcount; "ThreadCount"
0x1800163bf  mov     rcx, rbx
0x1800163c2  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800163c8  mov     r8d, [rdi+58h]
0x1800163cc  lea     rdx, aParentprocessi; "ParentProcessId"
0x1800163d3  mov     rcx, rbx
0x1800163d6  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800163dc  mov     r8d, [rdi+60h]
0x1800163e0  lea     rdx, aHandlecount; "HandleCount"
0x1800163e7  mov     rcx, rbx
0x1800163ea  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800163f0  mov     r8d, [rdi+64h]
0x1800163f4  lea     rdx, aSessionid; "SessionId"
0x1800163fb  mov     rcx, rbx
0x1800163fe  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180016404  mov     r8, [rdi+0D0h]
0x18001640b  lea     rdx, aReadoperationc; "ReadOperationCount"
0x180016412  mov     rcx, rbx
0x180016415  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x18001641b  mov     r8, [rdi+0D8h]
0x180016422  lea     rdx, aWriteoperation; "WriteOperationCount"
0x180016429  mov     rcx, rbx
0x18001642c  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x180016432  mov     r8, [rdi+0E0h]
0x180016439  lea     rdx, aOtheroperation; "OtherOperationCount"
0x180016440  mov     rcx, rbx
0x180016443  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x180016449  mov     r8, [rdi+0E8h]
0x180016450  lea     rdx, aReadtransferco; "ReadTransferCount"
0x180016457  mov     rcx, rbx
0x18001645a  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x180016460  mov     r8, [rdi+0F0h]
0x180016467  lea     rdx, aWritetransferc; "WriteTransferCount"
0x18001646e  mov     rcx, rbx
0x180016471  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x180016477  mov     r8, [rdi+0F8h]
0x18001647e  lea     rdx, aOthertransferc; "OtherTransferCount"
0x180016485  mov     rcx, rbx
0x180016488  call    cs:__imp_?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z; CInstance::SetWBEMINT64(ushort const *,unsigned __int64)
0x18001648e  mov     r8d, [rdi+50h]; dwProcessId
0x180016492  xor     edx, edx; bInheritHandle
0x180016494  mov     ecx, 410h; dwDesiredAccess
0x180016499  call    cs:__imp_OpenProcess
0x18001649f  mov     rdi, rax
0x1800164a2  mov     [rsp+0E20h+var_DB0], rax
0x1800164a7  lea     rcx, [rax-1]
0x1800164ab  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800164af  ja      loc_1800166D3
0x1800164b5  call    cs:__imp_GetLastError
0x1800164bb  test    eax, eax
0x1800164bd  jnz     loc_1800166D3
0x1800164c3  lea     rcx, [rsp+0E20h+var_DE0]
0x1800164c8  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800164ce  nop
0x1800164cf  xorps   xmm0, xmm0
0x1800164d2  movups  [rsp+0E20h+var_DA8], xmm0
0x1800164d7  movups  [rbp+0D20h+var_D98], xmm0
0x1800164db  movups  [rbp+0D20h+var_D88], xmm0
0x1800164df  mov     [rsp+0E20h+lpNumberOfBytesRead], r12
0x1800164e4  mov     r9d, 30h ; '0'
0x1800164ea  lea     r8, [rsp+0E20h+var_DA8]
0x1800164ef  xor     edx, edx
0x1800164f1  mov     rcx, rdi
0x1800164f4  mov     rax, [rsi+80h]
0x1800164fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016500  test    eax, eax
0x180016502  js      loc_1800165D2
0x180016508  mov     rdx, qword ptr [rbp+0D20h+var_DA8+8]
0x18001650c  mov     [rsp+0E20h+Buffer], r12
0x180016511  add     rdx, 18h; lpBaseAddress
0x180016515  mov     [rsp+0E20h+lpNumberOfBytesRead], r12; lpNumberOfBytesRead
0x18001651a  mov     r9d, 8; nSize
0x180016520  lea     r8, [rsp+0E20h+Buffer]; lpBuffer
0x180016525  mov     rcx, rdi; hProcess
0x180016528  call    cs:__imp_ReadProcessMemory
0x18001652e  test    eax, eax
0x180016530  jz      loc_1800165D2
0x180016536  mov     r15, [rsp+0E20h+Buffer]
0x18001653b  add     r15, 20h ; ' '
0x18001653f  mov     [rsp+0E20h+var_DF0], r12
0x180016544  mov     [rsp+0E20h+lpNumberOfBytesRead], r12; lpNumberOfBytesRead
0x180016549  mov     r9d, 8; nSize
0x18001654f  lea     r8, [rsp+0E20h+var_DF0]; lpBuffer
0x180016554  mov     rdx, r15; lpBaseAddress
0x180016557  mov     rcx, rdi; hProcess
  ... truncated ...
```
