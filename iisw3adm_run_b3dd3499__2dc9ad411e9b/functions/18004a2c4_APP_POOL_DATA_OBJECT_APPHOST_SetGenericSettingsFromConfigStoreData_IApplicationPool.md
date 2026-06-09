# APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData(IApplicationPool *)

- ea: `0x18004a2c4`
- end: `0x18004a977`
- name: `?SetGenericSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIApplicationPool@@@Z`
- size: `1715`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_APPHOST *__hidden this, struct IApplicationPool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048f34`

## callees

- `0x18004a2c4`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004a445`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a4e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a781`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a957`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a445`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a4e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a781`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a957`
- `iisutil!PuDbgPrint` at `0x18004a3a4`
- `iisutil!PuDbgPrint` at `0x18004a420`
- `iisutil!PuDbgPrint` at `0x18004a4c3`
- `iisutil!PuDbgPrint` at `0x18004a5d5`
- `iisutil!PuDbgPrint` at `0x18004a669`
- `iisutil!PuDbgPrint` at `0x18004a6e3`
- `iisutil!PuDbgPrint` at `0x18004a75c`
- `iisutil!PuDbgPrint` at `0x18004a822`
- `iisutil!PuDbgPrint` at `0x18004a8ce`
- `iisutil!PuDbgPrint` at `0x18004a948`
- `iisutil!PuDbgPrint` at `0x18004a3a4`
- `iisutil!PuDbgPrint` at `0x18004a420`
- `iisutil!PuDbgPrint` at `0x18004a4c3`
- `iisutil!PuDbgPrint` at `0x18004a5d5`
- `iisutil!PuDbgPrint` at `0x18004a669`
- `iisutil!PuDbgPrint` at `0x18004a6e3`
- `iisutil!PuDbgPrint` at `0x18004a75c`
- `iisutil!PuDbgPrint` at `0x18004a822`
- `iisutil!PuDbgPrint` at `0x18004a8ce`
- `iisutil!PuDbgPrint` at `0x18004a948`
- `iisutil!PuDbgPrintError` at `0x18004a346`
- `iisutil!PuDbgPrintError` at `0x18004a873`
- `iisutil!PuDbgPrintError` at `0x18004a346`
- `iisutil!PuDbgPrintError` at `0x18004a873`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a431`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a4d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a76d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a431`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a4d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a76d`

## string_xrefs

- `0x18004a336`: ` Failed reading property \n`
- `0x18004a65d`: ` PassAnonymousToken = %S \n`
- `0x18004a750`: ` CLR Config File = %S \n`
- `0x18004a850`: ` Failed reading 'enableConfigurationOverride' property \n`
- `0x18004a8aa`: ` Enable Configuration Override = %S \n`
- `0x18004a31b`: `APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x18004a357`: `APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData`
- `0x18004a328`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x18004a361`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_APPHOST *this,
        struct IApplicationPool *a2)
{
  _DWORD *v2; // r12
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax
  const wchar_t *v9; // r13
  const wchar_t *v10; // rax
  int v11; // eax
  BOOL v12; // edx
  bool v13; // zf
  const wchar_t *v14; // rax
  int v15; // eax
  BOOL v16; // edx
  const wchar_t *v17; // rax
  int v18; // eax
  int v19; // edx
  BOOL v20; // r8d
  __int16 v22; // [rsp+80h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF

  bstrString = 0;
  v22 = 0;
  v2 = (_DWORD *)((char *)this + 360);
  v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, char *))(*(_QWORD *)a2 + 64LL))(a2, (char *)this + 360);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_66;
    v6 = 56;
    goto LABEL_4;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      66,
      "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
      " Queue Length = %u (0x%X) \n",
      *v2,
      *v2);
  v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, BSTR *))(*(_QWORD *)a2 + 88LL))(a2, &bstrString);
  if ( v5 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        82,
        "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
        " Clr Version = %S \n",
        bstrString);
    v5 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 744), bstrString);
    if ( v5 >= 0 )
    {
      SysFreeString(bstrString);
      v7 = *(_QWORD *)a2;
      bstrString = 0;
      v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, BSTR *))(v7 + 96))(a2, &bstrString);
      if ( v5 >= 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
            105,
            "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
            " Clr Loader = %S \n",
            bstrString);
        v5 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 800), bstrString);
        if ( v5 >= 0 )
        {
          SysFreeString(bstrString);
          v8 = *(_QWORD *)a2;
          bstrString = 0;
          v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, __int16 *))(v8 + 80))(a2, &v22);
          if ( v5 >= 0 )
          {
            *((_DWORD *)this + 183) = v22 == -1;
            v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, __int16 *))(*(_QWORD *)a2 + 192LL))(a2, &v22);
            if ( v5 >= 0 )
            {
              *((_DWORD *)this + 184) = v22 == -1;
              v9 = L"TRUE";
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
              {
                v10 = L"TRUE";
                if ( !*((_DWORD *)this + 183) )
                  v10 = L"FALSE";
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                  139,
                  "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                  " Enable32bitAppOnWin64 = %S \n",
                  v10);
              }
              v22 = 0;
              v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, __int16 *))(*(_QWORD *)a2 + 128LL))(a2, &v22);
              if ( v5 >= 0 )
              {
                v11 = g_dwDebugFlags;
                v12 = v22 == -1;
                v13 = (g_dwDebugFlags & 3) == 0;
                *((_DWORD *)this + 229) = v12;
                if ( !v13 && (v11 & 0x40000000) != 0 )
                {
                  v14 = L"TRUE";
                  if ( !v12 )
                    v14 = L"FALSE";
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                    157,
                    "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                    " PassAnonymousToken = %S \n",
                    v14);
                }
                v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, char *))(*(_QWORD *)a2 + 112LL))(
                       a2,
                       (char *)this + 912);
                if ( v5 >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                      172,
                      "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                      " Pipeline mode = %u \n",
                      *((_DWORD *)this + 228));
                  v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, BSTR *))(*(_QWORD *)a2 + 120LL))(
                         a2,
                         &bstrString);
                  if ( v5 >= 0 )
                  {
                    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                        188,
                        "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                        " CLR Config File = %S \n",
                        bstrString);
                    v5 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 856), bstrString);
                    if ( v5 >= 0 )
                    {
                      SysFreeString(bstrString);
                      bstrString = 0;
                      v22 = 0;
                      v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, __int16 *))(*(_QWORD *)a2 + 72LL))(
                             a2,
                             &v22);
                      if ( v5 >= 0 )
                      {
                        v15 = g_dwDebugFlags;
                        v16 = v22 == -1;
                        v13 = (g_dwDebugFlags & 3) == 0;
                        *((_DWORD *)this + 149) = v16;
                        if ( !v13 && (v15 & 0x40000000) != 0 )
                        {
                          v17 = L"TRUE";
                          if ( !v16 )
                            v17 = L"FALSE";
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                            213,
                            "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                            " Auto Start = %S \n",
                            v17);
                        }
                        v22 = 0;
                        v18 = (*(__int64 (__fastcall **)(struct IApplicationPool *, __int16 *))(*(_QWORD *)a2 + 104LL))(
                                a2,
                                &v22);
                        v19 = g_dwDebugFlags;
                        if ( v18 < 0 && (g_dwDebugFlags & 0xF) != 0 )
                        {
                          PuDbgPrintError(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                            222,
                            "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                            v18,
                            " Failed reading 'enableConfigurationOverride' property \n");
                          v19 = g_dwDebugFlags;
                        }
                        v20 = v22 == -1;
                        *((_DWORD *)this + 230) = v20;
                        if ( (v19 & 3) != 0 && (v19 & 0x40000000) != 0 )
                        {
                          if ( !v20 )
                            v9 = L"FALSE";
                          PuDbgPrint(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                            230,
                            "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                            " Enable Configuration Override = %S \n",
                            v9);
                        }
                        v5 = (*(__int64 (__fastcall **)(struct IApplicationPool *, char *))(*(_QWORD *)a2 + 136LL))(
                               a2,
                               (char *)this + 928);
                        if ( v5 >= 0 )
                        {
                          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                            PuDbgPrint(
                              g_pDebug,
                              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                              246,
                              "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
                              " Start mode = %u \n",
                              *((_DWORD *)this + 232));
                        }
                        else if ( (g_dwDebugFlags & 0xF) != 0 )
                        {
                          v6 = 238;
                          goto LABEL_4;
                        }
                      }
                      else if ( (g_dwDebugFlags & 0xF) != 0 )
                      {
                        v6 = 204;
                        goto LABEL_4;
                      }
                    }
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v6 = 180;
                    goto LABEL_4;
                  }
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v6 = 165;
                  goto LABEL_4;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v6 = 148;
                goto LABEL_4;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v6 = 130;
              goto LABEL_4;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v6 = 120;
            goto LABEL_4;
          }
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v6 = 97;
        goto LABEL_4;
      }
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v6 = 74;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      v6,
      "APP_POOL_DATA_OBJECT_APPHOST::SetGenericSettingsFromConfigStoreData",
      v5,
      " Failed reading property \n");
  }
LABEL_66:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a2c4  mov     [rsp-38h+arg_10], rbx
0x18004a2c9  push    rbp
0x18004a2ca  push    rsi
0x18004a2cb  push    rdi
0x18004a2cc  push    r12
0x18004a2ce  push    r13
0x18004a2d0  push    r14
0x18004a2d2  push    r15
0x18004a2d4  mov     rbp, rsp
0x18004a2d7  sub     rsp, 40h
0x18004a2db  xor     eax, eax
0x18004a2dd  mov     [rbp+bstrString], 0
0x18004a2e5  mov     [rbp+arg_0], ax
0x18004a2e9  lea     r12, [rcx+168h]
0x18004a2f0  mov     rax, [rdx]
0x18004a2f3  mov     r14, rdx
0x18004a2f6  mov     r15, rcx
0x18004a2f9  mov     rdx, r12
0x18004a2fc  mov     rcx, r14
0x18004a2ff  mov     rax, [rax+40h]
0x18004a303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a308  mov     ebx, eax
0x18004a30a  test    eax, eax
0x18004a30c  jns     short loc_18004A351
0x18004a30e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a315  jz      loc_18004A94E
0x18004a31b  lea     r9, aAppPoolDataObj_18; "APP_POOL_DATA_OBJECT_APPHOST::SetGeneri"...
0x18004a322  mov     r8d, 38h ; '8'
0x18004a328  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004a32f  mov     rcx, cs:g_pDebug
0x18004a336  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x18004a33d  mov     [rsp+40h+var_18], rax
0x18004a342  mov     dword ptr [rsp+40h+var_20], ebx
0x18004a346  call    cs:__imp_PuDbgPrintError
0x18004a34c  jmp     loc_18004A94E
0x18004a351  mov     eax, cs:g_dwDebugFlags
0x18004a357  lea     rdi, aAppPoolDataObj_18; "APP_POOL_DATA_OBJECT_APPHOST::SetGeneri"...
0x18004a35e  mov     r13b, 3
0x18004a361  lea     rsi, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18004a368  test    r13b, al
0x18004a36b  setnz   cl
0x18004a36e  bt      eax, 1Eh
0x18004a372  setb    al
0x18004a375  test    al, cl
0x18004a377  jz      short loc_18004A3AA
0x18004a379  mov     eax, [r12]
0x18004a37d  mov     r9, rdi
0x18004a380  mov     rcx, cs:g_pDebug
0x18004a387  mov     r8d, 42h ; 'B'
0x18004a38d  mov     [rsp+40h+var_10], eax
0x18004a391  mov     rdx, rsi
0x18004a394  mov     dword ptr [rsp+40h+var_18], eax
0x18004a398  lea     rax, aQueueLengthU0x; " Queue Length = %u (0x%X) \n"
0x18004a39f  mov     [rsp+40h+var_20], rax
0x18004a3a4  call    cs:__imp_PuDbgPrint
0x18004a3aa  mov     rax, [r14]
0x18004a3ad  lea     rdx, [rbp+bstrString]
0x18004a3b1  mov     rcx, r14
0x18004a3b4  mov     rax, [rax+58h]
0x18004a3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3bd  mov     ebx, eax
0x18004a3bf  test    eax, eax
0x18004a3c1  jns     short loc_18004A3E1
0x18004a3c3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a3ca  jz      loc_18004A94E
0x18004a3d0  mov     r8d, 4Ah ; 'J'
0x18004a3d6  mov     r9, rdi
0x18004a3d9  mov     rdx, rsi
0x18004a3dc  jmp     loc_18004A32F
0x18004a3e1  mov     eax, cs:g_dwDebugFlags
0x18004a3e7  test    r13b, al
0x18004a3ea  setnz   cl
0x18004a3ed  bt      eax, 1Eh
0x18004a3f1  setb    al
0x18004a3f4  test    al, cl
0x18004a3f6  jz      short loc_18004A426
0x18004a3f8  mov     rax, [rbp+bstrString]
0x18004a3fc  mov     r9, rdi
0x18004a3ff  mov     rcx, cs:g_pDebug
0x18004a406  mov     r8d, 52h ; 'R'
0x18004a40c  mov     [rsp+40h+var_18], rax
0x18004a411  mov     rdx, rsi
0x18004a414  lea     rax, aClrVersionS; " Clr Version = %S \n"
0x18004a41b  mov     [rsp+40h+var_20], rax
0x18004a420  call    cs:__imp_PuDbgPrint
0x18004a426  mov     rdx, [rbp+bstrString]
0x18004a42a  lea     rcx, [r15+2E8h]
0x18004a431  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004a437  mov     ebx, eax
0x18004a439  test    eax, eax
0x18004a43b  js      loc_18004A94E
0x18004a441  mov     rcx, [rbp+bstrString]; bstrString
0x18004a445  call    cs:__imp_SysFreeString
0x18004a44b  mov     rax, [r14]
0x18004a44e  lea     rdx, [rbp+bstrString]
0x18004a452  mov     rcx, r14
0x18004a455  mov     [rbp+bstrString], 0
0x18004a45d  mov     rax, [rax+60h]
0x18004a461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a466  mov     ebx, eax
0x18004a468  test    eax, eax
0x18004a46a  jns     short loc_18004A484
0x18004a46c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a473  jz      loc_18004A94E
0x18004a479  mov     r8d, 61h ; 'a'
0x18004a47f  jmp     loc_18004A3D6
0x18004a484  mov     eax, cs:g_dwDebugFlags
0x18004a48a  test    r13b, al
0x18004a48d  setnz   cl
0x18004a490  bt      eax, 1Eh
0x18004a494  setb    al
0x18004a497  test    al, cl
0x18004a499  jz      short loc_18004A4C9
0x18004a49b  mov     rax, [rbp+bstrString]
0x18004a49f  mov     r9, rdi
0x18004a4a2  mov     rcx, cs:g_pDebug
0x18004a4a9  mov     r8d, 69h ; 'i'
0x18004a4af  mov     [rsp+40h+var_18], rax
0x18004a4b4  mov     rdx, rsi
0x18004a4b7  lea     rax, aClrLoaderS; " Clr Loader = %S \n"
0x18004a4be  mov     [rsp+40h+var_20], rax
0x18004a4c3  call    cs:__imp_PuDbgPrint
0x18004a4c9  mov     rdx, [rbp+bstrString]
0x18004a4cd  lea     rcx, [r15+320h]
0x18004a4d4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004a4da  mov     ebx, eax
0x18004a4dc  test    eax, eax
0x18004a4de  js      loc_18004A94E
0x18004a4e4  mov     rcx, [rbp+bstrString]; bstrString
0x18004a4e8  call    cs:__imp_SysFreeString
0x18004a4ee  mov     rax, [r14]
0x18004a4f1  lea     rdx, [rbp+arg_0]
0x18004a4f5  mov     rcx, r14
0x18004a4f8  mov     [rbp+bstrString], 0
0x18004a500  mov     rax, [rax+50h]
0x18004a504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a509  mov     ebx, eax
0x18004a50b  test    eax, eax
0x18004a50d  jns     short loc_18004A527
0x18004a50f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a516  jz      loc_18004A94E
0x18004a51c  mov     r8d, 78h ; 'x'
0x18004a522  jmp     loc_18004A3D6
0x18004a527  xor     eax, eax
0x18004a529  lea     rdx, [rbp+arg_0]
0x18004a52d  cmp     [rbp+arg_0], 0FFFFh
0x18004a532  mov     rcx, r14
0x18004a535  setz    al
0x18004a538  mov     [r15+2DCh], eax
0x18004a53f  mov     rax, [r14]
0x18004a542  mov     rax, [rax+0C0h]
0x18004a549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a54e  mov     ebx, eax
0x18004a550  test    eax, eax
0x18004a552  jns     short loc_18004A56C
0x18004a554  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a55b  jz      loc_18004A94E
0x18004a561  mov     r8d, 82h
0x18004a567  jmp     loc_18004A3D6
0x18004a56c  xor     eax, eax
0x18004a56e  lea     r12, aFalse_1; "FALSE"
0x18004a575  cmp     [rbp+arg_0], 0FFFFh
0x18004a57a  setz    al
0x18004a57d  mov     [r15+2E0h], eax
0x18004a584  mov     eax, cs:g_dwDebugFlags
0x18004a58a  test    r13b, al
0x18004a58d  lea     r13, aTrue_1; "TRUE"
0x18004a594  setnz   cl
0x18004a597  bt      eax, 1Eh
0x18004a59b  setb    al
0x18004a59e  test    al, cl
0x18004a5a0  jz      short loc_18004A5DB
0x18004a5a2  cmp     dword ptr [r15+2DCh], 0
0x18004a5aa  mov     rax, r13
0x18004a5ad  mov     rcx, cs:g_pDebug
0x18004a5b4  mov     r9, rdi
0x18004a5b7  cmovz   rax, r12
0x18004a5bb  mov     r8d, 8Bh
0x18004a5c1  mov     [rsp+40h+var_18], rax
0x18004a5c6  mov     rdx, rsi
0x18004a5c9  lea     rax, aEnable32bitapp_0; " Enable32bitAppOnWin64 = %S \n"
0x18004a5d0  mov     [rsp+40h+var_20], rax
0x18004a5d5  call    cs:__imp_PuDbgPrint
0x18004a5db  xor     eax, eax
0x18004a5dd  lea     rdx, [rbp+arg_0]
0x18004a5e1  mov     [rbp+arg_0], ax
0x18004a5e5  mov     rcx, r14
0x18004a5e8  mov     rax, [r14]
0x18004a5eb  mov     rax, [rax+80h]
0x18004a5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5f7  mov     ebx, eax
0x18004a5f9  test    eax, eax
0x18004a5fb  jns     short loc_18004A615
0x18004a5fd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a604  jz      loc_18004A94E
0x18004a60a  mov     r8d, 94h
0x18004a610  jmp     loc_18004A3D6
0x18004a615  mov     eax, cs:g_dwDebugFlags
0x18004a61b  xor     edx, edx
0x18004a61d  cmp     [rbp+arg_0], 0FFFFh
0x18004a622  setz    dl
0x18004a625  test    al, 3
0x18004a627  mov     [r15+394h], edx
0x18004a62e  setnz   cl
0x18004a631  bt      eax, 1Eh
0x18004a635  setb    al
0x18004a638  test    al, cl
0x18004a63a  jz      short loc_18004A66F
0x18004a63c  mov     rcx, cs:g_pDebug
0x18004a643  test    edx, edx
0x18004a645  mov     rax, r13
0x18004a648  mov     r9, rdi
0x18004a64b  cmovz   rax, r12
0x18004a64f  mov     r8d, 9Dh
0x18004a655  mov     [rsp+40h+var_18], rax
0x18004a65a  mov     rdx, rsi
0x18004a65d  lea     rax, aPassanonymoust_0; " PassAnonymousToken = %S \n"
0x18004a664  mov     [rsp+40h+var_20], rax
0x18004a669  call    cs:__imp_PuDbgPrint
0x18004a66f  mov     rax, [r14]
0x18004a672  lea     r12, [r15+390h]
0x18004a679  mov     rdx, r12
0x18004a67c  mov     rcx, r14
0x18004a67f  mov     rax, [rax+70h]
0x18004a683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a688  mov     ebx, eax
0x18004a68a  test    eax, eax
0x18004a68c  jns     short loc_18004A6A6
0x18004a68e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a695  jz      loc_18004A94E
0x18004a69b  mov     r8d, 0A5h
0x18004a6a1  jmp     loc_18004A3D6
0x18004a6a6  mov     eax, cs:g_dwDebugFlags
0x18004a6ac  test    al, 3
0x18004a6ae  setnz   cl
0x18004a6b1  bt      eax, 1Eh
0x18004a6b5  setb    al
0x18004a6b8  test    al, cl
0x18004a6ba  jz      short loc_18004A6E9
0x18004a6bc  mov     eax, [r12]
0x18004a6c0  mov     r9, rdi
0x18004a6c3  mov     rcx, cs:g_pDebug
0x18004a6ca  mov     r8d, 0ACh
0x18004a6d0  mov     dword ptr [rsp+40h+var_18], eax
0x18004a6d4  mov     rdx, rsi
0x18004a6d7  lea     rax, aPipelineModeU; " Pipeline mode = %u \n"
0x18004a6de  mov     [rsp+40h+var_20], rax
0x18004a6e3  call    cs:__imp_PuDbgPrint
0x18004a6e9  mov     rax, [r14]
0x18004a6ec  lea     rdx, [rbp+bstrString]
0x18004a6f0  mov     rcx, r14
0x18004a6f3  mov     rax, [rax+78h]
0x18004a6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6fc  mov     ebx, eax
0x18004a6fe  test    eax, eax
0x18004a700  jns     short loc_18004A71A
0x18004a702  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a709  jz      loc_18004A94E
0x18004a70f  mov     r8d, 0B4h
0x18004a715  jmp     loc_18004A3D6
0x18004a71a  mov     eax, cs:g_dwDebugFlags
0x18004a720  mov     r12b, 3
0x18004a723  test    r12b, al
0x18004a726  setnz   cl
0x18004a729  bt      eax, 1Eh
0x18004a72d  setb    al
0x18004a730  test    al, cl
0x18004a732  jz      short loc_18004A762
0x18004a734  mov     rax, [rbp+bstrString]
0x18004a738  mov     r9, rdi
0x18004a73b  mov     rcx, cs:g_pDebug
0x18004a742  mov     r8d, 0BCh
0x18004a748  mov     [rsp+40h+var_18], rax
0x18004a74d  mov     rdx, rsi
0x18004a750  lea     rax, aClrConfigFileS; " CLR Config File = %S \n"
0x18004a757  mov     [rsp+40h+var_20], rax
0x18004a75c  call    cs:__imp_PuDbgPrint
0x18004a762  mov     rdx, [rbp+bstrString]
0x18004a766  lea     rcx, [r15+358h]
0x18004a76d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004a773  mov     ebx, eax
0x18004a775  test    eax, eax
0x18004a777  js      loc_18004A94E
0x18004a77d  mov     rcx, [rbp+bstrString]; bstrString
0x18004a781  call    cs:__imp_SysFreeString
0x18004a787  xor     eax, eax
0x18004a789  mov     [rbp+bstrString], 0
0x18004a791  mov     [rbp+arg_0], ax
0x18004a795  lea     rdx, [rbp+arg_0]
0x18004a799  mov     rax, [r14]
0x18004a79c  mov     rcx, r14
0x18004a79f  mov     rax, [rax+48h]
0x18004a7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7a8  mov     ebx, eax
0x18004a7aa  test    eax, eax
0x18004a7ac  jns     short loc_18004A7C6
0x18004a7ae  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a7b5  jz      loc_18004A94E
0x18004a7bb  mov     r8d, 0CCh
0x18004a7c1  jmp     loc_18004A3D6
  ... truncated ...
```
