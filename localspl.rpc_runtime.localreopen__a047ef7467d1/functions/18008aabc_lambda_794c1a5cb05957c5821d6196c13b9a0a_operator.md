# _lambda_794c1a5cb05957c5821d6196c13b9a0a_::operator()

- ea: `0x18008aabc`
- end: `0x18008aed5`
- name: `_lambda_794c1a5cb05957c5821d6196c13b9a0a_::operator()`
- size: `1049`
- prototype: `void __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800893f8`

## callees

- `0x180005d90`
- `0x1800062a4`
- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x180013b00`
- `0x1800372f8`
- `0x18003ea2c`
- `0x18008aabc`
- `0x18008be6c`
- `0x18008d670`
- `0x18009ba20`
- `0x1800e3894`
- `0x1800e38a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ab57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008abbf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ac3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ad84`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ad9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ab57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008abbf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ac3a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ad84`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008ad9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008adea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008adea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008ac0f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008ac0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ae91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ae91`
- `SPOOLSS!RevertToPrinterSelf` at `0x18008ac6c`
- `SPOOLSS!RevertToPrinterSelf` at `0x18008ac6c`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008add8`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008ae21`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008add8`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008ae21`

## string_xrefs

- `0x18008abf0`: `PrintQueueV4DriverDirectory`
- `0x18008ab6e`: `ConfigDriverData`
- `0x18008ad7a`: `CopyFiles\ICM`
- `0x18008ae38`: `CopyFiles\`
- `0x18008ac30`: `SpoolDirectory`

## pseudocode

```c
void __fastcall lambda_794c1a5cb05957c5821d6196c13b9a0a_::operator()(__int64 **a1)
{
  __int64 v2; // r14
  __int64 v3; // rdx
  __int64 *v4; // rbx
  _WORD *v5; // rdx
  __int64 v6; // rbp
  __int64 *v7; // rcx
  _DWORD **v8; // rsi
  HANDLE v9; // r12
  const wchar_t *v10; // rbx
  int v11; // r15d
  int v12; // eax
  int v13; // eax
  __int64 *v14; // rbx
  const wchar_t *v15; // rbx
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  v2 = **a1;
  hKey = 0;
  if ( (unsigned int)ValidateSpoolHandle(v2, 0) )
  {
    v3 = *a1[1];
    if ( v3 )
    {
      if ( (*(_BYTE *)(v2 + 88) & 0x10) != 0 )
      {
LABEL_4:
        v4 = a1[2];
        *(_DWORD *)v4 = SplSetPrinterData(**a1, v3, *(_DWORD *)a1[3], *a1[4], *(_DWORD *)a1[5]);
        goto LABEL_52;
      }
      v5 = (_WORD *)*a1[6];
      if ( v5 )
      {
        if ( *v5 )
        {
          if ( !(unsigned int)_o__wcsicmp(L"PrinterDriverData", v5) )
          {
            v3 = *a1[1];
            goto LABEL_4;
          }
          if ( !wcscmp_0((const wchar_t *)*a1[6], L"ConfigDriverData") )
          {
            *(_DWORD *)a1[2] = 50;
            goto LABEL_50;
          }
          EnterSplSem(0);
          v6 = *(_QWORD *)(v2 + 64);
          if ( !(unsigned int)AccessGranted(1u, 4u, (struct _SPOOL *)v2)
            && ((unsigned int)_o__wcsicmp(L"QueueProperties", *a1[6])
             || !(unsigned int)AccessGranted(1u, 0x40u, (struct _SPOOL *)v2)) )
          {
            v8 = (_DWORD **)(a1 + 2);
            *(_DWORD *)a1[2] = 5;
LABEL_45:
            LeaveSplSem(v7);
            if ( !**v8 )
            {
              v15 = (const wchar_t *)*a1[6];
              if ( !wcsncmp_0(v15, L"CopyFiles\\", 0xAu)
                && (*(_DWORD *)(*(_QWORD *)(v2 + 168) + 168LL) & 0x4000000) == 0 )
              {
                SplCopyFileEvent(v2, v15, 1);
              }
            }
            goto LABEL_50;
          }
          if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)*a1[1], -1, L"PrintQueueV4DriverDirectory", -1) == 2 )
          {
            v8 = (_DWORD **)(a1 + 2);
            *(_DWORD *)a1[2] = 50;
            goto LABEL_45;
          }
          if ( !(unsigned int)_o__wcsicmp(*a1[1], L"SpoolDirectory")
            && !(unsigned int)IsValidSpoolDirectory((unsigned __int8 *)*a1[4], *(unsigned int *)a1[5]) )
          {
            v8 = (_DWORD **)(a1 + 2);
            *(_DWORD *)a1[2] = 87;
            goto LABEL_45;
          }
          v9 = RevertToPrinterSelf();
          v10 = (const wchar_t *)*a1[6];
          if ( !wcscmp_0(v10, L"DsSpooler") )
          {
            v11 = 1;
          }
          else if ( !wcscmp_0(v10, L"DsDriver") )
          {
            v11 = 2;
          }
          else
          {
            v11 = 0;
            if ( wcscmp_0(v10, L"DsUser") )
              goto LABEL_31;
            v11 = 4;
          }
          v7 = (__int64 *)*(unsigned int *)a1[3];
          if ( (unsigned int)v7 > 7 || (v12 = 146, !_bittest(&v12, (unsigned int)v7)) )
          {
            if ( (_DWORD)v7 != 3 || *(_DWORD *)a1[5] != 1 )
            {
              v8 = (_DWORD **)(a1 + 2);
              *(_DWORD *)a1[2] = 87;
LABEL_43:
              if ( v9 )
                ImpersonatePrinterClient(v9);
              goto LABEL_45;
            }
          }
LABEL_31:
          v13 = OpenPrinterKey(v6, 131103, &hKey, v10, 0);
          v8 = (_DWORD **)(a1 + 2);
          v7 = a1[2];
          *(_DWORD *)v7 = v13;
          if ( !*(_DWORD *)a1[2] )
          {
            v14 = a1[2];
            *(_DWORD *)v14 = SplRegSetValue(
                               hKey,
                               (const unsigned __int16 *)*a1[1],
                               *(_DWORD *)a1[3],
                               (const unsigned __int8 *)*a1[4],
                               *(_DWORD *)a1[5],
                               *(struct _INISPOOLER **)(v6 + 280));
            if ( !**v8 )
            {
              if ( !(unsigned int)_o__wcsicmp(*a1[6], L"CopyFiles\\ICM")
                && !(unsigned int)_o__wcsicmp(*a1[1], L"Module") )
              {
                UpdatePrinterIni((_INIPRINTER *)v6);
                SetPrinterChange(v6, 0, 0, 0x20000000, *(_QWORD *)(v2 + 168));
              }
              if ( v9 )
              {
                ImpersonatePrinterClient(v9);
                v9 = 0;
              }
              if ( ghDsUpdateThread && gdwDsUpdateThreadId == GetCurrentThreadId() )
                *(_DWORD *)(v6 + 344) |= v11;
              else
                *(_DWORD *)(v6 + 388) |= v11;
              UpdatePrinterIni((_INIPRINTER *)v6);
              v8 = (_DWORD **)(a1 + 2);
            }
          }
          goto LABEL_43;
        }
      }
    }
    *(_DWORD *)a1[2] = 87;
  }
LABEL_50:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_52:
  if ( (*(_DWORD *)a1[2] & 0xFFFFFFFD) != 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplSetPrinterDataEx::<lambda_794c1a5cb05957c5821d6196c13b9a0a>::operator ()",
      L"Failed to set printer data for key '%ws', value '%ws'.",
      *a1[6],
      *a1[1]);
}

```

## disassembly

```asm
0x18008aabc  mov     r11, rsp
0x18008aabf  push    rbx
0x18008aac0  push    rbp
0x18008aac1  push    rsi
0x18008aac2  push    rdi
0x18008aac3  push    r12
0x18008aac5  push    r13
0x18008aac7  push    r14
0x18008aac9  push    r15
0x18008aacb  sub     rsp, 38h
0x18008aacf  mov     rax, [rcx]
0x18008aad2  mov     rdi, rcx
0x18008aad5  xor     r13d, r13d
0x18008aad8  xor     edx, edx
0x18008aada  mov     r14, [rax]
0x18008aadd  mov     rcx, r14
0x18008aae0  mov     [r11+8], r13
0x18008aae4  call    ValidateSpoolHandle
0x18008aae9  test    eax, eax
0x18008aaeb  jz      loc_18008AE84
0x18008aaf1  mov     rax, [rdi+8]
0x18008aaf5  mov     rdx, [rax]
0x18008aaf8  test    rdx, rdx
0x18008aafb  jz      loc_18008AE7A
0x18008ab01  test    byte ptr [r14+58h], 10h
0x18008ab06  jz      short loc_18008AB36
0x18008ab08  mov     rax, [rdi+28h]
0x18008ab0c  mov     r8, [rdi+18h]
0x18008ab10  mov     r9, [rdi+20h]
0x18008ab14  mov     rcx, [rdi]
0x18008ab17  mov     eax, [rax]
0x18008ab19  mov     r8d, [r8]
0x18008ab1c  mov     r9, [r9]
0x18008ab1f  mov     rcx, [rcx]
0x18008ab22  mov     rbx, [rdi+10h]
0x18008ab26  mov     dword ptr [rsp+78h+lpString2], eax
0x18008ab2a  call    SplSetPrinterData
0x18008ab2f  mov     [rbx], eax
0x18008ab31  jmp     loc_18008AE97
0x18008ab36  mov     rax, [rdi+30h]
0x18008ab3a  mov     rdx, [rax]
0x18008ab3d  test    rdx, rdx
0x18008ab40  jz      loc_18008AE7A
0x18008ab46  cmp     [rdx], r13w
0x18008ab4a  jz      loc_18008AE7A
0x18008ab50  lea     rcx, szPrinterData; "PrinterDriverData"
0x18008ab57  call    cs:__imp__o__wcsicmp
0x18008ab5d  test    eax, eax
0x18008ab5f  jnz     short loc_18008AB6A
0x18008ab61  mov     rdx, [rdi+8]
0x18008ab65  mov     rdx, [rdx]
0x18008ab68  jmp     short loc_18008AB08
0x18008ab6a  mov     rcx, [rdi+30h]
0x18008ab6e  lea     rdx, aConfigdriverda; "ConfigDriverData"
0x18008ab75  mov     rcx, [rcx]; String1
0x18008ab78  call    wcscmp_0
0x18008ab7d  test    eax, eax
0x18008ab7f  jnz     short loc_18008AB90
0x18008ab81  mov     rax, [rdi+10h]
0x18008ab85  mov     dword ptr [rax], 32h ; '2'
0x18008ab8b  jmp     loc_18008AE84
0x18008ab90  xor     ecx, ecx
0x18008ab92  call    EnterSplSem
0x18008ab97  mov     rbp, [r14+40h]
0x18008ab9b  mov     edx, 4; unsigned int
0x18008aba0  mov     r8, r14; struct _SPOOL *
0x18008aba3  lea     esi, [rdx-3]
0x18008aba6  mov     ecx, esi; unsigned int
0x18008aba8  call    ?AccessGranted@@YAHKKPEAU_SPOOL@@@Z; AccessGranted(ulong,ulong,_SPOOL *)
0x18008abad  test    eax, eax
0x18008abaf  jnz     short loc_18008ABEC
0x18008abb1  mov     rdx, [rdi+30h]
0x18008abb5  lea     rcx, szQueuePropertiesData; "QueueProperties"
0x18008abbc  mov     rdx, [rdx]
0x18008abbf  call    cs:__imp__o__wcsicmp
0x18008abc5  test    eax, eax
0x18008abc7  jnz     short loc_18008ABDA
0x18008abc9  mov     r8, r14; struct _SPOOL *
0x18008abcc  lea     edx, [rsi+3Fh]; unsigned int
0x18008abcf  mov     ecx, esi; unsigned int
0x18008abd1  call    ?AccessGranted@@YAHKKPEAU_SPOOL@@@Z; AccessGranted(ulong,ulong,_SPOOL *)
0x18008abd6  test    eax, eax
0x18008abd8  jnz     short loc_18008ABEC
0x18008abda  lea     rsi, [rdi+10h]
0x18008abde  mov     rax, [rsi]
0x18008abe1  mov     dword ptr [rax], 5
0x18008abe7  jmp     loc_18008AE27
0x18008abec  mov     r8, [rdi+8]
0x18008abf0  lea     rax, String2; "PrintQueueV4DriverDirectory"
0x18008abf7  or      r9d, 0FFFFFFFFh; cchCount1
0x18008abfb  mov     edx, esi; dwCmpFlags
0x18008abfd  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18008ac02  mov     ecx, 7Fh; Locale
0x18008ac07  mov     [rsp+78h+lpString2], rax; lpString2
0x18008ac0c  mov     r8, [r8]; lpString1
0x18008ac0f  call    cs:__imp_CompareStringW
0x18008ac15  cmp     eax, 2
0x18008ac18  jnz     short loc_18008AC2C
0x18008ac1a  lea     rsi, [rdi+10h]
0x18008ac1e  mov     rax, [rsi]
0x18008ac21  mov     dword ptr [rax], 32h ; '2'
0x18008ac27  jmp     loc_18008AE27
0x18008ac2c  mov     rcx, [rdi+8]
0x18008ac30  lea     rdx, aSpooldirectory; "SpoolDirectory"
0x18008ac37  mov     rcx, [rcx]
0x18008ac3a  call    cs:__imp__o__wcsicmp
0x18008ac40  test    eax, eax
0x18008ac42  jnz     short loc_18008AC6C
0x18008ac44  mov     rdx, [rdi+28h]
0x18008ac48  mov     rcx, [rdi+20h]
0x18008ac4c  mov     edx, [rdx]; Size
0x18008ac4e  mov     rcx, [rcx]; Src
0x18008ac51  call    ?IsValidSpoolDirectory@@YAHPEAEK@Z; IsValidSpoolDirectory(uchar *,ulong)
0x18008ac56  test    eax, eax
0x18008ac58  jnz     short loc_18008AC6C
0x18008ac5a  lea     rsi, [rdi+10h]
0x18008ac5e  mov     rax, [rsi]
0x18008ac61  mov     dword ptr [rax], 57h ; 'W'
0x18008ac67  jmp     loc_18008AE27
0x18008ac6c  call    cs:__imp_RevertToPrinterSelf
0x18008ac72  mov     rcx, [rdi+30h]
0x18008ac76  lea     rdx, aDsspooler; "DsSpooler"
0x18008ac7d  mov     r12, rax
0x18008ac80  mov     rbx, [rcx]
0x18008ac83  mov     rcx, rbx; String1
0x18008ac86  call    wcscmp_0
0x18008ac8b  test    eax, eax
0x18008ac8d  jnz     short loc_18008AC94
0x18008ac8f  mov     r15d, esi
0x18008ac92  jmp     short loc_18008ACC7
0x18008ac94  lea     rdx, aDsdriver; "DsDriver"
0x18008ac9b  mov     rcx, rbx; String1
0x18008ac9e  call    wcscmp_0
0x18008aca3  test    eax, eax
0x18008aca5  jnz     short loc_18008ACAD
0x18008aca7  lea     r15d, [rax+2]
0x18008acab  jmp     short loc_18008ACC7
0x18008acad  lea     rdx, aDsuser; "DsUser"
0x18008acb4  mov     rcx, rbx; String1
0x18008acb7  mov     r15d, r13d
0x18008acba  call    wcscmp_0
0x18008acbf  test    eax, eax
0x18008acc1  jnz     short loc_18008ACFB
0x18008acc3  lea     r15d, [rax+4]
0x18008acc7  mov     rax, [rdi+18h]
0x18008accb  mov     ecx, [rax]
0x18008accd  cmp     ecx, 7
0x18008acd0  ja      short loc_18008ACDC
0x18008acd2  mov     eax, 92h
0x18008acd7  bt      eax, ecx
0x18008acda  jb      short loc_18008ACFB
0x18008acdc  cmp     ecx, 3
0x18008acdf  jnz     short loc_18008ACE9
0x18008ace1  mov     rax, [rdi+28h]
0x18008ace5  cmp     [rax], esi
0x18008ace7  jz      short loc_18008ACFB
0x18008ace9  lea     rsi, [rdi+10h]
0x18008aced  mov     rax, [rsi]
0x18008acf0  mov     dword ptr [rax], 57h ; 'W'
0x18008acf6  jmp     loc_18008AE19
0x18008acfb  mov     r9, rbx
0x18008acfe  mov     dword ptr [rsp+78h+lpString2], r13d
0x18008ad03  lea     r8, [rsp+78h+hKey]
0x18008ad0b  mov     edx, 2001Fh
0x18008ad10  mov     rcx, rbp
0x18008ad13  call    OpenPrinterKey
0x18008ad18  lea     rsi, [rdi+10h]
0x18008ad1c  mov     rcx, [rsi]
0x18008ad1f  mov     [rcx], eax
0x18008ad21  mov     rax, [rsi]
0x18008ad24  cmp     [rax], r13d
0x18008ad27  jnz     loc_18008AE19
0x18008ad2d  mov     rcx, [rdi+28h]
0x18008ad31  mov     rbx, rax
0x18008ad34  mov     rax, [rbp+118h]
0x18008ad3b  mov     r9, [rdi+20h]
0x18008ad3f  mov     r8, [rdi+18h]
0x18008ad43  mov     rdx, [rdi+8]
0x18008ad47  mov     qword ptr [rsp+78h+cchCount2], rax; struct _INISPOOLER *
0x18008ad4c  mov     eax, [rcx]
0x18008ad4e  mov     rcx, [rsp+78h+hKey]; void *
0x18008ad56  mov     r9, [r9]; unsigned __int8 *
0x18008ad59  mov     r8d, [r8]; unsigned int
0x18008ad5c  mov     rdx, [rdx]; unsigned __int16 *
0x18008ad5f  mov     dword ptr [rsp+78h+lpString2], eax; unsigned int
0x18008ad63  call    ?SplRegSetValue@@YAJPEAXPEBGKPEBEKPEAU_INISPOOLER@@@Z; SplRegSetValue(void *,ushort const *,ulong,uchar const *,ulong,_INISPOOLER *)
0x18008ad68  mov     [rbx], eax
0x18008ad6a  mov     rax, [rsi]
0x18008ad6d  cmp     [rax], r13d
0x18008ad70  jnz     loc_18008AE19
0x18008ad76  mov     rcx, [rdi+30h]
0x18008ad7a  lea     rdx, aCopyfilesIcm; "CopyFiles\\ICM"
0x18008ad81  mov     rcx, [rcx]
0x18008ad84  call    cs:__imp__o__wcsicmp
0x18008ad8a  test    eax, eax
0x18008ad8c  jnz     short loc_18008ADD0
0x18008ad8e  mov     rcx, [rdi+8]
0x18008ad92  lea     rdx, aModule; "Module"
0x18008ad99  mov     rcx, [rcx]
0x18008ad9c  call    cs:__imp__o__wcsicmp
0x18008ada2  test    eax, eax
0x18008ada4  jnz     short loc_18008ADD0
0x18008ada6  lea     edx, [rax+2]
0x18008ada9  mov     rcx, rbp; this
0x18008adac  call    UpdatePrinterIni
0x18008adb1  mov     rax, [r14+0A8h]
0x18008adb8  mov     r9d, 20000000h
0x18008adbe  xor     r8d, r8d
0x18008adc1  mov     [rsp+78h+lpString2], rax
0x18008adc6  xor     edx, edx
0x18008adc8  mov     rcx, rbp
0x18008adcb  call    SetPrinterChange
0x18008add0  test    r12, r12
0x18008add3  jz      short loc_18008ADE1
0x18008add5  mov     rcx, r12; hToken
0x18008add8  call    cs:__imp_ImpersonatePrinterClient
0x18008adde  mov     r12, r13
0x18008ade1  cmp     cs:?ghDsUpdateThread@@3PEAXEA, r13; void * ghDsUpdateThread
0x18008ade8  jz      short loc_18008AE01
0x18008adea  call    cs:__imp_GetCurrentThreadId
0x18008adf0  cmp     cs:?gdwDsUpdateThreadId@@3KA, eax; ulong gdwDsUpdateThreadId
0x18008adf6  jnz     short loc_18008AE01
0x18008adf8  or      [rbp+158h], r15d
0x18008adff  jmp     short loc_18008AE08
0x18008ae01  or      [rbp+184h], r15d
0x18008ae08  mov     edx, 3
0x18008ae0d  mov     rcx, rbp; this
0x18008ae10  call    UpdatePrinterIni
0x18008ae15  lea     rsi, [rdi+10h]
0x18008ae19  test    r12, r12
0x18008ae1c  jz      short loc_18008AE27
0x18008ae1e  mov     rcx, r12; hToken
0x18008ae21  call    cs:__imp_ImpersonatePrinterClient
0x18008ae27  call    LeaveSplSem
0x18008ae2c  mov     rax, [rsi]
0x18008ae2f  cmp     [rax], r13d
0x18008ae32  jnz     short loc_18008AE84
0x18008ae34  mov     rax, [rdi+30h]
0x18008ae38  lea     rdx, aCopyfiles; "CopyFiles\\"
0x18008ae3f  mov     r8d, 0Ah; MaxCount
0x18008ae45  mov     rbx, [rax]
0x18008ae48  mov     rcx, rbx; String1
0x18008ae4b  call    wcsncmp_0
0x18008ae50  test    eax, eax
0x18008ae52  jnz     short loc_18008AE84
0x18008ae54  mov     rax, [r14+0A8h]
0x18008ae5b  test    dword ptr [rax+0A8h], 4000000h
0x18008ae65  jnz     short loc_18008AE84
0x18008ae67  mov     r8d, 1
0x18008ae6d  mov     rdx, rbx
0x18008ae70  mov     rcx, r14
0x18008ae73  call    SplCopyFileEvent
0x18008ae78  jmp     short loc_18008AE84
0x18008ae7a  mov     rax, [rdi+10h]
0x18008ae7e  mov     dword ptr [rax], 57h ; 'W'
0x18008ae84  mov     rcx, [rsp+78h+hKey]; hKey
0x18008ae8c  test    rcx, rcx
0x18008ae8f  jz      short loc_18008AE97
0x18008ae91  call    cs:__imp_RegCloseKey
0x18008ae97  mov     rax, [rdi+10h]
0x18008ae9b  test    dword ptr [rax], 0FFFFFFFDh
0x18008aea1  jz      short loc_18008AEC4
0x18008aea3  mov     r9, [rdi+8]
0x18008aea7  lea     rdx, aFailedToSetPri_2; "Failed to set printer data for key '%ws"...
0x18008aeae  mov     r8, [rdi+30h]
0x18008aeb2  lea     rcx, aSplsetprinterd_2; "SplSetPrinterDataEx::<lambda_794c1a5cb0"...
0x18008aeb9  mov     r9, [r9]
0x18008aebc  mov     r8, [r8]
0x18008aebf  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18008aec4  add     rsp, 38h
0x18008aec8  pop     r15
0x18008aeca  pop     r14
0x18008aecc  pop     r13
0x18008aece  pop     r12
0x18008aed0  pop     rdi
0x18008aed1  pop     rsi
0x18008aed2  pop     rbp
0x18008aed3  pop     rbx
0x18008aed4  retn
```
