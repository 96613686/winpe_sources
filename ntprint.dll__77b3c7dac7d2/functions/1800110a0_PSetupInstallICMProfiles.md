# PSetupInstallICMProfiles

- ea: `0x1800110a0`
- end: `0x18001136c`
- name: `PSetupInstallICMProfiles`
- size: `716`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18000f698`

## callees

- `0x180001ea4`
- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000c368`
- `0x1800110a0`
- `0x1800348d8`
- `0x180035208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011288`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011213`
- `mscms!InstallColorProfileW` at `0x180011207`
- `mscms!InstallColorProfileW` at `0x180011207`
- `mscms!GetColorDirectoryW` at `0x180011157`
- `mscms!GetColorDirectoryW` at `0x180011157`

## string_xrefs

- `0x180011315`: `No ICM files to be installed`
- `0x18001112c`: `PSetupInstallICMProfiles`
- `0x18001124a`: `PSetupInstallICMProfiles`
- `0x1800112ae`: `PSetupInstallICMProfiles`
- `0x1800112e9`: `PSetupInstallICMProfiles`
- `0x180011321`: `PSetupInstallICMProfiles`
- `0x18001117c`: `GetColorDirectory failed`
- `0x18001123e`: `InstallColorProfile failed`

## pseudocode

```c
__int64 __fastcall PSetupInstallICMProfiles(unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int v5; // eax
  unsigned int v6; // ecx
  __int64 v7; // rax
  unsigned int v8; // ebx
  DWORD v9; // edx
  unsigned __int16 *v10; // rsi
  __int64 v11; // rax
  signed int LastError; // eax
  unsigned int v13; // ecx
  __int64 v14; // rax
  unsigned __int16 *v15; // rbx
  unsigned __int64 v16; // rdx
  DWORD pdwSize; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pBuffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(pBuffer, 0, 0x208u);
  pdwSize = 0;
  if ( a2 && *a2 )
  {
    if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    {
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"PSetupInstallICMProfiles",
        L"Windows Protected Print enabled",
        a1,
        0,
        0,
        0x800704EC);
    }
    else
    {
      pdwSize = 520;
      if ( GetColorDirectoryW(a1, pBuffer, &pdwSize) )
      {
        v7 = -1;
        v8 = 1;
        do
          ++v7;
        while ( pBuffer[v7] );
        v9 = v7 + 1;
        v10 = a2;
        pdwSize = v7 + 1;
        pBuffer[(unsigned int)v7] = 92;
        while ( 1 )
        {
          if ( !*v10 )
          {
            SplLogPrinterSetupGenericEvent(
              &SETUP_PRINTER_OPERATION_SUCCEEDED,
              L"PSetupInstallICMProfiles",
              a2,
              a1,
              0,
              0,
              0);
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          if ( (unsigned __int64)v9 + v11 + 1 > 0x104 )
            break;
          StringCchCopyW(&pBuffer[v9], 260 - v9, v10);
          v8 = InstallColorProfileW(0, pBuffer);
          if ( !v8 )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
            else
              v13 = LastError;
            SplLogPrinterSetupGenericEvent(
              &SETUP_PRINTER_OPERATION_FAILED,
              L"PSetupInstallICMProfiles",
              L"InstallColorProfile failed",
              pBuffer,
              0,
              LastError,
              v13);
          }
          v14 = -1;
          do
            ++v14;
          while ( v10[v14] );
          v10 += v14 + 1;
          if ( !v8 )
            return v8;
          v9 = pdwSize;
        }
        v18 = 0;
        SetLastError(8u);
        ConvertMultiToSingleSz(a2, &v18);
        v15 = v18;
        SplLogPrinterSetupGenericEvent(
          &SETUP_PRINTER_OPERATION_FAILED,
          L"PSetupInstallICMProfiles",
          L"Not enough memory",
          v18,
          0,
          8u,
          0x8007000E);
        if ( v15 )
          operator delete(v15, v16);
      }
      else
      {
        v5 = GetLastError();
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        else
          v6 = v5;
        SplLogPrinterSetupGenericEvent(
          &SETUP_PRINTER_OPERATION_FAILED,
          L"PSetupInstallICMProfiles",
          L"GetColorDirectory failed",
          a1,
          0,
          v5,
          v6);
      }
    }
    return 0;
  }
  else
  {
    SplLogPrinterSetupGenericEvent(
      &SETUP_PRINTER_OPERATION_SUCCEEDED,
      L"PSetupInstallICMProfiles",
      L"No ICM files to be installed",
      a1,
      0,
      0,
      0);
    return 1;
  }
}

```

## disassembly

```asm
0x1800110a0  mov     [rsp-8+arg_10], rbx
0x1800110a5  mov     [rsp-8+arg_18], rsi
0x1800110aa  push    rbp
0x1800110ab  push    rdi
0x1800110ac  push    r12
0x1800110ae  push    r14
0x1800110b0  push    r15
0x1800110b2  lea     rbp, [rsp-170h]
0x1800110ba  sub     rsp, 270h
0x1800110c1  mov     rax, cs:__security_cookie
0x1800110c8  xor     rax, rsp
0x1800110cb  mov     [rbp+190h+var_30], rax
0x1800110d2  mov     r14, rdx
0x1800110d5  mov     rdi, rcx
0x1800110d8  mov     ebx, 208h
0x1800110dd  lea     rcx, [rsp+290h+pBuffer]; void *
0x1800110e2  mov     r8d, ebx; Size
0x1800110e5  xor     edx, edx; Val
0x1800110e7  call    memset_0
0x1800110ec  xor     r15d, r15d
0x1800110ef  mov     [rsp+290h+pdwSize], r15d
0x1800110f4  test    r14, r14
0x1800110f7  jz      loc_180011310
0x1800110fd  cmp     [r14], r15w
0x180011101  jz      loc_180011310
0x180011107  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18001110c  test    al, al
0x18001110e  jz      short loc_180011146
0x180011110  mov     [rsp+290h+var_260], 800704ECh; unsigned int
0x180011118  lea     r8, aWindowsProtect; "Windows Protected Print enabled"
0x18001111f  mov     [rsp+290h+var_268], r15d; unsigned int
0x180011124  mov     r9, rdi; unsigned __int16 *
0x180011127  mov     [rsp+290h+var_270], r15; unsigned __int16 *
0x18001112c  lea     rdx, aPsetupinstalli_1; "PSetupInstallICMProfiles"
0x180011133  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18001113a  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001113f  xor     eax, eax
0x180011141  jmp     loc_180011341
0x180011146  lea     r8, [rsp+290h+pdwSize]; pdwSize
0x18001114b  mov     [rsp+290h+pdwSize], ebx
0x18001114f  lea     rdx, [rsp+290h+pBuffer]; pBuffer
0x180011154  mov     rcx, rdi; pMachineName
0x180011157  call    cs:__imp_GetColorDirectoryW
0x18001115d  test    eax, eax
0x18001115f  jnz     short loc_180011189
0x180011161  call    cs:__imp_GetLastError
0x180011167  test    eax, eax
0x180011169  jg      short loc_18001116F
0x18001116b  mov     ecx, eax
0x18001116d  jmp     short loc_180011178
0x18001116f  movzx   ecx, ax
0x180011172  or      ecx, 80070000h
0x180011178  mov     [rsp+290h+var_260], ecx
0x18001117c  lea     r8, aGetcolordirect; "GetColorDirectory failed"
0x180011183  mov     [rsp+290h+var_268], eax
0x180011187  jmp     short loc_180011124
0x180011189  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001118d  lea     rcx, [rsp+290h+pBuffer]
0x180011192  mov     rax, r12
0x180011195  mov     ebx, 1
0x18001119a  inc     rax
0x18001119d  cmp     [rcx+rax*2], r15w
0x1800111a2  jnz     short loc_18001119A
0x1800111a4  lea     edx, [rax+1]
0x1800111a7  mov     rsi, r14
0x1800111aa  lea     ecx, [rdx-1]
0x1800111ad  mov     [rsp+290h+pdwSize], edx
0x1800111b1  mov     eax, 5Ch ; '\'
0x1800111b6  mov     [rsp+rcx*2+290h+pBuffer], ax
0x1800111bb  cmp     [rsi], r15w
0x1800111bf  jz      loc_1800112E4
0x1800111c5  mov     ecx, edx
0x1800111c7  mov     rax, r12
0x1800111ca  inc     rax
0x1800111cd  cmp     [rsi+rax*2], r15w
0x1800111d2  jnz     short loc_1800111CA
0x1800111d4  inc     rax
0x1800111d7  add     rax, rcx
0x1800111da  cmp     rax, 104h
0x1800111e0  ja      loc_18001127C
0x1800111e6  mov     eax, 104h
0x1800111eb  mov     r8, rsi; unsigned __int16 *
0x1800111ee  sub     eax, edx
0x1800111f0  mov     edx, eax; unsigned __int64
0x1800111f2  lea     rax, [rsp+290h+pBuffer]
0x1800111f7  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x1800111fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011200  lea     rdx, [rsp+290h+pBuffer]; pProfileName
0x180011205  xor     ecx, ecx; pMachineName
0x180011207  call    cs:__imp_InstallColorProfileW
0x18001120d  mov     ebx, eax
0x18001120f  test    eax, eax
0x180011211  jnz     short loc_180011256
0x180011213  call    cs:__imp_GetLastError
0x180011219  test    eax, eax
0x18001121b  jg      short loc_180011221
0x18001121d  mov     ecx, eax
0x18001121f  jmp     short loc_18001122A
0x180011221  movzx   ecx, ax
0x180011224  or      ecx, 80070000h
0x18001122a  mov     [rsp+290h+var_260], ecx; unsigned int
0x18001122e  lea     r9, [rsp+290h+pBuffer]; unsigned __int16 *
0x180011233  mov     [rsp+290h+var_268], eax; unsigned int
0x180011237  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18001123e  lea     r8, aInstallcolorpr; "InstallColorProfile failed"
0x180011245  mov     [rsp+290h+var_270], r15; unsigned __int16 *
0x18001124a  lea     rdx, aPsetupinstalli_1; "PSetupInstallICMProfiles"
0x180011251  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180011256  mov     rax, r12
0x180011259  inc     rax
0x18001125c  cmp     [rsi+rax*2], r15w
0x180011261  jnz     short loc_180011259
0x180011263  lea     rsi, [rsi+rax*2]
0x180011267  add     rsi, 2
0x18001126b  test    ebx, ebx
0x18001126d  jz      loc_18001130C
0x180011273  mov     edx, [rsp+290h+pdwSize]
0x180011277  jmp     loc_1800111BB
0x18001127c  mov     ebx, 8
0x180011281  mov     [rsp+290h+var_248], r15
0x180011286  mov     ecx, ebx; dwErrCode
0x180011288  call    cs:__imp_SetLastError
0x18001128e  lea     rdx, [rsp+290h+var_248]; unsigned __int16 **
0x180011293  mov     rcx, r14; unsigned __int16 *
0x180011296  call    ?ConvertMultiToSingleSz@@YAJPEBGPEAPEAG@Z; ConvertMultiToSingleSz(ushort const *,ushort * *)
0x18001129b  mov     [rsp+290h+var_260], 8007000Eh; unsigned int
0x1800112a3  lea     r8, aNotEnoughMemor_3; "Not enough memory"
0x1800112aa  mov     [rsp+290h+var_268], ebx; unsigned int
0x1800112ae  lea     rdx, aPsetupinstalli_1; "PSetupInstallICMProfiles"
0x1800112b5  mov     rbx, [rsp+290h+var_248]
0x1800112ba  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800112c1  mov     r9, rbx; unsigned __int16 *
0x1800112c4  mov     [rsp+290h+var_270], r15; unsigned __int16 *
0x1800112c9  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800112ce  test    rbx, rbx
0x1800112d1  jz      loc_18001113F
0x1800112d7  mov     rcx, rbx; void *
0x1800112da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800112df  jmp     loc_18001113F
0x1800112e4  mov     [rsp+290h+var_260], r15d; unsigned int
0x1800112e9  lea     rdx, aPsetupinstalli_1; "PSetupInstallICMProfiles"
0x1800112f0  mov     [rsp+290h+var_268], r15d; unsigned int
0x1800112f5  lea     rcx, SETUP_PRINTER_OPERATION_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x1800112fc  mov     r9, rdi; unsigned __int16 *
0x1800112ff  mov     [rsp+290h+var_270], r15; unsigned __int16 *
0x180011304  mov     r8, r14; unsigned __int16 *
0x180011307  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001130c  mov     eax, ebx
0x18001130e  jmp     short loc_180011341
0x180011310  mov     [rsp+290h+var_260], r15d; unsigned int
0x180011315  lea     r8, aNoIcmFilesToBe; "No ICM files to be installed"
0x18001131c  mov     [rsp+290h+var_268], r15d; unsigned int
0x180011321  lea     rdx, aPsetupinstalli_1; "PSetupInstallICMProfiles"
0x180011328  mov     r9, rdi; unsigned __int16 *
0x18001132b  mov     [rsp+290h+var_270], r15; unsigned __int16 *
0x180011330  lea     rcx, SETUP_PRINTER_OPERATION_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x180011337  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001133c  mov     eax, 1
0x180011341  mov     rcx, [rbp+190h+var_30]
0x180011348  xor     rcx, rsp; StackCookie
0x18001134b  call    __security_check_cookie
0x180011350  lea     r11, [rsp+290h+var_20]
0x180011358  mov     rbx, [r11+40h]
0x18001135c  mov     rsi, [r11+48h]
0x180011360  mov     rsp, r11
0x180011363  pop     r15
0x180011365  pop     r14
0x180011367  pop     r12
0x180011369  pop     rdi
0x18001136a  pop     rbp
0x18001136b  retn
```
