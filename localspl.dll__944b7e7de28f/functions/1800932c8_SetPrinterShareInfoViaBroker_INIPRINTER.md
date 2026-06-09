# SetPrinterShareInfoViaBroker(_INIPRINTER *)

- ea: `0x1800932c8`
- end: `0x1800934d1`
- name: `?SetPrinterShareInfoViaBroker@@YAHPEAU_INIPRINTER@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(struct _INIPRINTER *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180058f28`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18003e984`
- `0x18003ea2c`
- `0x18004a2f0`
- `0x1800932c8`
- `0x1800934d8`
- `0x18009c908`
- `0x1800c7370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009341a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009349e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009341a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009349e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093464`
- `SPOOLSS!DllFreeSplStr` at `0x18009346d`
- `SPOOLSS!DllFreeSplStr` at `0x180093476`
- `SPOOLSS!DllFreeSplStr` at `0x18009347f`
- `SPOOLSS!DllFreeSplStr` at `0x18009346d`
- `SPOOLSS!DllFreeSplStr` at `0x180093476`
- `SPOOLSS!DllFreeSplStr` at `0x18009347f`
- `SPOOLSS!RevertToPrinterSelf` at `0x180093389`
- `SPOOLSS!RevertToPrinterSelf` at `0x180093389`
- `SPOOLSS!AllocSplStr` at `0x18009330a`
- `SPOOLSS!AllocSplStr` at `0x180093335`
- `SPOOLSS!AllocSplStr` at `0x180093359`
- `SPOOLSS!AllocSplStr` at `0x18009330a`
- `SPOOLSS!AllocSplStr` at `0x180093335`
- `SPOOLSS!AllocSplStr` at `0x180093359`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093440`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180093440`

## string_xrefs

- `0x1800933ca`: `BrokerPrinterShareOperation (Update) failed with error %d`
- `0x1800934a7`: `ImpersonatePrinterClient failed with error %d`
- `0x1800933d1`: `SetPrinterShareInfoViaBroker`
- `0x1800933ec`: `SetPrinterShareInfoViaBroker`
- `0x18009342a`: `SetPrinterShareInfoViaBroker`
- `0x1800934ae`: `SetPrinterShareInfoViaBroker`

## pseudocode

```c
bool __fastcall SetPrinterShareInfoViaBroker(void **a1)
{
  __int64 v2; // rsi
  __int64 v3; // r15
  void *v4; // r13
  __int64 v5; // rbp
  __int64 LastError; // rbx
  _WORD *v7; // rcx
  _WORD *v8; // rcx
  _DWORD *v9; // r14
  __int64 v10; // rcx
  HANDLE v11; // r12
  unsigned __int16 v12; // ax
  __int64 v13; // rcx
  DWORD v15; // eax
  const char *v16; // r9
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = 0;
  v3 = 0;
  v4 = MapPrinterSDToShareSD(a1[24]);
  if ( v4 )
  {
    v5 = AllocSplStr(a1[5]);
    if ( !v5 )
      goto LABEL_4;
    v7 = a1[10];
    if ( !v7 || !*v7 )
      v7 = a1[3];
    v2 = AllocSplStr(v7);
    if ( v2 && ((v8 = (_WORD *)*((_QWORD *)a1[35] + 3)) == 0 || !*v8 || (v3 = AllocSplStr(v8)) != 0) )
    {
      v9 = a1 + 2;
      if ( SafeIncrementReference((unsigned int *)a1 + 4) > *((_DWORD *)a1 + 62) )
        *((_DWORD *)a1 + 62) = *v9;
      LeaveSplSem(v10);
      v11 = RevertToPrinterSelf();
      if ( v11 )
      {
        v12 = BrokerPrinterShareOperation(1, v5, 0, v2, v3, v4);
        LODWORD(LastError) = v12;
        if ( v12 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "SetPrinterShareInfoViaBroker",
            L"BrokerPrinterShareOperation (Update) failed with error %d",
            v12);
          if ( (_DWORD)LastError == 2310 )
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "SetPrinterShareInfoViaBroker",
              L"Share information was not found. Recreating the share.");
            EnterSplSem(0);
            if ( (unsigned int)ShareThisPrinter(a1, a1[5], 1, 0) )
            {
              LODWORD(LastError) = 0;
            }
            else
            {
              LastError = GetLastError();
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "SetPrinterShareInfoViaBroker",
                L"ShareThisPrinter failed with error %d",
                LastError);
            }
            LeaveSplSem(v13);
          }
        }
        if ( !ImpersonatePrinterClient(v11) )
        {
          v15 = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "SetPrinterShareInfoViaBroker",
            L"ImpersonatePrinterClient failed with error %d",
            v15);
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x17B,
            (unsigned int)"printscan\\print\\spooler\\localspl\\net.c",
            v16);
        }
        EnterSplSem(0);
        if ( *v9 )
          SafeDecrementReference((unsigned int *)a1 + 4);
      }
      else
      {
        LODWORD(LastError) = GetLastError();
      }
    }
    else
    {
LABEL_4:
      LODWORD(LastError) = 8;
    }
    LocalFree(v4);
  }
  else
  {
    v5 = 0;
    LODWORD(LastError) = 1338;
  }
  DllFreeSplStr(v5);
  DllFreeSplStr(v2);
  DllFreeSplStr(v3);
  return (_DWORD)LastError == 0;
}

```

## disassembly

```asm
0x1800932c8  push    rbx
0x1800932ca  push    rbp
0x1800932cb  push    rsi
0x1800932cc  push    rdi
0x1800932cd  push    r12
0x1800932cf  push    r13
0x1800932d1  push    r14
0x1800932d3  push    r15
0x1800932d5  sub     rsp, 38h
0x1800932d9  mov     rdi, rcx
0x1800932dc  xor     r12d, r12d
0x1800932df  mov     rcx, [rcx+0C0h]; void *
0x1800932e6  mov     esi, r12d
0x1800932e9  mov     r15d, r12d
0x1800932ec  call    MapPrinterSDToShareSD
0x1800932f1  mov     r13, rax
0x1800932f4  test    rax, rax
0x1800932f7  jnz     short loc_180093306
0x1800932f9  mov     ebp, r12d
0x1800932fc  mov     ebx, 53Ah
0x180093301  jmp     loc_18009346A
0x180093306  mov     rcx, [rdi+28h]
0x18009330a  call    cs:__imp_AllocSplStr
0x180093310  mov     rbp, rax
0x180093313  test    rax, rax
0x180093316  jnz     short loc_180093322
0x180093318  mov     ebx, 8
0x18009331d  jmp     loc_180093461
0x180093322  mov     rcx, [rdi+50h]
0x180093326  test    rcx, rcx
0x180093329  jz      short loc_180093331
0x18009332b  cmp     [rcx], r12w
0x18009332f  jnz     short loc_180093335
0x180093331  mov     rcx, [rdi+18h]
0x180093335  call    cs:__imp_AllocSplStr
0x18009333b  mov     rsi, rax
0x18009333e  test    rax, rax
0x180093341  jz      short loc_180093318
0x180093343  mov     rax, [rdi+118h]
0x18009334a  mov     rcx, [rax+18h]
0x18009334e  test    rcx, rcx
0x180093351  jz      short loc_180093367
0x180093353  cmp     [rcx], r12w
0x180093357  jz      short loc_180093367
0x180093359  call    cs:__imp_AllocSplStr
0x18009335f  mov     r15, rax
0x180093362  test    rax, rax
0x180093365  jz      short loc_180093318
0x180093367  lea     r14, [rdi+10h]
0x18009336b  mov     rcx, r14; unsigned int *
0x18009336e  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180093373  cmp     eax, [rdi+0F8h]
0x180093379  jbe     short loc_180093384
0x18009337b  mov     eax, [r14]
0x18009337e  mov     [rdi+0F8h], eax
0x180093384  call    LeaveSplSem
0x180093389  call    cs:__imp_RevertToPrinterSelf
0x18009338f  mov     r12, rax
0x180093392  test    rax, rax
0x180093395  jnz     short loc_1800933A4
0x180093397  call    cs:__imp_GetLastError
0x18009339d  mov     ebx, eax
0x18009339f  jmp     loc_180093461
0x1800933a4  xor     r8d, r8d
0x1800933a7  mov     [rsp+78h+var_50], r13
0x1800933ac  mov     r9, rsi
0x1800933af  mov     [rsp+78h+var_58], r15
0x1800933b4  mov     rdx, rbp
0x1800933b7  lea     ecx, [r8+1]
0x1800933bb  call    ?BrokerPrinterShareOperation@@YAJW4SharingOperation@@PEBG111PEAX@Z; BrokerPrinterShareOperation(SharingOperation,ushort const *,ushort const *,ushort const *,ushort const *,void *)
0x1800933c0  movzx   ebx, ax
0x1800933c3  test    ebx, ebx
0x1800933c5  jz      short loc_18009343D
0x1800933c7  mov     r8d, ebx
0x1800933ca  lea     rdx, aBrokerprinters; "BrokerPrinterShareOperation (Update) fa"...
0x1800933d1  lea     rcx, aSetprintershar_0; "SetPrinterShareInfoViaBroker"
0x1800933d8  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800933dd  cmp     ebx, 906h
0x1800933e3  jnz     short loc_18009343D
0x1800933e5  lea     rdx, aShareInformati; "Share information was not found. Recrea"...
0x1800933ec  lea     rcx, aSetprintershar_0; "SetPrinterShareInfoViaBroker"
0x1800933f3  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800933f8  xor     ecx, ecx
0x1800933fa  call    EnterSplSem
0x1800933ff  mov     rdx, [rdi+28h]
0x180093403  xor     r9d, r9d
0x180093406  mov     rcx, rdi
0x180093409  lea     r8d, [r9+1]
0x18009340d  call    ?ShareThisPrinter@@YAHPEAU_INIPRINTER@@PEAGHW4Enum@PrinterSharingOptions@@@Z; ShareThisPrinter(_INIPRINTER *,ushort *,int,PrinterSharingOptions::Enum)
0x180093412  test    eax, eax
0x180093414  jz      short loc_18009341A
0x180093416  xor     ebx, ebx
0x180093418  jmp     short loc_180093438
0x18009341a  call    cs:__imp_GetLastError
0x180093420  mov     r8d, eax
0x180093423  lea     rdx, aSharethisprint_3; "ShareThisPrinter failed with error %d"
0x18009342a  lea     rcx, aSetprintershar_0; "SetPrinterShareInfoViaBroker"
0x180093431  mov     ebx, eax
0x180093433  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180093438  call    LeaveSplSem
0x18009343d  mov     rcx, r12; hToken
0x180093440  call    cs:__imp_ImpersonatePrinterClient
0x180093446  xor     r12d, r12d
0x180093449  test    eax, eax
0x18009344b  jz      short loc_18009349E
0x18009344d  xor     ecx, ecx
0x18009344f  call    EnterSplSem
0x180093454  cmp     [r14], r12d
0x180093457  jz      short loc_180093461
0x180093459  mov     rcx, r14; unsigned int *
0x18009345c  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180093461  mov     rcx, r13; hMem
0x180093464  call    cs:__imp_LocalFree
0x18009346a  mov     rcx, rbp
0x18009346d  call    cs:__imp_DllFreeSplStr
0x180093473  mov     rcx, rsi
0x180093476  call    cs:__imp_DllFreeSplStr
0x18009347c  mov     rcx, r15
0x18009347f  call    cs:__imp_DllFreeSplStr
0x180093485  test    ebx, ebx
0x180093487  mov     eax, r12d
0x18009348a  setz    al
0x18009348d  add     rsp, 38h
0x180093491  pop     r15
0x180093493  pop     r14
0x180093495  pop     r13
0x180093497  pop     r12
0x180093499  pop     rdi
0x18009349a  pop     rsi
0x18009349b  pop     rbp
0x18009349c  pop     rbx
0x18009349d  retn
0x18009349e  call    cs:__imp_GetLastError
0x1800934a4  mov     r8d, eax
0x1800934a7  lea     rdx, aImpersonatepri_0; "ImpersonatePrinterClient failed with er"...
0x1800934ae  lea     rcx, aSetprintershar_0; "SetPrinterShareInfoViaBroker"
0x1800934b5  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800934ba  mov     rcx, [rsp+78h]; this
0x1800934bf  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\localspl\\ne"...
0x1800934c6  mov     edx, 17Bh; void *
0x1800934cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
