# FreeDriverInfo8(_DRIVER_INFO_8W *)

- ea: `0x18004032c`
- end: `0x18004047b`
- name: `?FreeDriverInfo8@@YAXPEAU_DRIVER_INFO_8W@@@Z`
- size: `335`
- prototype: `void __fastcall(struct _DRIVER_INFO_8W *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800288e4`
- `0x1800402c8`

## callees

- `0x18004032c`

## import_xrefs

- `SPOOLSS!DllFreeSplMem` at `0x180040346`
- `SPOOLSS!DllFreeSplMem` at `0x180040355`
- `SPOOLSS!DllFreeSplMem` at `0x180040364`
- `SPOOLSS!DllFreeSplMem` at `0x180040373`
- `SPOOLSS!DllFreeSplMem` at `0x180040382`
- `SPOOLSS!DllFreeSplMem` at `0x180040391`
- `SPOOLSS!DllFreeSplMem` at `0x1800403a0`
- `SPOOLSS!DllFreeSplMem` at `0x1800403af`
- `SPOOLSS!DllFreeSplMem` at `0x1800403be`
- `SPOOLSS!DllFreeSplMem` at `0x1800403cd`
- `SPOOLSS!DllFreeSplMem` at `0x1800403dc`
- `SPOOLSS!DllFreeSplMem` at `0x1800403eb`
- `SPOOLSS!DllFreeSplMem` at `0x1800403fa`
- `SPOOLSS!DllFreeSplMem` at `0x18004040c`
- `SPOOLSS!DllFreeSplMem` at `0x18004041e`
- `SPOOLSS!DllFreeSplMem` at `0x180040430`
- `SPOOLSS!DllFreeSplMem` at `0x180040442`
- `SPOOLSS!DllFreeSplMem` at `0x180040454`
- `SPOOLSS!DllFreeSplMem` at `0x180040466`
- `SPOOLSS!DllFreeSplMem` at `0x18004046f`
- `SPOOLSS!DllFreeSplMem` at `0x180040346`
- `SPOOLSS!DllFreeSplMem` at `0x180040355`
- `SPOOLSS!DllFreeSplMem` at `0x180040364`
- `SPOOLSS!DllFreeSplMem` at `0x180040373`
- `SPOOLSS!DllFreeSplMem` at `0x180040382`
- `SPOOLSS!DllFreeSplMem` at `0x180040391`
- `SPOOLSS!DllFreeSplMem` at `0x1800403a0`
- `SPOOLSS!DllFreeSplMem` at `0x1800403af`
- `SPOOLSS!DllFreeSplMem` at `0x1800403be`
- `SPOOLSS!DllFreeSplMem` at `0x1800403cd`
- `SPOOLSS!DllFreeSplMem` at `0x1800403dc`
- `SPOOLSS!DllFreeSplMem` at `0x1800403eb`
- `SPOOLSS!DllFreeSplMem` at `0x1800403fa`
- `SPOOLSS!DllFreeSplMem` at `0x18004040c`
- `SPOOLSS!DllFreeSplMem` at `0x18004041e`
- `SPOOLSS!DllFreeSplMem` at `0x180040430`
- `SPOOLSS!DllFreeSplMem` at `0x180040442`
- `SPOOLSS!DllFreeSplMem` at `0x180040454`
- `SPOOLSS!DllFreeSplMem` at `0x180040466`
- `SPOOLSS!DllFreeSplMem` at `0x18004046f`

## pseudocode

```c
void __fastcall FreeDriverInfo8(struct _DRIVER_INFO_8W *a1)
{
  LPWSTR pName; // rcx
  LPWSTR pEnvironment; // rcx
  LPWSTR pDriverPath; // rcx
  LPWSTR pConfigFile; // rcx
  LPWSTR pHelpFile; // rcx
  LPWSTR pDataFile; // rcx
  LPWSTR pDependentFiles; // rcx
  LPWSTR pMonitorName; // rcx
  LPWSTR pDefaultDataType; // rcx
  LPWSTR pszzPreviousNames; // rcx
  LPWSTR pszMfgName; // rcx
  LPWSTR pszOEMUrl; // rcx
  LPWSTR pszHardwareID; // rcx
  LPWSTR pszProvider; // rcx
  LPWSTR pszPrintProcessor; // rcx
  LPWSTR pszVendorSetup; // rcx
  LPWSTR pszzColorProfiles; // rcx
  LPWSTR pszInfPath; // rcx
  LPWSTR pszzCoreDriverDependencies; // rcx

  if ( a1 )
  {
    pName = a1->pName;
    if ( pName )
      DllFreeSplMem(pName);
    pEnvironment = a1->pEnvironment;
    if ( pEnvironment )
      DllFreeSplMem(pEnvironment);
    pDriverPath = a1->pDriverPath;
    if ( pDriverPath )
      DllFreeSplMem(pDriverPath);
    pConfigFile = a1->pConfigFile;
    if ( pConfigFile )
      DllFreeSplMem(pConfigFile);
    pHelpFile = a1->pHelpFile;
    if ( pHelpFile )
      DllFreeSplMem(pHelpFile);
    pDataFile = a1->pDataFile;
    if ( pDataFile )
      DllFreeSplMem(pDataFile);
    pDependentFiles = a1->pDependentFiles;
    if ( pDependentFiles )
      DllFreeSplMem(pDependentFiles);
    pMonitorName = a1->pMonitorName;
    if ( pMonitorName )
      DllFreeSplMem(pMonitorName);
    pDefaultDataType = a1->pDefaultDataType;
    if ( pDefaultDataType )
      DllFreeSplMem(pDefaultDataType);
    pszzPreviousNames = a1->pszzPreviousNames;
    if ( pszzPreviousNames )
      DllFreeSplMem(pszzPreviousNames);
    pszMfgName = a1->pszMfgName;
    if ( pszMfgName )
      DllFreeSplMem(pszMfgName);
    pszOEMUrl = a1->pszOEMUrl;
    if ( pszOEMUrl )
      DllFreeSplMem(pszOEMUrl);
    pszHardwareID = a1->pszHardwareID;
    if ( pszHardwareID )
      DllFreeSplMem(pszHardwareID);
    pszProvider = a1->pszProvider;
    if ( pszProvider )
      DllFreeSplMem(pszProvider);
    pszPrintProcessor = a1->pszPrintProcessor;
    if ( pszPrintProcessor )
      DllFreeSplMem(pszPrintProcessor);
    pszVendorSetup = a1->pszVendorSetup;
    if ( pszVendorSetup )
      DllFreeSplMem(pszVendorSetup);
    pszzColorProfiles = a1->pszzColorProfiles;
    if ( pszzColorProfiles )
      DllFreeSplMem(pszzColorProfiles);
    pszInfPath = a1->pszInfPath;
    if ( pszInfPath )
      DllFreeSplMem(pszInfPath);
    pszzCoreDriverDependencies = a1->pszzCoreDriverDependencies;
    if ( pszzCoreDriverDependencies )
      DllFreeSplMem(pszzCoreDriverDependencies);
    DllFreeSplMem(a1);
  }
}

```

## disassembly

```asm
0x18004032c  test    rcx, rcx
0x18004032f  jz      locret_18004047A
0x180040335  push    rbx
0x180040336  sub     rsp, 20h
0x18004033a  mov     rbx, rcx
0x18004033d  mov     rcx, [rcx+8]
0x180040341  test    rcx, rcx
0x180040344  jz      short loc_18004034C
0x180040346  call    cs:__imp_DllFreeSplMem
0x18004034c  mov     rcx, [rbx+10h]
0x180040350  test    rcx, rcx
0x180040353  jz      short loc_18004035B
0x180040355  call    cs:__imp_DllFreeSplMem
0x18004035b  mov     rcx, [rbx+18h]
0x18004035f  test    rcx, rcx
0x180040362  jz      short loc_18004036A
0x180040364  call    cs:__imp_DllFreeSplMem
0x18004036a  mov     rcx, [rbx+28h]
0x18004036e  test    rcx, rcx
0x180040371  jz      short loc_180040379
0x180040373  call    cs:__imp_DllFreeSplMem
0x180040379  mov     rcx, [rbx+30h]
0x18004037d  test    rcx, rcx
0x180040380  jz      short loc_180040388
0x180040382  call    cs:__imp_DllFreeSplMem
0x180040388  mov     rcx, [rbx+20h]
0x18004038c  test    rcx, rcx
0x18004038f  jz      short loc_180040397
0x180040391  call    cs:__imp_DllFreeSplMem
0x180040397  mov     rcx, [rbx+38h]
0x18004039b  test    rcx, rcx
0x18004039e  jz      short loc_1800403A6
0x1800403a0  call    cs:__imp_DllFreeSplMem
0x1800403a6  mov     rcx, [rbx+40h]
0x1800403aa  test    rcx, rcx
0x1800403ad  jz      short loc_1800403B5
0x1800403af  call    cs:__imp_DllFreeSplMem
0x1800403b5  mov     rcx, [rbx+48h]
0x1800403b9  test    rcx, rcx
0x1800403bc  jz      short loc_1800403C4
0x1800403be  call    cs:__imp_DllFreeSplMem
0x1800403c4  mov     rcx, [rbx+50h]
0x1800403c8  test    rcx, rcx
0x1800403cb  jz      short loc_1800403D3
0x1800403cd  call    cs:__imp_DllFreeSplMem
0x1800403d3  mov     rcx, [rbx+68h]
0x1800403d7  test    rcx, rcx
0x1800403da  jz      short loc_1800403E2
0x1800403dc  call    cs:__imp_DllFreeSplMem
0x1800403e2  mov     rcx, [rbx+70h]
0x1800403e6  test    rcx, rcx
0x1800403e9  jz      short loc_1800403F1
0x1800403eb  call    cs:__imp_DllFreeSplMem
0x1800403f1  mov     rcx, [rbx+78h]
0x1800403f5  test    rcx, rcx
0x1800403f8  jz      short loc_180040400
0x1800403fa  call    cs:__imp_DllFreeSplMem
0x180040400  mov     rcx, [rbx+80h]
0x180040407  test    rcx, rcx
0x18004040a  jz      short loc_180040412
0x18004040c  call    cs:__imp_DllFreeSplMem
0x180040412  mov     rcx, [rbx+88h]
0x180040419  test    rcx, rcx
0x18004041c  jz      short loc_180040424
0x18004041e  call    cs:__imp_DllFreeSplMem
0x180040424  mov     rcx, [rbx+90h]
0x18004042b  test    rcx, rcx
0x18004042e  jz      short loc_180040436
0x180040430  call    cs:__imp_DllFreeSplMem
0x180040436  mov     rcx, [rbx+98h]
0x18004043d  test    rcx, rcx
0x180040440  jz      short loc_180040448
0x180040442  call    cs:__imp_DllFreeSplMem
0x180040448  mov     rcx, [rbx+0A0h]
0x18004044f  test    rcx, rcx
0x180040452  jz      short loc_18004045A
0x180040454  call    cs:__imp_DllFreeSplMem
0x18004045a  mov     rcx, [rbx+0B0h]
0x180040461  test    rcx, rcx
0x180040464  jz      short loc_18004046C
0x180040466  call    cs:__imp_DllFreeSplMem
0x18004046c  mov     rcx, rbx
0x18004046f  call    cs:__imp_DllFreeSplMem
0x180040475  add     rsp, 20h
0x180040479  pop     rbx
0x18004047a  retn
```
