# ServerMain(HINSTANCE__ *)

- ea: `0x1400011e4`
- end: `0x140002e03`
- name: `?ServerMain@@YAHPEAUHINSTANCE__@@@Z`
- size: `7199`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `49`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400010d0`

## callees

- `0x1400011e4`
- `0x140003883`
- `0x140003a94`
- `0x140003b5c`
- `0x140003b80`
- `0x140003bc0`
- `0x140003e10`
- `0x140003e70`
- `0x140003ea0`
- `0x1400040d4`
- `0x1400041d0`
- `0x14000453c`
- `0x140004768`
- `0x1400049a4`
- `0x140005000`
- `0x1400052a0`
- `0x1400053a0`
- `0x14000580c`
- `0x1400062a4`
- `0x140006300`
- `0x140006350`
- `0x1400063e0`
- `0x1400064f0`
- `0x14000669c`
- `0x1400066d8`
- `0x140006a90`
- `0x140006ad0`
- `0x140006c40`
- `0x140006e00`
- `0x140006e10`
- `0x140007110`
- `0x140007460`
- `0x140007550`
- `0x140007760`
- `0x1400080c4`
- `0x14000810c`
- `0x14000817c`
- `0x140008300`
- `0x140008668`
- `0x140008690`
- `0x140008808`
- `0x1400088c0`
- `0x14000894c`
- `0x1400089f0`
- `0x140008b10`
- `0x1400094c4`
- `0x140009820`
- `0x1400098b0`
- `0x14000a010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1400023f3`
- `ADVAPI32!GetTokenInformation` at `0x1400023f3`
- `ADVAPI32!MakeAbsoluteSD` at `0x140002611`
- `ADVAPI32!MakeAbsoluteSD` at `0x140002611`
- `ADVAPI32!RegQueryValueExW` at `0x140001449`
- `ADVAPI32!RegQueryValueExW` at `0x14000149f`
- `ADVAPI32!RegQueryValueExW` at `0x140001449`
- `ADVAPI32!RegQueryValueExW` at `0x14000149f`
- `ADVAPI32!OpenThreadToken` at `0x14000224f`
- `ADVAPI32!OpenThreadToken` at `0x14000224f`
- `ADVAPI32!OpenProcessToken` at `0x1400023b6`
- `ADVAPI32!OpenProcessToken` at `0x1400023b6`
- `ADVAPI32!EqualSid` at `0x140002409`
- `ADVAPI32!EqualSid` at `0x140002409`
- `ADVAPI32!RegEnumKeyW` at `0x140002373`
- `ADVAPI32!RegEnumKeyW` at `0x140002373`
- `ADVAPI32!RegCloseKey` at `0x14000146f`
- `ADVAPI32!RegCloseKey` at `0x1400014ac`
- `ADVAPI32!RegCloseKey` at `0x140002362`
- `ADVAPI32!RegCloseKey` at `0x14000146f`
- `ADVAPI32!RegCloseKey` at `0x1400014ac`
- `ADVAPI32!RegCloseKey` at `0x140002362`
- `ADVAPI32!RevertToSelf` at `0x140002352`
- `ADVAPI32!RevertToSelf` at `0x14000237e`
- `ADVAPI32!RevertToSelf` at `0x140002352`
- `ADVAPI32!RevertToSelf` at `0x14000237e`
- `KERNEL32!CompareStringW` at `0x1400017f1`
- `KERNEL32!CompareStringW` at `0x140001826`
- `KERNEL32!CompareStringW` at `0x140001917`
- `KERNEL32!CompareStringW` at `0x1400017f1`
- `KERNEL32!CompareStringW` at `0x140001826`
- `KERNEL32!CompareStringW` at `0x140001917`
- `KERNEL32!GetCommandLineW` at `0x140001294`
- `KERNEL32!GetCommandLineW` at `0x140001294`
- `KERNEL32!GetCurrentProcess` at `0x1400023a5`
- `KERNEL32!GetCurrentProcess` at `0x1400023a5`
- `KERNEL32!lstrlenW` at `0x140001c32`
- `KERNEL32!lstrlenW` at `0x140001c32`
- `KERNEL32!GetStdHandle` at `0x1400012e8`
- `KERNEL32!GetStdHandle` at `0x1400012e8`
- `KERNEL32!WaitForSingleObject` at `0x140002306`
- `KERNEL32!WaitForSingleObject` at `0x140002306`
- `KERNEL32!OpenEventW` at `0x1400022e9`
- `KERNEL32!OpenEventW` at `0x1400022e9`
- `KERNEL32!GetVersionExW` at `0x140001251`
- `KERNEL32!GetVersionExW` at `0x140001251`
- `KERNEL32!OpenProcess` at `0x1400029c4`
- `KERNEL32!OpenProcess` at `0x140002bd6`
- `KERNEL32!OpenProcess` at `0x1400029c4`
- `KERNEL32!OpenProcess` at `0x140002bd6`
- `KERNEL32!CreateEventW` at `0x14000272d`
- `KERNEL32!CreateEventW` at `0x1400027ca`
- `KERNEL32!CreateEventW` at `0x14000272d`
- `KERNEL32!CreateEventW` at `0x1400027ca`
- `KERNEL32!GetLastError` at `0x140002261`
- `KERNEL32!GetLastError` at `0x14000245a`
- `KERNEL32!GetLastError` at `0x14000261b`
- `KERNEL32!GetLastError` at `0x14000274f`
- `KERNEL32!GetLastError` at `0x1400027e8`
- `KERNEL32!GetLastError` at `0x1400029e2`
- `KERNEL32!GetLastError` at `0x140002c44`
- `KERNEL32!GetLastError` at `0x140002d95`
- `KERNEL32!GetLastError` at `0x140002261`
- `KERNEL32!GetLastError` at `0x14000245a`
- `KERNEL32!GetLastError` at `0x14000261b`
- `KERNEL32!GetLastError` at `0x14000274f`
- `KERNEL32!GetLastError` at `0x1400027e8`
- `KERNEL32!GetLastError` at `0x1400029e2`
- `KERNEL32!GetLastError` at `0x140002c44`
- `KERNEL32!GetLastError` at `0x140002d95`
- `KERNEL32!GetCurrentThread` at `0x14000223b`
- `KERNEL32!GetCurrentThread` at `0x14000223b`
- `KERNEL32!GlobalFree` at `0x1400013e6`
- `KERNEL32!GlobalFree` at `0x1400014f1`
- `KERNEL32!GlobalFree` at `0x14000150d`
- `KERNEL32!GlobalFree` at `0x14000153a`
- `KERNEL32!GlobalFree` at `0x14000156a`
- `KERNEL32!GlobalFree` at `0x140001586`
- `KERNEL32!GlobalFree` at `0x1400019a0`
- `KERNEL32!GlobalFree` at `0x1400019bc`
- `KERNEL32!GlobalFree` at `0x1400019ec`
- `KERNEL32!GlobalFree` at `0x140001a08`
- `KERNEL32!GlobalFree` at `0x140001bdc`
- `KERNEL32!GlobalFree` at `0x140001bfb`
- `KERNEL32!GlobalFree` at `0x140001e9d`
- `KERNEL32!GlobalFree` at `0x140001f79`
- `KERNEL32!GlobalFree` at `0x140001f94`
- `KERNEL32!GlobalFree` at `0x14000203c`
- `KERNEL32!GlobalFree` at `0x1400021e0`
- `KERNEL32!GlobalFree` at `0x14000233a`
- `KERNEL32!GlobalFree` at `0x1400027a9`
- `KERNEL32!GlobalFree` at `0x140002ca1`
- `KERNEL32!GlobalFree` at `0x140002d66`
- `KERNEL32!GlobalFree` at `0x140002d85`
- `KERNEL32!GlobalFree` at `0x1400013e6`
- `KERNEL32!GlobalFree` at `0x1400014f1`
- `KERNEL32!GlobalFree` at `0x14000150d`
- `KERNEL32!GlobalFree` at `0x14000153a`
- `KERNEL32!GlobalFree` at `0x14000156a`
- `KERNEL32!GlobalFree` at `0x140001586`
- `KERNEL32!GlobalFree` at `0x1400019a0`
- `KERNEL32!GlobalFree` at `0x1400019bc`
- `KERNEL32!GlobalFree` at `0x1400019ec`
- `KERNEL32!GlobalFree` at `0x140001a08`
- `KERNEL32!GlobalFree` at `0x140001bdc`
- `KERNEL32!GlobalFree` at `0x140001bfb`
- `KERNEL32!GlobalFree` at `0x140001e9d`
- `KERNEL32!GlobalFree` at `0x140001f79`
- `KERNEL32!GlobalFree` at `0x140001f94`
- `KERNEL32!GlobalFree` at `0x14000203c`
- `KERNEL32!GlobalFree` at `0x1400021e0`
- `KERNEL32!GlobalFree` at `0x14000233a`
- `KERNEL32!GlobalFree` at `0x1400027a9`
- `KERNEL32!GlobalFree` at `0x140002ca1`
- `KERNEL32!GlobalFree` at `0x140002d66`
- `KERNEL32!GlobalFree` at `0x140002d85`
- `KERNEL32!CloseHandle` at `0x140002311`
- `KERNEL32!CloseHandle` at `0x14000244c`
- `KERNEL32!CloseHandle` at `0x140002537`
- `KERNEL32!CloseHandle` at `0x14000262d`
- `KERNEL32!CloseHandle` at `0x1400026cd`
- `KERNEL32!CloseHandle` at `0x140002749`
- `KERNEL32!CloseHandle` at `0x1400027e2`
- `KERNEL32!CloseHandle` at `0x14000286a`
- `KERNEL32!CloseHandle` at `0x1400028cb`
- `KERNEL32!CloseHandle` at `0x1400029a3`
- `KERNEL32!CloseHandle` at `0x1400029dc`
- `KERNEL32!CloseHandle` at `0x140002a17`
- `KERNEL32!CloseHandle` at `0x140002aee`
- `KERNEL32!CloseHandle` at `0x140002ba8`
- `KERNEL32!CloseHandle` at `0x140002c3e`
- `KERNEL32!CloseHandle` at `0x140002cc1`
- `KERNEL32!CloseHandle` at `0x140002cdb`
- `KERNEL32!CloseHandle` at `0x140002311`
- `KERNEL32!CloseHandle` at `0x14000244c`
- `KERNEL32!CloseHandle` at `0x140002537`
- `KERNEL32!CloseHandle` at `0x14000262d`
- `KERNEL32!CloseHandle` at `0x1400026cd`
- `KERNEL32!CloseHandle` at `0x140002749`
- `KERNEL32!CloseHandle` at `0x1400027e2`
- `KERNEL32!CloseHandle` at `0x14000286a`
- `KERNEL32!CloseHandle` at `0x1400028cb`
- `KERNEL32!CloseHandle` at `0x1400029a3`
- `KERNEL32!CloseHandle` at `0x1400029dc`
- `KERNEL32!CloseHandle` at `0x140002a17`
- `KERNEL32!CloseHandle` at `0x140002aee`
- `KERNEL32!CloseHandle` at `0x140002ba8`
- `KERNEL32!CloseHandle` at `0x140002c3e`
- `KERNEL32!CloseHandle` at `0x140002cc1`
- `KERNEL32!CloseHandle` at `0x140002cdb`
- `KERNEL32!GetFileType` at `0x1400012fe`
- `KERNEL32!GetFileType` at `0x1400012fe`
- `USER32!MsgWaitForMultipleObjects` at `0x140002b8a`
- `USER32!MsgWaitForMultipleObjects` at `0x140002b8a`
- `USER32!DispatchMessageW` at `0x140002c2c`
- `USER32!DispatchMessageW` at `0x140002dfb`
- `USER32!DispatchMessageW` at `0x140002c2c`
- `USER32!DispatchMessageW` at `0x140002dfb`
- `USER32!PeekMessageW` at `0x140002c06`
- `USER32!PeekMessageW` at `0x140002c06`
- `USER32!TranslateMessage` at `0x140002c22`
- `USER32!TranslateMessage` at `0x140002df1`
- `USER32!TranslateMessage` at `0x140002c22`
- `USER32!TranslateMessage` at `0x140002df1`
- `USER32!GetMessageW` at `0x140002dc9`
- `USER32!GetMessageW` at `0x140002dc9`
- `ole32!CoUninitialize` at `0x140002d40`
- `ole32!CoUninitialize` at `0x140002d40`
- `ole32!CoRegisterClassObject` at `0x140002115`
- `ole32!CoRegisterClassObject` at `0x140002115`
- `ole32!CoRevokeClassObject` at `0x140002d3a`
- `ole32!CoRevokeClassObject` at `0x140002d3a`
- `ole32!CoInitialize` at `0x1400020b2`
- `ole32!CoInitialize` at `0x1400020b2`

## string_xrefs

- `0x1400013f8`: `Software\Microsoft\Windows\CurrentVersion\Installer\RunOnceEntries`
- `0x1400015be`: `update`
- `0x1400015db`: `uninstall`
- `0x14000170a`: `MSIPATCHREMOVE=`
- `0x1400020b8`: `OLEAUT32.dll`
- `0x1400021c5`: `ServerMain (CA): Wrong command line`
- `0x140002201`: `ServerMain (CA): Parsing command line failed`
- `0x140002d9d`: `ServerMain (CA): Open synchronization event failed`
- `0x140002274`: `ServerMain (CA): Access to token failed`
- `0x14000247c`: `OpenProcessToken failed with %d`
- `0x1400024cb`: `ServerMain (CA): Error: icacContext in CA server should be EEUI but is not any impersonated type`
- `0x1400024e3`: `ServerMain (CA): Error: icacContext in CA server should be AISImpersonated but is not any impersonated type`
- `0x14000253f`: `ServerMain (CA): Error: Access to SD`
- `0x1400026d5`: `ServerMain (CA): CoInitializeSecurity failed`
- `0x140002870`: `ServerMain (CA): Connection to Service failed.`
- `0x1400028d1`: `ServerMain (CA): Create Custom Action Server failed.`
- `0x1400029a9`: `ServerMain (CA): Process not registered with service.`
- `0x1400029ea`: `ServerMain (CA): Could not open synchronization handle.`
- `0x140002c4c`: `ServerMain (CA): Could not open synchronization handle.`
- `0x140002b00`: `ServerMain (CA): Impersonation token not saved.`

## pseudocode

```c
__int64 __fastcall ServerMain(HINSTANCE a1)
{
  char v2; // r13
  LPWSTR CommandLineW; // rax
  __int16 v4; // dx
  LPWSTR v5; // rbx
  unsigned __int16 v6; // cx
  LPWSTR v7; // rdi
  HANDLE StdHandle; // rax
  unsigned __int64 v9; // rdx
  unsigned __int16 v10; // ax
  HKEY v11; // rcx
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  bool v14; // cc
  LSTATUS v15; // ebx
  WCHAR *i; // rbx
  unsigned __int16 v17; // si
  unsigned __int64 v19; // rdx
  const unsigned __int16 *NextToken; // rax
  char *v21; // r15
  const unsigned __int16 *v22; // rdi
  unsigned __int16 v23; // ax
  int v24; // esi
  char *v25; // r14
  void *p_ReturnLength; // rax
  const unsigned __int16 *v27; // rax
  unsigned __int64 v28; // rdx
  __int64 v29; // r9
  const unsigned __int16 *v30; // rbx
  unsigned __int16 v31; // ax
  HKEY v32; // r14
  unsigned int j; // edi
  unsigned __int64 v34; // rdx
  const unsigned __int16 *v35; // rcx
  __int64 v36; // r9
  DWORD appended; // ebx
  WCHAR *k; // rcx
  WCHAR *v39; // rax
  const unsigned __int16 *v40; // r14
  signed int v41; // edi
  const unsigned __int16 *v42; // rcx
  const WCHAR *v43; // rbx
  int v44; // ecx
  const wchar_t *v45; // r15
  unsigned __int16 v46; // ax
  __int64 v47; // rcx
  BOOL v48; // ebx
  bool v49; // zf
  bool v50; // cc
  int v51; // eax
  size_t *v52; // r8
  unsigned __int64 v53; // rax
  __int64 v54; // rcx
  WCHAR *p_ValueName; // r12
  wchar_t *p_pszSrc; // rbx
  int v57; // eax
  size_t *v58; // r8
  void *v59; // rdx
  __int16 v60; // ax
  int v61; // esi
  DWORD v62; // r14d
  int v63; // eax
  int m; // esi
  int v65; // r9d
  WCHAR v66; // r8
  char v67; // al
  char v68; // r8
  char v69; // r10
  char v70; // al
  int v71; // eax
  int v72; // edx
  wchar_t *v73; // rcx
  bool v74; // cc
  char v75; // r14
  unsigned __int8 v76; // r12
  char v77; // r15
  HANDLE CurrentThread; // rax
  DWORD v79; // eax
  unsigned int v80; // edx
  BYTE *v81; // rcx
  char *v82; // rax
  void *v83; // rbx
  DWORD v84; // esi
  unsigned int v85; // esi
  HANDLE CurrentProcess; // rax
  DWORD v87; // ebx
  __int64 v88; // r8
  unsigned int v89; // ebx
  HANDLE EventW; // r15
  DWORD v91; // eax
  HANDLE v92; // r12
  DWORD v93; // eax
  LPCWSTR v94; // r14
  wchar_t *v95; // rcx
  DWORD v96; // edx
  struct IUnknown *CustomActionServer; // rax
  struct IUnknown *v98; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r13
  unsigned int (__fastcall *v100)(LPCWSTR, unsigned int *, __int128 *, __int64, PSID, DWORD *, __int64 *, int *); // rbx
  HANDLE v101; // rbx
  unsigned int *v102; // rdx
  __int64 v103; // r9
  __int64 v104; // r8
  int v105; // esi
  DWORD v106; // eax
  HANDLE v107; // rax
  DWORD v108; // eax
  DWORD LastError; // eax
  int lpData; // [rsp+20h] [rbp-E0h]
  char v111; // [rsp+60h] [rbp-A0h]
  char v112; // [rsp+61h] [rbp-9Fh]
  LPCWSTR lpString; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid2; // [rsp+78h] [rbp-88h] BYREF
  char v116; // [rsp+80h] [rbp-80h]
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  int cchCount2[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v121; // [rsp+A0h] [rbp-60h] BYREF
  DWORD dwProcessId; // [rsp+A4h] [rbp-5Ch] BYREF
  int v123; // [rsp+A8h] [rbp-58h]
  DWORD dwPrimaryGroupSize; // [rsp+ACh] [rbp-54h] BYREF
  DWORD dwOwnerSize; // [rsp+B0h] [rbp-50h] BYREF
  DWORD dwSaclSize; // [rsp+B4h] [rbp-4Ch] BYREF
  DWORD dwDaclSize; // [rsp+B8h] [rbp-48h] BYREF
  int v128; // [rsp+BCh] [rbp-44h] BYREF
  tagMSG Msg; // [rsp+C0h] [rbp-40h] BYREF
  HGLOBAL v130; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v131; // [rsp+F8h] [rbp-8h]
  char v132; // [rsp+100h] [rbp+0h] BYREF
  HGLOBAL hMem; // [rsp+110h] [rbp+10h] BYREF
  int v134; // [rsp+118h] [rbp+18h]
  int v135; // [rsp+11Ch] [rbp+1Ch]
  _BYTE v136[528]; // [rsp+120h] [rbp+20h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+330h] [rbp+230h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor[34]; // [rsp+450h] [rbp+350h] BYREF
  PSID pPrimaryGroup[34]; // [rsp+560h] [rbp+460h] BYREF
  PSID pOwner[34]; // [rsp+670h] [rbp+570h] BYREF
  PACL pSacl[34]; // [rsp+780h] [rbp+680h] BYREF
  unsigned __int16 *v142; // [rsp+890h] [rbp+790h] BYREF
  int v143; // [rsp+898h] [rbp+798h]
  int v144; // [rsp+89Ch] [rbp+79Ch]
  _BYTE v145[528]; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int64 v146; // [rsp+AB0h] [rbp+9B0h] BYREF
  int v147; // [rsp+AB8h] [rbp+9B8h]
  wchar_t v148; // [rsp+ABCh] [rbp+9BCh]
  DWORD ReturnLength; // [rsp+AC0h] [rbp+9C0h] BYREF
  wchar_t v150; // [rsp+AC4h] [rbp+9C4h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+AC8h] [rbp+9C8h] BYREF
  wchar_t v152; // [rsp+ACCh] [rbp+9CCh]
  __int128 v153; // [rsp+AD0h] [rbp+9D0h] BYREF
  HANDLE pHandles[2]; // [rsp+AE0h] [rbp+9E0h] BYREF
  __int128 v155; // [rsp+AF0h] [rbp+9F0h]
  PCNZWCH lpString2; // [rsp+B00h] [rbp+A00h] BYREF
  unsigned __int16 *p_dwAbsoluteSecurityDescriptorSize; // [rsp+B08h] [rbp+A08h]
  _BYTE v158[8]; // [rsp+B10h] [rbp+A10h]
  const wchar_t *v159; // [rsp+B18h] [rbp+A18h]
  void *v160; // [rsp+B20h] [rbp+A20h]
  char v161; // [rsp+B28h] [rbp+A28h]
  const WCHAR *v162; // [rsp+B30h] [rbp+A30h]
  const wchar_t *v163; // [rsp+B38h] [rbp+A38h]
  char v164; // [rsp+B40h] [rbp+A40h]
  const wchar_t *v165; // [rsp+B48h] [rbp+A48h]
  const wchar_t *v166; // [rsp+B50h] [rbp+A50h]
  char v167; // [rsp+B58h] [rbp+A58h]
  const wchar_t *v168; // [rsp+B60h] [rbp+A60h]
  const wchar_t *v169; // [rsp+B68h] [rbp+A68h]
  char v170; // [rsp+B70h] [rbp+A70h]
  const wchar_t *v171; // [rsp+B78h] [rbp+A78h]
  const wchar_t *v172; // [rsp+B80h] [rbp+A80h]
  char v173; // [rsp+B88h] [rbp+A88h]
  const wchar_t *v174; // [rsp+B90h] [rbp+A90h]
  const wchar_t *v175; // [rsp+B98h] [rbp+A98h]
  char v176; // [rsp+BA0h] [rbp+AA0h]
  const wchar_t *v177; // [rsp+BA8h] [rbp+AA8h]
  const wchar_t *v178; // [rsp+BB0h] [rbp+AB0h]
  char v179; // [rsp+BB8h] [rbp+AB8h]
  const wchar_t *v180; // [rsp+BC0h] [rbp+AC0h]
  const wchar_t *v181; // [rsp+BC8h] [rbp+AC8h]
  char v182; // [rsp+BD0h] [rbp+AD0h]
  const wchar_t *v183; // [rsp+BD8h] [rbp+AD8h]
  const wchar_t *v184; // [rsp+BE0h] [rbp+AE0h]
  char v185; // [rsp+BE8h] [rbp+AE8h]
  wchar_t pszDest[32]; // [rsp+C00h] [rbp+B00h] BYREF
  PSID TokenInformation[12]; // [rsp+C40h] [rbp+B40h] BYREF
  WCHAR ValueName; // [rsp+CA0h] [rbp+BA0h] BYREF
  char v189[2046]; // [rsp+CA2h] [rbp+BA2h] BYREF
  wchar_t pszSrc; // [rsp+14A0h] [rbp+13A0h] BYREF
  char v191[2046]; // [rsp+14A2h] [rbp+13A2h] BYREF
  wchar_t v192[1024]; // [rsp+1CA0h] [rbp+1BA0h] BYREF

  v130 = &v132;
  v131 = 1;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  v2 = 0;
  if ( GetVersionExW(&VersionInformation) )
  {
    g_fWoW = 1;
    g_fWinNT64 = 1;
  }
  *g_szCommandLine = 0;
  *g_szTransforms = 0;
  hMem = v136;
  v134 = 260;
  CommandLineW = GetCommandLineW();
  v4 = 34;
  v5 = CommandLineW;
  if ( *CommandLineW == 34 )
    v5 = ++CommandLineW;
  else
    v4 = 32;
  v6 = *v5;
  if ( *v5 )
  {
    do
    {
      v5 = CommandLineW + 1;
      v7 = CommandLineW + 1;
      if ( v6 == v4 )
        break;
      v6 = *v5;
      ++CommandLineW;
    }
    while ( *v5 );
  }
  else
  {
    v7 = CommandLineW;
  }
  g_hInstance = a1;
  StdHandle = GetStdHandle(0xFFFFFFF5);
  g_hStdOut = StdHandle;
  if ( StdHandle == (HANDLE)-1LL || GetFileType(StdHandle) != 3 )
    g_hStdOut = 0;
  ValueName = 0;
  memset_0(v189, 0, sizeof(v189));
  pszSrc = 0;
  memset_0(v191, 0, sizeof(v191));
  g_fCustomActionServer = 0;
  while ( 1 )
  {
    v10 = *v5;
    if ( *v5 != 32 && v10 != 9 )
      break;
    v5 = ++v7;
  }
  if ( ((v10 - 45) & 0xFFFD) == 0 && v7 != (LPWSTR)-2LL && (v5[1] | 0x20) == 0x60 )
  {
    lpString = v7 + 2;
    SkipWhiteSpace(&lpString);
    pSid2 = &ValueName;
    if ( !ParseValue(&lpString, (unsigned __int16 **)&pSid2, 0x400u) )
    {
      ShowHelp(0, 0);
      if ( v134 > 260 )
        GlobalFree(hMem);
      v14 = (int)v131 <= 1;
LABEL_175:
      v134 = 260;
LABEL_176:
      hMem = v136;
      if ( !v14 )
        GlobalFree(v130);
      return 1639;
    }
    hKey = 0;
    cbData = 2 * v134;
    Type = 0;
    if ( MsiRegOpen64bitKey(
           v11,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\RunOnceEntries",
           v12,
           v13,
           &hKey) )
    {
      goto LABEL_36;
    }
    v15 = RegQueryValueExW(hKey, &ValueName, 0, &Type, (LPBYTE)hMem, &cbData);
    if ( v15 == 234 )
    {
      if ( !(unsigned __int8)CAPITempBuffer<unsigned short,260>::SetSize(&hMem, cbData >> 1) )
      {
        RegCloseKey(hKey);
LABEL_46:
        if ( v134 > 260 )
          GlobalFree(hMem);
        v134 = 260;
        hMem = v136;
        if ( (int)v131 > 1 )
          GlobalFree(v130);
        return 14;
      }
      v15 = RegQueryValueExW(hKey, &ValueName, 0, &Type, (LPBYTE)hMem, &cbData);
    }
    RegCloseKey(hKey);
    if ( v15 || Type != 1 )
    {
LABEL_36:
      if ( v134 > 260 )
        GlobalFree(hMem);
      v134 = 260;
      hMem = v136;
      if ( (int)v131 > 1 )
        GlobalFree(v130);
      return 0;
    }
    for ( i = (WCHAR *)hMem; ; ++i )
    {
      v17 = *i;
      lpString = i;
      if ( v17 != 32 && v17 != 9 )
        break;
    }
    goto LABEL_99;
  }
  hKey = 0;
  if ( (int)StringCchLengthW(v5, v9, (unsigned __int64 *)&hKey) < 0 )
    goto LABEL_42;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,260>::SetSize(&hMem, (unsigned int)((_DWORD)hKey + 1)) )
    goto LABEL_46;
  p_dwAbsoluteSecurityDescriptorSize = 0;
  v158[0] = 0;
  v160 = 0;
  *(_WORD *)hMem = 0;
  lpString2 = L"update";
  v159 = L"uninstall";
  v163 = L"/i";
  v165 = L"help";
  v166 = L"/h";
  v168 = L"quiet";
  v169 = L"/qn";
  v171 = L"passive";
  v172 = L"/qb!- REBOOTPROMPT=S";
  v174 = L"norestart";
  v175 = L"REBOOT=ReallySuppress";
  v177 = L"forcerestart";
  v178 = L"REBOOT=Force";
  v180 = L"promptrestart";
  v181 = L"REBOOTPROMPT=\"\"";
  v183 = L"log";
  v184 = L"/l*";
  ReturnLength = *(_DWORD *)L"/x";
  v150 = asc_14000BF40[2];
  dwAbsoluteSecurityDescriptorSize = *(_DWORD *)L"/p";
  v152 = aP[2];
  v147 = *(_DWORD *)L"H=";
  v146 = *(_QWORD *)L"PATCH=";
  v148 = aPatch[6];
  v161 = 0;
  v162 = L"package";
  v164 = 1;
  v167 = 1;
  v170 = 1;
  v173 = 1;
  v176 = 1;
  v179 = 1;
  v182 = 1;
  v185 = 1;
  *(_OWORD *)pHandles = *(_OWORD *)L"MSIPATCHREMOVE=";
  *(_QWORD *)cchCount2 = 0;
  v155 = *(_OWORD *)L"REMOVE=";
  if ( (int)StringCchLengthW(L"package", v19, (unsigned __int64 *)cchCount2) < 0 )
  {
LABEL_42:
    if ( v134 > 260 )
      GlobalFree(hMem);
    hMem = v136;
LABEL_85:
    v134 = 260;
    if ( (int)v131 > 1 )
      GlobalFree(v130);
    return 1627;
  }
  pSid2 = v5;
  hKey = 0;
  NextToken = GetNextToken((const unsigned __int16 **)&pSid2, (unsigned __int64 *)&hKey);
  v21 = *(char **)cchCount2;
  while ( 1 )
  {
    v22 = NextToken;
    if ( !NextToken )
      break;
    v23 = *NextToken;
    if ( !v23 )
      break;
    if ( ((v23 - 45) & 0xFFFD) == 0 )
    {
      if ( (v24 = (int)hKey, v25 = (char *)hKey - 1, hKey == (HKEY)2)
        && CompareStringW(0x409u, 1u, v22 + 1, 1, L"i", -1) == 2
        || v21 == v25 && CompareStringW(0x409u, 1u, v22 + 1, v24 - 1, L"package", (int)v21) == 2 )
      {
        p_dwAbsoluteSecurityDescriptorSize = (unsigned __int16 *)&v146;
        p_ReturnLength = pHandles;
        goto LABEL_63;
      }
    }
    NextToken = GetNextToken((const unsigned __int16 **)&pSid2, (unsigned __int64 *)&hKey);
  }
  p_dwAbsoluteSecurityDescriptorSize = (unsigned __int16 *)&dwAbsoluteSecurityDescriptorSize;
  p_ReturnLength = &ReturnLength;
  v158[0] = 1;
  v161 = 1;
LABEL_63:
  v160 = p_ReturnLength;
  pSid2 = v5;
  hKey = 0;
  while ( 1 )
  {
    v27 = GetNextToken((const unsigned __int16 **)&pSid2, (unsigned __int64 *)&hKey);
    v30 = v27;
    if ( !v27 )
      break;
    v31 = *v27;
    if ( !v31 )
      break;
    v32 = hKey;
    if ( ((v31 - 45) & 0xFFFD) == 0 )
    {
      for ( j = 0; j < 0xA; ++j )
      {
        if ( CompareStringW(0x409u, 1u, v30 + 1, (_DWORD)v32 - 1, (&lpString2)[3 * (int)j], -1) == 2 )
        {
          v35 = *(const unsigned __int16 **)&v158[24 * j - 8];
          v135 = 260;
          *(_QWORD *)cchCount2 = 0;
          if ( (int)StringCchLengthW(v35, v34, (unsigned __int64 *)cchCount2) >= 0 )
          {
            LOBYTE(v36) = v158[24 * j];
            appended = AppendString(&hMem, *(_QWORD *)&v158[24 * j - 8], *(_QWORD *)cchCount2, v36);
          }
          else
          {
            appended = 1627;
          }
          goto LABEL_75;
        }
      }
    }
    LOBYTE(v29) = 1;
    v135 = 260;
    appended = AppendString(&hMem, v30, v32, v29);
LABEL_75:
    if ( appended )
      goto LABEL_76;
  }
  i = (WCHAR *)hMem;
  hKey = 0;
  if ( (int)StringCchLengthW((const unsigned __int16 *)hMem, v28, (unsigned __int64 *)&hKey) < 0 )
  {
    if ( v134 > 260 )
      GlobalFree(i);
    hMem = v136;
    goto LABEL_85;
  }
  if ( hKey )
  {
    for ( k = &i[(_QWORD)hKey - 1]; (*k == 32 || *k == 9) && k >= i; --k )
    {
      *k = 0;
      i = (WCHAR *)hMem;
    }
  }
  v17 = *i;
  lpString = i;
  if ( v17 )
  {
    v39 = i;
    do
    {
      if ( v17 != 32 && v17 != 9 )
        break;
      i = v39 + 1;
      v17 = v39[1];
      v39 = i;
      lpString = i;
    }
    while ( v17 );
  }
LABEL_99:
  v40 = g_pchOption;
  v41 = 0;
  while ( 1 )
  {
    if ( !v17 )
      goto LABEL_162;
    if ( v17 != 47 && v17 != 45 )
    {
      memset_0(v145, 0, 0x208u);
      v143 = 260;
      v142 = (unsigned __int16 *)v145;
      v144 = 260;
      if ( (unsigned int)ParseProperty(&lpString, &v142) )
      {
        Properties(v42, v142);
        v17 = SkipWhiteSpace(&lpString);
        CTempBuffer<unsigned short,260>::~CTempBuffer<unsigned short,260>(&v142);
        v40 = g_pchOption;
        goto LABEL_155;
      }
      ShowHelp(0, 0);
      v41 = 1639;
      CTempBuffer<unsigned short,260>::~CTempBuffer<unsigned short,260>(&v142);
      goto LABEL_118;
    }
    v43 = i + 1;
    v44 = *v43 | 0x20;
    if ( *v43 )
      ++v43;
    lpString = v43;
    v45 = L"RUVEH?IJDqXFAtPYZlgmnc";
    v46 = 82;
    do
    {
      if ( (v46 | 0x20) == v44 )
        break;
      v46 = *++v45;
    }
    while ( *v45 );
    if ( !*v45 )
    {
LABEL_117:
      ShowHelp(0, 0);
      v41 = 1639;
      goto LABEL_118;
    }
    v48 = 1;
    if ( *v43 <= 0x20u )
    {
      v47 = 0x100000201LL;
      if ( _bittest64(&v47, *v43) )
        v48 = 0;
    }
    SkipWhiteSpace(&lpString);
    v49 = *v45 == 99;
    pSid2 = &ValueName;
    if ( v49 )
    {
      if ( v48 )
        goto LABEL_117;
    }
    else if ( *v45 == 80 )
    {
      v51 = lstrlenW(lpString);
      if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v130, (unsigned int)(v51 + 10)) )
      {
        v41 = 14;
LABEL_118:
        HeapSetInformation_HeapEnableTerminationOnCorruption_Downlevel();
LABEL_119:
        if ( v134 > 260 )
          GlobalFree(hMem);
        v50 = (int)v131 <= 1;
        v134 = 260;
LABEL_122:
        hMem = v136;
        if ( !v50 )
          GlobalFree(v130);
        return (unsigned int)v41;
      }
      *(_QWORD *)cchCount2 = v130;
      if ( !ParseValue(&lpString, (unsigned __int16 **)cchCount2, v131) )
        goto LABEL_172;
      v40 = g_pchOption;
    }
    else if ( (*v45 != 113 || v48) && !ParseValue(&lpString, (unsigned __int16 **)&pSid2, 0x400u) )
    {
LABEL_172:
      ShowHelp(0, 0);
      if ( v134 > 260 )
        GlobalFree(hMem);
      v14 = (int)v131 <= 1;
      goto LABEL_175;
    }
    v17 = SkipWhiteSpace(&lpString);
    v53 = *v45;
    LOWORD(v53) = v53 - 70;
    if ( (unsigned __int16)v53 <= 0x2Bu && (v54 = 0x84000000011LL, _bittest64(&v54, v53)) && v48 )
    {
      v49 = *v45 == 113;
      pSid2 = &pszSrc;
      p_ValueName = &ValueName;
      p_pszSrc = &pszSrc;
      if ( !v49 )
      {
        if ( !ParseValue(&lpString, (unsigned __int16 **)&pSid2, 0x400u) )
        {
          ShowHelp(0, 0);
          if ( v134 > 260 )
            GlobalFree(hMem);
          v14 = (int)v131 <= 1;
          v134 = 260;
          goto LABEL_176;
        }
        v17 = SkipWhiteSpace(&lpString);
      }
    }
    else
    {
      p_pszSrc = &ValueName;
      p_ValueName = &pszSrc;
    }
    if ( (unsigned __int16)(*v45 - 97) <= 0x19u )
    {
      v57 = ((__int64 (__fastcall *)(WCHAR *, wchar_t *))(&rgCommandProcessor)[v45 - L"RUVEH?IJDqXFAtPYZlgmnc"])(
              p_ValueName,
              p_pszSrc);
LABEL_149:
      if ( v57 )
        goto LABEL_117;
      v40 = g_pchOption;
      goto LABEL_154;
    }
    if ( !v40 )
      break;
    if ( *v45 != 80 || *v40 != 65 )
    {
      if ( *v40 != 80 || *v45 != 65 )
        goto LABEL_117;
      v57 = SetProductToPatch(0x41u, p_pszSrc);
      goto LABEL_149;
    }
    if ( SetProductToPatch(0x41u, v192) )
      goto LABEL_117;
    g_pchOption = v45;
    v40 = v45;
    StringCopyWorkerW(pszDest, 0x1Eu, v58, p_ValueName, 0x1Eu);
LABEL_154:
    ValueName = 0;
    pszSrc = 0;
LABEL_155:
    i = (WCHAR *)lpString;
  }
  v49 = *v45 == 80;
  v40 = v45;
  g_pchOption = v45;
  if ( !v49 )
    StringCopyWorkerW(v192, 0x400u, v52, p_pszSrc, 0x400u);
  StringCopyWorkerW(pszDest, 0x1Eu, v52, p_ValueName, 0x1Eu);
  if ( *v45 != 69 )
    goto LABEL_154;
  i = (WCHAR *)lpString;
LABEL_162:
  if ( !v40 )
  {
    HeapSetInformation_HeapEnableTerminationOnCorruption_Downlevel();
    if ( !g_pchOption )
    {
      ShowHelp(0, 0);
      v41 = 1639;
      goto LABEL_119;
    }
    v61 = 0;
    v123 = 0;
    goto LABEL_202;
  }
  if ( *v40 != 69 && (unsigned __int16)(*v40 - 89) > 1u )
  {
    HeapSetInformation_HeapEnableTerminationOnCorruption_Downlevel();
    v40 = g_pchOption;
  }
  v59 = v192;
  if ( *v40 == 80 )
    v59 = v130;
  v41 = ((__int64 (__fastcall *)(wchar_t *, void *))(&rgCommandProcessor)[v40 - L"RUVEH?IJDqXFAtPYZlgmnc"])(
          pszDest,
          v59);
  v60 = *g_pchOption;
  if ( (unsigned __int16)(*g_pchOption - 89) <= 1u )
  {
    if ( v134 > 260 )
      GlobalFree(hMem);
    v50 = (int)v131 <= 1;
    v134 = 260;
    goto LABEL_122;
  }
  v123 = 0;
  v61 = 0;
  if ( v41 )
  {
    if ( v41 == 0x8000 )
    {
      g_fCustomActionServer = 0;
      v41 = 0;
      goto LABEL_119;
    }
    if ( v41 > 1259 )
    {
      if ( v41 != 1602 && v41 != 1603 && v41 != 1604 && v41 != 1641 && v41 != 3010 )
LABEL_195:
        DisplayError(v41);
    }
    else if ( v41 != 1259 && v41 != -2 && v41 != -1 )
    {
      if ( v41 == 2 || v41 == 3 || v41 == 123 )
        v41 = 1619;
      goto LABEL_195;
    }
LABEL_202:
    if ( !v41 )
    {
      v63 = g_fCustomActionServer;
      v62 = 0;
      cbData = 0;
      if ( g_fCustomActionServer )
        goto LABEL_204;
    }
    goto LABEL_119;
  }
  v62 = 0;
  if ( v60 == 69 )
  {
    g_fCustomActionServer = 1;
    cbData = 0;
    goto LABEL_205;
  }
  v63 = g_fCustomActionServer;
  v61 = 1;
  v123 = 1;
  cbData = 0;
LABEL_204:
  if ( v63 )
  {
LABEL_205:
    ((void (__fastcall *)(_QWORD, _QWORD))OLE32::CoInitializeEx)(0, 0);
  }
  else
  {
    CoInitialize(0);
    LoadSystemLibrary(L"OLEAUT32.dll");
  }
  if ( !v61 )
  {
LABEL_214:
    if ( g_fCustomActionServer )
      goto LABEL_215;
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) || g_fAutomation && g_cInstances )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
LABEL_361:
    if ( v123 && !g_fCustomActionServer && g_rghRegClass )
      CoRevokeClassObject(g_rghRegClass);
    CoUninitialize();
    if ( !v62 )
      goto LABEL_119;
    DisplayError(0x641u);
    if ( v134 > 260 )
      GlobalFree(hMem);
    hMem = v136;
    goto LABEL_369;
  }
  if ( !g_fCustomActionServer )
  {
    for ( m = 0; m < 1; ++m )
    {
      if ( CoRegisterClassObject(&rgCLSID + m, (LPUNKNOWN)&g_rgcfModule + m, 4u, 1u, &g_rghRegClass + m) )
      {
        v62 = 1;
        cbData = 1;
        goto LABEL_214;
      }
    }
    goto LABEL_214;
  }
LABEL_215:
  v65 = 0;
  NtCurrentPeb()->ProcessParameters->Flags = NtCurrentPeb()->ProcessParameters->Flags | 0x80000;
  v153 = 0;
  while ( 2 )
  {
    v66 = *i;
    if ( (unsigned __int16)(*i - 48) <= 9u )
    {
      v67 = *i;
      v68 = v66 - 48;
LABEL_220:
      v69 = v68;
      v70 = 16 * v67;
      if ( (v65 & 1) == 0 )
        v69 = v70;
      if ( v65 >= 32 )
      {
        v73 = (wchar_t *)L"ServerMain (CA): Wrong command line";
        goto LABEL_225;
      }
      v71 = v65;
      v72 = v65++ >> 31;
      *((_BYTE *)&pHandles[-2] + (int)(__SPAIR64__(v72, v71) / 2)) = v69
                                                                   | *((_BYTE *)&pHandles[-2]
                                                                     + (int)(__SPAIR64__(v72, v71) / 2));
      ++i;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v66 - 65) <= 5u )
  {
    v67 = v66 + 9;
    v68 = v66 - 55;
    goto LABEL_220;
  }
  if ( v65 != 32 )
  {
    v73 = L"ServerMain (CA): Parsing command line failed";
    goto LABEL_225;
  }
  v111 = 0;
  v116 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  if ( !v66 || (++i, *i != 67) )
  {
    if ( *i == 85 )
    {
      v112 = 1;
      v77 = 1;
      goto LABEL_234;
    }
    v112 = 0;
    switch ( *i )
    {
      case 'A':
        v2 = 1;
        v116 = 1;
        goto LABEL_234;
      case 'M':
        v75 = 1;
        break;
      case 'R':
        break;
      case 'E':
        goto LABEL_248;
      default:
        goto LABEL_234;
    }
    v111 = 1;
    v76 = 1;
LABEL_248:
    v82 = (char *)OpenEventW(0x100000u, 0, i + 2);
    v83 = v82;
    if ( (unsigned __int64)(v82 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v84 = WaitForSingleObject(v82, 0xFFFFFFFF);
      CloseHandle(v83);
      if ( !v84 )
        goto LABEL_234;
      v80 = v84;
      v81 = (BYTE *)L"ServerMain (CA): Wait on synchronization event failed";
LABEL_251:
      ReportErrorToDebugOutput(v81, v80);
      goto LABEL_252;
    }
    LastError = GetLastError();
    ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): Open synchronization event failed", LastError);
    goto LABEL_356;
  }
  v112 = 1;
LABEL_234:
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 2u, 1, &TokenHandle) )
  {
    TokenHandle = (void *)-1LL;
    v79 = GetLastError();
    if ( v79 != 1008 )
    {
      v80 = v79;
      v81 = (BYTE *)L"ServerMain (CA): Access to token failed";
      goto LABEL_251;
    }
  }
  if ( !v75 )
    RevertToSelf();
  RegCloseKey(HKEY_CURRENT_USER);
  RegEnumKeyW(HKEY_CURRENT_USER, 0, 0, 0);
  if ( v75 )
    RevertToSelf();
  ReturnLength = 0;
  v85 = g_fWoW;
  pSid2 = 0;
  *(_QWORD *)cchCount2 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, (PHANDLE)cchCount2) )
  {
    if ( !GetLocalSystemSID((char **)&pSid2)
      && GetTokenInformation(*(HANDLE *)cchCount2, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      if ( EqualSid(TokenInformation[0], pSid2) )
      {
        if ( g_fWoW )
          v85 = 2 * (v76 ^ 1) + 3;
        else
          v85 = v76 != 0 ? 2 : 4;
      }
      else
      {
        v85 = g_fWoW;
      }
    }
    CloseHandle(*(HANDLE *)cchCount2);
  }
  else
  {
    v87 = GetLastError();
    memset_0(&v142, 0, 0x208u);
    StringCchPrintfW((unsigned __int16 *)&v142, 0x104u, L"OpenProcessToken failed with %d", v87);
  }
  if ( v77 )
  {
    if ( v85 == 1 )
    {
      v85 = 9;
      goto LABEL_272;
    }
    if ( !v85 )
    {
      v85 = 8;
      goto LABEL_272;
    }
    v73 = L"ServerMain (CA): Error: icacContext in CA server should be EEUI but is not any impersonated type";
LABEL_225:
    ReportErrorToDebugOutput((BYTE *)v73, 0x57u);
LABEL_226:
    if ( v134 > 260 )
      GlobalFree(hMem);
    v74 = (int)v131 <= 1;
    hMem = v136;
    v134 = 260;
    goto LABEL_371;
  }
LABEL_272:
  if ( v2 )
  {
    if ( v85 )
    {
      if ( v85 != 1 )
      {
        v73 = L"ServerMain (CA): Error: icacContext in CA server should be AISImpersonated but is not any impersonated type";
        goto LABEL_225;
      }
      v85 = 7;
    }
    else
    {
      v85 = 6;
    }
    Type = 256;
LABEL_285:
    v88 = 2;
  }
  else
  {
    Type = 256;
    if ( v85 - 2 > 3 && v85 < 9 )
      goto LABEL_285;
    v88 = 3;
    if ( v85 == 9 )
      goto LABEL_285;
  }
  appended = GetSecurityDescriptor(&lpString2, &Type, v88);
  if ( appended )
  {
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
    ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): Error: Access to SD", appended);
    goto LABEL_76;
  }
  dwAbsoluteSecurityDescriptorSize = Type;
  dwDaclSize = Type;
  dwSaclSize = Type;
  dwOwnerSize = Type;
  dwPrimaryGroupSize = Type;
  CTempBuffer<char,256>::CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
  CTempBuffer<char,256>::CTempBuffer<char,256>(&VersionInformation);
  CTempBuffer<char,256>::CTempBuffer<char,256>(pSacl);
  CTempBuffer<char,256>::CTempBuffer<char,256>(pOwner);
  CTempBuffer<char,256>::CTempBuffer<char,256>(pPrimaryGroup);
  if ( MakeAbsoluteSD(
         &lpString2,
         pAbsoluteSecurityDescriptor[0],
         &dwAbsoluteSecurityDescriptorSize,
         *(PACL *)&VersionInformation.dwOSVersionInfoSize,
         &dwDaclSize,
         pSacl[0],
         &dwSaclSize,
         pOwner[0],
         &dwOwnerSize,
         pPrimaryGroup[0],
         &dwPrimaryGroupSize) )
  {
    v89 = ((__int64 (__fastcall *)(PSECURITY_DESCRIPTOR, __int64, _QWORD, _QWORD, int, int, _QWORD, _DWORD, _QWORD))OLE32::CoInitializeSecurity)(
            pAbsoluteSecurityDescriptor[0],
            0xFFFFFFFFLL,
            0,
            0,
            3,
            2,
            0,
            0,
            0);
    if ( v89 )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): CoInitializeSecurity failed", v89);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pPrimaryGroup);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pOwner);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pSacl);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(&VersionInformation);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
      goto LABEL_226;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v91 = GetLastError();
      ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): Error: Watch for the shutdown signal", v91);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pPrimaryGroup);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pOwner);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pSacl);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(&VersionInformation);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
      if ( v134 > 260 )
        GlobalFree(hMem);
      v134 = 260;
      hMem = v136;
      goto LABEL_370;
    }
    v92 = CreateEventW(0, 0, 0, 0);
    if ( !v92 )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v93 = GetLastError();
      ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): Error: Watch for change-of-owning-process signal", v93);
      goto LABEL_308;
    }
    hKey = 0;
    pSid2 = 0;
    v146 = 0;
    lpString = (LPCWSTR)CreateMsiServerProxyForCAServer();
    v94 = lpString;
    if ( !lpString )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v95 = (wchar_t *)L"ServerMain (CA): Connection to Service failed.";
      goto LABEL_313;
    }
    dwProcessId = 0;
    v128 = 0;
    CustomActionServer = CreateCustomActionServer();
    v98 = CustomActionServer;
    if ( !CustomActionServer )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v95 = L"ServerMain (CA): Create Custom Action Server failed.";
      goto LABEL_313;
    }
    QueryInterface = CustomActionServer->lpVtbl->QueryInterface;
    if ( pSid2 )
      (*(void (__fastcall **)(PSID))(*(_QWORD *)pSid2 + 16LL))(pSid2);
    pSid2 = 0;
    ((void (__fastcall *)(struct IUnknown *, GUID *, PSID *))QueryInterface)(v98, &IID_IMsiCustomAction, &pSid2);
    ((void (__fastcall *)(struct IUnknown *))v98->lpVtbl->Release)(v98);
    v121 = v85;
    v100 = *(unsigned int (__fastcall **)(LPCWSTR, unsigned int *, __int128 *, __int64, PSID, DWORD *, __int64 *, int *))(*(_QWORD *)v94 + 112LL);
    if ( v146 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
    v146 = 0;
    if ( v100(v94, &v121, &v153, 16, pSid2, &dwProcessId, &v146, &v128) )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v95 = L"ServerMain (CA): Process not registered with service.";
      goto LABEL_313;
    }
    v101 = OpenProcess(0x100000u, 0, dwProcessId);
    if ( !v101 )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v96 = GetLastError();
      v95 = (wchar_t *)L"ServerMain (CA): Could not open synchronization handle.";
      goto LABEL_314;
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64))OLE32::CoIsHandlerConnected)(v146) )
    {
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      v95 = L"ServerMain (CA): Connect to remote object failed.";
      goto LABEL_313;
    }
    (**(void (__fastcall ***)(PSID, GUID *, HKEY *))pSid2)(pSid2, &IID_IMsiCustomActionLocalConfig, &hKey);
    if ( v85 != v121 || v85 == 8 || (v102 = 0, v85 == 9) )
      v102 = &v121;
    (*(void (__fastcall **)(HKEY, unsigned int *, __int128 *))(*(_QWORD *)hKey + 320LL))(hKey, v102, &v153);
    (*(void (__fastcall **)(HKEY, HANDLE))(*(_QWORD *)hKey + 336LL))(hKey, EventW);
    (*(void (__fastcall **)(HKEY, HANDLE))(*(_QWORD *)hKey + 344LL))(hKey, v92);
    LOBYTE(v103) = v116;
    LOBYTE(v104) = v112;
    LOBYTE(lpData) = v111;
    v105 = (*(__int64 (__fastcall **)(HKEY, _QWORD, __int64, __int64, int, int, void *))(*(_QWORD *)hKey + 328LL))(
             hKey,
             dwProcessId,
             v104,
             v103,
             lpData,
             v128,
             TokenHandle);
    if ( TokenHandle != (void *)-1LL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = (void *)-1LL;
    }
    if ( v105 )
    {
      v95 = L"ServerMain (CA): Impersonation token not saved.";
LABEL_313:
      v96 = 1601;
LABEL_314:
      ReportErrorToDebugOutput((BYTE *)v95, v96);
      CComPointer<IMsiServer>::~CComPointer<IMsiServer>(&lpString);
      CComPointer<IMsiServer>::~CComPointer<IMsiServer>(&v146);
      CComPointer<IMsiServer>::~CComPointer<IMsiServer>(&pSid2);
LABEL_308:
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pPrimaryGroup);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pOwner);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pSacl);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(&VersionInformation);
      CTempBuffer<char,256>::~CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
LABEL_252:
      if ( v134 > 260 )
        GlobalFree(hMem);
      hMem = v136;
LABEL_369:
      v134 = 260;
LABEL_370:
      v74 = (int)v131 <= 1;
LABEL_371:
      if ( !v74 )
        GlobalFree(v130);
      return 1601;
    }
    (*(void (__fastcall **)(HKEY, __int64))(*(_QWORD *)hKey + 312LL))(hKey, v146);
    CComPointer<IMsiServer>::~CComPointer<IMsiServer>(&lpString);
    CComPointer<IMsiServer>::~CComPointer<IMsiServer>(&v146);
    CComPointer<IMsiServer>::~CComPointer<IMsiServer>(&pSid2);
    pHandles[0] = v101;
    memset(&Msg, 0, sizeof(Msg));
    pHandles[1] = EventW;
    *(_QWORD *)&v155 = v92;
    while ( 1 )
    {
      while ( 1 )
      {
        v106 = MsgWaitForMultipleObjects(3u, pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
        if ( !v106 )
          goto LABEL_360;
        if ( v106 == 1 )
        {
          CloseHandle(EventW);
LABEL_360:
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
          CloseHandle(v101);
          CTempBuffer<char,256>::~CTempBuffer<char,256>(pPrimaryGroup);
          CTempBuffer<char,256>::~CTempBuffer<char,256>(pOwner);
          CTempBuffer<char,256>::~CTempBuffer<char,256>(pSacl);
          CTempBuffer<char,256>::~CTempBuffer<char,256>(&VersionInformation);
          CTempBuffer<char,256>::~CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
          v62 = cbData;
          goto LABEL_361;
        }
        if ( v106 == 2 )
          break;
        if ( v106 != 3 )
          goto LABEL_360;
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message == 18 )
            goto LABEL_360;
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      CloseHandle(v101);
      LODWORD(lpString) = 0;
      (*(void (__fastcall **)(HKEY, LPCWSTR *))(*(_QWORD *)hKey + 352LL))(hKey, &lpString);
      v107 = OpenProcess(0x100000u, 0, (DWORD)lpString);
      v101 = v107;
      if ( !v107 )
        break;
      pHandles[0] = v107;
    }
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
    v108 = GetLastError();
    ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): Could not open synchronization handle.", v108);
    CTempBuffer<char,256>::~CTempBuffer<char,256>(pPrimaryGroup);
    CTempBuffer<char,256>::~CTempBuffer<char,256>(pOwner);
    CTempBuffer<char,256>::~CTempBuffer<char,256>(pSacl);
    CTempBuffer<char,256>::~CTempBuffer<char,256>(&VersionInformation);
    CTempBuffer<char,256>::~CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
LABEL_356:
    if ( v134 > 260 )
      GlobalFree(hMem);
    v74 = (int)v131 <= 1;
    hMem = v136;
    v134 = 260;
    goto LABEL_371;
  }
  appended = GetLastError();
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  ReportErrorToDebugOutput((BYTE *)L"ServerMain (CA): Error: Format SD", appended);
  CTempBuffer<char,256>::~CTempBuffer<char,256>(pPrimaryGroup);
  CTempBuffer<char,256>::~CTempBuffer<char,256>(pOwner);
  CTempBuffer<char,256>::~CTempBuffer<char,256>(pSacl);
  CTempBuffer<char,256>::~CTempBuffer<char,256>(&VersionInformation);
  CTempBuffer<char,256>::~CTempBuffer<char,256>(pAbsoluteSecurityDescriptor);
LABEL_76:
  if ( v134 > 260 )
    GlobalFree(hMem);
  v134 = 260;
  hMem = v136;
  if ( (int)v131 > 1 )
    GlobalFree(v130);
  return appended;
}

```

## disassembly

```asm
0x1400011e4  push    rbp
0x1400011e6  push    rbx
0x1400011e7  push    rsi
0x1400011e8  push    rdi
0x1400011e9  push    r12
0x1400011eb  push    r13
0x1400011ed  push    r14
0x1400011ef  push    r15
0x1400011f1  lea     rbp, [rsp-23B8h]
0x1400011f9  mov     eax, 24B8h
0x1400011fe  call    _alloca_probe
0x140001203  sub     rsp, rax
0x140001206  mov     rax, cs:__security_cookie
0x14000120d  xor     rax, rsp
0x140001210  mov     [rbp+23F0h+var_50], rax
0x140001217  mov     rsi, rcx
0x14000121a  lea     rax, [rbp+23F0h+var_23F0]
0x14000121e  mov     r15d, 1
0x140001224  mov     [rbp+23F0h+var_2400], rax
0x140001228  lea     rcx, [rbp+23F0h+VersionInformation.dwMajorVersion]; void *
0x14000122f  mov     [rbp+23F0h+var_23F8], r15d
0x140001233  xor     edx, edx; Val
0x140001235  mov     r8d, 118h; Size
0x14000123b  call    memset_0
0x140001240  lea     rcx, [rbp+23F0h+VersionInformation]; lpVersionInformation
0x140001247  mov     [rbp+23F0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140001251  call    cs:__imp_GetVersionExW
0x140001257  xor     r13d, r13d
0x14000125a  test    eax, eax
0x14000125c  jz      short loc_14000126C
0x14000125e  mov     cs:?g_fWoW@@3_NA, r15b; bool g_fWoW
0x140001265  mov     cs:?g_fWinNT64@@3_NA, r15b; bool g_fWinNT64
0x14000126c  mov     rax, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140001273  mov     r12d, 104h
0x140001279  mov     [rax], r13w
0x14000127d  mov     rax, cs:?g_szTransforms@@3V?$CAPITempBuffer@G$0EAA@@@A; CAPITempBuffer<ushort,1024> g_szTransforms
0x140001284  mov     [rax], r13w
0x140001288  lea     rax, [rbp+23F0h+var_23D0]
0x14000128c  mov     [rbp+23F0h+hMem], rax
0x140001290  mov     [rbp+23F0h+var_23D8], r12d
0x140001294  call    cs:__imp_GetCommandLineW
0x14000129a  mov     edx, 22h ; '"'
0x14000129f  mov     rbx, rax
0x1400012a2  lea     r14d, [rdx-2]
0x1400012a6  cmp     [rax], dx
0x1400012a9  jnz     short loc_1400012B4
0x1400012ab  add     rax, 2
0x1400012af  mov     rbx, rax
0x1400012b2  jmp     short loc_1400012B8
0x1400012b4  movzx   edx, r14w
0x1400012b8  movzx   ecx, word ptr [rbx]
0x1400012bb  test    cx, cx
0x1400012be  jz      short loc_1400012D9
0x1400012c0  lea     rbx, [rax+2]
0x1400012c4  mov     rdi, rbx
0x1400012c7  cmp     cx, dx
0x1400012ca  jz      short loc_1400012DC
0x1400012cc  movzx   ecx, word ptr [rbx]
0x1400012cf  mov     rax, rbx
0x1400012d2  test    cx, cx
0x1400012d5  jnz     short loc_1400012C0
0x1400012d7  jmp     short loc_1400012DC
0x1400012d9  mov     rdi, rax
0x1400012dc  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1400012e1  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hInstance
0x1400012e8  call    cs:__imp_GetStdHandle
0x1400012ee  mov     cs:?g_hStdOut@@3PEAXEA, rax; void * g_hStdOut
0x1400012f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400012f9  jz      short loc_140001309
0x1400012fb  mov     rcx, rax; hFile
0x1400012fe  call    cs:__imp_GetFileType
0x140001304  cmp     eax, 3
0x140001307  jz      short loc_140001310
0x140001309  mov     cs:?g_hStdOut@@3PEAXEA, r13; void * g_hStdOut
0x140001310  mov     esi, 7FEh
0x140001315  mov     [rbp+23F0h+ValueName], r13w
0x14000131d  mov     r8d, esi; Size
0x140001320  lea     rcx, [rbp+23F0h+var_184E]; void *
0x140001327  xor     edx, edx; Val
0x140001329  call    memset_0
0x14000132e  mov     r8d, esi; Size
0x140001331  mov     [rbp+23F0h+pszSrc], r13w
0x140001339  xor     edx, edx; Val
0x14000133b  lea     rcx, [rbp+23F0h+var_104E]; void *
0x140001342  call    memset_0
0x140001347  mov     ecx, 9
0x14000134c  mov     cs:?g_fCustomActionServer@@3W4Bool@@A, r13d; Bool g_fCustomActionServer
0x140001353  movzx   eax, word ptr [rbx]
0x140001356  cmp     ax, r14w
0x14000135a  jz      short loc_140001361
0x14000135c  cmp     ax, cx
0x14000135f  jnz     short loc_14000136A
0x140001361  lea     rbx, [rdi+2]
0x140001365  mov     rdi, rbx
0x140001368  jmp     short loc_140001353
0x14000136a  sub     ax, 2Dh ; '-'
0x14000136e  mov     esi, 0FFFDh
0x140001373  test    si, ax
0x140001376  jnz     loc_14000151A
0x14000137c  lea     rax, [rdi+2]
0x140001380  test    rax, rax
0x140001383  jz      loc_14000151A
0x140001389  movzx   eax, word ptr [rbx+2]
0x14000138d  or      ax, r14w
0x140001391  cmp     ax, 60h ; '`'
0x140001395  jnz     loc_14000151A
0x14000139b  lea     rax, [rdi+4]
0x14000139f  lea     rcx, [rsp+24F0h+lpString]; unsigned __int16 **
0x1400013a4  mov     [rsp+24F0h+lpString], rax
0x1400013a9  call    ?SkipWhiteSpace@@YAGAEAPEBG@Z; SkipWhiteSpace(ushort const * &)
0x1400013ae  lea     rcx, [rbp+23F0h+ValueName]
0x1400013b5  mov     r8d, 400h; unsigned int
0x1400013bb  mov     [rsp+24F0h+pSid2], rcx
0x1400013c0  lea     rdx, [rsp+24F0h+pSid2]; unsigned __int16 **
0x1400013c5  lea     rcx, [rsp+24F0h+lpString]; unsigned __int16 **
0x1400013ca  call    ?ParseValue@@YA_NAEAPEBGAEAPEAGI@Z; ParseValue(ushort const * &,ushort * &,uint)
0x1400013cf  test    al, al
0x1400013d1  jnz     short loc_1400013F5
0x1400013d3  xor     edx, edx; unsigned __int16 *
0x1400013d5  xor     ecx, ecx; unsigned __int16 *
0x1400013d7  call    ?ShowHelp@@YAHPEBG0@Z; ShowHelp(ushort const *,ushort const *)
0x1400013dc  cmp     [rbp+23F0h+var_23D8], r12d
0x1400013e0  jle     short loc_1400013EC
0x1400013e2  mov     rcx, [rbp+23F0h+hMem]; hMem
0x1400013e6  call    cs:__imp_GlobalFree
0x1400013ec  cmp     [rbp+23F0h+var_23F8], r15d
0x1400013f0  jmp     loc_140001F82
0x1400013f5  mov     eax, [rbp+23F0h+var_23D8]
0x1400013f8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400013ff  add     eax, eax
0x140001401  mov     [rsp+24F0h+hKey], r13
0x140001406  mov     [rbp+23F0h+cbData], eax
0x140001409  lea     rax, [rsp+24F0h+hKey]
0x14000140e  mov     [rsp+24F0h+lpData], rax; HKEY *
0x140001413  mov     [rbp+23F0h+Type], r13d
0x140001417  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x14000141c  test    eax, eax
0x14000141e  jnz     loc_1400014E7
0x140001424  mov     rax, [rbp+23F0h+hMem]
0x140001428  lea     rcx, [rbp+23F0h+cbData]
0x14000142c  mov     [rsp+24F0h+lpcbData], rcx; lpcbData
0x140001431  lea     r9, [rbp+23F0h+Type]; lpType
0x140001435  mov     rcx, [rsp+24F0h+hKey]; hKey
0x14000143a  lea     rdx, [rbp+23F0h+ValueName]; lpValueName
0x140001441  xor     r8d, r8d; lpReserved
0x140001444  mov     [rsp+24F0h+lpData], rax; lpData
0x140001449  call    cs:__imp_RegQueryValueExW
0x14000144f  mov     ebx, eax
0x140001451  cmp     eax, 0EAh
0x140001456  jnz     short loc_1400014A7
0x140001458  mov     edx, [rbp+23F0h+cbData]
0x14000145b  lea     rcx, [rbp+23F0h+hMem]
0x14000145f  shr     edx, 1
0x140001461  call    ?SetSize@?$CAPITempBuffer@G$0BAE@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,260>::SetSize(int,bool)
0x140001466  test    al, al
0x140001468  jnz     short loc_14000147A
0x14000146a  mov     rcx, [rsp+24F0h+hKey]; hKey
0x14000146f  call    cs:__imp_RegCloseKey
0x140001475  jmp     loc_140001560
0x14000147a  mov     rax, [rbp+23F0h+hMem]
0x14000147e  lea     rcx, [rbp+23F0h+cbData]
0x140001482  mov     [rsp+24F0h+lpcbData], rcx; lpcbData
0x140001487  lea     r9, [rbp+23F0h+Type]; lpType
0x14000148b  mov     rcx, [rsp+24F0h+hKey]; hKey
0x140001490  lea     rdx, [rbp+23F0h+ValueName]; lpValueName
0x140001497  xor     r8d, r8d; lpReserved
0x14000149a  mov     [rsp+24F0h+lpData], rax; lpData
0x14000149f  call    cs:__imp_RegQueryValueExW
0x1400014a5  mov     ebx, eax
0x1400014a7  mov     rcx, [rsp+24F0h+hKey]; hKey
0x1400014ac  call    cs:__imp_RegCloseKey
0x1400014b2  test    ebx, ebx
0x1400014b4  jnz     short loc_1400014E7
0x1400014b6  cmp     [rbp+23F0h+Type], r15d
0x1400014ba  jnz     short loc_1400014E7
0x1400014bc  mov     rbx, [rbp+23F0h+hMem]
0x1400014c0  mov     r8d, 9
0x1400014c6  movzx   esi, word ptr [rbx]
0x1400014c9  mov     rax, rbx
0x1400014cc  mov     [rsp+24F0h+lpString], rbx
0x1400014d1  cmp     si, r14w
0x1400014d5  jz      short loc_1400014E1
0x1400014d7  cmp     si, r8w
0x1400014db  jnz     loc_140001A83
0x1400014e1  lea     rbx, [rax+2]
0x1400014e5  jmp     short loc_1400014C6
0x1400014e7  cmp     [rbp+23F0h+var_23D8], r12d
0x1400014eb  jle     short loc_1400014F7
0x1400014ed  mov     rcx, [rbp+23F0h+hMem]; hMem
0x1400014f1  call    cs:__imp_GlobalFree
0x1400014f7  lea     rax, [rbp+23F0h+var_23D0]
0x1400014fb  mov     [rbp+23F0h+var_23D8], r12d
0x1400014ff  mov     [rbp+23F0h+hMem], rax
0x140001503  cmp     [rbp+23F0h+var_23F8], r15d
0x140001507  jle     short loc_140001513
0x140001509  mov     rcx, [rbp+23F0h+var_2400]; hMem
0x14000150d  call    cs:__imp_GlobalFree
0x140001513  xor     eax, eax
0x140001515  jmp     loc_140001C03
0x14000151a  lea     r8, [rsp+24F0h+hKey]; unsigned __int64 *
0x14000151f  mov     [rsp+24F0h+hKey], r13
0x140001524  mov     rcx, rbx; unsigned __int16 *
0x140001527  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000152c  test    eax, eax
0x14000152e  jns     short loc_14000154D
0x140001530  cmp     [rbp+23F0h+var_23D8], r12d
0x140001534  jle     short loc_140001540
0x140001536  mov     rcx, [rbp+23F0h+hMem]; hMem
0x14000153a  call    cs:__imp_GlobalFree
0x140001540  lea     rax, [rbp+23F0h+var_23D0]
0x140001544  mov     [rbp+23F0h+hMem], rax
0x140001548  jmp     loc_1400019FA
0x14000154d  mov     edx, dword ptr [rsp+24F0h+hKey]
0x140001551  lea     rcx, [rbp+23F0h+hMem]
0x140001555  inc     edx
0x140001557  call    ?SetSize@?$CAPITempBuffer@G$0BAE@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,260>::SetSize(int,bool)
0x14000155c  test    al, al
0x14000155e  jnz     short loc_140001596
0x140001560  cmp     [rbp+23F0h+var_23D8], r12d
0x140001564  jle     short loc_140001570
0x140001566  mov     rcx, [rbp+23F0h+hMem]; hMem
0x14000156a  call    cs:__imp_GlobalFree
0x140001570  lea     rax, [rbp+23F0h+var_23D0]
0x140001574  mov     [rbp+23F0h+var_23D8], r12d
0x140001578  mov     [rbp+23F0h+hMem], rax
0x14000157c  cmp     [rbp+23F0h+var_23F8], r15d
0x140001580  jle     short loc_14000158C
0x140001582  mov     rcx, [rbp+23F0h+var_2400]; hMem
0x140001586  call    cs:__imp_GlobalFree
0x14000158c  mov     eax, 0Eh
0x140001591  jmp     loc_140001C03
0x140001596  mov     rax, [rbp+23F0h+hMem]
0x14000159a  lea     rcx, aPackage; "package"
0x1400015a1  lea     r8, [rbp+23F0h+cchCount2]; unsigned __int64 *
0x1400015a5  mov     [rbp+23F0h+var_19E8], r13
0x1400015ac  mov     [rbp+23F0h+var_19E0], r13b
0x1400015b3  mov     [rbp+23F0h+var_19D0], r13
0x1400015ba  mov     [rax], r13w
0x1400015be  lea     rax, aUpdate; "update"
0x1400015c5  movsd   xmm0, qword ptr cs:aPatch; "PATCH="
0x1400015cd  movups  xmm1, xmmword ptr cs:aMsipatchremove+10h; "REMOVE="
0x1400015d4  mov     [rbp+23F0h+lpString2], rax
0x1400015db  lea     rax, aUninstall; "uninstall"
0x1400015e2  mov     [rbp+23F0h+var_19D8], rax
0x1400015e9  lea     rax, aI; "/i"
0x1400015f0  mov     [rbp+23F0h+var_19B8], rax
0x1400015f7  lea     rax, aHelp; "help"
0x1400015fe  mov     [rbp+23F0h+var_19A8], rax
0x140001605  lea     rax, asc_14000BE04; "/h"
0x14000160c  mov     [rbp+23F0h+var_19A0], rax
0x140001613  lea     rax, aQuiet; "quiet"
0x14000161a  mov     [rbp+23F0h+var_1990], rax
0x140001621  lea     rax, aQn; "/qn"
0x140001628  mov     [rbp+23F0h+var_1988], rax
0x14000162f  lea     rax, aPassive; "passive"
0x140001636  mov     [rbp+23F0h+var_1978], rax
0x14000163d  lea     rax, aQbRebootprompt; "/qb!- REBOOTPROMPT=S"
0x140001644  mov     [rbp+23F0h+var_1970], rax
0x14000164b  lea     rax, aNorestart; "norestart"
0x140001652  mov     [rbp+23F0h+var_1960], rax
0x140001659  lea     rax, aRebootReallysu; "REBOOT=ReallySuppress"
0x140001660  mov     [rbp+23F0h+var_1958], rax
0x140001667  lea     rax, aForcerestart; "forcerestart"
0x14000166e  mov     [rbp+23F0h+var_1948], rax
0x140001675  lea     rax, aRebootForce; "REBOOT=Force"
0x14000167c  mov     [rbp+23F0h+var_1940], rax
0x140001683  lea     rax, aPromptrestart; "promptrestart"
0x14000168a  mov     [rbp+23F0h+var_1930], rax
0x140001691  lea     rax, aRebootprompt; "REBOOTPROMPT=\"\""
0x140001698  mov     [rbp+23F0h+var_1928], rax
0x14000169f  lea     rax, aLog; "log"
0x1400016a6  mov     [rbp+23F0h+var_1918], rax
0x1400016ad  lea     rax, asc_14000BF38; "/l*"
0x1400016b4  mov     [rbp+23F0h+var_1910], rax
0x1400016bb  mov     eax, dword ptr cs:asc_14000BF40; "/x"
0x1400016c1  mov     [rbp+23F0h+ReturnLength], eax
0x1400016c7  movzx   eax, word ptr cs:asc_14000BF40+4; ""
0x1400016ce  mov     [rbp+23F0h+var_1A2C], ax
0x1400016d5  mov     eax, dword ptr cs:aP; "/p"
0x1400016db  mov     [rbp+23F0h+dwAbsoluteSecurityDescriptorSize], eax
0x1400016e1  movzx   eax, word ptr cs:aP+4; ""
0x1400016e8  mov     [rbp+23F0h+var_1A24], ax
0x1400016ef  mov     eax, dword ptr cs:aPatch+8; "H="
0x1400016f5  mov     [rbp+23F0h+var_1A38], eax
0x1400016fb  movzx   eax, word ptr cs:aPatch+0Ch; ""
0x140001702  movsd   [rbp+23F0h+var_1A40], xmm0
0x14000170a  movups  xmm0, xmmword ptr cs:aMsipatchremove; "MSIPATCHREMOVE="
0x140001711  mov     [rbp+23F0h+var_1A34], ax
0x140001718  mov     [rbp+23F0h+var_19C8], r13b
0x14000171f  mov     [rbp+23F0h+var_19C0], rcx
0x140001726  mov     [rbp+23F0h+var_19B0], r15b
0x14000172d  mov     [rbp+23F0h+var_1998], r15b
0x140001734  mov     [rbp+23F0h+var_1980], r15b
0x14000173b  mov     [rbp+23F0h+var_1968], r15b
0x140001742  mov     [rbp+23F0h+var_1950], r15b
0x140001749  mov     [rbp+23F0h+var_1938], r15b
0x140001750  mov     [rbp+23F0h+var_1920], r15b
0x140001757  mov     [rbp+23F0h+var_1908], r15b
0x14000175e  movups  xmmword ptr [rbp+23F0h+pHandles], xmm0
0x140001765  mov     qword ptr [rbp+23F0h+cchCount2], r13
  ... truncated ...
```
