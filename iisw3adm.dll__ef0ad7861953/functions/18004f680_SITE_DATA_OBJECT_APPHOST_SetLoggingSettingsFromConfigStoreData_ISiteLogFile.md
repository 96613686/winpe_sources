# SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData(ISiteLogFile *)

- ea: `0x18004f680`
- end: `0x18004fde7`
- name: `?SetLoggingSettingsFromConfigStoreData@SITE_DATA_OBJECT_APPHOST@@QEAAJPEAUISiteLogFile@@@Z`
- size: `1895`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_APPHOST *__hidden this, struct ISiteLogFile *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e444`

## callees

- `0x18004f680`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004faef`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd7c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004faef`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd7c`
- `iisutil!PuDbgPrint` at `0x18004f786`
- `iisutil!PuDbgPrint` at `0x18004f815`
- `iisutil!PuDbgPrint` at `0x18004f897`
- `iisutil!PuDbgPrint` at `0x18004f919`
- `iisutil!PuDbgPrint` at `0x18004f9ae`
- `iisutil!PuDbgPrint` at `0x18004fa2b`
- `iisutil!PuDbgPrint` at `0x18004fab1`
- `iisutil!PuDbgPrint` at `0x18004fb6f`
- `iisutil!PuDbgPrint` at `0x18004fca0`
- `iisutil!PuDbgPrint` at `0x18004f786`
- `iisutil!PuDbgPrint` at `0x18004f815`
- `iisutil!PuDbgPrint` at `0x18004f897`
- `iisutil!PuDbgPrint` at `0x18004f919`
- `iisutil!PuDbgPrint` at `0x18004f9ae`
- `iisutil!PuDbgPrint` at `0x18004fa2b`
- `iisutil!PuDbgPrint` at `0x18004fab1`
- `iisutil!PuDbgPrint` at `0x18004fb6f`
- `iisutil!PuDbgPrint` at `0x18004fca0`
- `iisutil!PuDbgPrintError` at `0x18004f70a`
- `iisutil!PuDbgPrintError` at `0x18004f70a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004fac7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004fb90`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004fac7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004fb90`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004fbc2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004fbf0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004fbc2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004fbf0`

## string_xrefs

- `0x18004f6df`: ` Failed reading property \n`
- `0x18004f7be`: ` Failed reading property \n`
- `0x18004fa99`: ` Log File Directory '%S' \n`
- `0x18004fba9`: ` Failed copying in the { for the guid \n `
- `0x18004fc09`: ` Failed copying in the } for the guid \n `
- `0x18004f6f3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f727`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f6ec`: `SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData`
- `0x18004f71a`: `SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData(
        SITE_DATA_OBJECT_APPHOST *this,
        struct ISiteLogFile *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(struct ISiteLogFile *, __int16 *); // rax
  int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  int v9; // eax
  const wchar_t *v10; // r8
  BOOL v11; // edx
  const wchar_t *v12; // r13
  bool v13; // zf
  const wchar_t *v14; // rax
  int v15; // eax
  int v16; // edx
  bool v17; // cl
  int v18; // eax
  BOOL v19; // edx
  const wchar_t *v20; // r12
  const wchar_t *v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF
  __int16 v27; // [rsp+A8h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v29; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *(_QWORD *)a2;
  bstrString = 0;
  v27 = 0;
  v26 = 0;
  v5 = *(__int64 (__fastcall **)(struct ISiteLogFile *, __int16 *))(v2 + 112);
  v29 = 0;
  v24 = 0;
  v25 = 0;
  v6 = v5(a2, &v27);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_82;
    v7 = " Failed reading property \n";
    v8 = 340;
    goto LABEL_4;
  }
  v9 = g_dwDebugFlags;
  v10 = L"FALSE";
  v11 = v27 == -1;
  v12 = L"TRUE";
  v13 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 35) = v11;
  if ( !v13 && (v9 & 0x40000000) != 0 )
  {
    v14 = L"TRUE";
    if ( !v11 )
      v14 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
      349,
      "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
      " Log Enabled = %S \n ",
      v14);
  }
  v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, char *, const wchar_t *))(*(_QWORD *)a2 + 88LL))(
         a2,
         (char *)this + 144,
         v10);
  if ( v6 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
        367,
        "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
        " Log File Period = %u (0x%X) (%d) \n ",
        *((_DWORD *)this + 36),
        *((_DWORD *)this + 36),
        *((_DWORD *)this + 36));
    v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v26);
    if ( v6 >= 0 )
    {
      v15 = g_dwDebugFlags;
      v16 = v26;
      v17 = (g_dwDebugFlags & 3) != 0;
      *((_DWORD *)this + 37) = v26;
      if ( v17 && (v15 & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
          389,
          "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
          " Log File Trucate Size = %u (0x%X) (%d) \n ",
          v16,
          v16,
          v16);
      v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, char *))(*(_QWORD *)a2 + 56LL))(a2, (char *)this + 152);
      if ( v6 >= 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
            407,
            "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
            " Log Ext File Flags = %u (0x%X) (%d) \n ",
            *((_DWORD *)this + 38),
            *((_DWORD *)this + 38),
            *((_DWORD *)this + 38));
        v27 = 0;
        v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, __int16 *))(*(_QWORD *)a2 + 104LL))(a2, &v27);
        if ( v6 >= 0 )
        {
          v18 = g_dwDebugFlags;
          v19 = v27 == -1;
          v13 = (g_dwDebugFlags & 3) == 0;
          *((_DWORD *)this + 39) = v19;
          if ( !v13 && (v18 & 0x40000000) != 0 )
          {
            if ( !v19 )
              v12 = L"FALSE";
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
              425,
              "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
              " Localtime Rollover = %S \n ",
              v12);
          }
          v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, char *))(*(_QWORD *)a2 + 72LL))(a2, (char *)this + 160);
          if ( v6 >= 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
                441,
                "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
                " LogFormat = %d \n ",
                *((_DWORD *)this + 40));
            v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, BSTR *))(*(_QWORD *)a2 + 80LL))(a2, &bstrString);
            if ( v6 >= 0 )
            {
              v20 = L"NULL";
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              {
                v21 = L"NULL";
                if ( bstrString )
                  v21 = bstrString;
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
                  457,
                  "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
                  " Log File Directory '%S' \n",
                  v21);
              }
              if ( bstrString )
              {
                v6 = STRU::Copy((SITE_DATA_OBJECT_APPHOST *)((char *)this + 224), bstrString);
                if ( v6 < 0 )
                {
                  if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v8 = 467;
                    goto LABEL_12;
                  }
                  goto LABEL_82;
                }
                SysFreeString(bstrString);
                bstrString = 0;
              }
              v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, BSTR *))(*(_QWORD *)a2 + 64LL))(a2, &bstrString);
              if ( v6 >= 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                {
                  if ( bstrString )
                    v20 = bstrString;
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
                    488,
                    "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
                    " Logging Module '%S' \n",
                    v20);
                }
                if ( bstrString )
                {
                  v6 = STRU::Copy((SITE_DATA_OBJECT_APPHOST *)((char *)this + 168), L"{");
                  if ( v6 < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v7 = " Failed copying in the { for the guid \n ";
                      v8 = 498;
                      goto LABEL_4;
                    }
                    goto LABEL_82;
                  }
                  v6 = STRU::Append((SITE_DATA_OBJECT_APPHOST *)((char *)this + 168), bstrString);
                  if ( v6 < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v8 = 508;
                      goto LABEL_12;
                    }
                    goto LABEL_82;
                  }
                  v6 = STRU::Append((SITE_DATA_OBJECT_APPHOST *)((char *)this + 168), L"}");
                  if ( v6 < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v7 = " Failed copying in the } for the guid \n ";
                      v8 = 517;
                      goto LABEL_4;
                    }
                    goto LABEL_82;
                  }
                  SysFreeString(bstrString);
                  bstrString = 0;
                }
                v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, char *))(*(_QWORD *)a2 + 128LL))(
                       a2,
                       (char *)this + 280);
                if ( v6 >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
                      539,
                      "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
                      " LogTargetW3C = %d \n ",
                      *((_DWORD *)this + 70));
                  v6 = (*(__int64 (__fastcall **)(struct ISiteLogFile *, __int64 *))(*(_QWORD *)a2 + 152LL))(a2, &v29);
                  if ( v6 >= 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 64LL))(v29, &v24);
                    if ( v6 >= 0 )
                    {
                      while ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 56LL))(v24, &v25) >= 0 )
                      {
                        v22 = v25;
                        if ( !v25 )
                          break;
                        ++*((_DWORD *)this + 71);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                        v25 = 0;
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                      v24 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                      v29 = 0;
                    }
                    else if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      v7 = " Failed getting customFields enumerator \n";
                      v8 = 556;
                      goto LABEL_4;
                    }
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v8 = 547;
                    goto LABEL_12;
                  }
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v8 = 531;
                  goto LABEL_12;
                }
                goto LABEL_82;
              }
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v8 = 480;
                goto LABEL_12;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v8 = 449;
              goto LABEL_12;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v8 = 433;
            goto LABEL_12;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v8 = 416;
          goto LABEL_12;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v8 = 397;
        goto LABEL_12;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v8 = 375;
      goto LABEL_12;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v8 = 357;
LABEL_12:
    v7 = " Failed reading property \n";
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
      v8,
      "SITE_DATA_OBJECT_APPHOST::SetLoggingSettingsFromConfigStoreData",
      v6,
      v7);
  }
LABEL_82:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004f680  mov     [rsp-38h+arg_0], rbx
0x18004f685  push    rbp
0x18004f686  push    rsi
0x18004f687  push    rdi
0x18004f688  push    r12
0x18004f68a  push    r13
0x18004f68c  push    r14
0x18004f68e  push    r15
0x18004f690  mov     rbp, rsp
0x18004f693  sub     rsp, 60h
0x18004f697  mov     rax, [rdx]
0x18004f69a  xor     r13d, r13d
0x18004f69d  mov     r14, rdx
0x18004f6a0  mov     [rbp+bstrString], r13
0x18004f6a4  mov     r15, rcx
0x18004f6a7  mov     [rbp+arg_8], r13w
0x18004f6ac  lea     rdx, [rbp+arg_8]
0x18004f6b0  mov     [rbp+var_10], r13
0x18004f6b4  mov     rax, [rax+70h]
0x18004f6b8  mov     rcx, r14
0x18004f6bb  mov     [rbp+arg_18], r13
0x18004f6bf  mov     [rbp+var_20], r13
0x18004f6c3  mov     [rbp+var_18], r13
0x18004f6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6cc  mov     ebx, eax
0x18004f6ce  test    eax, eax
0x18004f6d0  jns     short loc_18004F715
0x18004f6d2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f6d9  jz      loc_18004FD71
0x18004f6df  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004f6e6  mov     r8d, 154h
0x18004f6ec  lea     r9, aSiteDataObject_3; "SITE_DATA_OBJECT_APPHOST::SetLoggingSet"...
0x18004f6f3  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f6fa  mov     rcx, cs:g_pDebug
0x18004f701  mov     [rsp+60h+var_38], rax
0x18004f706  mov     dword ptr [rsp+60h+var_40], ebx
0x18004f70a  call    cs:__imp_PuDbgPrintError
0x18004f710  jmp     loc_18004FD71
0x18004f715  cmp     [rbp+arg_8], 0FFFFh
0x18004f71a  lea     rdi, aSiteDataObject_3; "SITE_DATA_OBJECT_APPHOST::SetLoggingSet"...
0x18004f721  mov     eax, cs:g_dwDebugFlags
0x18004f727  lea     rsi, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f72e  mov     edx, r13d
0x18004f731  lea     r8, aFalse_1; "FALSE"
0x18004f738  setz    dl
0x18004f73b  lea     r13, aTrue_1; "TRUE"
0x18004f742  test    al, 3
0x18004f744  mov     [r15+8Ch], edx
0x18004f74b  setnz   cl
0x18004f74e  bt      eax, 1Eh
0x18004f752  setb    al
0x18004f755  test    al, cl
0x18004f757  jz      short loc_18004F78C
0x18004f759  mov     rcx, cs:g_pDebug
0x18004f760  test    edx, edx
0x18004f762  mov     rax, r13
0x18004f765  mov     r9, rdi
0x18004f768  cmovz   rax, r8
0x18004f76c  mov     rdx, rsi
0x18004f76f  mov     [rsp+60h+var_38], rax
0x18004f774  mov     r8d, 15Dh
0x18004f77a  lea     rax, aLogEnabledS; " Log Enabled = %S \n "
0x18004f781  mov     [rsp+60h+var_40], rax
0x18004f786  call    cs:__imp_PuDbgPrint
0x18004f78c  mov     rax, [r14]
0x18004f78f  lea     r12, [r15+90h]
0x18004f796  mov     rdx, r12
0x18004f799  mov     rcx, r14
0x18004f79c  mov     rax, [rax+58h]
0x18004f7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7a5  mov     ebx, eax
0x18004f7a7  test    eax, eax
0x18004f7a9  jns     short loc_18004F7D0
0x18004f7ab  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f7b2  jz      loc_18004FD71
0x18004f7b8  mov     r8d, 165h
0x18004f7be  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004f7c5  mov     r9, rdi
0x18004f7c8  mov     rdx, rsi
0x18004f7cb  jmp     loc_18004F6FA
0x18004f7d0  mov     eax, cs:g_dwDebugFlags
0x18004f7d6  test    al, 3
0x18004f7d8  setnz   cl
0x18004f7db  bt      eax, 1Eh
0x18004f7df  setb    al
0x18004f7e2  test    al, cl
0x18004f7e4  jz      short loc_18004F81B
0x18004f7e6  mov     eax, [r12]
0x18004f7ea  mov     r9, rdi
0x18004f7ed  mov     rcx, cs:g_pDebug
0x18004f7f4  mov     r8d, 16Fh
0x18004f7fa  mov     [rsp+60h+var_28], eax
0x18004f7fe  mov     rdx, rsi
0x18004f801  mov     [rsp+60h+var_30], eax
0x18004f805  mov     dword ptr [rsp+60h+var_38], eax
0x18004f809  lea     rax, aLogFilePeriodU; " Log File Period = %u (0x%X) (%d) \n "
0x18004f810  mov     [rsp+60h+var_40], rax
0x18004f815  call    cs:__imp_PuDbgPrint
0x18004f81b  mov     rax, [r14]
0x18004f81e  lea     rdx, [rbp+var_10]
0x18004f822  mov     rcx, r14
0x18004f825  mov     rax, [rax+60h]
0x18004f829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f82e  mov     ebx, eax
0x18004f830  test    eax, eax
0x18004f832  jns     short loc_18004F84C
0x18004f834  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f83b  jz      loc_18004FD71
0x18004f841  mov     r8d, 177h
0x18004f847  jmp     loc_18004F7BE
0x18004f84c  mov     eax, cs:g_dwDebugFlags
0x18004f852  test    al, 3
0x18004f854  mov     edx, dword ptr [rbp+var_10]
0x18004f857  setnz   cl
0x18004f85a  mov     [r15+94h], edx
0x18004f861  bt      eax, 1Eh
0x18004f865  setb    al
0x18004f868  test    al, cl
0x18004f86a  jz      short loc_18004F89D
0x18004f86c  mov     rcx, cs:g_pDebug
0x18004f873  lea     rax, aLogFileTrucate; " Log File Trucate Size = %u (0x%X) (%d)"...
0x18004f87a  mov     [rsp+60h+var_28], edx
0x18004f87e  mov     r9, rdi
0x18004f881  mov     [rsp+60h+var_30], edx
0x18004f885  mov     r8d, 185h
0x18004f88b  mov     dword ptr [rsp+60h+var_38], edx
0x18004f88f  mov     rdx, rsi
0x18004f892  mov     [rsp+60h+var_40], rax
0x18004f897  call    cs:__imp_PuDbgPrint
0x18004f89d  mov     rax, [r14]
0x18004f8a0  lea     r12, [r15+98h]
0x18004f8a7  mov     rdx, r12
0x18004f8aa  mov     rcx, r14
0x18004f8ad  mov     rax, [rax+38h]
0x18004f8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8b6  mov     ebx, eax
0x18004f8b8  test    eax, eax
0x18004f8ba  jns     short loc_18004F8D4
0x18004f8bc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f8c3  jz      loc_18004FD71
0x18004f8c9  mov     r8d, 18Dh
0x18004f8cf  jmp     loc_18004F7BE
0x18004f8d4  mov     eax, cs:g_dwDebugFlags
0x18004f8da  test    al, 3
0x18004f8dc  setnz   cl
0x18004f8df  bt      eax, 1Eh
0x18004f8e3  setb    al
0x18004f8e6  test    al, cl
0x18004f8e8  jz      short loc_18004F91F
0x18004f8ea  mov     eax, [r12]
0x18004f8ee  mov     r9, rdi
0x18004f8f1  mov     rcx, cs:g_pDebug
0x18004f8f8  mov     r8d, 197h
0x18004f8fe  mov     [rsp+60h+var_28], eax
0x18004f902  mov     rdx, rsi
0x18004f905  mov     [rsp+60h+var_30], eax
0x18004f909  mov     dword ptr [rsp+60h+var_38], eax
0x18004f90d  lea     rax, aLogExtFileFlag; " Log Ext File Flags = %u (0x%X) (%d) \n"...
0x18004f914  mov     [rsp+60h+var_40], rax
0x18004f919  call    cs:__imp_PuDbgPrint
0x18004f91f  xor     eax, eax
0x18004f921  lea     rdx, [rbp+arg_8]
0x18004f925  mov     [rbp+arg_8], ax
0x18004f929  mov     rcx, r14
0x18004f92c  mov     rax, [r14]
0x18004f92f  mov     rax, [rax+68h]
0x18004f933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f938  mov     ebx, eax
0x18004f93a  test    eax, eax
0x18004f93c  jns     short loc_18004F956
0x18004f93e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f945  jz      loc_18004FD71
0x18004f94b  mov     r8d, 1A0h
0x18004f951  jmp     loc_18004F7BE
0x18004f956  mov     eax, cs:g_dwDebugFlags
0x18004f95c  xor     edx, edx
0x18004f95e  cmp     [rbp+arg_8], 0FFFFh
0x18004f963  setz    dl
0x18004f966  test    al, 3
0x18004f968  mov     [r15+9Ch], edx
0x18004f96f  setnz   cl
0x18004f972  bt      eax, 1Eh
0x18004f976  setb    al
0x18004f979  test    al, cl
0x18004f97b  jz      short loc_18004F9B4
0x18004f97d  mov     rcx, cs:g_pDebug
0x18004f984  lea     rax, aFalse_1; "FALSE"
0x18004f98b  test    edx, edx
0x18004f98d  mov     r9, rdi
0x18004f990  mov     r8d, 1A9h
0x18004f996  mov     rdx, rsi
0x18004f999  cmovz   r13, rax
0x18004f99d  lea     rax, aLocaltimeRollo; " Localtime Rollover = %S \n "
0x18004f9a4  mov     [rsp+60h+var_38], r13
0x18004f9a9  mov     [rsp+60h+var_40], rax
0x18004f9ae  call    cs:__imp_PuDbgPrint
0x18004f9b4  mov     rax, [r14]
0x18004f9b7  lea     r12, [r15+0A0h]
0x18004f9be  mov     rdx, r12
0x18004f9c1  mov     rcx, r14
0x18004f9c4  mov     rax, [rax+48h]
0x18004f9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9cd  xor     r13d, r13d
0x18004f9d0  mov     ebx, eax
0x18004f9d2  test    eax, eax
0x18004f9d4  jns     short loc_18004F9EE
0x18004f9d6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f9dd  jz      loc_18004FD71
0x18004f9e3  mov     r8d, 1B1h
0x18004f9e9  jmp     loc_18004F7BE
0x18004f9ee  mov     eax, cs:g_dwDebugFlags
0x18004f9f4  test    al, 3
0x18004f9f6  setnz   cl
0x18004f9f9  bt      eax, 1Eh
0x18004f9fd  setb    al
0x18004fa00  test    al, cl
0x18004fa02  jz      short loc_18004FA31
0x18004fa04  mov     eax, [r12]
0x18004fa08  mov     r9, rdi
0x18004fa0b  mov     rcx, cs:g_pDebug
0x18004fa12  mov     r8d, 1B9h
0x18004fa18  mov     dword ptr [rsp+60h+var_38], eax
0x18004fa1c  mov     rdx, rsi
0x18004fa1f  lea     rax, aLogformatD; " LogFormat = %d \n "
0x18004fa26  mov     [rsp+60h+var_40], rax
0x18004fa2b  call    cs:__imp_PuDbgPrint
0x18004fa31  mov     rax, [r14]
0x18004fa34  lea     rdx, [rbp+bstrString]
0x18004fa38  mov     rcx, r14
0x18004fa3b  mov     rax, [rax+50h]
0x18004fa3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa44  mov     ebx, eax
0x18004fa46  test    eax, eax
0x18004fa48  jns     short loc_18004FA62
0x18004fa4a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004fa51  jz      loc_18004FD71
0x18004fa57  mov     r8d, 1C1h
0x18004fa5d  jmp     loc_18004F7BE
0x18004fa62  mov     eax, cs:g_dwDebugFlags
0x18004fa68  lea     r12, aNull_0; "NULL"
0x18004fa6f  test    al, 3
0x18004fa71  setnz   cl
0x18004fa74  bt      eax, 1Eh
0x18004fa78  setb    al
0x18004fa7b  test    al, cl
0x18004fa7d  jz      short loc_18004FAB7
0x18004fa7f  mov     rax, [rbp+bstrString]
0x18004fa83  mov     rcx, r12
0x18004fa86  test    rax, rax
0x18004fa89  mov     r9, rdi
0x18004fa8c  mov     r8d, 1C9h
0x18004fa92  mov     rdx, rsi
0x18004fa95  cmovnz  rcx, rax
0x18004fa99  lea     rax, aLogFileDirecto_0; " Log File Directory '%S' \n"
0x18004faa0  mov     [rsp+60h+var_38], rcx
0x18004faa5  mov     rcx, cs:g_pDebug
0x18004faac  mov     [rsp+60h+var_40], rax
0x18004fab1  call    cs:__imp_PuDbgPrint
0x18004fab7  mov     rdx, [rbp+bstrString]
0x18004fabb  test    rdx, rdx
0x18004fabe  jz      short loc_18004FAF9
0x18004fac0  lea     rcx, [r15+0E0h]
0x18004fac7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004facd  mov     ebx, eax
0x18004facf  test    eax, eax
0x18004fad1  jns     short loc_18004FAEB
0x18004fad3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004fada  jz      loc_18004FD71
0x18004fae0  mov     r8d, 1D3h
0x18004fae6  jmp     loc_18004F7BE
0x18004faeb  mov     rcx, [rbp+bstrString]; bstrString
0x18004faef  call    cs:__imp_SysFreeString
0x18004faf5  mov     [rbp+bstrString], r13
0x18004faf9  mov     rax, [r14]
0x18004fafc  lea     rdx, [rbp+bstrString]
0x18004fb00  mov     rcx, r14
0x18004fb03  mov     rax, [rax+40h]
0x18004fb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb0c  mov     ebx, eax
0x18004fb0e  test    eax, eax
0x18004fb10  jns     short loc_18004FB2A
0x18004fb12  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004fb19  jz      loc_18004FD71
0x18004fb1f  mov     r8d, 1E0h
0x18004fb25  jmp     loc_18004F7BE
0x18004fb2a  mov     eax, cs:g_dwDebugFlags
0x18004fb30  test    al, 3
0x18004fb32  setnz   cl
0x18004fb35  bt      eax, 1Eh
0x18004fb39  setb    al
0x18004fb3c  test    al, cl
0x18004fb3e  jz      short loc_18004FB75
0x18004fb40  mov     rax, [rbp+bstrString]
0x18004fb44  mov     r9, rdi
0x18004fb47  mov     rcx, cs:g_pDebug
0x18004fb4e  test    rax, rax
0x18004fb51  mov     r8d, 1E8h
0x18004fb57  mov     rdx, rsi
0x18004fb5a  cmovnz  r12, rax
0x18004fb5e  lea     rax, aLoggingModuleS; " Logging Module '%S' \n"
  ... truncated ...
```
