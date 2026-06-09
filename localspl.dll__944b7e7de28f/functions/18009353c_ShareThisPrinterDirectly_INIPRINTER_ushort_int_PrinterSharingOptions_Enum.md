# ShareThisPrinterDirectly(_INIPRINTER *,ushort *,int,PrinterSharingOptions::Enum)

- ea: `0x18009353c`
- end: `0x1800939df`
- name: `?ShareThisPrinterDirectly@@YAHPEAU_INIPRINTER@@PEAGHW4Enum@PrinterSharingOptions@@@Z`
- size: `1187`
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
- `0x180032f28`
- `0x18003b010`
- `0x18003ea2c`
- `0x180041188`
- `0x180046650`
- `0x180047330`
- `0x180092ce4`
- `0x180092e64`
- `0x180093008`
- `0x18009353c`
- `0x180093f44`
- `0x180099ab8`
- `0x18009c908`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800938b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800938b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093906`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800935e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009384a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009397b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800939ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800935e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180093676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009384a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009397b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800939ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093876`
- `SPOOLSS!AllowRemoteCalls` at `0x1800937cd`
- `SPOOLSS!AllowRemoteCalls` at `0x1800937cd`
- `SPOOLSS!DllFreeSplStr` at `0x180093990`
- `SPOOLSS!DllFreeSplStr` at `0x180093999`
- `SPOOLSS!DllFreeSplStr` at `0x1800939a4`
- `SPOOLSS!DllFreeSplStr` at `0x180093990`
- `SPOOLSS!DllFreeSplStr` at `0x180093999`
- `SPOOLSS!DllFreeSplStr` at `0x1800939a4`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009372e`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800938a2`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009372e`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800938a2`
- `SPOOLSS!AllocSplStr` at `0x180093640`
- `SPOOLSS!AllocSplStr` at `0x180093698`
- `SPOOLSS!AllocSplStr` at `0x180093640`
- `SPOOLSS!AllocSplStr` at `0x180093698`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093763`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009382a`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800938f8`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093763`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009382a`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800938f8`
- `srvcli!NetShareDel` at `0x1800937e9`
- `srvcli!NetShareDel` at `0x1800938d1`
- `srvcli!NetShareDel` at `0x1800937e9`
- `srvcli!NetShareDel` at `0x1800938d1`

## string_xrefs

- `0x1800935ce`: `Access denied sharing printer because the user is not a full admin and the firewall file & print rule is disabled`

## pseudocode

```c
__int64 __fastcall ShareThisPrinterDirectly(__int64 a1, __int64 a2, int a3, int a4)
{
  struct _INISPOOLER *v8; // r14
  unsigned int LastError; // ebx
  unsigned int v10; // r12d
  WCHAR *v11; // r15
  void *v12; // r13
  _WORD *v13; // rcx
  WCHAR *v14; // rax
  WCHAR *PrinterName; // rax
  unsigned int *v16; // rsi
  __int64 v17; // rcx
  HANDLE v18; // r12
  unsigned int v19; // eax
  int v20; // eax
  unsigned __int16 v21; // di
  struct SplLogType *v22; // rax
  __int64 v23; // r10
  unsigned int *v24; // rsi
  __int64 v25; // rcx
  HANDLE v26; // rdi
  struct SplLogType *v27; // rax
  __int64 v28; // r10
  bool v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  int v31; // [rsp+38h] [rbp-C8h]
  WCHAR *v32; // [rsp+40h] [rbp-C0h]
  WCHAR *v33; // [rsp+48h] [rbp-B8h]
  struct _SHARE_INFO_503 netname; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[24]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v37[520]; // [rsp+D0h] [rbp-30h] BYREF

  v31 = a3;
  if ( a3 && !a4 )
  {
    v29 = 0;
    if ( !(unsigned int)IsFirewallPrintRuleEnabled(&v29) )
      return 0;
    if ( !v29 && !(unsigned int)ValidateObjectAccess(0, 1, 0, 0, *(_QWORD *)(a1 + 280), 0) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "ShareThisPrinterDirectly",
        L"Access denied sharing printer because the user is not a full admin and the firewall file & print rule is disabled");
      SetLastError(5u);
      return 0;
    }
  }
  memset_0(&netname, 0, sizeof(netname));
  v8 = *(struct _INISPOOLER **)(a1 + 280);
  v33 = 0;
  v30 = 0;
  LastError = 0;
  v32 = 0;
  v10 = 0;
  memset_0(v37, 0, 0x40Eu);
  StringCchCopyW(v37, 0x207u, *(const unsigned __int16 **)(a1 + 24));
  v11 = (WCHAR *)AllocSplStr(a2);
  if ( v11 )
  {
    if ( a3 )
    {
      v12 = MapPrinterSDToShareSD(*(void **)(a1 + 192));
      if ( !v12 )
      {
        SetLastError(0x53Au);
        goto LABEL_62;
      }
      v13 = *(_WORD **)(a1 + 80);
      netname.shi503_netname = v11;
      if ( !v13 || !*v13 )
        v13 = *(_WORD **)(a1 + 24);
      v14 = (WCHAR *)AllocSplStr(v13);
      v32 = v14;
      if ( !v14
        || (netname.shi503_remark = v14,
            PrinterName = pszGetPrinterName((struct _INIPRINTER *)a1, v8 != pLocalIniSpooler, L"LocalsplOnly"),
            (v33 = PrinterName) == 0) )
      {
LABEL_43:
        LocalFree(v12);
        goto LABEL_62;
      }
      netname.shi503_path = PrinterName;
      netname.shi503_permissions = 0;
      netname.shi503_passwd = 0;
      v16 = (unsigned int *)(a1 + 16);
      netname.shi503_max_uses = -1;
      netname.shi503_current_uses = -1;
      netname.shi503_type = 1;
      netname.shi503_security_descriptor = v12;
      netname.shi503_servername = *(LPWSTR *)(*((_QWORD *)v8 + 18) + 56LL);
      if ( SafeIncrementReference((unsigned int *)(a1 + 16)) > *(_DWORD *)(a1 + 248) )
        *(_DWORD *)(a1 + 248) = *v16;
      LeaveSplSem(v17);
      v18 = RevertToPrinterSelf();
      v19 = AddPrintShare(v8);
      LastError = v19;
      if ( v19 && v19 != 2114 )
      {
        EnterSplSem(0);
        if ( *v16 )
          SafeDecrementReference((unsigned int *)(a1 + 16));
        ImpersonatePrinterClient(v18);
LABEL_41:
        SetLastError(LastError);
        LogShareActionError(LastError, v37, v11, v31);
        v10 = 0;
        goto LABEL_43;
      }
      LastError = ShareWithAppropriateLevel(&netname, 0, 0);
      if ( (*((_DWORD *)v8 + 42) & 0x1000000) != 0 )
        WebShareManagement(v11, 1);
      if ( LastError == 2118 )
      {
        if ( CheckShareSame((struct _INIPRINTER *)a1, &netname, &v30) || !v30 )
          goto LABEL_38;
        LastError = 0;
      }
      else if ( LastError && LastError != 2114 )
      {
LABEL_36:
        if ( !LastError )
        {
          SplLogType::SplLogType((SplLogType *)v35, v11);
          v22 = SplLogType::SplLogType((SplLogType *)v36, v37);
          SplLogEvent2(&PRINTER_SHARE_SUCCEEDED, v22, v23, 0);
        }
LABEL_38:
        ImpersonatePrinterClient(v18);
        EnterSplSem(0);
        if ( *v16 )
          SafeDecrementReference(v16);
        if ( !LastError )
        {
          CreateServerThread();
          v10 = 1;
          goto LABEL_43;
        }
        goto LABEL_41;
      }
      v20 = AllowRemoteCalls();
      v21 = v20;
      if ( v20 < 0 )
      {
        if ( !LastError )
          NetShareDel(netname.shi503_servername, netname.shi503_netname, 0);
        LastError = v21;
      }
      goto LABEL_36;
    }
    v24 = (unsigned int *)(a1 + 16);
    if ( SafeIncrementReference((unsigned int *)(a1 + 16)) > *(_DWORD *)(a1 + 248) )
      *(_DWORD *)(a1 + 248) = *v24;
    LeaveSplSem(v25);
    v26 = RevertToPrinterSelf();
    if ( v26 || (LastError = GetLastError()) == 0 )
    {
      LastError = NetShareDel(*(LPWSTR *)(*((_QWORD *)v8 + 18) + 56LL), v11, 0);
      if ( (*((_DWORD *)v8 + 42) & 0x1000000) != 0 )
        WebShareManagement(v11, 0);
      if ( !v26 || ImpersonatePrinterClient(v26) )
        goto LABEL_54;
      if ( !LastError )
      {
        LastError = GetLastError();
LABEL_54:
        if ( !LastError )
        {
          SplLogType::SplLogType((SplLogType *)v36, v11);
          v27 = SplLogType::SplLogType((SplLogType *)v35, v37);
          SplLogEvent2(&PRINTER_UNSHARE_SUCCEEDED, v27, v28, 0);
        }
      }
    }
    EnterSplSem(0);
    if ( *v24 )
      SafeDecrementReference(v24);
    if ( !LastError || LastError == 2310 )
    {
      LastError = 0;
    }
    else
    {
      LocalSpoolerTelemetry::WriteDbgTraceError("ShareThisPrinterDirectly", L"NetShareDel failed. Error %d", LastError);
      SetLastError(LastError);
      v10 = 1;
    }
  }
LABEL_62:
  DllFreeSplStr(v33);
  DllFreeSplStr(v11);
  DllFreeSplStr(v32);
  SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x18009353c  mov     [rsp-8+arg_18], rbx
0x180093541  push    rbp
0x180093542  push    rsi
0x180093543  push    rdi
0x180093544  push    r12
0x180093546  push    r13
0x180093548  push    r14
0x18009354a  push    r15
0x18009354c  lea     rbp, [rsp-3F0h]
0x180093554  sub     rsp, 4F0h
0x18009355b  mov     rax, cs:__security_cookie
0x180093562  xor     rax, rsp
0x180093565  mov     [rbp+420h+var_40], rax
0x18009356c  xor     r15d, r15d
0x18009356f  mov     [rsp+520h+var_4E8], r8d
0x180093574  mov     r13d, r8d
0x180093577  mov     rsi, rdx
0x18009357a  mov     rdi, rcx
0x18009357d  test    r8d, r8d
0x180093580  jz      short loc_1800935EE
0x180093582  test    r9d, r9d
0x180093585  jnz     short loc_1800935EE
0x180093587  lea     rcx, [rsp+520h+var_4F0]; bool *
0x18009358c  mov     [rsp+520h+var_4F0], r15b
0x180093591  call    ?IsFirewallPrintRuleEnabled@@YAHPEA_N@Z; IsFirewallPrintRuleEnabled(bool *)
0x180093596  test    eax, eax
0x180093598  jnz     short loc_1800935A1
0x18009359a  xor     eax, eax
0x18009359c  jmp     loc_1800939B5
0x1800935a1  cmp     [rsp+520h+var_4F0], r15b
0x1800935a6  jnz     short loc_1800935EE
0x1800935a8  mov     rax, [rdi+118h]
0x1800935af  xor     r9d, r9d
0x1800935b2  mov     [rsp+520h+var_4F8], r15d
0x1800935b7  xor     r8d, r8d
0x1800935ba  xor     ecx, ecx
0x1800935bc  mov     [rsp+520h+var_500], rax
0x1800935c1  lea     edx, [r9+1]
0x1800935c5  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x1800935ca  test    eax, eax
0x1800935cc  jnz     short loc_1800935EE
0x1800935ce  lea     rdx, aAccessDeniedSh; "Access denied sharing printer because t"...
0x1800935d5  lea     rcx, aSharethisprint_2; "ShareThisPrinterDirectly"
0x1800935dc  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800935e1  mov     ecx, 5; dwErrCode
0x1800935e6  call    cs:__imp_SetLastError
0x1800935ec  jmp     short loc_18009359A
0x1800935ee  xor     edx, edx; Val
0x1800935f0  lea     rcx, [rsp+520h+netname]; void *
0x1800935f5  lea     r8d, [rdx+50h]; Size
0x1800935f9  call    memset_0
0x1800935fe  mov     r14, [rdi+118h]
0x180093605  lea     rcx, [rbp+420h+var_450]; void *
0x180093609  xor     edx, edx; Val
0x18009360b  mov     [rsp+520h+var_4D8], r15
0x180093610  mov     r8d, 40Eh; Size
0x180093616  mov     [rsp+520h+var_4EC], r15d
0x18009361b  mov     ebx, r15d
0x18009361e  mov     [rsp+520h+var_4E0], r15
0x180093623  mov     r12d, r15d
0x180093626  call    memset_0
0x18009362b  mov     r8, [rdi+18h]; unsigned __int16 *
0x18009362f  lea     rcx, [rbp+420h+var_450]; unsigned __int16 *
0x180093633  mov     edx, 207h; unsigned __int64
0x180093638  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009363d  mov     rcx, rsi
0x180093640  call    cs:__imp_AllocSplStr
0x180093646  xor     esi, esi
0x180093648  mov     r15, rax
0x18009364b  test    rax, rax
0x18009364e  jz      loc_18009398B
0x180093654  test    r13d, r13d
0x180093657  jz      loc_180093881
0x18009365d  mov     rcx, [rdi+0C0h]; void *
0x180093664  call    MapPrinterSDToShareSD
0x180093669  mov     r13, rax
0x18009366c  test    rax, rax
0x18009366f  jnz     short loc_180093681
0x180093671  mov     ecx, 53Ah; dwErrCode
0x180093676  call    cs:__imp_SetLastError
0x18009367c  jmp     loc_18009398B
0x180093681  mov     rcx, [rdi+50h]
0x180093685  mov     [rsp+520h+netname], r15
0x18009368a  test    rcx, rcx
0x18009368d  jz      short loc_180093694
0x18009368f  cmp     [rcx], si
0x180093692  jnz     short loc_180093698
0x180093694  mov     rcx, [rdi+18h]
0x180093698  call    cs:__imp_AllocSplStr
0x18009369e  mov     [rsp+520h+var_4E0], rax
0x1800936a3  test    rax, rax
0x1800936a6  jz      loc_180093873
0x1800936ac  cmp     r14, cs:pLocalIniSpooler
0x1800936b3  lea     r8, aLocalsplonly; "LocalsplOnly"
0x1800936ba  mov     edx, esi
0x1800936bc  mov     [rsp+520h+var_4C0], rax
0x1800936c1  setnz   dl; int
0x1800936c4  mov     rcx, rdi; struct _INIPRINTER *
0x1800936c7  call    ?pszGetPrinterName@@YAPEAGPEAU_INIPRINTER@@HPEBG@Z; pszGetPrinterName(_INIPRINTER *,int,ushort const *)
0x1800936cc  mov     [rsp+520h+var_4D8], rax
0x1800936d1  test    rax, rax
0x1800936d4  jz      loc_180093873
0x1800936da  mov     [rsp+520h+var_4A8], rax
0x1800936df  or      eax, 0FFFFFFFFh
0x1800936e2  mov     [rsp+520h+var_4B8], esi
0x1800936e6  mov     [rbp+420h+var_4A0], rsi
0x1800936ea  lea     rsi, [rdi+10h]
0x1800936ee  mov     [rsp+520h+var_4B4], eax
0x1800936f2  mov     [rsp+520h+var_4B0], eax
0x1800936f6  mov     [rsp+520h+var_4C8], 1
0x1800936fe  mov     [rbp+420h+var_488], r13
0x180093702  mov     rcx, [r14+90h]
0x180093709  mov     rdx, [rcx+38h]
0x18009370d  mov     rcx, rsi; unsigned int *
0x180093710  mov     [rbp+420h+servername], rdx
0x180093714  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180093719  cmp     eax, [rdi+0F8h]
0x18009371f  jbe     short loc_180093729
0x180093721  mov     eax, [rsi]
0x180093723  mov     [rdi+0F8h], eax
0x180093729  call    LeaveSplSem
0x18009372e  call    cs:__imp_RevertToPrinterSelf
0x180093734  mov     rcx, r14; struct _INISPOOLER *
0x180093737  mov     r12, rax
0x18009373a  call    ?AddPrintShare@@YAKPEAU_INISPOOLER@@@Z; AddPrintShare(_INISPOOLER *)
0x18009373f  mov     ebx, eax
0x180093741  test    eax, eax
0x180093743  jz      short loc_18009376E
0x180093745  cmp     eax, 842h
0x18009374a  jz      short loc_18009376E
0x18009374c  xor     ecx, ecx
0x18009374e  call    EnterSplSem
0x180093753  cmp     dword ptr [rsi], 0
0x180093756  jz      short loc_180093760
0x180093758  mov     rcx, rsi; unsigned int *
0x18009375b  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180093760  mov     rcx, r12; hToken
0x180093763  call    cs:__imp_ImpersonatePrinterClient
0x180093769  jmp     loc_180093848
0x18009376e  xor     r8d, r8d; unsigned __int16 *
0x180093771  lea     rcx, [rsp+520h+netname]; struct _SHARE_INFO_503 *
0x180093776  xor     edx, edx; unsigned __int16 *
0x180093778  call    ?ShareWithAppropriateLevel@@YAKPEAU_SHARE_INFO_503@@PEBG1@Z; ShareWithAppropriateLevel(_SHARE_INFO_503 *,ushort const *,ushort const *)
0x18009377d  test    dword ptr [r14+0A8h], 1000000h
0x180093788  mov     ebx, eax
0x18009378a  jz      short loc_180093799
0x18009378c  mov     edx, 1; int
0x180093791  mov     rcx, r15; unsigned __int16 *
0x180093794  call    ?WebShareManagement@@YAXPEAGH@Z; WebShareManagement(ushort *,int)
0x180093799  cmp     ebx, 846h
0x18009379f  jnz     short loc_1800937C1
0x1800937a1  lea     r8, [rsp+520h+var_4EC]; int *
0x1800937a6  mov     rcx, rdi; struct _INIPRINTER *
0x1800937a9  lea     rdx, [rsp+520h+netname]; struct _SHARE_INFO_503 *
0x1800937ae  call    ?CheckShareSame@@YAKPEAU_INIPRINTER@@PEAU_SHARE_INFO_503@@PEAH@Z; CheckShareSame(_INIPRINTER *,_SHARE_INFO_503 *,int *)
0x1800937b3  test    eax, eax
0x1800937b5  jnz     short loc_180093827
0x1800937b7  cmp     [rsp+520h+var_4EC], eax
0x1800937bb  jz      short loc_180093827
0x1800937bd  xor     ebx, ebx
0x1800937bf  jmp     short loc_1800937CD
0x1800937c1  test    ebx, ebx
0x1800937c3  jz      short loc_1800937CD
0x1800937c5  cmp     ebx, 842h
0x1800937cb  jnz     short loc_1800937F2
0x1800937cd  call    cs:__imp_AllowRemoteCalls
0x1800937d3  mov     edi, eax
0x1800937d5  test    eax, eax
0x1800937d7  jns     short loc_1800937F2
0x1800937d9  test    ebx, ebx
0x1800937db  jnz     short loc_1800937EF
0x1800937dd  mov     rdx, [rsp+520h+netname]; netname
0x1800937e2  xor     r8d, r8d; reserved
0x1800937e5  mov     rcx, [rbp+420h+servername]; servername
0x1800937e9  call    cs:__imp_NetShareDel
0x1800937ef  movzx   ebx, di
0x1800937f2  test    ebx, ebx
0x1800937f4  jnz     short loc_180093827
0x1800937f6  mov     rdx, r15; unsigned __int16 *
0x1800937f9  lea     rcx, [rbp+420h+var_480]; this
0x1800937fd  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180093802  lea     rdx, [rbp+420h+var_450]; unsigned __int16 *
0x180093806  mov     r10, rax
0x180093809  lea     rcx, [rbp+420h+var_468]; this
0x18009380d  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180093812  xor     r9d, r9d
0x180093815  lea     rcx, PRINTER_SHARE_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18009381c  mov     r8, r10
0x18009381f  mov     rdx, rax; struct SplLogType *
0x180093822  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180093827  mov     rcx, r12; hToken
0x18009382a  call    cs:__imp_ImpersonatePrinterClient
0x180093830  xor     ecx, ecx
0x180093832  call    EnterSplSem
0x180093837  cmp     dword ptr [rsi], 0
0x18009383a  jz      short loc_180093844
0x18009383c  mov     rcx, rsi; unsigned int *
0x18009383f  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180093844  test    ebx, ebx
0x180093846  jz      short loc_180093868
0x180093848  mov     ecx, ebx; dwErrCode
0x18009384a  call    cs:__imp_SetLastError
0x180093850  mov     r9d, [rsp+520h+var_4E8]; int
0x180093855  lea     rdx, [rbp+420h+var_450]; unsigned __int16 *
0x180093859  mov     r8, r15; unsigned __int16 *
0x18009385c  mov     ecx, ebx; unsigned int
0x18009385e  call    ?LogShareActionError@@YAXKPEBG0H@Z; LogShareActionError(ulong,ushort const *,ushort const *,int)
0x180093863  xor     r12d, r12d
0x180093866  jmp     short loc_180093873
0x180093868  call    CreateServerThread
0x18009386d  mov     r12d, 1
0x180093873  mov     rcx, r13; hMem
0x180093876  call    cs:__imp_LocalFree
0x18009387c  jmp     loc_18009398B
0x180093881  lea     rsi, [rdi+10h]
0x180093885  mov     rcx, rsi; unsigned int *
0x180093888  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18009388d  cmp     eax, [rdi+0F8h]
0x180093893  jbe     short loc_18009389D
0x180093895  mov     eax, [rsi]
0x180093897  mov     [rdi+0F8h], eax
0x18009389d  call    LeaveSplSem
0x1800938a2  call    cs:__imp_RevertToPrinterSelf
0x1800938a8  mov     rdi, rax
0x1800938ab  test    rax, rax
0x1800938ae  jnz     short loc_1800938C0
0x1800938b0  call    cs:__imp_GetLastError
0x1800938b6  mov     ebx, eax
0x1800938b8  test    eax, eax
0x1800938ba  jnz     loc_180093943
0x1800938c0  mov     rcx, [r14+90h]
0x1800938c7  xor     r8d, r8d; reserved
0x1800938ca  mov     rdx, r15; netname
0x1800938cd  mov     rcx, [rcx+38h]; servername
0x1800938d1  call    cs:__imp_NetShareDel
0x1800938d7  test    dword ptr [r14+0A8h], 1000000h
0x1800938e2  mov     ebx, eax
0x1800938e4  jz      short loc_1800938F0
0x1800938e6  xor     edx, edx; int
0x1800938e8  mov     rcx, r15; unsigned __int16 *
0x1800938eb  call    ?WebShareManagement@@YAXPEAGH@Z; WebShareManagement(ushort *,int)
0x1800938f0  test    rdi, rdi
0x1800938f3  jz      short loc_18009390E
0x1800938f5  mov     rcx, rdi; hToken
0x1800938f8  call    cs:__imp_ImpersonatePrinterClient
0x1800938fe  test    eax, eax
0x180093900  jnz     short loc_18009390E
0x180093902  test    ebx, ebx
0x180093904  jnz     short loc_180093943
0x180093906  call    cs:__imp_GetLastError
0x18009390c  mov     ebx, eax
0x18009390e  test    ebx, ebx
0x180093910  jnz     short loc_180093943
0x180093912  mov     rdx, r15; unsigned __int16 *
0x180093915  lea     rcx, [rbp+420h+var_468]; this
0x180093919  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18009391e  lea     rdx, [rbp+420h+var_450]; unsigned __int16 *
0x180093922  mov     r10, rax
0x180093925  lea     rcx, [rbp+420h+var_480]; this
0x180093929  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18009392e  xor     r9d, r9d
0x180093931  lea     rcx, PRINTER_UNSHARE_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x180093938  mov     r8, r10
0x18009393b  mov     rdx, rax; struct SplLogType *
0x18009393e  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180093943  xor     ecx, ecx
0x180093945  call    EnterSplSem
0x18009394a  cmp     [rsi], r12d
0x18009394d  jz      short loc_180093957
0x18009394f  mov     rcx, rsi; unsigned int *
0x180093952  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180093957  test    ebx, ebx
0x180093959  jz      short loc_180093989
0x18009395b  cmp     ebx, 906h
0x180093961  jz      short loc_180093989
0x180093963  mov     r8d, ebx
0x180093966  lea     rdx, aNetsharedelFai; "NetShareDel failed. Error %d"
0x18009396d  lea     rcx, aSharethisprint_2; "ShareThisPrinterDirectly"
0x180093974  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180093979  mov     ecx, ebx; dwErrCode
0x18009397b  call    cs:__imp_SetLastError
0x180093981  mov     r12d, 1
0x180093987  jmp     short loc_18009398B
0x180093989  xor     ebx, ebx
0x18009398b  mov     rcx, [rsp+520h+var_4D8]
0x180093990  call    cs:__imp_DllFreeSplStr
0x180093996  mov     rcx, r15
0x180093999  call    cs:__imp_DllFreeSplStr
0x18009399f  mov     rcx, [rsp+520h+var_4E0]
0x1800939a4  call    cs:__imp_DllFreeSplStr
0x1800939aa  mov     ecx, ebx; dwErrCode
0x1800939ac  call    cs:__imp_SetLastError
0x1800939b2  mov     eax, r12d
0x1800939b5  mov     rcx, [rbp+420h+var_40]
0x1800939bc  xor     rcx, rsp; StackCookie
0x1800939bf  call    __security_check_cookie
0x1800939c4  mov     rbx, [rsp+520h+arg_18]
0x1800939cc  add     rsp, 4F0h
0x1800939d3  pop     r15
0x1800939d5  pop     r14
  ... truncated ...
```
