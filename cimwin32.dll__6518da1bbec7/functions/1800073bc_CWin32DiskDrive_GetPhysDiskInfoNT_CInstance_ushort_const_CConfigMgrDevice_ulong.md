# CWin32DiskDrive::GetPhysDiskInfoNT(CInstance *,ushort const *,CConfigMgrDevice *,ulong)

- ea: `0x1800073bc`
- end: `0x1800082d0`
- name: `?GetPhysDiskInfoNT@CWin32DiskDrive@@AEAAJPEAVCInstance@@PEBGPEAVCConfigMgrDevice@@K@Z`
- size: `3860`
- prototype: `int(CWin32DiskDrive *__hidden this, struct CInstance *, const unsigned __int16 *, struct CConfigMgrDevice *, unsigned int)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800082d8`
- `0x18005f600`

## callees

- `0x180006900`
- `0x1800073bc`
- `0x1800086bc`
- `0x18000876c`
- `0x18000a9f0`
- `0x18000ab30`
- `0x18000cac0`
- `0x1800127e0`
- `0x180013ae0`
- `0x180014c58`
- `0x180020e5c`
- `0x180052b84`
- `0x180056c34`
- `0x18006a880`
- `0x18007a574`
- `0x18008bb9c`
- `0x1800fc8f6`
- `0x1800fc902`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!_itow` at `0x180007521`
- `msvcrt!_itow` at `0x180007521`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008197`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000746e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007af0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000746e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007af0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800074ca`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800075e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007782`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007849`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000792d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007d1d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800074ca`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800075e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007782`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007849`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000792d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007d1d`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x180007ee6`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800081d1`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x180007ee6`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800081d1`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x180007edf`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800081ca`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000767a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18000767a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800074e6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007897`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007949`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18000795d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007971`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007985`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d3b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d51`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d67`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d7d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d9f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800074e6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007897`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007949`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18000795d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007971`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007985`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d3b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d51`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d67`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d7d`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180007d9f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18000741c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007548`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18000755d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007572`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007587`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800076e0`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800076f5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18000773b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007c86`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007cba`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007ccf`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18000741c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007548`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18000755d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007572`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007587`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800076e0`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800076f5`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18000773b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007c86`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007cba`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180007ccf`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800078bc`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800078bc`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180007533`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180007533`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180007433`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18000744a`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180007b79`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180008063`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180007433`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18000744a`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180007b79`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180008063`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180007400`
- `framedynos!?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z` at `0x180007400`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180007409`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180007409`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18000799c`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800079b6`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800079d0`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800079e8`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x18000799c`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800079b6`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800079d0`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800079e8`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800074f8`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800074f8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180007ea2`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180007ea2`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180007b8d`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180007ba9`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180007b8d`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180007ba9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x180007619`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x180007645`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x180007619`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x180007645`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180007593`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180007795`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180007593`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180007795`
- `OLEAUT32!__imp_SysAllocString` at `0x180007aa4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007f6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180008025`
- `OLEAUT32!__imp_SysAllocString` at `0x180008138`
- `OLEAUT32!__imp_SysAllocString` at `0x180007aa4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007f6f`
- `OLEAUT32!__imp_SysAllocString` at `0x180008025`
- `OLEAUT32!__imp_SysAllocString` at `0x180008138`
- `OLEAUT32!__imp_VariantInit` at `0x1800079fb`
- `OLEAUT32!__imp_VariantInit` at `0x180007a06`
- `OLEAUT32!__imp_VariantInit` at `0x1800079fb`
- `OLEAUT32!__imp_VariantInit` at `0x180007a06`
- `OLEAUT32!__imp_VariantClear` at `0x180007bdc`
- `OLEAUT32!__imp_VariantClear` at `0x180007bee`
- `OLEAUT32!__imp_VariantClear` at `0x180007bdc`
- `OLEAUT32!__imp_VariantClear` at `0x180007bee`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007a1b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007a2f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007a1b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007a2f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007a4e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007b20`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007f3c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007ff2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000804c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800080dd`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800080ee`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000810e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008287`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007b20`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007f3c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007ff2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000804c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800080dd`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800080ee`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000810e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180008287`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007efe`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007f14`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007fb4`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007fca`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007efe`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007f14`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007fb4`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180007fca`

## string_xrefs

- `0x180007a9d`: `Random Access`
- `0x180007422`: `Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CWin32DiskDrive::GetPhysDiskInfoNT(
        CWin32DiskDrive *this,
        struct CInstance *a2,
        const unsigned __int16 *a3,
        struct CConfigMgrDevice *a4,
        unsigned int a5)
{
  const struct CHString *LocalComputerName; // rax
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  DWORD v12; // r13d
  unsigned int *v13; // rdi
  DWORD v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // r15d
  CWin32DiskDrive *v18; // rcx
  unsigned int v19; // edi
  DWORD v20; // r13d
  _DWORD *v21; // rdi
  unsigned int v22; // r13d
  __int64 v23; // r15
  bool v24; // r8
  __int64 v25; // rdi
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // rdi
  SAFEARRAY *v28; // rax
  SAFEARRAY *v29; // r12
  void **v30; // rax
  void **v31; // rdi
  BSTR v32; // rax
  CWin32DiskDrive *v33; // rcx
  const unsigned __int16 *v34; // r8
  HRESULT v35; // eax
  HRESULT v36; // eax
  CRefPtrLite *v38; // rdi
  int Parent; // eax
  volatile signed __int32 *v40; // rsi
  CRefPtrLite *v41; // rcx
  __int64 v42; // rcx
  const unsigned __int16 *v43; // r8
  void **v44; // rax
  void **v45; // rsi
  BSTR v46; // rax
  void **v47; // rax
  void **v48; // rsi
  BSTR v49; // rax
  void **v50; // rax
  void **v51; // rdi
  BSTR v52; // rax
  DWORD v53; // eax
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  LONG rgIndices; // [rsp+44h] [rbp-BCh] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v60[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v61; // [rsp+60h] [rbp-A0h]
  unsigned int v62; // [rsp+64h] [rbp-9Ch]
  DWORD v63[2]; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpOutBuffer; // [rsp+70h] [rbp-90h] BYREF
  DWORD v65[2]; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  CRefPtrLite *v67; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v68; // [rsp+A0h] [rbp-60h]
  struct CConfigMgrDevice *v69; // [rsp+A8h] [rbp-58h]
  char v70[8]; // [rsp+B0h] [rbp-50h] BYREF
  void (__fastcall *v71)(__int64); // [rsp+B8h] [rbp-48h]
  __int64 v72; // [rsp+C0h] [rbp-40h]
  VARIANTARG v73; // [rsp+C8h] [rbp-38h] BYREF
  char v74; // [rsp+E0h] [rbp-20h]
  void (__fastcall *v75)(void *); // [rsp+E8h] [rbp-18h]
  LPVOID *p_lpOutBuffer; // [rsp+F0h] [rbp-10h]
  void **OutBuffer; // [rsp+F8h] [rbp-8h] BYREF
  int v78; // [rsp+100h] [rbp+0h]
  void **InBuffer; // [rsp+108h] [rbp+8h] BYREF
  int v80; // [rsp+110h] [rbp+10h]
  __int128 v81; // [rsp+118h] [rbp+18h] BYREF
  __int64 v82; // [rsp+128h] [rbp+28h]
  _DWORD v83[132]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t Buffer[32]; // [rsp+340h] [rbp+240h] BYREF

  *(_QWORD *)v65 = a3;
  v61 = 0;
  Provider::SetCreationClassName(this, a2);
  LocalComputerName = Provider::GetLocalComputerName(this);
  CInstance::SetCHString(a2, L"SystemName", LocalComputerName);
  CInstance::SetWCHARSplat(a2, L"SystemCreationClassName", L"Win32_ComputerSystem");
  CInstance::SetWCHARSplat(a2, L"Status", L"OK");
  FileW = CreateFileW(a3, 0x80000000, 3u, 0, 3u, 0, 0);
  v68 = FileW;
  LastError = GetLastError();
  v12 = LastError;
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_2;
  if ( LastError == 5 )
  {
    FileW = CreateFileW(a3, 0, 3u, 0, 3u, 0, 0);
    v68 = FileW;
    v12 = GetLastError();
  }
  if ( FileW != (HANDLE)-1LL )
  {
LABEL_2:
    BytesReturned = 0;
    OutBuffer = 0;
    v78 = 0;
    if ( DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
    {
      CInstance::SetDWORD(a2, L"Index", HIDWORD(OutBuffer));
      CHString::CHString((CHString *)&rgsabound, L"\\\\.\\PHYSICALDRIVE");
      memset_0(Buffer, 0, sizeof(Buffer));
      _itow(SHIDWORD(OutBuffer), Buffer, 10);
      CHString::operator+=(&rgsabound, Buffer);
      CInstance::SetCHString(a2, L"DeviceID", (const struct CHString *)&rgsabound);
      CInstance::SetCHString(a2, L"Caption", (const struct CHString *)&rgsabound);
      CInstance::SetCHString(a2, L"Name", (const struct CHString *)&rgsabound);
      CInstance::SetCHString(a2, L"Description", (const struct CHString *)&rgsabound);
      CHString::~CHString((CHString *)&rgsabound);
    }
    InBuffer = 0;
    v80 = 0;
    v13 = (unsigned int *)operator new(0x828u);
    if ( v13 )
    {
      if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, v13, 0x826u, &BytesReturned, 0) )
      {
        v14 = BytesReturned;
        if ( BytesReturned )
        {
          v15 = v13[5];
          if ( (unsigned int)(v15 - 1) <= 0xFFFFFFFD && *((_BYTE *)v13 + v15) )
          {
            CInstance::SetCHString(a2, L"FirmwareRevision", (const char *)v13 + v15);
            v14 = BytesReturned;
          }
          if ( v14 )
          {
            v16 = v13[6];
            if ( (unsigned int)(v16 - 1) <= 0xFFFFFFFD )
            {
              if ( *((_BYTE *)v13 + v16) )
                CInstance::SetCHString(a2, L"SerialNumber", (const char *)v13 + v16);
            }
          }
        }
      }
      operator delete(v13);
    }
  }
  LODWORD(pExceptionObject) = 0;
  v17 = a5;
  if ( FileW != (HANDLE)-1LL && (a5 & 0x3C360181) != 0 )
  {
    CHString::CHString((CHString *)v60);
    if ( (a5 & 0x200000) != 0 )
      CWin32DiskDrive::SetInterfaceType(v18, a2, a4);
    if ( (a5 & 0x20000) != 0 )
    {
      v67 = 0;
      v38 = a4;
      v69 = a4;
      if ( a4 )
        _InterlockedIncrement((volatile signed __int32 *)a4 + 2);
      while ( 1 )
      {
        if ( !v38 )
          goto LABEL_139;
        Parent = CConfigMgrDevice::GetParent(v38, &v67);
        v40 = (volatile signed __int32 *)v67;
        if ( !Parent )
          goto LABEL_97;
        if ( !v67 )
LABEL_139:
          _com_issue_error(-2147467261);
        if ( !memcmp_0(&GUID_DEVCLASS_USB, (char *)v67 + 72, 0x10u) )
          break;
        if ( v38 != (CRefPtrLite *)v40 )
        {
          v41 = v38;
          v38 = (CRefPtrLite *)v40;
          v69 = (struct CConfigMgrDevice *)v40;
          if ( v40 )
            _InterlockedIncrement(v40 + 2);
          CRefPtrLite::Release(v41);
        }
      }
      LODWORD(pExceptionObject) = 1;
LABEL_97:
      CRefPtrLite::Release(v38);
      if ( v40 )
        CRefPtrLite::Release((CRefPtrLite *)v40);
    }
    if ( (a5 & 0x38000000) != 0 )
      SetConfigMgrProperties(a4, a2);
    if ( (a5 & 0x100100) != 0 && (unsigned int)CConfigMgrDevice::GetStringProperty(a4, 1u, (struct CHString *)v60) )
    {
      CInstance::SetCHString(a2, L"Description", (const struct CHString *)v60);
      CInstance::SetCHString(a2, L"Caption", (const struct CHString *)v60);
    }
    if ( (a5 & 0x101) != 0 && (unsigned int)CConfigMgrDevice::GetStringProperty(a4, 0xDu, (struct CHString *)v60) )
    {
      CInstance::SetCHString(a2, L"Caption", (const struct CHString *)v60);
      CInstance::SetCHString(a2, L"Model", (const struct CHString *)v60);
    }
    if ( (a5 & 0x4000000) != 0 && (unsigned int)CConfigMgrDevice::GetStringProperty(a4, 0xCu, (struct CHString *)v60) )
      CInstance::SetCHString(a2, L"Manufacturer", (const struct CHString *)v60);
    if ( (a5 & 0x80u) != 0 )
    {
      if ( (unsigned int)CConfigMgrDevice::GetStatus(a4, (struct CHString *)v60) )
      {
        CInstance::SetCHString(a2, L"Status", (const struct CHString *)v60);
        memset_0(v83, 0, 0x204u);
        v63[0] = 0;
        if ( DeviceIoControl(FileW, 0x2D1100u, 0, 0, v83, 0x204u, v63, 0) )
        {
          v43 = L"OK";
          if ( v83[0] )
            v43 = L"Pred Fail";
          CInstance::SetCHString(a2, L"Status", v43);
        }
      }
    }
    CHString::~CHString((CHString *)v60);
  }
  v19 = 0;
  v62 = 0;
  if ( FileW == (HANDLE)-1LL && v12 != 5 )
  {
    if ( v12 == 2 )
      v19 = -2147217406;
    goto LABEL_75;
  }
  if ( (a5 & 0x40040002) == 0 || FileW == (HANDLE)-1LL )
    goto LABEL_50;
  v20 = 4288;
  lpOutBuffer = operator new(0x10C0u);
  v74 = 0;
  v75 = deleteArray<unsigned long>;
  p_lpOutBuffer = &lpOutBuffer;
  v61 = 1;
  v21 = lpOutBuffer;
  BytesReturned = 4288;
  while ( 1 )
  {
    if ( !v21 )
    {
      LODWORD(pExceptionObject) = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    v63[0] = 0;
    if ( DeviceIoControl(FileW, 0x70050u, 0, 0, v21, v20, v63, 0) )
    {
      if ( (a5 & 2) == 0 )
        goto LABEL_45;
      v22 = 0;
      if ( !v21[1] )
        goto LABEL_44;
      v23 = 0;
      while ( 1 )
      {
        if ( *v21 )
        {
          if ( *v21 == 1 )
          {
            v42 = 36 * v23;
LABEL_105:
            if ( memcmp_0(&v21[v42 + 20], &PARTITION_MSFT_RESERVED_GUID, 0x10u) )
              ++v22;
          }
        }
        else
        {
          v42 = 36 * v23;
          if ( BYTE2(v21[36 * v23 + 20]) )
            goto LABEL_105;
        }
        v23 = (unsigned int)(v23 + 1);
        if ( (unsigned int)v23 >= v21[1] )
        {
          v17 = a5;
LABEL_44:
          CInstance::SetDWORD(a2, L"Partitions", v22);
LABEL_45:
          if ( (v17 & 0x40000000) != 0 && !*v21 )
            CInstance::SetDWORD(a2, L"Signature", v21[2]);
          if ( (v17 & 0x40000) != 0 )
          {
            v24 = 1;
            goto LABEL_48;
          }
          goto LABEL_49;
        }
      }
    }
    v53 = GetLastError();
    if ( v53 != 122 && v53 != 234 )
      break;
    if ( lpOutBuffer )
    {
      operator delete(lpOutBuffer);
      lpOutBuffer = 0;
    }
    SafeInt<unsigned long>::operator+=<unsigned long>(&BytesReturned, 4096);
    v20 = BytesReturned;
    v21 = operator new(BytesReturned);
    lpOutBuffer = v21;
  }
  LODWORD(hTemplateFile) = GetLastError();
  ProviderLog::LocalLogMessage(
    captainsLog,
    L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\diskdrive.cpp",
    882,
    1,
    L"Failed to IOCTL_DISK_GET_DRIVE_LAYOUT_EX device %s (%d)",
    *(_QWORD *)v65,
    hTemplateFile);
  if ( (a5 & 0x40000) != 0 )
  {
    v24 = 0;
LABEL_48:
    CInstance::Setbool(a2, L"MediaLoaded", v24);
  }
LABEL_49:
  v61 = 0;
  deleteArray<unsigned long>(lpOutBuffer);
LABEL_50:
  if ( (v17 & 0xBFE00) == 0 || FileW == (HANDLE)-1LL )
    goto LABEL_73;
  v65[0] = 0;
  v81 = 0;
  v82 = 0;
  if ( !DeviceIoControl(FileW, 0x70000u, 0, 0, &v81, 0x18u, v65, 0) )
  {
    dwFlagsAndAttributes[0] = GetLastError();
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\diskdrive.cpp",
      1128,
      2,
      L"Failed to GetDriveGeometry: %d",
      *(_QWORD *)dwFlagsAndAttributes);
    goto LABEL_73;
  }
  CInstance::SetDWORD(a2, L"TotalHeads", HIDWORD(v81));
  CInstance::SetDWORD(a2, L"TracksPerCylinder", HIDWORD(v81));
  CInstance::SetDWORD(a2, L"SectorsPerTrack", v82);
  CInstance::SetDWORD(a2, L"BytesPerSector", HIDWORD(v82));
  v25 = v81;
  CInstance::SetWBEMINT64(a2, L"TotalCylinders", v81);
  v26 = v25 * HIDWORD(v81);
  CInstance::SetWBEMINT64(a2, L"TotalTracks", v26);
  v27 = v26 * (unsigned int)v82;
  CInstance::SetWBEMINT64(a2, L"TotalSectors", v27);
  CInstance::SetWBEMINT64(a2, L"Size", v27 * HIDWORD(v82));
  rgsabound = (SAFEARRAYBOUND)2LL;
  VariantInit(&pvarg);
  VariantInit(&v73);
  pvarg.llVal = (LONGLONG)SafeArrayCreate(2u, 1u, &rgsabound);
  v28 = SafeArrayCreate(8u, 1u, &rgsabound);
  v29 = v28;
  if ( !pvarg.llVal || !v28 )
  {
    LODWORD(pExceptionObject) = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  MakeGuard<void (*)(void *),void *>(v70, SafeArrayDestroy, v28);
  pvarg.vt = 8194;
  v73.vt = 8200;
  BytesReturned = 3;
  rgIndices = 0;
  v30 = (void **)operator new(0x18u);
  v31 = v30;
  OutBuffer = v30;
  if ( v30 )
  {
    v30[1] = 0;
    *((_DWORD *)v30 + 4) = 1;
    v32 = SysAllocString(L"Random Access");
    *v31 = v32;
    if ( !v32 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v31 = 0;
  }
  OutBuffer = v31;
  if ( !v31 )
    _com_issue_error(-2147024882);
  SafeArrayPutElement(pvarg.parray, &rgIndices, &BytesReturned);
  SafeArrayPutElement(v29, &rgIndices, *v31);
  BytesReturned = 4;
  rgIndices = 1;
  SafeArrayPutElement(pvarg.parray, &rgIndices, &BytesReturned);
  v50 = (void **)operator new(0x18u);
  v51 = v50;
  InBuffer = v50;
  if ( v50 )
  {
    v50[1] = 0;
    *((_DWORD *)v50 + 4) = 1;
    v52 = SysAllocString(L"Supports Writing");
    *v51 = v52;
    if ( !v52 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v51 = 0;
  }
  InBuffer = v51;
  if ( !v51 )
    _com_issue_error(-2147024882);
  SafeArrayPutElement(v29, &rgIndices, *v51);
  v63[0] = 0;
  CWin32DiskDrive::SupportsSMARTNotification(v33, FileW, (int *)v63);
  if ( v63[0] )
  {
    ++rgsabound.cElements;
    if ( SafeArrayRedim(pvarg.parray, &rgsabound) == -2147024882 )
    {
      LODWORD(pExceptionObject) = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    if ( SafeArrayRedim(v29, &rgsabound) == -2147024882 )
    {
      LODWORD(pExceptionObject) = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    ++rgIndices;
    BytesReturned = 10;
    SafeArrayPutElement(pvarg.parray, &rgIndices, &BytesReturned);
    v44 = (void **)operator new(0x18u);
    v45 = v44;
    *(_QWORD *)v63 = v44;
    if ( v44 )
    {
      v44[1] = 0;
      *((_DWORD *)v44 + 4) = 1;
      v46 = SysAllocString(L"SMART Notification");
      *v45 = v46;
      if ( !v46 )
        _com_issue_error(-2147024882);
    }
    else
    {
      v45 = 0;
    }
    *(_QWORD *)v63 = v45;
    if ( v45 )
    {
      SafeArrayPutElement(v29, &rgIndices, *v45);
      _bstr_t::_Free((_bstr_t *)v63);
      goto LABEL_64;
    }
    goto LABEL_116;
  }
LABEL_64:
  if ( DWORD2(v81) == 11 )
  {
    ++rgsabound.cElements;
    if ( SafeArrayRedim(pvarg.parray, &rgsabound) == -2147024882 )
    {
      LODWORD(pExceptionObject) = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    if ( SafeArrayRedim(v29, &rgsabound) == -2147024882 )
    {
      LODWORD(pExceptionObject) = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    ++rgIndices;
    BytesReturned = 7;
    SafeArrayPutElement(pvarg.parray, &rgIndices, &BytesReturned);
    v47 = (void **)operator new(0x18u);
    v48 = v47;
    pExceptionObject = v47;
    if ( v47 )
    {
      v47[1] = 0;
      *((_DWORD *)v47 + 4) = 1;
      v49 = SysAllocString(L"Supports Removable Media");
      *v48 = v49;
      if ( !v49 )
        _com_issue_error(-2147024882);
    }
    else
    {
      v48 = 0;
    }
    pExceptionObject = v48;
    if ( v48 )
    {
      SafeArrayPutElement(v29, &rgIndices, *v48);
      CInstance::SetWCHARSplat(a2, L"MediaType", L"Removable Media");
      _bstr_t::_Free((_bstr_t *)&pExceptionObject);
      goto LABEL_69;
    }
LABEL_116:
    _com_issue_error(-2147024882);
  }
  if ( DWORD2(v81) == 12 )
  {
    v34 = L"External hard disk media";
    if ( !(_DWORD)pExceptionObject )
      v34 = L"Fixed hard disk media";
  }
  else
  {
    v34 = L"Format is unknown";
  }
  CInstance::SetWCHARSplat(a2, L"MediaType", v34);
LABEL_69:
  CInstance::SetVariant(a2, L"Capabilities", &pvarg);
  v73.llVal = (LONGLONG)v29;
  v70[0] = 1;
  CInstance::SetVariant(a2, L"CapabilityDescriptions", &v73);
  _bstr_t::_Free((_bstr_t *)&InBuffer);
  _bstr_t::_Free((_bstr_t *)&OutBuffer);
  if ( !v70[0] )
    v71(v72);
  v35 = VariantClear(&v73);
  if ( v35 < 0 )
    _com_issue_error(v35);
  v36 = VariantClear(&pvarg);
  if ( v36 < 0 )
    _com_issue_error(v36);
LABEL_73:
  if ( (v17 & 0x7D00000) != 0 && FileW != (HANDLE)-1LL )
  {
    v65[0] = 0;
    rgsabound = 0;
    if ( DeviceIoControl(FileW, 0x41018u, 0, 0, &rgsabound, 8u, v65, 0) )
    {
      CInstance::SetDWORD(a2, L"SCSIPort", LOBYTE(rgsabound.lLbound));
      CInstance::SetDWORD(a2, L"SCSIBus", BYTE1(rgsabound.lLbound));
      CInstance::SetDWORD(a2, L"SCSITargetID", BYTE2(rgsabound.lLbound));
      CInstance::SetDWORD(a2, L"SCSILogicalUnit", HIBYTE(rgsabound.lLbound));
    }
  }
  v19 = v62;
LABEL_75:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return v19;
}

```

## disassembly

```asm
0x1800073bc  push    rbp
0x1800073be  push    rbx
0x1800073bf  push    rsi
0x1800073c0  push    rdi
0x1800073c1  push    r12
0x1800073c3  push    r13
0x1800073c5  push    r14
0x1800073c7  push    r15
0x1800073c9  lea     rbp, [rsp-298h]
0x1800073d1  sub     rsp, 398h
0x1800073d8  mov     rax, cs:__security_cookie
0x1800073df  xor     rax, rsp
0x1800073e2  mov     [rbp+2D0h+var_50], rax
0x1800073e9  mov     r12, r9
0x1800073ec  mov     rdi, r8
0x1800073ef  mov     qword ptr [rsp+3D0h+var_358], r8
0x1800073f4  mov     r14, rdx
0x1800073f7  mov     rbx, rcx
0x1800073fa  xor     esi, esi
0x1800073fc  mov     [rsp+3D0h+var_370], esi
0x180007400  call    cs:__imp_?SetCreationClassName@Provider@@IEAA_NPEAVCInstance@@@Z; Provider::SetCreationClassName(CInstance *)
0x180007406  mov     rcx, rbx
0x180007409  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x18000740f  mov     r8, rax
0x180007412  lea     rdx, aSystemname; "SystemName"
0x180007419  mov     rcx, r14
0x18000741c  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180007422  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180007429  lea     rdx, aSystemcreation; "SystemCreationClassName"
0x180007430  mov     rcx, r14
0x180007433  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180007439  lea     r8, aOk; "OK"
0x180007440  lea     rdx, aStatus; "Status"
0x180007447  mov     rcx, r14
0x18000744a  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180007450  mov     [rsp+3D0h+hTemplateFile], rsi; hTemplateFile
0x180007455  mov     [rsp+3D0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180007459  lea     eax, [rsi+3]
0x18000745c  mov     [rsp+3D0h+dwCreationDisposition], eax; dwCreationDisposition
0x180007460  xor     r9d, r9d; lpSecurityAttributes
0x180007463  mov     r8d, eax; dwShareMode
0x180007466  mov     edx, 80000000h; dwDesiredAccess
0x18000746b  mov     rcx, rdi; lpFileName
0x18000746e  call    cs:__imp_CreateFileW
0x180007474  mov     rbx, rax
0x180007477  mov     [rbp+2D0h+var_330], rax
0x18000747b  call    cs:__imp_GetLastError
0x180007481  mov     r13d, eax
0x180007484  lea     r15d, [rsi+0Ch]
0x180007488  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000748c  jz      loc_180007ACE
0x180007492  mov     [rsp+3D0h+BytesReturned], esi
0x180007496  xor     eax, eax
0x180007498  mov     [rbp+2D0h+OutBuffer], rax
0x18000749c  mov     [rbp+2D0h+var_2D0], eax
0x18000749f  mov     [rsp+3D0h+lpOverlapped], rsi; lpOverlapped
0x1800074a4  lea     rax, [rsp+3D0h+BytesReturned]
0x1800074a9  mov     [rsp+3D0h+hTemplateFile], rax; lpBytesReturned
0x1800074ae  mov     [rsp+3D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1800074b3  lea     rax, [rbp+2D0h+OutBuffer]
0x1800074b7  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rax; lpOutBuffer
0x1800074bc  xor     r9d, r9d; nInBufferSize
0x1800074bf  xor     r8d, r8d; lpInBuffer
0x1800074c2  mov     edx, 2D1080h; dwIoControlCode
0x1800074c7  mov     rcx, rbx; hDevice
0x1800074ca  call    cs:__imp_DeviceIoControl
0x1800074d0  test    eax, eax
0x1800074d2  jz      loc_180007599
0x1800074d8  mov     r8d, dword ptr [rbp+2D0h+OutBuffer+4]
0x1800074dc  lea     rdx, aIndex; "Index"
0x1800074e3  mov     rcx, r14
0x1800074e6  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800074ec  lea     rdx, aPhysicaldrive; "\\\\.\\PHYSICALDRIVE"
0x1800074f3  lea     rcx, [rsp+3D0h+rgsabound]
0x1800074f8  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800074fe  nop
0x1800074ff  xor     edx, edx; Val
0x180007501  lea     r8d, [rdx+40h]; Size
0x180007505  lea     rcx, [rbp+2D0h+Buffer]; void *
0x18000750c  call    memset_0
0x180007511  mov     r8d, 0Ah; Radix
0x180007517  lea     rdx, [rbp+2D0h+Buffer]; Buffer
0x18000751e  mov     ecx, dword ptr [rbp+2D0h+OutBuffer+4]; Value
0x180007521  call    cs:__imp__itow
0x180007527  lea     rdx, [rbp+2D0h+Buffer]
0x18000752e  lea     rcx, [rsp+3D0h+rgsabound]
0x180007533  call    cs:__imp_??YCHString@@QEAAAEBV0@PEBG@Z; CHString::operator+=(ushort const *)
0x180007539  lea     r8, [rsp+3D0h+rgsabound]
0x18000753e  lea     rdx, aDeviceid; "DeviceID"
0x180007545  mov     rcx, r14
0x180007548  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18000754e  lea     r8, [rsp+3D0h+rgsabound]
0x180007553  lea     rdx, aCaption; "Caption"
0x18000755a  mov     rcx, r14
0x18000755d  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180007563  lea     r8, [rsp+3D0h+rgsabound]
0x180007568  lea     rdx, aName; "Name"
0x18000756f  mov     rcx, r14
0x180007572  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180007578  lea     r8, [rsp+3D0h+rgsabound]
0x18000757d  lea     rdx, aDescription; "Description"
0x180007584  mov     rcx, r14
0x180007587  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18000758d  nop
0x18000758e  lea     rcx, [rsp+3D0h+rgsabound]
0x180007593  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180007599  xor     eax, eax
0x18000759b  mov     [rbp+2D0h+InBuffer], rax
0x18000759f  mov     [rbp+2D0h+var_2C0], eax
0x1800075a2  mov     ecx, 828h; unsigned __int64
0x1800075a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800075ac  mov     rdi, rax
0x1800075af  test    rax, rax
0x1800075b2  jz      loc_180007653
0x1800075b8  mov     [rsp+3D0h+lpOverlapped], rsi; lpOverlapped
0x1800075bd  lea     rax, [rsp+3D0h+BytesReturned]
0x1800075c2  mov     [rsp+3D0h+hTemplateFile], rax; lpBytesReturned
0x1800075c7  mov     [rsp+3D0h+dwFlagsAndAttributes], 826h; nOutBufferSize
0x1800075cf  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rdi; lpOutBuffer
0x1800075d4  mov     r9d, r15d; nInBufferSize
0x1800075d7  lea     r8, [rbp+2D0h+InBuffer]; lpInBuffer
0x1800075db  mov     edx, 2D1400h; dwIoControlCode
0x1800075e0  mov     rcx, rbx; hDevice
0x1800075e3  call    cs:__imp_DeviceIoControl
0x1800075e9  test    eax, eax
0x1800075eb  jz      short loc_18000764B
0x1800075ed  mov     ecx, [rsp+3D0h+BytesReturned]
0x1800075f1  test    ecx, ecx
0x1800075f3  jz      short loc_18000764B
0x1800075f5  mov     edx, [rdi+14h]
0x1800075f8  lea     eax, [rdx-1]
0x1800075fb  mov     r15d, 0FFFFFFFDh
0x180007601  cmp     eax, r15d
0x180007604  ja      short loc_180007623
0x180007606  lea     r8, [rdi+rdx]
0x18000760a  cmp     [r8], sil
0x18000760d  jz      short loc_180007623
0x18000760f  lea     rdx, aFirmwarerevisi; "FirmwareRevision"
0x180007616  mov     rcx, r14
0x180007619  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z; CInstance::SetCHString(ushort const *,char const *)
0x18000761f  mov     ecx, [rsp+3D0h+BytesReturned]
0x180007623  test    ecx, ecx
0x180007625  jz      short loc_18000764B
0x180007627  mov     ecx, [rdi+18h]
0x18000762a  lea     eax, [rcx-1]
0x18000762d  cmp     eax, r15d
0x180007630  ja      short loc_18000764B
0x180007632  lea     r8, [rdi+rcx]
0x180007636  cmp     [r8], sil
0x180007639  jz      short loc_18000764B
0x18000763b  lea     rdx, aSerialnumber; "SerialNumber"
0x180007642  mov     rcx, r14
0x180007645  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z; CInstance::SetCHString(ushort const *,char const *)
0x18000764b  mov     rcx, rdi; void *
0x18000764e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007653  mov     dword ptr [rsp+3D0h+pExceptionObject], esi
0x180007657  mov     r15d, [rbp+2D0h+arg_20]
0x18000765e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180007662  jz      loc_18000779B
0x180007668  test    r15d, 3C360181h
0x18000766f  jz      loc_18000779B
0x180007675  lea     rcx, [rsp+3D0h+var_378]
0x18000767a  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180007680  nop
0x180007681  bt      r15d, 15h
0x180007686  jnb     short loc_180007693
0x180007688  mov     r8, r12; struct CConfigMgrDevice *
0x18000768b  mov     rdx, r14; struct CInstance *
0x18000768e  call    ?SetInterfaceType@CWin32DiskDrive@@AEAAXPEAVCInstance@@PEAVCConfigMgrDevice@@@Z; CWin32DiskDrive::SetInterfaceType(CInstance *,CConfigMgrDevice *)
0x180007693  bt      r15d, 11h
0x180007698  jb      loc_180007DAA
0x18000769e  test    r15d, 38000000h
0x1800076a5  jz      short loc_1800076B2
0x1800076a7  mov     rdx, r14; struct CInstance *
0x1800076aa  mov     rcx, r12; this
0x1800076ad  call    ?SetConfigMgrProperties@@YAXPEAVCConfigMgrDevice@@PEAVCInstance@@@Z; SetConfigMgrProperties(CConfigMgrDevice *,CInstance *)
0x1800076b2  test    r15d, 100100h
0x1800076b9  jz      short loc_1800076FB
0x1800076bb  lea     r8, [rsp+3D0h+var_378]; struct CHString *
0x1800076c0  mov     edx, 1; unsigned int
0x1800076c5  mov     rcx, r12; this
0x1800076c8  call    ?GetStringProperty@CConfigMgrDevice@@QEAAHKAEAVCHString@@@Z; CConfigMgrDevice::GetStringProperty(ulong,CHString &)
0x1800076cd  test    eax, eax
0x1800076cf  jz      short loc_1800076FB
0x1800076d1  lea     r8, [rsp+3D0h+var_378]
0x1800076d6  lea     rdx, aDescription; "Description"
0x1800076dd  mov     rcx, r14
0x1800076e0  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800076e6  lea     r8, [rsp+3D0h+var_378]
0x1800076eb  lea     rdx, aCaption; "Caption"
0x1800076f2  mov     rcx, r14
0x1800076f5  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800076fb  test    r15d, 101h
0x180007702  jnz     loc_180007C91
0x180007708  bt      r15d, 1Ah
0x18000770d  jb      loc_180007C5D
0x180007713  test    r15b, r15b
0x180007716  jns     short loc_180007790
0x180007718  lea     rdx, [rsp+3D0h+var_378]; struct CHString *
0x18000771d  mov     rcx, r12; this
0x180007720  call    ?GetStatus@CConfigMgrDevice@@QEAAHAEAVCHString@@@Z; CConfigMgrDevice::GetStatus(CHString &)
0x180007725  test    eax, eax
0x180007727  jz      short loc_180007790
0x180007729  lea     r8, [rsp+3D0h+var_378]
0x18000772e  lea     r12, aStatus; "Status"
0x180007735  mov     rdx, r12
0x180007738  mov     rcx, r14
0x18000773b  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180007741  mov     edi, 204h
0x180007746  mov     r8d, edi; Size
0x180007749  xor     edx, edx; Val
0x18000774b  lea     rcx, [rbp+2D0h+var_2A0]; void *
0x18000774f  call    memset_0
0x180007754  mov     [rsp+3D0h+var_368], esi
0x180007758  mov     [rsp+3D0h+lpOverlapped], rsi; lpOverlapped
0x18000775d  lea     rax, [rsp+3D0h+var_368]
0x180007762  mov     [rsp+3D0h+hTemplateFile], rax; lpBytesReturned
0x180007767  mov     [rsp+3D0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18000776b  lea     rax, [rbp+2D0h+var_2A0]
0x18000776f  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rax; lpOutBuffer
0x180007774  xor     r9d, r9d; nInBufferSize
0x180007777  xor     r8d, r8d; lpInBuffer
0x18000777a  mov     edx, 2D1100h; dwIoControlCode
0x18000777f  mov     rcx, rbx; hDevice
0x180007782  call    cs:__imp_DeviceIoControl
0x180007788  test    eax, eax
0x18000778a  jnz     loc_180007E8C
0x180007790  lea     rcx, [rsp+3D0h+var_378]
0x180007795  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18000779b  mov     edi, esi
0x18000779d  mov     [rsp+3D0h+var_36C], esi
0x1800077a1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800077a5  jz      loc_180007C41
0x1800077ab  mov     r12d, 2
0x1800077b1  test    r15d, 40040002h
0x1800077b8  jz      loc_1800078D3
0x1800077be  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800077c2  jz      loc_1800078D3
0x1800077c8  mov     r13d, 10C0h
0x1800077ce  mov     ecx, r13d; unsigned __int64
0x1800077d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800077d6  mov     [rsp+3D0h+lpOutBuffer], rax
0x1800077db  mov     [rbp+2D0h+var_2F0], sil
0x1800077df  lea     rax, ??$deleteArray@K@@YAXPEAK@Z; deleteArray<ulong>(ulong *)
0x1800077e6  mov     [rbp+2D0h+var_2E8], rax
0x1800077ea  lea     rax, [rsp+3D0h+lpOutBuffer]
0x1800077ef  mov     [rbp+2D0h+var_2E0], rax
0x1800077f3  mov     [rsp+3D0h+var_370], r12d
0x1800077f8  mov     esi, r12d
0x1800077fb  and     esi, 0FFFFFFFDh
0x1800077fe  mov     [rsp+3D0h+var_370], esi
0x180007802  or      esi, 1
0x180007805  mov     [rsp+3D0h+var_370], esi
0x180007809  mov     rdi, [rsp+3D0h+lpOutBuffer]
0x18000780e  mov     [rsp+3D0h+BytesReturned], r13d
0x180007813  xor     eax, eax
0x180007815  test    rdi, rdi
0x180007818  jz      loc_180008238
0x18000781e  mov     [rsp+3D0h+var_368], eax
0x180007822  mov     [rsp+3D0h+lpOverlapped], rax; lpOverlapped
0x180007827  lea     rax, [rsp+3D0h+var_368]
0x18000782c  mov     [rsp+3D0h+hTemplateFile], rax; lpBytesReturned
0x180007831  mov     [rsp+3D0h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x180007836  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rdi; lpOutBuffer
0x18000783b  xor     r9d, r9d; nInBufferSize
0x18000783e  xor     r8d, r8d; lpInBuffer
0x180007841  mov     edx, 70050h; dwIoControlCode
0x180007846  mov     rcx, rbx; hDevice
0x180007849  call    cs:__imp_DeviceIoControl
0x18000784f  test    eax, eax
0x180007851  jz      loc_180008185
0x180007857  test    r12b, r15b
0x18000785a  jz      short loc_18000789D
0x18000785c  xor     r13d, r13d
0x18000785f  cmp     [rdi+4], r13d
0x180007863  jbe     short loc_18000788A
0x180007865  xor     r15d, r15d
0x180007868  cmp     dword ptr [rdi], 0
0x18000786b  jz      loc_180007E50
0x180007871  cmp     dword ptr [rdi], 1
0x180007874  jz      loc_18000822B
0x18000787a  inc     r15d
0x18000787d  cmp     r15d, [rdi+4]
0x180007881  jb      short loc_180007868
0x180007883  mov     r15d, [rbp+2D0h+arg_20]
0x18000788a  mov     r8d, r13d
0x18000788d  lea     rdx, aPartitions; "Partitions"
0x180007894  mov     rcx, r14
0x180007897  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18000789d  bt      r15d, 1Eh
0x1800078a2  jb      loc_180007D88
0x1800078a8  bt      r15d, 12h
0x1800078ad  jnb     short loc_1800078C2
0x1800078af  mov     r8b, 1
0x1800078b2  lea     rdx, aMedialoaded; "MediaLoaded"
0x1800078b9  mov     rcx, r14
0x1800078bc  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800078c2  and     esi, 0FFFFFFFEh
0x1800078c5  mov     [rsp+3D0h+var_370], esi
0x1800078c9  mov     rcx, [rsp+3D0h+lpOutBuffer]
  ... truncated ...
```
