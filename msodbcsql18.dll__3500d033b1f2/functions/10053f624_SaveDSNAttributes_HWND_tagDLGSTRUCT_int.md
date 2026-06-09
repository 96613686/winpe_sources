# SaveDSNAttributes(HWND__ *,tagDLGSTRUCT *,int)

- ea: `0x10053f624`
- end: `0x10053ff46`
- name: `?SaveDSNAttributes@@YAKPEAUHWND__@@PEAUtagDLGSTRUCT@@H@Z`
- size: `2338`
- prototype: `unsigned int __fastcall(HWND hWnd, struct tagDLGSTRUCT *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10051baa0`
- `0x10053ffb0`

## callees

- `0x100405948`
- `0x1004070bc`
- `0x10046c6c4`
- `0x10046cf68`
- `0x10046d140`
- `0x10053f624`
- `0x10053ff4c`
- `0x100546ff0`
- `0x1005470b0`
- `0x100547130`
- `0x100547180`
- `0x100548210`

## import_xrefs

- `USER32!MessageBoxW` at `0x10053f75c`
- `USER32!MessageBoxW` at `0x10053f75c`
- `USER32!LoadStringW` at `0x10053f740`
- `USER32!LoadStringW` at `0x10053f740`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10053fdf2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10053fe54`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10053fdf2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10053fe54`

## string_xrefs

- `0x10053fb2b`: `GetDataExtensions`
- `0x10053fd7e`: `TranslationDLL`

## pseudocode

```c
__int64 __fastcall SaveDSNAttributes(HWND hWnd, struct tagDLGSTRUCT *a2, int a3)
{
  HWND v3; // r14
  struct CDlgATTRs *v4; // rbx
  __int64 v7; // rcx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  WCHAR *v14; // r8
  DWORD pfErrorCode[4]; // [rsp+30h] [rbp-678h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-668h] BYREF
  WCHAR Text[528]; // [rsp+250h] [rbp-458h] BYREF

  v3 = (HWND)*((_QWORD *)a2 + 7);
  v4 = (struct tagDLGSTRUCT *)((char *)a2 + 136);
  v7 = *((_QWORD *)a2 + 18);
  v9 = *(_QWORD *)(*((_QWORD *)a2 + 19) + 32LL);
  v10 = (const unsigned __int16 *)(v9 + *(_QWORD *)(v7 + 56));
  if ( (*((_BYTE *)a2 + 120) & 0x20) != 0
    && (!*(_WORD *)(v9 + *(_QWORD *)(v7 + 128))
     || !*(_WORD *)(v9 + *(_QWORD *)(v7 + 344)) && (*(_BYTE *)(v7 + 336) & 0x20) == 0
     || !*(_WORD *)(v9 + *(_QWORD *)(v7 + 320)) && (*(_BYTE *)(v7 + 312) & 0x20) == 0) )
  {
    return 4;
  }
  if ( SQLWriteDSNToIniW(v10, L"ODBC Driver 18 for SQL Server") )
  {
    WriteDSNAttribute(v3, v10, v4, 3, L"Description");
    WriteDSNAttribute(v3, v10, v4, 5, L"Server");
    WriteDSNAttribute(v3, v10, v4, 25, L"Regional");
    WriteDSNAttribute(v3, v10, v4, 26, L"QuotedId");
    WriteDSNAttribute(v3, v10, v4, 27, L"AnsiNPW");
    WriteDSNAttribute(v3, v10, v4, 11, L"Database");
    WriteDSNAttribute(v3, v10, v4, 12, L"Language");
    WriteDSNAttribute(v3, v10, v4, 28, L"AttachDBFileName");
    WriteDSNAttribute(v3, v10, v4, 15, L"Encrypt");
    WriteDSNAttribute(v3, v10, v4, 16, L"TrustServerCertificate");
    WriteDSNAttribute(v3, v10, v4, 17, L"MARS_Connection");
    WriteDSNAttribute(v3, v10, v4, 18, L"Failover_Partner");
    WriteDSNAttribute(v3, v10, v4, 29, L"ServerSPN");
    WriteDSNAttribute(v3, v10, v4, 30, L"FailoverPartnerSPN");
    WriteDSNAttribute(v3, v10, v4, 31, L"ApplicationIntent");
    WriteDSNAttribute(v3, v10, v4, 32, L"MultiSubnetFailover");
    WriteDSNAttribute(v3, v10, v4, 33, L"ConnectRetryCount");
    WriteDSNAttribute(v3, v10, v4, 34, L"ConnectRetryInterval");
    WriteDSNAttribute(v3, v10, v4, 35, L"ClientCertificate");
    WriteDSNAttribute(v3, v10, v4, 36, L"ColumnEncryption");
    WriteDSNAttribute(v3, v10, v4, 37, L"TransparentNetworkIPResolution");
    WriteDSNAttribute(v3, v10, v4, 39, L"KeystoreAuthentication");
    WriteDSNAttribute(v3, v10, v4, 40, L"KeystorePrincipalId");
    WriteDSNAttribute(v3, v10, v4, 41, L"KeystoreSecret");
    WriteDSNAttribute(v3, v10, v4, 42, L"KeystoreLocation");
    WriteDSNAttribute(v3, v10, v4, 43, L"UseFMTONLY");
    WriteDSNAttribute(v3, v10, v4, 45, L"KeepAlive");
    WriteDSNAttribute(v3, v10, v4, 46, L"KeepAliveInterval");
    WriteDSNAttribute(v3, v10, v4, 48, L"LongAsMax");
    WriteDSNAttribute(v3, v10, v4, 49, L"HostNameInCertificate");
    WriteDSNAttribute(v3, v10, v4, 50, L"GetDataExtensions");
    WriteDSNAttribute(v3, v10, v4, 51, L"IpAddressPreference");
    WriteDSNAttribute(v3, v10, v4, 52, L"ServerCertificate");
    WriteDSNAttribute(v3, v10, v4, 53, L"RetryExec");
    WriteDSNAttribute(v3, v10, v4, 55, L"PacketSize");
    WriteDSNAttribute(v3, v10, v4, 56, L"vectorTypeSupport");
    WriteDSNAttribute(v3, v10, v4, 6, L"LastUser");
    WriteDSNAttribute(v3, v10, v4, 21, L"QueryLogFile");
    WriteDSNAttribute(v3, v10, v4, 24, L"StatsLogFile");
    WriteDSNAttribute(v3, v10, v4, 20, L"QueryLog_On");
    WriteDSNAttribute(v3, v10, v4, 23, L"StatsLog_On");
    WriteDSNAttribute(v3, v10, v4, 22, L"QueryLogTime");
    WriteDSNAttribute(v3, v10, v4, 8, L"Trusted_Connection");
    WriteDSNAttribute(v3, v10, v4, 38, L"Authentication");
    WriteDSNAttribute(v3, v10, v4, 19, L"AutoTranslate");
    SQLWritePrivateProfileStringW(v10, L"FastConnectOption", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"Network", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"Address", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"TranslationName", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"TranslationOption", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"TranslationDLL", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"OemToAnsi", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"UseProcForPrepare", 0, L"ODBC.INI");
    SQLWritePrivateProfileStringW(v10, L"Fallback", 0, L"ODBC.INI");
    if ( !a3
      && (*(_BYTE *)(*((_QWORD *)v4 + 1) + 48LL) & 1) != 0
      && *((_WORD *)a2 + 96)
      && _wcsicmp((const wchar_t *)a2 + 96, v10) )
    {
      SQLRemoveDSNFromIniW((LPCWSTR)a2 + 96);
    }
    if ( *((_QWORD *)a2 + 7)
      || (v12 = *((_QWORD *)v4 + 1), (*(_BYTE *)(v12 + 312) & 1) != 0)
      || (*(_BYTE *)(v12 + 336) & 1) != 0 )
    {
      v13 = *((_QWORD *)v4 + 1);
      if ( (*(_BYTE *)(v13 + 312) & 0x20) != 0 && (*(_BYTE *)(v13 + 336) & 0x20) != 0
        || !_wcsicmp((const wchar_t *)(*(_QWORD *)(*((_QWORD *)v4 + 2) + 32LL) + *(_QWORD *)(v13 + 128)), L"(local)") )
      {
        v14 = 0;
      }
      else
      {
        if ( (*(_BYTE *)(*((_QWORD *)v4 + 1) + 312LL) & 0x20) != 0 && CDlgATTRs::SetATTRValue(v4, 13, L"DBNETLIB") < 0
          || (*(_BYTE *)(*((_QWORD *)v4 + 1) + 336LL) & 0x20) != 0 && (int)CDlgATTRs::CopyATTRValue(v4, 14, 5) < 0 )
        {
          return 21;
        }
        StringCchPrintfW(
          Text,
          0x20Au,
          L"%s,%s",
          *(_QWORD *)(*((_QWORD *)v4 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v4 + 1) + 320LL),
          *(_QWORD *)(*((_QWORD *)v4 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v4 + 1) + 344LL));
        v14 = Text;
      }
      DrvWriteProfileString(
        L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo",
        (LPCWSTR)(*(_QWORD *)(*((_QWORD *)v4 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v4 + 1) + 128LL)),
        (BYTE *)v14);
    }
    return 0;
  }
  else
  {
    pfErrorCode[0] = 0;
    SQLInstallerErrorW(1u, pfErrorCode, 0, 0, 0);
    if ( hWnd )
    {
      if ( pfErrorCode[0] == 7 )
      {
        LoadFormattedMessage(g_hinstance_language, 0x9C49u, Text, 0x20Au, v10);
        LoadStringW(g_hinstance_language, 0x9C4Cu, Buffer, 261);
        MessageBoxW(hWnd, Text, Buffer, 0x30u);
      }
    }
    return pfErrorCode[0];
  }
}

```

## disassembly

```asm
0x10053f624  mov     [rsp+arg_10], rbx
0x10053f629  mov     [rsp+arg_18], rbp
0x10053f62e  push    rsi
0x10053f62f  push    rdi
0x10053f630  push    r12
0x10053f632  push    r14
0x10053f634  push    r15
0x10053f636  sub     rsp, 680h
0x10053f63d  mov     rax, cs:__security_cookie
0x10053f644  xor     rax, rsp
0x10053f647  mov     [rsp+6A8h+var_38], rax
0x10053f64f  mov     r14, [rdx+38h]
0x10053f653  lea     rbx, [rdx+88h]
0x10053f65a  mov     rax, [rbx+10h]
0x10053f65e  mov     rdi, rdx
0x10053f661  mov     rbp, rcx
0x10053f664  xor     r12d, r12d
0x10053f667  mov     rcx, [rbx+8]
0x10053f66b  mov     r15d, r8d
0x10053f66e  mov     rdx, [rax+20h]
0x10053f672  mov     rsi, [rcx+38h]
0x10053f676  add     rsi, rdx
0x10053f679  test    byte ptr [rdi+78h], 20h
0x10053f67d  jz      short loc_10053F6C5
0x10053f67f  mov     rax, [rcx+80h]
0x10053f686  cmp     [rdx+rax], r12w
0x10053f68b  jz      short loc_10053F6BB
0x10053f68d  mov     rax, [rcx+158h]
0x10053f694  cmp     [rdx+rax], r12w
0x10053f699  jnz     short loc_10053F6A4
0x10053f69b  test    byte ptr [rcx+150h], 20h
0x10053f6a2  jz      short loc_10053F6BB
0x10053f6a4  mov     rax, [rcx+140h]
0x10053f6ab  cmp     [rdx+rax], r12w
0x10053f6b0  jnz     short loc_10053F6C5
0x10053f6b2  test    byte ptr [rcx+138h], 20h
0x10053f6b9  jnz     short loc_10053F6C5
0x10053f6bb  mov     eax, 4
0x10053f6c0  jmp     loc_10053FF1A
0x10053f6c5  lea     rdx, szDriver; "ODBC Driver 18 for SQL Server"
0x10053f6cc  mov     rcx, rsi; lpszDSN
0x10053f6cf  call    SQLWriteDSNToIniW
0x10053f6d4  test    eax, eax
0x10053f6d6  jnz     loc_10053F76B
0x10053f6dc  xor     r9d, r9d; cchErrorMsgMax
0x10053f6df  mov     [rsp+6A8h+pfErrorCode], r12d
0x10053f6e4  lea     ecx, [rax+1]; iError
0x10053f6e7  mov     [rsp+6A8h+pcchErrorMsg], r12; pcchErrorMsg
0x10053f6ec  xor     r8d, r8d; lpszErrorMsg
0x10053f6ef  lea     rdx, [rsp+6A8h+pfErrorCode]; pfErrorCode
0x10053f6f4  call    SQLInstallerErrorW
0x10053f6f9  test    rbp, rbp
0x10053f6fc  jz      short loc_10053F762
0x10053f6fe  cmp     [rsp+6A8h+pfErrorCode], 7
0x10053f703  jnz     short loc_10053F762
0x10053f705  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x10053f70c  lea     r8, [rsp+6A8h+Text]; unsigned __int16 *
0x10053f714  mov     r9d, 20Ah; unsigned int
0x10053f71a  mov     [rsp+6A8h+pcchErrorMsg], rsi
0x10053f71f  mov     edx, 9C49h; unsigned int
0x10053f724  call    ?LoadFormattedMessage@@YAKPEAUHINSTANCE__@@KPEAGKZZ; LoadFormattedMessage(HINSTANCE__ *,ulong,ushort *,ulong,...)
0x10053f729  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x10053f730  lea     r8, [rsp+6A8h+Buffer]; lpBuffer
0x10053f735  mov     r9d, 105h; cchBufferMax
0x10053f73b  mov     edx, 9C4Ch; uID
0x10053f740  call    cs:__imp_LoadStringW
0x10053f746  mov     r9d, 30h ; '0'; uType
0x10053f74c  lea     r8, [rsp+6A8h+Buffer]; lpCaption
0x10053f751  lea     rdx, [rsp+6A8h+Text]; lpText
0x10053f759  mov     rcx, rbp; hWnd
0x10053f75c  call    cs:__imp_MessageBoxW
0x10053f762  mov     eax, [rsp+6A8h+pfErrorCode]
0x10053f766  jmp     loc_10053FF1A
0x10053f76b  lea     rax, aDescription; "Description"
0x10053f772  mov     r9d, 3; int
0x10053f778  mov     r8, rbx; struct CDlgATTRs *
0x10053f77b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f780  mov     rdx, rsi; unsigned __int16 *
0x10053f783  mov     rcx, r14; HWND
0x10053f786  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f78b  lea     rax, szEntry; "Server"
0x10053f792  mov     r9d, 5; int
0x10053f798  mov     r8, rbx; struct CDlgATTRs *
0x10053f79b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f7a0  mov     rdx, rsi; unsigned __int16 *
0x10053f7a3  mov     rcx, r14; HWND
0x10053f7a6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f7ab  lea     rax, aRegional; "Regional"
0x10053f7b2  mov     r9d, 19h; int
0x10053f7b8  mov     r8, rbx; struct CDlgATTRs *
0x10053f7bb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f7c0  mov     rdx, rsi; unsigned __int16 *
0x10053f7c3  mov     rcx, r14; HWND
0x10053f7c6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f7cb  lea     rax, aQuotedid; "QuotedId"
0x10053f7d2  mov     r9d, 1Ah; int
0x10053f7d8  mov     r8, rbx; struct CDlgATTRs *
0x10053f7db  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f7e0  mov     rdx, rsi; unsigned __int16 *
0x10053f7e3  mov     rcx, r14; HWND
0x10053f7e6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f7eb  lea     rax, aAnsinpw; "AnsiNPW"
0x10053f7f2  mov     r9d, 1Bh; int
0x10053f7f8  mov     r8, rbx; struct CDlgATTRs *
0x10053f7fb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f800  mov     rdx, rsi; unsigned __int16 *
0x10053f803  mov     rcx, r14; HWND
0x10053f806  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f80b  lea     rax, aDatabase; "Database"
0x10053f812  mov     r9d, 0Bh; int
0x10053f818  mov     r8, rbx; struct CDlgATTRs *
0x10053f81b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f820  mov     rdx, rsi; unsigned __int16 *
0x10053f823  mov     rcx, r14; HWND
0x10053f826  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f82b  lea     rax, aLanguage; "Language"
0x10053f832  mov     r9d, 0Ch; int
0x10053f838  mov     r8, rbx; struct CDlgATTRs *
0x10053f83b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f840  mov     rdx, rsi; unsigned __int16 *
0x10053f843  mov     rcx, r14; HWND
0x10053f846  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f84b  lea     rax, aAttachdbfilena; "AttachDBFileName"
0x10053f852  mov     r9d, 1Ch; int
0x10053f858  mov     r8, rbx; struct CDlgATTRs *
0x10053f85b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f860  mov     rdx, rsi; unsigned __int16 *
0x10053f863  mov     rcx, r14; HWND
0x10053f866  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f86b  lea     rax, aEncrypt_0; "Encrypt"
0x10053f872  mov     r9d, 0Fh; int
0x10053f878  mov     r8, rbx; struct CDlgATTRs *
0x10053f87b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f880  mov     rdx, rsi; unsigned __int16 *
0x10053f883  mov     rcx, r14; HWND
0x10053f886  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f88b  lea     rax, aTrustservercer; "TrustServerCertificate"
0x10053f892  mov     r9d, 10h; int
0x10053f898  mov     r8, rbx; struct CDlgATTRs *
0x10053f89b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f8a0  mov     rdx, rsi; unsigned __int16 *
0x10053f8a3  mov     rcx, r14; HWND
0x10053f8a6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f8ab  lea     rax, aMarsConnection; "MARS_Connection"
0x10053f8b2  mov     r9d, 11h; int
0x10053f8b8  mov     r8, rbx; struct CDlgATTRs *
0x10053f8bb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f8c0  mov     rdx, rsi; unsigned __int16 *
0x10053f8c3  mov     rcx, r14; HWND
0x10053f8c6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f8cb  lea     rax, aFailoverPartne; "Failover_Partner"
0x10053f8d2  mov     r9d, 12h; int
0x10053f8d8  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f8dd  mov     r8, rbx; struct CDlgATTRs *
0x10053f8e0  mov     rdx, rsi; unsigned __int16 *
0x10053f8e3  mov     rcx, r14; HWND
0x10053f8e6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f8eb  lea     rax, aServerspn; "ServerSPN"
0x10053f8f2  mov     r9d, 1Dh; int
0x10053f8f8  mov     r8, rbx; struct CDlgATTRs *
0x10053f8fb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f900  mov     rdx, rsi; unsigned __int16 *
0x10053f903  mov     rcx, r14; HWND
0x10053f906  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f90b  lea     rax, aFailoverpartne; "FailoverPartnerSPN"
0x10053f912  mov     r9d, 1Eh; int
0x10053f918  mov     r8, rbx; struct CDlgATTRs *
0x10053f91b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f920  mov     rdx, rsi; unsigned __int16 *
0x10053f923  mov     rcx, r14; HWND
0x10053f926  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f92b  lea     rax, aApplicationint; "ApplicationIntent"
0x10053f932  mov     r9d, 1Fh; int
0x10053f938  mov     r8, rbx; struct CDlgATTRs *
0x10053f93b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f940  mov     rdx, rsi; unsigned __int16 *
0x10053f943  mov     rcx, r14; HWND
0x10053f946  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f94b  lea     rax, aMultisubnetfai; "MultiSubnetFailover"
0x10053f952  mov     r9d, 20h ; ' '; int
0x10053f958  mov     r8, rbx; struct CDlgATTRs *
0x10053f95b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f960  mov     rdx, rsi; unsigned __int16 *
0x10053f963  mov     rcx, r14; HWND
0x10053f966  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f96b  lea     rax, aConnectretryco; "ConnectRetryCount"
0x10053f972  mov     r9d, 21h ; '!'; int
0x10053f978  mov     r8, rbx; struct CDlgATTRs *
0x10053f97b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f980  mov     rdx, rsi; unsigned __int16 *
0x10053f983  mov     rcx, r14; HWND
0x10053f986  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f98b  lea     rax, aConnectretryin; "ConnectRetryInterval"
0x10053f992  mov     r9d, 22h ; '"'; int
0x10053f998  mov     r8, rbx; struct CDlgATTRs *
0x10053f99b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f9a0  mov     rdx, rsi; unsigned __int16 *
0x10053f9a3  mov     rcx, r14; HWND
0x10053f9a6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f9ab  lea     rax, aClientcertific; "ClientCertificate"
0x10053f9b2  mov     r9d, 23h ; '#'; int
0x10053f9b8  mov     r8, rbx; struct CDlgATTRs *
0x10053f9bb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f9c0  mov     rdx, rsi; unsigned __int16 *
0x10053f9c3  mov     rcx, r14; HWND
0x10053f9c6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f9cb  lea     rax, aColumnencrypti; "ColumnEncryption"
0x10053f9d2  mov     r9d, 24h ; '$'; int
0x10053f9d8  mov     r8, rbx; struct CDlgATTRs *
0x10053f9db  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053f9e0  mov     rdx, rsi; unsigned __int16 *
0x10053f9e3  mov     rcx, r14; HWND
0x10053f9e6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053f9eb  lea     rax, aTransparentnet; "TransparentNetworkIPResolution"
0x10053f9f2  mov     r9d, 25h ; '%'; int
0x10053f9f8  mov     r8, rbx; struct CDlgATTRs *
0x10053f9fb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fa00  mov     rdx, rsi; unsigned __int16 *
0x10053fa03  mov     rcx, r14; HWND
0x10053fa06  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fa0b  lea     rax, aKeystoreauthen; "KeystoreAuthentication"
0x10053fa12  mov     r9d, 27h ; '''; int
0x10053fa18  mov     r8, rbx; struct CDlgATTRs *
0x10053fa1b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fa20  mov     rdx, rsi; unsigned __int16 *
0x10053fa23  mov     rcx, r14; HWND
0x10053fa26  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fa2b  lea     rax, aKeystoreprinci; "KeystorePrincipalId"
0x10053fa32  mov     r9d, 28h ; '('; int
0x10053fa38  mov     r8, rbx; struct CDlgATTRs *
0x10053fa3b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fa40  mov     rdx, rsi; unsigned __int16 *
0x10053fa43  mov     rcx, r14; HWND
0x10053fa46  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fa4b  lea     rax, aKeystoresecret; "KeystoreSecret"
0x10053fa52  mov     r9d, 29h ; ')'; int
0x10053fa58  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fa5d  mov     r8, rbx; struct CDlgATTRs *
0x10053fa60  mov     rdx, rsi; unsigned __int16 *
0x10053fa63  mov     rcx, r14; HWND
0x10053fa66  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fa6b  lea     rax, aKeystorelocati; "KeystoreLocation"
0x10053fa72  mov     r9d, 2Ah ; '*'; int
0x10053fa78  mov     r8, rbx; struct CDlgATTRs *
0x10053fa7b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fa80  mov     rdx, rsi; unsigned __int16 *
0x10053fa83  mov     rcx, r14; HWND
0x10053fa86  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fa8b  lea     rax, aUsefmtonly; "UseFMTONLY"
0x10053fa92  mov     r9d, 2Bh ; '+'; int
0x10053fa98  mov     r8, rbx; struct CDlgATTRs *
0x10053fa9b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053faa0  mov     rdx, rsi; unsigned __int16 *
0x10053faa3  mov     rcx, r14; HWND
0x10053faa6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053faab  lea     rax, aKeepalive_0; "KeepAlive"
0x10053fab2  mov     r9d, 2Dh ; '-'; int
0x10053fab8  mov     r8, rbx; struct CDlgATTRs *
0x10053fabb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fac0  mov     rdx, rsi; unsigned __int16 *
0x10053fac3  mov     rcx, r14; HWND
0x10053fac6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053facb  lea     rax, aKeepaliveinter; "KeepAliveInterval"
0x10053fad2  mov     r9d, 2Eh ; '.'; int
0x10053fad8  mov     r8, rbx; struct CDlgATTRs *
0x10053fadb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fae0  mov     rdx, rsi; unsigned __int16 *
0x10053fae3  mov     rcx, r14; HWND
0x10053fae6  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053faeb  lea     rax, aLongasmax; "LongAsMax"
0x10053faf2  mov     r9d, 30h ; '0'; int
0x10053faf8  mov     r8, rbx; struct CDlgATTRs *
0x10053fafb  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fb00  mov     rdx, rsi; unsigned __int16 *
0x10053fb03  mov     rcx, r14; HWND
0x10053fb06  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fb0b  lea     rax, aHostnameincert; "HostNameInCertificate"
0x10053fb12  mov     r9d, 31h ; '1'; int
0x10053fb18  mov     r8, rbx; struct CDlgATTRs *
0x10053fb1b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fb20  mov     rdx, rsi; unsigned __int16 *
0x10053fb23  mov     rcx, r14; HWND
0x10053fb26  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fb2b  lea     rax, aGetdataextensi; "GetDataExtensions"
0x10053fb32  mov     r9d, 32h ; '2'; int
0x10053fb38  mov     r8, rbx; struct CDlgATTRs *
0x10053fb3b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fb40  mov     rdx, rsi; unsigned __int16 *
0x10053fb43  mov     rcx, r14; HWND
0x10053fb46  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fb4b  lea     rax, aIpaddressprefe; "IpAddressPreference"
0x10053fb52  mov     r9d, 33h ; '3'; int
0x10053fb58  mov     r8, rbx; struct CDlgATTRs *
0x10053fb5b  mov     [rsp+6A8h+pcchErrorMsg], rax; unsigned __int16 *
0x10053fb60  mov     rdx, rsi; unsigned __int16 *
0x10053fb63  mov     rcx, r14; HWND
0x10053fb66  call    ?WriteDSNAttribute@@YAXPEAUHWND__@@PEBGAEAVCDlgATTRs@@H1@Z; WriteDSNAttribute(HWND__ *,ushort const *,CDlgATTRs &,int,ushort const *)
0x10053fb6b  lea     rax, aServercertific; "ServerCertificate"
0x10053fb72  mov     r9d, 34h ; '4'; int
0x10053fb78  mov     r8, rbx; struct CDlgATTRs *
  ... truncated ...
```
