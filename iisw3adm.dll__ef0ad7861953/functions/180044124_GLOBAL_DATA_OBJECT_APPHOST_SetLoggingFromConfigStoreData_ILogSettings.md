# GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData(ILogSettings *)

- ea: `0x180044124`
- end: `0x180044907`
- name: `?SetLoggingFromConfigStoreData@GLOBAL_DATA_OBJECT_APPHOST@@QEAAJPEAUILogSettings@@@Z`
- size: `2019`
- prototype: `__int64 __fastcall(GLOBAL_DATA_OBJECT_APPHOST *__hidden this, struct ILogSettings *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043c80`

## callees

- `0x180044124`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800444df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800447df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800448e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800444df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800447df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800448e7`
- `iisutil!PuDbgPrint` at `0x1800441f8`
- `iisutil!PuDbgPrint` at `0x180044287`
- `iisutil!PuDbgPrint` at `0x180044315`
- `iisutil!PuDbgPrint` at `0x18004438f`
- `iisutil!PuDbgPrint` at `0x18004441d`
- `iisutil!PuDbgPrint` at `0x1800444a4`
- `iisutil!PuDbgPrint` at `0x180044584`
- `iisutil!PuDbgPrint` at `0x18004461e`
- `iisutil!PuDbgPrint` at `0x18004469b`
- `iisutil!PuDbgPrint` at `0x180044724`
- `iisutil!PuDbgPrint` at `0x1800447a1`
- `iisutil!PuDbgPrint` at `0x180044887`
- `iisutil!PuDbgPrint` at `0x1800441f8`
- `iisutil!PuDbgPrint` at `0x180044287`
- `iisutil!PuDbgPrint` at `0x180044315`
- `iisutil!PuDbgPrint` at `0x18004438f`
- `iisutil!PuDbgPrint` at `0x18004441d`
- `iisutil!PuDbgPrint` at `0x1800444a4`
- `iisutil!PuDbgPrint` at `0x180044584`
- `iisutil!PuDbgPrint` at `0x18004461e`
- `iisutil!PuDbgPrint` at `0x18004469b`
- `iisutil!PuDbgPrint` at `0x180044724`
- `iisutil!PuDbgPrint` at `0x1800447a1`
- `iisutil!PuDbgPrint` at `0x180044887`
- `iisutil!PuDbgPrintError` at `0x1800448d8`
- `iisutil!PuDbgPrintError` at `0x1800448d8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800444b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800447b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800444b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800447b7`

## string_xrefs

- `0x1800448c1`: ` Failed reading property \n`
- `0x18004448c`: ` Binary Log File Directory  = '%S' \n`
- `0x180044790`: ` W3C log File Directory  = '%S' \n`
- `0x18004418a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\globalstore_apphost.cxx`
- `0x1800441a5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\globalstore_apphost.cxx`
- `0x18004417d`: `GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData`
- `0x18004419c`: `GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData(
        GLOBAL_DATA_OBJECT_APPHOST *this,
        struct ILogSettings *a2)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  const wchar_t *v8; // rax
  int v9; // eax
  BOOL v10; // edx
  bool v11; // zf
  const wchar_t *v12; // rax
  int v13; // eax
  BOOL v14; // edx
  const wchar_t *v15; // rax
  int v16; // eax
  int v17; // edx
  const wchar_t *v18; // r13
  const wchar_t *v19; // rcx
  int v20; // eax
  BOOL v21; // edx
  const wchar_t *v22; // rax
  int v23; // eax
  BOOL v24; // edx
  const wchar_t *v25; // rax
  int v26; // eax
  int v27; // edx
  int v28; // eax
  BOOL v29; // edx
  const wchar_t *v30; // rax
  __int16 v32; // [rsp+80h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF
  __int64 v34; // [rsp+90h] [rbp+50h] BYREF

  bstrString = 0;
  v32 = 0;
  v3 = *(_QWORD *)a2;
  v34 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, char *))(v3 + 64))(a2, (char *)this + 64);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 197;
    goto LABEL_90;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v8 = L"TRUE";
    if ( !*((_DWORD *)this + 16) )
      v8 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      206,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Central logging mode  = %d \n",
      (_DWORD)v8);
  }
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int16 *))(*(_QWORD *)a2 + 56LL))(a2, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 214;
    goto LABEL_90;
  }
  v9 = g_dwDebugFlags;
  v10 = v32 == -1;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 19) = v10;
  if ( !v11 && (v9 & 0x40000000) != 0 )
  {
    v12 = L"TRUE";
    if ( !v10 )
      v12 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      224,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Log In utf 8  = %S \n",
      v12);
  }
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int16 *))(*(_QWORD *)a2 + 72LL))(a2, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 237;
    goto LABEL_90;
  }
  v13 = g_dwDebugFlags;
  v14 = v32 == -1;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 17) = v14;
  if ( !v11 && (v13 & 0x40000000) != 0 )
  {
    v15 = L"TRUE";
    if ( !v14 )
      v15 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      247,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Binary central logging enabled  = %S \n",
      v15);
  }
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, char *))(*(_QWORD *)a2 + 88LL))(a2, (char *)this + 136);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 255;
    goto LABEL_90;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      264,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Binary Log File Period = %u \n",
      *((_DWORD *)this + 34));
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v34);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 272;
    goto LABEL_90;
  }
  v16 = g_dwDebugFlags;
  v17 = v34;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 35) = v34;
  v34 = 0;
  if ( !v11 && (v16 & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      288,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Binary Log File Trucate Size = %u (0x%X) (%d) \n",
      v17,
      v17,
      v17);
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, BSTR *))(*(_QWORD *)a2 + 80LL))(a2, &bstrString);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 296;
    goto LABEL_90;
  }
  v18 = L"NULL";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v19 = L"NULL";
    if ( bstrString )
      v19 = bstrString;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      305,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Binary Log File Directory  = '%S' \n",
      v19);
  }
  if ( bstrString )
  {
    v5 = STRU::Copy((GLOBAL_DATA_OBJECT_APPHOST *)((char *)this + 80), bstrString);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_91;
      v7 = 315;
      goto LABEL_90;
    }
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int16 *))(*(_QWORD *)a2 + 104LL))(a2, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 328;
    goto LABEL_90;
  }
  v20 = g_dwDebugFlags;
  v21 = v32 == -1;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 36) = v21;
  if ( !v11 && (v20 & 0x40000000) != 0 )
  {
    v22 = L"TRUE";
    if ( !v21 )
      v22 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      338,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " Binary log local time rollover = %S \n",
      v22);
  }
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int16 *))(*(_QWORD *)a2 + 112LL))(a2, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 351;
    goto LABEL_90;
  }
  v23 = g_dwDebugFlags;
  v24 = v32 == -1;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 18) = v24;
  if ( !v11 && (v23 & 0x40000000) != 0 )
  {
    v25 = L"TRUE";
    if ( !v24 )
      v25 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      361,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " W3C central logging enabled  = %S \n",
      v25);
  }
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, char *))(*(_QWORD *)a2 + 128LL))(a2, (char *)this + 208);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 369;
    goto LABEL_90;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      378,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " W3C log File Period = %u \n",
      *((_DWORD *)this + 52));
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int64 *))(*(_QWORD *)a2 + 136LL))(a2, &v34);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 386;
    goto LABEL_90;
  }
  v26 = g_dwDebugFlags;
  v27 = v34;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 53) = v34;
  if ( !v11 && (v26 & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      401,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " W3C log File Trucate Size = %u (0x%X) (%d) \n",
      v27,
      v27,
      v27);
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, BSTR *))(*(_QWORD *)a2 + 120LL))(a2, &bstrString);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 409;
    goto LABEL_90;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    if ( bstrString )
      v18 = bstrString;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      418,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " W3C log File Directory  = '%S' \n",
      v18);
  }
  if ( bstrString )
  {
    v5 = STRU::Copy((GLOBAL_DATA_OBJECT_APPHOST *)((char *)this + 152), bstrString);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_91;
      v7 = 428;
      goto LABEL_90;
    }
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, __int16 *))(*(_QWORD *)a2 + 144LL))(a2, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_91;
    v7 = 441;
    goto LABEL_90;
  }
  v28 = g_dwDebugFlags;
  v29 = v32 == -1;
  v11 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 54) = v29;
  if ( !v11 && (v28 & 0x40000000) != 0 )
  {
    v30 = L"TRUE";
    if ( !v29 )
      v30 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      451,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      " W3C Log local time rollover = %S \n",
      v30);
  }
  v5 = (*(__int64 (__fastcall **)(struct ILogSettings *, char *))(*(_QWORD *)a2 + 152LL))(a2, (char *)this + 220);
  v6 = v5;
  if ( v5 < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = 459;
LABEL_90:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\globalstore_apphost.cxx",
      v7,
      "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingFromConfigStoreData",
      v5,
      " Failed reading property \n");
  }
LABEL_91:
  if ( bstrString )
    SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x180044124  mov     [rsp-38h+arg_18], rbx
0x180044129  push    rbp
0x18004412a  push    rsi
0x18004412b  push    rdi
0x18004412c  push    r12
0x18004412e  push    r13
0x180044130  push    r14
0x180044132  push    r15
0x180044134  mov     rbp, rsp
0x180044137  sub     rsp, 40h
0x18004413b  xor     eax, eax
0x18004413d  mov     [rbp+bstrString], 0
0x180044145  mov     [rbp+arg_0], ax
0x180044149  mov     r14, rdx
0x18004414c  mov     rax, [rdx]
0x18004414f  mov     r15, rcx
0x180044152  lea     rdx, [rcx+40h]
0x180044156  mov     [rbp+arg_10], 0
0x18004415e  mov     rcx, r14
0x180044161  mov     rax, [rax+40h]
0x180044165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004416a  mov     ebx, eax
0x18004416c  test    eax, eax
0x18004416e  jns     short loc_180044196
0x180044170  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180044177  jz      loc_1800448DE
0x18004417d  lea     r9, aGlobalDataObje_2; "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingF"...
0x180044184  mov     r8d, 0C5h
0x18004418a  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180044191  jmp     loc_1800448C1
0x180044196  mov     eax, cs:g_dwDebugFlags
0x18004419c  lea     rdi, aGlobalDataObje_2; "GLOBAL_DATA_OBJECT_APPHOST::SetLoggingF"...
0x1800441a3  test    al, 3
0x1800441a5  lea     rsi, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800441ac  lea     rdx, aFalse_1; "FALSE"
0x1800441b3  setnz   cl
0x1800441b6  lea     r13, aTrue_1; "TRUE"
0x1800441bd  bt      eax, 1Eh
0x1800441c1  setb    al
0x1800441c4  test    al, cl
0x1800441c6  jz      short loc_1800441FE
0x1800441c8  cmp     dword ptr [r15+40h], 0
0x1800441cd  mov     rax, r13
0x1800441d0  mov     rcx, cs:g_pDebug
0x1800441d7  mov     r9, rdi
0x1800441da  cmovz   rax, rdx
0x1800441de  mov     r8d, 0CEh
0x1800441e4  mov     [rsp+40h+var_18], rax
0x1800441e9  mov     rdx, rsi
0x1800441ec  lea     rax, aCentralLogging; " Central logging mode  = %d \n"
0x1800441f3  mov     [rsp+40h+var_20], rax
0x1800441f8  call    cs:__imp_PuDbgPrint
0x1800441fe  mov     rax, [r14]
0x180044201  lea     rdx, [rbp+arg_0]
0x180044205  mov     rcx, r14
0x180044208  mov     rax, [rax+38h]
0x18004420c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044211  mov     ebx, eax
0x180044213  test    eax, eax
0x180044215  jns     short loc_18004422F
0x180044217  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004421e  jz      loc_1800448DE
0x180044224  mov     r8d, 0D6h
0x18004422a  jmp     loc_1800448BB
0x18004422f  mov     eax, cs:g_dwDebugFlags
0x180044235  lea     r12, aFalse_1; "FALSE"
0x18004423c  xor     edx, edx
0x18004423e  cmp     [rbp+arg_0], 0FFFFh
0x180044243  setz    dl
0x180044246  test    al, 3
0x180044248  mov     [r15+4Ch], edx
0x18004424c  setnz   cl
0x18004424f  bt      eax, 1Eh
0x180044253  setb    al
0x180044256  test    al, cl
0x180044258  jz      short loc_18004428D
0x18004425a  mov     rcx, cs:g_pDebug
0x180044261  test    edx, edx
0x180044263  mov     rax, r13
0x180044266  mov     r9, rdi
0x180044269  cmovz   rax, r12
0x18004426d  mov     r8d, 0E0h
0x180044273  mov     [rsp+40h+var_18], rax
0x180044278  mov     rdx, rsi
0x18004427b  lea     rax, aLogInUtf8S; " Log In utf 8  = %S \n"
0x180044282  mov     [rsp+40h+var_20], rax
0x180044287  call    cs:__imp_PuDbgPrint
0x18004428d  xor     eax, eax
0x18004428f  lea     rdx, [rbp+arg_0]
0x180044293  mov     [rbp+arg_0], ax
0x180044297  mov     rcx, r14
0x18004429a  mov     rax, [r14]
0x18004429d  mov     rax, [rax+48h]
0x1800442a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442a6  mov     ebx, eax
0x1800442a8  test    eax, eax
0x1800442aa  jns     short loc_1800442C4
0x1800442ac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800442b3  jz      loc_1800448DE
0x1800442b9  mov     r8d, 0EDh
0x1800442bf  jmp     loc_1800448BB
0x1800442c4  mov     eax, cs:g_dwDebugFlags
0x1800442ca  xor     edx, edx
0x1800442cc  cmp     [rbp+arg_0], 0FFFFh
0x1800442d1  setz    dl
0x1800442d4  test    al, 3
0x1800442d6  mov     [r15+44h], edx
0x1800442da  setnz   cl
0x1800442dd  bt      eax, 1Eh
0x1800442e1  setb    al
0x1800442e4  test    al, cl
0x1800442e6  jz      short loc_18004431B
0x1800442e8  mov     rcx, cs:g_pDebug
0x1800442ef  test    edx, edx
0x1800442f1  mov     rax, r13
0x1800442f4  mov     r9, rdi
0x1800442f7  cmovz   rax, r12
0x1800442fb  mov     r8d, 0F7h
0x180044301  mov     [rsp+40h+var_18], rax
0x180044306  mov     rdx, rsi
0x180044309  lea     rax, aBinaryCentralL; " Binary central logging enabled  = %S "...
0x180044310  mov     [rsp+40h+var_20], rax
0x180044315  call    cs:__imp_PuDbgPrint
0x18004431b  mov     rax, [r14]
0x18004431e  lea     r12, [r15+88h]
0x180044325  mov     rdx, r12
0x180044328  mov     rcx, r14
0x18004432b  mov     rax, [rax+58h]
0x18004432f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044334  mov     ebx, eax
0x180044336  test    eax, eax
0x180044338  jns     short loc_180044352
0x18004433a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180044341  jz      loc_1800448DE
0x180044347  mov     r8d, 0FFh
0x18004434d  jmp     loc_1800448BB
0x180044352  mov     eax, cs:g_dwDebugFlags
0x180044358  test    al, 3
0x18004435a  setnz   cl
0x18004435d  bt      eax, 1Eh
0x180044361  setb    al
0x180044364  test    al, cl
0x180044366  jz      short loc_180044395
0x180044368  mov     eax, [r12]
0x18004436c  mov     r9, rdi
0x18004436f  mov     rcx, cs:g_pDebug
0x180044376  mov     r8d, 108h
0x18004437c  mov     dword ptr [rsp+40h+var_18], eax
0x180044380  mov     rdx, rsi
0x180044383  lea     rax, aBinaryLogFileP; " Binary Log File Period = %u \n"
0x18004438a  mov     [rsp+40h+var_20], rax
0x18004438f  call    cs:__imp_PuDbgPrint
0x180044395  mov     rax, [r14]
0x180044398  lea     rdx, [rbp+arg_10]
0x18004439c  mov     rcx, r14
0x18004439f  mov     rax, [rax+60h]
0x1800443a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443a8  mov     ebx, eax
0x1800443aa  test    eax, eax
0x1800443ac  jns     short loc_1800443C6
0x1800443ae  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800443b5  jz      loc_1800448DE
0x1800443bb  mov     r8d, 110h
0x1800443c1  jmp     loc_1800448BB
0x1800443c6  mov     eax, cs:g_dwDebugFlags
0x1800443cc  mov     r12b, 3
0x1800443cf  mov     edx, dword ptr [rbp+arg_10]
0x1800443d2  test    r12b, al
0x1800443d5  mov     [r15+8Ch], edx
0x1800443dc  setnz   cl
0x1800443df  mov     [rbp+arg_10], 0
0x1800443e7  bt      eax, 1Eh
0x1800443eb  setb    al
0x1800443ee  test    al, cl
0x1800443f0  jz      short loc_180044423
0x1800443f2  mov     rcx, cs:g_pDebug
0x1800443f9  lea     rax, aBinaryLogFileT; " Binary Log File Trucate Size = %u (0x%"...
0x180044400  mov     [rsp+40h+var_8], edx
0x180044404  mov     r9, rdi
0x180044407  mov     [rsp+40h+var_10], edx
0x18004440b  mov     r8d, 120h
0x180044411  mov     dword ptr [rsp+40h+var_18], edx
0x180044415  mov     rdx, rsi
0x180044418  mov     [rsp+40h+var_20], rax
0x18004441d  call    cs:__imp_PuDbgPrint
0x180044423  mov     rax, [r14]
0x180044426  lea     rdx, [rbp+bstrString]
0x18004442a  mov     rcx, r14
0x18004442d  mov     rax, [rax+50h]
0x180044431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044436  mov     ebx, eax
0x180044438  test    eax, eax
0x18004443a  jns     short loc_180044454
0x18004443c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180044443  jz      loc_1800448DE
0x180044449  mov     r8d, 128h
0x18004444f  jmp     loc_1800448BB
0x180044454  mov     eax, cs:g_dwDebugFlags
0x18004445a  lea     r13, aNull_0; "NULL"
0x180044461  test    r12b, al
0x180044464  setnz   cl
0x180044467  bt      eax, 1Eh
0x18004446b  setb    al
0x18004446e  test    al, cl
0x180044470  jz      short loc_1800444AA
0x180044472  mov     rax, [rbp+bstrString]
0x180044476  mov     rcx, r13
0x180044479  test    rax, rax
0x18004447c  mov     r9, rdi
0x18004447f  mov     r8d, 131h
0x180044485  mov     rdx, rsi
0x180044488  cmovnz  rcx, rax
0x18004448c  lea     rax, aBinaryLogFileD; " Binary Log File Directory  = '%S' \n"
0x180044493  mov     [rsp+40h+var_18], rcx
0x180044498  mov     rcx, cs:g_pDebug
0x18004449f  mov     [rsp+40h+var_20], rax
0x1800444a4  call    cs:__imp_PuDbgPrint
0x1800444aa  mov     rdx, [rbp+bstrString]
0x1800444ae  test    rdx, rdx
0x1800444b1  jz      short loc_1800444ED
0x1800444b3  lea     rcx, [r15+50h]
0x1800444b7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800444bd  mov     ebx, eax
0x1800444bf  test    eax, eax
0x1800444c1  jns     short loc_1800444DB
0x1800444c3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800444ca  jz      loc_1800448DE
0x1800444d0  mov     r8d, 13Bh
0x1800444d6  jmp     loc_1800448BB
0x1800444db  mov     rcx, [rbp+bstrString]; bstrString
0x1800444df  call    cs:__imp_SysFreeString
0x1800444e5  mov     [rbp+bstrString], 0
0x1800444ed  xor     eax, eax
0x1800444ef  lea     rdx, [rbp+arg_0]
0x1800444f3  mov     [rbp+arg_0], ax
0x1800444f7  mov     rcx, r14
0x1800444fa  mov     rax, [r14]
0x1800444fd  mov     rax, [rax+68h]
0x180044501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044506  mov     ebx, eax
0x180044508  test    eax, eax
0x18004450a  jns     short loc_180044524
0x18004450c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180044513  jz      loc_1800448DE
0x180044519  mov     r8d, 148h
0x18004451f  jmp     loc_1800448BB
0x180044524  mov     eax, cs:g_dwDebugFlags
0x18004452a  xor     edx, edx
0x18004452c  cmp     [rbp+arg_0], 0FFFFh
0x180044531  setz    dl
0x180044534  test    r12b, al
0x180044537  mov     [r15+90h], edx
0x18004453e  setnz   cl
0x180044541  bt      eax, 1Eh
0x180044545  setb    al
0x180044548  test    al, cl
0x18004454a  jz      short loc_18004458A
0x18004454c  test    edx, edx
0x18004454e  lea     rcx, aFalse_1; "FALSE"
0x180044555  lea     rax, aTrue_1; "TRUE"
0x18004455c  mov     r9, rdi
0x18004455f  cmovz   rax, rcx
0x180044563  mov     r8d, 152h
0x180044569  mov     rcx, cs:g_pDebug
0x180044570  mov     rdx, rsi
0x180044573  mov     [rsp+40h+var_18], rax
0x180044578  lea     rax, aBinaryLogLocal; " Binary log local time rollover = %S \n"
0x18004457f  mov     [rsp+40h+var_20], rax
0x180044584  call    cs:__imp_PuDbgPrint
0x18004458a  xor     eax, eax
0x18004458c  lea     rdx, [rbp+arg_0]
0x180044590  mov     [rbp+arg_0], ax
0x180044594  mov     rcx, r14
0x180044597  mov     rax, [r14]
0x18004459a  mov     rax, [rax+70h]
0x18004459e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445a3  mov     ebx, eax
0x1800445a5  test    eax, eax
0x1800445a7  jns     short loc_1800445C1
0x1800445a9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800445b0  jz      loc_1800448DE
0x1800445b6  mov     r8d, 15Fh
0x1800445bc  jmp     loc_1800448BB
0x1800445c1  mov     eax, cs:g_dwDebugFlags
0x1800445c7  xor     edx, edx
0x1800445c9  cmp     [rbp+arg_0], 0FFFFh
0x1800445ce  setz    dl
0x1800445d1  test    r12b, al
0x1800445d4  mov     [r15+48h], edx
0x1800445d8  setnz   cl
0x1800445db  bt      eax, 1Eh
0x1800445df  setb    al
0x1800445e2  test    al, cl
0x1800445e4  jz      short loc_180044624
0x1800445e6  test    edx, edx
0x1800445e8  lea     rcx, aFalse_1; "FALSE"
0x1800445ef  lea     rax, aTrue_1; "TRUE"
0x1800445f6  mov     r9, rdi
0x1800445f9  cmovz   rax, rcx
0x1800445fd  mov     r8d, 169h
  ... truncated ...
```
