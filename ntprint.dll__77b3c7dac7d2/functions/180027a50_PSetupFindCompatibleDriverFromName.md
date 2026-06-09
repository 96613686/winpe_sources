# PSetupFindCompatibleDriverFromName

- ea: `0x180027a50`
- end: `0x180027c77`
- name: `PSetupFindCompatibleDriverFromName`
- size: `551`
- prototype: `__int64 __usercall@<rax>(LPCWSTR@<rcx>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007944`
- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x18001c5c0`
- `0x18001e264`
- `0x180026634`
- `0x180026820`
- `0x180027a50`
- `0x1800284d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180027ba0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180027ba0`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180027c0f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180027c0f`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180027ad9`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180027ad9`

## string_xrefs

- `0x180027c37`: `Invalid Argument: pszModel=%ws, pszEnvironment=%ws, pszInfPath=%p`
- `0x180027aa3`: `PSetupFindCompatibleDriverFromName`
- `0x180027c28`: `PSetupFindCompatibleDriverFromName`
- `0x180027aad`: `Searching for a driver compatible with %ws`
- `0x180027bf1`: `Found a compatible driver at %ws`
- `0x180027c4e`: `Error finding a compatible driver: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall PSetupFindCompatibleDriverFromName(
        LPCWSTR a1,
        FILETIME a2,
        unsigned __int64 a3,
        const WCHAR *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v5; // r12
  int v6; // r14d
  __int64 LastErrorAsFailHR; // rbx
  NCoreLibrary *v11; // rcx
  char *DeviceInfoList; // rbp
  __int64 v13; // rsi
  NCoreLibrary *v14; // rcx
  NCoreLibrary *v15; // rcx
  NCoreLibrary *v16; // rcx
  LONG v17; // eax
  int v19; // [rsp+70h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+78h] [rbp+10h] BYREF

  FileTime1 = a2;
  v5 = a5;
  v6 = 1;
  v19 = 1;
  if ( !a1 || !a4 || !a5 )
  {
    LODWORD(LastErrorAsFailHR) = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupFindCompatibleDriverFromName",
      L"Invalid Argument: pszModel=%ws, pszEnvironment=%ws, pszInfPath=%p",
      a1);
LABEL_29:
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupFindCompatibleDriverFromName",
      L"Error finding a compatible driver: hr: 0x%x",
      (unsigned int)LastErrorAsFailHR);
    return (unsigned int)LastErrorAsFailHR;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "PSetupFindCompatibleDriverFromName",
    L"Searching for a driver compatible with %ws",
    a1);
  LODWORD(LastErrorAsFailHR) = GetPlatformFromEnvironmentString(a4, &v19);
  if ( (int)LastErrorAsFailHR < 0 )
    goto LABEL_29;
  DeviceInfoList = (char *)SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, 0);
  if ( DeviceInfoList == (char *)-1LL )
  {
    LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v11);
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupFindCompatibleDriverFromName",
      L"Error creating device info list: hr: 0x%x",
      LastErrorAsFailHR);
    if ( (int)LastErrorAsFailHR < 0 )
      goto LABEL_29;
  }
  v13 = 0;
  if ( (unsigned int)BuildClassDriverList(DeviceInfoList)
    || (LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v14),
        ClassInstallerTelemetry::WriteDbgTraceError(
          "PSetupFindCompatibleDriverFromName",
          L"Error building class driver list: hr: 0x%x",
          LastErrorAsFailHR),
        (int)LastErrorAsFailHR >= 0) )
  {
    if ( (unsigned int)PreSelectDriverEx((int)DeviceInfoList, 0, a1, MyPlatform, 0) )
    {
      v13 = BuildInternalData((int)DeviceInfoList, 0);
      if ( !v13 )
        LODWORD(LastErrorAsFailHR) = NCoreLibrary::GetLastErrorAsFailHR(v16);
    }
    else
    {
      LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v15);
      ClassInstallerTelemetry::WriteDbgTraceError(
        "PSetupFindCompatibleDriverFromName",
        L"Error selecting the newest version of the driver in the driver store: hr: 0x%x",
        LastErrorAsFailHR);
    }
    if ( (int)LastErrorAsFailHR >= 0 )
    {
      v17 = CompareFileTime(&FileTime1, (const FILETIME *)(v13 + 64));
      if ( v17 == -1 )
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "PSetupFindCompatibleDriverFromName",
          L"The driver date of the driver in the driver store is newer than the driver we are searching for");
      }
      else if ( v17 || *(_QWORD *)(v13 + 72) < a3 )
      {
        v6 = 0;
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "PSetupFindCompatibleDriverFromName",
          L"The driver on the local system is older than the driver we are searching for");
      }
      else
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "PSetupFindCompatibleDriverFromName",
          L"The driver date of the driver on the local system is the same, and the version the same or newer, than the dri"
           "ver we are searching for");
      }
      if ( v6 )
      {
        LODWORD(LastErrorAsFailHR) = StringCchCopyW(v5, 0x104u, *(const unsigned __int16 **)v13);
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "PSetupFindCompatibleDriverFromName",
          L"Found a compatible driver at %ws",
          v5);
      }
    }
  }
  if ( (unsigned __int64)(DeviceInfoList - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
  if ( v13 )
    DestroyLocalData((HLOCAL)v13);
  if ( (int)LastErrorAsFailHR < 0 )
    goto LABEL_29;
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180027a50  mov     [rsp+arg_10], rbx
0x180027a55  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rdx
0x180027a5a  push    rbp
0x180027a5b  push    rsi
0x180027a5c  push    rdi
0x180027a5d  push    r12
0x180027a5f  push    r13
0x180027a61  push    r14
0x180027a63  push    r15
0x180027a65  sub     rsp, 30h
0x180027a69  mov     r12, [rsp+68h+arg_20]
0x180027a71  mov     r14d, 1
0x180027a77  mov     [rsp+68h+arg_0], r14d
0x180027a7c  mov     rsi, r9
0x180027a7f  mov     r13, r8
0x180027a82  mov     r15, rcx
0x180027a85  test    rcx, rcx
0x180027a88  jz      loc_180027C28
0x180027a8e  test    r9, r9
0x180027a91  jz      loc_180027C28
0x180027a97  test    r12, r12
0x180027a9a  jz      loc_180027C28
0x180027aa0  mov     r8, rcx
0x180027aa3  lea     rdi, aPsetupfindcomp_0; "PSetupFindCompatibleDriverFromName"
0x180027aaa  mov     rcx, rdi; char *
0x180027aad  lea     rdx, aSearchingForAD; "Searching for a driver compatible with "...
0x180027ab4  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180027ab9  lea     rdx, [rsp+68h+arg_0]
0x180027abe  mov     rcx, rsi; lpString1
0x180027ac1  call    GetPlatformFromEnvironmentString
0x180027ac6  mov     ebx, eax
0x180027ac8  test    eax, eax
0x180027aca  js      loc_180027C4B
0x180027ad0  xor     edx, edx; hwndParent
0x180027ad2  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x180027ad9  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180027adf  mov     rbp, rax
0x180027ae2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027ae6  jnz     short loc_180027B09
0x180027ae8  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180027aed  mov     r8d, eax
0x180027af0  lea     rdx, aErrorCreatingD; "Error creating device info list: hr: 0x"...
0x180027af7  mov     rcx, rdi; char *
0x180027afa  mov     ebx, eax
0x180027afc  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180027b01  test    ebx, ebx
0x180027b03  js      loc_180027C4B
0x180027b09  mov     rcx, rbp; DeviceInfoSet
0x180027b0c  xor     esi, esi
0x180027b0e  call    BuildClassDriverList
0x180027b13  test    eax, eax
0x180027b15  jnz     short loc_180027B38
0x180027b17  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180027b1c  mov     r8d, eax
0x180027b1f  lea     rdx, aErrorBuildingC; "Error building class driver list: hr: 0"...
0x180027b26  mov     rcx, rdi; char *
0x180027b29  mov     ebx, eax
0x180027b2b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180027b30  test    ebx, ebx
0x180027b32  js      loc_180027C02
0x180027b38  mov     eax, cs:MyPlatform
0x180027b3e  mov     r9d, r14d
0x180027b41  mov     [rsp+68h+var_40], esi; int
0x180027b45  mov     r8, r15; LPCWSTR
0x180027b48  xor     edx, edx; lpString1
0x180027b4a  mov     [rsp+68h+var_48], eax; int
0x180027b4e  mov     rcx, rbp; int
0x180027b51  call    PreSelectDriverEx
0x180027b56  test    eax, eax
0x180027b58  jz      short loc_180027B7A
0x180027b5a  mov     r8d, [rsp+68h+arg_0]
0x180027b5f  xor     edx, edx; int
0x180027b61  mov     rcx, rbp; int
0x180027b64  call    BuildInternalData
0x180027b69  mov     rsi, rax
0x180027b6c  test    rax, rax
0x180027b6f  jnz     short loc_180027B93
0x180027b71  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180027b76  mov     ebx, eax
0x180027b78  jmp     short loc_180027B93
0x180027b7a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180027b7f  mov     r8d, eax
0x180027b82  lea     rdx, aErrorSelecting_0; "Error selecting the newest version of t"...
0x180027b89  mov     rcx, rdi; char *
0x180027b8c  mov     ebx, eax
0x180027b8e  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180027b93  test    ebx, ebx
0x180027b95  js      short loc_180027C02
0x180027b97  lea     rdx, [rsi+40h]; lpFileTime2
0x180027b9b  lea     rcx, [rsp+68h+FileTime1]; lpFileTime1
0x180027ba0  call    cs:__imp_CompareFileTime
0x180027ba6  cmp     eax, 0FFFFFFFFh
0x180027ba9  jnz     short loc_180027BB4
0x180027bab  lea     rdx, aTheDriverDateO_0; "The driver date of the driver in the dr"...
0x180027bb2  jmp     short loc_180027BD1
0x180027bb4  test    eax, eax
0x180027bb6  jnz     short loc_180027BC7
0x180027bb8  cmp     [rsi+48h], r13
0x180027bbc  jb      short loc_180027BC7
0x180027bbe  lea     rdx, aTheDriverDateO; "The driver date of the driver on the lo"...
0x180027bc5  jmp     short loc_180027BD1
0x180027bc7  xor     r14d, r14d
0x180027bca  lea     rdx, aTheDriverOnThe; "The driver on the local system is older"...
0x180027bd1  mov     rcx, rdi; char *
0x180027bd4  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180027bd9  test    r14d, r14d
0x180027bdc  jz      short loc_180027C02
0x180027bde  mov     r8, [rsi]; unsigned __int16 *
0x180027be1  mov     edx, 104h; unsigned __int64
0x180027be6  mov     rcx, r12; unsigned __int16 *
0x180027be9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027bee  mov     r8, r12
0x180027bf1  lea     rdx, aFoundACompatib; "Found a compatible driver at %ws"
0x180027bf8  mov     rcx, rdi; char *
0x180027bfb  mov     ebx, eax
0x180027bfd  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180027c02  lea     rax, [rbp-1]
0x180027c06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027c0a  ja      short loc_180027C15
0x180027c0c  mov     rcx, rbp; DeviceInfoSet
0x180027c0f  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180027c15  test    rsi, rsi
0x180027c18  jz      short loc_180027C22
0x180027c1a  mov     rcx, rsi; hMem
0x180027c1d  call    DestroyLocalData
0x180027c22  test    ebx, ebx
0x180027c24  jns     short loc_180027C5D
0x180027c26  jmp     short loc_180027C4B
0x180027c28  lea     rdi, aPsetupfindcomp_0; "PSetupFindCompatibleDriverFromName"
0x180027c2f  mov     qword ptr [rsp+68h+var_48], r12
0x180027c34  mov     rcx, rdi; char *
0x180027c37  lea     rdx, aInvalidArgumen_19; "Invalid Argument: pszModel=%ws, pszEnvi"...
0x180027c3e  mov     r8, r15
0x180027c41  mov     ebx, 80070057h
0x180027c46  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180027c4b  mov     r8d, ebx
0x180027c4e  lea     rdx, aErrorFindingAC; "Error finding a compatible driver: hr: "...
0x180027c55  mov     rcx, rdi; char *
0x180027c58  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180027c5d  mov     eax, ebx
0x180027c5f  mov     rbx, [rsp+68h+arg_10]
0x180027c67  add     rsp, 30h
0x180027c6b  pop     r15
0x180027c6d  pop     r14
0x180027c6f  pop     r13
0x180027c71  pop     r12
0x180027c73  pop     rdi
0x180027c74  pop     rsi
0x180027c75  pop     rbp
0x180027c76  retn
```
