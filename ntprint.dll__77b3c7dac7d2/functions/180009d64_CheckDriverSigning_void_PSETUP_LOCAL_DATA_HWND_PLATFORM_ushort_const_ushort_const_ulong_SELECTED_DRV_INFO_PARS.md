# CheckDriverSigning(void *,_PSETUP_LOCAL_DATA *,HWND__ *,PLATFORM,ushort const *,ushort const *,ulong,_SELECTED_DRV_INFO *,_PARSEINF_INFO *,void *,_FILE_QUEUE_CONTEXT *,uint (*)(void *,uint,unsigned __int64,unsigned __int64),ushort *,_HINF_ARRAY *)

- ea: `0x180009d64`
- end: `0x18000a6d6`
- name: `?CheckDriverSigning@@YAKPEAXPEAU_PSETUP_LOCAL_DATA@@PEAUHWND__@@W4PLATFORM@@PEBG4KPEAU_SELECTED_DRV_INFO@@PEAU_PARSEINF_INFO@@0PEAU_FILE_QUEUE_CONTEXT@@P6AI0I_K8@ZPEAGPEAU_HINF_ARRAY@@@Z`
- size: `2418`
- prototype: `unsigned int __high(void *, struct _PSETUP_LOCAL_DATA *, HWND, enum PLATFORM, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _SELECTED_DRV_INFO *, struct _PARSEINF_INFO *, void *, struct _FILE_QUEUE_CONTEXT *, unsigned int (__high *)(void *, unsigned int, unsigned __int64, unsigned __int64), unsigned __int16 *, struct _HINF_ARRAY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f698`

## callees

- `0x18000908c`
- `0x180009d64`
- `0x18000d4a4`
- `0x18001dbac`
- `0x18001f958`
- `0x180020b60`
- `0x1800288a0`
- `0x180034bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009eab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a556`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6a4`
- `SETUPAPI!SetupScanFileQueueW` at `0x18000a627`
- `SETUPAPI!SetupScanFileQueueW` at `0x18000a627`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18000a273`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18000a273`
- `SETUPAPI!SetupOpenFileQueue` at `0x180009f39`
- `SETUPAPI!SetupOpenFileQueue` at `0x18000a0bb`
- `SETUPAPI!SetupOpenFileQueue` at `0x180009f39`
- `SETUPAPI!SetupOpenFileQueue` at `0x18000a0bb`
- `SETUPAPI!SetupFindFirstLineW` at `0x180009e96`
- `SETUPAPI!SetupFindFirstLineW` at `0x180009e96`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x18000a696`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x18000a696`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18000a548`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18000a548`
- `SETUPAPI!SetupCloseFileQueue` at `0x18000a675`
- `SETUPAPI!SetupCloseFileQueue` at `0x18000a684`
- `SETUPAPI!SetupCloseFileQueue` at `0x18000a675`
- `SETUPAPI!SetupCloseFileQueue` at `0x18000a684`
- `SETUPAPI!SetupCloseInfFile` at `0x18000a6b3`
- `SETUPAPI!SetupCloseInfFile` at `0x18000a6b3`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180009f33`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x180009f33`

## string_xrefs

- `0x180009f79`: `SetupOpenFileQueue failed`
- `0x18000a0fb`: `SetupOpenFileQueue failed`
- `0x18000a1f4`: `InstallAllInfSections failed`
- `0x18000a4c9`: `ChangeDestinationToTempDirectory failed`
- `0x18000a5b1`: `SetupCommitFileQueue failed`

## pseudocode

```c
__int64 __fastcall CheckDriverSigning(
        char *a1,
        __int64 a2,
        HWND a3,
        int a4,
        const unsigned __int16 *lpString1,
        const WCHAR *a6,
        unsigned int a7,
        const unsigned __int16 **a8,
        __int64 a9,
        char *InfSpec,
        _QWORD *a11,
        DWORD Result,
        __int64 a13,
        __int64 a14)
{
  __int64 v14; // r12
  __int64 v15; // r13
  __int64 v16; // r14
  unsigned int v18; // eax
  DWORD LastError; // ebx
  int v20; // edx
  const unsigned __int16 *v21; // rcx
  int *v22; // r14
  int v23; // ecx
  const unsigned __int16 *v24; // rax
  __int64 v25; // rsi
  __int64 v26; // r15
  signed int v27; // eax
  int v28; // edx
  const unsigned __int16 *v29; // rcx
  const unsigned __int16 **v30; // r13
  int *v31; // rsi
  const unsigned __int16 *v32; // rcx
  signed int v33; // eax
  int v34; // edx
  const unsigned __int16 *v35; // rcx
  __int64 v36; // r15
  signed int v37; // eax
  unsigned int v38; // ecx
  const unsigned __int16 *v39; // rax
  signed int CatalogFromInf; // eax
  const unsigned __int16 *v41; // rcx
  signed int v42; // eax
  int *v43; // rsi
  int v44; // edx
  const unsigned __int16 *v45; // rcx
  const unsigned __int16 **v46; // r15
  __int64 v47; // r14
  signed int v48; // eax
  const unsigned __int16 *v49; // rcx
  signed int v50; // eax
  unsigned int v51; // ecx
  const unsigned __int16 *v52; // rdx
  int v53; // eax
  __int64 QueueHandle; // [rsp+68h] [rbp-49h]
  __int64 v56; // [rsp+78h] [rbp-39h]
  HINF InfHandle; // [rsp+80h] [rbp-31h]
  PVOID inited; // [rsp+88h] [rbp-29h]
  __int64 v59; // [rsp+90h] [rbp-21h]
  _INFCONTEXT Context; // [rsp+98h] [rbp-19h] BYREF

  v14 = a4;
  v15 = -1;
  v56 = -1;
  v16 = -1;
  QueueHandle = -1;
  inited = 0;
  Result = 0;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a2 || !a4 || !a8 || !a9 || !a11 )
  {
    v59 = 0;
    LastError = 87;
    goto LABEL_93;
  }
  v59 = a11[1];
  v18 = VerifyInfFile(a3, *a8, a8[1], (a7 & 8) == 0);
  if ( v18 == 2 )
  {
    LastError = 1223;
    goto LABEL_93;
  }
  LastError = 0;
  if ( v18 != 1 )
  {
    InfHandle = (HINF)OpenPrinterInfFile((unsigned __int16 *)*a8);
    v15 = (__int64)InfHandle;
    if ( InfHandle != (HINF)-1LL || (LastError = GetLastError()) == 0 )
    {
      if ( (_DWORD)v14 != MyPlatform )
      {
        memset(&Context, 0, sizeof(Context));
        if ( SetupFindFirstLineW(InfHandle, L"Version", L"LayoutFile", &Context) )
        {
          LastError = 1633;
          SetLastError(0x661u);
          v20 = *(_DWORD *)(a2 + 172);
          if ( v20 )
            v21 = *(const unsigned __int16 **)(a2 + 224);
          else
            v21 = 0;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"CheckDriverSigning",
            L"SetupFindFirstLine(Version, LayoutFile) failed",
            lpString1,
            *(const unsigned __int16 **)a2,
            *(const unsigned __int16 **)(a2 + 8),
            *(const unsigned __int16 **)(a2 + 184),
            (const unsigned __int16 *)PlatformEnv[v14],
            v20,
            v21,
            0x661u,
            0x80070661);
          goto LABEL_93;
        }
      }
      SetupOpenAppendInfFileW(0, InfHandle, 0);
      v56 = (__int64)SetupOpenFileQueue();
      if ( v56 == -1 )
      {
        v22 = (int *)(a2 + 172);
        LastError = GetLastError();
        v23 = *(_DWORD *)(a2 + 172);
        if ( v23 )
          v24 = *(const unsigned __int16 **)(a2 + 224);
        else
          v24 = 0;
        v25 = v14;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"CheckDriverSigning",
          L"SetupOpenFileQueue failed",
          lpString1,
          *(const unsigned __int16 **)a2,
          *(const unsigned __int16 **)(a2 + 8),
          *(const unsigned __int16 **)(a2 + 184),
          (const unsigned __int16 *)PlatformEnv[v14],
          v23,
          v24,
          6u,
          0x80070006);
        if ( LastError )
          goto LABEL_92;
      }
      else
      {
        v22 = (int *)(a2 + 172);
        v25 = v14;
      }
      v26 = v25;
      if ( (unsigned int)SetAltPlatform(a1, lpString1, 0) )
      {
        v30 = (const unsigned __int16 **)(a2 + 184);
        v31 = v22;
      }
      else
      {
        v27 = GetLastError();
        LastError = v27;
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        v28 = *(_DWORD *)(a2 + 172);
        if ( v28 )
          v29 = *(const unsigned __int16 **)(a2 + 224);
        else
          v29 = 0;
        v30 = (const unsigned __int16 **)(a2 + 184);
        v26 = v14;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"CheckDriverSigning",
          L"SetAltPlatform failed",
          lpString1,
          *(const unsigned __int16 **)a2,
          *(const unsigned __int16 **)(a2 + 8),
          *(const unsigned __int16 **)(a2 + 184),
          (const unsigned __int16 *)PlatformEnv[v14],
          v28,
          v29,
          LastError,
          v27);
        if ( LastError )
          goto LABEL_91;
        v31 = (int *)(a2 + 172);
      }
      QueueHandle = (__int64)SetupOpenFileQueue();
      if ( QueueHandle != -1 )
      {
LABEL_40:
        v15 = (__int64)InfHandle;
        if ( (unsigned int)InstallAllInfSections(
                             (struct _PSETUP_LOCAL_DATA *)a2,
                             v14,
                             (__int64)lpString1,
                             (char *)v56,
                             a6,
                             a7,
                             InfHandle,
                             *(PCWSTR *)(a9 + 16),
                             (__int64)InfSpec,
                             (unsigned int *)a14,
                             a2 + 400) )
        {
          v36 = v14;
        }
        else
        {
          v33 = GetLastError();
          LastError = v33;
          if ( v33 > 0 )
            v33 = (unsigned __int16)v33 | 0x80070000;
          v31 = (int *)(a2 + 172);
          v34 = *(_DWORD *)(a2 + 172);
          if ( v34 )
            v35 = *(const unsigned __int16 **)(a2 + 224);
          else
            v35 = 0;
          v36 = v14;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"CheckDriverSigning",
            L"InstallAllInfSections failed",
            lpString1,
            *(const unsigned __int16 **)a2,
            *(const unsigned __int16 **)(a2 + 8),
            *(const unsigned __int16 **)(a2 + 184),
            (const unsigned __int16 *)PlatformEnv[v14],
            v34,
            v35,
            LastError,
            v33);
          if ( LastError )
            goto LABEL_92;
        }
        inited = SetupInitDefaultQueueCallbackEx(a3, HWND_MESSAGE|0x2LL, 0, 0, 0);
        if ( !inited )
        {
          v37 = GetLastError();
          LastError = v37;
          if ( v37 > 0 )
            v38 = (unsigned __int16)v37 | 0x80070000;
          else
            v38 = v37;
          if ( *v31 )
            v39 = *(const unsigned __int16 **)(a2 + 224);
          else
            v39 = 0;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"CheckDriverSigning",
            L"SetupInitDefaultQueueCallbackEx failed",
            lpString1,
            *(const unsigned __int16 **)a2,
            *(const unsigned __int16 **)(a2 + 8),
            *(const unsigned __int16 **)(a2 + 184),
            (const unsigned __int16 *)PlatformEnv[v36],
            *v31,
            v39,
            LastError,
            v38);
          if ( LastError )
            goto LABEL_92;
          v31 = (int *)(a2 + 172);
        }
        a11[1] = inited;
        if ( (unsigned __int64)(InfSpec - 1) > 0xFFFFFFFFFFFFFFFDuLL
          || (CatalogFromInf = GetCatalogFromInf(InfSpec), CatalogFromInf >= 0)
          || ((LastError = (unsigned __int16)CatalogFromInf, !*v31)
            ? (v41 = 0)
            : (v41 = *(const unsigned __int16 **)(a2 + 224)),
              SplLogPrinterSetupCoreDriverEvent(
                &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
                L"CheckDriverSigning",
                L"GetCatalogFromInf failed",
                lpString1,
                *(const unsigned __int16 **)a2,
                *(const unsigned __int16 **)(a2 + 8),
                *(const unsigned __int16 **)(a2 + 184),
                (const unsigned __int16 *)PlatformEnv[v36],
                *v31,
                v41,
                (unsigned __int16)CatalogFromInf,
                CatalogFromInf),
              !LastError) )
        {
          if ( (unsigned int)SetAltPlatform(a1, lpString1, 0) )
          {
            v43 = (int *)(a2 + 172);
            v47 = v14;
            v46 = (const unsigned __int16 **)(a2 + 184);
          }
          else
          {
            v42 = GetLastError();
            LastError = v42;
            if ( v42 > 0 )
              v42 = (unsigned __int16)v42 | 0x80070000;
            v43 = (int *)(a2 + 172);
            v44 = *(_DWORD *)(a2 + 172);
            if ( v44 )
              v45 = *(const unsigned __int16 **)(a2 + 224);
            else
              v45 = 0;
            v46 = (const unsigned __int16 **)(a2 + 184);
            v47 = v14;
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
              L"CheckDriverSigning",
              L"SetAltPlatform failed",
              lpString1,
              *(const unsigned __int16 **)a2,
              *(const unsigned __int16 **)(a2 + 8),
              *(const unsigned __int16 **)(a2 + 184),
              (const unsigned __int16 *)PlatformEnv[v14],
              v44,
              v45,
              LastError,
              v42);
            if ( LastError )
              goto LABEL_92;
          }
          v48 = ChangeDestinationToTempDirectory(InfHandle, (unsigned int)v14, v56, QueueHandle, a13);
          if ( v48 >= 0 )
          {
LABEL_79:
            v16 = QueueHandle;
            if ( SetupCommitFileQueueW(a3, (HSPFILEQ)QueueHandle, MyQueueCallback, a11)
              || ((v50 = GetLastError(), LastError = v50, v50 > 0)
                ? (v51 = (unsigned __int16)v50 | 0x80070000)
                : (v51 = v50),
                  !*v43 ? (v52 = 0) : (v52 = *(const unsigned __int16 **)(a2 + 224)),
                  SplLogPrinterSetupCoreDriverEvent(
                    &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
                    L"CheckDriverSigning",
                    L"SetupCommitFileQueue failed",
                    lpString1,
                    *(const unsigned __int16 **)a2,
                    *(const unsigned __int16 **)(a2 + 8),
                    *(const unsigned __int16 **)(a2 + 184),
                    (const unsigned __int16 *)PlatformEnv[v14],
                    *v43,
                    v52,
                    v50,
                    v51),
                  !LastError) )
            {
              Context.CurrentInf = (PVOID)a7;
              Context.Inf = a3;
              *(_QWORD *)&Context.Section = a8[1];
              SetupScanFileQueueW((HSPFILEQ)QueueHandle, 0x40u, a3, MyVerifyCallback, &Context, &Result);
              v53 = LastError;
              if ( Result == 2 )
                v53 = 1223;
              LastError = v53;
            }
            goto LABEL_93;
          }
          LastError = (unsigned __int16)v48;
          if ( *v43 )
            v49 = *(const unsigned __int16 **)(a2 + 224);
          else
            v49 = 0;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"CheckDriverSigning",
            L"ChangeDestinationToTempDirectory failed",
            lpString1,
            *(const unsigned __int16 **)a2,
            *(const unsigned __int16 **)(a2 + 8),
            *v46,
            (const unsigned __int16 *)PlatformEnv[v47],
            *v43,
            v49,
            (unsigned __int16)v48,
            v48);
          if ( !LastError )
          {
            v43 = (int *)(a2 + 172);
            goto LABEL_79;
          }
        }
LABEL_92:
        v16 = QueueHandle;
        goto LABEL_93;
      }
      LastError = GetLastError();
      if ( *v22 )
      {
        v32 = *(const unsigned __int16 **)(a2 + 224);
      }
      else
      {
        v32 = 0;
        v26 = v14;
      }
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"CheckDriverSigning",
        L"SetupOpenFileQueue failed",
        lpString1,
        *(const unsigned __int16 **)a2,
        *(const unsigned __int16 **)(a2 + 8),
        *v30,
        (const unsigned __int16 *)PlatformEnv[v26],
        *v22,
        v32,
        6u,
        0x80070006);
      if ( !LastError )
      {
        v31 = (int *)(a2 + 172);
        goto LABEL_40;
      }
LABEL_91:
      v15 = (__int64)InfHandle;
      goto LABEL_92;
    }
  }
LABEL_93:
  a11[1] = v59;
  if ( v56 != -1 )
    SetupCloseFileQueue((HSPFILEQ)v56);
  if ( v16 != -1 )
    SetupCloseFileQueue((HSPFILEQ)v16);
  if ( inited )
    SetupTermDefaultQueueCallback(inited);
  if ( v15 != -1 )
    SetupCloseInfFile((HINF)v15);
  return LastError;
}

```

## disassembly

```asm
0x180009d64  mov     rax, rsp
0x180009d67  mov     [rax+10h], rbx
0x180009d6b  mov     [rax+18h], r8
0x180009d6f  mov     [rax+8], rcx
0x180009d73  push    rbp
0x180009d74  push    rsi
0x180009d75  push    rdi
0x180009d76  push    r12
0x180009d78  push    r13
0x180009d7a  push    r14
0x180009d7c  push    r15
0x180009d7e  lea     rbp, [rax-3Fh]
0x180009d82  sub     rsp, 0B0h
0x180009d89  lea     rax, [rcx-1]
0x180009d8d  movsxd  r12, r9d
0x180009d90  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009d94  xor     esi, esi
0x180009d96  mov     r13, rcx
0x180009d99  mov     [rbp+37h+var_70], rcx
0x180009d9d  mov     r14, rcx
0x180009da0  mov     [rbp+37h+QueueHandle], rcx
0x180009da4  xor     ecx, ecx
0x180009da6  mov     [rbp+37h+AlternateDefaultCatalogFile], rsi
0x180009daa  mov     [rbp+37h+var_60], rcx
0x180009dae  mov     r10, r8
0x180009db1  mov     [rbp+37h+arg_58], ecx
0x180009db7  mov     rdi, rdx
0x180009dba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009dbe  ja      loc_18000A642
0x180009dc4  test    rdx, rdx
0x180009dc7  jz      loc_18000A642
0x180009dcd  test    r9d, r9d
0x180009dd0  jz      loc_18000A642
0x180009dd6  mov     r15, [rbp+37h+arg_38]
0x180009dda  test    r15, r15
0x180009ddd  jz      loc_18000A642
0x180009de3  cmp     [rbp+37h+arg_40], rcx
0x180009dea  jz      loc_18000A642
0x180009df0  mov     rax, [rbp+37h+arg_50]
0x180009df7  test    rax, rax
0x180009dfa  jz      loc_18000A642
0x180009e00  mov     r9d, dword ptr [rbp+37h+arg_30]
0x180009e04  mov     rcx, r10; HWND
0x180009e07  mov     rax, [rax+8]
0x180009e0b  mov     r8, [r15+8]; unsigned __int16 *
0x180009e0f  mov     rdx, [r15]; unsigned __int16 *
0x180009e12  shr     r9d, 3
0x180009e16  not     r9d
0x180009e19  mov     [rbp+37h+var_58], rax
0x180009e1d  and     r9d, 1; int
0x180009e21  call    ?VerifyInfFile@@YAKPEAUHWND__@@PEBG1H@Z; VerifyInfFile(HWND__ *,ushort const *,ushort const *,int)
0x180009e26  cmp     eax, 2
0x180009e29  jnz     short loc_180009E35
0x180009e2b  mov     ebx, 4C7h
0x180009e30  jmp     loc_18000A659
0x180009e35  xor     ebx, ebx
0x180009e37  cmp     eax, 1
0x180009e3a  jz      loc_18000A659
0x180009e40  mov     rcx, [r15]; unsigned __int16 *
0x180009e43  xor     edx, edx
0x180009e45  call    OpenPrinterInfFile
0x180009e4a  mov     [rbp+37h+var_68], rax
0x180009e4e  mov     r13, rax
0x180009e51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009e55  jnz     short loc_180009E67
0x180009e57  call    cs:__imp_GetLastError
0x180009e5d  mov     ebx, eax
0x180009e5f  test    eax, eax
0x180009e61  jnz     loc_18000A659
0x180009e67  cmp     r12d, cs:MyPlatform
0x180009e6e  jz      loc_180009F2B
0x180009e74  xorps   xmm0, xmm0
0x180009e77  lea     r9, [rbp+37h+Context]; Context
0x180009e7b  xor     eax, eax
0x180009e7d  lea     r8, Key; "LayoutFile"
0x180009e84  lea     rdx, Section; "Version"
0x180009e8b  mov     qword ptr [rbp+37h+Context.Section], rax
0x180009e8f  mov     rcx, r13; InfHandle
0x180009e92  movups  xmmword ptr [rbp+37h+Context.Inf], xmm0
0x180009e96  call    cs:__imp_SetupFindFirstLineW
0x180009e9c  test    eax, eax
0x180009e9e  jz      loc_180009F2B
0x180009ea4  mov     ebx, 661h
0x180009ea9  mov     ecx, ebx; dwErrCode
0x180009eab  call    cs:__imp_SetLastError
0x180009eb1  mov     edx, [rdi+0ACh]
0x180009eb7  test    edx, edx
0x180009eb9  jz      short loc_180009EC4
0x180009ebb  mov     rcx, [rdi+0E0h]
0x180009ec2  jmp     short loc_180009EC6
0x180009ec4  xor     ecx, ecx
0x180009ec6  mov     r9, [rbp+37h+lpString1]; unsigned __int16 *
0x180009eca  lea     r8, PlatformEnv
0x180009ed1  mov     rax, [r8+r12*8]
0x180009ed5  lea     r8, aSetupfindfirst; "SetupFindFirstLine(Version, LayoutFile)"...
0x180009edc  mov     dword ptr [rsp+58h], 80070661h; unsigned int
0x180009ee4  mov     [rsp+0E0h+var_90], ebx; unsigned int
0x180009ee8  mov     [rsp+0E0h+var_98], rcx; unsigned __int16 *
0x180009eed  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180009ef4  mov     dword ptr [rsp+0E0h+var_A0], edx; int
0x180009ef8  lea     rdx, aCheckdriversig; "CheckDriverSigning"
0x180009eff  mov     [rsp+0E0h+SectionName], rax; unsigned __int16 *
0x180009f04  mov     rax, [rdi+0B8h]
0x180009f0b  mov     [rsp+0E0h+InfHandle], rax; unsigned __int16 *
0x180009f10  mov     rax, [rdi+8]
0x180009f14  mov     [rsp+0E0h+Result], rax; unsigned __int16 *
0x180009f19  mov     rax, [rdi]
0x180009f1c  mov     [rsp+0E0h+Reserved2], rax; unsigned __int16 *
0x180009f21  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x180009f26  jmp     loc_18000A659
0x180009f2b  xor     r8d, r8d; ErrorLine
0x180009f2e  mov     rdx, r13; InfHandle
0x180009f31  xor     ecx, ecx; FileName
0x180009f33  call    cs:__imp_SetupOpenAppendInfFileW
0x180009f39  call    cs:__imp_SetupOpenFileQueue
0x180009f3f  mov     [rbp+37h+var_70], rax
0x180009f43  lea     r15, PlatformEnv
0x180009f4a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009f4e  jnz     loc_180009FE3
0x180009f54  call    cs:__imp_GetLastError
0x180009f5a  lea     r14, [rdi+0ACh]
0x180009f61  mov     ebx, eax
0x180009f63  mov     ecx, [r14]
0x180009f66  test    ecx, ecx
0x180009f68  jz      short loc_180009F73
0x180009f6a  mov     rax, [rdi+0E0h]
0x180009f71  jmp     short loc_180009F75
0x180009f73  xor     eax, eax
0x180009f75  mov     r9, [rbp+37h+lpString1]; unsigned __int16 *
0x180009f79  lea     r8, aSetupopenfileq; "SetupOpenFileQueue failed"
0x180009f80  mov     dword ptr [rsp+58h], 80070006h; unsigned int
0x180009f88  lea     rdx, aCheckdriversig; "CheckDriverSigning"
0x180009f8f  mov     [rsp+0E0h+var_90], 6; unsigned int
0x180009f97  mov     rsi, r12
0x180009f9a  mov     [rsp+0E0h+var_98], rax; unsigned __int16 *
0x180009f9f  mov     rax, [r15+r12*8]
0x180009fa3  mov     dword ptr [rsp+0E0h+var_A0], ecx; int
0x180009fa7  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180009fae  mov     [rsp+0E0h+SectionName], rax; unsigned __int16 *
0x180009fb3  mov     rax, [rdi+0B8h]
0x180009fba  mov     [rsp+0E0h+InfHandle], rax; unsigned __int16 *
0x180009fbf  mov     rax, [rdi+8]
0x180009fc3  mov     [rsp+0E0h+Result], rax; unsigned __int16 *
0x180009fc8  mov     rax, [rdi]
0x180009fcb  mov     [rsp+0E0h+Reserved2], rax; unsigned __int16 *
0x180009fd0  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x180009fd5  test    ebx, ebx
0x180009fd7  jnz     loc_18000A651
0x180009fdd  mov     rax, [rbp+37h+var_70]
0x180009fe1  jmp     short loc_180009FED
0x180009fe3  lea     r14, [rdi+0ACh]
0x180009fea  mov     rsi, r12
0x180009fed  mov     rdx, [rbp+37h+lpString1]; lpString1
0x180009ff1  mov     r9, rax
0x180009ff4  mov     rcx, [rbp+37h+DeviceInfoSet]; DeviceInfoSet
0x180009ff8  mov     r8d, r12d
0x180009ffb  mov     r15, rsi
0x180009ffe  mov     [rsp+0E0h+Reserved2], 0; AlternateDefaultCatalogFile
0x18000a007  call    SetAltPlatform
0x18000a00c  test    eax, eax
0x18000a00e  jnz     loc_18000A0B1
0x18000a014  call    cs:__imp_GetLastError
0x18000a01a  mov     ebx, eax
0x18000a01c  test    eax, eax
0x18000a01e  jle     short loc_18000A028
0x18000a020  movzx   eax, bx
0x18000a023  or      eax, 80070000h
0x18000a028  mov     edx, [rdi+0ACh]
0x18000a02e  test    edx, edx
0x18000a030  jz      short loc_18000A03B
0x18000a032  mov     rcx, [rdi+0E0h]
0x18000a039  jmp     short loc_18000A03D
0x18000a03b  xor     ecx, ecx
0x18000a03d  mov     r9, [rbp+37h+lpString1]; unsigned __int16 *
0x18000a041  lea     r13, [rdi+0B8h]
0x18000a048  mov     [rsp+58h], eax; unsigned int
0x18000a04c  lea     r8, aSetaltplatform_0; "SetAltPlatform failed"
0x18000a053  mov     [rsp+0E0h+var_90], ebx; unsigned int
0x18000a057  lea     rax, PlatformEnv
0x18000a05e  mov     rax, [rax+r12*8]
0x18000a062  mov     r15, r12
0x18000a065  mov     [rsp+0E0h+var_98], rcx; unsigned __int16 *
0x18000a06a  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000a071  mov     dword ptr [rsp+0E0h+var_A0], edx; int
0x18000a075  lea     rdx, aCheckdriversig; "CheckDriverSigning"
0x18000a07c  mov     [rsp+0E0h+SectionName], rax; unsigned __int16 *
0x18000a081  mov     rax, [r13+0]
0x18000a085  mov     [rsp+0E0h+InfHandle], rax; unsigned __int16 *
0x18000a08a  mov     rax, [rdi+8]
0x18000a08e  mov     [rsp+0E0h+Result], rax; unsigned __int16 *
0x18000a093  mov     rax, [rdi]
0x18000a096  mov     [rsp+0E0h+Reserved2], rax; unsigned __int16 *
0x18000a09b  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000a0a0  test    ebx, ebx
0x18000a0a2  jnz     loc_18000A64D
0x18000a0a8  lea     rsi, [rdi+0ACh]
0x18000a0af  jmp     short loc_18000A0BB
0x18000a0b1  lea     r13, [rdi+0B8h]
0x18000a0b8  mov     rsi, r14
0x18000a0bb  call    cs:__imp_SetupOpenFileQueue
0x18000a0c1  mov     [rbp+37h+QueueHandle], rax
0x18000a0c5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a0c9  jnz     loc_18000A15C
0x18000a0cf  call    cs:__imp_GetLastError
0x18000a0d5  mov     edx, [r14]
0x18000a0d8  mov     ebx, eax
0x18000a0da  test    edx, edx
0x18000a0dc  jz      short loc_18000A0E7
0x18000a0de  mov     rcx, [rdi+0E0h]
0x18000a0e5  jmp     short loc_18000A0EC
0x18000a0e7  xor     ecx, ecx
0x18000a0e9  mov     r15, r12
0x18000a0ec  mov     r9, [rbp+37h+lpString1]; unsigned __int16 *
0x18000a0f0  lea     rax, PlatformEnv
0x18000a0f7  mov     rax, [rax+r15*8]
0x18000a0fb  lea     r8, aSetupopenfileq; "SetupOpenFileQueue failed"
0x18000a102  mov     dword ptr [rsp+58h], 80070006h; unsigned int
0x18000a10a  mov     [rsp+0E0h+var_90], 6; unsigned int
0x18000a112  mov     [rsp+0E0h+var_98], rcx; unsigned __int16 *
0x18000a117  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000a11e  mov     dword ptr [rsp+0E0h+var_A0], edx; int
0x18000a122  lea     rdx, aCheckdriversig; "CheckDriverSigning"
0x18000a129  mov     [rsp+0E0h+SectionName], rax; unsigned __int16 *
0x18000a12e  mov     rax, [r13+0]
0x18000a132  mov     [rsp+0E0h+InfHandle], rax; unsigned __int16 *
0x18000a137  mov     rax, [rdi+8]
0x18000a13b  mov     [rsp+0E0h+Result], rax; unsigned __int16 *
0x18000a140  mov     rax, [rdi]
0x18000a143  mov     [rsp+0E0h+Reserved2], rax; unsigned __int16 *
0x18000a148  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000a14d  test    ebx, ebx
0x18000a14f  jnz     loc_18000A64D
0x18000a155  lea     rsi, [rdi+0ACh]
0x18000a15c  mov     r14, [rbp+37h+InfSpec]
0x18000a163  lea     rax, [rdi+190h]
0x18000a16a  mov     r13, [rbp+37h+var_68]
0x18000a16e  mov     edx, r12d
0x18000a171  mov     r9, [rbp+37h+var_70]
0x18000a175  mov     rcx, rdi; struct _PSETUP_LOCAL_DATA *
0x18000a178  mov     r8, [rbp+37h+lpString1]
0x18000a17c  mov     qword ptr [rsp+0E0h+var_90], rax; __int64
0x18000a181  mov     rax, [rbp+37h+arg_68]
0x18000a188  mov     [rsp+0E0h+var_98], rax; __int64
0x18000a18d  mov     rax, [rbp+37h+arg_40]
0x18000a194  mov     [rsp+0E0h+var_A0], r14; __int64
0x18000a199  mov     rax, [rax+10h]
0x18000a19d  mov     [rsp+0E0h+SectionName], rax; SectionName
0x18000a1a2  mov     eax, dword ptr [rbp+37h+arg_30]
0x18000a1a5  mov     [rsp+0E0h+InfHandle], r13; InfHandle
0x18000a1aa  mov     dword ptr [rsp+0E0h+Result], eax; char
0x18000a1ae  mov     rax, [rbp+37h+arg_28]
0x18000a1b2  mov     [rsp+0E0h+Reserved2], rax; PCWSTR
0x18000a1b7  call    InstallAllInfSections
0x18000a1bc  test    eax, eax
0x18000a1be  jnz     loc_18000A259
0x18000a1c4  call    cs:__imp_GetLastError
0x18000a1ca  mov     ebx, eax
0x18000a1cc  test    eax, eax
0x18000a1ce  jle     short loc_18000A1D8
0x18000a1d0  movzx   eax, bx
0x18000a1d3  or      eax, 80070000h
0x18000a1d8  lea     rsi, [rdi+0ACh]
0x18000a1df  mov     edx, [rsi]
0x18000a1e1  test    edx, edx
0x18000a1e3  jz      short loc_18000A1EE
0x18000a1e5  mov     rcx, [rdi+0E0h]
0x18000a1ec  jmp     short loc_18000A1F0
0x18000a1ee  xor     ecx, ecx
0x18000a1f0  mov     r9, [rbp+37h+lpString1]; unsigned __int16 *
0x18000a1f4  lea     r8, aInstallallinfs_1; "InstallAllInfSections failed"
0x18000a1fb  mov     [rsp+58h], eax; unsigned int
0x18000a1ff  mov     r15, r12
0x18000a202  mov     [rsp+0E0h+var_90], ebx; unsigned int
0x18000a206  lea     rax, PlatformEnv
0x18000a20d  mov     rax, [rax+r12*8]
0x18000a211  mov     [rsp+0E0h+var_98], rcx; unsigned __int16 *
0x18000a216  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000a21d  mov     dword ptr [rsp+0E0h+var_A0], edx; int
0x18000a221  lea     rdx, aCheckdriversig; "CheckDriverSigning"
0x18000a228  mov     [rsp+0E0h+SectionName], rax; unsigned __int16 *
0x18000a22d  mov     rax, [rdi+0B8h]
0x18000a234  mov     [rsp+0E0h+InfHandle], rax; unsigned __int16 *
0x18000a239  mov     rax, [rdi+8]
0x18000a23d  mov     [rsp+0E0h+Result], rax; unsigned __int16 *
0x18000a242  mov     rax, [rdi]
0x18000a245  mov     [rsp+0E0h+Reserved2], rax; unsigned __int16 *
0x18000a24a  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000a24f  test    ebx, ebx
0x18000a251  jnz     loc_18000A651
0x18000a257  jmp     short loc_18000A25C
0x18000a259  mov     r15, r12
0x18000a25c  mov     rcx, [rbp+37h+OwnerWindow]; OwnerWindow
0x18000a260  xor     r9d, r9d; Reserved1
0x18000a263  xor     r8d, r8d; ProgressMessage
0x18000a266  mov     [rsp+0E0h+Reserved2], 0; Reserved2
0x18000a26f  or      rdx, 0FFFFFFFFFFFFFFFFh; AlternateProgressWindow
0x18000a273  call    cs:__imp_SetupInitDefaultQueueCallbackEx
0x18000a279  mov     [rbp+37h+var_60], rax
0x18000a27d  test    rax, rax
0x18000a280  jnz     loc_18000A31B
  ... truncated ...
```
