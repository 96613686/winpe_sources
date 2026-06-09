# SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData(ISiteLimits *)

- ea: `0x18004f468`
- end: `0x18004f678`
- name: `?SetLimitSettingsFromConfigStoreData@SITE_DATA_OBJECT_APPHOST@@QEAAJPEAUISiteLimits@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(SITE_DATA_OBJECT_APPHOST *__hidden this, struct ISiteLimits *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e444`

## callees

- `0x18004f468`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18004f530`
- `iisutil!PuDbgPrint` at `0x18004f5e0`
- `iisutil!PuDbgPrint` at `0x18004f665`
- `iisutil!PuDbgPrint` at `0x18004f530`
- `iisutil!PuDbgPrint` at `0x18004f5e0`
- `iisutil!PuDbgPrint` at `0x18004f665`
- `iisutil!PuDbgPrintError` at `0x18004f4d9`
- `iisutil!PuDbgPrintError` at `0x18004f4d9`

## string_xrefs

- `0x18004f4b4`: ` Failed reading property \n`
- `0x18004f55d`: ` Failed reading connection timeout property \n`
- `0x18004f4ce`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f50b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f5d4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f640`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore_apphost.cxx`
- `0x18004f4c2`: `SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData`
- `0x18004f4fd`: `SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData`
- `0x18004f5bf`: `SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData`
- `0x18004f632`: `SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData(
        SITE_DATA_OBJECT_APPHOST *this,
        struct ISiteLimits *a2)
{
  __int64 v2; // rax
  _DWORD *v3; // r15
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rdx
  int v9; // eax
  bool v10; // zf
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = (_DWORD *)((char *)this + 288);
  v12 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ISiteLimits *, char *))(v2 + 56))(a2, (char *)this + 288);
  if ( v6 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
        643,
        "SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData",
        " Max Bandwidth = %u (0x%X) (%d) \n ",
        *v3,
        *v3,
        *v3);
    v6 = (*(__int64 (__fastcall **)(struct ISiteLimits *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v12);
    if ( v6 >= 0 )
    {
      v8 = v12 / 10000000;
      v9 = g_dwDebugFlags;
      v10 = (g_dwDebugFlags & 3) == 0;
      *((_DWORD *)this + 74) = v12 / 10000000;
      if ( !v10 && (v9 & 0x40000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
          662,
          "SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData",
          " Connection Timeout (as seconds) = %u (0x%X) (%d) \n ",
          v8,
          v8,
          v8);
      v6 = (*(__int64 (__fastcall **)(struct ISiteLimits *, char *))(*(_QWORD *)a2 + 64LL))(a2, (char *)this + 292);
      if ( v6 >= 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
            680,
            "SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData",
            " Max Connections = %u (0x%X) (%d) \n ",
            *((_DWORD *)this + 73),
            *((_DWORD *)this + 73),
            *((_DWORD *)this + 73));
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v7 = 670;
        goto LABEL_4;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
        651,
        "SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData",
        v6,
        " Failed reading connection timeout property \n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = 633;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore_apphost.cxx",
      v7,
      "SITE_DATA_OBJECT_APPHOST::SetLimitSettingsFromConfigStoreData",
      v6,
      " Failed reading property \n");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004f468  push    rbx
0x18004f46a  push    rbp
0x18004f46b  push    r14
0x18004f46d  push    r15
0x18004f46f  sub     rsp, 48h
0x18004f473  mov     rax, [rdx]
0x18004f476  lea     r15, [rcx+120h]
0x18004f47d  mov     r14, rdx
0x18004f480  mov     [rsp+68h+arg_0], 0
0x18004f489  mov     rbp, rcx
0x18004f48c  mov     rdx, r15
0x18004f48f  mov     rcx, r14
0x18004f492  mov     rax, [rax+38h]
0x18004f496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f49b  mov     ebx, eax
0x18004f49d  test    eax, eax
0x18004f49f  jns     short loc_18004F4E4
0x18004f4a1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f4a8  jz      loc_18004F66B
0x18004f4ae  mov     r8d, 279h
0x18004f4b4  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004f4bb  mov     rcx, cs:g_pDebug
0x18004f4c2  lea     r9, aSiteDataObject_8; "SITE_DATA_OBJECT_APPHOST::SetLimitSetti"...
0x18004f4c9  mov     [rsp+68h+var_40], rax
0x18004f4ce  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f4d5  mov     dword ptr [rsp+68h+var_48], ebx
0x18004f4d9  call    cs:__imp_PuDbgPrintError
0x18004f4df  jmp     loc_18004F66B
0x18004f4e4  mov     eax, cs:g_dwDebugFlags
0x18004f4ea  test    al, 3
0x18004f4ec  setnz   cl
0x18004f4ef  bt      eax, 1Eh
0x18004f4f3  setb    al
0x18004f4f6  test    al, cl
0x18004f4f8  jz      short loc_18004F536
0x18004f4fa  mov     eax, [r15]
0x18004f4fd  lea     r9, aSiteDataObject_8; "SITE_DATA_OBJECT_APPHOST::SetLimitSetti"...
0x18004f504  mov     rcx, cs:g_pDebug
0x18004f50b  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f512  mov     [rsp+68h+var_30], eax
0x18004f516  mov     r8d, 283h
0x18004f51c  mov     [rsp+68h+var_38], eax
0x18004f520  mov     dword ptr [rsp+68h+var_40], eax
0x18004f524  lea     rax, aMaxBandwidthU0; " Max Bandwidth = %u (0x%X) (%d) \n "
0x18004f52b  mov     [rsp+68h+var_48], rax
0x18004f530  call    cs:__imp_PuDbgPrint
0x18004f536  mov     rax, [r14]
0x18004f539  lea     rdx, [rsp+68h+arg_0]
0x18004f53e  mov     rcx, r14
0x18004f541  mov     rax, [rax+48h]
0x18004f545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f54a  mov     ebx, eax
0x18004f54c  test    eax, eax
0x18004f54e  jns     short loc_18004F56F
0x18004f550  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f557  jz      loc_18004F66B
0x18004f55d  lea     rax, aFailedReadingC_3; " Failed reading connection timeout prop"...
0x18004f564  mov     r8d, 28Bh
0x18004f56a  jmp     loc_18004F4BB
0x18004f56f  mov     rax, 0D6BF94D5E57A42BDh
0x18004f579  imul    [rsp+68h+arg_0]
0x18004f57e  add     rdx, [rsp+68h+arg_0]
0x18004f583  sar     rdx, 17h
0x18004f587  mov     rax, rdx
0x18004f58a  shr     rax, 3Fh
0x18004f58e  add     rdx, rax
0x18004f591  mov     eax, cs:g_dwDebugFlags
0x18004f597  test    al, 3
0x18004f599  mov     [rbp+128h], edx
0x18004f59f  setnz   cl
0x18004f5a2  bt      eax, 1Eh
0x18004f5a6  setb    al
0x18004f5a9  test    al, cl
0x18004f5ab  jz      short loc_18004F5E6
0x18004f5ad  mov     rcx, cs:g_pDebug
0x18004f5b4  lea     rax, aConnectionTime; " Connection Timeout (as seconds) = %u ("...
0x18004f5bb  mov     [rsp+68h+var_30], edx
0x18004f5bf  lea     r9, aSiteDataObject_8; "SITE_DATA_OBJECT_APPHOST::SetLimitSetti"...
0x18004f5c6  mov     [rsp+68h+var_38], edx
0x18004f5ca  mov     r8d, 296h
0x18004f5d0  mov     dword ptr [rsp+68h+var_40], edx
0x18004f5d4  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f5db  mov     [rsp+68h+var_48], rax
0x18004f5e0  call    cs:__imp_PuDbgPrint
0x18004f5e6  mov     rax, [r14]
0x18004f5e9  lea     r15, [rbp+124h]
0x18004f5f0  mov     rdx, r15
0x18004f5f3  mov     rcx, r14
0x18004f5f6  mov     rax, [rax+40h]
0x18004f5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5ff  mov     ebx, eax
0x18004f601  test    eax, eax
0x18004f603  jns     short loc_18004F619
0x18004f605  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004f60c  jz      short loc_18004F66B
0x18004f60e  mov     r8d, 29Eh
0x18004f614  jmp     loc_18004F4B4
0x18004f619  mov     eax, cs:g_dwDebugFlags
0x18004f61f  test    al, 3
0x18004f621  setnz   cl
0x18004f624  bt      eax, 1Eh
0x18004f628  setb    al
0x18004f62b  test    al, cl
0x18004f62d  jz      short loc_18004F66B
0x18004f62f  mov     eax, [r15]
0x18004f632  lea     r9, aSiteDataObject_8; "SITE_DATA_OBJECT_APPHOST::SetLimitSetti"...
0x18004f639  mov     rcx, cs:g_pDebug
0x18004f640  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004f647  mov     [rsp+68h+var_30], eax
0x18004f64b  mov     r8d, 2A8h
0x18004f651  mov     [rsp+68h+var_38], eax
0x18004f655  mov     dword ptr [rsp+68h+var_40], eax
0x18004f659  lea     rax, aMaxConnections; " Max Connections = %u (0x%X) (%d) \n "
0x18004f660  mov     [rsp+68h+var_48], rax
0x18004f665  call    cs:__imp_PuDbgPrint
0x18004f66b  mov     eax, ebx
0x18004f66d  add     rsp, 48h
0x18004f671  pop     r15
0x18004f673  pop     r14
0x18004f675  pop     rbp
0x18004f676  pop     rbx
0x18004f677  retn
```
