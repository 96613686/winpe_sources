# _lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8_::operator()

- ea: `0x18009a740`
- end: `0x18009a9ff`
- name: `_lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8_::operator()`
- size: `703`
- prototype: `_DWORD *__fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18009a3d4`

## callees

- `0x18001f090`
- `0x180021250`
- `0x18003ea2c`
- `0x1800430b8`
- `0x1800547a4`
- `0x18008d5c0`
- `0x18009a740`
- `0x18009aa08`
- `0x18009afe0`
- `0x18009bb70`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a8be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a8be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a964`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a964`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009a9d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009a9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a994`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a7d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a926`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a7d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a926`
- `SPOOLSS!DllFreeSplStr` at `0x18009a9be`
- `SPOOLSS!DllFreeSplStr` at `0x18009a9c8`
- `SPOOLSS!DllFreeSplStr` at `0x18009a9be`
- `SPOOLSS!DllFreeSplStr` at `0x18009a9c8`
- `SPOOLSS!DllAllocSplMem` at `0x18009a84d`
- `SPOOLSS!DllAllocSplMem` at `0x18009a84d`

## string_xrefs

- `0x18009a791`: `CopyFiles is not allowed!`
- `0x18009a8db`: `CopyFiles specified module %ws for copy operations but only mscms.dll is allowed!`
- `0x18009a798`: `SplCopyFileEvent::<lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8>::operator ()`
- `0x18009a8e2`: `SplCopyFileEvent::<lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8>::operator ()`
- `0x18009a9a8`: `SplCopyFileEvent::<lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8>::operator ()`
- `0x18009a95a`: `SpoolerCopyFileEvent`
- `0x18009a99d`: `SpoolerCopyFileEvent %ws %ws with error code %d`
- `0x18009a8b4`: `mscms.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_DWORD *__fastcall lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8_::operator()(_QWORD **a1)
{
  struct _SPOOL **v1; // rax
  _WORD *v3; // rsi
  HMODULE v4; // r14
  struct _SPOOL *v5; // r12
  int CopyFilesPolicy; // r15d
  _QWORD **v7; // rbx
  int PrinterData; // eax
  _DWORD *result; // rax
  int v10; // eax
  HMODULE LibraryTheCopyFileModule; // rax
  FARPROC ProcAddress; // rax
  const char *v13; // r9
  __int64 v14; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned int v16; // [rsp+80h] [rbp+40h] BYREF
  int v17; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int16 *v18; // [rsp+90h] [rbp+50h] BYREF

  v1 = (struct _SPOOL **)*a1;
  v16 = 0;
  v17 = 0;
  v3 = 0;
  v4 = 0;
  v18 = 0;
  v5 = *v1;
  CopyFilesPolicy = GetCopyFilesPolicy();
  if ( CopyFilesPolicy )
  {
    v7 = a1 + 1;
    PrinterData = SplGetPrinterDataEx(**a1, *a1[1], (unsigned int)L"Module", (unsigned int)&v17, 0, 0, (char)&v16);
    if ( PrinterData == 2 )
    {
      result = a1[2];
      *result = 1;
      return result;
    }
    if ( !PrinterData )
    {
      v3 = (_WORD *)DllAllocSplMem(v16);
      if ( v3 )
      {
        if ( !(unsigned int)SplGetPrinterDataEx(
                              **a1,
                              **v7,
                              (unsigned int)L"Module",
                              (unsigned int)&v17,
                              (char)v3,
                              v16,
                              (char)&v16)
          && v17 == 1 )
        {
          if ( CopyFilesPolicy == 1 && (!*v3 || (unsigned int)_o__wcsicmp(v3, L"mscms.dll")) )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl'::`2'::impl) )
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "SplCopyFileEvent::<lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8>::operator ()",
                L"CopyFiles specified module %ws for copy operations but only mscms.dll is allowed!",
                v3);
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_4049b621959e327872b18248b38d24a4_Traceguids, v3);
            }
            SetLastError(0x4ECu);
          }
          else
          {
            v10 = CreateFullyQualifiedNameFromPSpool(v5, &v18);
            *(_DWORD *)a1[2] = v10;
            if ( v10 )
            {
              LibraryTheCopyFileModule = (HMODULE)SplLoadLibraryTheCopyFileModule(**a1, v3);
              v4 = LibraryTheCopyFileModule;
              if ( LibraryTheCopyFileModule )
              {
                ProcAddress = GetProcAddress(LibraryTheCopyFileModule, "SpoolerCopyFileEvent");
                if ( ProcAddress )
                  *(_DWORD *)a1[2] = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD))ProcAddress)(
                                       v18,
                                       **v7,
                                       *(unsigned int *)a1[3]);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl'::`2'::impl) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SplCopyFileEvent::<lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8>::operator ()",
        L"CopyFiles is not allowed!");
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_4049b621959e327872b18248b38d24a4_Traceguids);
    }
    SetLastError(0x4ECu);
    v7 = a1 + 1;
  }
  if ( !*(_DWORD *)a1[2] )
  {
    LODWORD(v14) = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplCopyFileEvent::<lambda_fbcc33b90cc6c8610804c3a1cb3e1cd8>::operator ()",
      L"SpoolerCopyFileEvent %ws %ws with error code %d",
      v18,
      **v7,
      v14);
  }
  DllFreeSplStr(v3);
  DllFreeSplStr(v18);
  if ( v4 )
    FreeLibrary(v4);
  result = a1[2];
  if ( !*result )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x45A,
      (unsigned int)"printscan\\print\\spooler\\localspl\\files.c",
      v13);
  return result;
}

```

## disassembly

```asm
0x18009a740  mov     [rsp-38h+arg_18], rbx
0x18009a745  push    rbp
0x18009a746  push    rsi
0x18009a747  push    rdi
0x18009a748  push    r12
0x18009a74a  push    r13
0x18009a74c  push    r14
0x18009a74e  push    r15
0x18009a750  mov     rbp, rsp
0x18009a753  sub     rsp, 40h
0x18009a757  mov     rax, [rcx]
0x18009a75a  xor     r13d, r13d
0x18009a75d  mov     [rbp+arg_0], r13d
0x18009a761  mov     rdi, rcx
0x18009a764  mov     [rbp+arg_8], r13d
0x18009a768  mov     esi, r13d
0x18009a76b  mov     r14d, r13d
0x18009a76e  mov     [rbp+arg_10], r13
0x18009a772  mov     r12, [rax]
0x18009a775  call    ?GetCopyFilesPolicy@@YA?AW4ECopyFilesPolicy@@XZ; GetCopyFilesPolicy(void)
0x18009a77a  mov     r15d, eax
0x18009a77d  test    eax, eax
0x18009a77f  jnz     short loc_18009A7E8
0x18009a781  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl(void)'::`2'::impl
0x18009a788  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(void)
0x18009a78d  test    al, al
0x18009a78f  jz      short loc_18009A7A6
0x18009a791  lea     rdx, aCopyfilesIsNot_0; "CopyFiles is not allowed!"
0x18009a798  lea     rcx, aSplcopyfileeve_0; "SplCopyFileEvent::<lambda_fbcc33b90cc6c"...
0x18009a79f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a7a4  jmp     short loc_18009A7D4
0x18009a7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a7ad  lea     rax, WPP_GLOBAL_Control
0x18009a7b4  cmp     rcx, rax
0x18009a7b7  jz      short loc_18009A7D4
0x18009a7b9  test    byte ptr [rcx+44h], 10h
0x18009a7bd  jz      short loc_18009A7D4
0x18009a7bf  mov     rcx, [rcx+38h]
0x18009a7c3  lea     r8, WPP_4049b621959e327872b18248b38d24a4_Traceguids
0x18009a7ca  mov     edx, 0Bh
0x18009a7cf  call    WPP_SF_
0x18009a7d4  mov     ecx, 4ECh; dwErrCode
0x18009a7d9  call    cs:__imp_SetLastError
0x18009a7df  lea     rbx, [rdi+8]
0x18009a7e3  jmp     loc_18009A98B
0x18009a7e8  mov     rcx, [rdi]
0x18009a7eb  lea     rax, [rbp+arg_0]
0x18009a7ef  mov     [rsp+40h+var_10], rax
0x18009a7f4  lea     rbx, [rdi+8]
0x18009a7f8  mov     rdx, [rbx]
0x18009a7fb  lea     r9, [rbp+arg_8]
0x18009a7ff  mov     [rsp+40h+var_18], r13d
0x18009a804  lea     r8, aModule; "Module"
0x18009a80b  mov     rcx, [rcx]
0x18009a80e  mov     [rsp+40h+var_20], r13
0x18009a813  mov     rdx, [rdx]
0x18009a816  call    SplGetPrinterDataEx
0x18009a81b  cmp     eax, 2
0x18009a81e  jnz     short loc_18009A842
0x18009a820  mov     rax, [rdi+10h]
0x18009a824  mov     dword ptr [rax], 1
0x18009a82a  mov     rbx, [rsp+40h+arg_18]
0x18009a832  add     rsp, 40h
0x18009a836  pop     r15
0x18009a838  pop     r14
0x18009a83a  pop     r13
0x18009a83c  pop     r12
0x18009a83e  pop     rdi
0x18009a83f  pop     rsi
0x18009a840  pop     rbp
0x18009a841  retn
0x18009a842  test    eax, eax
0x18009a844  jnz     loc_18009A98B
0x18009a84a  mov     ecx, [rbp+arg_0]
0x18009a84d  call    cs:__imp_DllAllocSplMem
0x18009a853  mov     rsi, rax
0x18009a856  test    rax, rax
0x18009a859  jz      loc_18009A98B
0x18009a85f  mov     r9d, [rbp+arg_0]
0x18009a863  lea     rax, [rbp+arg_0]
0x18009a867  mov     rdx, [rbx]
0x18009a86a  lea     r8, aModule; "Module"
0x18009a871  mov     rcx, [rdi]
0x18009a874  mov     [rsp+40h+var_10], rax
0x18009a879  mov     [rsp+40h+var_18], r9d
0x18009a87e  lea     r9, [rbp+arg_8]
0x18009a882  mov     rdx, [rdx]
0x18009a885  mov     rcx, [rcx]
0x18009a888  mov     [rsp+40h+var_20], rsi
0x18009a88d  call    SplGetPrinterDataEx
0x18009a892  test    eax, eax
0x18009a894  jnz     loc_18009A98B
0x18009a89a  cmp     [rbp+arg_8], 1
0x18009a89e  jnz     loc_18009A98B
0x18009a8a4  cmp     r15d, 1
0x18009a8a8  jnz     loc_18009A92E
0x18009a8ae  cmp     [rsi], r13w
0x18009a8b2  jz      short loc_18009A8C8
0x18009a8b4  lea     rdx, aMscmsDll_0; "mscms.dll"
0x18009a8bb  mov     rcx, rsi
0x18009a8be  call    cs:__imp__o__wcsicmp
0x18009a8c4  test    eax, eax
0x18009a8c6  jz      short loc_18009A92E
0x18009a8c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl(void)'::`2'::impl
0x18009a8cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(void)
0x18009a8d4  test    al, al
0x18009a8d6  jz      short loc_18009A8F0
0x18009a8d8  mov     r8, rsi
0x18009a8db  lea     rdx, aCopyfilesSpeci_1; "CopyFiles specified module %ws for copy"...
0x18009a8e2  lea     rcx, aSplcopyfileeve_0; "SplCopyFileEvent::<lambda_fbcc33b90cc6c"...
0x18009a8e9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a8ee  jmp     short loc_18009A921
0x18009a8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a8f7  lea     rax, WPP_GLOBAL_Control
0x18009a8fe  cmp     rcx, rax
0x18009a901  jz      short loc_18009A921
0x18009a903  test    byte ptr [rcx+44h], 10h
0x18009a907  jz      short loc_18009A921
0x18009a909  mov     rcx, [rcx+38h]
0x18009a90d  lea     r8, WPP_4049b621959e327872b18248b38d24a4_Traceguids
0x18009a914  mov     edx, 0Ch
0x18009a919  mov     r9, rsi
0x18009a91c  call    WPP_SF_S
0x18009a921  mov     ecx, 4ECh; dwErrCode
0x18009a926  call    cs:__imp_SetLastError
0x18009a92c  jmp     short loc_18009A98B
0x18009a92e  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18009a932  mov     rcx, r12; struct _SPOOL *
0x18009a935  call    ?CreateFullyQualifiedNameFromPSpool@@YAHPEAU_SPOOL@@PEAPEAG@Z; CreateFullyQualifiedNameFromPSpool(_SPOOL *,ushort * *)
0x18009a93a  mov     rcx, [rdi+10h]
0x18009a93e  mov     [rcx], eax
0x18009a940  test    eax, eax
0x18009a942  jz      short loc_18009A98B
0x18009a944  mov     rcx, [rdi]
0x18009a947  mov     rdx, rsi
0x18009a94a  mov     rcx, [rcx]
0x18009a94d  call    SplLoadLibraryTheCopyFileModule
0x18009a952  mov     r14, rax
0x18009a955  test    rax, rax
0x18009a958  jz      short loc_18009A98B
0x18009a95a  lea     rdx, aSpoolercopyfil; "SpoolerCopyFileEvent"
0x18009a961  mov     rcx, rax; hModule
0x18009a964  call    cs:__imp_GetProcAddress
0x18009a96a  test    rax, rax
0x18009a96d  jz      short loc_18009A98B
0x18009a96f  mov     r8, [rdi+18h]
0x18009a973  mov     rdx, [rbx]
0x18009a976  mov     rcx, [rbp+arg_10]
0x18009a97a  mov     r8d, [r8]
0x18009a97d  mov     rdx, [rdx]
0x18009a980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a985  mov     rcx, [rdi+10h]
0x18009a989  mov     [rcx], eax
0x18009a98b  mov     rax, [rdi+10h]
0x18009a98f  cmp     [rax], r13d
0x18009a992  jnz     short loc_18009A9BB
0x18009a994  call    cs:__imp_GetLastError
0x18009a99a  mov     r9, [rbx]
0x18009a99d  lea     rdx, aSpoolercopyfil_0; "SpoolerCopyFileEvent %ws %ws with error"...
0x18009a9a4  mov     r8, [rbp+arg_10]
0x18009a9a8  lea     rcx, aSplcopyfileeve_0; "SplCopyFileEvent::<lambda_fbcc33b90cc6c"...
0x18009a9af  mov     dword ptr [rsp+40h+var_20], eax
0x18009a9b3  mov     r9, [r9]
0x18009a9b6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a9bb  mov     rcx, rsi
0x18009a9be  call    cs:__imp_DllFreeSplStr
0x18009a9c4  mov     rcx, [rbp+arg_10]
0x18009a9c8  call    cs:__imp_DllFreeSplStr
0x18009a9ce  test    r14, r14
0x18009a9d1  jz      short loc_18009A9DC
0x18009a9d3  mov     rcx, r14; hLibModule
0x18009a9d6  call    cs:__imp_FreeLibrary
0x18009a9dc  mov     rax, [rdi+10h]
0x18009a9e0  cmp     [rax], r13d
0x18009a9e3  jnz     loc_18009A82A
0x18009a9e9  mov     rcx, [rbp+38h]; this
0x18009a9ed  lea     r8, aPrintscanPrint_20; "printscan\\print\\spooler\\localspl\\fi"...
0x18009a9f4  mov     edx, 45Ah; void *
0x18009a9f9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
