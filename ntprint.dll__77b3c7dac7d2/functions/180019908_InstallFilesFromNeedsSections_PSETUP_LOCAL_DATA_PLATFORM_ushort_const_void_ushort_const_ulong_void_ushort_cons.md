# InstallFilesFromNeedsSections(_PSETUP_LOCAL_DATA *,PLATFORM,ushort const *,void *,ushort const *,ulong,void *,ushort const *,void *)

- ea: `0x180019908`
- end: `0x180019c14`
- name: `?InstallFilesFromNeedsSections@@YAHPEAU_PSETUP_LOCAL_DATA@@W4PLATFORM@@PEBGPEAX2K323@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001f958`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x180012424`
- `0x180019908`
- `0x180034bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019baa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019baa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019a6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019a6b`
- `SETUPAPI!SetupGetStringFieldW` at `0x180019a4c`
- `SETUPAPI!SetupGetStringFieldW` at `0x180019a9c`
- `SETUPAPI!SetupGetStringFieldW` at `0x180019a4c`
- `SETUPAPI!SetupGetStringFieldW` at `0x180019a9c`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x180019ade`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x180019ade`
- `SETUPAPI!SetupGetFieldCount` at `0x180019a0d`
- `SETUPAPI!SetupGetFieldCount` at `0x180019a0d`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800199fa`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800199fa`

## string_xrefs

- `0x180019975`: `Installing files from needs sections.`
- `0x18001997c`: `InstallFilesFromNeedsSections`
- `0x1800199b8`: `InstallFilesFromNeedsSections`
- `0x180019ab6`: `InstallFilesFromNeedsSections`
- `0x180019b0a`: `InstallFilesFromNeedsSections`
- `0x180019bd4`: `InstallFilesFromNeedsSections`
- `0x180019c06`: `InstallFilesFromNeedsSections`
- `0x1800199ac`: `Invalid Argument: hInf=%p, pLocalData=%p, CopyQueue=%p, pszInstallSection=%ws, hIncludedInf=%p`
- `0x180019aaf`: `Installing all files from %ws section of the included inf`
- `0x180019b00`: `Error installing files from section %ws of the included inf: %d`
- `0x180019b78`: `SetupInstallFilesFromInfSection failed (Needs section name in additional info)`
- `0x180019b65`: `InstallFilesFromNeedsSections`
- `0x180019bff`: `Successfully installed files from included inf.`
- `0x180019bcd`: `Error installing files from included inf: %d`

## pseudocode

```c
__int64 __fastcall InstallFilesFromNeedsSections(
        __int64 a1,
        int a2,
        WCHAR *a3,
        char *a4,
        __int64 a5,
        char a6,
        HINF InfHandle,
        PCWSTR Section,
        HINF a9)
{
  HINF v9; // rsi
  char *v10; // r15
  HINF v11; // r13
  const unsigned __int16 *v13; // r12
  unsigned int StringFieldW; // ebx
  DWORD FieldCount; // eax
  DWORD v18; // ebp
  WCHAR *v19; // rsi
  signed int LastError; // r15d
  DWORD v21; // eax
  unsigned int v22; // ecx
  int v23; // r8d
  const unsigned __int16 *v24; // rdx
  DWORD v25; // eax
  struct _INFCONTEXT Context; // [rsp+60h] [rbp-48h] BYREF
  DWORD v30; // [rsp+D0h] [rbp+28h]

  v9 = InfHandle;
  v10 = a4;
  v11 = a9;
  v13 = Section;
  if ( (char *)InfHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
    && a1
    && (unsigned __int64)(a4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
    && Section
    && (char *)a9 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "InstallFilesFromNeedsSections",
      L"Installing files from needs sections.");
    StringFieldW = SetTargetDirectories((struct _PSETUP_LOCAL_DATA *)a1, a2, a3, v11, a6);
  }
  else
  {
    StringFieldW = 0;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InstallFilesFromNeedsSections",
      L"Invalid Argument: hInf=%p, pLocalData=%p, CopyQueue=%p, pszInstallSection=%ws, hIncludedInf=%p",
      InfHandle,
      a1,
      a4,
      Section,
      a9);
  }
  if ( StringFieldW )
  {
    memset(&Context, 0, sizeof(Context));
    if ( SetupFindFirstLineW(v9, v13, L"needs", &Context) )
    {
      FieldCount = SetupGetFieldCount(&Context);
      LODWORD(InfHandle) = 0;
      v18 = 1;
      v30 = FieldCount;
      while ( v18 <= FieldCount )
      {
        StringFieldW = SetupGetStringFieldW(&Context, v18, 0, 0, (PDWORD)&InfHandle);
        if ( StringFieldW )
        {
          v19 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * (_DWORD)InfHandle));
          if ( !v19 )
          {
            StringFieldW = 0;
            goto LABEL_27;
          }
          StringFieldW = SetupGetStringFieldW(&Context, v18, v19, (DWORD)InfHandle, (PDWORD)&InfHandle);
          if ( StringFieldW )
          {
            ClassInstallerTelemetry::WriteDbgTraceInfo(
              "InstallFilesFromNeedsSections",
              L"Installing all files from %ws section of the included inf",
              v19);
            StringFieldW = SetupInstallFilesFromInfSectionW(v11, 0, v10, v19, 0, 0x20u);
            if ( !StringFieldW )
            {
              LastError = GetLastError();
              v21 = GetLastError();
              ClassInstallerTelemetry::WriteDbgTraceError(
                "InstallFilesFromNeedsSections",
                L"Error installing files from section %ws of the included inf: %d",
                v19,
                v21);
              if ( LastError > 0 )
                v22 = (unsigned __int16)LastError | 0x80070000;
              else
                v22 = LastError;
              v23 = *(_DWORD *)(a1 + 172);
              if ( v23 )
                v24 = *(const unsigned __int16 **)(a1 + 224);
              else
                v24 = 0;
              SplLogPrinterSetupCoreDriverEvent(
                &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
                L"InstallFilesFromNeedsSections",
                L"SetupInstallFilesFromInfSection failed (Needs section name in additional info)",
                v19,
                *(const unsigned __int16 **)a1,
                *(const unsigned __int16 **)(a1 + 8),
                v13,
                (const unsigned __int16 *)PlatformEnv[a2],
                v23,
                v24,
                LastError,
                v22);
              v10 = a4;
            }
          }
          LocalFree(v19);
        }
        ++v18;
        if ( !StringFieldW )
          goto LABEL_27;
        FieldCount = v30;
      }
    }
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "InstallFilesFromNeedsSections",
      L"Successfully installed files from included inf.");
  }
  else
  {
LABEL_27:
    v25 = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InstallFilesFromNeedsSections",
      L"Error installing files from included inf: %d",
      v25);
  }
  return StringFieldW;
}

```

## disassembly

```asm
0x180019908  mov     rax, rsp
0x18001990b  mov     [rax+8], rbx
0x18001990f  mov     [rax+18h], rbp
0x180019913  mov     [rax+20h], r9
0x180019917  mov     [rax+10h], edx
0x18001991a  push    rsi
0x18001991b  push    r12
0x18001991d  push    r13
0x18001991f  push    r14
0x180019921  push    r15
0x180019923  sub     rsp, 80h
0x18001992a  mov     rsi, [rsp+0A8h+InfHandle]
0x180019932  mov     r15, r9
0x180019935  mov     r13, [rsp+0A8h+arg_40]
0x18001993d  mov     rbx, r8
0x180019940  mov     r12, [rsp+0A8h+Section]
0x180019948  mov     ebp, edx
0x18001994a  mov     r14, rcx
0x18001994d  lea     rax, [rsi-1]
0x180019951  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019955  ja      short loc_1800199A7
0x180019957  test    rcx, rcx
0x18001995a  jz      short loc_1800199A7
0x18001995c  lea     rax, [r9-1]
0x180019960  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019964  ja      short loc_1800199A7
0x180019966  test    r12, r12
0x180019969  jz      short loc_1800199A7
0x18001996b  lea     rax, [r13-1]
0x18001996f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019973  ja      short loc_1800199A7
0x180019975  lea     rdx, aInstallingFile; "Installing files from needs sections."
0x18001997c  lea     rcx, aInstallfilesfr_0; "InstallFilesFromNeedsSections"
0x180019983  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180019988  mov     eax, dword ptr [rsp+0A8h+arg_28]
0x18001998f  mov     r9, r13
0x180019992  mov     r8, rbx
0x180019995  mov     dword ptr [rsp+0A8h+RequiredSize], eax; char
0x180019999  mov     edx, ebp
0x18001999b  mov     rcx, r14; struct _PSETUP_LOCAL_DATA *
0x18001999e  call    SetTargetDirectories
0x1800199a3  mov     ebx, eax
0x1800199a5  jmp     short loc_1800199D1
0x1800199a7  mov     [rsp+0A8h+var_78], r13
0x1800199ac  lea     rdx, aInvalidArgumen_8; "Invalid Argument: hInf=%p, pLocalData=%"...
0x1800199b3  mov     qword ptr [rsp+0A8h+CopyFlags], r12
0x1800199b8  lea     rcx, aInstallfilesfr_0; "InstallFilesFromNeedsSections"
0x1800199bf  mov     [rsp+0A8h+RequiredSize], r9
0x1800199c4  xor     ebx, ebx
0x1800199c6  mov     r9, r14
0x1800199c9  mov     r8, rsi
0x1800199cc  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800199d1  test    ebx, ebx
0x1800199d3  jz      loc_180019BC4
0x1800199d9  xorps   xmm0, xmm0
0x1800199dc  lea     r9, [rsp+0A8h+Context]; Context
0x1800199e1  xor     eax, eax
0x1800199e3  lea     r8, aNeeds_0; "needs"
0x1800199ea  mov     rdx, r12; Section
0x1800199ed  mov     qword ptr [rsp+0A8h+Context.Section], rax
0x1800199f2  mov     rcx, rsi; InfHandle
0x1800199f5  movups  xmmword ptr [rsp+0A8h+Context.Inf], xmm0
0x1800199fa  call    cs:__imp_SetupFindFirstLineW
0x180019a00  test    eax, eax
0x180019a02  jz      loc_180019BFF
0x180019a08  lea     rcx, [rsp+0A8h+Context]; Context
0x180019a0d  call    cs:__imp_SetupGetFieldCount
0x180019a13  mov     dword ptr [rsp+0A8h+InfHandle], 0
0x180019a1e  mov     ebp, 1
0x180019a23  mov     [rsp+0A8h+arg_20], eax
0x180019a2a  cmp     ebp, eax
0x180019a2c  ja      loc_180019BFF
0x180019a32  lea     rax, [rsp+0A8h+InfHandle]
0x180019a3a  xor     r9d, r9d; ReturnBufferSize
0x180019a3d  xor     r8d, r8d; ReturnBuffer
0x180019a40  mov     [rsp+0A8h+RequiredSize], rax; RequiredSize
0x180019a45  mov     edx, ebp; FieldIndex
0x180019a47  lea     rcx, [rsp+0A8h+Context]; Context
0x180019a4c  call    cs:__imp_SetupGetStringFieldW
0x180019a52  mov     ebx, eax
0x180019a54  test    eax, eax
0x180019a56  jz      loc_180019BB0
0x180019a5c  mov     eax, dword ptr [rsp+0A8h+InfHandle]
0x180019a63  mov     ecx, 40h ; '@'; uFlags
0x180019a68  lea     edx, [rax+rax]; uBytes
0x180019a6b  call    cs:__imp_LocalAlloc
0x180019a71  mov     rsi, rax
0x180019a74  test    rax, rax
0x180019a77  jz      loc_180019BC2
0x180019a7d  mov     r9d, dword ptr [rsp+0A8h+InfHandle]; ReturnBufferSize
0x180019a85  lea     rax, [rsp+0A8h+InfHandle]
0x180019a8d  mov     r8, rsi; ReturnBuffer
0x180019a90  mov     [rsp+0A8h+RequiredSize], rax; RequiredSize
0x180019a95  mov     edx, ebp; FieldIndex
0x180019a97  lea     rcx, [rsp+0A8h+Context]; Context
0x180019a9c  call    cs:__imp_SetupGetStringFieldW
0x180019aa2  mov     ebx, eax
0x180019aa4  test    eax, eax
0x180019aa6  jz      loc_180019BA7
0x180019aac  mov     r8, rsi
0x180019aaf  lea     rdx, aInstallingAllF; "Installing all files from %ws section o"...
0x180019ab6  lea     rcx, aInstallfilesfr_0; "InstallFilesFromNeedsSections"
0x180019abd  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180019ac2  mov     r9, rsi; SectionName
0x180019ac5  mov     [rsp+0A8h+CopyFlags], 20h ; ' '; CopyFlags
0x180019acd  mov     r8, r15; FileQueue
0x180019ad0  mov     [rsp+0A8h+RequiredSize], 0; SourceRootPath
0x180019ad9  xor     edx, edx; LayoutInfHandle
0x180019adb  mov     rcx, r13; InfHandle
0x180019ade  call    cs:__imp_SetupInstallFilesFromInfSectionW
0x180019ae4  mov     ebx, eax
0x180019ae6  test    eax, eax
0x180019ae8  jnz     loc_180019BA7
0x180019aee  call    cs:__imp_GetLastError
0x180019af4  mov     r15d, eax
0x180019af7  call    cs:__imp_GetLastError
0x180019afd  mov     r8, rsi
0x180019b00  lea     rdx, aErrorInstallin_2; "Error installing files from section %ws"...
0x180019b07  mov     r9d, eax
0x180019b0a  lea     rcx, aInstallfilesfr_0; "InstallFilesFromNeedsSections"
0x180019b11  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180019b16  test    r15d, r15d
0x180019b19  jg      short loc_180019B20
0x180019b1b  mov     ecx, r15d
0x180019b1e  jmp     short loc_180019B2A
0x180019b20  movzx   ecx, r15w
0x180019b24  or      ecx, 80070000h
0x180019b2a  mov     r8d, [r14+0ACh]
0x180019b31  test    r8d, r8d
0x180019b34  jz      short loc_180019B3F
0x180019b36  mov     rdx, [r14+0E0h]
0x180019b3d  jmp     short loc_180019B41
0x180019b3f  xor     edx, edx
0x180019b41  movsxd  rax, [rsp+0A8h+arg_8]
0x180019b49  lea     r9, PlatformEnv
0x180019b50  mov     [rsp+0A8h+var_50], ecx; unsigned int
0x180019b54  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180019b5b  mov     [rsp+0A8h+var_58], r15d; unsigned int
0x180019b60  mov     [rsp+0A8h+var_60], rdx; unsigned __int16 *
0x180019b65  lea     rdx, aInstallfilesfr; "InstallFilesFromNeedsSections"
0x180019b6c  mov     rax, [r9+rax*8]
0x180019b70  mov     r9, rsi; unsigned __int16 *
0x180019b73  mov     [rsp+0A8h+var_68], r8d; int
0x180019b78  lea     r8, aSetupinstallfi_1; "SetupInstallFilesFromInfSection failed "...
0x180019b7f  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x180019b84  mov     rax, [r14+8]
0x180019b88  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x180019b8d  mov     qword ptr [rsp+0A8h+CopyFlags], rax; unsigned __int16 *
0x180019b92  mov     rax, [r14]
0x180019b95  mov     [rsp+0A8h+RequiredSize], rax; unsigned __int16 *
0x180019b9a  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x180019b9f  mov     r15, [rsp+0A8h+arg_18]
0x180019ba7  mov     rcx, rsi; hMem
0x180019baa  call    cs:__imp_LocalFree
0x180019bb0  inc     ebp
0x180019bb2  test    ebx, ebx
0x180019bb4  jz      short loc_180019BC4
0x180019bb6  mov     eax, [rsp+0A8h+arg_20]
0x180019bbd  jmp     loc_180019A2A
0x180019bc2  xor     ebx, ebx
0x180019bc4  call    cs:__imp_GetLastError
0x180019bca  mov     r8d, eax
0x180019bcd  lea     rdx, aErrorInstallin_0; "Error installing files from included in"...
0x180019bd4  lea     rcx, aInstallfilesfr_0; "InstallFilesFromNeedsSections"
0x180019bdb  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180019be0  lea     r11, [rsp+0A8h+var_28]
0x180019be8  mov     eax, ebx
0x180019bea  mov     rbx, [r11+30h]
0x180019bee  mov     rbp, [r11+40h]
0x180019bf2  mov     rsp, r11
0x180019bf5  pop     r15
0x180019bf7  pop     r14
0x180019bf9  pop     r13
0x180019bfb  pop     r12
0x180019bfd  pop     rsi
0x180019bfe  retn
0x180019bff  lea     rdx, aSuccessfullyIn; "Successfully installed files from inclu"...
0x180019c06  lea     rcx, aInstallfilesfr_0; "InstallFilesFromNeedsSections"
0x180019c0d  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180019c12  jmp     short loc_180019BE0
```
