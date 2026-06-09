# SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData(IAppHostSite *)

- ea: `0x18004f27c`
- end: `0x18004f461`
- name: `?SetGenericSettingsFromConfigStoreData@SITE_DATA_OBJECT_APPHOST@@QEAAJPEAUIAppHostSite@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_APPHOST *__hidden this, struct IAppHostSite *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e444`

## callees

- `0x18004f27c`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004f397`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f448`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f397`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f448`
- `iisutil!PuDbgPrint` at `0x18004f353`
- `iisutil!PuDbgPrint` at `0x18004f438`
- `iisutil!PuDbgPrint` at `0x18004f353`
- `iisutil!PuDbgPrint` at `0x18004f438`
- `iisutil!PuDbgPrintError` at `0x18004f2f3`
- `iisutil!PuDbgPrintError` at `0x18004f2f3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004f367`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004f367`

## string_xrefs

- `0x18004f2ce`: ` Failed reading property \n`
- `0x18004f380`: ` Failed copying string property \n`
- `0x18004f2dc`: `SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x18004f323`: `SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x18004f412`: `SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x18004f2e8`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f330`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f420`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData(
        SITE_DATA_OBJECT_APPHOST *this,
        struct IAppHostSite *a2)
{
  int v4; // ebx
  __int64 v5; // r8
  const wchar_t *v6; // rcx
  int v7; // eax
  BOOL v8; // edx
  bool v9; // zf
  const wchar_t *v10; // rax
  __int16 v12; // [rsp+48h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF

  bstrString = 0;
  v12 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IAppHostSite *, BSTR *))(*(_QWORD *)a2 + 56LL))(a2, &bstrString);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_22;
    v5 = 52;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
      v5,
      "SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
      v4,
      " Failed reading property \n");
    goto LABEL_22;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v6 = L"NULL";
    if ( bstrString )
      v6 = bstrString;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
      60,
      "SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
      " Site Name '%S' \n",
      v6);
  }
  if ( bstrString )
  {
    v4 = STRU::Copy((SITE_DATA_OBJECT_APPHOST *)((char *)this + 80), bstrString);
    if ( v4 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
          71,
          "SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
          v4,
          " Failed copying string property \n");
      goto LABEL_22;
    }
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v4 = (*(__int64 (__fastcall **)(struct IAppHostSite *, __int16 *))(*(_QWORD *)a2 + 72LL))(a2, &v12);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_22;
    v5 = 83;
    goto LABEL_4;
  }
  v7 = g_dwDebugFlags;
  v8 = v12 == -1;
  v9 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 18) = v8;
  if ( !v9 && (v7 & 0x40000000) != 0 )
  {
    v10 = L"TRUE";
    if ( !v8 )
      v10 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
      92,
      "SITE_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
      " Auto Start '%S' \n",
      v10);
  }
LABEL_22:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004f27c  mov     r11, rsp
0x18004f27f  mov     [r11+8], rbx
0x18004f283  mov     [r11+20h], rbp
0x18004f287  push    r14
0x18004f289  sub     rsp, 30h
0x18004f28d  xor     eax, eax
0x18004f28f  mov     qword ptr [r11+18h], 0
0x18004f297  mov     [rsp+38h+arg_8], ax
0x18004f29c  mov     r14, rdx
0x18004f29f  mov     rax, [rdx]
0x18004f2a2  mov     rbp, rcx
0x18004f2a5  lea     rdx, [r11+18h]
0x18004f2a9  mov     rcx, r14
0x18004f2ac  mov     rax, [rax+38h]
0x18004f2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2b5  mov     ebx, eax
0x18004f2b7  test    eax, eax
0x18004f2b9  jns     short loc_18004F2FE
0x18004f2bb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f2c2  jz      loc_18004F43E
0x18004f2c8  mov     r8d, 34h ; '4'
0x18004f2ce  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004f2d5  mov     rcx, cs:g_pDebug
0x18004f2dc  lea     r9, aSiteDataObject_9; "SITE_DATA_OBJECT_APPHOST::SetGenericSet"...
0x18004f2e3  mov     [rsp+38h+var_10], rax
0x18004f2e8  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f2ef  mov     dword ptr [rsp+38h+var_18], ebx
0x18004f2f3  call    cs:__imp_PuDbgPrintError
0x18004f2f9  jmp     loc_18004F43E
0x18004f2fe  mov     eax, cs:g_dwDebugFlags
0x18004f304  test    al, 3
0x18004f306  setnz   cl
0x18004f309  bt      eax, 1Eh
0x18004f30d  setb    al
0x18004f310  test    al, cl
0x18004f312  jz      short loc_18004F359
0x18004f314  mov     rax, [rsp+38h+bstrString]
0x18004f319  lea     rcx, aNull_0; "NULL"
0x18004f320  test    rax, rax
0x18004f323  lea     r9, aSiteDataObject_9; "SITE_DATA_OBJECT_APPHOST::SetGenericSet"...
0x18004f32a  mov     r8d, 3Ch ; '<'
0x18004f330  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f337  cmovnz  rcx, rax
0x18004f33b  lea     rax, aSiteNameS; " Site Name '%S' \n"
0x18004f342  mov     [rsp+38h+var_10], rcx
0x18004f347  mov     rcx, cs:g_pDebug
0x18004f34e  mov     [rsp+38h+var_18], rax
0x18004f353  call    cs:__imp_PuDbgPrint
0x18004f359  mov     rdx, [rsp+38h+bstrString]
0x18004f35e  test    rdx, rdx
0x18004f361  jz      short loc_18004F3A6
0x18004f363  lea     rcx, [rbp+50h]
0x18004f367  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004f36d  mov     ebx, eax
0x18004f36f  test    eax, eax
0x18004f371  jns     short loc_18004F392
0x18004f373  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f37a  jz      loc_18004F43E
0x18004f380  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x18004f387  mov     r8d, 47h ; 'G'
0x18004f38d  jmp     loc_18004F2D5
0x18004f392  mov     rcx, [rsp+38h+bstrString]; bstrString
0x18004f397  call    cs:__imp_SysFreeString
0x18004f39d  mov     [rsp+38h+bstrString], 0
0x18004f3a6  mov     rax, [r14]
0x18004f3a9  lea     rdx, [rsp+38h+arg_8]
0x18004f3ae  mov     rcx, r14
0x18004f3b1  mov     rax, [rax+48h]
0x18004f3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3ba  mov     ebx, eax
0x18004f3bc  test    eax, eax
0x18004f3be  jns     short loc_18004F3D4
0x18004f3c0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f3c7  jz      short loc_18004F43E
0x18004f3c9  mov     r8d, 53h ; 'S'
0x18004f3cf  jmp     loc_18004F2CE
0x18004f3d4  mov     eax, cs:g_dwDebugFlags
0x18004f3da  xor     edx, edx
0x18004f3dc  cmp     [rsp+38h+arg_8], 0FFFFh
0x18004f3e2  setz    dl
0x18004f3e5  test    al, 3
0x18004f3e7  mov     [rbp+48h], edx
0x18004f3ea  setnz   cl
0x18004f3ed  bt      eax, 1Eh
0x18004f3f1  setb    al
0x18004f3f4  test    al, cl
0x18004f3f6  jz      short loc_18004F43E
0x18004f3f8  test    edx, edx
0x18004f3fa  lea     rcx, aFalse_1; "FALSE"
0x18004f401  lea     rax, aTrue_1; "TRUE"
0x18004f408  mov     r8d, 5Ch ; '\'
0x18004f40e  cmovz   rax, rcx
0x18004f412  lea     r9, aSiteDataObject_9; "SITE_DATA_OBJECT_APPHOST::SetGenericSet"...
0x18004f419  mov     rcx, cs:g_pDebug
0x18004f420  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f427  mov     [rsp+38h+var_10], rax
0x18004f42c  lea     rax, aAutoStartS; " Auto Start '%S' \n"
0x18004f433  mov     [rsp+38h+var_18], rax
0x18004f438  call    cs:__imp_PuDbgPrint
0x18004f43e  mov     rcx, [rsp+38h+bstrString]; bstrString
0x18004f443  test    rcx, rcx
0x18004f446  jz      short loc_18004F44E
0x18004f448  call    cs:__imp_SysFreeString
0x18004f44e  mov     rbp, [rsp+38h+arg_18]
0x18004f453  mov     eax, ebx
0x18004f455  mov     rbx, [rsp+38h+arg_0]
0x18004f45a  add     rsp, 30h
0x18004f45e  pop     r14
0x18004f460  retn
```
