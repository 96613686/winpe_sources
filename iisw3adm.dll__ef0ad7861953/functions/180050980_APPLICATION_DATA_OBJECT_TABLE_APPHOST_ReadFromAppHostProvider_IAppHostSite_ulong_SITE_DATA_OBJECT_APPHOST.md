# APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider(IAppHostSite *,ulong,SITE_DATA_OBJECT_APPHOST *)

- ea: `0x180050980`
- end: `0x180050e61`
- name: `?ReadFromAppHostProvider@APPLICATION_DATA_OBJECT_TABLE_APPHOST@@UEAAJPEAUIAppHostSite@@KPEAVSITE_DATA_OBJECT_APPHOST@@@Z`
- size: `1249`
- prototype: `int(APPLICATION_DATA_OBJECT_TABLE_APPHOST *__hidden this, struct IAppHostSite *, unsigned int, struct SITE_DATA_OBJECT_APPHOST *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001234`
- `0x180039938`
- `0x18003a8d8`
- `0x18003ac14`
- `0x18003ac88`
- `0x180050980`
- `0x18006101a`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180050b2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180050b97`
- `OLEAUT32!__imp_SysFreeString` at `0x180050c86`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ccd`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ce4`
- `OLEAUT32!__imp_SysFreeString` at `0x180050b2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180050b97`
- `OLEAUT32!__imp_SysFreeString` at `0x180050c86`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ccd`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ce4`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180050d19`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180050d19`
- `iisutil!PuDbgPrint` at `0x180050aac`
- `iisutil!PuDbgPrint` at `0x180050c5a`
- `iisutil!PuDbgPrint` at `0x180050aac`
- `iisutil!PuDbgPrint` at `0x180050c5a`
- `iisutil!PuDbgPrintError` at `0x180050a05`
- `iisutil!PuDbgPrintError` at `0x180050b88`
- `iisutil!PuDbgPrintError` at `0x180050bff`
- `iisutil!PuDbgPrintError` at `0x180050db2`
- `iisutil!PuDbgPrintError` at `0x180050a05`
- `iisutil!PuDbgPrintError` at `0x180050b88`
- `iisutil!PuDbgPrintError` at `0x180050bff`
- `iisutil!PuDbgPrintError` at `0x180050db2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050c68`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050ca2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050c68`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050ca2`

## string_xrefs

- `0x180050b68`: ` Failed reading property \n`
- `0x180050bd8`: ` Failed getting enabled protocols attribute \n`
- `0x180050cb7`: ` Failed to copy the protocol list \n `
- `0x180050dea`: ` Failed to get the path of the app \n`
- `0x180050a94`: ` App Path '%S' \n `
- `0x180050d92`: ` Failed to setup enabled protocols for application \n`
- `0x180050b74`: `APPLICATION_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x180050c2e`: `APPLICATION_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x1800509e7`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\applicationstore_apphost.cxx`
- `0x180050a10`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\applicationstore_apphost.cxx`
- `0x180050bec`: `APPLICATION_DATA_OBJECT_APPHOST::SetEnabledProtocols`
- `0x1800509f5`: `APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`
- `0x180050a80`: `APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`
- `0x180050d9e`: `APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider`

## pseudocode

```c
__int64 __fastcall APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider(
        APPLICATION_DATA_OBJECT_TABLE_APPHOST *this,
        struct IAppHostSite *a2,
        unsigned int a3,
        struct SITE_DATA_OBJECT_APPHOST *a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v6)(struct IAppHostSite *, __int64 *); // rax
  int FakeAppRoot; // edi
  const wchar_t *v10; // rcx
  char *v11; // rax
  char *v12; // rbx
  OLECHAR *v13; // rcx
  const wchar_t *v14; // rcx
  OLECHAR *v15; // rcx
  int inserted; // eax
  bool v17; // zf
  BSTR v19; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+40h] [rbp-10h] BYREF
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF

  v4 = *(_QWORD *)a2;
  v21 = 0;
  v22 = 0;
  v6 = *(__int64 (__fastcall **)(struct IAppHostSite *, __int64 *))(v4 + 112);
  bstrString = 0;
  FakeAppRoot = v6(a2, &v21);
  if ( FakeAppRoot < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
        244,
        "APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
        FakeAppRoot,
        " Failed to get apps collection \n",
        v19);
    goto LABEL_52;
  }
  while ( 1 )
  {
    FakeAppRoot = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 56LL))(v21, &v22);
    if ( FakeAppRoot < 0 || !v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
      goto LABEL_52;
    }
    FakeAppRoot = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 56LL))(v22, &bstrString);
    if ( FakeAppRoot < 0 )
      break;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      v10 = L"NULL";
      if ( bstrString )
        v10 = bstrString;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
        276,
        "APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
        " App Path '%S' \n ",
        v10);
    }
    v11 = (char *)operator new(0x168u);
    v12 = v11;
    if ( !v11 )
    {
      FakeAppRoot = -2147024888;
      goto LABEL_52;
    }
    memset_0(v11, 0, 0x168u);
    APPLICATION_DATA_OBJECT::APPLICATION_DATA_OBJECT((APPLICATION_DATA_OBJECT *)v12);
    *(_QWORD *)v12 = &APPLICATION_DATA_OBJECT_CS::`vftable';
    FakeAppRoot = APPLICATION_DATA_OBJECT::Create((APPLICATION_DATA_OBJECT *)v12, bstrString, a3);
    if ( FakeAppRoot < 0 )
      goto LABEL_46;
    FakeAppRoot = CreateFakeAppRoot(
                    *((_DWORD *)v12 + 26),
                    *((const unsigned __int16 **)v12 + 10),
                    (struct STRU *)(v12 + 176));
    if ( FakeAppRoot < 0 )
      goto LABEL_46;
    *((_QWORD *)v12 + 37) = 0;
    SysFreeString(bstrString);
    bstrString = 0;
    v19 = 0;
    FakeAppRoot = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 64LL))(v22, &v19);
    if ( FakeAppRoot < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
          96,
          "APPLICATION_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
          FakeAppRoot,
          " Failed reading property \n");
LABEL_17:
      v13 = v19;
      goto LABEL_18;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    {
      v14 = L"NULL";
      if ( v19 )
        v14 = v19;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
        104,
        "APPLICATION_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
        " App Pool Name '%S' \n",
        v14);
    }
    FakeAppRoot = STRU::Copy((STRU *)(v12 + 120), v19);
    if ( FakeAppRoot < 0 )
      goto LABEL_17;
    v15 = v19;
    *((_DWORD *)v12 + 75) = 0;
    SysFreeString(v15);
    v13 = 0;
    v19 = 0;
LABEL_18:
    if ( v13 )
      SysFreeString(v13);
    if ( FakeAppRoot < 0 )
      goto LABEL_46;
    v19 = 0;
    FakeAppRoot = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 72LL))(v22, &v19);
    if ( FakeAppRoot >= 0 )
    {
      FakeAppRoot = STRU::Copy((STRU *)(v12 + 232), v19);
      if ( FakeAppRoot >= 0 )
      {
        SysFreeString(v19);
        v19 = 0;
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
          177,
          "APPLICATION_DATA_OBJECT_APPHOST::SetEnabledProtocols",
          FakeAppRoot,
          " Failed to copy the protocol list \n ");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
        168,
        "APPLICATION_DATA_OBJECT_APPHOST::SetEnabledProtocols",
        FakeAppRoot,
        " Failed getting enabled protocols attribute \n");
    }
    if ( v19 )
    {
      SysFreeString(v19);
      v19 = 0;
    }
    if ( FakeAppRoot < 0 )
    {
      v17 = (g_dwDebugFlags & 0xF) == 0;
      **((_WORD **)v12 + 33) = 0;
      *((_DWORD *)v12 + 70) = 0;
      if ( !v17 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
          317,
          "APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
          FakeAppRoot,
          " Failed to setup enabled protocols for application \n");
      goto LABEL_46;
    }
    FakeAppRoot = SITE_DATA_OBJECT::AddAppPoolName(a4, *((const unsigned __int16 **)v12 + 19));
    if ( FakeAppRoot < 0 )
      goto LABEL_46;
    inserted = CLKRHashTable::InsertRecord((char *)this + 8, v12, 0);
    FakeAppRoot = inserted;
    if ( (unsigned int)inserted > 1 )
    {
      if ( inserted > 0 )
        FakeAppRoot = (unsigned __int16)inserted | 0x80070000;
LABEL_46:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 3, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(void *, __int64))v12)(v12, 1);
      goto LABEL_52;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 3, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(void *, __int64))v12)(v12, 1);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\applicationstore_apphost.cxx",
      267,
      "APPLICATION_DATA_OBJECT_TABLE_APPHOST::ReadFromAppHostProvider",
      FakeAppRoot,
      " Failed to get the path of the app \n",
      v19);
LABEL_52:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)FakeAppRoot;
}

```

## disassembly

```asm
0x180050980  mov     [rsp-28h+arg_0], rbx
0x180050985  mov     [rsp-28h+arg_10], rdi
0x18005098a  push    rbp
0x18005098b  push    r12
0x18005098d  push    r13
0x18005098f  push    r14
0x180050991  push    r15
0x180050993  mov     rbp, rsp
0x180050996  sub     rsp, 50h
0x18005099a  mov     rax, [rdx]
0x18005099d  mov     r10, rdx
0x1800509a0  xor     ebx, ebx
0x1800509a2  lea     rdx, [rbp+var_10]
0x1800509a6  mov     r13, rcx
0x1800509a9  mov     [rbp+var_10], rbx
0x1800509ad  mov     rcx, r10
0x1800509b0  mov     [rbp+arg_8], rbx
0x1800509b4  mov     rax, [rax+70h]
0x1800509b8  mov     r15, r9
0x1800509bb  mov     r12d, r8d
0x1800509be  mov     [rbp+bstrString], rbx
0x1800509c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509c7  mov     edi, eax
0x1800509c9  test    eax, eax
0x1800509cb  jns     short loc_180050A10
0x1800509cd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800509d4  jz      loc_180050E13
0x1800509da  lea     rax, aFailedToGetApp_2; " Failed to get apps collection \n"
0x1800509e1  mov     r8d, 0F4h
0x1800509e7  lea     rdx, aServercommonIn_51; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800509ee  mov     rcx, cs:g_pDebug
0x1800509f5  lea     r9, aApplicationDat_1; "APPLICATION_DATA_OBJECT_TABLE_APPHOST::"...
0x1800509fc  mov     [rsp+50h+var_28], rax
0x180050a01  mov     dword ptr [rsp+50h+var_30], edi
0x180050a05  call    cs:__imp_PuDbgPrintError
0x180050a0b  jmp     loc_180050E13
0x180050a10  lea     r14, aServercommonIn_51; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180050a17  mov     rcx, [rbp+var_10]
0x180050a1b  lea     rdx, [rbp+arg_8]
0x180050a1f  mov     rax, [rcx]
0x180050a22  mov     rax, [rax+38h]
0x180050a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a2b  mov     edi, eax
0x180050a2d  test    eax, eax
0x180050a2f  js      loc_180050DFF
0x180050a35  mov     rcx, [rbp+arg_8]
0x180050a39  test    rcx, rcx
0x180050a3c  jz      loc_180050DFF
0x180050a42  mov     rax, [rcx]
0x180050a45  lea     rdx, [rbp+bstrString]
0x180050a49  mov     rax, [rax+38h]
0x180050a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a52  mov     edi, eax
0x180050a54  test    eax, eax
0x180050a56  js      loc_180050DE1
0x180050a5c  mov     eax, cs:g_dwDebugFlags
0x180050a62  test    al, 3
0x180050a64  setnz   cl
0x180050a67  bt      eax, 1Eh
0x180050a6b  setb    al
0x180050a6e  test    al, cl
0x180050a70  jz      short loc_180050AB2
0x180050a72  mov     rax, [rbp+bstrString]
0x180050a76  lea     rcx, aNull_0; "NULL"
0x180050a7d  test    rax, rax
0x180050a80  lea     r9, aApplicationDat_1; "APPLICATION_DATA_OBJECT_TABLE_APPHOST::"...
0x180050a87  mov     r8d, 114h
0x180050a8d  mov     rdx, r14
0x180050a90  cmovnz  rcx, rax
0x180050a94  lea     rax, aAppPathS; " App Path '%S' \n "
0x180050a9b  mov     [rsp+50h+var_28], rcx
0x180050aa0  mov     rcx, cs:g_pDebug
0x180050aa7  mov     [rsp+50h+var_30], rax
0x180050aac  call    cs:__imp_PuDbgPrint
0x180050ab2  mov     edi, 168h
0x180050ab7  mov     ecx, edi; Size
0x180050ab9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050abe  mov     rbx, rax
0x180050ac1  test    rax, rax
0x180050ac4  jz      loc_180050DDA
0x180050aca  mov     r8d, edi; Size
0x180050acd  xor     edx, edx; Val
0x180050acf  mov     rcx, rax; void *
0x180050ad2  call    memset_0
0x180050ad7  mov     rcx, rbx; this
0x180050ada  call    ??0APPLICATION_DATA_OBJECT@@QEAA@XZ; APPLICATION_DATA_OBJECT::APPLICATION_DATA_OBJECT(void)
0x180050adf  lea     rax, ??_7APPLICATION_DATA_OBJECT_CS@@6B@; const APPLICATION_DATA_OBJECT_CS::`vftable'
0x180050ae6  mov     r8d, r12d; unsigned int
0x180050ae9  mov     [rbx], rax
0x180050aec  mov     rcx, rbx; this
0x180050aef  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180050af3  call    ?Create@APPLICATION_DATA_OBJECT@@QEAAJPEBGK@Z; APPLICATION_DATA_OBJECT::Create(ushort const *,ulong)
0x180050af8  mov     edi, eax
0x180050afa  test    eax, eax
0x180050afc  js      loc_180050DB8
0x180050b02  mov     rdx, [rbx+50h]; unsigned __int16 *
0x180050b06  lea     r8, [rbx+0B0h]; struct STRU *
0x180050b0d  mov     ecx, [rbx+68h]; Value
0x180050b10  call    ?CreateFakeAppRoot@@YAJKPEBGPEAVSTRU@@@Z; CreateFakeAppRoot(ulong,ushort const *,STRU *)
0x180050b15  mov     edi, eax
0x180050b17  test    eax, eax
0x180050b19  js      loc_180050DB8
0x180050b1f  xor     edi, edi
0x180050b21  mov     [rbx+128h], rdi
0x180050b28  mov     rcx, [rbp+bstrString]; bstrString
0x180050b2c  call    cs:__imp_SysFreeString
0x180050b32  mov     rcx, [rbp+arg_8]
0x180050b36  lea     rdx, [rbp+var_20]
0x180050b3a  mov     [rbp+bstrString], rdi
0x180050b3e  mov     [rbp+var_20], rdi
0x180050b42  mov     rax, [rcx]
0x180050b45  mov     rax, [rax+40h]
0x180050b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b4e  mov     edi, eax
0x180050b50  test    eax, eax
0x180050b52  jns     loc_180050C0A
0x180050b58  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050b5f  jz      short loc_180050B8E
0x180050b61  mov     rcx, cs:g_pDebug
0x180050b68  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180050b6f  mov     [rsp+50h+var_28], rax
0x180050b74  lea     r9, aApplicationDat_2; "APPLICATION_DATA_OBJECT_APPHOST::SetGen"...
0x180050b7b  mov     r8d, 60h ; '`'
0x180050b81  mov     dword ptr [rsp+50h+var_30], edi
0x180050b85  mov     rdx, r14
0x180050b88  call    cs:__imp_PuDbgPrintError
0x180050b8e  mov     rcx, [rbp+var_20]; bstrString
0x180050b92  test    rcx, rcx
0x180050b95  jz      short loc_180050B9D
0x180050b97  call    cs:__imp_SysFreeString
0x180050b9d  test    edi, edi
0x180050b9f  js      loc_180050DB8
0x180050ba5  mov     rcx, [rbp+arg_8]
0x180050ba9  lea     rdx, [rbp+var_20]
0x180050bad  mov     [rbp+var_20], 0
0x180050bb5  mov     rax, [rcx]
0x180050bb8  mov     rax, [rax+48h]
0x180050bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bc1  mov     edi, eax
0x180050bc3  test    eax, eax
0x180050bc5  jns     loc_180050C97
0x180050bcb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050bd2  jz      loc_180050CDB
0x180050bd8  lea     rax, aFailedGettingE; " Failed getting enabled protocols attri"...
0x180050bdf  mov     r8d, 0A8h
0x180050be5  mov     rcx, cs:g_pDebug
0x180050bec  lea     r9, aApplicationDat_3; "APPLICATION_DATA_OBJECT_APPHOST::SetEna"...
0x180050bf3  mov     [rsp+50h+var_28], rax
0x180050bf8  mov     rdx, r14
0x180050bfb  mov     dword ptr [rsp+50h+var_30], edi
0x180050bff  call    cs:__imp_PuDbgPrintError
0x180050c05  jmp     loc_180050CDB
0x180050c0a  mov     eax, cs:g_dwDebugFlags
0x180050c10  test    al, 3
0x180050c12  setnz   cl
0x180050c15  bt      eax, 1Eh
0x180050c19  setb    al
0x180050c1c  test    al, cl
0x180050c1e  jz      short loc_180050C60
0x180050c20  mov     rax, [rbp+var_20]
0x180050c24  lea     rcx, aNull_0; "NULL"
0x180050c2b  test    rax, rax
0x180050c2e  lea     r9, aApplicationDat_2; "APPLICATION_DATA_OBJECT_APPHOST::SetGen"...
0x180050c35  mov     r8d, 68h ; 'h'
0x180050c3b  mov     rdx, r14
0x180050c3e  cmovnz  rcx, rax
0x180050c42  lea     rax, aAppPoolNameS; " App Pool Name '%S' \n"
0x180050c49  mov     [rsp+50h+var_28], rcx
0x180050c4e  mov     rcx, cs:g_pDebug
0x180050c55  mov     [rsp+50h+var_30], rax
0x180050c5a  call    cs:__imp_PuDbgPrint
0x180050c60  mov     rdx, [rbp+var_20]
0x180050c64  lea     rcx, [rbx+78h]
0x180050c68  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180050c6e  mov     edi, eax
0x180050c70  test    eax, eax
0x180050c72  js      loc_180050B8E
0x180050c78  mov     rcx, [rbp+var_20]; bstrString
0x180050c7c  mov     dword ptr [rbx+12Ch], 0
0x180050c86  call    cs:__imp_SysFreeString
0x180050c8c  xor     ecx, ecx
0x180050c8e  mov     [rbp+var_20], rcx
0x180050c92  jmp     loc_180050B92
0x180050c97  mov     rdx, [rbp+var_20]
0x180050c9b  lea     rcx, [rbx+0E8h]
0x180050ca2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180050ca8  mov     edi, eax
0x180050caa  test    eax, eax
0x180050cac  jns     short loc_180050CC9
0x180050cae  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050cb5  jz      short loc_180050CDB
0x180050cb7  lea     rax, aFailedToCopyTh_0; " Failed to copy the protocol list \n "
0x180050cbe  mov     r8d, 0B1h
0x180050cc4  jmp     loc_180050BE5
0x180050cc9  mov     rcx, [rbp+var_20]; bstrString
0x180050ccd  call    cs:__imp_SysFreeString
0x180050cd3  mov     [rbp+var_20], 0
0x180050cdb  mov     rcx, [rbp+var_20]; bstrString
0x180050cdf  test    rcx, rcx
0x180050ce2  jz      short loc_180050CF2
0x180050ce4  call    cs:__imp_SysFreeString
0x180050cea  mov     [rbp+var_20], 0
0x180050cf2  test    edi, edi
0x180050cf4  js      short loc_180050D70
0x180050cf6  mov     rdx, [rbx+98h]; unsigned __int16 *
0x180050cfd  mov     rcx, r15; this
0x180050d00  call    ?AddAppPoolName@SITE_DATA_OBJECT@@QEAAJPEBG@Z; SITE_DATA_OBJECT::AddAppPoolName(ushort const *)
0x180050d05  mov     edi, eax
0x180050d07  test    eax, eax
0x180050d09  js      loc_180050DB8
0x180050d0f  lea     rcx, [r13+8]
0x180050d13  xor     r8d, r8d
0x180050d16  mov     rdx, rbx
0x180050d19  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180050d1f  mov     edi, eax
0x180050d21  cmp     eax, 1
0x180050d24  ja      short loc_180050D61
0x180050d26  or      eax, 0FFFFFFFFh
0x180050d29  lock xadd [rbx+0Ch], eax
0x180050d2e  cmp     eax, 1
0x180050d31  jnz     short loc_180050D46
0x180050d33  mov     rax, [rbx]
0x180050d36  mov     edx, 1
0x180050d3b  mov     rcx, rbx
0x180050d3e  mov     rax, [rax]
0x180050d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d46  mov     rcx, [rbp+arg_8]
0x180050d4a  mov     rax, [rcx]
0x180050d4d  mov     rax, [rax+10h]
0x180050d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d56  xor     ebx, ebx
0x180050d58  mov     [rbp+arg_8], rbx
0x180050d5c  jmp     loc_180050A17
0x180050d61  test    eax, eax
0x180050d63  jle     short loc_180050DB8
0x180050d65  movzx   edi, ax
0x180050d68  or      edi, 80070000h
0x180050d6e  jmp     short loc_180050DB8
0x180050d70  mov     rcx, [rbx+108h]
0x180050d77  xor     eax, eax
0x180050d79  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050d80  mov     [rcx], ax
0x180050d83  mov     [rbx+118h], eax
0x180050d89  jz      short loc_180050DB8
0x180050d8b  mov     rcx, cs:g_pDebug
0x180050d92  lea     rax, aFailedToSetupE; " Failed to setup enabled protocols for "...
0x180050d99  mov     [rsp+50h+var_28], rax
0x180050d9e  lea     r9, aApplicationDat_1; "APPLICATION_DATA_OBJECT_TABLE_APPHOST::"...
0x180050da5  mov     r8d, 13Dh
0x180050dab  mov     dword ptr [rsp+50h+var_30], edi
0x180050daf  mov     rdx, r14
0x180050db2  call    cs:__imp_PuDbgPrintError
0x180050db8  or      eax, 0FFFFFFFFh
0x180050dbb  lock xadd [rbx+0Ch], eax
0x180050dc0  cmp     eax, 1
0x180050dc3  jnz     short loc_180050E13
0x180050dc5  mov     rax, [rbx]
0x180050dc8  mov     edx, 1
0x180050dcd  mov     rcx, rbx
0x180050dd0  mov     rax, [rax]
0x180050dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dd8  jmp     short loc_180050E13
0x180050dda  mov     edi, 80070008h
0x180050ddf  jmp     short loc_180050E13
0x180050de1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180050de8  jz      short loc_180050E13
0x180050dea  lea     rax, aFailedToGetThe_2; " Failed to get the path of the app \n"
0x180050df1  mov     r8d, 10Bh
0x180050df7  mov     rdx, r14
0x180050dfa  jmp     loc_1800509EE
0x180050dff  mov     rcx, [rbp+var_10]
0x180050e03  mov     rax, [rcx]
0x180050e06  mov     rax, [rax+10h]
0x180050e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e0f  mov     [rbp+var_10], rbx
0x180050e13  mov     rcx, [rbp+arg_8]
0x180050e17  test    rcx, rcx
0x180050e1a  jz      short loc_180050E30
0x180050e1c  mov     rax, [rcx]
0x180050e1f  mov     rax, [rax+10h]
0x180050e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e28  mov     [rbp+arg_8], 0
0x180050e30  mov     rcx, [rbp+var_10]
0x180050e34  test    rcx, rcx
0x180050e37  jz      short loc_180050E45
0x180050e39  mov     rax, [rcx]
0x180050e3c  mov     rax, [rax+10h]
0x180050e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e45  lea     r11, [rsp+50h+var_s0]
0x180050e4a  mov     eax, edi
0x180050e4c  mov     rbx, [r11+30h]
0x180050e50  mov     rdi, [r11+40h]
0x180050e54  mov     rsp, r11
0x180050e57  pop     r15
0x180050e59  pop     r14
0x180050e5b  pop     r13
0x180050e5d  pop     r12
0x180050e5f  pop     rbp
0x180050e60  retn
```
