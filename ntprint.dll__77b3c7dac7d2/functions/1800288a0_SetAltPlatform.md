# SetAltPlatform

- ea: `0x1800288a0`
- end: `0x180028a1d`
- name: `SetAltPlatform`
- size: `381`
- prototype: `__int64 __usercall@<rax>(HDEVINFO DeviceInfoSet@<rcx>, LPCWSTR lpString1@<rdx>, PCWSTR AlternateDefaultCatalogFile)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x180009d64`
- `0x18000f698`
- `0x180011c70`
- `0x18002c0f0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x18001e164`
- `0x180026584`
- `0x1800288a0`
- `0x180036248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289c7`
- `SETUPAPI!SetupSetFileQueueAlternatePlatformW` at `0x1800289aa`
- `SETUPAPI!SetupSetFileQueueAlternatePlatformW` at `0x1800289aa`

## string_xrefs

- `0x18002896b`: `Setting alternate platform for driver installation`

## pseudocode

```c
__int64 __fastcall SetAltPlatform(
        char *DeviceInfoSet,
        WCHAR *lpString1,
        int a3,
        void *a4,
        PCWSTR AlternateDefaultCatalogFile)
{
  __int64 v5; // r15
  unsigned int OSVersion; // ebx
  DWORD LastError; // eax
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+20h] [rbp-E0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF

  v5 = a3;
  memset(&AlternatePlatformInfo, 0, sizeof(AlternatePlatformInfo));
  if ( (unsigned __int64)(DeviceInfoSet - 1) > 0xFFFFFFFFFFFFFFFDuLL || a4 == (void *)-1LL )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "SetAltPlatform",
      L"Invalid Argument: hDevInfo=%p, AltDrvQueue=%p",
      DeviceInfoSet);
    return 0;
  }
  else
  {
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    OSVersion = GetOSVersion(lpString1, &VersionInformation);
    if ( !OSVersion )
      goto LABEL_9;
    if ( MyPlatform == (_DWORD)v5 && (unsigned int)IsLocalMachine(lpString1) )
      return 1;
    AlternatePlatformInfo.Platform = *(&PlatformArch + 2 * v5);
    AlternatePlatformInfo.ProcessorArchitecture = *((_WORD *)&PlatformArch + 4 * v5 + 2);
    AlternatePlatformInfo.Reserved = 0;
    AlternatePlatformInfo.cbSize = 28;
    AlternatePlatformInfo.MajorVersion = VersionInformation.dwMajorVersion;
    AlternatePlatformInfo.MinorVersion = VersionInformation.dwMinorVersion;
    AlternatePlatformInfo.FirstValidatedMajorVersion = VersionInformation.dwMajorVersion;
    AlternatePlatformInfo.FirstValidatedMinorVersion = VersionInformation.dwMinorVersion;
    ClassInstallerTelemetry::WriteDbgTraceInfo("SetAltPlatform", L"Setting alternate platform for driver installation");
    OSVersion = SetupSetFileQueueAlternatePlatformW(a4, &AlternatePlatformInfo, AlternateDefaultCatalogFile);
    if ( !OSVersion || (OSVersion = AssociateQueueWithDeviceInfoList(DeviceInfoSet, a4)) == 0 )
    {
LABEL_9:
      LastError = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError("SetAltPlatform", L"Error setting alternate platform: %d", LastError);
    }
    return OSVersion;
  }
}

```

## disassembly

```asm
0x1800288a0  push    rbp
0x1800288a2  push    rbx
0x1800288a3  push    rsi
0x1800288a4  push    rdi
0x1800288a5  push    r12
0x1800288a7  push    r14
0x1800288a9  push    r15
0x1800288ab  lea     rbp, [rsp-70h]
0x1800288b0  sub     rsp, 170h
0x1800288b7  mov     rax, cs:__security_cookie
0x1800288be  xor     rax, rsp
0x1800288c1  mov     [rbp+0A0h+var_40], rax
0x1800288c5  mov     r12, [rbp+0A0h+AlternateDefaultCatalogFile]
0x1800288cc  lea     rax, [rcx-1]
0x1800288d0  movsxd  r15, r8d
0x1800288d3  xorps   xmm0, xmm0
0x1800288d6  mov     rdi, r9
0x1800288d9  mov     r14, rdx
0x1800288dc  mov     rsi, rcx
0x1800288df  movups  xmmword ptr [rsp+1A0h+AlternatePlatformInfo.cbSize], xmm0
0x1800288e4  movups  xmmword ptr [rsp+1A0h+AlternatePlatformInfo.MinorVersion], xmm0
0x1800288e9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800288ed  ja      loc_1800289E7
0x1800288f3  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800288f7  jz      loc_1800289E7
0x1800288fd  xor     edx, edx; Val
0x1800288ff  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x180028904  mov     r8d, 114h; Size
0x18002890a  call    memset_0
0x18002890f  lea     rdx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x180028914  mov     rcx, r14; pPrinterName
0x180028917  call    GetOSVersion
0x18002891c  mov     ebx, eax
0x18002891e  test    eax, eax
0x180028920  jz      loc_1800289C7
0x180028926  cmp     cs:MyPlatform, r15d
0x18002892d  jnz     short loc_180028945
0x18002892f  mov     rcx, r14; lpString1
0x180028932  call    IsLocalMachine
0x180028937  test    eax, eax
0x180028939  jz      short loc_180028945
0x18002893b  mov     eax, 1
0x180028940  jmp     loc_1800289FF
0x180028945  mov     r9d, [rsp+1A0h+VersionInformation.dwMajorVersion]
0x18002894a  lea     rdx, PlatformArch
0x180028951  mov     eax, [rdx+r15*8]
0x180028955  lea     rcx, aSetaltplatform; "SetAltPlatform"
0x18002895c  mov     r10d, [rsp+1A0h+VersionInformation.dwMinorVersion]
0x180028961  mov     [rsp+1A0h+AlternatePlatformInfo.Platform], eax
0x180028965  movzx   eax, word ptr [rdx+r15*8+4]
0x18002896b  lea     rdx, aSettingAlterna; "Setting alternate platform for driver i"...
0x180028972  mov     [rsp+1A0h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x180028977  xor     eax, eax
0x180028979  mov     word ptr [rsp+1A0h+AlternatePlatformInfo.12h], ax
0x18002897e  mov     [rsp+1A0h+AlternatePlatformInfo.cbSize], 1Ch
0x180028986  mov     [rsp+1A0h+AlternatePlatformInfo.MajorVersion], r9d
0x18002898b  mov     [rsp+1A0h+AlternatePlatformInfo.MinorVersion], r10d
0x180028990  mov     [rsp+1A0h+AlternatePlatformInfo.FirstValidatedMajorVersion], r9d
0x180028995  mov     [rsp+1A0h+AlternatePlatformInfo.FirstValidatedMinorVersion], r10d
0x18002899a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002899f  mov     r8, r12; AlternateDefaultCatalogFile
0x1800289a2  lea     rdx, [rsp+1A0h+AlternatePlatformInfo]; AlternatePlatformInfo
0x1800289a7  mov     rcx, rdi; QueueHandle
0x1800289aa  call    cs:__imp_SetupSetFileQueueAlternatePlatformW
0x1800289b0  mov     ebx, eax
0x1800289b2  test    eax, eax
0x1800289b4  jz      short loc_1800289C7
0x1800289b6  mov     rdx, rdi
0x1800289b9  mov     rcx, rsi; DeviceInfoSet
0x1800289bc  call    AssociateQueueWithDeviceInfoList
0x1800289c1  mov     ebx, eax
0x1800289c3  test    eax, eax
0x1800289c5  jnz     short loc_1800289E3
0x1800289c7  call    cs:__imp_GetLastError
0x1800289cd  mov     r8d, eax
0x1800289d0  lea     rdx, aErrorSettingAl; "Error setting alternate platform: %d"
0x1800289d7  lea     rcx, aSetaltplatform; "SetAltPlatform"
0x1800289de  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800289e3  mov     eax, ebx
0x1800289e5  jmp     short loc_1800289FF
0x1800289e7  mov     r8, rsi
0x1800289ea  lea     rdx, aInvalidArgumen_12; "Invalid Argument: hDevInfo=%p, AltDrvQu"...
0x1800289f1  lea     rcx, aSetaltplatform; "SetAltPlatform"
0x1800289f8  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800289fd  xor     eax, eax
0x1800289ff  mov     rcx, [rbp+0A0h+var_40]
0x180028a03  xor     rcx, rsp; StackCookie
0x180028a06  call    __security_check_cookie
0x180028a0b  add     rsp, 170h
0x180028a12  pop     r15
0x180028a14  pop     r14
0x180028a16  pop     r12
0x180028a18  pop     rdi
0x180028a19  pop     rsi
0x180028a1a  pop     rbx
0x180028a1b  pop     rbp
0x180028a1c  retn
```
