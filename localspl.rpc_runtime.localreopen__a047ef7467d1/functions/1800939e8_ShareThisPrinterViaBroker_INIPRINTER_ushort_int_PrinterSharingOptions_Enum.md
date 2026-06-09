# ShareThisPrinterViaBroker(_INIPRINTER *,ushort *,int,PrinterSharingOptions::Enum)

- ea: `0x1800939e8`
- end: `0x180093f3e`
- name: `?ShareThisPrinterViaBroker@@YAHPEAU_INIPRINTER@@PEAGHW4Enum@PrinterSharingOptions@@@Z`
- size: `1366`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800934d8`

## callees

- `0x1800051f0`
- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180011f00`
- `0x18001fb10`
- `0x18003b010`
- `0x18003ea2c`
- `0x180041188`
- `0x180046650`
- `0x180047330`
- `0x18004a2f0`
- `0x18005470c`
- `0x180093008`
- `0x1800939e8`
- `0x180099ab8`
- `0x18009c908`
- `0x1800c7370`
- `0x1800c7f94`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093f09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093aaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093d1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093e6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093ea0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093aaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093d1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093e6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093dc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093dc0`
- `SPOOLSS!AllowRemoteCalls` at `0x180093c67`
- `SPOOLSS!AllowRemoteCalls` at `0x180093c9b`
- `SPOOLSS!AllowRemoteCalls` at `0x180093c67`
- `SPOOLSS!AllowRemoteCalls` at `0x180093c9b`
- `SPOOLSS!DllFreeSplStr` at `0x180093e86`
- `SPOOLSS!DllFreeSplStr` at `0x180093e8f`
- `SPOOLSS!DllFreeSplStr` at `0x180093e98`
- `SPOOLSS!DllFreeSplStr` at `0x180093e86`
- `SPOOLSS!DllFreeSplStr` at `0x180093e8f`
- `SPOOLSS!DllFreeSplStr` at `0x180093e98`
- `SPOOLSS!RevertToPrinterSelf` at `0x180093bb7`
- `SPOOLSS!RevertToPrinterSelf` at `0x180093d84`
- `SPOOLSS!RevertToPrinterSelf` at `0x180093bb7`
- `SPOOLSS!RevertToPrinterSelf` at `0x180093d84`
- `SPOOLSS!AllocSplStr` at `0x180093b65`
- `SPOOLSS!AllocSplStr` at `0x180093b88`
- `SPOOLSS!AllocSplStr` at `0x180093d51`
- `SPOOLSS!AllocSplStr` at `0x180093b65`
- `SPOOLSS!AllocSplStr` at `0x180093b88`
- `SPOOLSS!AllocSplStr` at `0x180093d51`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093cde`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093ded`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093cde`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093ded`

## string_xrefs

- `0x180093edd`: `ImpersonatePrinterClient failed with error %d`
- `0x180093f12`: `ImpersonatePrinterClient failed with error %d`
- `0x180093a92`: `Access denied sharing printer because the user is not a full admin and the firewall file & print rule is disabled`
- `0x180093a99`: `ShareThisPrinterViaBroker`
- `0x180093d11`: `ShareThisPrinterViaBroker`
- `0x180093e60`: `ShareThisPrinterViaBroker`
- `0x180093ee4`: `ShareThisPrinterViaBroker`
- `0x180093f19`: `ShareThisPrinterViaBroker`

## pseudocode

```c
__int64 __fastcall ShareThisPrinterViaBroker(__int64 a1, const unsigned __int16 *a2, int a3, int a4)
{
  __int64 v4; // r13
  const unsigned __int16 *v10; // r8
  __int64 v11; // r12
  const unsigned __int16 *v12; // rsi
  int v13; // eax
  void *v14; // r14
  DWORD v15; // ebx
  _WORD *v16; // rcx
  _WORD *v17; // rcx
  unsigned int *v18; // rdi
  __int64 v19; // rcx
  HANDLE v20; // r13
  __int64 v21; // rdx
  int v22; // ecx
  unsigned __int16 v23; // ax
  unsigned __int16 v24; // ax
  struct SplLogType *v25; // rax
  __int64 v26; // r10
  _WORD *v27; // rcx
  unsigned int *v28; // rdi
  __int64 v29; // rcx
  HANDLE v30; // rbx
  unsigned __int16 v31; // r14
  struct SplLogType *v32; // rax
  __int64 v33; // r10
  DWORD LastError; // eax
  const char *v35; // r9
  DWORD v36; // eax
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  bool v39; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v40; // [rsp+34h] [rbp-CCh]
  unsigned __int16 *PrinterName; // [rsp+38h] [rbp-C8h]
  int v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+44h] [rbp-BCh]
  _BYTE v44[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v45[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v46[520]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v4 = *(_QWORD *)(a1 + 280);
  v43 = a3;
  memset_0(v46, 0, 0x40Eu);
  if ( a3 && !a4 )
  {
    v39 = 0;
    if ( !(unsigned int)IsFirewallPrintRuleEnabled(&v39) )
      return 0;
    if ( !v39 && !(unsigned int)ValidateObjectAccess(0, 1, 0, 0, *(_QWORD *)(a1 + 280), 0) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "ShareThisPrinterViaBroker",
        L"Access denied sharing printer because the user is not a full admin and the firewall file & print rule is disabled");
      SetLastError(5u);
      return 0;
    }
  }
  v10 = *(const unsigned __int16 **)(a1 + 24);
  v40 = 0;
  PrinterName = 0;
  v11 = 0;
  v12 = 0;
  v13 = StringCchCopyW(v46, 0x207u, v10);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AE,
      (unsigned int)"printscan\\print\\spooler\\localspl\\net.c",
      (const char *)(unsigned int)v13,
      v38);
  if ( !a3 )
  {
    v14 = 0;
    v27 = *(_WORD **)(*(_QWORD *)(v4 + 144) + 56LL);
    if ( !v27 || !*v27 || (v12 = (const unsigned __int16 *)AllocSplStr(v27)) != 0 )
    {
      v28 = (unsigned int *)(a1 + 16);
      if ( SafeIncrementReference((unsigned int *)(a1 + 16)) > *(_DWORD *)(a1 + 248) )
        *(_DWORD *)(a1 + 248) = *v28;
      LeaveSplSem(v29);
      v30 = RevertToPrinterSelf();
      if ( v30 )
      {
        v31 = BrokerPrinterShareOperation(2, (__int64)a2, 0, 0, (__int64)v12, 0);
        if ( !ImpersonatePrinterClient(v30) )
        {
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "ShareThisPrinterViaBroker",
            L"ImpersonatePrinterClient failed with error %d",
            LastError);
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x458,
            (unsigned int)"printscan\\print\\spooler\\localspl\\net.c",
            v35);
        }
        v15 = v31;
        if ( !v31 )
        {
          SplLogType::SplLogType((SplLogType *)v45, a2);
          v32 = SplLogType::SplLogType((SplLogType *)v44, v46);
          SplLogEvent2(&PRINTER_UNSHARE_SUCCEEDED, v32, v33, 0);
        }
        EnterSplSem(0);
        if ( *v28 )
          SafeDecrementReference(v28);
        if ( !v31 || v31 == 2310 )
        {
          v15 = 0;
        }
        else
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "ShareThisPrinterViaBroker",
            L"Removing the shared printer failed! Error %d",
            v31);
          SetLastError(v31);
          v40 = 1;
        }
        goto LABEL_64;
      }
      goto LABEL_51;
    }
LABEL_14:
    v15 = 8;
    goto LABEL_52;
  }
  v14 = MapPrinterSDToShareSD(*(void **)(a1 + 192));
  if ( v14 )
  {
    PrinterName = pszGetPrinterName(
                    (struct _INIPRINTER *)a1,
                    *(_QWORD *)(a1 + 280) != (_QWORD)pLocalIniSpooler,
                    L"LocalsplOnly");
    if ( PrinterName )
    {
      v16 = *(_WORD **)(a1 + 80);
      if ( !v16 || !*v16 )
        v16 = *(_WORD **)(a1 + 24);
      v11 = AllocSplStr(v16);
      if ( v11 )
      {
        v17 = *(_WORD **)(*(_QWORD *)(v4 + 144) + 56LL);
        if ( !v17 || !*v17 || (v12 = (const unsigned __int16 *)AllocSplStr(v17)) != 0 )
        {
          v18 = (unsigned int *)(a1 + 16);
          if ( SafeIncrementReference((unsigned int *)(a1 + 16)) > *(_DWORD *)(a1 + 248) )
            *(_DWORD *)(a1 + 248) = *v18;
          LeaveSplSem(v19);
          v20 = RevertToPrinterSelf();
          if ( v20 )
          {
            v15 = (unsigned __int16)BrokerPrinterShareOperation(
                                      0,
                                      (__int64)a2,
                                      (__int64)PrinterName,
                                      v11,
                                      (__int64)v12,
                                      v14);
            if ( v15 == 2118 )
            {
              v42 = 0;
              v15 = (unsigned __int16)IsSamePrinterShare(a2, PrinterName, v12, &v42);
              if ( v15 )
                goto LABEL_35;
              v21 = (__int64)a2;
              if ( v42 )
              {
                v22 = 1;
              }
              else
              {
                v23 = BrokerPrinterShareOperation(2, (__int64)a2, 0, 0, (__int64)v12, 0);
                v15 = v23;
                if ( v23 )
                  goto LABEL_35;
                v21 = (__int64)a2;
                v22 = 0;
              }
              v15 = (unsigned __int16)BrokerPrinterShareOperation(
                                        v22,
                                        v21,
                                        (__int64)PrinterName,
                                        v11,
                                        (__int64)v12,
                                        v14);
            }
            if ( !v15 )
            {
              v24 = AllowRemoteCalls();
              v15 = v24;
              if ( !v24 )
                goto LABEL_38;
              BrokerPrinterShareOperation(2, (__int64)a2, 0, 0, (__int64)v12, 0);
LABEL_37:
              if ( v15 )
              {
LABEL_39:
                if ( !ImpersonatePrinterClient(v20) )
                {
                  v36 = GetLastError();
                  LocalSpoolerTelemetry::WriteDbgTraceError(
                    "ShareThisPrinterViaBroker",
                    L"ImpersonatePrinterClient failed with error %d",
                    v36);
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x424,
                    (unsigned int)"printscan\\print\\spooler\\localspl\\net.c",
                    v37);
                }
                EnterSplSem(0);
                if ( *v18 )
                  SafeDecrementReference(v18);
                if ( !v15 )
                {
                  CreateServerThread();
                  v40 = 1;
LABEL_54:
                  LocalFree(v14);
                  goto LABEL_64;
                }
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "ShareThisPrinterViaBroker",
                  L"Sharing the printer failed! Error %d",
                  v15);
                SetLastError(v15);
                goto LABEL_52;
              }
LABEL_38:
              SplLogType::SplLogType((SplLogType *)v44, a2);
              v25 = SplLogType::SplLogType((SplLogType *)v45, v46);
              SplLogEvent2(&PRINTER_SHARE_SUCCEEDED, v25, v26, 0);
              goto LABEL_39;
            }
LABEL_35:
            if ( v15 == 2114 )
              v15 = (unsigned __int16)AllowRemoteCalls();
            goto LABEL_37;
          }
LABEL_51:
          v15 = GetLastError();
          if ( !v15 )
            goto LABEL_53;
          goto LABEL_52;
        }
      }
    }
    goto LABEL_14;
  }
  v15 = 1338;
LABEL_52:
  LogShareActionError(v15, v46, a2, v43);
LABEL_53:
  if ( v14 )
    goto LABEL_54;
LABEL_64:
  DllFreeSplStr(PrinterName);
  DllFreeSplStr(v11);
  DllFreeSplStr(v12);
  SetLastError(v15);
  return v40;
}

```

## disassembly

```asm
0x1800939e8  mov     [rsp-8+arg_18], rbx
0x1800939ed  push    rbp
0x1800939ee  push    rsi
0x1800939ef  push    rdi
0x1800939f0  push    r12
0x1800939f2  push    r13
0x1800939f4  push    r14
0x1800939f6  push    r15
0x1800939f8  lea     rbp, [rsp-3A0h]
0x180093a00  sub     rsp, 4A0h
0x180093a07  mov     rax, cs:__security_cookie
0x180093a0e  xor     rax, rsp
0x180093a11  mov     [rbp+3D0h+var_40], rax
0x180093a18  mov     r13, [rcx+118h]
0x180093a1f  mov     r14d, r8d
0x180093a22  mov     [rsp+4D0h+var_48C], r8d
0x180093a27  mov     r15, rdx
0x180093a2a  mov     rbx, rcx
0x180093a2d  xor     edx, edx; Val
0x180093a2f  mov     r8d, 40Eh; Size
0x180093a35  lea     rcx, [rbp+3D0h+var_450]; void *
0x180093a39  mov     edi, r9d
0x180093a3c  call    memset_0
0x180093a41  test    r14d, r14d
0x180093a44  jz      short loc_180093AB2
0x180093a46  test    edi, edi
0x180093a48  jnz     short loc_180093AB2
0x180093a4a  xor     edi, edi
0x180093a4c  lea     rcx, [rsp+4D0h+var_4A0]; bool *
0x180093a51  mov     [rsp+4D0h+var_4A0], dil
0x180093a56  call    ?IsFirewallPrintRuleEnabled@@YAHPEA_N@Z; IsFirewallPrintRuleEnabled(bool *)
0x180093a5b  test    eax, eax
0x180093a5d  jnz     short loc_180093A66
0x180093a5f  xor     eax, eax
0x180093a61  jmp     loc_180093EAA
0x180093a66  cmp     [rsp+4D0h+var_4A0], dil
0x180093a6b  jnz     short loc_180093AB4
0x180093a6d  mov     rax, [rbx+118h]
0x180093a74  xor     r9d, r9d
0x180093a77  mov     dword ptr [rsp+4D0h+var_4A8], edi
0x180093a7b  xor     r8d, r8d
0x180093a7e  xor     ecx, ecx
0x180093a80  mov     [rsp+4D0h+var_4B0], rax
0x180093a85  lea     edx, [r9+1]
0x180093a89  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180093a8e  test    eax, eax
0x180093a90  jnz     short loc_180093AB4
0x180093a92  lea     rdx, aAccessDeniedSh; "Access denied sharing printer because t"...
0x180093a99  lea     rcx, aSharethisprint_1; "ShareThisPrinterViaBroker"
0x180093aa0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180093aa5  mov     ecx, 5; dwErrCode
0x180093aaa  call    cs:__imp_SetLastError
0x180093ab0  jmp     short loc_180093A5F
0x180093ab2  xor     edi, edi
0x180093ab4  mov     r8, [rbx+18h]; unsigned __int16 *
0x180093ab8  lea     rcx, [rbp+3D0h+var_450]; unsigned __int16 *
0x180093abc  mov     edx, 207h; unsigned __int64
0x180093ac1  mov     [rsp+4D0h+var_49C], edi
0x180093ac5  mov     [rsp+4D0h+var_498], rdi
0x180093aca  mov     r12, rdi
0x180093acd  mov     rsi, rdi
0x180093ad0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093ad5  test    eax, eax
0x180093ad7  jns     short loc_180093AF4
0x180093ad9  mov     rcx, [rbp+3D8h]; this
0x180093ae0  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\localspl\\ne"...
0x180093ae7  mov     r9d, eax; char *
0x180093aea  mov     edx, 3AEh; void *
0x180093aef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093af4  test    r14d, r14d
0x180093af7  jz      loc_180093D39
0x180093afd  mov     rcx, [rbx+0C0h]; void *
0x180093b04  call    MapPrinterSDToShareSD
0x180093b09  mov     r14, rax
0x180093b0c  test    rax, rax
0x180093b0f  jnz     short loc_180093B1B
0x180093b11  mov     ebx, 53Ah
0x180093b16  jmp     loc_180093DA1
0x180093b1b  mov     rax, cs:pLocalIniSpooler
0x180093b22  lea     r8, aLocalsplonly; "LocalsplOnly"
0x180093b29  cmp     [rbx+118h], rax
0x180093b30  mov     edx, edi
0x180093b32  mov     rcx, rbx; struct _INIPRINTER *
0x180093b35  setnz   dl; int
0x180093b38  call    ?pszGetPrinterName@@YAPEAGPEAU_INIPRINTER@@HPEBG@Z; pszGetPrinterName(_INIPRINTER *,int,ushort const *)
0x180093b3d  mov     [rsp+4D0h+var_498], rax
0x180093b42  test    rax, rax
0x180093b45  jnz     short loc_180093B51
0x180093b47  mov     ebx, 8
0x180093b4c  jmp     loc_180093DA1
0x180093b51  mov     rcx, [rbx+50h]
0x180093b55  xor     edi, edi
0x180093b57  test    rcx, rcx
0x180093b5a  jz      short loc_180093B61
0x180093b5c  cmp     [rcx], di
0x180093b5f  jnz     short loc_180093B65
0x180093b61  mov     rcx, [rbx+18h]
0x180093b65  call    cs:__imp_AllocSplStr
0x180093b6b  mov     r12, rax
0x180093b6e  test    rax, rax
0x180093b71  jz      short loc_180093B47
0x180093b73  mov     rax, [r13+90h]
0x180093b7a  mov     rcx, [rax+38h]
0x180093b7e  test    rcx, rcx
0x180093b81  jz      short loc_180093B96
0x180093b83  cmp     [rcx], di
0x180093b86  jz      short loc_180093B96
0x180093b88  call    cs:__imp_AllocSplStr
0x180093b8e  mov     rsi, rax
0x180093b91  test    rax, rax
0x180093b94  jz      short loc_180093B47
0x180093b96  lea     rdi, [rbx+10h]
0x180093b9a  mov     rcx, rdi; unsigned int *
0x180093b9d  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180093ba2  cmp     eax, [rbx+0F8h]
0x180093ba8  jbe     short loc_180093BB2
0x180093baa  mov     eax, [rdi]
0x180093bac  mov     [rbx+0F8h], eax
0x180093bb2  call    LeaveSplSem
0x180093bb7  call    cs:__imp_RevertToPrinterSelf
0x180093bbd  mov     r13, rax
0x180093bc0  test    rax, rax
0x180093bc3  jz      loc_180093D95
0x180093bc9  mov     r8, [rsp+4D0h+var_498]
0x180093bce  mov     r9, r12
0x180093bd1  mov     [rsp+4D0h+var_4A8], r14
0x180093bd6  mov     rdx, r15
0x180093bd9  xor     ecx, ecx
0x180093bdb  mov     [rsp+4D0h+var_4B0], rsi
0x180093be0  call    ?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z; BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)
0x180093be5  movzx   ebx, ax
0x180093be8  cmp     ebx, 846h
0x180093bee  jnz     short loc_180093C63
0x180093bf0  mov     rdx, [rsp+4D0h+var_498]; unsigned __int16 *
0x180093bf5  lea     r9, [rsp+4D0h+var_490]; int *
0x180093bfa  mov     r8, rsi; unsigned __int16 *
0x180093bfd  mov     [rsp+4D0h+var_490], 0
0x180093c05  mov     rcx, r15; unsigned __int16 *
0x180093c08  call    ?IsSamePrinterShare@@YAJPEBG00PEAH@Z; IsSamePrinterShare(ushort const *,ushort const *,ushort const *,int *)
0x180093c0d  movzx   ebx, ax
0x180093c10  xor     eax, eax
0x180093c12  test    ebx, ebx
0x180093c14  jnz     short loc_180093C93
0x180093c16  mov     rdx, r15
0x180093c19  cmp     [rsp+4D0h+var_490], eax
0x180093c1d  jz      short loc_180093C24
0x180093c1f  lea     ecx, [rax+1]
0x180093c22  jmp     short loc_180093C49
0x180093c24  xor     r9d, r9d
0x180093c27  mov     [rsp+4D0h+var_4A8], rax
0x180093c2c  xor     r8d, r8d
0x180093c2f  mov     [rsp+4D0h+var_4B0], rsi
0x180093c34  lea     ecx, [r9+2]
0x180093c38  call    ?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z; BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)
0x180093c3d  movzx   ebx, ax
0x180093c40  test    ebx, ebx
0x180093c42  jnz     short loc_180093C93
0x180093c44  mov     rdx, r15
0x180093c47  xor     ecx, ecx
0x180093c49  mov     r8, [rsp+4D0h+var_498]
0x180093c4e  mov     r9, r12
0x180093c51  mov     [rsp+4D0h+var_4A8], r14
0x180093c56  mov     [rsp+4D0h+var_4B0], rsi
0x180093c5b  call    ?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z; BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)
0x180093c60  movzx   ebx, ax
0x180093c63  test    ebx, ebx
0x180093c65  jnz     short loc_180093C93
0x180093c67  call    cs:__imp_AllowRemoteCalls
0x180093c6d  movzx   ebx, ax
0x180093c70  xor     eax, eax
0x180093c72  test    ebx, ebx
0x180093c74  jz      short loc_180093CA8
0x180093c76  mov     [rsp+4D0h+var_4A8], rax
0x180093c7b  lea     ecx, [rax+2]
0x180093c7e  xor     r9d, r9d
0x180093c81  mov     [rsp+4D0h+var_4B0], rsi
0x180093c86  xor     r8d, r8d
0x180093c89  mov     rdx, r15
0x180093c8c  call    ?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z; BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)
0x180093c91  jmp     short loc_180093CA4
0x180093c93  cmp     ebx, 842h
0x180093c99  jnz     short loc_180093CA4
0x180093c9b  call    cs:__imp_AllowRemoteCalls
0x180093ca1  movzx   ebx, ax
0x180093ca4  test    ebx, ebx
0x180093ca6  jnz     short loc_180093CDB
0x180093ca8  mov     rdx, r15; unsigned __int16 *
0x180093cab  lea     rcx, [rsp+4D0h+var_488]; this
0x180093cb0  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180093cb5  lea     rdx, [rbp+3D0h+var_450]; unsigned __int16 *
0x180093cb9  mov     r10, rax
0x180093cbc  lea     rcx, [rsp+4D0h+var_470]; this
0x180093cc1  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180093cc6  xor     r9d, r9d
0x180093cc9  lea     rcx, PRINTER_SHARE_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x180093cd0  mov     r8, r10
0x180093cd3  mov     rdx, rax; struct SplLogType *
0x180093cd6  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180093cdb  mov     rcx, r13; hToken
0x180093cde  call    cs:__imp_ImpersonatePrinterClient
0x180093ce4  xor     r13d, r13d
0x180093ce7  test    eax, eax
0x180093ce9  jz      loc_180093F09
0x180093cef  xor     ecx, ecx
0x180093cf1  call    EnterSplSem
0x180093cf6  cmp     [rdi], r13d
0x180093cf9  jz      short loc_180093D03
0x180093cfb  mov     rcx, rdi; unsigned int *
0x180093cfe  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180093d03  test    ebx, ebx
0x180093d05  jz      short loc_180093D27
0x180093d07  mov     r8d, ebx
0x180093d0a  lea     rdx, aSharingThePrin; "Sharing the printer failed! Error %d"
0x180093d11  lea     rcx, aSharethisprint_1; "ShareThisPrinterViaBroker"
0x180093d18  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180093d1d  mov     ecx, ebx; dwErrCode
0x180093d1f  call    cs:__imp_SetLastError
0x180093d25  jmp     short loc_180093DA1
0x180093d27  call    CreateServerThread
0x180093d2c  mov     [rsp+4D0h+var_49C], 1
0x180093d34  jmp     loc_180093DBD
0x180093d39  mov     rax, [r13+90h]
0x180093d40  mov     r14, rdi
0x180093d43  mov     rcx, [rax+38h]
0x180093d47  test    rcx, rcx
0x180093d4a  jz      short loc_180093D63
0x180093d4c  cmp     [rcx], di
0x180093d4f  jz      short loc_180093D63
0x180093d51  call    cs:__imp_AllocSplStr
0x180093d57  mov     rsi, rax
0x180093d5a  test    rax, rax
0x180093d5d  jz      loc_180093B47
0x180093d63  lea     rdi, [rbx+10h]
0x180093d67  mov     rcx, rdi; unsigned int *
0x180093d6a  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180093d6f  cmp     eax, [rbx+0F8h]
0x180093d75  jbe     short loc_180093D7F
0x180093d77  mov     eax, [rdi]
0x180093d79  mov     [rbx+0F8h], eax
0x180093d7f  call    LeaveSplSem
0x180093d84  call    cs:__imp_RevertToPrinterSelf
0x180093d8a  xor     r13d, r13d
0x180093d8d  mov     rbx, rax
0x180093d90  test    rax, rax
0x180093d93  jnz     short loc_180093DCB
0x180093d95  call    cs:__imp_GetLastError
0x180093d9b  mov     ebx, eax
0x180093d9d  test    eax, eax
0x180093d9f  jz      short loc_180093DB4
0x180093da1  mov     r9d, [rsp+4D0h+var_48C]; int
0x180093da6  lea     rdx, [rbp+3D0h+var_450]; unsigned __int16 *
0x180093daa  mov     r8, r15; unsigned __int16 *
0x180093dad  mov     ecx, ebx; unsigned int
0x180093daf  call    ?LogShareActionError@@YAXKPEBG0H@Z; LogShareActionError(ulong,ushort const *,ushort const *,int)
0x180093db4  test    r14, r14
0x180093db7  jz      loc_180093E81
0x180093dbd  mov     rcx, r14; hMem
0x180093dc0  call    cs:__imp_LocalFree
0x180093dc6  jmp     loc_180093E81
0x180093dcb  xor     r9d, r9d
0x180093dce  mov     [rsp+4D0h+var_4A8], r13
0x180093dd3  xor     r8d, r8d
0x180093dd6  mov     [rsp+4D0h+var_4B0], rsi
0x180093ddb  mov     rdx, r15
0x180093dde  lea     ecx, [r9+2]
0x180093de2  call    ?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z; BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)
0x180093de7  mov     rcx, rbx; hToken
0x180093dea  mov     r14d, eax
0x180093ded  call    cs:__imp_ImpersonatePrinterClient
0x180093df3  test    eax, eax
0x180093df5  jz      loc_180093ED4
0x180093dfb  movzx   ebx, r14w
0x180093dff  test    ebx, ebx
0x180093e01  jnz     short loc_180093E36
0x180093e03  mov     rdx, r15; unsigned __int16 *
0x180093e06  lea     rcx, [rsp+4D0h+var_470]; this
0x180093e0b  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180093e10  lea     rdx, [rbp+3D0h+var_450]; unsigned __int16 *
0x180093e14  mov     r10, rax
0x180093e17  lea     rcx, [rsp+4D0h+var_488]; this
0x180093e1c  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180093e21  xor     r9d, r9d
0x180093e24  lea     rcx, PRINTER_UNSHARE_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x180093e2b  mov     r8, r10
0x180093e2e  mov     rdx, rax; struct SplLogType *
0x180093e31  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180093e36  xor     ecx, ecx
0x180093e38  call    EnterSplSem
0x180093e3d  cmp     [rdi], r13d
0x180093e40  jz      short loc_180093E4A
0x180093e42  mov     rcx, rdi; unsigned int *
0x180093e45  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180093e4a  test    ebx, ebx
0x180093e4c  jz      short loc_180093E7E
0x180093e4e  cmp     ebx, 906h
0x180093e54  jz      short loc_180093E7E
0x180093e56  mov     r8d, ebx
0x180093e59  lea     rdx, aRemovingTheSha; "Removing the shared printer failed! Err"...
0x180093e60  lea     rcx, aSharethisprint_1; "ShareThisPrinterViaBroker"
0x180093e67  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
  ... truncated ...
```
