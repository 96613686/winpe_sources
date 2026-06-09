# CEnergyTaskHandler::RunEnergyReport(void)

- ea: `0x180002728`
- end: `0x1800029b6`
- name: `?RunEnergyReport@CEnergyTaskHandler@@AEAAJXZ`
- size: `654`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002da0`

## callees

- `0x1800023f8`
- `0x180002728`
- `0x180002c00`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002965`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002965`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000289e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000289e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000287d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000287d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000296f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000296f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800027e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800027e6`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180002927`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180002927`
- `ENERGY!EnergyWizard_CollectTrace` at `0x180002893`
- `ENERGY!EnergyWizard_CollectTrace` at `0x180002893`
- `ENERGY!EnergyWizard_Analyze` at `0x1800028ca`
- `ENERGY!EnergyWizard_Analyze` at `0x1800028ca`
- `ENERGY!EnergyWizard_TransformReport` at `0x180002942`
- `ENERGY!EnergyWizard_TransformReport` at `0x180002942`
- `ENERGY!EnergyWizard_SqmAnalysis` at `0x1800028fc`
- `ENERGY!EnergyWizard_SqmAnalysis` at `0x1800028fc`
- `ENERGY!EnergyWizard_SaveReport` at `0x1800028e4`
- `ENERGY!EnergyWizard_SaveReport` at `0x1800028e4`
- `ENERGY!EnergyWizard_CreateEnergyWizard` at `0x180002851`
- `ENERGY!EnergyWizard_CreateEnergyWizard` at `0x180002851`
- `ENERGY!EnergyWizard_DestroyEnergyWizard` at `0x180002987`
- `ENERGY!EnergyWizard_DestroyEnergyWizard` at `0x180002987`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180002784`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathAndSubDirW` at `0x180002784`

## string_xrefs

- `0x1800027c4`: `%s\energy-report-latest.xml`
- `0x180002817`: `%s\energy-report-%04d-%02d-%02d.xml`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::RunEnergyReport(CEnergyTaskHandler *this)
{
  __int64 EnergyWizard; // rsi
  int v3; // edi
  CEnergyTaskHandler *v4; // rcx
  const unsigned __int16 *v5; // r8
  unsigned int v6; // r9d
  signed int LastError; // eax
  LPCWSTR pszSubDir; // [rsp+20h] [rbp-E0h]
  LPWSTR pszPath; // [rsp+28h] [rbp-D8h]
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v12[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR NewFileName[264]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v16[264]; // [rsp+890h] [rbp+790h] BYREF

  EnergyWizard = 0;
  SystemTime = 0;
  v3 = SHGetFolderPathAndSubDirW(0, 35, 0, 0, L"Microsoft\\Windows\\Power Efficiency Diagnostics\\", v12);
  if ( v3 >= 0 )
  {
    v3 = StringCchPrintfW(FileName, 0x104u, L"%s\\energy-trace.etl", v12);
    if ( v3 >= 0 )
    {
      v3 = StringCchPrintfW(ExistingFileName, 0x104u, L"%s\\energy-report-latest.xml", v12);
      if ( v3 >= 0 )
      {
        GetLocalTime(&SystemTime);
        LODWORD(pszPath) = SystemTime.wMonth;
        LODWORD(pszSubDir) = SystemTime.wYear;
        v3 = StringCchPrintfW(
               NewFileName,
               0x104u,
               L"%s\\energy-report-%04d-%02d-%02d.xml",
               v12,
               pszSubDir,
               pszPath,
               SystemTime.wDay);
        if ( v3 >= 0 )
        {
          v3 = StringCchPrintfW(v16, 0x104u, L"%s\\energy-report.html", v12);
          if ( v3 >= 0 )
          {
            EnergyWizard = EnergyWizard_CreateEnergyWizard();
            if ( EnergyWizard )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
              *((_QWORD *)this + 12) = EnergyWizard;
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
              v3 = EnergyWizard_CollectTrace(EnergyWizard, FileName, 60);
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
              *((_QWORD *)this + 12) = 0;
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
              if ( v3 >= 0 )
              {
                v3 = EnergyWizard_Analyze(EnergyWizard, FileName, 0);
                if ( v3 >= 0 )
                {
                  v3 = EnergyWizard_SaveReport(EnergyWizard, ExistingFileName);
                  if ( v3 >= 0 )
                  {
                    EnergyWizard_SqmAnalysis(EnergyWizard, 1);
                    if ( !CopyFileExW(ExistingFileName, NewFileName, 0, 0, 0, 0)
                      || (v3 = EnergyWizard_TransformReport(EnergyWizard, ExistingFileName, v16), v3 >= 0)
                      && (v3 = CEnergyTaskHandler::ReportsCleanup(v4, v12, v5, v6), v3 >= 0)
                      && !DeleteFileW(FileName) )
                    {
                      LastError = GetLastError();
                      v3 = LastError;
                      if ( LastError > 0 )
                        v3 = (unsigned __int16)LastError | 0x80070000;
                    }
                  }
                }
              }
            }
            else
            {
              v3 = -2147467259;
            }
          }
        }
      }
    }
  }
  EnergyWizard_DestroyEnergyWizard(EnergyWizard);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002728  mov     [rsp-8+arg_8], rbx
0x18000272d  mov     [rsp-8+arg_10], rsi
0x180002732  push    rbp
0x180002733  push    rdi
0x180002734  push    r14
0x180002736  lea     rbp, [rsp-9B0h]
0x18000273e  sub     rsp, 0AB0h
0x180002745  mov     rax, cs:__security_cookie
0x18000274c  xor     rax, rsp
0x18000274f  mov     [rbp+9C0h+var_20], rax
0x180002756  lea     rax, [rsp+0AC0h+var_A70]
0x18000275b  mov     r14, rcx
0x18000275e  mov     [rsp+0AC0h+pszPath], rax; pszPath
0x180002763  xorps   xmm0, xmm0
0x180002766  lea     rax, pszSubDir; "Microsoft\\Windows\\Power Efficiency Di"...
0x18000276d  xor     esi, esi
0x18000276f  xor     r9d, r9d; dwFlags
0x180002772  mov     [rsp+0AC0h+pszSubDir], rax; pszSubDir
0x180002777  xor     r8d, r8d; hToken
0x18000277a  xor     ecx, ecx; hwnd
0x18000277c  movups  xmmword ptr [rsp+0AC0h+SystemTime.wYear], xmm0
0x180002781  lea     edx, [rsi+23h]; csidl
0x180002784  call    cs:__imp_SHGetFolderPathAndSubDirW
0x18000278a  mov     edi, eax
0x18000278c  test    eax, eax
0x18000278e  js      loc_180002984
0x180002794  mov     ebx, 104h
0x180002799  lea     r9, [rsp+0AC0h+var_A70]
0x18000279e  mov     edx, ebx; unsigned __int64
0x1800027a0  lea     r8, aSEnergyTraceEt; "%s\\energy-trace.etl"
0x1800027a7  lea     rcx, [rbp+9C0h+FileName]; unsigned __int16 *
0x1800027ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800027b3  mov     edi, eax
0x1800027b5  test    eax, eax
0x1800027b7  js      loc_180002984
0x1800027bd  lea     r9, [rsp+0AC0h+var_A70]
0x1800027c2  mov     edx, ebx; unsigned __int64
0x1800027c4  lea     r8, aSEnergyReportL; "%s\\energy-report-latest.xml"
0x1800027cb  lea     rcx, [rbp+9C0h+ExistingFileName]; unsigned __int16 *
0x1800027d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800027d7  mov     edi, eax
0x1800027d9  test    eax, eax
0x1800027db  js      loc_180002984
0x1800027e1  lea     rcx, [rsp+0AC0h+SystemTime]; lpSystemTime
0x1800027e6  call    cs:__imp_GetLocalTime
0x1800027ec  movzx   ecx, [rsp+0AC0h+SystemTime.wMonth]
0x1800027f1  lea     r9, [rsp+0AC0h+var_A70]
0x1800027f6  movzx   r8d, [rsp+0AC0h+SystemTime.wYear]
0x1800027fc  mov     edx, ebx; unsigned __int64
0x1800027fe  movzx   eax, [rsp+0AC0h+SystemTime.wDay]
0x180002803  mov     [rsp+0AC0h+var_A90], eax
0x180002807  mov     dword ptr [rsp+0AC0h+pszPath], ecx
0x18000280b  lea     rcx, [rbp+9C0h+NewFileName]; unsigned __int16 *
0x180002812  mov     dword ptr [rsp+0AC0h+pszSubDir], r8d
0x180002817  lea     r8, aSEnergyReport0; "%s\\energy-report-%04d-%02d-%02d.xml"
0x18000281e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002823  mov     edi, eax
0x180002825  test    eax, eax
0x180002827  js      loc_180002984
0x18000282d  lea     r9, [rsp+0AC0h+var_A70]
0x180002832  mov     edx, ebx; unsigned __int64
0x180002834  lea     r8, aSEnergyReportH; "%s\\energy-report.html"
0x18000283b  lea     rcx, [rbp+9C0h+var_230]; unsigned __int16 *
0x180002842  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002847  mov     edi, eax
0x180002849  test    eax, eax
0x18000284b  js      loc_180002984
0x180002851  call    cs:__imp_EnergyWizard_CreateEnergyWizard
0x180002857  mov     rsi, rax
0x18000285a  test    rax, rax
0x18000285d  jnz     short loc_180002869
0x18000285f  mov     edi, 80004005h
0x180002864  jmp     loc_180002984
0x180002869  lea     rbx, [r14+38h]
0x18000286d  mov     rcx, rbx; lpCriticalSection
0x180002870  call    cs:__imp_EnterCriticalSection
0x180002876  mov     rcx, rbx; lpCriticalSection
0x180002879  mov     [r14+60h], rsi
0x18000287d  call    cs:__imp_LeaveCriticalSection
0x180002883  mov     r8d, 3Ch ; '<'
0x180002889  lea     rdx, [rbp+9C0h+FileName]
0x180002890  mov     rcx, rsi
0x180002893  call    cs:__imp_EnergyWizard_CollectTrace
0x180002899  mov     rcx, rbx; lpCriticalSection
0x18000289c  mov     edi, eax
0x18000289e  call    cs:__imp_EnterCriticalSection
0x1800028a4  mov     rcx, rbx; lpCriticalSection
0x1800028a7  mov     qword ptr [r14+60h], 0
0x1800028af  call    cs:__imp_LeaveCriticalSection
0x1800028b5  test    edi, edi
0x1800028b7  js      loc_180002984
0x1800028bd  xor     r8d, r8d
0x1800028c0  lea     rdx, [rbp+9C0h+FileName]
0x1800028c7  mov     rcx, rsi
0x1800028ca  call    cs:__imp_EnergyWizard_Analyze
0x1800028d0  mov     edi, eax
0x1800028d2  test    eax, eax
0x1800028d4  js      loc_180002984
0x1800028da  lea     rdx, [rbp+9C0h+ExistingFileName]
0x1800028e1  mov     rcx, rsi
0x1800028e4  call    cs:__imp_EnergyWizard_SaveReport
0x1800028ea  mov     edi, eax
0x1800028ec  test    eax, eax
0x1800028ee  js      loc_180002984
0x1800028f4  mov     edx, 1
0x1800028f9  mov     rcx, rsi
0x1800028fc  call    cs:__imp_EnergyWizard_SqmAnalysis
0x180002902  xor     r9d, r9d; lpData
0x180002905  mov     dword ptr [rsp+0AC0h+pszPath], 0; dwCopyFlags
0x18000290d  xor     r8d, r8d; lpProgressRoutine
0x180002910  mov     [rsp+0AC0h+pszSubDir], 0; pbCancel
0x180002919  lea     rdx, [rbp+9C0h+NewFileName]; lpNewFileName
0x180002920  lea     rcx, [rbp+9C0h+ExistingFileName]; lpExistingFileName
0x180002927  call    cs:__imp_CopyFileExW
0x18000292d  test    eax, eax
0x18000292f  jz      short loc_18000296F
0x180002931  lea     r8, [rbp+9C0h+var_230]
0x180002938  mov     rcx, rsi
0x18000293b  lea     rdx, [rbp+9C0h+ExistingFileName]
0x180002942  call    cs:__imp_EnergyWizard_TransformReport
0x180002948  mov     edi, eax
0x18000294a  test    eax, eax
0x18000294c  js      short loc_180002984
0x18000294e  lea     rdx, [rsp+0AC0h+var_A70]; unsigned __int16 *
0x180002953  call    ?ReportsCleanup@CEnergyTaskHandler@@AEAAJPEBG0K@Z; CEnergyTaskHandler::ReportsCleanup(ushort const *,ushort const *,ulong)
0x180002958  mov     edi, eax
0x18000295a  test    eax, eax
0x18000295c  js      short loc_180002984
0x18000295e  lea     rcx, [rbp+9C0h+FileName]; lpFileName
0x180002965  call    cs:__imp_DeleteFileW
0x18000296b  test    eax, eax
0x18000296d  jnz     short loc_180002984
0x18000296f  call    cs:__imp_GetLastError
0x180002975  mov     edi, eax
0x180002977  test    eax, eax
0x180002979  jle     short loc_180002984
0x18000297b  movzx   edi, ax
0x18000297e  or      edi, 80070000h
0x180002984  mov     rcx, rsi
0x180002987  call    cs:__imp_EnergyWizard_DestroyEnergyWizard
0x18000298d  mov     eax, edi
0x18000298f  mov     rcx, [rbp+9C0h+var_20]
0x180002996  xor     rcx, rsp; StackCookie
0x180002999  call    __security_check_cookie
0x18000299e  lea     r11, [rsp+0AC0h+var_10]
0x1800029a6  mov     rbx, [r11+28h]
0x1800029aa  mov     rsi, [r11+30h]
0x1800029ae  mov     rsp, r11
0x1800029b1  pop     r14
0x1800029b3  pop     rdi
0x1800029b4  pop     rbp
0x1800029b5  retn
```
