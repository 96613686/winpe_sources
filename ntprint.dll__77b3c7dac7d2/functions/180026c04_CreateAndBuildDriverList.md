# CreateAndBuildDriverList

- ea: `0x180026c04`
- end: `0x180026d08`
- name: `CreateAndBuildDriverList`
- size: `260`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180009724`
- `0x18001a5e0`
- `0x18001b648`
- `0x18001c978`
- `0x1800244f0`

## callees

- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x180012b28`
- `0x1800266ec`
- `0x180026c04`
- `0x180026ed4`
- `0x180027e90`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180026c4e`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180026c4e`

## string_xrefs

- `0x180026c30`: `CreateAndBuildDriverList`
- `0x180026cc1`: `CreateAndBuildDriverList`
- `0x180026ce2`: `CreateAndBuildDriverList`

## pseudocode

```c
__int64 __fastcall CreateAndBuildDriverList(__int64 a1, __int64 *a2)
{
  int v3; // ebp
  NCoreLibrary *v4; // rcx
  __int64 DeviceInfoList; // rdi
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v7; // rcx
  NCoreLibrary *v8; // rcx

  v3 = a1;
  if ( (unsigned int)ValidPlatform(a1) && a2 )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "CreateAndBuildDriverList",
      L"Building a driver list for all drivers in the driver store (including drivers with the ExcludeFromSelect flag set)");
    *a2 = -1;
    DeviceInfoList = (__int64)SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, HWND_MESSAGE|0x2LL);
    if ( DeviceInfoList != -1 || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v4), LastErrorAsFailHR >= 0) )
    {
      if ( (unsigned int)PSetupSetDriverPlatform((char *)DeviceInfoList, v3, 0, 0, 0, 0)
        || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v7), LastErrorAsFailHR >= 0) )
      {
        if ( (unsigned int)BuildExcludedDriverList((HDEVINFO)DeviceInfoList, 0, 0) )
        {
          LastErrorAsFailHR = 0;
LABEL_10:
          *a2 = DeviceInfoList;
          ClassInstallerTelemetry::WriteDbgTraceInfo("CreateAndBuildDriverList", L"Successfully built driver list");
          return (unsigned int)LastErrorAsFailHR;
        }
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8);
        if ( LastErrorAsFailHR >= 0 )
          goto LABEL_10;
      }
    }
  }
  else
  {
    DeviceInfoList = -1;
    LastErrorAsFailHR = -2147024809;
  }
  ClassInstallerTelemetry::WriteDbgTraceError(
    "CreateAndBuildDriverList",
    L"Failed building driver list: hr: 0x%x",
    (unsigned int)LastErrorAsFailHR);
  if ( DeviceInfoList != -1 )
    DestroyOnlyPrinterDeviceInfoList(DeviceInfoList);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180026c04  push    rbx
0x180026c06  push    rbp
0x180026c07  push    rdi
0x180026c08  push    r14
0x180026c0a  sub     rsp, 38h
0x180026c0e  mov     r14, rdx
0x180026c11  mov     ebp, ecx
0x180026c13  call    ValidPlatform
0x180026c18  test    eax, eax
0x180026c1a  jz      loc_180026CCF
0x180026c20  test    r14, r14
0x180026c23  jz      loc_180026CCF
0x180026c29  lea     rdx, aBuildingADrive; "Building a driver list for all drivers "...
0x180026c30  lea     rcx, aCreateandbuild; "CreateAndBuildDriverList"
0x180026c37  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026c3c  or      rdx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x180026c40  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180026c47  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x180026c4e  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180026c54  mov     rdi, rax
0x180026c57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026c5b  jnz     short loc_180026C68
0x180026c5d  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180026c62  mov     ebx, eax
0x180026c64  test    eax, eax
0x180026c66  js      short loc_180026CD8
0x180026c68  mov     [rsp+58h+var_30], 0; int
0x180026c70  xor     r9d, r9d
0x180026c73  xor     r8d, r8d
0x180026c76  mov     [rsp+58h+var_38], 0; int
0x180026c7e  mov     edx, ebp
0x180026c80  mov     rcx, rdi; DeviceInfoSet
0x180026c83  call    PSetupSetDriverPlatform
0x180026c88  test    eax, eax
0x180026c8a  jnz     short loc_180026C97
0x180026c8c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180026c91  mov     ebx, eax
0x180026c93  test    eax, eax
0x180026c95  js      short loc_180026CD8
0x180026c97  xor     r8d, r8d
0x180026c9a  xor     edx, edx; unsigned __int16 *
0x180026c9c  mov     rcx, rdi; DeviceInfoSet
0x180026c9f  call    BuildExcludedDriverList
0x180026ca4  test    eax, eax
0x180026ca6  jz      short loc_180026CAC
0x180026ca8  xor     ebx, ebx
0x180026caa  jmp     short loc_180026CB7
0x180026cac  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180026cb1  mov     ebx, eax
0x180026cb3  test    eax, eax
0x180026cb5  js      short loc_180026CD8
0x180026cb7  lea     rdx, aSuccessfullyBu; "Successfully built driver list"
0x180026cbe  mov     [r14], rdi
0x180026cc1  lea     rcx, aCreateandbuild; "CreateAndBuildDriverList"
0x180026cc8  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026ccd  jmp     short loc_180026CFC
0x180026ccf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026cd3  mov     ebx, 80070057h
0x180026cd8  mov     r8d, ebx
0x180026cdb  lea     rdx, aFailedBuilding; "Failed building driver list: hr: 0x%x"
0x180026ce2  lea     rcx, aCreateandbuild; "CreateAndBuildDriverList"
0x180026ce9  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180026cee  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180026cf2  jz      short loc_180026CFC
0x180026cf4  mov     rcx, rdi
0x180026cf7  call    DestroyOnlyPrinterDeviceInfoList
0x180026cfc  mov     eax, ebx
0x180026cfe  add     rsp, 38h
0x180026d02  pop     r14
0x180026d04  pop     rdi
0x180026d05  pop     rbp
0x180026d06  pop     rbx
0x180026d07  retn
```
