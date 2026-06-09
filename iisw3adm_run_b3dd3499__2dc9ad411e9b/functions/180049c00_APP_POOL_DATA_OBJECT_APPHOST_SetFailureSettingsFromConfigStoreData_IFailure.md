# APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData(IFailure *)

- ea: `0x180049c00`
- end: `0x18004a2be`
- name: `?SetFailureSettingsFromConfigStoreData@APP_POOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIFailure@@@Z`
- size: `1726`
- prototype: `__int64 __fastcall(APP_POOL_DATA_OBJECT_APPHOST *__hidden this, struct IFailure *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048f34`

## callees

- `0x180049c00`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180049e55`
- `OLEAUT32!__imp_SysFreeString` at `0x180049f21`
- `OLEAUT32!__imp_SysFreeString` at `0x180049fed`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a29e`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e55`
- `OLEAUT32!__imp_SysFreeString` at `0x180049f21`
- `OLEAUT32!__imp_SysFreeString` at `0x180049fed`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a29e`
- `iisutil!PuDbgPrint` at `0x180049ce4`
- `iisutil!PuDbgPrint` at `0x180049d8a`
- `iisutil!PuDbgPrint` at `0x180049e10`
- `iisutil!PuDbgPrint` at `0x180049edc`
- `iisutil!PuDbgPrint` at `0x180049fa8`
- `iisutil!PuDbgPrint` at `0x18004a071`
- `iisutil!PuDbgPrint` at `0x18004a157`
- `iisutil!PuDbgPrint` at `0x18004a214`
- `iisutil!PuDbgPrint` at `0x18004a28f`
- `iisutil!PuDbgPrint` at `0x180049ce4`
- `iisutil!PuDbgPrint` at `0x180049d8a`
- `iisutil!PuDbgPrint` at `0x180049e10`
- `iisutil!PuDbgPrint` at `0x180049edc`
- `iisutil!PuDbgPrint` at `0x180049fa8`
- `iisutil!PuDbgPrint` at `0x18004a071`
- `iisutil!PuDbgPrint` at `0x18004a157`
- `iisutil!PuDbgPrint` at `0x18004a214`
- `iisutil!PuDbgPrint` at `0x18004a28f`
- `iisutil!PuDbgPrintError` at `0x180049c8a`
- `iisutil!PuDbgPrintError` at `0x180049c8a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049e26`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049ef2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049fbe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a087`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049e26`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049ef2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180049fbe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004a087`

## string_xrefs

- `0x180049d16`: ` Failed reading property \n`
- `0x180049e3f`: ` Failed copying string property \n`
- `0x180049f0b`: ` Failed copying string property \n`
- `0x180049fd7`: ` Failed copying string property \n`
- `0x18004a0a0`: ` Failed copying string property \n`
- `0x180049c5f`: ` Failed reading load balancer capabilities property \n`
- `0x180049c73`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x180049ca4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\apppoolstore_apphost.cxx`
- `0x180049c6c`: `APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData`
- `0x180049c9b`: `APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData`

## pseudocode

```c
__int64 __fastcall APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData(
        APP_POOL_DATA_OBJECT_APPHOST *this,
        struct IFailure *a2)
{
  _DWORD *v2; // r12
  __int64 v3; // rax
  int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  int v9; // eax
  const wchar_t *v10; // r8
  const wchar_t *v11; // r13
  BOOL v12; // edx
  bool v13; // zf
  const wchar_t *v14; // rax
  BSTR v15; // r12
  BSTR v16; // rcx
  BSTR v17; // rcx
  BSTR v18; // rcx
  int v19; // eax
  BOOL v20; // edx
  __int64 v21; // rdx
  int v22; // eax
  __int16 v24; // [rsp+80h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF
  __int64 v26; // [rsp+90h] [rbp+50h] BYREF

  bstrString = 0;
  v24 = 0;
  v2 = (_DWORD *)((char *)this + 720);
  v3 = *(_QWORD *)a2;
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IFailure *, char *))(v3 + 56))(a2, (char *)this + 720);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_80;
    v7 = " Failed reading load balancer capabilities property \n";
    v8 = 964;
    goto LABEL_4;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      973,
      "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
      " Load Balancer Type = %u (0x%X) \n",
      *v2,
      *v2);
  v6 = (*(__int64 (__fastcall **)(struct IFailure *, __int16 *))(*(_QWORD *)a2 + 64LL))(a2, &v24);
  if ( v6 >= 0 )
  {
    v9 = g_dwDebugFlags;
    v10 = L"FALSE";
    v11 = L"TRUE";
    v12 = v24 == -1;
    v13 = (g_dwDebugFlags & 3) == 0;
    *((_DWORD *)this + 55) = v12;
    if ( !v13 && (v9 & 0x40000000) != 0 )
    {
      v14 = L"TRUE";
      if ( !v12 )
        v14 = L"FALSE";
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
        990,
        "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
        " Orphan WP %S \n",
        v14);
    }
    v6 = (*(__int64 (__fastcall **)(struct IFailure *, BSTR *, const wchar_t *))(*(_QWORD *)a2 + 72LL))(
           a2,
           &bstrString,
           v10);
    if ( v6 >= 0 )
    {
      v15 = L"NULL";
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
      {
        v16 = L"NULL";
        if ( bstrString )
          v16 = bstrString;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
          1006,
          "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
          " Oprhan Exe = '%s' \n",
          (const char *)v16);
      }
      if ( bstrString )
      {
        v6 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 248), bstrString);
        if ( v6 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v7 = " Failed copying string property \n";
            v8 = 1016;
            goto LABEL_4;
          }
          goto LABEL_80;
        }
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v6 = (*(__int64 (__fastcall **)(struct IFailure *, BSTR *))(*(_QWORD *)a2 + 80LL))(a2, &bstrString);
      if ( v6 >= 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
        {
          v17 = L"NULL";
          if ( bstrString )
            v17 = bstrString;
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
            1037,
            "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
            " Orphan Arguments = '%s' \n",
            (const char *)v17);
        }
        if ( bstrString )
        {
          v6 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 304), bstrString);
          if ( v6 < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v7 = " Failed copying string property \n";
              v8 = 1047;
              goto LABEL_4;
            }
            goto LABEL_80;
          }
          SysFreeString(bstrString);
          bstrString = 0;
        }
        v6 = (*(__int64 (__fastcall **)(struct IFailure *, BSTR *))(*(_QWORD *)a2 + 112LL))(a2, &bstrString);
        if ( v6 >= 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
          {
            v18 = L"NULL";
            if ( bstrString )
              v18 = bstrString;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
              1068,
              "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
              " Auto Shutdown Exe = '%s' \n",
              (const char *)v18);
          }
          if ( bstrString )
          {
            v6 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 608), bstrString);
            if ( v6 < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v7 = " Failed copying string property \n";
                v8 = 1078;
                goto LABEL_4;
              }
              goto LABEL_80;
            }
            SysFreeString(bstrString);
            bstrString = 0;
          }
          v6 = (*(__int64 (__fastcall **)(struct IFailure *, BSTR *))(*(_QWORD *)a2 + 120LL))(a2, &bstrString);
          if ( v6 >= 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
            {
              if ( bstrString )
                v15 = bstrString;
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                1099,
                "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
                " Auto Shutdown arguments = '%s' \n",
                (const char *)v15);
            }
            if ( bstrString )
            {
              v6 = STRU::Copy((APP_POOL_DATA_OBJECT_APPHOST *)((char *)this + 664), bstrString);
              if ( v6 < 0 )
              {
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v7 = " Failed copying string property \n";
                  v8 = 1109;
                  goto LABEL_4;
                }
                goto LABEL_80;
              }
              SysFreeString(bstrString);
              bstrString = 0;
            }
            v24 = 0;
            v6 = (*(__int64 (__fastcall **)(struct IFailure *, __int16 *))(*(_QWORD *)a2 + 88LL))(a2, &v24);
            if ( v6 >= 0 )
            {
              v19 = g_dwDebugFlags;
              v20 = v24 == -1;
              v13 = (g_dwDebugFlags & 3) == 0;
              *((_DWORD *)this + 48) = v20;
              if ( !v13 && (v19 & 0x40000000) != 0 )
              {
                if ( !v20 )
                  v11 = L"FALSE";
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                  1132,
                  "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
                  " RFP %S \n",
                  v11);
              }
              v6 = (*(__int64 (__fastcall **)(struct IFailure *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v26);
              if ( v6 >= 0 )
              {
                v21 = v26 / 10000000 / 60;
                v22 = g_dwDebugFlags;
                v13 = (g_dwDebugFlags & 3) == 0;
                *((_DWORD *)this + 150) = v21;
                if ( !v13 && (v22 & 0x40000000) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                    1150,
                    "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
                    " Rapid Fail Protection Interval = %u (0x%X) \n",
                    v21,
                    v21);
                v6 = (*(__int64 (__fastcall **)(struct IFailure *, char *))(*(_QWORD *)a2 + 104LL))(
                       a2,
                       (char *)this + 604);
                if ( v6 >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
                      1167,
                      "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
                      " Rapid Fail Protection Max Crashes = %u (0x%X) \n",
                      *((_DWORD *)this + 151),
                      *((_DWORD *)this + 151));
                }
                else if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v8 = 1158;
                  goto LABEL_10;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v8 = 1140;
                goto LABEL_10;
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v8 = 1123;
              goto LABEL_10;
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v8 = 1091;
            goto LABEL_10;
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v8 = 1060;
          goto LABEL_10;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v8 = 1029;
        goto LABEL_10;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v8 = 998;
      goto LABEL_10;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v8 = 981;
LABEL_10:
    v7 = " Failed reading property \n";
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\apppoolstore_apphost.cxx",
      v8,
      "APP_POOL_DATA_OBJECT_APPHOST::SetFailureSettingsFromConfigStoreData",
      v6,
      v7);
  }
LABEL_80:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049c00  mov     [rsp-38h+arg_18], rbx
0x180049c05  push    rbp
0x180049c06  push    rsi
0x180049c07  push    rdi
0x180049c08  push    r12
0x180049c0a  push    r13
0x180049c0c  push    r14
0x180049c0e  push    r15
0x180049c10  mov     rbp, rsp
0x180049c13  sub     rsp, 40h
0x180049c17  xor     eax, eax
0x180049c19  mov     [rbp+bstrString], 0
0x180049c21  mov     [rbp+arg_0], ax
0x180049c25  lea     r12, [rcx+2D0h]
0x180049c2c  mov     rax, [rdx]
0x180049c2f  mov     r14, rdx
0x180049c32  mov     r15, rcx
0x180049c35  mov     [rbp+arg_10], 0
0x180049c3d  mov     rdx, r12
0x180049c40  mov     rcx, r14
0x180049c43  mov     rax, [rax+38h]
0x180049c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c4c  mov     ebx, eax
0x180049c4e  test    eax, eax
0x180049c50  jns     short loc_180049C95
0x180049c52  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049c59  jz      loc_18004A295
0x180049c5f  lea     rax, aFailedReadingL; " Failed reading load balancer capabilit"...
0x180049c66  mov     r8d, 3C4h
0x180049c6c  lea     r9, aAppPoolDataObj_15; "APP_POOL_DATA_OBJECT_APPHOST::SetFailur"...
0x180049c73  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180049c7a  mov     rcx, cs:g_pDebug
0x180049c81  mov     [rsp+40h+var_18], rax
0x180049c86  mov     dword ptr [rsp+40h+var_20], ebx
0x180049c8a  call    cs:__imp_PuDbgPrintError
0x180049c90  jmp     loc_18004A295
0x180049c95  mov     eax, cs:g_dwDebugFlags
0x180049c9b  lea     rdi, aAppPoolDataObj_15; "APP_POOL_DATA_OBJECT_APPHOST::SetFailur"...
0x180049ca2  test    al, 3
0x180049ca4  lea     rsi, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180049cab  setnz   cl
0x180049cae  bt      eax, 1Eh
0x180049cb2  setb    al
0x180049cb5  test    al, cl
0x180049cb7  jz      short loc_180049CEA
0x180049cb9  mov     eax, [r12]
0x180049cbd  mov     r9, rdi
0x180049cc0  mov     rcx, cs:g_pDebug
0x180049cc7  mov     r8d, 3CDh
0x180049ccd  mov     [rsp+40h+var_10], eax
0x180049cd1  mov     rdx, rsi
0x180049cd4  mov     dword ptr [rsp+40h+var_18], eax
0x180049cd8  lea     rax, aLoadBalancerTy; " Load Balancer Type = %u (0x%X) \n"
0x180049cdf  mov     [rsp+40h+var_20], rax
0x180049ce4  call    cs:__imp_PuDbgPrint
0x180049cea  mov     rax, [r14]
0x180049ced  lea     rdx, [rbp+arg_0]
0x180049cf1  mov     rcx, r14
0x180049cf4  mov     rax, [rax+40h]
0x180049cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cfd  mov     ebx, eax
0x180049cff  test    eax, eax
0x180049d01  jns     short loc_180049D28
0x180049d03  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049d0a  jz      loc_18004A295
0x180049d10  mov     r8d, 3D5h
0x180049d16  lea     rax, aFailedReadingP_1; " Failed reading property \n"
0x180049d1d  mov     r9, rdi
0x180049d20  mov     rdx, rsi
0x180049d23  jmp     loc_180049C7A
0x180049d28  mov     eax, cs:g_dwDebugFlags
0x180049d2e  lea     r8, aFalse_1; "FALSE"
0x180049d35  xor     edx, edx
0x180049d37  lea     r13, aTrue_1; "TRUE"
0x180049d3e  cmp     [rbp+arg_0], 0FFFFh
0x180049d43  setz    dl
0x180049d46  test    al, 3
0x180049d48  mov     [r15+0DCh], edx
0x180049d4f  setnz   cl
0x180049d52  bt      eax, 1Eh
0x180049d56  setb    al
0x180049d59  test    al, cl
0x180049d5b  jz      short loc_180049D90
0x180049d5d  mov     rcx, cs:g_pDebug
0x180049d64  test    edx, edx
0x180049d66  mov     rax, r13
0x180049d69  mov     r9, rdi
0x180049d6c  cmovz   rax, r8
0x180049d70  mov     rdx, rsi
0x180049d73  mov     [rsp+40h+var_18], rax
0x180049d78  mov     r8d, 3DEh
0x180049d7e  lea     rax, aOrphanWpS; " Orphan WP %S \n"
0x180049d85  mov     [rsp+40h+var_20], rax
0x180049d8a  call    cs:__imp_PuDbgPrint
0x180049d90  mov     rax, [r14]
0x180049d93  lea     rdx, [rbp+bstrString]
0x180049d97  mov     rcx, r14
0x180049d9a  mov     rax, [rax+48h]
0x180049d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049da3  mov     ebx, eax
0x180049da5  test    eax, eax
0x180049da7  jns     short loc_180049DC1
0x180049da9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049db0  jz      loc_18004A295
0x180049db6  mov     r8d, 3E6h
0x180049dbc  jmp     loc_180049D16
0x180049dc1  mov     eax, cs:g_dwDebugFlags
0x180049dc7  lea     r12, aNull_0; "NULL"
0x180049dce  test    al, 3
0x180049dd0  setnz   cl
0x180049dd3  bt      eax, 1Eh
0x180049dd7  setb    al
0x180049dda  test    al, cl
0x180049ddc  jz      short loc_180049E16
0x180049dde  mov     rax, [rbp+bstrString]
0x180049de2  mov     rcx, r12
0x180049de5  test    rax, rax
0x180049de8  mov     r9, rdi
0x180049deb  mov     r8d, 3EEh
0x180049df1  mov     rdx, rsi
0x180049df4  cmovnz  rcx, rax
0x180049df8  lea     rax, aOprhanExeS; " Oprhan Exe = '%s' \n"
0x180049dff  mov     [rsp+40h+var_18], rcx
0x180049e04  mov     rcx, cs:g_pDebug
0x180049e0b  mov     [rsp+40h+var_20], rax
0x180049e10  call    cs:__imp_PuDbgPrint
0x180049e16  mov     rdx, [rbp+bstrString]
0x180049e1a  test    rdx, rdx
0x180049e1d  jz      short loc_180049E63
0x180049e1f  lea     rcx, [r15+0F8h]
0x180049e26  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180049e2c  mov     ebx, eax
0x180049e2e  test    eax, eax
0x180049e30  jns     short loc_180049E51
0x180049e32  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049e39  jz      loc_18004A295
0x180049e3f  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180049e46  mov     r8d, 3F8h
0x180049e4c  jmp     loc_180049D1D
0x180049e51  mov     rcx, [rbp+bstrString]; bstrString
0x180049e55  call    cs:__imp_SysFreeString
0x180049e5b  mov     [rbp+bstrString], 0
0x180049e63  mov     rax, [r14]
0x180049e66  lea     rdx, [rbp+bstrString]
0x180049e6a  mov     rcx, r14
0x180049e6d  mov     rax, [rax+50h]
0x180049e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e76  mov     ebx, eax
0x180049e78  test    eax, eax
0x180049e7a  jns     short loc_180049E94
0x180049e7c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049e83  jz      loc_18004A295
0x180049e89  mov     r8d, 405h
0x180049e8f  jmp     loc_180049D16
0x180049e94  mov     eax, cs:g_dwDebugFlags
0x180049e9a  test    al, 3
0x180049e9c  setnz   cl
0x180049e9f  bt      eax, 1Eh
0x180049ea3  setb    al
0x180049ea6  test    al, cl
0x180049ea8  jz      short loc_180049EE2
0x180049eaa  mov     rax, [rbp+bstrString]
0x180049eae  mov     rcx, r12
0x180049eb1  test    rax, rax
0x180049eb4  mov     r9, rdi
0x180049eb7  mov     r8d, 40Dh
0x180049ebd  mov     rdx, rsi
0x180049ec0  cmovnz  rcx, rax
0x180049ec4  lea     rax, aOrphanArgument; " Orphan Arguments = '%s' \n"
0x180049ecb  mov     [rsp+40h+var_18], rcx
0x180049ed0  mov     rcx, cs:g_pDebug
0x180049ed7  mov     [rsp+40h+var_20], rax
0x180049edc  call    cs:__imp_PuDbgPrint
0x180049ee2  mov     rdx, [rbp+bstrString]
0x180049ee6  test    rdx, rdx
0x180049ee9  jz      short loc_180049F2F
0x180049eeb  lea     rcx, [r15+130h]
0x180049ef2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180049ef8  mov     ebx, eax
0x180049efa  test    eax, eax
0x180049efc  jns     short loc_180049F1D
0x180049efe  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049f05  jz      loc_18004A295
0x180049f0b  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180049f12  mov     r8d, 417h
0x180049f18  jmp     loc_180049D1D
0x180049f1d  mov     rcx, [rbp+bstrString]; bstrString
0x180049f21  call    cs:__imp_SysFreeString
0x180049f27  mov     [rbp+bstrString], 0
0x180049f2f  mov     rax, [r14]
0x180049f32  lea     rdx, [rbp+bstrString]
0x180049f36  mov     rcx, r14
0x180049f39  mov     rax, [rax+70h]
0x180049f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f42  mov     ebx, eax
0x180049f44  test    eax, eax
0x180049f46  jns     short loc_180049F60
0x180049f48  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049f4f  jz      loc_18004A295
0x180049f55  mov     r8d, 424h
0x180049f5b  jmp     loc_180049D16
0x180049f60  mov     eax, cs:g_dwDebugFlags
0x180049f66  test    al, 3
0x180049f68  setnz   cl
0x180049f6b  bt      eax, 1Eh
0x180049f6f  setb    al
0x180049f72  test    al, cl
0x180049f74  jz      short loc_180049FAE
0x180049f76  mov     rax, [rbp+bstrString]
0x180049f7a  mov     rcx, r12
0x180049f7d  test    rax, rax
0x180049f80  mov     r9, rdi
0x180049f83  mov     r8d, 42Ch
0x180049f89  mov     rdx, rsi
0x180049f8c  cmovnz  rcx, rax
0x180049f90  lea     rax, aAutoShutdownEx; " Auto Shutdown Exe = '%s' \n"
0x180049f97  mov     [rsp+40h+var_18], rcx
0x180049f9c  mov     rcx, cs:g_pDebug
0x180049fa3  mov     [rsp+40h+var_20], rax
0x180049fa8  call    cs:__imp_PuDbgPrint
0x180049fae  mov     rdx, [rbp+bstrString]
0x180049fb2  test    rdx, rdx
0x180049fb5  jz      short loc_180049FFB
0x180049fb7  lea     rcx, [r15+260h]
0x180049fbe  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180049fc4  mov     ebx, eax
0x180049fc6  test    eax, eax
0x180049fc8  jns     short loc_180049FE9
0x180049fca  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180049fd1  jz      loc_18004A295
0x180049fd7  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180049fde  mov     r8d, 436h
0x180049fe4  jmp     loc_180049D1D
0x180049fe9  mov     rcx, [rbp+bstrString]; bstrString
0x180049fed  call    cs:__imp_SysFreeString
0x180049ff3  mov     [rbp+bstrString], 0
0x180049ffb  mov     rax, [r14]
0x180049ffe  lea     rdx, [rbp+bstrString]
0x18004a002  mov     rcx, r14
0x18004a005  mov     rax, [rax+78h]
0x18004a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a00e  mov     ebx, eax
0x18004a010  test    eax, eax
0x18004a012  jns     short loc_18004A02C
0x18004a014  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a01b  jz      loc_18004A295
0x18004a021  mov     r8d, 443h
0x18004a027  jmp     loc_180049D16
0x18004a02c  mov     eax, cs:g_dwDebugFlags
0x18004a032  test    al, 3
0x18004a034  setnz   cl
0x18004a037  bt      eax, 1Eh
0x18004a03b  setb    al
0x18004a03e  test    al, cl
0x18004a040  jz      short loc_18004A077
0x18004a042  mov     rax, [rbp+bstrString]
0x18004a046  mov     r9, rdi
0x18004a049  mov     rcx, cs:g_pDebug
0x18004a050  test    rax, rax
0x18004a053  mov     r8d, 44Bh
0x18004a059  mov     rdx, rsi
0x18004a05c  cmovnz  r12, rax
0x18004a060  lea     rax, aAutoShutdownAr; " Auto Shutdown arguments = '%s' \n"
0x18004a067  mov     [rsp+40h+var_18], r12
0x18004a06c  mov     [rsp+40h+var_20], rax
0x18004a071  call    cs:__imp_PuDbgPrint
0x18004a077  mov     rdx, [rbp+bstrString]
0x18004a07b  test    rdx, rdx
0x18004a07e  jz      short loc_18004A0C4
0x18004a080  lea     rcx, [r15+298h]
0x18004a087  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004a08d  mov     ebx, eax
0x18004a08f  test    eax, eax
0x18004a091  jns     short loc_18004A0B2
0x18004a093  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a09a  jz      loc_18004A295
0x18004a0a0  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x18004a0a7  mov     r8d, 455h
0x18004a0ad  jmp     loc_180049D1D
0x18004a0b2  mov     rcx, [rbp+bstrString]; bstrString
0x18004a0b6  call    cs:__imp_SysFreeString
0x18004a0bc  mov     [rbp+bstrString], 0
0x18004a0c4  xor     eax, eax
0x18004a0c6  lea     rdx, [rbp+arg_0]
0x18004a0ca  mov     [rbp+arg_0], ax
0x18004a0ce  mov     rcx, r14
0x18004a0d1  mov     rax, [r14]
0x18004a0d4  mov     rax, [rax+58h]
0x18004a0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0dd  mov     ebx, eax
0x18004a0df  test    eax, eax
0x18004a0e1  jns     short loc_18004A0FB
0x18004a0e3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004a0ea  jz      loc_18004A295
0x18004a0f0  mov     r8d, 463h
0x18004a0f6  jmp     loc_180049D16
0x18004a0fb  mov     eax, cs:g_dwDebugFlags
0x18004a101  xor     edx, edx
0x18004a103  cmp     [rbp+arg_0], 0FFFFh
0x18004a108  mov     r12b, 3
  ... truncated ...
```
