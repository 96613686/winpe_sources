# PrintConfigDataHelper::CreateConfigProviderHandle(ushort const *,_INIDRIVER *,PrintConfigDataHelper::ConfigProviderHandle * *)

- ea: `0x1800a0318`
- end: `0x1800a0655`
- name: `?CreateConfigProviderHandle@PrintConfigDataHelper@@YAKPEBGPEAU_INIDRIVER@@PEAPEAUConfigProviderHandle@1@@Z`
- size: `829`
- prototype: `__int64 __fastcall(PrintConfigDataHelper *this, const unsigned __int16 *, struct _INIDRIVER *, struct PrintConfigDataHelper::ConfigProviderHandle **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008a1fc`
- `0x1800a065c`

## callees

- `0x180008520`
- `0x180008560`
- `0x180009630`
- `0x18000fb8c`
- `0x180011f74`
- `0x18001683c`
- `0x180017a08`
- `0x18002fda0`
- `0x18002fdcc`
- `0x18003ea2c`
- `0x180043740`
- `0x180046a5c`
- `0x180073be0`
- `0x1800a0318`
- `0x1800ca8c4`
- `0x1800caa48`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a0411`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a0411`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a0382`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a0382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a041c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a03e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a041c`
- `SPOOLSS!DllFreeSplStr` at `0x1800a05be`
- `SPOOLSS!DllFreeSplStr` at `0x1800a05be`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800a0369`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800a0369`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a03c8`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a03c8`

## string_xrefs

- `0x1800a051e`: `Microsoft enhanced Point and Print compatibility driver`
- `0x1800a03e7`: `Failed to revert to Spooler service for loading the binary, %d`
- `0x1800a0407`: `DllGetClassObject`
- `0x1800a03b9`: `PrintConfigDataHelper::CreateConfigProviderHandle`
- `0x1800a03f3`: `PrintConfigDataHelper::CreateConfigProviderHandle`
- `0x1800a03d8`: `Failed to impersonate printer client, %d`

## pseudocode

```c
__int64 __fastcall PrintConfigDataHelper::CreateConfigProviderHandle(
        PrintConfigDataHelper *this,
        const unsigned __int16 *a2,
        struct _INIDRIVER *a3,
        struct PrintConfigDataHelper::ConfigProviderHandle **a4)
{
  struct _INIDRIVER *v4; // rsi
  HMODULE v7; // r14
  const WCHAR *ConfigFilePath; // r12
  __int64 LastError; // rdi
  HANDLE v10; // rbx
  HMODULE Library; // rax
  DWORD v12; // eax
  unsigned __int16 *v13; // rdx
  FARPROC ProcAddress; // rax
  OLECHAR *v15; // rbx
  int v16; // edx
  int v17; // esi
  __int64 v18; // rax
  struct _INIDRIVER *DriverInEnvironment; // r13
  struct _INIENVIRONMENT *IniKey; // rax
  __int64 v21; // rcx
  unsigned __int16 *v22; // r15
  __int64 v23; // rcx
  TString *v24; // rcx
  NCoreLibrary::TString *v25; // rcx
  _QWORD *v26; // rax
  HMODULE v27; // rdx
  __int64 v28; // rsi
  __int64 v29; // rbx
  struct TString *v31; // [rsp+20h] [rbp-40h]
  HMODULE hModule; // [rsp+30h] [rbp-30h] BYREF
  void *v33; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v34; // [rsp+40h] [rbp-20h] BYREF
  int v35; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v36; // [rsp+50h] [rbp-10h]
  __int64 v38; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a3;
  v7 = 0;
  hModule = 0;
  v38 = 0;
  ConfigFilePath = (const WCHAR *)GetConfigFilePath(a2, pLocalIniSpooler, a3, a4);
  if ( !ConfigFilePath )
  {
    LODWORD(LastError) = 1168;
    goto LABEL_38;
  }
  v10 = RevertToPrinterSelf();
  if ( v10 )
  {
    Library = LoadLibraryExW(ConfigFilePath, 0, 0x800u);
    NCoreLibrary::TAutoHandleHMODULE::operator=(&hModule, Library);
    v7 = hModule;
    if ( hModule )
    {
      LODWORD(LastError) = 0;
    }
    else
    {
      LastError = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "PrintConfigDataHelper::CreateConfigProviderHandle",
        L"Failed to load %ws, %d",
        ConfigFilePath,
        LastError);
    }
    if ( ImpersonatePrinterClient(v10) )
      goto LABEL_11;
    v12 = GetLastError();
    v13 = L"Failed to impersonate printer client, %d";
  }
  else
  {
    v12 = GetLastError();
    v13 = L"Failed to revert to Spooler service for loading the binary, %d";
  }
  LODWORD(LastError) = v12;
  LocalSpoolerTelemetry::WriteDbgTraceError("PrintConfigDataHelper::CreateConfigProviderHandle", v13, v12);
LABEL_11:
  if ( !(_DWORD)LastError )
  {
    ProcAddress = GetProcAddress(v7, "DllGetClassObject");
    if ( ProcAddress )
    {
      v34 = 0;
      v15 = &NCoreLibrary::TString::gszNullState;
      v33 = &NCoreLibrary::TString::gszNullState;
      v17 = ((__int64 (__fastcall *)(GUID *, GUID *, _QWORD **))ProcAddress)(
              &GUID_a1550b03_fcec_49b8_9e6e_9a4c750e73c3,
              &GUID_00000001_0000_0000_c000_000000000046,
              &v34);
      if ( v17 < 0 )
        goto LABEL_28;
      v17 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, GUID *, __int64 *))(*v34 + 24LL))(
              v34,
              0,
              &GUID_ab9a1b23_4ae0_446e_9285_67bb71714f50,
              &v38);
      if ( v17 < 0 )
        goto LABEL_28;
      v17 = NUtilityLibrary::PrintCrackName(this, 0, (struct TString *)&v33, 0, v31);
      v15 = (OLECHAR *)v33;
      if ( v17 < 0 )
        goto LABEL_28;
      v17 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v38 + 40LL))(v38, v33);
      if ( v17 < 0 )
        goto LABEL_28;
      v18 = *((_QWORD *)a2 + 34);
      if ( v18 )
      {
        if ( *(_QWORD *)(v18 + 192) )
        {
          v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 64LL))(v38);
          if ( v17 < 0 )
            goto LABEL_28;
        }
      }
      EnterSplSem(0);
      DriverInEnvironment = 0;
      IniKey = (struct _INIENVIRONMENT *)FindIniKey(*((_QWORD *)pLocalIniSpooler + 6), L"Windows NT x86", 0);
      if ( !IniKey
        || (DriverInEnvironment = FindDriverInEnvironment(
                                    L"Microsoft enhanced Point and Print compatibility driver",
                                    IniKey)) == 0 )
      {
        v17 = -2147418113;
      }
      v35 = 1735554163;
      v22 = (unsigned __int16 *)&TString::gszNullState;
      v36 = (unsigned __int16 *)&TString::gszNullState;
      if ( v17 < 0 )
      {
        LeaveSplSem(v21);
      }
      else
      {
        TString::Update((TString *)&v35, *((const unsigned __int16 **)DriverInEnvironment + 24));
        LeaveSplSem(v23);
        v22 = v36;
        v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v38 + 72LL))(v38, v36);
      }
      TString::vFree(v24, v22);
      if ( v17 < 0 )
LABEL_28:
        LODWORD(LastError) = NCoreLibrary::StatusFromHResult((NCoreLibrary *)(unsigned int)v17, v16);
      NCoreLibrary::TString::vFree(v25, v15);
      if ( v34 )
        (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
      v4 = a3;
    }
    else
    {
      LODWORD(LastError) = GetLastError();
    }
  }
  DllFreeSplStr(ConfigFilePath);
  if ( !(_DWORD)LastError )
  {
    v26 = operator new(0x10u);
    v34 = v26;
    *v26 = 0;
    v26[1] = 0;
    *(_QWORD *)v4 = v26;
    v27 = 0;
    if ( v7 )
    {
      v27 = v7;
      hModule = 0;
    }
    NCoreLibrary::TAutoHandleHMODULE::operator=(v26, v27);
    v28 = *(_QWORD *)v4;
    v29 = v38;
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
    NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(v28 + 8);
    *(_QWORD *)(v28 + 8) = v29;
  }
LABEL_38:
  NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(&v38);
  NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&hModule);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800a0318  mov     [rsp-38h+arg_0], rbx
0x1800a031d  mov     [rsp-38h+arg_10], r8
0x1800a0322  push    rbp
0x1800a0323  push    rsi
0x1800a0324  push    rdi
0x1800a0325  push    r12
0x1800a0327  push    r13
0x1800a0329  push    r14
0x1800a032b  push    r15
0x1800a032d  mov     rbp, rsp
0x1800a0330  sub     rsp, 60h
0x1800a0334  mov     rsi, r8
0x1800a0337  mov     r15, rdx
0x1800a033a  mov     r13, rcx
0x1800a033d  xor     r14d, r14d
0x1800a0340  mov     [rbp+hModule], r14
0x1800a0344  mov     [rbp+arg_18], r14
0x1800a0348  mov     rdx, cs:pLocalIniSpooler
0x1800a034f  mov     rcx, r15
0x1800a0352  call    GetConfigFilePath
0x1800a0357  mov     r12, rax
0x1800a035a  test    rax, rax
0x1800a035d  jnz     short loc_1800A0369
0x1800a035f  mov     edi, 490h
0x1800a0364  jmp     loc_1800A0628
0x1800a0369  call    cs:__imp_RevertToPrinterSelf
0x1800a036f  mov     rbx, rax
0x1800a0372  test    rax, rax
0x1800a0375  jz      short loc_1800A03E1
0x1800a0377  xor     edx, edx; hFile
0x1800a0379  mov     r8d, 800h; dwFlags
0x1800a037f  mov     rcx, r12; lpLibFileName
0x1800a0382  call    cs:__imp_LoadLibraryExW
0x1800a0388  mov     rdx, rax
0x1800a038b  lea     rcx, [rbp+hModule]
0x1800a038f  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x1800a0394  mov     r14, [rbp+hModule]
0x1800a0398  test    r14, r14
0x1800a039b  jz      short loc_1800A03A4
0x1800a039d  xor     edi, edi
0x1800a039f  test    r14, r14
0x1800a03a2  jnz     short loc_1800A03C5
0x1800a03a4  call    cs:__imp_GetLastError
0x1800a03aa  mov     edi, eax
0x1800a03ac  mov     r9d, eax
0x1800a03af  mov     r8, r12
0x1800a03b2  lea     rdx, aFailedToLoadWs; "Failed to load %ws, %d"
0x1800a03b9  lea     rcx, aPrintconfigdat; "PrintConfigDataHelper::CreateConfigProv"...
0x1800a03c0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a03c5  mov     rcx, rbx; hToken
0x1800a03c8  call    cs:__imp_ImpersonatePrinterClient
0x1800a03ce  test    eax, eax
0x1800a03d0  jnz     short loc_1800A03FF
0x1800a03d2  call    cs:__imp_GetLastError
0x1800a03d8  lea     rdx, aFailedToImpers_2; "Failed to impersonate printer client, %"...
0x1800a03df  jmp     short loc_1800A03EE
0x1800a03e1  call    cs:__imp_GetLastError
0x1800a03e7  lea     rdx, aFailedToRevert_3; "Failed to revert to Spooler service for"...
0x1800a03ee  mov     edi, eax
0x1800a03f0  mov     r8d, eax
0x1800a03f3  lea     rcx, aPrintconfigdat; "PrintConfigDataHelper::CreateConfigProv"...
0x1800a03fa  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a03ff  test    edi, edi
0x1800a0401  jnz     loc_1800A05BB
0x1800a0407  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x1800a040e  mov     rcx, r14; hModule
0x1800a0411  call    cs:__imp_GetProcAddress
0x1800a0417  test    rax, rax
0x1800a041a  jnz     short loc_1800A0429
0x1800a041c  call    cs:__imp_GetLastError
0x1800a0422  mov     edi, eax
0x1800a0424  jmp     loc_1800A05BB
0x1800a0429  mov     [rbp+var_20], 0
0x1800a0431  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800a0438  mov     [rbp+var_28], rbx
0x1800a043c  lea     r8, [rbp+var_20]
0x1800a0440  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x1800a0447  lea     rcx, _GUID_a1550b03_fcec_49b8_9e6e_9a4c750e73c3
0x1800a044e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0453  mov     esi, eax
0x1800a0455  test    eax, eax
0x1800a0457  js      loc_1800A058F
0x1800a045d  mov     rcx, [rbp+var_20]
0x1800a0461  mov     rax, [rcx]
0x1800a0464  lea     r9, [rbp+arg_18]
0x1800a0468  lea     r8, _GUID_ab9a1b23_4ae0_446e_9285_67bb71714f50
0x1800a046f  xor     edx, edx
0x1800a0471  mov     rax, [rax+18h]
0x1800a0475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a047a  mov     esi, eax
0x1800a047c  test    eax, eax
0x1800a047e  js      loc_1800A058F
0x1800a0484  xor     r9d, r9d; struct TString *
0x1800a0487  lea     r8, [rbp+var_28]; struct TString *
0x1800a048b  xor     edx, edx; NCoreLibrary::TString *
0x1800a048d  mov     rcx, r13; this
0x1800a0490  call    ?PrintCrackName@NUtilityLibrary@@YAJPEBGPEAVTString@NCoreLibrary@@11@Z; NUtilityLibrary::PrintCrackName(ushort const *,NCoreLibrary::TString *,NCoreLibrary::TString *,NCoreLibrary::TString *)
0x1800a0495  mov     esi, eax
0x1800a0497  mov     rbx, [rbp+var_28]
0x1800a049b  test    eax, eax
0x1800a049d  js      loc_1800A058F
0x1800a04a3  mov     rcx, [rbp+arg_18]
0x1800a04a7  mov     rax, [rcx]
0x1800a04aa  mov     rdx, rbx
0x1800a04ad  mov     rax, [rax+28h]
0x1800a04b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a04b6  mov     esi, eax
0x1800a04b8  test    eax, eax
0x1800a04ba  js      loc_1800A058F
0x1800a04c0  mov     rax, [r15+110h]
0x1800a04c7  test    rax, rax
0x1800a04ca  jz      short loc_1800A04F2
0x1800a04cc  mov     rdx, [rax+0C0h]
0x1800a04d3  test    rdx, rdx
0x1800a04d6  jz      short loc_1800A04F2
0x1800a04d8  mov     rcx, [rbp+arg_18]
0x1800a04dc  mov     rax, [rcx]
0x1800a04df  mov     rax, [rax+40h]
0x1800a04e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a04e8  mov     esi, eax
0x1800a04ea  test    eax, eax
0x1800a04ec  js      loc_1800A058F
0x1800a04f2  xor     ecx, ecx
0x1800a04f4  call    EnterSplSem
0x1800a04f9  xor     r13d, r13d
0x1800a04fc  xor     r8d, r8d
0x1800a04ff  lea     rdx, aWindowsNtX86; "Windows NT x86"
0x1800a0506  mov     rcx, cs:pLocalIniSpooler
0x1800a050d  mov     rcx, [rcx+30h]
0x1800a0511  call    FindIniKey
0x1800a0516  test    rax, rax
0x1800a0519  jz      short loc_1800A0532
0x1800a051b  mov     rdx, rax; struct _INIENVIRONMENT *
0x1800a051e  lea     rcx, aMicrosoftEnhan; "Microsoft enhanced Point and Print comp"...
0x1800a0525  call    ?FindDriverInEnvironment@@YAPEAU_INIDRIVER@@PEBGPEAU_INIENVIRONMENT@@@Z; FindDriverInEnvironment(ushort const *,_INIENVIRONMENT *)
0x1800a052a  mov     r13, rax
0x1800a052d  test    rax, rax
0x1800a0530  jnz     short loc_1800A0537
0x1800a0532  mov     esi, 8000FFFFh
0x1800a0537  mov     [rbp+var_18], 67727473h
0x1800a053e  lea     r15, ?gszNullState@TString@@0PAGA; ushort near * TString::gszNullState
0x1800a0545  mov     [rbp+var_10], r15
0x1800a0549  test    esi, esi
0x1800a054b  js      short loc_1800A057D
0x1800a054d  mov     rdx, [r13+0C0h]; unsigned __int16 *
0x1800a0554  lea     rcx, [rbp+var_18]; this
0x1800a0558  call    ?Update@TString@@QEAAJPEBG@Z; TString::Update(ushort const *)
0x1800a055d  call    LeaveSplSem
0x1800a0562  mov     rcx, [rbp+arg_18]
0x1800a0566  mov     rax, [rcx]
0x1800a0569  mov     r15, [rbp+var_10]
0x1800a056d  mov     rdx, r15
0x1800a0570  mov     rax, [rax+48h]
0x1800a0574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0579  mov     esi, eax
0x1800a057b  jmp     short loc_1800A0583
0x1800a057d  call    LeaveSplSem
0x1800a0582  nop
0x1800a0583  mov     rdx, r15; unsigned __int16 *
0x1800a0586  call    ?vFree@TString@@AEAAXPEAG@Z; TString::vFree(ushort *)
0x1800a058b  test    esi, esi
0x1800a058d  jns     short loc_1800A0598
0x1800a058f  mov     ecx, esi; this
0x1800a0591  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x1800a0596  mov     edi, eax
0x1800a0598  mov     rdx, rbx; void *
0x1800a059b  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1800a05a0  nop
0x1800a05a1  mov     rcx, [rbp+var_20]
0x1800a05a5  test    rcx, rcx
0x1800a05a8  jz      short loc_1800A05B7
0x1800a05aa  mov     rax, [rcx]
0x1800a05ad  mov     rax, [rax+10h]
0x1800a05b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a05b6  nop
0x1800a05b7  mov     rsi, [rbp+arg_10]
0x1800a05bb  mov     rcx, r12
0x1800a05be  call    cs:__imp_DllFreeSplStr
0x1800a05c4  test    edi, edi
0x1800a05c6  jnz     short loc_1800A0628
0x1800a05c8  lea     ecx, [rdi+10h]; Size
0x1800a05cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a05d0  mov     [rbp+var_20], rax
0x1800a05d4  mov     qword ptr [rax], 0
0x1800a05db  mov     qword ptr [rax+8], 0
0x1800a05e3  mov     [rsi], rax
0x1800a05e6  xor     edx, edx
0x1800a05e8  test    r14, r14
0x1800a05eb  jz      short loc_1800A05F8
0x1800a05ed  mov     rdx, r14
0x1800a05f0  mov     [rbp+hModule], 0
0x1800a05f8  mov     rcx, rax
0x1800a05fb  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x1800a0600  mov     rsi, [rsi]
0x1800a0603  mov     rbx, [rbp+arg_18]
0x1800a0607  test    rbx, rbx
0x1800a060a  jz      short loc_1800A061B
0x1800a060c  mov     rax, [rbx]
0x1800a060f  mov     rcx, rbx
0x1800a0612  mov     rax, [rax+8]
0x1800a0616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a061b  lea     rcx, [rsi+8]
0x1800a061f  call    ?Reset@?$TGenericSP@UIPrintProcessorQuery@@V?$TRefPtrCOM@UIPrintProcessorQuery@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(void)
0x1800a0624  mov     [rsi+8], rbx
0x1800a0628  lea     rcx, [rbp+arg_18]
0x1800a062c  call    ?Reset@?$TGenericSP@UIPrintProcessorQuery@@V?$TRefPtrCOM@UIPrintProcessorQuery@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<IPrintProcessorQuery,NCoreLibrary::TRefPtrCOM<IPrintProcessorQuery>,IPrintProcessorQuery *,0,IPrintProcessorQuery const *>::Reset(void)
0x1800a0631  nop
0x1800a0632  lea     rcx, [rbp+hModule]
0x1800a0636  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x1800a063b  mov     eax, edi
0x1800a063d  mov     rbx, [rsp+60h+arg_0]
0x1800a0645  add     rsp, 60h
0x1800a0649  pop     r15
0x1800a064b  pop     r14
0x1800a064d  pop     r13
0x1800a064f  pop     r12
0x1800a0651  pop     rdi
0x1800a0652  pop     rsi
0x1800a0653  pop     rbp
0x1800a0654  retn
```
